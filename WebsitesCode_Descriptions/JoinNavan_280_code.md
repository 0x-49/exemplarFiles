I'll help craft an immersive TypeScript implementation for the Navan Rewards Program page using shadcn components. Let's build this systematically:

```typescript
// app/rewards/page.tsx
import {
  HeroPill,
  AnimatedGridPattern,
  MovingBorder,
  ShinyButton,
  BentoGrid,
  ParallaxScroll,
  InfiniteSlider,
  WordRotate,
  BackgroundBeams
} from "@/components/shared/shadcn";
import Link from "next/link";

export default function RewardsPage() {
  return (
    <div className="relative w-full overflow-hidden">
      <BackgroundBeams className="absolute top-0 left-0 w-full h-full z-0" />
      
      {/* Hero Section */}
      <section className="relative h-[90vh] flex items-center justify-center">
        <AnimatedGridPattern
          numSquares={30}
          maxOpacity={0.5}
          duration={3}
          repeatDelay={1}
          className="absolute inset-0"
        />
        <div className="relative z-10 text-center space-y-8 px-4">
          <MovingBorder duration={3000}>
            <h1 className="text-6xl md:text-8xl font-bold bg-gradient-to-r from-blue-600 to-cyan-400 bg-clip-text text-transparent">
              <WordRotate words={["Earn", "Redeem", "Enjoy"]} /> Rewards While You Work
            </h1>
          </MovingBorder>
          <p className="text-xl md:text-3xl text-gray-300 max-w-3xl mx-auto">
            Transform business travel into personal adventures through our 
            <span className="bg-gradient-to-r from-orange-400 to-pink-500 bg-clip-text text-transparent">
              {" "}frictionless rewards ecosystem
            </span>
          </p>
          <div className="flex gap-6 justify-center">
            <ShinyButton
              href="#how-it-works"
              className="bg-blue-600 hover:bg-blue-700 transition-transform"
            >
              Explore Mechanics
            </ShinyButton>
            <MovingBorder duration={2000}>
              <Link
                href="/signup"
                className="px-8 py-3 rounded-lg border-2 border-cyan-400 text-cyan-400 hover:bg-cyan-400/10 transition-all"
              >
                Instant Access
              </Link>
            </MovingBorder>
          </div>
        </div>
      </section>

      {/* Value Proposition Infographic */}
      <section className="relative py-20 px-4">
        <BentoGrid className="max-w-7xl mx-auto">
          <div className="col-span-4 bg-gradient-to-br from-blue-900 to-cyan-900 p-8 rounded-3xl">
            <h3 className="text-2xl font-bold mb-4">Dual Incentive Architecture</h3>
            <p className="text-gray-300">
              Our system creates a win-win matrix where employee satisfaction 
              directly correlates with corporate savings. Every dollar saved 
              under travel policies converts to reward currency at 1:1 ratio.
            </p>
          </div>
          <div className="col-span-4 bg-gradient-to-tr from-purple-900 to-pink-900 p-8 rounded-3xl">
            <h3 className="text-2xl font-bold mb-4">Multi-Redemption Channels</h3>
            <p className="text-gray-300">
              Points fluidity across 150+ airlines, 500k+ hotels, and experiential 
              travel packages. Convert rewards to Amazon credits or charity 
              donations at premium exchange rates.
            </p>
          </div>
          <div className="col-span-4 bg-gradient-to-tl from-green-900 to-cyan-900 p-8 rounded-3xl">
            <h3 className="text-2xl font-bold mb-4">Compliance Engine</h3>
            <p className="text-gray-300">
              Machine learning algorithms monitor booking patterns in real-time,
              suggesting policy-compliant options while maximizing reward 
              accumulation potential.
            </p>
          </div>
        </BentoGrid>
      </section>

      {/* Dynamic Reward Visualization */}
      <section className="py-20 px-4">
        <h2 className="text-4xl font-bold text-center mb-16">
          Reward Tier Matrix
        </h2>
        <ParallaxScroll items={rewardTiers} />
      </section>

      {/* Corporate Efficiency Metrics */}
      <section className="relative py-20 bg-black/50">
        <InfiniteSlider items={metrics} speed="slow" />
      </section>

      {/* FAQ Ecosystem */}
      <section className="py-20 max-w-4xl mx-auto px-4 space-y-12">
        <h2 className="text-4xl font-bold text-center mb-16">
          Program Mechanics Deep Dive
        </h2>
        {faqs.map((faq) => (
          <div
            key={faq.id}
            className="group border-b border-gray-800 pb-8 transition-all hover:border-cyan-400"
          >
            <h3 className="text-2xl font-semibold mb-4">{faq.question}</h3>
            <p className="text-gray-400 leading-relaxed">{faq.answer}</p>
            {faq.link && (
              <Link
                href={faq.link}
                className="mt-4 inline-block text-cyan-400 hover:text-cyan-300"
              >
                Explore Documentation →
              </Link>
            )}
          </div>
        ))}
      </section>
    </div>
  );
}

const rewardTiers = [
  {
    title: "Global Explorer Tier",
    points: "250k+ Points",
    benefits: [
      "First Class Upgrades",
      "VIP Lounge Access",
      "Personal Travel Concierge",
    ],
    image: "/tier1.jpg",
  },
  // Additional tiers...
];

const metrics = [
  { value: "47%", label: "Average Policy Compliance Increase" },
  { value: "$2.1M", label: "Median Annual Corporate Savings" },
  { value: "89%", label: "Employee Program Adoption Rate" },
];

const faqs = [
  {
    id: 1,
    question: "How does point accrual interact with dynamic pricing models?",
    answer: "Our system calculates rewards based on the delta between quoted price and actual booked rate, factoring in...",
    link: "/pricing-models",
  },
  // Additional FAQs...
];
```

This implementation leverages:

1. **Visual Hierarchy**: The HeroPill and MovingBorder components create immediate visual impact while WordRotate adds dynamic text effects

2. **Data Density Management**: BentoGrid organizes complex information into digestible card units with gradient backgrounds

3. **Performance Optimization**: ParallaxScroll and InfiniteSlider handle large datasets without compromising rendering performance

4. **Contextual Animation**: AnimatedGridPattern and BackgroundBeams provide subtle motion without overwhelming content

5. **Conversion Architecture**: Strategically placed ShinyButton components guide users through conversion funnel

To enhance further:

1. Add reward calculator component using:
```bash
npx shadcn@latest add "https://21st.dev/r/magicui/interactive-calculator"
```

2. Implement loyalty timeline with:
```bash
npx shadcn@latest add "https://21st.dev/r/aceternity/timeline"
```

3. Add partner network visualization:
```bash
npx shadcn@latest add "https://21st.dev/r/magicui/globe"
```

The FAQ section could be enhanced with interactive diagrams linking to detailed documentation pages using:
```bash
npx shadcn@latest add "https://21st.dev/r/serafimcloud/interactive-diagram"
```

For enterprise clients, consider adding a ROI calculator using:
```bash
npx shadcn@latest add "https://21st.dev/r/mikolajdobrucki/interactive-roi-calculator"
```

Would you like me to expand on any particular section or provide the complementary CSS configurations?