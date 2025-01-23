Certainly! Below is a detailed and expansive TypeScript code that outlines the creation of a comprehensive "Duty of Care" page for Navan, designed with beautiful ShadCN components in mind. The code includes various sections of the page as outlined, with a focus on rich descriptive text, features, use cases, a detailed FAQ section, and more. 

This example assumes you're using a React-based application with TypeScript and Tailwind CSS, leveraging ShadCN components.

```typescript
import React from 'react';
import { Hero, Features, Benefits, UseCases, Testimonials, Faq, Footer, CallToAction } from './components'; // Assuming you have these components created
import { Button, Card, Icon } from 'shadcn'; // Example imports from ShadCN components

const DutyOfCarePage: React.FC = () => {
    return (
        <div className="bg-white text-gray-900">
            {/* Hero Section */}
            <Hero
                headline="Your Employees’ Safety, Our Priority: Navan’s Duty of Care Solutions"
                subheadline="Proactively monitor trips, ensure compliance, and provide real-time support to keep your team safe and informed—wherever they are in the world."
                backgroundImage="/path/to/hero-image.jpg" // Replace with actual image path
                ctaButtons={[
                    { text: "Learn More", link: "#features" },
                    { text: "Request a Demo", link: "#request-demo" },
                    { text: "Contact Us", link: "/contact" },
                ]}
            />

            {/* Key Features Section */}
            <section id="features">
                <h2 className="text-3xl font-bold text-center my-8">Key Features</h2>
                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    {keyFeatures.map((feature, index) => (
                        <Card key={index} className="shadow-md p-5 hover:bg-gray-100">
                            <Icon name={feature.icon} className="text-4xl mb-4" />
                            <h3 className="font-semibold text-lg">{feature.headline}</h3>
                            <p>{feature.description}</p>
                        </Card>
                    ))}
                </div>
            </section>

            {/* Benefits Section */}
            <section className="bg-gray-100 py-10">
                <h2 className="text-3xl font-bold text-center mb-8">Benefits of Navan’s Duty of Care</h2>
                <div className="flex flex-col md:flex-row justify-center">
                    {benefits.map((benefit, index) => (
                        <div key={index} className="bg-white m-4 p-6 rounded-lg shadow-md flex-1">
                            <h3 className="text-xl font-semibold">{benefit.title}</h3>
                            <p>{benefit.description}</p>
                        </div>
                    ))}
                </div>
            </section>

            {/* Use Cases Section */}
            <section id="use-cases">
                <h2 className="text-3xl font-bold text-center my-8">Real-World Use Cases</h2>
                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    {useCases.map((useCase, index) => (
                        <Card key={index} className="shadow-md p-5">
                            <h3 className="font-semibold text-lg">{useCase.title}</h3>
                            <p>{useCase.description}</p>
                        </Card>
                    ))}
                </div>
            </section>

            {/* Testimonials Section */}
            <section id="testimonials" className="bg-gray-100 py-10">
                <h2 className="text-3xl font-bold text-center mb-8">What Our Clients Say</h2>
                <div className="flex flex-col md:flex-row justify-center">
                    {testimonials.map((testimony, index) => (
                        <Card key={index} className="bg-white m-4 p-6 rounded-lg shadow-md flex-1">
                            <blockquote className="italic">{testimony.quote}</blockquote>
                            <cite className="block mt-2 font-semibold">{testimony.author}</cite>
                        </Card>
                    ))}
                </div>
            </section>

            {/* FAQ Section */}
            <section id="faq" className="bg-gray-200 py-10">
                <h2 className="text-3xl font-bold text-center mb-8">Frequently Asked Questions</h2>
                <div className="max-w-3xl mx-auto">
                    {faqs.map((faq, index) => (
                        <div key={index} className="border-b py-4">
                            <h3 className="font-semibold">{faq.question}</h3>
                            <p>{faq.answer}</p>
                        </div>
                    ))}
                </div>
            </section>

            {/* Call to Action Section */}
            <CallToAction
                headline="Ready to Prioritize Your Employees’ Safety?"
                description="Discover how Navan’s duty of care solutions can protect your team and streamline your travel program."
                ctaButtons={[
                    { text: "Request a Demo", link: "#request-demo" },
                    { text: "Contact Us", link: "/contact" },
                ]}
            />

            {/* Footer Section */}
            <Footer
                links={[
                    { text: "Learn More About Navan Travel", link: "/travel" },
                    { text: "Explore Our Expense Management Solutions", link: "/expense-management" },
                    { text: "Read Our Blog on Travel Safety", link: "/blog/travel-safety" },
                    { text: "Download Our Duty of Care Whitepaper", link: "/whitepaper/duty-of-care" },
                ]}
            />
        </div>
    );
};

// Sample Data
const keyFeatures = [
    {
        icon: 'globe',
        headline: "Track Travelers in Real Time",
        description: "Monitor employee locations and itineraries in real time, with instant alerts for delays, cancellations, or emergencies."
    },
    {
        icon: 'bell',
        headline: "Stay Ahead of Disruptions",
        description: "Receive proactive alerts about flight delays, weather disruptions, or security risks, ensuring employees are always informed."
    },
    {
        icon: 'headset',
        headline: "24/7 Traveler Support",
        description: "Access to a dedicated support team available around the clock to assist with emergencies, rebookings, or travel changes."
    },
    {
        icon: 'shield',
        headline: "Mitigate Risks Effectively",
        description: "Identify and mitigate potential risks with tools that monitor global events, health advisories, and security threats."
    },
    {
        icon: 'checklist',
        headline: "Ensure Policy Compliance",
        description: "Automatically enforce travel policies and ensure employees book within approved guidelines, reducing risks and costs."
    },
    {
        icon: 'cross',
        headline: "Emergency Response",
        description: "Immediate access to emergency assistance, including medical support, evacuation services, and crisis management."
    }
];

const benefits = [
    {
        title: "Empower Your Team with Confidence",
        description: "Gain peace of mind knowing your employees are safe and supported, while maintaining control over travel policies and budgets."
    },
    {
        title: "Travel with Peace of Mind",
        description: "Enjoy a seamless travel experience with real-time updates, 24/7 support, and tools to stay safe and informed."
    },
    {
        title: "Protect Your People and Your Business",
        description: "Reduce risks, ensure compliance, and demonstrate your commitment to employee safety with Navan’s duty of care solutions."
    }
];

const useCases = [
    {
        title: "Managing Complex Travel Programs",
        description: "Navan helps global enterprises monitor thousands of travelers across multiple regions, ensuring compliance and safety at scale."
    },
    {
        title: "Simplifying Travel Safety for Small Teams",
        description: "Even small teams can benefit from Navan’s duty of care tools, with easy-to-use features that don’t require a dedicated travel manager."
    },
    {
        title: "Navigating High-Risk Travel",
        description: "Navan provides real-time alerts and emergency support for employees traveling to high-risk destinations, ensuring their safety at all times."
    }
];

const testimonials = [
    {
        quote: "Navan’s duty of care tools have been a game-changer for our organization. We can now monitor our employees’ safety in real time, no matter where they are in the world.",
        author: "Jane Doe, Travel Manager at XYZ Corporation"
    },
    // Add more testimonials as needed
];

const faqs = [
    {
        question: "What is Duty of Care?",
        answer: "Duty of Care refers to the legal and moral obligation of employers to ensure the safety and well-being of their employees while they are traveling for work."
    },
    {
        question: "How does Navan ensure compliance?",
        answer: "Navan automates travel policy compliance by integrating with existing systems and providing real-time alerts and monitoring."
    },
    // Add more FAQs as needed
];

export default DutyOfCarePage;
```

