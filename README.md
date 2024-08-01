////////////////// Rule-Based Chatbot with nltk///////////////////////////
pip install nltk

import nltk
from nltk.chat.util import Chat, reflections

# Define pairs of patterns and responses
pairs = [
    (r'hi|hello|hey', ['Hello!', 'Hi there!', 'Hey!']),
    (r'how are you?', ['I am doing great, thank you!', 'I am good. How about you?']),
    (r'what is your name?', ['I am a chatbot created by you.']),
    (r'(.*) your name?', ['My name is Chatbot.']),
    (r'quit', ['Bye! Have a nice day!']),
]

# Create a chatbot instance
chatbot = Chat(pairs, reflections)

def chat():
    print("Hi! I'm a chatbot. Type 'quit' to end the chat.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'quit':
            break
        response = chatbot.respond(user_input)
        print(f"Chatbot: {response}")

if __name__ == "__main__":
    chat()
///////////////////////////////////////Machine Learning Chatbot with ChatterBot///////////////////////////////////
pip install chatterbot chatterbot_corpus

from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer

# Create a new chatbot instance
chatbot = ChatBot('MyBot')

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train the chatbot on English language corpus data
trainer.train('chatterbot.corpus.english')

def chat():
    print("Hi! I'm a chatbot. Type 'exit' to end the chat.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'exit':
            break
        response = chatbot.get_response(user_input)
        print(f"Chatbot: {response}")

if __name__ == "__main__":
    chat()

