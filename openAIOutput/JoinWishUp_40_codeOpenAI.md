```typescript
// Import necessary libraries and components
import React from 'react';
import { Button, Hero, Statistics, ServiceCards, BenefitsList, CTASection, Footer } from 'shadcn-components'; // Assuming these components are from a library
import './HiringAssistantsPage.css'; // CSS for custom styling

const HiringAssistantsPage: React.FC = () => {
    return (
        <div className="hiring-assistants-page">
            {/* Hero Section */}
            <Hero
                title="80+ Experts to Choose From"
                subtitle="Hire a Virtual Recruiter from Wishup"
                leadCaptureForm={
                    <form className="lead-capture-form">
                        <input type="text" placeholder="Name" required />
                        <input type="email" placeholder="Email" required />
                        <input type="tel" placeholder="Phone Number" required />
                        <textarea placeholder="What tasks do you need help with?" required></textarea>
                        <Button text="Get Started" />
                    </form>
                }
                backgroundImage="https://example.com/background-image.jpg" // Replace with actual image URL
            />

            {/* Key Statistics Section */}
            <section className="statistics">
                <h2>Why Choose Wishup for Recruitment?</h2>
                <div className="statistics-tiles">
                    {statisticsData.map((stat) => (
                        <div className="stat-tile" key={stat.title}>
                            <img src={stat.icon} alt={stat.title} />
                            <h3>{stat.title}</h3>
                            <p>{stat.description}</p>
                        </div>
                    ))}
                </div>
            </section>

            {/* Services Offered Section */}
            <section className="services-offered">
                <h2>What Can Our Recruitment VAs Do for You?</h2>
                <div className="service-cards">
                    {serviceData.map((service) => (
                        <div className="service-card" key={service.name}>
                            <img src={service.icon} alt={service.name} />
                            <h3>{service.name}</h3>
                            <p>{service.description}</p>
                        </div>
                    ))}
                </div>
            </section>

            {/* Why Wishup? Section */}
            <section className="why-wishup">
                <h2>Why Wishup?</h2>
                <ul>
                    {benefitsData.map((benefit) => (
                        <li key={benefit.title}>
                            <img src={benefit.icon} alt={benefit.title} />
                            <strong>{benefit.title}</strong>
                            <p>{benefit.description}</p>
                        </li>
                    ))}
                </ul>
            </section>

            {/* Call-to-Action Section */}
            <CTASection
                title="Hiring Was Never This Easy!"
                steps={ctaSteps}
                ctaButtonText="Hire a Recruitment VA Now"
            />

            {/* Footer */}
            <Footer
                links={footerLinks}
                socialMediaIcons={socialMediaIcons}
                copyrightText="© 2023 Wishup. All rights reserved."
            />
        </div>
    );
};

// Sample data
const statisticsData = [
    {
        title: "80+ Recruitment Specialists",
        icon: "https://example.com/icon1.png",
        description: "Access a diverse pool of experts with specialized skills."
    },
    {
        title: "900+ Satisfied Clients",
        icon: "https://example.com/icon2.png",
        description: "Join thousands of businesses that trust Wishup for hiring."
    },
    {
        title: "60-Minute Onboarding",
        icon: "https://example.com/icon3.png",
        description: "Get started with your VA in just 60 minutes."
    }
];

const serviceData = [
    {
        name: "Talent Discovery",
        icon: "https://example.com/icon-talent-discovery.png",
        description: "Find the best candidates for your open roles."
    },
    {
        name: "HR Paperwork",
        icon: "https://example.com/icon-hr-paperwork.png",
        description: "Streamline onboarding and compliance tasks."
    },
    {
        name: "Candidate Assessment",
        icon: "https://example.com/icon-candidate-assessment.png",
        description: "Evaluate candidates based on your criteria."
    },
    {
        name: "Job Posting",
        icon: "https://example.com/icon-job-posting.png",
        description: "Create and manage job postings across platforms."
    }
];

const benefitsData = [
    {
        title: "Top 0.1% Talent",
        icon: "https://example.com/icon-top-talent.png",
        description: "Access the best recruitment specialists in the industry."
    },
    {
        title: "60-Minute Onboarding",
        icon: "https://example.com/icon-onboarding.png",
        description: "Get started with your VA in just 60 minutes."
    },
    {
        title: "Long-Term Stability",
        icon: "https://example.com/icon-stability.png",
        description: "Enjoy consistent support with no turnover issues."
    }
];

const ctaSteps = [
    {
        step: "Choose Your VA",
        icon: "https://example.com/icon-choose-va.png",
        description: "Select from our top 0.1% talent."
    },
    {
        step: "Onboard in 60 Minutes",
        icon: "https://example.com/icon-onboard.png",
        description: "Get started with your VA in just 60 minutes."
    },
    {
        step: "Scale Your Team",
        icon: "https://example.com/icon-scale-team.png",
        description: "Easily add more VAs as your needs grow."
    }
];

const footerLinks = [
    { text: "About Us", url: "/about" },
    { text: "Reviews", url: "/reviews" },
    { text: "Wishup Partners", url: "/partners" },
    { text: "Careers", url: "/careers" },
    { text: "Contact Us", url: "/contact" }
];

const socialMediaIcons = [
    { platform: "LinkedIn", url: "https://linkedin.com/in/wishup" },
    { platform: "Facebook", url: "https://facebook.com/wishup" },
    { platform: "Twitter", url: "https://twitter.com/wishup" },
    { platform: "Instagram", url: "https://instagram.com/wishup" }
];

export default HiringAssistantsPage;
```

