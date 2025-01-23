Sure! Below is a comprehensive TypeScript implementation for the **Stora Investment Calculator** page, designed with Node.js in mind, including the use of ShadCN components to enhance the UI/UX. 

This code includes the necessary imports, structure, and components outlined in your detailed description. The project is structured to facilitate further enhancements and integrations.

### TypeScript Code for Stora Investment Calculator Page

```typescript
import React, { useState } from 'react';
import { 
    Button, 
    Input, 
    Tooltip, 
    Navbar, 
    Footer, 
    Modal 
} from 'shadcn-ui';
import './InvestmentCalculator.css'; // Assuming a CSS file for styles

const InvestmentCalculator: React.FC = () => {
    const [facilitySize, setFacilitySize] = useState<number>(0);
    const [occupancyRate, setOccupancyRate] = useState<number>(0);
    const [rentalRates, setRentalRates] = useState<number>(0);
    const [operatingCosts, setOperatingCosts] = useState<number>(0);
    const [capitalExpenditures, setCapitalExpenditures] = useState<number>(0);
    const [loanDetails, setLoanDetails] = useState<{ interestRate: number; term: number; downPayment: number }>({
        interestRate: 0,
        term: 0,
        downPayment: 0,
    });

    const [results, setResults] = useState<any>(null);
    const [showModal, setShowModal] = useState(false);

    const calculateInvestment = () => {
        // Basic calculations based on input
        const annualRevenue = facilitySize * occupancyRate * rentalRates * 12;
        const totalOperatingCosts = operatingCosts * 12;
        const netProfit = annualRevenue - totalOperatingCosts;
        const roi = (netProfit / (capitalExpenditures - loanDetails.downPayment)) * 100;
        const breakEvenPoint = capitalExpenditures / (annualRevenue - totalOperatingCosts);

        setResults({
            annualRevenue,
            netProfit,
            roi,
            breakEvenPoint,
        });
    };

    return (
        <div className="investment-calculator">
            <Navbar />
            <header className="hero-section">
                <h1>Maximize Your Self-Storage ROI with Our Investment Calculator</h1>
                <p>Forecast your annual returns, evaluate potential investments, and make data-driven decisions for your self-storage business.</p>
                <Button onClick={() => setShowModal(true)}>Start Calculating Now</Button>
            </header>

            <main>
                <section>
                    <h2>Investment Calculator Tool</h2>
                    <div className="inputs">
                        <Input
                            label="Facility Size (units)"
                            type="number"
                            value={facilitySize}
                            onChange={(e) => setFacilitySize(Number(e.target.value))}
                        />
                        <Input
                            label="Occupancy Rate (%)"
                            type="number"
                            value={occupancyRate}
                            onChange={(e) => setOccupancyRate(Number(e.target.value))}
                        />
                        <Input
                            label="Rental Rates ($)"
                            type="number"
                            value={rentalRates}
                            onChange={(e) => setRentalRates(Number(e.target.value))}
                        />
                        <Input
                            label="Operating Costs ($/month)"
                            type="number"
                            value={operatingCosts}
                            onChange={(e) => setOperatingCosts(Number(e.target.value))}
                        />
                        <Input
                            label="Capital Expenditures ($)"
                            type="number"
                            value={capitalExpenditures}
                            onChange={(e) => setCapitalExpenditures(Number(e.target.value))}
                        />
                        <div className="loan-details">
                            <h3>Loan Details</h3>
                            <Input
                                label="Interest Rate (%)"
                                type="number"
                                value={loanDetails.interestRate}
                                onChange={(e) => setLoanDetails({ ...loanDetails, interestRate: Number(e.target.value) })}
                            />
                            <Input
                                label="Loan Term (years)"
                                type="number"
                                value={loanDetails.term}
                                onChange={(e) => setLoanDetails({ ...loanDetails, term: Number(e.target.value) })}
                            />
                            <Input
                                label="Down Payment ($)"
                                type="number"
                                value={loanDetails.downPayment}
                                onChange={(e) => setLoanDetails({ ...loanDetails, downPayment: Number(e.target.value) })}
                            />
                        </div>
                        <Button onClick={calculateInvestment}>Calculate</Button>
                    </div>
                </section>

                {results && (
                    <section className="results">
                        <h2>Calculation Results</h2>
                        <p><strong>Annual Revenue:</strong> ${results.annualRevenue.toFixed(2)}</p>
                        <p><strong>Net Profit:</strong> ${results.netProfit.toFixed(2)}</p>
                        <p><strong>ROI:</strong> {results.roi.toFixed(2)}%</p>
                        <p><strong>Break-Even Point:</strong> {results.breakEvenPoint.toFixed(2)} years</p>
                    </section>
                )}

                <section className="educational-content">
                    <h2>How It Works</h2>
                    <ol>
                        <li>Enter Your Data: Input your facility details and financial assumptions.</li>
                        <li>Review Results: Analyze the projected financial performance.</li>
                        <li>Adjust Inputs: Experiment with different scenarios to see how changes impact your ROI.</li>
                        <li>Make Decisions: Use the insights to plan your next steps.</li>
                    </ol>
                    <h3>Tips for Accurate Calculations</h3>
                    <ul>
                        <li>Use historical data to estimate occupancy rates.</li>
                        <li>Include all operating costs, even minor expenses.</li>
                        <li>Consider seasonal fluctuations in demand.</li>
                    </ul>
                </section>

                <section className="testimonials">
                    <h2>Testimonials</h2>
                    <blockquote>
                        <p>"The Investment Calculator helped us identify the most profitable unit mix for our new facility. It’s an indispensable tool!"</p>
                        <footer>- User Name, Business Name</footer>
                    </blockquote>
                </section>

                <section className="related-resources">
                    <h2>Related Resources</h2>
                    <div className="resource-links">
                        <a href="/financial-model" className="resource-card">Financial Model (Download)</a>
                        <a href="/self-storage-growth-guide" className="resource-card">Self-Storage Growth Guide</a>
                        <a href="/webinar" className="resource-card">Webinar: Maximizing ROI in Self-Storage</a>
                    </div>
                </section>
            </main>

            <Footer />
            
            <Modal open={showModal} onClose={() => setShowModal(false)}>
                <h2>Investment Calculator</h2>
                <p>Start forecasting your self-storage investment returns today!</p>
                <Button onClick={() => { calculateInvestment(); setShowModal(false); }}>Calculate Now</Button>
            </Modal>
        </div>
    );
};

export default InvestmentCalculator;
```

