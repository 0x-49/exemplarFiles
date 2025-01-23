Certainly! Below is a comprehensive TypeScript code that embodies the outlined structure for the Helium 10 Follow-Up Tool page. It leverages Node.js and utilizes the Shadcn components to create a visually appealing and user-friendly interface. The code is designed to be modular and maintainable, with each section encapsulated in its own component. The text is embellished with rich, persuasive copy, and the layout is enhanced for an immaculate user experience.

### TypeScript Code for Helium 10 Follow-Up Tool Page

```typescript
import React from 'react';
import { Hero, KeyFeatures, Benefits, HowItWorks, Testimonials, Pricing, FAQ, Footer } from './components';
import { Button, Carousel, Card, Grid, Accordion, Marquee } from 'shadcn';

const FollowUpToolPage: React.FC = () => {
  return (
    <div className="bg-white">
      {/* Hero Section */}
      <Hero 
        headline="Automate Your Amazon Email Marketing with Follow-Up"
        subheadline="Increase reviews, boost seller feedback, and drive repeat purchases with automated, customizable email campaigns."
        primaryCTA="Start Your Free Trial"
        secondaryCTA="Watch Demo"
        heroImage="/images/hero-image.png"
      />

      {/* Marquee for Promotions */}
      <Marquee text="Join 4 Million+ Sellers Using Helium 10!" />

      {/* Key Features Section */}
      <section className="py-16 bg-gray-100">
        <h2 className="text-3xl font-bold text-center mb-8">Key Features</h2>
        <Grid>
          <KeyFeatures features={[
            {
              title: "Automated Email Campaigns",
              description: "Set up automated email sequences to engage customers after purchase, increasing the likelihood of reviews and feedback.",
              icon: "/icons/automated-emails.png"
            },
            {
              title: "Customizable Templates",
              description: "Choose from pre-designed email templates or create your own to match your brand's voice and style.",
              icon: "/icons/customizable-templates.png"
            },
            {
              title: "A/B Testing",
              description: "Test different email subject lines, content, and CTAs to optimize open and response rates.",
              icon: "/icons/ab-testing.png"
            },
            {
              title: "Review Monitoring",
              description: "Track customer reviews and feedback in real-time, ensuring compliance with Amazon's policies.",
              icon: "/icons/review-monitoring.png"
            },
            {
              title: "Performance Analytics",
              description: "Monitor campaign performance with detailed metrics, including open rates, click-through rates, and review conversion rates.",
              icon: "/icons/performance-analytics.png"
            }
          ]} />
        </Grid>
      </section>

      {/* Benefits Section */}
      <section className="py-16 bg-white">
        <h2 className="text-3xl font-bold text-center mb-8">Benefits</h2>
        <div className="flex flex-col space-y-8">
          {[
            {
              challenge: "Manually sending follow-up emails is time-consuming and inefficient.",
              solution: "Automate your email campaigns to save time and focus on growing your business."
            },
            {
              challenge: "Low review rates can hurt your product's visibility and credibility.",
              solution: "Increase review rates with personalized, timely follow-up emails."
            },
            {
              challenge: "Amazon's strict policies make it difficult to request reviews without violating terms of service.",
              solution: "Follow-Up ensures compliance with Amazon's guidelines, reducing the risk of penalties."
            }
          ].map((item, index) => (
            <div key={index} className="bg-blue-50 p-4 rounded-md shadow-md">
              <h3 className="text-xl font-bold">{item.challenge}</h3>
              <p className="mt-2">{item.solution}</p>
            </div>
          ))}
        </div>
      </section>

      {/* How It Works Section */}
      <section className="py-16 bg-gray-200">
        <h2 className="text-3xl font-bold text-center mb-8">How It Works</h2>
        <div className="flex flex-col items-center">
          {[
            "Set Up Your Campaign: Choose a template or create your own email sequence.",
            "Customize Your Emails: Personalize your messages with dynamic fields like the customer's name and product details.",
            "Launch Your Campaign: Automate your emails to send at optimal times, based on customer purchase behavior.",
            "Track Results: Monitor campaign performance and make adjustments to improve outcomes."
          ].map((step, index) => (
            <div key={index} className="bg-white p-4 rounded-md shadow-md mb-4">
              <span className="font-bold">{index + 1}.</span> {step}
            </div>
          ))}
        </div>
      </section>

      {/* Testimonials Section */}
      <section className="py-16 bg-white">
        <h2 className="text-3xl font-bold text-center mb-8">Testimonials</h2>
        <Carousel>
          {[
            {
              name: "Sarah T.",
              quote: "Follow-Up has been a game-changer for my business. My review rates have doubled, and I’ve seen a significant increase in repeat customers.",
              image: "/images/sarah.png"
            },
            {
              name: "John D.",
              quote: "The customizable templates and A/B testing features have helped me optimize my email campaigns like never before.",
              image: "/images/john.png"
            }
          ].map((testimonial, index) => (
            <Card key={index} className="p-4">
              <img src={testimonial.image} alt={testimonial.name} className="rounded-full w-16 h-16 mb-2" />
              <p className="font-italic">"{testimonial.quote}"</p>
              <p className="font-bold mt-2">{testimonial.name}</p>
            </Card>
          ))}
        </Carousel>
      </section>

      {/* Pricing Section */}
      <section className="py-16 bg-gray-100">
        <h2 className="text-3xl font-bold text-center mb-8">Pricing Plans</h2>
        <Grid>
          {[
            {
              plan: "Starter Plan",
              description: "Ideal for new sellers. Includes basic email templates and campaign automation.",
              price: "$29/month"
            },
            {
              plan: "Pro Plan",
              description: "For growing businesses. Adds A/B testing, advanced analytics, and priority support.",
              price: "$79/month"
            },
            {
              plan: "Enterprise Plan",
              description: "For established brands. Includes custom templates, dedicated account management, and API access.",
              price: "$149/month"
            }
          ].map((pricing, index) => (
            <Card key={index} className="p-4">
              <h3 className="text-lg font-bold">{pricing.plan}</h3>
              <p>{pricing.description}</p>
              <p className="text-xl font-bold">{pricing.price}</p>
              <Button className="mt-4">Choose Plan</Button>
            </Card>
          ))}
        </Grid>
      </section>

      {/* FAQ Section */}
      <section className="py-16 bg-white">
        <h2 className="text-3xl font-bold text-center mb-8">Frequently Asked Questions</h2>
        <Accordion>
          {[
            {
              question: "Is Follow-Up compliant with Amazon's policies?",
              answer: "Yes, Follow-Up is designed to comply with Amazon's guidelines to ensure that your campaigns are safe and effective."
            },
            {
              question: "Can I customize the timing of my email campaigns?",
              answer: "Absolutely! You can set your emails to send at optimal times based on customer behavior."
            },
            {
              question: "What metrics can I track with Follow-Up?",
              answer: "You can track open rates, click-through rates, review conversion rates, and more!"
            }
          ].map((faq, index) => (
            <Accordion.Item key={index} title={faq.question}>
              {faq.answer}
            </Accordion.Item>
          ))}
        </Accordion>
      </section>

      {/* Footer Section */}
      <Footer>
        <div className="flex justify-between p-4 bg-gray-800 text-white">
          <div>© 2023 Helium 10. All rights reserved.</div>
          <div>
            <span>Follow Us:</span>
            <a href="/social" className="ml-2">Social Links</a>
          </div>
        </div>
      </Footer>
    </div>
  );
};

export default FollowUpToolPage;
```

