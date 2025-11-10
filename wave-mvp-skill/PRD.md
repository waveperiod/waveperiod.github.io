# **Product Requirements Document (PRD)**
## Wave GAS Fitness Planner - MVP

**Version:** 1.0
**Date:** 2025-11-10
**Status:** Pre-Development
**Owner:** Product Team
**Timeline:** 5 Days (MVP Sprint)

---

## **1. Executive Summary**

### **1.1 Product Vision**
Wave is a web-based fitness planning tool that helps women optimize their training by synchronizing workout intensity with their menstrual cycle phases. We turn hormonal fluctuations from a perceived weakness into a strategic advantage.

### **1.2 Core Value Proposition**
> **"该冲的时候冲,该歇的时候歇"**
> "Push when it's time to push, rest when it's time to rest"

### **1.3 Target Market**
- **Primary**: Women aged 25-40 who exercise regularly (intermediate to advanced fitness levels)
- **Secondary**: Women new to fitness wanting to understand their body's natural rhythms
- **Geographic**: Global (bilingual: Chinese + English)

### **1.4 Success Metrics (MVP Phase)**
- 100+ unique visitors in first week
- 50+ ICS calendar downloads
- 30+ email signups
- <2 second page load time
- >60% mobile traffic handling

---

## **2. Problem Statement**

### **2.1 User Pain Points**
1. **Inconsistent Performance**: Women experience unexplained energy fluctuations during training
2. **Generic Plans**: Existing fitness plans ignore hormonal cycle impacts (designed for male physiology)
3. **Information Overload**: Scattered advice about "period and exercise" lacks actionable structure
4. **Planning Difficulty**: Hard to manually coordinate 12-week training programs with 4-week cycle phases

### **2.2 Market Gap**
- Apps like Whoop/Oura track data but don't provide cycle-specific training plans
- Period trackers (Flo/Clue) lack fitness integration
- No tool combines GAS (General Adaptation Syndrome) training principles with menstrual cycle science

---

## **3. Product Goals**

### **3.1 Business Goals**
1. **Validate Demand**: Test if users want cycle-synchronized fitness planning
2. **Build Email List**: Collect 30+ emails for future app launch
3. **Test Pricing**: Gauge interest in premium "Shero" membership (¥299 early bird vs ¥999 regular)
4. **Rapid Learning**: Complete full cycle from idea→launch→feedback in 5 days

### **3.2 User Goals**
1. Understand how their cycle affects workout capacity
2. Get a personalized 12-week training plan
3. Export plan to their existing calendar app
4. Learn about GAS training methodology

---

## **4. Functional Requirements**

### **4.1 P0 Features (Must Have - Core MVP)**

#### **F1: User Input Form**
**User Story**: As a user, I want to input my cycle data so the system can generate my personalized plan.

**Acceptance Criteria:**
- [ ] Input field: Menstrual cycle length (21-35 days, slider)
- [ ] Input field: Next period start date (date picker)
- [ ] Input field: Fitness level (Beginner/Intermediate/Advanced, dropdown)
- [ ] Form validation with clear error messages
- [ ] Mobile-responsive design
- [ ] Input persists in sessionStorage

**Technical Notes:**
- Use native HTML5 date picker (browser compatibility)
- Slider implemented with TailwindCSS styling

---

#### **F2: Data Visualization**
**User Story**: As a user, I want to see my 12-week training intensity mapped to my menstrual cycle phases.

**Acceptance Criteria:**
- [ ] 12-week bar chart showing training intensity (1-10 scale)
- [ ] 4 menstrual cycle phases overlaid with distinct colors
- [ ] Coral-to-orange gradient indicating energy levels
- [ ] Key dates marked with black dots (period start, ovulation)
- [ ] Hover tooltips showing: Week #, Intensity, Phase, Energy tip
- [ ] Responsive sizing (desktop: 800px, mobile: auto-width)
- [ ] Legend explaining phases: 🌙 Menstrual, 🌱 Follicular, ⚡ Ovulation, 🌗 Luteal

**Technical Notes:**
- Chart.js library via CDN
- Update chart dynamically when form inputs change

**Visual Reference:**
```
Energy:  High ████████████ 10
              ██████████    8
              ██████        6
              ████          4
         Low  ██            2
         ─────────────────────────────
         Wk1  Wk4  Wk7  Wk10  Wk12
         🌙   🌱   ⚡   🌗    🌙
```

