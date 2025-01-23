Creating a comprehensive webpage for **AI Avatars and Voices** on the Synthesia platform involves a blend of aesthetic design, engaging content, and functional components that all work together to deliver an exceptional user experience. Below is a detailed breakdown of the TypeScript code, using Node.js as the backend and incorporating **ShadCN components** to enrich the UI design. This code will encapsulate all elements outlined in your description while ensuring that the page is not only informative but also highly interactive and visually appealing.

### TypeScript Code for AI Avatars and Voices Page

```typescript
// Import necessary modules and components
import React from 'react';
import { HeroSection, KeyFeatures, UseCases, Benefits, Testimonials, Pricing, Footer, Navigation } from './components';
import { Button, Card, Carousel, Grid, Text } from 'shadcn';

// Main Page Component
const AIVoiceAvatarPage: React.FC = () => {
    return (
        <div className="flex flex-col min-h-screen">
            <Navigation />
            <HeroSection />
            <KeyFeatures />
            <UseCases />
            <Benefits />
            <Testimonials />
            <Pricing />
            <Footer />
        </div>
    );
};

// Hero Section Component
const HeroSection: React.FC = () => {
    return (
        <div className="bg-gradient-to-r from-blue-500 to-purple-500 p-10 text-center">
            <Text variant="h1" className="text-white font-bold text-4xl mb-3">
                Bring Your Videos to Life with 240+ AI Avatars and 140+ Voices in 120+ Languages.
            </Text>
            <Text variant="h2" className="text-white text-lg mb-5">
                Create professional, engaging videos with AI avatars that look and sound like real people—no cameras, microphones, or actors required.
            </Text>
            <Carousel>
                {/* Dynamic Avatar Carousel */}
                {avatarData.map((avatar) => (
                    <Card key={avatar.id} className="m-2">
                        <img src={avatar.image} alt={avatar.name} className="rounded-lg" />
                        <Text variant="h3" className="text-center">{avatar.name}</Text>
                    </Card>
                ))}
            </Carousel>
            <div className="mt-5">
                <Button variant="primary" className="mr-3">Create Your Free AI Video</Button>
                <Button variant="secondary">Book a Demo</Button>
            </div>
        </div>
    );
};

// Key Features Component
const KeyFeatures: React.FC = () => {
    return (
        <section className="p-10 bg-white">
            <Text variant="h2" className="text-center text-3xl mb-5">Key Features</Text>
            <Grid>
                <div className="feature-card">
                    <Text variant="h3">AI Avatars</Text>
                    <Text>Choose from 240+ diverse AI avatars that represent different ethnicities, ages, and genders.</Text>
                    <Button variant="link">Explore All Avatars</Button>
                </div>
                <div className="feature-card">
                    <Text variant="h3">AI Voices</Text>
                    <Text>Generate natural-sounding voiceovers in multiple languages, accents, and tones.</Text>
                    <Button variant="link">Listen to Voice Samples</Button>
                </div>
            </Grid>
        </section>
    );
};

// Use Cases Component
const UseCases: React.FC = () => {
    return (
        <section className="p-10 bg-gray-100">
            <Text variant="h2" className="text-center text-3xl mb-5">Transform Your Communication</Text>
            <Grid>
                {useCases.map((useCase) => (
                    <Card key={useCase.id} className="m-2">
                        <img src={useCase.image} alt={useCase.title} className="rounded-lg" />
                        <Text variant="h4">{useCase.title}</Text>
                        <Text>{useCase.description}</Text>
                    </Card>
                ))}
            </Grid>
            <Button variant="link" className="text-center">See More Use Cases</Button>
        </section>
    );
};

// Benefits Section
const Benefits: React.FC = () => {
    return (
        <section className="p-10 bg-white">
            <Text variant="h2" className="text-center text-3xl mb-5">Why Choose Synthesia?</Text>
            <Grid>
                {benefits.map((benefit) => (
                    <div key={benefit.id} className="benefit-card">
                        <Text variant="h3">{benefit.title}</Text>
                        <Text>{benefit.description}</Text>
                    </div>
                ))}
            </Grid>
            <Button variant="link" className="text-center">Get Started Today</Button>
        </section>
    );
};

// Testimonials Component
const Testimonials: React.FC = () => {
    return (
        <section className="p-10 bg-gray-100">
            <Text variant="h2" className="text-center text-3xl mb-5">Trusted by 50,000+ Teams Worldwide.</Text>
            <Carousel>
                {testimonials.map((testimonial) => (
                    <Card key={testimonial.id} className="m-2">
                        <Text>{testimonial.quote}</Text>
                        <Text className="font-bold">{testimonial.author}</Text>
                    </Card>
                ))}
            </Carousel>
            <Button variant="link" className="text-center">Read More Reviews</Button>
        </section>
    );
};

// Pricing Component
const Pricing: React.FC = () => {
    return (
        <section className="p-10 bg-white">
            <Text variant="h2" className="text-center text-3xl mb-5">Flexible Plans for Every Need</Text>
            <Grid>
                {pricingPlans.map((plan) => (
                    <Card key={plan.id} className="m-2">
                        <Text variant="h3">{plan.name}</Text>
                        <Text>{plan.details}</Text>
                        <Button variant="link">View Full Pricing</Button>
                    </Card>
                ))}
            </Grid>
        </section>
    );
};

// Footer Component
const Footer: React.FC = () => {
    return (
        <footer className="p-10 bg-gray-800 text-white text-center">
            <Text>© 2023 Synthesia - All rights reserved.</Text>
            <div>
                <Button variant="link">Privacy Policy</Button>
                <Button variant="link">Terms of Service</Button>
            </div>
        </footer>
    );
};

// Sample Data for Dynamic Rendering
const avatarData = [
    { id: 1, name: 'Maria', image: '/images/maria.png' },
    { id: 2, name: 'John', image: '/images/john.png' },
    // Add more avatars as needed
];

const useCases = [
    { id: 1, title: 'Corporate Training', description: 'Create onboarding and compliance videos.', image: '/images/corporate_training.jpg' },
    { id: 2, title: 'Marketing Campaigns', description: 'Produce multilingual promotional videos.', image: '/images/marketing_campaigns.jpg' },
    // Add more use cases as needed
];

const benefits = [
    { id: 1, title: 'Cost-Effective', description: 'Save on production costs.' },
    { id: 2, title: 'Time-Saving', description: 'Create videos in minutes.' },
    // Add more benefits as needed
];

const testimonials = [
    { id: 1, quote: 'Synthesia transformed our video production!', author: 'Jane Doe, Marketing Director' },
    { id: 2, quote: 'The AI avatars are incredibly lifelike!', author: 'John Smith, Training Manager' },
    // Add more testimonials as needed
];

const pricingPlans = [
    { id: 1, name: 'Starter', details: 'Access to 50 avatars and 10 voices.' },
    { id: 2, name: 'Pro', details: 'Access to 150 avatars and 50 voices.' },
    // Add more pricing plans as needed
];

// Exporting the main component
export default AIVoiceAvatarPage;
```

