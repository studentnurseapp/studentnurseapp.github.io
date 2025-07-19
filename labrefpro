<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LabRef Pro: Interpret. Learn. Apply.</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-gradient-start: #1a0134;
            --bg-gradient-mid: #3b0266;
            --bg-gradient-end: #57008a;
            --text-primary: #f1f5f9;
            --text-secondary: #cbd5e1;
            --text-accent: #b4a3c1;
            --glass-bg-card: rgba(59, 2, 102, 0.6);
            --glass-border: rgba(255, 255, 255, 0.1);
            --blue-accent: #a855f7;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-image: linear-gradient(135deg, var(--bg-gradient-start) 0%, var(--bg-gradient-mid) 50%, var(--bg-gradient-end) 100%);
            color: var(--text-primary);
            background-attachment: fixed;
        }

        .gradient-text {
            background-image: linear-gradient(to right, #e879f9, #a855f7, #6366f1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .input-glass {
            background: rgba(15, 23, 42, 0.5);
            border: 1px solid var(--glass-border);
            color: var(--text-primary);
            border-radius: 9999px;
            transition: all 0.2s ease-in-out;
            padding: 0.75rem 1rem 0.75rem 3rem;
        }
        .input-glass:focus {
            outline: none;
            border-color: var(--blue-accent);
            box-shadow: 0 0 0 3px rgba(168, 85, 247, 0.4);
        }

        .category-filter-btn {
            flex-shrink: 0;
            padding: 0.5rem 1.25rem;
            border-radius: 9999px;
            font-size: 0.875rem;
            font-weight: 600;
            color: var(--text-secondary);
            background-color: var(--glass-bg-card);
            border: 1px solid var(--glass-border);
            transition: all 0.2s ease-in-out;
            cursor: pointer;
            white-space: nowrap;
        }
        .category-filter-btn:hover {
            color: var(--text-primary);
            border-color: var(--blue-accent);
            transform: translateY(-2px);
        }
        .category-filter-btn.active {
            color: white;
            background-image: linear-gradient(to right, #8b5cf6, #d946ef);
            border-color: transparent;
            box-shadow: 0 4px 15px rgba(168, 85, 247, 0.3);
        }

        .lab-value-card {
            background: var(--glass-bg-card);
            backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: 0.75rem;
            overflow: hidden;
            transition: all 0.2s ease-in-out;
        }
        .lab-value-card summary {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 1.5rem;
            cursor: pointer;
            outline: none;
        }
        .lab-value-card summary::-webkit-details-marker { display: none; }
        .lab-value-card summary:hover { background-color: rgba(255, 255, 255, 0.05); }
        .lab-value-card .summary-arrow { transition: transform 0.2s ease-in-out; }
        .lab-value-card[open] .summary-arrow { transform: rotate(90deg); }
        
        .lab-value-details {
            padding: 1rem 1.5rem;
            background-color: rgba(15, 23, 42, 0.3);
            border-top: 1px solid var(--glass-border);
        }
        .etiology-column h4.high { color: #f87171; }
        .etiology-column h4.low { color: #60a5fa; }
        .lab-notes {
            margin-top: 1rem;
            padding: 0.75rem;
            background-color: rgba(168, 85, 247, 0.1);
            border: 1px solid rgba(168, 85, 247, 0.2);
            border-radius: 0.5rem;
            font-size: 0.875rem;
            color: #d8b4fe;
        }
    </style>
</head>
<body class="bg-slate-900 text-slate-200">

    <div id="app" class="min-h-screen">
        <div id="labsContent" class="p-4 sm:p-6 lg:p-8">
             <header class="text-center mb-8 sm:mb-12">
                <h1 class="text-4xl sm:text-5xl md:text-6xl font-extrabold tracking-tight gradient-text">
                    LabRef Pro
                </h1>
                <p class="mt-4 text-lg text-text-secondary max-w-3xl mx-auto">
                    Interpret. Learn. Apply.
                </p>
                <div class="mt-8 max-w-xl mx-auto">
                    <div class="relative">
                        <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                            <svg class="w-5 h-5 text-text-accent" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                                <path fill-rule="evenodd" d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z" clip-rule="evenodd" />
                            </svg>
                        </div>
                        <input type="search" id="labSearchInput" placeholder="Search lab tests (e.g., Potassium, WBC, Glucose)..." class="input-glass block w-full shadow-lg">
                    </div>
                </div>
            </header>

            <div id="labCategoryFilters" class="sticky top-0 z-10 py-3 bg-gradient-to-b from-bg-gradient-mid to-transparent -mx-4 sm:-mx-6 lg:-mx-8 px-4 sm:px-6 lg:px-8 mb-6 backdrop-blur-md">
                <div class="max-w-7xl mx-auto flex items-center space-x-3 overflow-x-auto pb-2">
                    <!-- Category filter buttons will be dynamically inserted here -->
                </div>
            </div>

            <main id="labValuesHost" class="max-w-7xl mx-auto space-y-8">
            </main>
             <div id="no-lab-results" class="text-center p-10 hidden">
                <h2 class="text-2xl font-bold text-text-secondary">No lab values found</h2>
                <p class="text-text-accent mt-2">Try adjusting your search terms.</p>
            </div>
        </div>
    </div>

<script type="module">
// --- COMPLETE LAB VALUES DATABASE ---
const allLabValuesData = [
    {
        title: "Serum, Plasma, and Whole Blood Chemistries",
        icon: "🩸",
        values: [
            { test: "Aldolase", conventionalUnits: "22-59 mU/L", siUnits: "22-59 mU/L", etiology: { high: "Skeletal muscle disease", low: "Muscle-wasting disease" } },
            { test: "α₁-Antitrypsin", conventionalUnits: "85-213 mg/dL", siUnits: "0.85-2.13 g/L", etiology: { high: "Acute and chronic inflammation, arthritis", low: "Early-onset emphysema, malnutrition, nephrotic syndrome" } },
            { test: "α-Fetoprotein", conventionalUnits: "<40 ng/mL", siUnits: "<40 mcg/L", etiology: { high: "Cancer of testes, ovaries, and liver", low: "" } },
            { test: "Ammonia", conventionalUnits: "10-80 mcg/dL", siUnits: "6-47 µmol/L", etiology: { high: "Severe liver disease", low: "Acute alcoholism, cirrhosis of liver, extensive destruction of pancreas" } },
            { test: "Amylase", conventionalUnits: "60-120 Somogyi U/dL", siUnits: "30-220 U/L", etiology: { high: "Acute and chronic pancreatitis, salivary gland disease, perforated ulcers", low: "" } },
            { test: "Bicarbonate", conventionalUnits: "21-28 mEq/L", siUnits: "21-28 mmol/L", etiology: { high: "Compensated respiratory acidosis, metabolic alkalosis", low: "Compensated respiratory alkalosis, metabolic acidosis" } },
            { test: "b-Type natriuretic peptide (BNP)", conventionalUnits: "<100 pg/mL", siUnits: "<100 pmol/L", etiology: { high: "Heart failure", low: "" } },
            { test: "Bilirubin, Total", conventionalUnits: "0.3-1.0 mg/dL", siUnits: "5.1-17 µmol/L", etiology: { high: "Biliary obstruction, hemolytic anemia, impaired liver function, pernicious anemia", low: "" } },
            { test: "Bilirubin, Indirect", conventionalUnits: "0.2-0.8 mg/dL", siUnits: "3.4-12.0 µmol/L", etiology: { high: "Biliary obstruction, hemolytic anemia, impaired liver function, pernicious anemia", low: "" } },
            { test: "Bilirubin, Direct", conventionalUnits: "0.1-0.3 mg/dL", siUnits: "1.7-5.1 µmol/L", etiology: { high: "Biliary obstruction, hemolytic anemia, impaired liver function, pernicious anemia", low: "" } },
            { test: "Blood gases, Arterial pH", conventionalUnits: "7.35-7.45", siUnits: "7.35-7.45", etiology: { high: "Alkalosis", low: "Acidosis" }, notes: "Because arterial blood gases are influenced by altitude, the value for PaO₂ decreases as altitude increases. The lower value is normal for an altitude of 1 mile." },
            { test: "Blood gases, Venous pH", conventionalUnits: "7.31-7.41", siUnits: "7.31-7.41", etiology: { high: "Alkalosis", low: "Acidosis" } },
            { test: "Blood gases, PaCO₂", conventionalUnits: "35-45 mm Hg", siUnits: "4.66-5.98 kPa", etiology: { high: "Compensated metabolic alkalosis, Respiratory acidosis", low: "Compensated metabolic acidosis, Respiratory alkalosis" } },
            { test: "Blood gases, PvCO₂", conventionalUnits: "40-50 mm Hg", siUnits: "5.06-7.32 kPa", etiology: { high: "Compensated metabolic alkalosis, Respiratory acidosis", low: "Compensated metabolic acidosis, Respiratory alkalosis" } },
            { test: "Blood gases, PaO₂", conventionalUnits: "80-100 mm Hg", siUnits: "10.6-13.33 kPa", etiology: { high: "Administration of high concentration of O₂", low: "Chronic lung disease, decreased cardiac output" } },
            { test: "Blood gases, PvO₂", conventionalUnits: "40-50 mm Hg", siUnits: "5.04-5.57 kPa", etiology: { high: "", low: "" } },
            { test: "Calcium (total)", conventionalUnits: "9.0-10.5 mg/dL", siUnits: "2.25-2.62 mmol/L", etiology: { high: "Hyperthyroidism, hyperparathyroidism, vitamin D intoxication, multiple myeloma", low: "Pancreatitis, hypoparathyroidism, malabsorption syndrome, renal failure, vitamin D deficiency" } },
            { test: "Calcium (ionized)", conventionalUnits: "4.5-5.6 mg/dL", siUnits: "1.05-1.3 mmol/L", etiology: { high: "Acidosis", low: "Alkalosis" } },
            { test: "Chloride", conventionalUnits: "98-106 mEq/L", siUnits: "98-106 mmol/L", etiology: { high: "Metabolic acidosis, respiratory alkalosis, corticosteroid therapy, uremia", low: "Addison's disease, vomiting, metabolic alkalosis, respiratory acidosis" } },
            { test: "Cholesterol", conventionalUnits: "<200 mg/dL", siUnits: "<5.2 mmol/L", etiology: { high: "Biliary obstruction, hypothyroidism, idiopathic hypercholesterolemia, renal disease, uncontrolled diabetes", low: "Extensive liver disease, hyperthyroidism, malnutrition, malabsorption" } },
            { test: "High-density lipoproteins (HDLs)", conventionalUnits: "Male: >45 mg/dL, Female: >55 mg/dL", siUnits: "Male: >0.75 mmol/L, Female: >0.91 mmol/L", etiology: { high: "Excessive exercise", low: "Metabolic syndrome, liver disease" } },
            { test: "Low-density lipoproteins (LDLs)", conventionalUnits: "Recommended: <130 mg/dL", siUnits: "", etiology: { high: "Chronic liver disease, familial hypercholesterolemia, nephrotic syndrome", low: "Hyperthyroidism" } },
            { test: "Very low-density lipoproteins (VLDLs)", conventionalUnits: "7-32 mg/dL", siUnits: "", etiology: { high: "Familial hypercholesterolemia, nephrotic syndrome", low: "Hyperthyroidism" } },
            { test: "Cortisol", conventionalUnits: "8 AM: 5-23 mcg/dL, 4 PM: 3-13 mcg/dL", siUnits: "8 AM: 138-635 nmol/L, 4 PM: 83-359 nmol/L", etiology: { high: "Cushing syndrome, hyperthyroidism", low: "Adrenal insufficiency, panhypopituitary states" } },
            { test: "Creatine kinase (CK)", conventionalUnits: "Male: 55-170 U/L, Female: 30-135 U/L", siUnits: "Male: 55-170 U/L, Female: 30-135 U/L", etiology: { high: "Musculoskeletal injury or disease, myocardial infarction, severe myocarditis, exercise, numerous IM injections", low: "" } },
            { test: "CK-MB", conventionalUnits: "<4%-6% of total CK", siUnits: "<0.4-0.6", etiology: { high: "Acute myocardial infarction", low: "" } },
            { test: "Creatinine", conventionalUnits: "Male: 0.6-1.2 mg/dL, Female: 0.5-1.1 mg/dL", siUnits: "Male: 53-106 µmol/L, Female: 44-97 µmol/L", etiology: { high: "Severe renal disease", low: "Decreased muscle mass, debilitation" } },
            { test: "Ferritin", conventionalUnits: "Male: 12-300 ng/mL, Female: 10-150 ng/mL", siUnits: "Male: 12-300 mcg/L, Female: 10-150 mcg/L", etiology: { high: "Anemia of chronic disease, sideroblastic anemia", low: "Iron-deficiency anemia" } },
            { test: "Folic acid (folate)", conventionalUnits: "5-25 ng/mL", siUnits: "11-57 nmol/L", etiology: { high: "Hypothyroidism, pernicious anemia", low: "Alcoholism, hemolytic anemia, inadequate diet, malabsorption syndrome, megaloblastic anemia" } },
            { test: "γ-Glutamyl transferase (GGT)", conventionalUnits: "Male and Female >45: 8-38 U/L, Female <45: 5-27 U/L", siUnits: "Male and Female >45: 8-38 U/L, Female <45: 5-27 U/L", etiology: { high: "Liver disease, infectious myocardial infarction, pancreatitis, hyperthyroidism", low: "Hypothyroidism" } },
            { test: "Glucose (fasting)", conventionalUnits: "74-106 mg/dL", siUnits: "4.1-5.9 mmol/L", etiology: { high: "Acute stress, Cushing disease, diabetes, hyperthyroidism, pancreatic insufficiency", low: "Addison's disease, hepatic disease, hypothyroidism, insulin overdosage, pancreatic tumor, pituitary hypofunction" } },
            { test: "Haptoglobin", conventionalUnits: "50-220 mg/dL", siUnits: "0.5-2.2 g/L", etiology: { high: "Infectious and inflammatory processes, cancer", low: "Hemolytic anemia, malnutrition, chronic liver disease" } },
            { test: "Insulin (fasting)", conventionalUnits: "6-26 µU/mL", siUnits: "43-186 pmol/L", etiology: { high: "Acromegaly, adenoma of pancreatic islet cells, Cushing syndrome", low: "Diabetes, hypopituitarism" } },
            { test: "Iron, total", conventionalUnits: "Male: 80-180 mcg/dL, Female: 60-160 mcg/dL", siUnits: "Male: 14-32 µmol/L, Female: 11-29 µmol/L", etiology: { high: "Excess RBC destruction, hepatitis, massive blood transfusion", low: "Anemia of chronic disease, iron-deficiency anemia, cancer" } },
            { test: "(Total) iron-binding capacity", conventionalUnits: "250-460 mcg/dL", siUnits: "45-82 µmol/L", etiology: { high: "Iron-deficient state, polycythemia", low: "Cirrhosis, chronic infections, pernicious anemia" } },
            { test: "Lactic acid (L-Lactate), venous", conventionalUnits: "5-20 mg/dL", siUnits: "0.6-2.2 mmol/L", etiology: { high: "Acidosis, liver disease, sepsis, shock", low: "" } },
            { test: "Lactic dehydrogenase (LDH)", conventionalUnits: "100-190 U/L", siUnits: "100-190 U/L", etiology: { high: "Heart failure, hemolytic disorders, hepatitis, metastatic cancer of liver, myocardial infarction, pernicious anemia, pulmonary embolus, skeletal muscle damage", low: "" } },
            { test: "LDH₁, isoenzymes", conventionalUnits: "17%-27%", siUnits: "0.17-0.27", etiology: { high: "Myocardial infarction, pernicious anemia", low: "" } },
            { test: "LDH₂, isoenzymes", conventionalUnits: "27%-37%", siUnits: "0.27-0.37", etiology: { high: "Pulmonary embolus, sickle cell crisis", low: "" } },
            { test: "LDH₃, isoenzymes", conventionalUnits: "18%-25%", siUnits: "0.18-0.26", etiology: { high: "Malignant lymphoma, pulmonary embolus", low: "" } },
            { test: "LDH₄, isoenzymes", conventionalUnits: "3%-8%", siUnits: "0.03-0.08", etiology: { high: "Systemic lupus erythematosus, pulmonary infarction", low: "" } },
            { test: "LDH₅, isoenzymes", conventionalUnits: "0%-5%", siUnits: "0.00-0.05", etiology: { high: "Heart failure, hepatitis, pulmonary embolus and infarction, skeletal muscle damage", low: "" } },
            { test: "Lipase", conventionalUnits: "0-160 U/L", siUnits: "0-160 U/L", etiology: { high: "Acute pancreatitis, hepatic disorders, perforated peptic ulcer", low: "" } },
            { test: "Magnesium", conventionalUnits: "1.3-2.1 mEq/L", siUnits: "0.65-1.05 mmol/L", etiology: { high: "Addison's disease, hypothyroidism, renal failure", low: "Chronic alcoholism, severe malabsorption" } },
            { test: "Osmolality", conventionalUnits: "285-295 mOsm/kg", siUnits: "285-295 mmol/kg", etiology: { high: "Chronic renal disease, diabetes, diabetes insipidus", low: "Addison's disease, diuretic therapy, SIADH, hypervolemia" } },
            { test: "O₂ saturation (arterial) (SaO₂)", conventionalUnits: ">95%", siUnits: ">0.95", etiology: { high: "Polycythemia", low: "Anemia, cardiac decompensation, respiratory disorders" } },
            { test: "Phosphatase, alkaline", conventionalUnits: "30-120 U/L", siUnits: "0.5-2.0 µkat/L", etiology: { high: "Biliary system obstruction, bone diseases, marked hyperparathyroidism, rickets", low: "Excess vitamin D ingestion, hypothyroidism" } },
            { test: "Phosphorus (phosphate)", conventionalUnits: "3.0-4.5 mg/dL", siUnits: "0.97-1.45 mmol/L", etiology: { high: "Bone cancer, hypoparathyroidism, renal disease, vitamin D intoxication, hypocalcemia", low: "Diabetes, hyperparathyroidism, vitamin D deficiency" } },
            { test: "Potassium", conventionalUnits: "3.5-5.0 mEq/L", siUnits: "3.5-5.0 mmol/L", etiology: { high: "Addison's disease, diabetic ketosis, massive tissue destruction, renal failure, infection, dehydration", low: "Cushing syndrome, diarrhea (severe), diuretic therapy, gastrointestinal fistula, starvation, vomiting" } },
            { test: "Progesterone (Female), Follicular phase", conventionalUnits: "<50 ng/dL", siUnits: "0.5-2.2 nmol/L", etiology: { high: "Adrenal hyperplasia, choriocarcinoma of ovary, pregnancy, cysts of ovary", low: "Threatened abortion, hypogonadism, amenorrhea, ovarian tumor" } },
            { test: "Progesterone (Female), Luteal phase", conventionalUnits: "300-2500 ng/dL", siUnits: "6.4-79.5 nmol/L", etiology: { high: "Adrenal hyperplasia, choriocarcinoma of ovary, pregnancy, cysts of ovary", low: "Threatened abortion, hypogonadism, amenorrhea, ovarian tumor" } },
            { test: "Progesterone (Female), Postmenopause", conventionalUnits: "<40 ng/dL", siUnits: "<1.28 nmol/L", etiology: { high: "Adrenal hyperplasia, choriocarcinoma of ovary, pregnancy, cysts of ovary", low: "Threatened abortion, hypogonadism, amenorrhea, ovarian tumor" } },
            { test: "Prostate-specific antigen (PSA)", conventionalUnits: "<4.0 ng/mL", siUnits: "<4.0 mcg/L", etiology: { high: "Prostate cancer, prostatitis, benign prostatic hypertrophy", low: "" } },
            { test: "Proteins, Total", conventionalUnits: "6.4-8.3 g/dL", siUnits: "64-83 g/L", etiology: { high: "Burns, cirrhosis (globulin fraction), dehydration, multiple myeloma (globulin fraction), shock, vomiting", low: "Liver disease, malabsorption" } },
            { test: "Proteins, Albumin", conventionalUnits: "3.5-5.0 g/dL", siUnits: "35-50 g/L", etiology: { high: "Dehydration", low: "Malnutrition, nephrotic syndrome, proteinuria, renal disease, severe burns" } },
            { test: "Proteins, Globulin", conventionalUnits: "2.3-3.4 g/dL", siUnits: "23-34 g/L", etiology: { high: "", low: "" } },
            { test: "Albumin/globulin ratio", conventionalUnits: "1.5:1-2.5:1", siUnits: "1.5:1-2.5:1", etiology: { high: "", low: "" } },
            { test: "Sodium", conventionalUnits: "136-145 mEq/L", siUnits: "136-145 mmol/L", etiology: { high: "Dehydration, impaired renal function, primary aldosteronism, corticosteroid therapy", low: "Addison's disease, diabetic ketoacidosis, diuretic therapy, excessive loss from GI tract, excessive perspiration, water intoxication" } },
            { test: "Testosterone (total)", conventionalUnits: "Male: 280-1080 ng/dL, Female: <70 ng/dL", siUnits: "Male: 280-1080 ng/dL, Female: <70 ng/dL", etiology: { high: "Polycystic ovary, virilizing tumors", low: "Hypofunction of testes, hypogonadism" } },
            { test: "T₄ (thyroxine), total", conventionalUnits: "Male: 4-12 mcg/dL, Female: 5-12 mcg/dL", siUnits: "Male: 59-135 nmol/L, Female: 71-142 nmol/L", etiology: { high: "Hyperthyroidism, thyroiditis, hepatitis, Graves' disease, thyroid cancer", low: "Cretinism, hypothyroidism, myxedema, Cushing syndrome, renal failure" } },
            { test: "T₄ (thyroxine), free", conventionalUnits: "0.8-2.8 ng/dL", siUnits: "10-36 pmol/L", etiology: { high: "Hyperthyroidism", low: "Hypothyroidism" } },
            { test: "T₃ uptake", conventionalUnits: "24%-34%", siUnits: "0.24-0.34", etiology: { high: "Hyperthyroidism", low: "Hypothyroidism" } },
            { test: "T₃ (triiodothyronine), total", conventionalUnits: "Age 20-50: 70-205 ng/dL, Age >50: 40-180 ng/dL", siUnits: "1.2-3.4 nmol/L, 0.60-2.8 nmol/L", etiology: { high: "Hyperthyroidism", low: "Hypothyroidism" } },
            { test: "Thyroid-stimulating hormone (TSH)", conventionalUnits: "2.0-10 µU/mL", siUnits: "2.0-10 mU/L", etiology: { high: "Myxedema, primary hypothyroidism", low: "Secondary hypothyroidism, hyperthyroidism" } },
            { test: "Aspartate aminotransferase (AST)", conventionalUnits: "0-35 U/L", siUnits: "0-0.58 µkat/L", etiology: { high: "Liver disease, myocardial infarction, pulmonary infarction, acute hepatitis", low: "Acute renal disease, diabetic ketoacidosis" } },
            { test: "Alanine aminotransferase (ALT)", conventionalUnits: "4-36 U/L", siUnits: "4-36 U/L", etiology: { high: "Liver disease, shock", low: "" } },
            { test: "Transferrin", conventionalUnits: "Male: 215-365 mg/dL, Female: 250-380 mg/dL", siUnits: "Male: 2.15-3.65 g/L, Female: 2.5-3.8 g/L", etiology: { high: "Iron-deficiency anemia, polycythemia vera", low: "Cirrhosis, pernicious anemia, sickle cell disease" } },
            { test: "Transferrin saturation (%)", conventionalUnits: "Male: 20%-50%, Female: 15%-50%", siUnits: "Male: 20%-50%, Female: 15%-50%", etiology: { high: "Hemolytic anemia, iron overdose", low: "Malnutrition" } },
            { test: "Triglycerides", conventionalUnits: "Male: 40-160 mg/dL, Female: 35-135 mg/dL", siUnits: "Male: 0.45-1.81 g/L, Female: 0.40-1.52 g/L", etiology: { high: "Diabetes, hyperlipidemia, hypothyroidism, liver disease", low: "Malnutrition" } },
            { test: "Troponin T (cTnT)", conventionalUnits: "<0.1 ng/mL", siUnits: "<0.1 mcg/L", etiology: { high: "Myocardial infarction, myocardial injury", low: "" } },
            { test: "Troponin I (cTnI)", conventionalUnits: "<0.03 ng/mL", siUnits: "<0.03 mcg/L", etiology: { high: "Myocardial infarction, myocardial injury", low: "" } },
            { test: "Urea nitrogen (BUN)", conventionalUnits: "10-20 mg/dL", siUnits: "3.6-7.1 mmol/L", etiology: { high: "Increase in protein catabolism (fever, sepsis, stress), renal disease, heart failure, myocardial infarction", low: "Malnutrition, severe liver damage" } },
            { test: "Uric acid", conventionalUnits: "Male: 4.0-8.5 mg/dL, Female: 2.7-7.3 mg/dL", siUnits: "Male: 0.24-0.51 mmol/L, Female: 0.16-0.43 mmol/L", etiology: { high: "Gout, gross tissue destruction, high-protein weight reduction diet, leukemia, renal failure", low: "Administration of uricosuric drugs" } },
            { test: "Vitamin B₁₂ (cobalamin)", conventionalUnits: "160-950 pg/mL", siUnits: "118-701 pmol/L", etiology: { high: "Chronic myeloid leukemia", low: "Strict vegetarianism, malabsorption syndrome, pernicious anemia, total or partial gastrectomy" } },
            { test: "Vitamin C (ascorbic acid)", conventionalUnits: "0.4-2.0 mg/dL", siUnits: "23-114 µmol/L", etiology: { high: "Excessive ingestion of vitamin C", low: "Connective tissue disorders, hepatic disease, renal disease, rheumatic fever, vitamin C deficiency" } },
            { test: "Vitamin D", conventionalUnits: "25-80 ng/dL", siUnits: "25-80 ng/dL", etiology: { high: "Excess dietary supplement", low: "Liver disease, malabsorption syndromes, osteoporosis, renal disease" } }
        ]
    },
    {
        title: "Hematology",
        icon: "🔬",
        values: [
            { test: "Bleeding time", conventionalUnits: "60-540 sec", siUnits: "60-540 sec", etiology: { high: "Aspirin ingestion, ineffective platelet function, thrombocytopenia, vascular disease, von Willebrand disease", low: "" } },
            { test: "Activated partial thromboplastin time (aPTT)", conventionalUnits: "30-40 sec", siUnits: "30-40 sec", etiology: { high: "Deficiency of factors I, II, V, VIII, IX, X, XI, XII, hemophilia, heparin therapy, liver disease", low: "Early DIC, extensive cancer" } },
            { test: "Prothrombin time (protime, PT)", conventionalUnits: "11-12.5 sec", siUnits: "11-12.5 sec", etiology: { high: "Deficiency of factors I, II, V, VII, and X, liver disease, vitamin K deficiency, warfarin therapy", low: "" } },
            { test: "Fibrinogen", conventionalUnits: "200-400 mg/dL", siUnits: "2-4 g/L", etiology: { high: "Burns (after first 36 hr), inflammatory disease, stroke, myocardial infarction", low: "Burns (during first 36 hr), DIC, severe liver disease, malnutrition" } },
            { test: "Fibrin split (degradation) products", conventionalUnits: "<10 mcg/mL", siUnits: "<10 mg/L", etiology: { high: "Acute DIC, massive hemorrhage, primary fibrinolysis", low: "" } },
            { test: "D-Dimer", conventionalUnits: "<250 ng/mL", siUnits: "<250 mcg/L", etiology: { high: "DIC, myocardial infarction, VTE, unstable angina, cancer", low: "" } },
            { test: "Erythrocyte count (altitude dependent)", conventionalUnits: "Male: 4.7-6.1 x 10⁶/µL, Female: 4.2-5.4 x 10⁶/µL", siUnits: "Male: 4.7-6.1 x 10¹²/L, Female: 4.2-5.4 x 10¹²/L", etiology: { high: "Dehydration, high altitudes, polycythemia vera, severe COPD", low: "Anemia, leukemia, hemorrhage, cancer, chronic illness, kidney disease" } },
            { test: "Mean corpuscular volume (MCV)", conventionalUnits: "80-95 fL", siUnits: "80-95 fL", etiology: { high: "Alcoholism, liver disease, macrocytic anemia", low: "Microcytic anemia, thalassemia" } },
            { test: "Mean corpuscular hemoglobin (MCH)", conventionalUnits: "27-31 pg", siUnits: "27-31 pg", etiology: { high: "Macrocytic anemia", low: "Microcytic anemia" } },
            { test: "Mean corpuscular hemoglobin concentration (MCHC)", conventionalUnits: "32%-36%", siUnits: "32-36 g/dL", etiology: { high: "Spherocytosis", low: "Iron deficiency anemia, thalassemia" } },
            { test: "Erythrocyte sedimentation rate (ESR)", conventionalUnits: "<20 mm/hr (some gender variation)", siUnits: "<20 mm/hr (some gender variation)", etiology: { high: "Moderate increase: acute hepatitis, myocardial infarction, rheumatoid arthritis. Marked increase: acute and severe bacterial infections, cancer, pelvic inflammatory disease", low: "Malaria, severe liver disease, sickle cell anemia" } },
            { test: "Hematocrit (altitude dependent)", conventionalUnits: "Male: 42%-52%, Female: 37%-47%", siUnits: "Male: 0.42-0.52, Female: 0.37-0.47", etiology: { high: "Dehydration, high altitudes, polycythemia, COPD", low: "Anemia, hemorrhage, overhydration, some kidney disease" } },
            { test: "Hemoglobin (altitude dependent)", conventionalUnits: "Male: 14-18 g/dL, Female: 12-16 g/dL", siUnits: "Male: 140-180 g/L, Female: 120-160 g/L", etiology: { high: "COPD, high altitudes, polycythemia, dehydration, burns", low: "Anemia, hemorrhage, kidney disease, cancer" } },
            { test: "Hemoglobin, glycosylated (A1C)", conventionalUnits: "4.0%-5.6%", siUnits: "4.0%-5.6%", etiology: { high: "Diabetes, pre-diabetes", low: "Sickle cell anemia, renal failure, pregnancy" } },
            { test: "Platelets (thrombocytes)", conventionalUnits: "150-400 x 10³/µL", siUnits: "150-400 x 10⁹/L", etiology: { high: "Acute infections, chronic granulocytic leukemia, chronic pancreatitis, cirrhosis, collagen disorders, polycythemia, postsplenectomy", low: "Acute leukemia, DIC, thrombocytopenic purpura" } },
            { test: "Reticulocyte count", conventionalUnits: "0.5%-2.0% of RBC", siUnits: "0.5%-2.0% of RBC", etiology: { high: "Hemolytic anemia, polycythemia vera", low: "Hypoproliferative anemias, macrocytic anemia, microcytic anemia" } },
            { test: "White blood cell count", conventionalUnits: "5000-10000/mm³", siUnits: "5.0-10.0 x 10⁹/L", etiology: { high: "Inflammatory and infectious processes, leukemia", low: "Aplastic anemia, effects of chemotherapy and irradiation" } },
            { test: "WBC, Segmented neutrophils", conventionalUnits: "55%-70%", siUnits: "0.55-0.70", etiology: { high: "Bacterial infections, collagen diseases, Hodgkin's lymphoma", low: "Aplastic anemia, viral infections" } },
            { test: "WBC, Band neutrophils", conventionalUnits: "0-8%", siUnits: "0-0.08", etiology: { high: "Acute infections", low: "" } },
            { test: "WBC, Lymphocytes", conventionalUnits: "20%-40%", siUnits: "0.20-0.40", etiology: { high: "Chronic infections, lymphocytic leukemia, mononucleosis, viral infections", low: "Corticosteroid therapy, whole body radiation" } },
            { test: "WBC, Monocytes", conventionalUnits: "2%-8%", siUnits: "0.02-0.08", etiology: { high: "Chronic inflammatory disorders, malaria, monocytic leukemia, acute infections, Hodgkin's lymphoma", low: "" } },
            { test: "WBC, Eosinophils", conventionalUnits: "1%-4%", siUnits: "0.01-0.04", etiology: { high: "Allergic reactions, eosinophilic and chronic granulocytic leukemia, parasitic disorders, Hodgkin's lymphoma", low: "Corticosteroid therapy" } },
            { test: "WBC, Basophils", conventionalUnits: "0.5%-1%", siUnits: "0.005-0.01", etiology: { high: "Hypothyroidism, ulcerative colitis, myeloproliferative diseases", low: "Hyperthyroidism, stress" } }
        ]
    },
    {
        title: "Serology-Immunology",
        icon: "🛡️",
        values: [
            { test: "Antinuclear antibody (ANA)", conventionalUnits: "Negative at 1:40 dilution", siUnits: "Negative at 1:40 dilution", etiology: { high: "Chronic hepatitis, rheumatoid arthritis, scleroderma, systemic lupus erythematosus", low: "" } },
            { test: "Anti-DNA antibody", conventionalUnits: "<5 IU/mL", siUnits: "<5 IU/mL", etiology: { high: "Systemic lupus erythematosus", low: "" } },
            { test: "Anti-Sm (Smith)", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Systemic lupus erythematosus", low: "" } },
            { test: "C-reactive protein (CRP)", conventionalUnits: "<1.0 mg/dL", siUnits: "<10.0 mg/L", etiology: { high: "Acute infections, any inflammatory condition, widespread cancer", low: "" } },
            { test: "Carcinoembryonic antigen (CEA)", conventionalUnits: "Nonsmoker: <3 ng/mL, Smoker: <5 ng/mL", siUnits: "Nonsmoker: <3 mcg/L, Smoker: <5 mcg/L", etiology: { high: "Cancer of colon, liver, pancreas, cigarette smoking; inflammatory bowel disease", low: "" } },
            { test: "Complement, total hemolytic (CH₅₀)", conventionalUnits: "30-75 U/mL", siUnits: "30-75 U/mL", etiology: { high: "Cancer, ulcerative colitis", low: "Bacterial endocarditis, glomerulonephritis, rheumatoid arthritis, systemic lupus erythematosus" } },
            { test: "Direct Coombs or direct antihuman globulin test (DAT)", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Acquired hemolytic anemia, drug reactions, transfusion reactions", low: "" } },
            { test: "Fluorescent treponemal antibody absorption (FTA-Abs)", conventionalUnits: "Negative or nonreactive", siUnits: "Negative or nonreactive", etiology: { high: "Syphilis", low: "" } },
            { test: "Hepatitis A antibody", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Hepatitis A", low: "" } },
            { test: "Hepatitis B surface antigen (HBsAg)", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Hepatitis B", low: "" } },
            { test: "Hepatitis C antibody", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Hepatitis C", low: "" } },
            { test: "Monospot or monotest", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Infectious mononucleosis", low: "" } },
            { test: "Rheumatoid factor (RF)", conventionalUnits: "Negative or titer <1:17", siUnits: "Negative or titer <1:17", etiology: { high: "Rheumatoid arthritis, Sjögren's syndrome, systemic lupus erythematosus", low: "" } },
            { test: "RPR", conventionalUnits: "Negative or nonreactive", siUnits: "Negative or nonreactive", etiology: { high: "Leprosy, malaria, rheumatoid arthritis, systemic lupus erythematosus, syphilis", low: "" } },
            { test: "VDRL", conventionalUnits: "Negative or nonreactive", siUnits: "Negative or nonreactive", etiology: { high: "Syphilis", low: "" } }
        ]
    },
    {
        title: "Urine Chemistry",
        icon: "💧",
        values: [
            { test: "Acetone", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Diabetes, high-fat and low-carbohydrate diets, starvation", low: "" } },
            { test: "Aldosterone", specimen: "24 hr", conventionalUnits: "2-26 mcg/day", siUnits: "6-72 nmol/day", etiology: { high: "Primary aldosteronism: adrenocortical tumors. Secondary aldosteronism: cirrhosis, heart failure, hyperkalemia, hyponatremia", low: "ACTH deficiency, Addison's disease, corticosteroid therapy, hypokalemia" } },
            { test: "Amylase", specimen: "24 hr", conventionalUnits: "<5000 Somogyi U/day", siUnits: "6.5-48.1 U/hr", etiology: { high: "Acute pancreatitis", low: "" } },
            { test: "Bence Jones protein", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Multiple myeloma", low: "" } },
            { test: "Bilirubin", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Liver disorders", low: "" } },
            { test: "Catecholamines, Epinephrine", specimen: "24 hr", conventionalUnits: "<20 mcg/day", siUnits: "<109 nmol/day", etiology: { high: "Heart failure, pheochromocytoma, progressive muscular dystrophy", low: "" } },
            { test: "Catecholamines, Norepinephrine", specimen: "24 hr", conventionalUnits: "<100 mcg/day", siUnits: "<590 nmol/day", etiology: { high: "Heart failure, pheochromocytoma, progressive muscular dystrophy", low: "" } },
            { test: "Cortisol", specimen: "24 hr", conventionalUnits: "<100 mcg/day", siUnits: "<276 nmol/day", etiology: { high: "Adrenal cancer, Cushing syndrome, hyperthyroidism, obesity, stress", low: "Addison's disease, hypothyroidism, liver disease" } },
            { test: "Creatinine clearance", specimen: "24 hr", conventionalUnits: "Male: 107-139 mL/min, Female: 87-107 mL/min", siUnits: "Male: 1.78-2.32 mL/sec, Female: 1.45-1.78 mL/sec", etiology: { high: "Exercise, pregnancy", low: "Cirrhosis, heart failure, renal disease" } },
            { test: "Estrogens, Female (Nonpregnant)", specimen: "24 hr", conventionalUnits: "4-60 mcg/day", siUnits: "4-60 mcg/day", etiology: { high: "Gonadal or adrenal tumor", low: "Endocrine disturbance, ovarian dysfunction, menopause" } },
            { test: "Estrogens, Female (Postmenopause)", specimen: "24 hr", conventionalUnits: "<20 mcg/day", siUnits: "<20 mcg/day", etiology: { high: "Gonadal or adrenal tumor", low: "Endocrine disturbance, ovarian dysfunction, menopause" } },
            { test: "Estrogens, Male", specimen: "24 hr", conventionalUnits: "4-25 mcg/day", siUnits: "4-25 mcg/day", etiology: { high: "Gonadal or adrenal tumor", low: "" } },
            { test: "Glucose", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Diabetes, pituitary disorders", low: "" } },
            { test: "Hemoglobin", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Extensive burns, glomerulonephritis, hemolytic anemia, hemolytic transfusion reaction", low: "" } },
            { test: "5-Hydroxyindole acetic acid (5-HIAA)", specimen: "24 hr", conventionalUnits: "2-8 mg/day", siUnits: "10-40 µmol/day", etiology: { high: "Malignant carcinoid syndrome", low: "" } },
            { test: "Ketones", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Diabetes, starvation, dehydration", low: "" } },
            { test: "Metanephrine", specimen: "24 hr", conventionalUnits: "<1.3 mg/day", siUnits: "<7 µmol/day", etiology: { high: "Pheochromocytoma", low: "" } },
            { test: "Myoglobin", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Crushing injuries, electric injuries, extreme physical exertion", low: "" } },
            { test: "Osmolality", specimen: "Random", conventionalUnits: "50-1200 mOsm/kg", siUnits: "50-1200 mmol/kg", etiology: { high: "Heart failure, liver disease, shock, SIADH", low: "Aldosteronism, diabetes insipidus, hypokalemia, pyelonephritis" } },
            { test: "pH", specimen: "Random", conventionalUnits: "4.6-8.0", siUnits: "4.6-8.0", etiology: { high: "Urinary tract infection, urine allowed to stand at room temperature", low: "Respiratory or metabolic acidosis" } },
            { test: "Protein", specimen: "Random", conventionalUnits: "0-8 mg/dL", siUnits: "0-8 mg/dL", etiology: { high: "Acute and chronic renal disease, heart failure", low: "" } },
            { test: "Protein (quantitative)", specimen: "24 hr", conventionalUnits: "50-80 mg/day", siUnits: "50-80 mg/day", etiology: { high: "Heart failure, inflammatory process of urinary tract, nephritis, nephrosis, strenuous exercise", low: "" } },
            { test: "Sodium", specimen: "24 hr", conventionalUnits: "40-220 mEq/day", siUnits: "40-220 mmol/day", etiology: { high: "Acute tubular necrosis", low: "Hyponatremia" } },
            { test: "Specific gravity", specimen: "Random", conventionalUnits: "1.005-1.030", siUnits: "1.005-1.030", etiology: { high: "Albuminuria, dehydration, glycosuria, fever", low: "Diabetes insipidus, hypothermia, diuresis" } },
            { test: "Uric acid", specimen: "24 hr", conventionalUnits: "250-750 mg/day", siUnits: "1.48-4.43 mmol/day", etiology: { high: "Gout, leukemia", low: "Nephritis" } },
            { test: "Urobilinogen", specimen: "Random", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Hemolytic disease, hepatic parenchymal cell damage, liver disease", low: "Complete bile duct obstruction" } },
            { test: "Vanillylmandelic acid (VMA)", specimen: "24 hr", conventionalUnits: "<6.8 mg/day", siUnits: "<35 µmol/day", etiology: { high: "Pheochromocytoma", low: "" } }
        ]
    },
    {
        title: "Fecal Analysis",
        icon: "💩",
        values: [
            { test: "Fecal fat", conventionalUnits: "2-6 g/24 hr", siUnits: "7-21 mmol/day", etiology: { high: "Common bile duct obstruction, malabsorption syndrome, pancreatic disease", low: "" } },
            { test: "Mucus", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Mucous colitis, spastic constipation", low: "" } },
            { test: "Pus", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Chronic bacillary dysentery, chronic ulcerative colitis, localized abscesses", low: "" } },
            { test: "Blood", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Anal fissures, gastrointestinal cancer, hemorrhoids, inflammatory bowel disease, peptic ulcer disease", low: "" }, notes: "Ingestion of meat may produce false-positive results. Patient may be placed on a meat-free diet for 3 days before the test." },
            { test: "Color, Brown", conventionalUnits: "", siUnits: "", etiology: { high: "Various color depending on diet", low: "" } },
            { test: "Color, Clay", conventionalUnits: "", siUnits: "", etiology: { high: "Biliary obstruction, presence of barium sulfate", low: "" } },
            { test: "Color, Tarry", conventionalUnits: "", siUnits: "", etiology: { high: "More than 100 mL of blood in gastrointestinal tract", low: "" } },
            { test: "Color, Red", conventionalUnits: "", siUnits: "", etiology: { high: "Blood in large intestine", low: "" } },
            { test: "Color, Black", conventionalUnits: "", siUnits: "", etiology: { high: "Blood in upper gastrointestinal tract, iron medication", low: "" } }
        ]
    },
    {
        title: "Cerebrospinal Fluid Analysis",
        icon: "🧠",
        values: [
            { test: "Pressure", conventionalUnits: "<20 mm H₂O", siUnits: "<20 mm H₂O", etiology: { high: "Hemorrhage, intracranial tumor, meningitis", low: "Head injury, spinal tumor, subdural hematoma" } },
            { test: "Blood", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Intracranial hemorrhage", low: "" } },
            { test: "WBC (age dependent)", conventionalUnits: "0-5 cells/µL", siUnits: "0-5 x 10⁶ cells/L", etiology: { high: "CNS infection or inflammation", low: "" } },
            { test: "RBC", conventionalUnits: "Negative", siUnits: "Negative", etiology: { high: "Intracranial hemorrhage", low: "" } },
            { test: "Chloride", conventionalUnits: "700-750 mg/dL", siUnits: "118-132 mmol/L", etiology: { high: "Uremia", low: "CNS bacterial infection" } },
            { test: "Glucose", conventionalUnits: "50-75 mg/dL", siUnits: "2.2-3.9 mmol/L", etiology: { high: "CNS viral infection, diabetes", low: "Bacterial infection, CNS tuberculosis" } },
            { test: "Protein, Lumbar", conventionalUnits: "15-45 mg/dL", siUnits: "0.15-0.45 g/L", etiology: { high: "Guillain-Barré syndrome, poliomyelitis, trauma", low: "" } },
            { test: "Protein, Cisternal", conventionalUnits: "15-25 mg/dL", siUnits: "0.15-0.25 g/L", etiology: { high: "CNS syphilis", low: "" } },
            { test: "Protein, Ventricular", conventionalUnits: "5-15 mg/dL", siUnits: "0.05-0.15 g/L", etiology: { high: "Acute meningitis, brain tumor, chronic CNS infection, multiple sclerosis", low: "" } }
        ]
    }
];

    // --- APP LOGIC ---
    document.addEventListener('DOMContentLoaded', () => {
        const labValuesHost = document.getElementById('labValuesHost');
        const labSearchInput = document.getElementById('labSearchInput');
        const noResultsDiv = document.getElementById('no-lab-results');
        const categoryFiltersContainer = document.getElementById('labCategoryFilters')?.querySelector('.flex');

        function renderCategoryFilters() {
            if (!categoryFiltersContainer) return;
            categoryFiltersContainer.innerHTML = '';
            allLabValuesData.forEach((category, index) => {
                const categoryId = `lab-category-${category.title.replace(/[^a-zA-Z0-9]/g, '-')}`;
                const button = document.createElement('button');
                button.className = `category-filter-btn ${index === 0 ? 'active' : ''}`;
                button.textContent = category.title;
                button.dataset.targetId = categoryId;
                
                button.addEventListener('click', () => {
                    document.getElementById(categoryId)?.scrollIntoView({ behavior: 'smooth', block: 'start' });
                });
                categoryFiltersContainer.appendChild(button);
            });
        }

        function renderLabValues(filteredData = allLabValuesData) {
            labValuesHost.innerHTML = '';
            const hasResults = filteredData.some(cat => cat.values.length > 0);
            noResultsDiv.classList.toggle('hidden', hasResults);

            filteredData.forEach(category => {
                if (category.values.length === 0) return;

                const categoryId = `lab-category-${category.title.replace(/[^a-zA-Z0-9]/g, '-')}`;
                const categorySection = document.createElement('section');
                categorySection.id = categoryId;
                categorySection.className = 'mb-12 scroll-mt-24';

                const categoryTitleEl = document.createElement('h2');
                categoryTitleEl.className = 'text-2xl font-bold text-text-secondary mb-6 pb-2 border-b border-b-glass-border flex items-center gap-3';
                categoryTitleEl.innerHTML = `<span class="text-3xl">${category.icon}</span> ${category.title}`;
                categorySection.appendChild(categoryTitleEl);
                
                const valuesContainer = document.createElement('div');
                valuesContainer.className = 'space-y-4';

                category.values.forEach(val => {
                    const details = document.createElement('details');
                    details.className = 'lab-value-card';
                    
                    details.innerHTML = `
                        <summary>
                            <span class="font-semibold text-text-primary">${val.test} ${val.specimen ? `<span class="text-xs font-normal text-text-accent">(${val.specimen})</span>` : ''}</span>
                            <span class="summary-arrow text-text-accent">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </span>
                        </summary>
                        <div class="lab-value-details">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-6">
                                <div class="bg-slate-900/50 p-3 rounded-lg"><div class="text-sm text-text-accent">Conventional Units</div><div class="font-semibold">${val.conventionalUnits || 'N/A'}</div></div>
                                <div class="bg-slate-900/50 p-3 rounded-lg"><div class="text-sm text-text-accent">SI Units</div><div class="font-semibold">${val.siUnits || 'N/A'}</div></div>
                            </div>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                                <div class="etiology-column">
                                    <h4 class="font-bold mb-2 high">Possible High Etiology</h4>
                                    <p class="text-sm text-text-secondary">${val.etiology.high || 'N/A'}</p>
                                </div>
                                <div class="etiology-column">
                                    <h4 class="font-bold mb-2 low">Possible Low Etiology</h4>
                                    <p class="text-sm text-text-secondary">${val.etiology.low || 'N/A'}</p>
                                </div>
                            </div>
                            ${val.notes ? `<div class="lab-notes"><strong>Note:</strong> ${val.notes}</div>` : ''}
                        </div>
                    `;
                    valuesContainer.appendChild(details);
                });

                categorySection.appendChild(valuesContainer);
                labValuesHost.appendChild(categorySection);
            });
        }

        function handleLabSearch() {
            const searchTerm = labSearchInput.value.toLowerCase().trim();
            const filteredData = !searchTerm ? allLabValuesData : allLabValuesData.map(category => ({
                ...category,
                values: category.values.filter(value => value.test.toLowerCase().includes(searchTerm))
            }));
            renderLabValues(filteredData);
        }

        labSearchInput.addEventListener('input', handleLabSearch);
        renderCategoryFilters();
        renderLabValues();
    });
</script>
</body>
</html>