---

#### **F3: ICS Calendar Export**
**User Story**: As a user, I want to download my plan as a calendar file so I can view it in my daily calendar app.

**Acceptance Criteria:**
- [ ] "Download to Calendar" button visible after chart loads
- [ ] Generates .ics file with 84 daily events (12 weeks × 7 days)
- [ ] Event title format: `[Intensity Level] Phase - Training Type`
  - Example: `【中强度】排卵期 - 力量训练`
- [ ] Event description includes:
  - Energy index (e.g., "能量指数: 8/10")
  - Training suggestions (e.g., "建议: 增加重量")
  - Cycle phase explanation
- [ ] Events set at 6:00 AM by default
- [ ] Compatible with Apple Calendar, Google Calendar, Outlook
- [ ] Bilingual support (user's selected language)

**Technical Notes:**
- Use ics.js library (CDN: unpkg.com)
- Test with multiple calendar apps

---

#### **F4: Email Collection**
**User Story**: As the business, we want to collect user emails before download so we can notify them of the app launch.

**Acceptance Criteria:**
- [ ] Modal popup appears when user clicks "Download"
- [ ] Single email input field with validation
- [ ] Privacy disclaimer: "We'll only email you about the Wave app launch"
- [ ] "Submit" button enables download
- [ ] Optional "Skip" link (allows download without email)
- [ ] Thank you message after submission
- [ ] Integration with Formspree or Google Forms
- [ ] Email stored in accessible database/spreadsheet

**Technical Notes:**
- Formspree free tier: 50 submissions/month (sufficient for MVP)

---

### **4.2 P1 Features (Should Have - Enhances Experience)**

#### **F5: Language Toggle**
**User Story**: As a bilingual user, I want to switch between Chinese and English.

**Acceptance Criteria:**
- [ ] Toggle button in top-right corner (🇨🇳/🇬🇧 flags)
- [ ] Auto-detect browser language on first visit
- [ ] Preference saved in localStorage
- [ ] All text updates instantly (no page refresh)
- [ ] Chart labels update to selected language

---

#### **F6: Shero Membership Section**
**User Story**: As a potential customer, I want to learn about premium membership benefits.

**Acceptance Criteria:**
- [ ] Standalone section at page bottom
- [ ] Headline: "Join Shero - Beta Membership"
- [ ] Pricing: ¥299 (strike-through ¥999)
- [ ] 3-5 key benefits listed
- [ ] CTA button: "Reserve My Spot" → links to booking form
- [ ] Visual differentiation from rest of page (background color/border)

---

#### **F7: GAS Theory Explainer**
**User Story**: As a user unfamiliar with GAS, I want to understand the science behind my plan.

**Acceptance Criteria:**
- [ ] "What is GAS?" info icon (?) next to title
- [ ] Click opens modal/drawer with explanation
- [ ] Content: 2-3 paragraphs in plain language
- [ ] Optional: simple diagram
- [ ] Close button returns to main view

---

### **4.3 P2 Features (Nice to Have - Future Iterations)**
- Detailed workout suggestions per week
- Import historical period data
- Social sharing functionality
- Multiple plan comparison

---

## **5. Non-Functional Requirements**

### **5.1 Performance**
- Page load: <2 seconds (on 4G connection)
- Chart rendering: <500ms
- User interaction response: <100ms
- File size: Total <1MB (HTML+CSS+JS+assets)

### **5.2 Compatibility**
- **Desktop**: Chrome 90+, Safari 14+, Edge 90+
- **Mobile**: iOS Safari 14+, Android Chrome 90+
- Screen sizes: 320px - 2560px width

### **5.3 Accessibility**
- WCAG 2.1 Level A minimum
- Keyboard navigation support
- Screen reader compatible (ARIA labels)
- Color contrast ratio >4.5:1

### **5.4 Security & Privacy**
- No storage of sensitive health data on server
- Client-side computation only
- Email collection via HTTPS
- GDPR-friendly privacy policy link

---

## **6. Design Requirements**

### **6.1 Brand Identity**
- **Logo**: `({})` in #D60D0D (Wave Red)
- **Color Palette**:
  - Primary: #D60D0D (brand red)
  - Background: #FFFFFF (white) / #000000 (black text)
  - Data viz gradient: #FF6B6B → #FFB8B8 → #FFE5E5
- **Style**: Minimalist geometric, data-driven (Whoop/Oura aesthetic)
- **Typography**: Clean sans-serif (system fonts for speed)

### **6.2 Tone & Voice**
- **Professional but approachable**: No medical jargon
- **Empowering not prescriptive**: "适合恢复性训练" not "不能做运动"
- **Warm but not cutesy**: Avoid stereotypical feminine clichés
- **Data-backed**: Reference GAS methodology and hormonal science

### **6.3 Messaging Framework**
| ❌ Avoid | ✅ Use Instead |
|---------|---------------|
| "大姨妈" (colloquial) | "月经期" (professional) |
| "经期不适合运动" (negative) | "这周适合恢复性训练" (constructive) |
| "激素让你情绪化" (stigmatizing) | "这几天情绪敏感度更高" (neutral) |

---

## **7. Technical Architecture**

### **7.1 Tech Stack**
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Styling**: TailwindCSS (CDN)
- **Charting**: Chart.js 3.x (CDN)
- **Calendar**: ics.js 2.35.0 (CDN)
- **Form Backend**: Formspree
- **Hosting**: GitHub Pages
- **Analytics**: Google Analytics 4

### **7.2 File Structure**
```
wave-mvp/
├── index.html
├── css/
│   └── custom.css
├── js/
│   ├── i18n.js          # Language switching
│   ├── cycle.js         # Menstrual cycle calculations
│   ├── gas.js           # GAS training logic
│   ├── chart.js         # Chart.js rendering
│   ├── ics-export.js    # Calendar file generation
│   └── main.js          # Main controller
├── assets/
│   └── logo.svg
└── README.md
```

### **7.3 Key Algorithms**

**Cycle Phase Calculation:**
```
Input: cycle_length (days), next_period_date
Output: 12-week array of phases

1. Calculate ovulation = next_period_date - 14 days
2. Map phases:
   - Menstrual: Days 1-5
   - Follicular: Days 6 - (ovulation)
   - Ovulation: Ovulation ± 2 days
   - Luteal: (ovulation + 3) - (period - 1)
3. Repeat cycle for 12 weeks
```

**GAS Training Intensity:**
```
Week 1-3:  Shock phase (intensity 6-7-8)
Week 4:    Recovery (intensity 4)
Week 5-7:  Adaptation (intensity 7-8-9)
Week 8:    Recovery (intensity 5)
Week 9-11: Peak (intensity 8-9-10)
Week 12:   Deload (intensity 3-4)

Adjust ±1 based on cycle phase energy
```

---

## **8. User Journey**

### **8.1 Happy Path**
1. User lands on homepage → sees hero section with value prop
2. Scrolls down → reads "How it works" (3 simple steps)
3. Fills out input form (cycle length, next period, fitness level)
4. Clicks "Generate My Plan" → chart animates in
5. Reviews 12-week visualization → understands pattern
6. Clicks "What is GAS?" → reads brief explainer → closes modal
7. Clicks "Download to Calendar" → email modal appears
8. Enters email → submits → .ics file downloads
9. Opens Apple Calendar → imports file → sees 84 events
10. Scrolls to Shero section → clicks "Reserve My Spot" → fills booking form

### **8.2 Error Handling**
- Invalid date (past): "Please select a future date"
- Cycle length <21 or >35 days: "Typical cycles are 21-35 days. Consult a doctor if yours differs significantly."
- Invalid email format: "Please enter a valid email address"
- Download failure: "Download failed. Try again or contact support@wave.com"

---

## **9. Development Timeline**

### **Day 1: Foundation** ⏳
- Project setup (repo, structure)
- HTML framework + form inputs
- Core cycle calculation algorithm

**Deliverable**: Working form that logs data to console

---

### **Day 2: Visualization** ⏳
- Integrate Chart.js
- Implement bar chart with GAS data
- Overlay cycle phases with color coding

**Deliverable**: Dynamic chart that updates with form inputs

---

### **Day 3: Export** ⏳
- Implement ics.js integration
- Generate 84-day event array
- Download functionality + email modal

**Deliverable**: Working .ics download + email collection

---

### **Day 4: Polish** ⏳
- Add language toggle
- Implement Shero section
- Cross-browser/device testing + bug fixes

**Deliverable**: Feature-complete MVP

---

### **Day 5: Launch** ⏳
- Final copywriting review
- Deploy to GitHub Pages
- Add Google Analytics
- Conduct production QA

**Deliverable**: Live website at [username].github.io/wave

---

## **10. Risks & Mitigation**

| Risk | Impact | Likelihood | Mitigation |
|------|--------|-----------|------------|
| Chart.js too complex | High | Medium | Use default config first, iterate later |
| ICS format incompatibility | High | Low | Test with Apple/Google/Outlook early (Day 3) |
| Mobile layout breaks | Medium | Medium | Use Tailwind responsive classes, test daily |
| Formspree 50-submission limit | Medium | Low | Monitor submissions, switch to Google Forms if needed |
| Low user traffic | Low | High | This is expected for MVP - focus on conversion rate |

---

## **11. Success Criteria**

### **11.1 Launch Criteria (Go-Live Checklist)**
- [ ] All P0 features functional
- [ ] No P0 bugs
- [ ] Mobile responsiveness verified
- [ ] .ics tested on 3 calendar apps
- [ ] Analytics tracking confirmed
- [ ] Privacy policy page linked
- [ ] Page load <2 seconds

### **11.2 Post-Launch Metrics (Week 1)**
| Metric | Target | Stretch Goal |
|--------|--------|-------------|
| Unique Visitors | 100 | 500 |
| Form Completions | 50 (50%) | 250 (50%) |
| ICS Downloads | 30 (30%) | 150 (30%) |
| Email Signups | 20 (20%) | 100 (20%) |
| Shero Inquiries | 5 | 20 |
| Bounce Rate | <60% | <40% |

### **11.3 Validation Questions**
1. Do users understand the value proposition in <10 seconds?
2. Is the form completion rate >40%?
3. Do users successfully import .ics files (support tickets)?
4. Is there willingness to pay ¥299 for Shero membership?

---

## **12. Open Questions & Decisions Needed**

### **12.1 Before Development Starts**
- [ ] **Email tool**: Formspree or Google Forms? → *Decision: Formspree (easier UX)*
- [ ] **Email optional**: Allow skip or force submission? → *Decision: Allow skip (lower friction)*
- [ ] **ICS event time**: 6 AM, 8 AM, or user-selectable? → *Decision: 6 AM default*
- [ ] **Shero form**: Embedded or external link? → *Decision: External Google Form*

### **12.2 To Explore During Development**
- Exact Chart.js gradient configuration
- Optimal mobile chart height
- Hover tooltip content hierarchy
- Error message phrasing (test with users)

---

## **13. Out of Scope (For This MVP)**

**Explicitly NOT included:**
- User accounts / login system
- Historical data tracking
- Social features (sharing, community)
- Nutrition recommendations
- Workout video library
- Push notifications
- Native mobile apps
- Payment processing (Shero membership)
- Scientific citations / research papers
- Integration with wearables (Whoop, Oura, etc.)

---

## **14. Appendices**

### **14.1 References**
- GAS Training: Selye's General Adaptation Syndrome
- Menstrual Cycle Phases: Standard 28-day model with adjustments
- Brand Toolkit: `/wave-mvp-skill/brand.md`
- Full Pain Points: `/Wave-Deep-Pain-Points-Supplement.md`

### **14.2 Glossary**
- **GAS**: General Adaptation Syndrome - training principle of stress → adaptation → growth
- **ICS**: iCalendar format - universal calendar file standard (RFC 5545)
- **Shero**: Portmanteau of "She" + "Hero" - brand term for premium members

---

## **15. Approval & Sign-off**

| Role | Name | Status | Date |
|------|------|--------|------|
| Product Manager | [You] | ✅ Approved | 2025-11-10 |
| Developer Lead | [TBD] | ⏳ Pending | |
| Designer | [TBD] | ⏳ Pending | |
| QA Lead | [TBD] | ⏳ Pending | |

---

**Document Status:** Ready for Development Kickoff
**Next Steps:**
1. Review PRD with full team
2. Clarify open questions (Section 12.1)
3. Begin Day 1 implementation
4. Set up daily standup (async updates in dev-plan.md)

---

*This PRD follows an "explore while building" approach - expect updates as we learn during development.*
