```typescript
import React from 'react';
import { Button, Card, Carousel, Container, Row, Col } from 'shadcn-ui';
import './VOCInfluencerProgram.css'; // Import your CSS file for custom styling

const VOCInfluencerProgram = () => {
  return (
    <Container>
      {/* 1. Hero Section */}
      <section className="hero-section">
        <h1 className="hero-title">Join the VOC AI Influencer Program and Earn Commissions!</h1>
        <p className="hero-subtitle">Promote cutting-edge AI tools for e-commerce and earn up to 20% commission on every sale!</p>
        <Button className="cta-button" onClick={() => window.location.href='/signup'}>
          Sign Up Now
        </Button>
      </section>

      {/* 2. Program Benefits Section */}
      <section className="benefits-section">
        <h2 className="section-title">Why Join the VOC AI Influencer Program?</h2>
        <Row>
          {benefits.map((benefit, index) => (
            <Col key={index} xs={12} sm={6} md={4}>
              <Card className="benefit-card">
                <img src={benefit.icon} alt={benefit.title} className="benefit-icon" />
                <h3 className="benefit-title">{benefit.title}</h3>
                <p className="benefit-description">{benefit.description}</p>
              </Card>
            </Col>
          ))}
        </Row>
      </section>

      {/* 3. How It Works Section */}
      <section className="how-it-works-section">
        <h2 className="section-title">How It Works</h2>
        <Row>
          {steps.map((step, index) => (
            <Col key={index} xs={12} sm={6} md={3}>
              <Card className="step-card">
                <img src={step.icon} alt={step.title} className="step-icon" />
                <h3 className="step-title">{step.title}</h3>
                <p className="step-description">{step.description}</p>
              </Card>
            </Col>
          ))}
        </Row>
      </section>

      {/* 4. Tools You Can Promote Section */}
      <section className="tools-section">
        <h2 className="section-title">Promote Cutting-Edge AI Tools</h2>
        <Carousel>
          {tools.map((tool, index) => (
            <Card key={index} className="tool-card">
              <img src={tool.icon} alt={tool.title} className="tool-icon" />
              <h3 className="tool-title">{tool.title}</h3>
              <p className="tool-description">{tool.description}</p>
            </Card>
          ))}
        </Carousel>
      </section>

      {/* 5. Testimonials Section */}
      <section className="testimonials-section">
        <h2 className="section-title">What Our Influencers Say</h2>
        <Carousel>
          {testimonials.map((testimonial, index) => (
            <Card key={index} className="testimonial-card">
              <img src={testimonial.photo} alt={testimonial.name} className="testimonial-photo" />
              <p className="testimonial-quote">"{testimonial.quote}"</p>
              <h4 className="testimonial-name">{testimonial.name}</h4>
              <p className="testimonial-role">{testimonial.role}</p>
            </Card>
          ))}
        </Carousel>
      </section>

      {/* 6. Call-to-Action Section */}
      <section className="cta-section">
        <h2 className="cta-title">Ready to Start Earning?</h2>
        <p className="cta-subtitle">Sign up today and start promoting VOC AI to your audience.</p>
        <Button className="cta-button" onClick={() => window.location.href='/signup'}>
          Join Now
        </Button>
      </section>

      {/* 7. Footer Section */}
      <footer className="footer-section">
        <nav className="footer-nav">
          <a href="/about">About Us</a>
          <a href="/contact">Contact</a>
          <a href="/privacy">Privacy Policy</a>
          <a href="/terms">Terms of Service</a>
        </nav>
        <div className="social-icons">
          <a href="https://youtube.com"><img src="/icons/youtube.svg" alt="YouTube" /></a>
          <a href="https://twitter.com"><img src="/icons/twitter.svg" alt="Twitter" /></a>
          <a href="https://linkedin.com"><img src="/icons/linkedin.svg" alt="LinkedIn" /></a>
          <a href="https://tiktok.com"><img src="/icons/tiktok.svg" alt="TikTok" /></a>
          <a href="https://quora.com"><img src="/icons/quora.svg" alt="Quora" /></a>
        </div>
        <p className="footer-copyright">© 2025 VOC AI Inc. All rights reserved.</p>
      </footer>
    </Container>
  );
};

// Example data for benefits, steps, tools, and testimonials
const benefits = [
  {
    title: 'High Commissions',
    description: 'Earn up to 20% commission on every sale you refer.',
    icon: '/icons/benefit-1.svg',
  },
  {
    title: 'Exclusive Resources',
    description: 'Get access to marketing materials, product demos, and training.',
    icon: '/icons/benefit-2.svg',
  },
  {
    title: 'Flexible Promotion',
    description: 'Promote VOC AI on your blog, social media, or YouTube channel.',
    icon: '/icons/benefit-3.svg',
  },
  {
    title: 'Real-Time Tracking',
    description: 'Track your earnings and performance with our dashboard.',
    icon: '/icons/benefit-4.svg',
  },
];

const steps = [
  {
    title: 'Sign Up',
    description: 'Create your influencer account in minutes.',
    icon: '/icons/step-1.svg',
  },
  {
    title: 'Get Your Link',
    description: 'Receive a unique referral link to share with your audience.',
    icon: '/icons/step-2.svg',
  },
  {
    title: 'Promote',
    description: 'Share VOC AI tools on your platform and drive traffic.',
    icon: '/icons/step-3.svg',
  },
  {
    title: 'Earn',
    description: 'Track your earnings and withdraw your commissions.',
    icon: '/icons/step-4.svg',
  },
];

const tools = [
  {
    title: 'Sentiment Analysis',
    description: 'Help businesses understand customer emotions with AI.',
    icon: '/icons/tool-1.svg',
  },
  {
    title: 'Review Analysis',
    description: 'Analyze Amazon and Shopify reviews in seconds.',
    icon: '/icons/tool-2.svg',
  },
  {
    title: 'AI Chatbot',
    description: 'Automate customer service with AI-powered chatbots.',
    icon: '/icons/tool-3.svg',
  },
  {
    title: 'Free AI Tools',
    description: 'Promote free tools like hashtag generators and FBA calculators.',
    icon: '/icons/tool-4.svg',
  },
];

const testimonials = [
  {
    name: 'Sarah T.',
    role: 'Social Media Influencer',
    quote: 'Joining the VOC AI Influencer Program was one of the best decisions I made. The tools are easy to promote, and the commissions are fantastic!',
    photo: '/images/testimonial-1.jpg',
  },
  {
    name: 'John D.',
    role: 'Tech Enthusiast',
    quote: 'The support and resources provided are top-notch. I love promoting VOC AI!',
    photo: '/images/testimonial-2.jpg',
  },
  {
    name: 'Emily R.',
    role: 'E-commerce Specialist',
    quote: 'I’ve seen great results since joining! The tools are powerful and effective.',
    photo: '/images/testimonial-3.jpg',
  },
];

export default VOCInfluencerProgram;
```