### Detailed Overview of the Components and Features:

#### 1. Hero Section
The Hero section serves as the first impression for users visiting the Wishup Hiring Assistants page. Its purpose is to immediately communicate the value proposition. The bold headline and sub-headline work in tandem to inform users of the extensive network of virtual recruiters available for hire.

The lead capture form is designed with user experience in mind. Each input field is clearly labeled, and the CTA button is vibrant and inviting, encouraging users to engage and provide their details. The background image enhances the overall aesthetic, creating a welcoming environment.

#### 2. Key Statistics Section
Statistics build credibility. By showcasing key figures such as "80+ Recruitment Specialists" and "900+ Satisfied Clients," this section effectively communicates the trust and reliability of Wishup’s services. Each statistic tile is visually appealing, with an icon that corresponds to the message being conveyed, further enhancing user understanding.

#### 3. Services Offered Section
This section is crucial in detailing what users can expect from Wishup’s VAs. Each service card is designed to be visually distinct yet cohesive. The use of icons aids in quick recognition, allowing users to scan through services effortlessly. The short descriptions ensure that users can easily grasp the benefits of each service.

#### 4. Why Wishup? Section
In this section, Wishup differentiates itself from competitors. By focusing on unique selling points like "Top 0.1% Talent" and "60-Minute Onboarding," Wishup addresses common concerns prospective clients may have about hiring virtual assistants. The straightforward list format makes it easy to digest, ensuring that users can quickly understand the advantages.

#### 5. Call-to-Action Section
The CTA section serves as the final nudge for users to take action. The clear, bold title, along with the step-by-step guide, simplifies the process of hiring a VA, making it seem less daunting. The prominent button invites immediate engagement, reinforcing the ease of the process.

#### 6. Footer
The footer provides essential navigation links and social media icons, ensuring that users can easily explore more about Wishup. The inclusion of copyright information adds a professional touch.

### Conclusion
The Wishup Hiring Assistants Page is meticulously designed to offer a seamless user experience while effectively communicating the core value of hiring virtual assistants for recruitment tasks. Each section is thoughtfully crafted to guide users through the process, addressing potential questions and concerns while encouraging engagement. The use of visuals, statistics, and clear CTAs creates an inviting atmosphere that positions Wishup as a trustworthy partner in recruitment.

By leveraging the Shadcn component library, the page not only looks visually stunning but is also functional and responsive, ensuring that users have a positive experience regardless of the device they are using. The combination of rich text, user-friendly design, and strategic content makes this page a powerful tool for converting visitors into clients.