# Summary
This document provides comprehensive documentation of the scoring algorithm, computational methodology, and evidence base for the Lifestyle, Diet, and Gut Microbiome Health Survey based on the attached HTML file (index-7.html). The assessment tool integrates evidence-based dietary indices, lifestyle factors, and medication use patterns to generate a holistic gut health risk score with personalized recommendations.
## 1. Algorithmic Architecture
1.1 Overview
The survey employs a cumulative point-based scoring system with weighted components across multiple domains:
Total Maximum Score: 99 points

**Domain Distribution:**

Dietary Patterns (Section A): 64 points (64.6%)
Lifestyle & Medications (Section B): 35 points (35.4%)

1.2 Computational Flow
User Input → Form Validation → Score Calculation → Risk Classification → Personalized Recommendations

**2. Detailed Scoring Methodology**
2.1 Individual Question Scoring
Q1: Vegetable Servings (0-3 points): Vegetable consumption correlates with gut microbial diversity and SCFA production. Higher vegetable intake (>3 servings/day) associated with increased Bifidobacterium and Lactobacillus abundance.
    
    0 servings → 0 points;
    1-2 servings → 1 point;
    2-3 servings → 2 points;
    >3 servings → 3 points.
    
Q2: Fruit Servings (0-2 points): Fruit fiber promotes beneficial bacteria growth. Two or more servings daily shown to enhance gut microbiome richness.
    
    0 servings → 0 points;
    1 serving → 1 point;
    ≥2 servings → 2 points.
    
Q3: Fermented Foods (0-5 points): 
  
  Method: Multi-select checkbox aggregation; 
  
  Each selection → +1 point (Yogurt, Kefir, Sauerkraut, Tempeh, Kimchi)
   
    "None" option → 0 points
    Maximum: 5 points
  
  Evidence: Stanford study demonstrated 10-week fermented food diet increased microbiome diversity by 59% and decreased inflammatory markers (IL-6, IL-10). Each fermented food type delivers distinct probiotic strains:
  
  Yogurt/Kefir: Lactobacillus, Bifidobacterium
  Sauerkraut/Kimchi: Leuconostoc, Lactobacillus plantarum
  Tempeh: Rhizopus oligosporus
  
Q4: Whole Grains (0-2 points): Whole grains contain resistant starch and arabinoxylans that increase butyrate-producing bacteria (Ruminococcus bromii, Eubacterium rectale)
   
    0 servings → 0 points;
    1-2 servings → 1 point;
    ≥3 servings → 2 points.
    
Q5: Unhealthy Foods Frequency Table (0-20 points): 5 food categories with reverse scoring:

  Frequency Options (per item):

    Never → 4 points;
    Rarely → 3 points;
    Occasionally → 2 points;
    Frequently → 1 point;
    Daily → 0 points.

Total Q5 = Sum of 5 items (0-20 points max)

Food Categories:
    Fast food
    Alcohol
    Red meat (beef, pork, lamb)
    Processed meats (bacon, sausage, pepperoni, deli meats, hot dogs)
    Diet/artificially sweetened drinks

Lower consumption receives higher points due to inverse relationship between processed foods and gut health. Western diet patterns (high meat, saturated fat) shift microbiome toward dysbiosis associated with inflammatory bowel disease.

Q6: Ultra-Processed Foods (0-32 points): 8 food categories with reverse scoring:

  Frequency Options (per item):

    Never → 4 points
    1-2×/week → 3 points
    3-4×/week → 2 points
    5-6×/week → 1 point
    Daily → 0 points

Total Q6 = Sum of 8 items (0-32 points max)

Food Categories:
    Sweet snacks/cakes/cookies
    Juices/Sugary drinks/Soda
    Ready-to-eat meals
    Pre-packaged meats (turkey, ham, roast beef, salami)
    Breakfast cereals
    Chips/crackers
    Condiments/sauces/mayonnaise
    Ice cream