### Explanation of the Code Structure

1. **Component Structure**: The page is divided into several functional components, each representing different sections of the webpage. This modular approach allows for easier maintenance and scalability.

2. **Dynamic Data Rendering**: Arrays such as `avatarData`, `useCases`, `benefits`, `testimonials`, and `pricingPlans` are used to populate the UI dynamically. This ensures the content can be easily updated without altering the structure of the component.

3. **Use of ShadCN Components**: The code utilizes ShadCN components like `Button`, `Card`, `Grid`, and `Carousel` to create a visually appealing and consistent UI. These components help in building a modern-looking interface that is responsive and user-friendly.

4. **Styling and Layout**: Tailwind CSS classes are used for styling, ensuring that the page is not only functional but visually appealing as well. The use of responsive design principles ensures compatibility across various devices.

5. **Call-to-Action (CTA)**: Each section contains well-placed CTAs that guide users towards desired actions, such as exploring avatars, listening to voice samples, or starting a free trial.

6. **Accessibility**: The use of semantic HTML elements (like `section` and `footer`) along with appropriate alt texts for images ensures that the webpage is accessible to a wider audience, including those using assistive technologies.

### Conclusion

The above code provides a comprehensive framework for creating a dynamic, user-friendly webpage dedicated to showcasing Synthesia's AI avatars and voices. It effectively combines design, functionality, and content to deliver an exceptional user experience. By leveraging modern web technologies and design principles, Synthesia can effectively communicate its value proposition and engage its audience. 

---
This code is designed to deliver a seamless experience for users while maintaining a professional and modern aesthetic. You can expand upon this further by integrating additional functionality, such as user authentication, analytics tracking, and more advanced interactive elements as needed.