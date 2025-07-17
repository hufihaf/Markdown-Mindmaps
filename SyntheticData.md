## Explanation
--- 
What is **Synthetic data**?

How is it made?
- not real, but *realistic*

How does it compare to *real data*?    

---

## Subdomains of Synthetic Data

#### Synthetic Tabular Data, Image Data, Text Data, Time-Series Data, Audio/Video:

  - Typically made by another generation model! These are designed to mimic sensor logs, common financial sequences, waveforms, etc.
  - Synthetic is a distant abstraction from real data, but not unreliable.
		  - real data -> 
		  - train the data generation model -> 
		  - test the model -> 
		  - synthetic data -> 
		  - train the synthetic AI ->
		  - test the model -> 
		  - output.


### Subdomains, By Generation Method:

More direct (using real data, just not precise):
- Rule-Based Simulation
- Statistical Sampling

Less direct (AI, slight changes for security)
- Generative Models
	  - GANs (Generative Adversarial Networks)
	  - VAEs (Variational Autoencoders)
	  - Diffusion models
- Data Augmentation
	  - Slight modifications to real data (e.g., image flips, rotations)

---

## How ML Training with Synthetic Data Works

1. **Generate the Synthetic Dataset**
2. **Label the Data**
3. **Train the Model**

4. **Validate/Test on Real Data**
   - Models trained on synthetic data are usually tested or fine-tuned on real validation sets to ensure generalization.

## Is Synthetic Data Fake? Will It Harm the Model?

### Benefits
- **Data Privacy**: Avoids using sensitive real-world data.
- **Rare Events**: Can simulate edge cases or dangerous situations (e.g., accidents for self-driving cars -> NVIDIA).
- **Infinite Scaling**: You can generate as much as needed (Waymo cars are trained on billions of synthetic miles)
- Easier to gather
### Risks
- **Distribution Shift**: If synthetic data doesn't match the real-world data distribution well, the model may not generalize. What if a car frequently experiences a lighting condition that it was not trained on?
- **Overfitting to Unrealistic Features**: Poorly generated synthetic data may introduce biases or artifacts.
- **Lack of Diversity**: Synthetic data is usually smoothed out, averagy stuff -> an LLM trained on this may produce bland results
### Best Practice
- Use synthetic data to **augment**, not replace, real data
- Always **validate on real data**.

