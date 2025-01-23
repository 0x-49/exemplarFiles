**Wishup Bookkeeping Assistant: Comprehensive Landing Page Script with Shadcn Component Integration**

---

# **Hero Section: Financial Liberation at First Scroll**

```tsx
import { LampComponent } from "@/components/aceternity/lamp";
import { HeroPill } from "@/components/Codehagen/hero-pill";
import { ScrambleHover } from "@/components/danielpetho/scramble-hover";
import { BackgroundBeams } from "@/components/aceternity/background-beams";

export default function HeroSection() {
  return (
    <section className="relative h-[800px] overflow-hidden">
      <LampComponent>
        <div className="z-10 relative">
          <HeroPill 
            text="IRS-Nightmare Solution Certified"
            className="mb-8 animate-fade-in"
          />
          <h1 className="text-6xl font-bold mb-6 bg-gradient-to-r from-blue-600 to-green-500 bg-clip-text text-transparent">
            <ScrambleHover 
              text="Are Financial Ghosts Haunting Your Business Dreams?"
              scrambleVelocity={0.3}
            />
          </h1>
          <p className="text-xl mb-12 text-gray-600 dark:text-gray-300">
            <TypewriterEffect 
              words={["Hire Elite Bookkeeping Guardians", "60-Minute Onboarding", "100% Compliance Guarantee"]}
              className="font-medium"
            />
          </p>
          <div className="max-w-2xl mx-auto bg-white dark:bg-gray-900 rounded-xl p-1 shadow-2xl">
            <MovingBorder duration={3000} rx="30px">
              <LeadCaptureForm />
            </MovingBorder>
          </div>
        </div>
      </LampComponent>
      <BackgroundBeams className="top-0" />
    </section>
  );
}
```

**Copywriting Narrative:**
Beneath our luminescent LampComponent that bathes visitors in financial clarity, the HeroPill component pulses with urgent credibility - your first assurance of elite expertise. The ScrambleHover headline performs digital alchemy, transforming accounting anxiety into focused action through its mesmerizing letter dance. As the TypewriterEffect mechanically types promises of rapid resolution, the MovingBorder form container undulates with latent energy - a visual metaphor for the dynamic solutions contained within. This orchestrated spectacle positions Wishup not as mere service, but as financial exorcists banishing spreadsheet specters.

---

# **Key Statistics: The Proof Matrix**

```tsx
import { BentoGrid } from "@/components/aceternity/bento-grid";
import { TiltedScroll } from "@/components/DavidHDev/tilted-scroll";

const stats = [
  { 
    title: "Global Compliance Warriors", 
    value: "900+", 
    description: "Businesses shielded from financial peril",
    icon: <ShieldCheck className="h-8 w-8 text-green-500" />
  },
  // Additional stat objects...
];

export function StatsSection() {
  return (
    <section className="py-24 relative">
      <AnimatedGridPattern className="opacity-30" />
      <h2 className="text-4xl font-bold text-center mb-20">
        <GradientText>Why 900+ CEOs Sleep Soundly</GradientText>
      </h2>
      <TiltedScroll>
        <BentoGrid items={stats} />
      </TiltedScroll>
    </section>
  );
}
```

**Data Storytelling:**
The BentoGrid doesn't just present numbers - it architecturally reconstructs trust. Each card in the TiltedScroll carousel becomes a crystalline proof point, angled to catch the light of scrutiny from every entrepreneurial perspective. The AnimatedGridPattern beneath creates subtle movement, suggesting perpetual activity in our compliance engines. GradientText components transform dry numbers into radiant achievements, while custom icons serve as visual warrants for each claim.

---

# **Services Gallery: Financial Arsenal Revealed**

```tsx
import { CardWithNoise } from "@/components/Ali-Hussein-dev/card-with-noise-pattern";
import { HoverBorderGradient } from "@/components/aceternity/hover-border-gradient";

const services = [
  {
    title: "Cash Flow Alchemy",
    description: "Transform financial trickles into torrents",
    link: "/services/cash-flow-management"
  },
  // Additional service objects...
];

export function ServicesSection() {
  return (
    <section className="py-24">
      <h2 className="text-4xl font-bold text-center mb-16">
        <WordRotate 
          words={["Financial Toolkit", "Compliance Arsenal", "Growth Catalyst"]} 
          className="text-blue-600"
        />
      </h2>
      <div className="grid grid-cols-3 gap-8">
        {services.map((service) => (
          <HoverBorderGradient>
            <CardWithNoise>
              <h3>{service.title}</h3>
              <p>{service.description}</p>
              <HyperText href={service.link}>Explore Methodology →</HyperText>
            </CardWithNoise>
          </HoverBorderGradient>
        ))}
      </div>
    </section>
  );
}
```

**Service Elevation:**
Each CardWithNoise component features cryptographic visual texture - a literal representation of the complex patterns our bookkeepers decode. Wrapped in HoverBorderGradient, these service modules appear to breathe with potential energy, their edges shimmering with unspent financial potential. The WordRotate headline acts as conceptual scaffolding, continually reframing services as strategic assets rather than mere tasks.

---

[Continued in Next Message Due to Length]