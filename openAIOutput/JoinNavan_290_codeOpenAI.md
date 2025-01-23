Certainly! Below is a comprehensive TypeScript code that incorporates the structure you provided for the **Global Capabilities** page on Navan’s website. The aim is to create a well-structured, functional, and visually appealing page that reflects Navan's global reach and capabilities. This code will utilize Node.js principles, along with Shadcn components for the UI design.

### TypeScript Code for the Global Capabilities Page

```typescript
import express from 'express';
import path from 'path';
import { renderToString } from 'react-dom/server';
import React from 'react';
import { Helmet } from 'react-helmet';
import GlobalCapabilitiesPage from './components/GlobalCapabilitiesPage';

const app = express();
const PORT = process.env.PORT || 3000;

// Serve static files
app.use('/static', express.static(path.join(__dirname, 'public')));

// Route to render the Global Capabilities page
app.get('/', (req, res) => {
    const helmet = Helmet.renderStatic();
    const content = renderToString(<GlobalCapabilitiesPage />);
    
    res.send(`
        <!DOCTYPE html>
        <html lang="en">
        <head>
            ${helmet.title.toString()}
            ${helmet.meta.toString()}
            <link rel="stylesheet" href="/static/styles.css">
        </head>
        <body>
            <div id="app">${content}</div>
            <script src="/static/bundle.js"></script>
        </body>
        </html>
    `);
});

// Start the server
app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
```

### GlobalCapabilitiesPage Component

```tsx
// components/GlobalCapabilitiesPage.tsx
import React from 'react';
import HeroSection from './HeroSection';
import KeyFeaturesSection from './KeyFeaturesSection';
import GlobalReachSection from './GlobalReachSection';
import IndustrySpecificSolutions from './IndustrySpecificSolutions';
import IntegrationEcosystem from './IntegrationEcosystem';
import SustainabilitySection from './SustainabilitySection';
import TestimonialsSection from './TestimonialsSection';
import GlobalSupportSection from './GlobalSupportSection';
import Footer from './Footer';

const GlobalCapabilitiesPage: React.FC = () => {
    return (
        <div>
            <HeroSection />
            <KeyFeaturesSection />
            <GlobalReachSection />
            <IndustrySpecificSolutions />
            <IntegrationEcosystem />
            <SustainabilitySection />
            <TestimonialsSection />
            <GlobalSupportSection />
            <Footer />
        </div>
    );
};

export default GlobalCapabilitiesPage;
```

### HeroSection Component

```tsx
// components/HeroSection.tsx
import React from 'react';
import { Button } from 'shadcn-ui';

const HeroSection: React.FC = () => {
    return (
        <section className="hero-section">
            <div className="hero-content">
                <h1>Global Capabilities: Empowering Businesses Worldwide</h1>
                <p>From local teams to global enterprises, Navan provides seamless travel and expense solutions tailored to your needs, no matter where you operate.</p>
                <Button onClick={() => window.location.href = '/demo'}>Explore Our Global Solutions</Button>
                <Button onClick={() => window.location.href = '/contact'}>Contact Us for Global Support</Button>
            </div>
            <div className="hero-image">
                <img src="/static/images/global-presence.jpg" alt="Global Presence" />
            </div>
            <div className="trust-indicators">
                <span>Trusted by 10,000+ companies worldwide</span>
                <span>Supporting businesses in 150+ countries</span>
            </div>
        </section>
    );
};

export default HeroSection;
```

### KeyFeaturesSection Component

```tsx
// components/KeyFeaturesSection.tsx
import React from 'react';

const KeyFeaturesSection: React.FC = () => {
    const features = [
        {
            title: 'Global Inventory Access',
            description: 'Access to millions of flights, hotels, and ground transportation options worldwide.',
            icon: '🌎'
        },
        {
            title: 'Multi-Language Support',
            description: 'Available in 20+ languages, ensuring a seamless experience for your global workforce.',
            icon: '🌐'
        },
        {
            title: 'Localized Content and Support',
            description: 'Regional expertise and 24/7 support in local languages.',
            icon: '💬'
        },
        {
            title: 'Multi-Currency Expense Management',
            description: 'Automated currency conversion and real-time expense tracking in 100+ currencies.',
            icon: '💱'
        },
        {
            title: 'Global Compliance and Security',
            description: 'Adherence to local regulations and global security standards, including GDPR and SOC 2.',
            icon: '🔒'
        }
    ];

    return (
        <section className="key-features-section">
            <h2>Key Features</h2>
            <div className="features-grid">
                {features.map((feature, index) => (
                    <div key={index} className="feature-card">
                        <span className="feature-icon">{feature.icon}</span>
                        <h3>{feature.title}</h3>
                        <p>{feature.description}</p>
                    </div>
                ))}
            </div>
        </section>
    );
};

export default KeyFeaturesSection;
```

### GlobalReachSection Component

```tsx
// components/GlobalReachSection.tsx
import React from 'react';

const GlobalReachSection: React.FC = () => {
    return (
        <section className="global-reach-section">
            <h2>Global Reach and Regional Expertise</h2>
            <p>Explore our presence in various regions and discover how we tailor solutions to meet local needs.</p>
            <div className="interactive-map">
                {/* Interactive map component to be implemented here */}
            </div>
            <div className="regional-case-studies">
                {/* Case studies to be listed here */}
            </div>
        </section>
    );
};

export default GlobalReachSection;
```

### IndustrySpecificSolutions Component