### Explanation of Key Features

1. **Hero Section:** The hero section captures user attention with a strong headline and subheadline, encouraging them to engage further via clear CTAs.

2. **Marquee:** An attention-grabbing marquee promotes the value proposition of Helium 10, instilling trust and credibility.

3. **Key Features Section:** This section employs a grid layout to present the core functionalities of the Follow-Up tool, making it easy for users to digest the essential features at a glance.

4. **Benefits Section:** It highlights how the tool addresses the common pain points faced by Amazon sellers, providing a clear solution-oriented approach.

5. **How It Works Section:** A step-by-step guide simplifies the user learning curve, making the process transparent and approachable.

6. **Testimonials Section:** Real-world success stories help build trust, encouraging prospective users to envision their success with the tool.

7. **Pricing Section:** A clear breakdown of pricing options helps users make informed decisions about which plan suits their needs.

8. **FAQ Section:** This section addresses common concerns, reassuring potential users and reducing barriers to entry.

9. **Footer Section:** Essential links and information ensure users have easy access to additional resources and support.

### Conclusion

This TypeScript code outlines a comprehensive, user-friendly page for the Helium 10 Follow-Up Tool, featuring rich content and interactive elements designed to enhance user engagement. Each section is thoughtfully constructed to guide potential customers through the value proposition of the tool, ultimately leading to higher conversion rates. The use of Shadcn components adds a layer of aesthetic appeal and functionality, ensuring a polished final product that meets the needs of modern web users.