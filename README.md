# textsummarization

from transformers import pipeline

summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

text = """
India, a land of astounding diversity, is woven with countless cultures, languages, and traditions, each contributing to its vibrant and rich tapestry. Throughout the nation, every state flaunts its unique heritage, ranging from Rajasthan's colorful fairs and festivals to Kerala's tranquil backwaters and lush greenery. This kaleidoscope of cultural nuances is mirrored in the myriad expressions of art, cuisine, and daily life, making India a living library of human experiences. Every corner of the country offers a different historical tale, a slice of architectural beauty that ranges from the majestic forts of the north to the ancient temples of the south. The Indian economy, a juggernaut in its own right, reflects a unique blend of traditional industries alongside cutting-edge technology. It's a realm where hand-woven silks are sold next to high-tech software, symbolizing a blend of the old and the new. This dichotomy not only fuels economic growth but also projects India as a significant player on the global stage. With vast reserves of human talent and an enormous market, India has positioned itself as a significant hub for technology, pharmaceuticals, and textile industries, setting the stage for a new era of economic development. Environmental conservation in India is another area seeing innovative transformations. With projects like Project Tiger, which aims to protect and conserve the endangered Bengal tiger and its habitats, coupled with the push towards renewable energy sources, India is making strides in balancing economic advancement with ecological sustainability. Initiatives to clean up rivers, battle air pollution, and the substantial increase in solar energy installations are reflective of a nation that is increasingly conscious of the global call for environmental stewardship. The challenges are many, but the drive to find solutions is palpable across its policies and public initiatives.
"""

summary = summarizer(text, max_length=200, min_length=50, do_sample=False)
print("Summary:", summary[0]['summary_text'])