```tsx
// components/IndustrySpecificSolutions.tsx
import React from 'react';

const IndustrySpecificSolutions: React.FC = () => {
    const industries = [
        {
            name: 'Energy & Utilities',
            description: 'Track project expenses across multiple countries with real-time insights and automated compliance checks.'
        },
        {
            name: 'Technology',
            description: 'Manage travel and expenses efficiently for teams operating on a global scale.'
        },
        {
            name: 'Retail',
            description: 'Optimize inventory and travel expenses for retail chains operating in multiple regions.'
        },
        {
            name: 'Professional Services',
            description: 'Streamline travel management for consultants and professionals working across borders.'
        }
    ];

    return (
        <section className="industry-specific-solutions">
            <h2>Industry-Specific Solutions</h2>
            <div className="industry-tiles">
                {industries.map((industry, index) => (
                    <div key={index} className="industry-tile">
                        <h3>{industry.name}</h3>
                        <p>{industry.description}</p>
                    </div>
                ))}
            </div>
        </section>
    );
};

export default IndustrySpecificSolutions;
```

### IntegrationEcosystem Component

```tsx
// components/IntegrationEcosystem.tsx
import React from 'react';

const IntegrationEcosystem: React.FC = () => {
    return (
        <section className="integration-ecosystem">
            <h2>Global Integration Ecosystem</h2>
            <p>Navan seamlessly integrates with a variety of systems to streamline your global operations.</p>
            <div className="integration-partners">
                {/* Logos of integration partners to be displayed here */}
            </div>
            <button onClick={() => window.location.href = '/api'}>Learn More About Our API</button>
        </section>
    );
};

export default IntegrationEcosystem;
```

### SustainabilitySection Component

```tsx
// components/SustainabilitySection.tsx
import React from 'react';

const SustainabilitySection: React.FC = () => {
    return (
        <section className="sustainability-section">
            <h2>Sustainability and Global Responsibility</h2>
            <p>Navan is committed to promoting sustainable practices in business travel.</p>
            <div className="sustainability-features">
                <div className="feature">
                    <h3>Carbon Emissions Tracking</h3>
                    <p>Track and manage your company’s carbon footprint across global operations.</p>
                </div>
                <div className="feature">
                    <h3>Sustainable Travel Options</h3>
                    <p>Access to sustainable aviation fuel (SAF) and rail alternatives in supported regions.</p>
                </div>
                <div className="feature">
                    <h3>Global Partnerships</h3>
                    <p>Collaborating with global organizations to promote sustainable travel practices.</p>
                </div>
            </div>
        </section>
    );
};

export default SustainabilitySection;
```

### TestimonialsSection Component

```tsx
// components/TestimonialsSection.tsx
import React from 'react';

const TestimonialsSection: React.FC = () => {
    const testimonials = [
        {
            quote: "Navan has transformed how we manage travel and expenses across 30 countries. The platform is intuitive, and the support is exceptional.",
            company: "Company Name",
            region: "Region"
        },
        {
            quote: "Thanks to Navan, we have streamlined our travel processes and improved our expense management significantly.",
            company: "Another Company",
            region: "Another Region"
        }
    ];

    return (
        <section className="testimonials-section">
            <h2>Testimonials and Global Success Stories</h2>
            <div className="testimonial-cards">
                {testimonials.map((testimonial, index) => (
                    <div key={index} className="testimonial-card">
                        <p>"{testimonial.quote}"</p>
                        <span>- {testimonial.company}, {testimonial.region}</span>
                    </div>
                ))}
            </div>
        </section>
    );
};

export default TestimonialsSection;
```

### GlobalSupportSection Component

```tsx
// components/GlobalSupportSection.tsx
import React from 'react';

const GlobalSupportSection: React.FC = () => {
    return (
        <section className="global-support-section">
            <h2>Global Support and Resources</h2>
            <p>Our support team is available around the clock to assist with travel disruptions, expense issues, and platform questions.</p>
            <button onClick={() => window.location.href = '/support'}>Contact Global Support</button>
            <div className="resource-links">
                <a href="/resources/travel-policies">Travel Policies</a>
                <a href="/resources/compliance-guides">Compliance Guides</a>
                <a href="/resources/expense-templates">Expense Templates</a>
            </div>
        </section>
    );
};

export default GlobalSupportSection;
```

### Footer Component

```tsx
// components/Footer.tsx
import React from 'react';

const Footer: React.FC = () => {
    return (
        <footer className="footer">
            <div className="footer-links">
                <a href="/solutions/regions">Explore Regional Solutions</a>
                <a href="/contact">Contact Global Support</a>
                <a href="/case-studies">View Our Global Case Studies</a>
            </div>
            <div className="language-selector">
                <label htmlFor="language">Language:</label>
                <select id="language" name="language">
                    <option value="en">English</option>
                    <option value="es">Español</option>
                    {/* More language options */}
                </select>
            </div>
            <div className="social-media-links">
                {/* Social media icons */}
            </div>
        </footer>
    );
};

export default Footer;
```

### Styling and Design Considerations

The styling for the above components should be handled through CSS or a CSS-in-JS solution, ensuring a clean and visually appealing layout that aligns with Navan’s branding. Here are some suggestions:

- Use a consistent color palette that reflects Navan's branding, utilizing earth tones to emphasize sustainability.
- Implement responsive design principles, ensuring that the layout is adaptable to different screen sizes.
- Utilize Shadcn components for interactive elements like buttons, modals, and tooltips.
- Incorporate high-quality images and icons that resonate with the global theme.

### Conclusion

The above code structure embodies a comprehensive, immersive experience for users navigating the **Global Capabilities** page of Navan’s website. With rich text, interactive elements, and beautiful UI components in mind, this implementation not only serves to inform users but also encourages engagement and fosters trust in Navan's global offerings. The modular approach allows for easy updates and maintenance, thereby ensuring the page remains relevant and effective in communicating Navan's value proposition. 

Feel free to expand further on any specific sections, implement additional features, or refine the UI design based on your exact requirements!