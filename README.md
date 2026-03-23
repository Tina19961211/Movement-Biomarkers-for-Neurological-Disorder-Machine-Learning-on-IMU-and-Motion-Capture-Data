🧠 Gait Analysis for Ataxia Detection
Turning Human Movement into Meaningful Signals for Rehabilitation and Wearables
🌱 Why This Project Exists

Walking looks simple, but it is not.

It is a continuous conversation between the brain and the body. Every step depends on timing, coordination, and symmetry. When that coordination is disrupted, such as in cerebellar ataxia, walking becomes unstable, irregular, and unpredictable.

In clinical settings today, gait assessment is still largely based on observation. While experienced clinicians are highly skilled, subtle changes can be missed, especially in early stages. Progress is also difficult to measure objectively over time.

This project aims to change that.

The goal is to move from observation to measurement, and from intuition to data-driven insight, with a long-term vision of integrating these insights into wearable technologies.

🔬 What This Project Does

This notebook transforms raw motion capture data into clinically meaningful insights.

It focuses on one central question:

Can left-right asymmetry in movement reliably detect ataxic gait?

To answer this, the project:

Normalizes human motion data
Extracts biomechanical asymmetry features
Validates those features statistically
Uses machine learning to classify gait patterns
⚙️ Pipeline Overview
1. Data Normalization

People differ in height, posture, and position relative to the camera. Raw coordinates are not directly comparable.

To address this, all joint positions are normalized relative to the hip midpoint, which approximates the body’s center of mass.

This ensures that the analysis reflects movement patterns rather than absolute position.

2. Asymmetry Feature Engineering

Ataxia often presents as imbalance between the left and right sides of the body.

We quantify this using:

asymmetry = |Left - Right| / average(Left + Right)

Key features include:

Hip movement asymmetry
Knee movement asymmetry
Stride speed asymmetry

These features are clinically meaningful and directly related to stability and fall risk.

3. Statistical Validation

To verify that these features truly differentiate gait types, the Mann–Whitney U test is applied.

Results show that:

Hip asymmetry is statistically significant
Knee asymmetry is statistically significant
Stride speed asymmetry is statistically significant

This confirms that asymmetry is a meaningful and reliable signal.

4. Machine Learning Classification

A Random Forest classifier is trained to distinguish between normal and ataxic gait.

This model is chosen because it:

Handles nonlinear relationships
Is robust to noise
Provides interpretable feature importance
📊 Results
Model Performance
Class	Precision	Recall	F1 Score
Normal	0.72	0.65	0.68
Ataxia	0.68	0.75	0.71
Key Insight

The model correctly identifies 75 percent of individuals with ataxia.

This is important in clinical contexts, where missing pathological gait can delay intervention.

Feature Importance
Hip asymmetry is the most informative feature
Stride speed asymmetry follows
Knee asymmetry also contributes meaningfully

This aligns with biomechanics, where the hip plays a central role in stability and propulsion.

🚨 High-Risk Detection

The model identifies individuals with gait patterns consistent with ataxia.

These individuals may benefit from:

Further clinical evaluation
Fall risk assessment
Targeted rehabilitation strategies
🦾 Implications for Wearable Devices

These findings can be translated directly into real-world technologies.

Potential applications include:

Smart insoles

Detect asymmetry in real time
Provide propulsion support on the weaker side

Exoskeletons

Deliver side-specific assistance
Adapt to user gait patterns

Biofeedback systems

Provide real-time cues to improve symmetry
Support motor learning

Remote monitoring tools

Track gait changes over time
Enable early intervention
🧑‍⚕️ Clinical Meaning

Asymmetry reflects:

Uneven force distribution
Neuromotor impairment
Compensation strategies
Increased joint stress

These insights allow clinicians to move beyond observation toward objective and personalized care.

🧪 Tech Stack
pandas, numpy for data processing
scipy for statistical analysis
scikit-learn for machine learning
seaborn and matplotlib for visualization
🚀 Key Takeaways
Lower limb asymmetry is a strong marker of ataxic gait
Objective metrics can support clinical decision-making
Simple features can produce meaningful predictions
This work connects rehabilitation, machine learning, and wearable technology
🌍 Bigger Vision

This project represents a shift:

From subjective assessment to objective measurement
From clinic-based evaluation to continuous monitoring
From reactive care to proactive intervention

The long-term goal is to turn movement data into actionable insights that improve independence, safety, and quality of life.

🤝 Collaboration

If you are working in:

Wearable technology
Rehabilitation science
Biomechanics
Human-centered AI

I would love to connect and collaborate.
