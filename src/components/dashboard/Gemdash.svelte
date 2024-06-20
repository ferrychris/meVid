/*
 * Install the Generative AI SDK
 *
 * $ npm install @google/generative-ai
 *
 * See the getting started guide for more information
 * https://ai.google.dev/gemini-api/docs/get-started/node
 */
<script>
import GoogleGenerativeAI from '@google/generative-ai';
import HarmCategory from '@google/generative-ai';
import HarmBlockThreshold from '@google/generative-ai'
const {
  GoogleGenerativeAI,
  HarmCategory,
  HarmBlockThreshold,
} = require("@google/generative-ai");

const apiKey = process.env.AIzaSyCVGKoOosPdTX_jGyhtYDWILY2YiULvnbY;
const genAI = new GoogleGenerativeAI(apiKey);

const model = genAI.getGenerativeModel({
  model: "gemini-1.5-flash",
});

const generationConfig = {
  temperature: 1,
  topP: 0.95,
  topK: 64,
  maxOutputTokens: 8192,
  responseMimeType: "text/plain",
};

async function run() {
  const chatSession = model.startChat({
    generationConfig,
 // safetySettings: Adjust safety settings
 // See https://ai.google.dev/gemini-api/docs/safety-settings
    history: [
      {
        role: "user",
        parts: [
          {text: "can i get a story\n"},
        ],
      },
      {
        role: "model",
        parts: [
          {text: "The old woman, her face a roadmap of wrinkles, sat hunched over a chipped teacup, the steam curling up like wisps of memory. The air in the dusty antique shop was thick with the scent of old books and forgotten dreams. Outside, the rain lashed against the windows, blurring the cityscape into a watercolour mess. \n\nShe was a fixture in the shop, always there, a silent observer of the day’s comings and goings. Her name was Elara, and the whispers among the other patrons claimed she was a keeper of secrets. Nobody knew her story, though, not really. \n\nOne day, a young man, his eyes filled with a restless fire, wandered in. He was a writer, they said, searching for inspiration. He browsed the shelves, his fingers tracing the spines of books like he was reading a braille map of forgotten worlds. \n\nElara watched him, a knowing smile playing on her lips. He stopped, his gaze drawn to a dusty, leather-bound volume tucked away on a high shelf. It was an old journal, its pages brittle with age, the ink faded and spidery. \n\nThe man reached for it, his fingers brushing against Elara's as she handed him the book. “Careful, dear,” she said, her voice a gentle rasp. “It holds a story, a story that’s waiting to be told.”\n\nHe opened the journal, the faded ink whispering secrets of a lost love, a journey across continents, a life lived in the shadow of war. As he read, the young man’s face paled, his eyes widening with each turn of the page. He saw his own story mirrored in the words, the dreams and fears, the longing for a place he could truly call home. \n\nHe read through the night, the storm raging outside mirroring the tempest within him. When he finished, he looked at Elara, his eyes filled with gratitude and a new understanding. \n\n“Thank you,” he said, his voice choked with emotion. “This story… it’s given me my own.”\n\nElara smiled, a single tear tracing its way down her cheek. “It’s not your story,” she said, her voice soft as the falling rain. “It’s a part of you, waiting to be discovered.”\n\nThe young man left the shop, the rain washing away the shadows of his past. He knew now what he had to do. He had a story to tell, a story that had found its way to him through the mists of time, a story that would echo through the generations to come. And Elara, the old woman with secrets in her eyes, smiled as she watched him go. The rain had stopped, a rainbow arcing across the sky, a promise of new beginnings. \n"},
        ],
      },
      {
        role: "user",
        parts: [
          {text: "whats the error in this story\n"},
        ],
      },
      {
        role: "model",
        parts: [
          {text: "The story is well-written and engaging! There isn't a glaring error, but there is a slight inconsistency in the characterization of Elara. \n\nThe story initially describes Elara as a silent observer, a keeper of secrets, with nobody knowing her story.  This implies she is mysterious and possibly guarded. \n\nHowever, later in the story, she tells the young man that the story in the journal \"is not your story, it's a part of you, waiting to be discovered.\" This line, while insightful, feels slightly out of character for the initial description. \n\nIt would be more consistent if Elara remained more mysterious, perhaps offering the journal without explanation, or leaving the young man to discover the connection to his own story on his own. \n\nThis is a minor issue, but it could be addressed by either:\n\n* **Adjusting Elara's initial characterization:**  Instead of \"silent observer\" and \"keeper of secrets,\" portray her as someone who is wise and understands the power of stories, but keeps her own story private. \n* **Subtly adding to Elara's backstory:**  A small hint about her past, perhaps a fleeting memory or a shared connection to the story in the journal, could justify her more insightful words. \n\nOverall, the story is strong and emotionally resonant. A minor adjustment to Elara's character could strengthen the narrative consistency and make her role even more intriguing. \n"},
        ],
      },
    ],
  });

  const result = await chatSession.sendMessage("INSERT_INPUT_HERE");
  console.log(result.response.text());
}

run();
</script>