Evidence: Ultra-processed foods associated with:

    23% increased diabetes risk per 10% energy intake increase​
    Reduced Faecalibacterium prausnitzii (anti-inflammatory bacteria)
    Elevated systemic inflammation markers (CRP, IL-6)

Q7: Water Intake (0-3 points): Adequate hydration essential for gut motility, mucus layer maintenance, and preventing constipation.

    <1 liter → 0 points
    1-2 liters → 1 poin  
    2-3 liters → 2 points
    >3 liters → 3 points

Q8: Physical Activity (0-3 points)

    ≥150 min/week moderate OR ≥70 min/week intense → 3 points
    Occasionally (<1×/week) → 1 point
    Never → 0 points

  Evidence:
  150 min/week moderate exercise increases gut microbial diversity by 40%​
  Aerobic exercise (30-60 min, 3×/week) increases butyrate-producing bacteria​
  Exercise enhances Faecalibacterium abundance and SCFA production​
  Effects reverse upon return to sedentary lifestyle within 6 weeks

Q9: Sleep Quality (0-3 points)

      Excellent → 3 points
      Good → 2 points
      Fair → 1 point
      Poor → 0 points

  Evidence:
  Sleep deprivation disrupts gut microbiota and reduces Lactobacillus abundance​
  Poor sleep increases pro-inflammatory cytokines (IL-1β, TNF-α) via gut-brain axis​
  Gut microbiota modulates serotonin and GABA production affecting sleep quality​

Q10: Stress Level (0-3 points): Chronic stress disrupts gut-brain axis, increases intestinal permeability, and alters microbiome composition toward pro-inflammatory states.

      Rarely → 3 points
      Sometimes → 2 points
      Often → 1 point
      Almost all the time → 0 points

Q11: Digestive Discomfort (0-3 points): Frequent digestive symptoms (bloating, indigestion) indicate dysbiosis and reduced microbial diversity. Correlates with altered Firmicutes/Bacteroidetes ratios.

Q12: Antibiotic Use (0-3 points): Frequent antibiotic use significantly reduces gut microbiome diversity with prolonged recovery periods (months to years). Antibiotic-induced dysbiosis persists without probiotic restoration.

      Never → 3 points
      Once/year → 2 points
      2-3 times/year → 1 point
      >3 times/year → 0 points

Q13: Proton Pump Inhibitors (PPIs) (0-3 points): PPI Medications Listed: Omeprazole (Prilosec), Esomeprazole (Nexium), Lansoprazole (Prevacid), Dexlansoprazole (Dexilant), Pantoprazole (Protonix), Rabeprazole (AcipHex)

Long-term PPI use alters gastric pH, affecting upper GI microbiota. Daily PPI regimens associated with increased Enterococcus and reduced Lactobacillus, elevated risk of C. difficile infection.

      Never → 3 points
      2-3 short cycles (2 weeks each) → 2 points
      1-2 cycles (month+ each) → 1 point
      Daily PPI regimen → 0 points
      
Q14: Gut Health Improvement Steps (0-14 points): Multi-component lifestyle interventions show synergistic effects on microbiome health. Combination of diet, exercise, and stress management optimizes gut microbial resilience.​

  Method: Multi-select checkbox aggregation
  Each practice selected → +1 point
  Maximum: 14 points

  Practices:
  1. High-fiber diet
  2. Probiotic foods/supplements
  3. Prebiotic foods/supplements
  4. Stay hydrated
  5. Choose lean meats
  6. Eat whole foods
  7. Minimize processed foods
  8. Mindful eating
  9. Exercise regularly
  10. Manage stress
  11. Prioritize sleep
  12. Avoid/quit smoking
  13. Limit caffeine/alcohol
  14. Identify trigger foods

Risk Categories
Risk Level: 
      Low Risk	≥69.3/99	≥70%	
      Moderate Risk	39.6-69.2/99	40-69%	
      High Risk	<39.6/99	<40%	