### CSS Styles (VOCInfluencerProgram.css)
```css
.hero-section {
  text-align: center;
  padding: 60px 20px;
  background: linear-gradient(135deg, #3B82F6, #F7FAFC);
  color: white;
}

.hero-title {
  font-size: 2.5rem;
  font-weight: bold;
}

.hero-subtitle {
  font-size: 1.25rem;
  margin: 20px 0;
}

.cta-button {
  background-color: #1A1A1A;
  color: white;
  padding: 15px 30px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.cta-button:hover {
  background-color: #3B82F6;
}

.benefits-section, .how-it-works-section, .tools-section, .testimonials-section, .cta-section {
  padding: 40px 20px;
  background-color: #F7FAFC;
}

.section-title {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 30px;
}

.benefit-card, .step-card, .tool-card, .testimonial-card {
  background-color: white;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.benefit-icon, .step-icon, .tool-icon, .testimonial-photo {
  width: 50px;
  height: 50px;
  margin-bottom: 10px;
}

.footer-section {
  text-align: center;
  padding: 20px;
  background-color: #1A1A1A;
  color: white;
}

.footer-nav a {
  color: #F7FAFC;
  margin: 0 15px;
  text-decoration: none;
}

.social-icons img {
  width: 24px;
  height: 24px;
  margin: 0 5px;
}
```

### Conclusion

The **VOC AI Influencer Program** page, as detailed above, combines an engaging design with a clear structure to attract influencers. Each section of the page is meticulously crafted with the user in mind, ensuring that the messaging is persuasive and the call-to-action is compelling. The use of shadcn components and CSS styling ensures a modern and visually appealing user experience. 

Incorporating these elements into your Node.js application will enhance the overall functionality and aesthetic, creating an inviting atmosphere for potential influencers. The rich text and components not only convey the value of the program but also encourage visitors to join, thereby driving engagement and conversions.

This structure allows for easy navigation and interaction, ensuring that influencers can easily understand the benefits of joining the VOC AI Influencer Program, the tools they can promote, and the steps required to get started. By providing testimonials and clear calls to action, this page serves as an effective marketing tool to expand the reach of VOC AI's offerings.