# Excel-Transformer
> **Note**: This project was previously hosted publicly on my other gitHub account. It has been copied here for continued development and the other repository has been made private.

## Description
A Microsoft Excel demonstration of the transformer from the 'Attention Is All You Need' paper. This Excel document implements a basic two-example mini-batch of the transformer from the aforementioned paper. The document aims to provide a basic numerical example which illustrates the internal workings of a transformer. The transformer contains two layers, with each layer containing a two-headed encoder and decoder. This work assumes that the reader understands how the internal workings of a transformer operate. If you do not understand this, I recommend looking at all the resources in the acknowledgments section, particularly the last three. Then, once this is understood, this material will make more sense.

## Features
- The transformer contains two layers with each layer containing an encoder and decoder. The attention mechanism in every layer utilizes two heads.
- The excel doument outlines the full forward, backward pass and gradient update for a mini-batch containing two examples.

## Glossary

- **SS**: Similiratiy Score
  
- **SSS**: Scaled Similarity Score

- **A, B, C**: Used to represent the position of input to the softmax function. 

- **SA, SB, SC**: The softmaxed version of the inputs A, B, and C, respectively. 

- **WR**: Weighted Representation

- **Missing terms**: If there are any other terms that you feel should be added, please contact me.

## Usage / Instructions
- There are two sheets: "Transformer EX1" and "Transformer EX2". These contain the forward and backward passes for individual training examples. The contents of each of the example sheets is contained within rows 1045-3219 and columns A-VT. WHEN NAVIGATING AROUND THE EXCEL FILE, ZOOM OUT AS FAR AS POSSIBLE. THIS WILL MAKE THE STRUCTURE OF THE DOCUMENT CLEARER. AFTER FINDING THE SECTION YOU ARE INTERESTED IN, YOU CAN THEN ZOOM IN TO FURTHER EXPLORE IT.
- The inputs to the encoder and decoder can be found at the middle bottom of the "DECODER 0" and "ENCODER 0" and are contained within the "Embedding" Layer.
- The output and cost calculation is centered and above "DECODER 1".
- The "PARAMETER UPDATES" sheet contains the calculations involved in performing a gradient step using the ADAM optimizer for all the parameters within the example. This section does not use the learning rate scheduler that was used in the original "Attention is All You Need" paper.
- The Transformer has been broken down into modules. In these modules, the green cells represent the flow of the forward pass and the red cells represent the flow of the backward pass.
- On other occasions, there are other colored cells that represent the flow of the forward and backward passes in the model. In these cases, the darker shades of the color represent the forward pass and the lighter shades represent the backward pass. I have tried to keep the colors consistent and have them represent the same token position throughout the Excel document; however, this was not always possible, and I have prioritized readability over strict adherence to these rules.
- On the two example sheets "Transformer EX1" and "Transformer EX2", the boxes with parameter gradients inside them that are colored pink contain the parameter gradients accumulated total for that layer over the course of that particular layer. These gradient accumulations are then used in the "PARAMETER UPDATES" sheet in order to calculate the total parameter gradients accumulated total for two example mini-batch.
- As mentioned, there are two heads per attention layer. The head calculations are separated by cells forming a dashed line.
- Many of the formulas within the document use Excel array/matrix formulas. Sometimes clicking on cells with these formulas in them can take away this formatting which may lead to errors causing all cells with formulas dependent on that cell to throw an error which will be denoted by "#########" if this occurs locate the cell (trace back to where the formulas are no longer "########") and then when inside the cell hit "ctrl+shift+enter" this will cause excel to treat it as an array operation again.

## Contributions
As the sole creator of this educational material on the underlying mechanisms within transformers, my goal is to provide clear, accurate, and accessible explanations that can benefit learners at all levels. While I am not seeking direct contributions to the material at this time, your insights, especially in identifying and reporting errors, are invaluable for maintaining the quality and accuracy of this resource.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

The layer normalization portions of this work are derived from "Understanding the backward pass through Batch Normalization Layer" by Dean Attali, licensed under the MIT License (MIT). Copyright (c) 2016 Dean Attali.

## Acknowledgments
- I'm thankful to Dean Attali for his clear and practical explanation of Batch Normalization (which I then adapted into layer normalization), particularly through his discussion on "Understanding the backward pass through Batch Normalization Layer." His work has been a valuable resource in understanding complex machine learning concepts and implementing them in this project. Frederik's contributions, along with the CS231n course material, have significantly enhanced my learning journey in machine learning. Check out more of his insights on [his blog](https://kratzert.github.io/).
- Special thanks to Jay Alammar for his enlightening work, particularly "The Illustrated Transformer," which has greatly informed this project. His clear visual explanations of complex machine learning concepts have been invaluable. Check out his insights on his blog (https://jalammar.github.io/illustrated-transformer/) and [YouTube channel](https://www.youtube.com/@arp_ai) for more transformative content.
- I would like to express my gratitude to Josh Starmer for their exceptional series of videos on deep learning, especially their insights on transformers and cross-entropy loss, which have significantly influenced this project. Their expertise and clear explanations have been invaluable. For anyone interested in deepening their understanding of deep learning or statistics, I highly recommend exploring their content at https://www.youtube.com/@statquest.
- The concepts presented here are based on the concepts outlined by the seminal paper "Attention Is All You Need" by Ashish Vaswani et al. This work has been foundational in understanding the Transformer model's architecture and its applications in natural language processing. For a comprehensive dive into these groundbreaking ideas, the original paper is accessible at [https://arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762). I am grateful for the authors’ contributions to the field.
- This project benefited from the use of OpenAI's ChatGPT, which provided assistance with gaining an understanding of the transformer's underlying architecture. The AI's input was invaluable for refining ideas and enhancing the quality of the work presented.

