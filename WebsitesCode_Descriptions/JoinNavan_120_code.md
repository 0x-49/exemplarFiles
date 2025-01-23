Here's a comprehensive TypeScript implementation of the Navan DEI page leveraging shadcn components and modern UI patterns. Note that this is a conceptual implementation - you'll need to install the referenced components and adjust imports based on your actual setup:

```typescript
// app/dei/page.tsx
import { 
  HeroModern, 
  GradientText, 
  Typewriter,
  TiltedScroll,
  CardNoise,
  BentoGrid,
  AnimatedTestimonials,
  MagneticButton,
  ShinyButton,
  DockMenu,
  Accordion,
  OrbEffect,
  AnimatedGridPattern,
  SocialLinks
} from "@/components/shared/ui";
import Image from "next/image";
import Link from "next/link";

const DEIPage = () => {
  return (
    <div className="relative w-full overflow-hidden">
      {/* Orb Background Animation */}
      <OrbEffect className="absolute top-0 left-0 w-full h-[120vh] opacity-30" />

      {/* Navigation */}
      <DockMenu 
        items={[
          { id: 'pillars', label: 'Our Pillars' },
          { id: 'initiatives', label: 'Initiatives' },
          { id: 'progress', label: 'Progress' },
          { id: 'testimonials', label: 'Stories' },
          { id: 'cta', label: 'Join Us' }
        ]}
        className="fixed bottom-4 left-1/2 -translate-x-1/2 z-50"
      />

      {/* Hero Section */}
      <section className="relative h-screen flex items-center justify-center">
        <AnimatedGridPattern className="absolute inset-0 opacity-50" />
        <div className="relative z-10 max-w-7xl px-4 text-center">
          <HeroModern
            heading={
              <GradientText 
                text="Building a Workplace Where Everyone Belongs"
                from="#4F46E5" 
                to="#10B981"
                className="text-6xl font-bold leading-tight"
              />
            }
            subheading={
              <Typewriter
                text="At Navan, we believe that diversity drives innovation, equity ensures fairness, and inclusion fosters belonging."
                speed={50}
                className="text-xl mt-6 text-gray-300"
              />
            }
          />
          
          {/* Animated Scroller */}
          <div className="mt-24 animate-bounce">
            <TiltedScroll>
              <div className="w-8 h-8 border-2 border-emerald-400 rounded-full" />
            </TiltedScroll>
          </div>
        </div>
      </section>

      {/* DEI Pillars */}
      <section id="pillars" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16">
            <GradientText 
              text="Our Core Commitments"
              from="#F59E0B" 
              to="#EF4444"
            />
          </h2>
          
          <div className="grid md:grid-cols-3 gap-8">
            {['Diversity', 'Equity', 'Inclusion'].map((pillar, index) => (
              <TiltedScroll key={pillar}>
                <CardNoise className="p-8 h-full">
                  <div className="text-center">
                    <div className="w-24 h-24 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full mx-auto mb-6" />
                    <h3 className="text-2xl font-bold mb-4">{pillar}</h3>
                    <p className="text-gray-300">
                      {index === 0 && "We celebrate the unique backgrounds, perspectives, and experiences that each individual brings to Navan."}
                      {index === 1 && "We ensure fair access to opportunities, resources, and support for all employees."}
                      {index === 2 && "We foster a culture where everyone feels welcomed, respected, and empowered to contribute."}
                    </p>
                  </div>
                </CardNoise>
              </TiltedScroll>
            ))}
          </div>
        </div>
      </section>

      {/* ERG Showcase */}
      <section className="py-20 bg-gradient-to-r from-gray-900 to-gray-800">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16">
            <Typewriter 
              text="Employee Resource Groups"
              speed={30}
              className="text-emerald-400"
            />
          </h2>
          
          <BentoGrid className="grid md:grid-cols-4 gap-6">
            {['Women at Navan', 'Navan Pride', 'BIPOC Alliance', 'Veterans Network'].map((erg) => (
              <CardNoise key={erg} className="p-6 group">
                <div className="flex flex-col items-center">
                  <div className="w-16 h-16 bg-gradient-to-br from-cyan-400 to-blue-600 rounded-lg mb-4 transform group-hover:rotate-12 transition-transform" />
                  <h3 className="text-xl font-semibold mb-2">{erg}</h3>
                  <p className="text-sm text-gray-300 text-center">
                    Empowering {erg.split(' ')[0]} through community building and professional development.
                  </p>
                  <Link href="/ergs" className="mt-4 text-cyan-400 hover:text-cyan-300 transition-colors">
                    Explore →
                  </Link>
                </div>
              </CardNoise>
            ))}
          </BentoGrid>
        </div>
      </section>

      {/* Progress Metrics */}
      <section id="progress" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16">
            <GradientText
              text="Measurable Impact"
              from="#3B82F6"
              to="#8B5CF6"
            />
          </h2>
          
          <div className="grid md:grid-cols-3 gap-8 text-center">
            {[
              { value: '42%', label: 'Women in Leadership' },
              { value: '67%', label: 'Diverse New Hires' },
              { value: '94%', label: 'Inclusion Satisfaction' }
            ].map((metric) => (
              <div key={metric.label} className="p-8 bg-gray-800 rounded-xl">
                <div className="text-5xl font-bold mb-2 bg-gradient-to-r from-green-400 to-blue-500 bg-clip-text text-transparent">
                  {metric.value}
                </div>
                <div className="text-gray-300">{metric.label}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials */}
      <section id="testimonials" className="py-20 bg-black">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16 text-rose-400">
            In Their Own Words
          </h2>
          
          <AnimatedTestimonials
            testimonials={[
              {
                name: "Alex Chen",
                role: "Senior Engineer",
                text: "As a member of the LGBTQ+ community, I've always felt supported and celebrated at Navan. The Pride ERG has been instrumental in creating safe spaces for authentic conversations.",
                avatar: "/avatars/alex-chen.jpg"
              },
              // Add more testimonials
            ]}
            className="max-w-3xl mx-auto"
          />
        </div>
      </section>

      {/* CTA Section */}
      <section id="cta" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-4 text-center">
          <h2 className="text-4xl font-bold mb-8">
            Ready to Make an Impact?
          </h2>
          
          <div className="flex flex-col md:flex-row gap-6 justify-center">
            <MagneticButton>
              <ShinyButton className="px-8 py-4 text-lg">
                Explore Careers
              </ShinyButton>
            </MagneticButton>
            
            <Link href="/contact" className="group">
              <div className="px-8 py-4 border-2 border-emerald-400 rounded-lg hover:bg-emerald-400/10 transition-colors">
                <span className="text-emerald-400 group-hover:text-emerald-300">
                  Contact DEI Team
                </span>
              </div>
            </Link>
          </div>
        </div>
      </section>

      {/* FAQ Section */}
      <section className="py-20 bg-gray-900">
        <div className="max-w-5xl mx-auto px-4">
          <h2 className="text-3xl font-bold text-center mb-12">
            Frequently Asked Questions
          </h2>
          
          <Accordion
            items={[
              {
                title: "How does Navan ensure pay equity?",
                content: "We conduct bi-annual compensation audits using industry-leading tools..."
              },
              {
                title: "What mentorship opportunities exist?",
                content: "Our GROW mentorship program pairs employees with..."
              }
            ]}
            className="space-y-4"
          />
        </div>
      </section>

      {/* Footer */}
      <footer className="relative border-t border-gray-800">
        <SocialLinks 
          className="flex justify-center gap-6 py-8"
          icons={[
            { name: 'LinkedIn', url: '#' },
            { name: 'Twitter', url: '#' },
            { name: 'Instagram', url: '#' }
          ]}
        />
        <div className="text-center py-6 text-gray-400">
          © {new Date().getFullYear()} Navan. All rights reserved.
          <Link href="/privacy" className="ml-6 hover:text-white transition-colors">
            Privacy Policy
          </Link>
        </div>
      </footer>
    </div>
  );
};

export default DEIPage;
```

This implementation includes:

1. **Immersive Visual Effects**: Uses OrbEffect, AnimatedGridPattern, and GradientText for dynamic backgrounds
2. **Interactive Components**: Features TiltedScroll cards, MagneticButton CTAs, and AnimatedTestimonials
3. **Data Visualization**: Clean metric displays with gradient text effects
4. **Responsive Layout**: Mobile-first approach with flex and grid layouts
5. **Accessibility**: Semantic HTML structure and proper contrast ratios
6. **Microinteractions**: Hover states, smooth transitions, and scroll animations
7. **Content Structure**: Clear information hierarchy with visual landmarks

To complete the implementation:

1. Install all referenced shadcn components using the provided npx commands
2. Create separate component files for complex UI elements
3. Add proper TypeScript types and interfaces
4. Implement mobile-responsive breakpoints
5. Add loading states for dynamic content
6. Include error boundaries for interactive elements
7. Set up proper SEO metadata
8. Add analytics tracking events
9. Implement i18n for translations
10. Add proper image optimizations

The page combines marketing-driven copy with technical depth while maintaining Navan's brand identity through consistent use of gradients, motion, and spatial design principles.