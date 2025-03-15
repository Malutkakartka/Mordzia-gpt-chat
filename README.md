# Mordzia-gpt-chat
Kopia mordzi agenta gpt chat
# jeepy-chat
Klon agenta gpt4 mordzia 
import openai

# Wstaw tutaj swój klucz API z OpenAI
openai.api_key = "TWÓJ_KLUCZ_API"

def zapytaj_do_chatgpt(pytanie):
    response = openai.Completion.create(
      engine="text-davinci-003",  # Możesz użyć "gpt-4" jeśli masz dostęp
      prompt=pytanie,
      max_tokens=150
    )
    return response.choices[0].text.strip()

print("Cześć! Jestem Twoim agentem ChatGPT.")
while True:
    pytanie = input("Zadaj pytanie: ")
    if pytanie.lower() == "wyjście":
        print("Dziękuję za rozmowę! Do zobaczenia!")
        break
    odpowiedź = zapytaj_do_chatgpt(pytanie)
    print("Agent mówi:", odpowiedź)