### Explanation of the Code Structure:

1. **Hero Section**:
   - This section introduces the page with a strong headline, subheadline, and call-to-action buttons.

2. **Key Features Section**:
   - Displays key features of the duty of care solution in a visually engaging grid format.

3. **Benefits Section**:
   - Outlines the benefits for different stakeholders (travel managers, employees, organizations) in a two-column layout.

4. **Use Cases Section**:
   - Provides real-world use cases showcasing how Navan’s solutions effectively address specific challenges.

5. **Testimonials Section**:
   - Builds credibility with customer testimonials and quotes from real users.

6. **FAQ Section**:
   - Answers common questions related to duty of care, helping to clarify any uncertainties potential customers may have.

7. **Call-to-Action Section**:
   - Encourages users to take the next steps, either requesting a demo or contacting Navan.

8. **Footer Section**:
   - Contains links to related resources, enhancing navigation and providing additional information.

### Design and Component Choices:

- **ShadCN Components**: Utilizes ShadCN components like `Button`, `Card`, and `Icon` to maintain a consistent and modern UI.
- **Tailwind CSS**: Ensures responsive design and utility-first styling for quick adjustments.
- **Rich Text**: The content is rich in descriptive text, providing depth and clarity about Navan’s offerings.

This structure not only meets the requirement for a comprehensive page but also ensures a user-friendly experience that clearly articulates the value proposition of Navan’s duty of care solutions.