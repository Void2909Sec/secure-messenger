import os
import random

def play_random_music():
    # Список путей к музыкальным файлам
    music_files = [
        "C:\\Users\\Public\\Music\\bit.mp3",
        "C:\\Users\\Public\\Music\\relax.mp3",
        "C:\\Users\\Public\\Music\\gimn.mp3"
    ]

    # Выбор случайной песни
    song = random.choice(music_files)
    print(f"🎵 Случайная песня: {os.path.basename(song)}")
    
    # Запуск в плеере по умолчанию
    os.startfile(song)

# Пример использования:
command = input(">> ").strip().lower()
if command == "музыка":
    play_random_music()
else:
    print("Неизвестная команда.")