### Explanation of Code Structure

1. **Imports**: The code begins with imports from React and ShadCN UI components. It assumes you have a CSS file for custom styles.

2. **State Management**: 
   - Uses hooks (`useState`) to manage the inputs and results of the calculator.
   - The loan details are kept in a separate state object.

3. **Calculation Logic**:
   - The `calculateInvestment` function performs the calculations for annual revenue, net profit, ROI, and the break-even point based on user inputs.

4. **UI Structure**:
   - A header section welcomes users and provides a brief overview of the calculator.
   - Input fields are provided for users to enter their data.
   - A results section displays the calculated financial metrics.
   - Educational content and testimonials sections provide additional context and credibility.
   - Links to related resources encourage further engagement.

5. **Modal for CTA**: A modal is included to prompt users to start calculating their investment, enhancing user experience.

6. **Styling and Responsiveness**: Ensure that the CSS file includes styles for responsive design, making it accessible on various devices.

### Additional Recommendations
- **Accessibility**: Ensure that all components follow accessibility standards for better usability.
- **Testing**: Implement tests to validate the calculations and ensure the UI behaves as expected.
- **Deployment**: Use a Node.js backend to handle any server-side logic if needed (e.g., saving scenarios, user data).

This structure and code provide a solid foundation for your **Stora Investment Calculator** page, ensuring it is functional, engaging, and visually appealing. You can expand on this further by adding additional features, improving styles, or integrating it with backend services.