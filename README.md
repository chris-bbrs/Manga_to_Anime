## Manga_to_Anime

This is an ongoing project where we try to create a dataset for training a Nueral net to generate the anime frames which correspond to subsequent manga panels.

The following are the steps we went through:
- Create the corresponding folder structure for a specified Anime using the folder_structure.ipynb, the anime used as an example in the code is the fullmetal alchemist.

![image](https://user-images.githubusercontent.com/24413081/227810682-c7d8f876-2cff-42c2-9e60-bb99fb9d15be.png)

- Acquire the Anime episodes.
- Extract P-Frames for each episode.
- Use of the Mangadex API to download each manga chapter.
- For each manga page we used a modified version of this repo https://github.com/njean42/kumiko to extract each panel as an individual image and then crop out the text in the bubbles using the model from this paper https://arxiv.org/abs/1902.08137.
- Then we used pretraind models to extract features from the frames and keep only the most significant frames by deleting the ones with similar enouph features.

- The next step is supposed to go through the last step's frames and look for the most similar panel for each frame at the corresponding chapter. After trying out a lot of pretrained models, we had no success on correlating the panels with the most similar frames.

The last one was the most challenging part and obviously there is a need for a model that was trained on these kind of images, which unfortunately doesnt exist and would take a huge amount of time to be created by a small number of people.
