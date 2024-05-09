# Presenting Mangalingua - the AI Manga Translator and Japanese Learning App!
### Contributors: Apratim Banerjee, Michelle Wu, Chia-Jung Kuo, Yuhan Chen
Note: This project is part of the CS 160/260A course final project, [UI/UX Design and Development](https://www2.eecs.berkeley.edu/Courses/CS160) at UC Berkeley. This readme first dives into a brief introduction of the project and an app demo, followed by instructions to run the repo by yourself locally!

## Introduction
Many language-learners seek to broaden their abilities through consumption of media they already enjoy, such as movies, TV shows, and books. One such popular medium for Japanese language-learners is comics, or “manga”. However, there is a lack of a reliable tool to give valuable feedback on their learning. They also aren’t sensitive to the Japanese dialect and their references. Current learning apps generally cater to a broad range of language learners, offering structured lessons and exercise, whereas translation apps focus on general translation and fail to cover fictional aspects, cultural references, and nuances. 

We created an app that allows users to upload manga pages easily that get translated to English, with the translated text overlayed on top of the original text. It also uses AI to save specific vocabulary, nuances, and phrases relevant to the comic book. Users can save these into their word bank for easy reference and learning. We stuck to a minimalistic design for the web app, manga themed. We ensured all standard UI/UX practices were maintained, and Heuristic Evaluations not violated. 

For capturing the Japanese text from images, we used the Optical character recognition (OCR) model and Open Computer Vision (Open CV) libaries. We located and saved the conversation bubble location first. Then the Japanese text was extracted line by line, vertically and converted to English using GPT. Once the entire text within the bubble was translated, we overlayed it with the English text. This all happens in seconds and users can enjoy translated text in real-time. GPT also captured the verbs and nuances from the image as word cards that the user could save to their own word bank. 

<img src="https://github.com/misha-wu/cs160-final-project/blob/main/media/Mangalingua.png" width="623" height="500">

## How to run the server

1. Clone the repo on your local system using VS Code or any other platform
```bash
git clone https://github.com/misha-wu/cs160-final-project
```
2. First you will need to [install Flask](https://flask.palletsprojects.com/en/3.0.x/installation).
- First you will need to go into the directory flask_py.
  ```bash
  cd public/flask_py
  ```
- Then we need to activate the environment.
  For MacOS/Linux:
  ```bash
  $ . .venv/bin/activate
  ```
  For Windows:
  ```bash
  .venv\Scripts\activate
  ```
  Your shell prompt will change to show the name of the activated environment.

- Within the activated environment, use the following command to install Flask:
  ```bash
  $ pip install Flask
  ```
3. Before running flask, make sure `public\flask_py\.venv\Scripts` has pip and python installed. 
4. In the public folder, install the the requirements.txt file which contains the dependent libraries and frameworks:
```bash
python -m pip install -r requirements.txt
```
5. Do the same within the comic_text_detector folder
```bash
cd public\flask_py\comic_text_detector
python -m pip install -r requirements.txt
```
6. Once everyhting is installed, run Flask using the below command (ensure .venv is active):
```bash
Flask run
```

## Common Errors

1. If you are getting an error for modules that are not comic_text_detector or other locally forked packages
re-add python path in `public/flask_py/.venv/lib/python3.9/site-packages`
reinstall all requirements.txt with
```bash
python -m pip install -r requirements.txt instead of pip install -r requirements.txt
```

2. If you are getting an error for "could not clone remote repository" for submodule:
```bash
cat ~/.ssh/id_rsa.pub.
```
If something shows up, copy the entire thing. else, run ssh-keygen first. (leave filename and password blank by pressing enter)
- Save this as a new key @ https://github.com/settings/keys
- Try pulling again

3. If getting error for modules that are comic_text_detector
- Make sure requirements.txt is downloaded for comic_text_detector (separate file!) while in the venv
- Make sure venv is activated and in the right folder
- Make sure comic_text_detector is cloned locally (use git submodule update command)
- Make sure requirements.txt is installed

## App Demonstration

View the App Demo in this link: [Mangalingua App](https://www.youtube.com/watch?v=4srbkxu9zmI)

## Additional information

### Customer and Market Research
We interviewed a varied set of subjects within a specific group of users. Interviewees varied in age (low to mid 20’s), gender, language fluency, occupancy, and hobbies. 
All target users were interested in learning languages, preferably through reading media, and had a cumbersome existing method of learning.

After doing market research, we realized that Language learners, both familiar with the language and beginners, currently rely on various online tools like Google Translate, Naver, and Easy German to translate media content such as books, switching between source text and translation apps to comprehend meanings. Desired tasks include smoother translations considering character names and nuances, a dictionary function for saving phrases and their translations, understanding grammatical structures, and comparing source text to translations for review. Users typically learn these tasks intuitively, iterating through different segments for translation and adjusting for inaccuracies. Tasks are predominantly performed at home, 
where users have the necessary privacy and time for learning. Users consume processed data to check understanding and utilize applications to support comprehension through translation and vocabulary analysis. They access tools like phones and computers to select text from images for translation and may use auxiliary apps to store personal vocabulary. Communication between users is unnecessary as the app is designed for solo use. Task frequency varies from every few days to once a day, serving as a supplement to other learning methods. Challenges arise when translations are incorrect, hindering comprehension and potentially leading to misunderstandings of context, interfering with language learning goals.

### Competitors 
<li> Drops: This app demonstrates the application of Visual Mnemonic and interaction-based vocabulary learning. However, it’s still hard to bridge the real-world usage since the given teaching contents including vocabulary and illustrations are far from the user’s real life, which might increase the memory burden. 
 </li>
<li> Google Translate: While Google Translate is an accessible option, the quality of its results make it difficult for language learners to accurately translate entertainment content, which is often long-winded and context heavy. Our app will also support user-specific content – such as “saved” vocabulary and phrases – to engage learning better. </li>
<li> Jiandanci: The app successfully combines learning the vocabulary with language context with the help of media, enabling people to understand the way to use certain words. Unlike our app, Jiandanci is more focused on memorization and exams – both of which are very formal situations requiring a distinct set of vocabulary. This means that Jiandanci is not as applicable to our form of media – written and/or illustrated.
 </li>
<li> Pimsleur: A versatile and portable learning platform that combines audio-centric learning with comprehensive reading lessons, voice recognition, and gamified elements. It stands out in emphasis on practical conversational skills making it suitable for a wide range of learners. However, potential improvements in visual interaction could elevate the user experience, particularly incorporating media such as books, movies, and tv-shows as a learning tool for users. </li>
<li> Naver: This is a leisure app which can be used for advanced Korean learners with the means of media including news, songs, and video. It also helps learners to understand unfamiliar expressions with their built-in dictionary app. However, it takes some time to switch from the media to the dictionary. Besides, the built-in dictionary has a limited vocabulary and cannot always accurately translate slangs or new expressions. 
</li>
