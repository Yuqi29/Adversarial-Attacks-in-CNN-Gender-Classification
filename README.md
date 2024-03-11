# Adversarial-Attacks-in-CNN-Gender-Classification

This project build a gender classification Convolutional Neural Network (CNN), with dataset gathered from online search engine duckduckgo.com, backbone of resnet18, and trained from transfer learning. More details can be found in [the paper](https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/blob/main/doc/Interpretation%20and%20Adversarial%20Attacks%20in%20CNN%20Gender%20Classification.pdf).

The training result shows a gender bias, and the curiosity starts here. An analysis and adversarial attack is then conducted to test the ability and safety of the network.

<img width="946" alt="Capture d’écran 2024-03-11 à 9 04 50 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/5d055dd2-3a24-45d7-a11a-9b5ccc87c1c6">

Figure 1. Biased CNN gender classifier with wrong results

Using interpretation tools of Local Interpretable Model-agnostic Explanations (LAME) and SHapley Additive exPlanation (SHAP), it reveals that for thie network, the main clue of femininity comes from long hair, makeup features and facial features, while the source of masculinity is based on beard, facial features and tattoos. This result shows a clear sterotype of gender. 

<img width="281" alt="Capture d’écran 2024-03-11 à 9 26 37 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/52b69cfd-9283-4922-8587-c5462b376205">
<img width="285" alt="Capture d’écran 2024-03-11 à 9 26 52 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/02520265-a428-4395-933e-c58786a707de">
<img width="294" alt="Capture d’écran 2024-03-11 à 9 27 11 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/11a1c39c-5297-4594-bc1d-7159aeb5c8f5">

Fig 2. Examples of interpretation result of a girl with long hair, a female with short hair and makeup and a male with beard

Loop back to the intial picture that drew our curiosity, the same tools show that predicted masculinity came from big muscles and the dumbbell.

<img width="387" alt="Capture d’écran 2024-03-11 à 9 29 48 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/8b45174c-524d-4f6c-8e19-5cd599df8efb">

Fig 3. Explanations of a muscular female

Further adversarial attack shows that adding noise (white block) to the input results in a sever decrease in masculine prediction.

<img width="820" alt="Capture d’écran 2024-03-11 à 9 11 54 AM" src="https://github.com/Yuqi29/Adversarial-Attacks-in-CNN-Gender-Classification/assets/92478707/1c934254-f469-44f4-a39b-62636c7d25da">

Figure 4. CNN predictions with and without adversarial attacks Above: Prediction results of the original muscular female image Below: Prediction results of the original muscular female image with adversarial attack (white block)


