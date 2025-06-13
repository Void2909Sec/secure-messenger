import os
import webbrowser
import datetime

def greet():
    hour = datetime.datetime.now().hour
    if hour < 12:
        print("Доброе утро!")
    elif 12 <= hour < 18:
        print("Добрый день!")
    else:
        print("Добрый вечер!")
    print("Я ассистент. Что нужно сделать?")

def show_time():
    now = datetime.datetime.now().strftime("%H:%M:%S")
    print(f"⏰ Сейчас: {now}")

def open_browser():
    print("🌐 Открываю браузер...")
    webbrowser.open("https://www.google.com")

def play_music():
    try:
        file_path = "C:\\Users\\Public\\Music\\sample.mp3"  # укажи свой путь
        if os.path.exists(file_path):
            print(f"🎵 Воспроизвожу: {file_path}")
            os.startfile(file_path)
        else:
            print(f"❌ Файл не найден: {file_path}")
    except Exception as e:
        print(f"[Ошибка] Не удалось воспроизвести музыку: {e}")

def play_video():
    try:
        file_path = "C:\\Users\\Public\\Videos\\sample.mp4"  # укажи свой путь
        if os.path.exists(file_path):
            print(f"🎬 Воспроизвожу: {file_path}")
            os.startfile(file_path)
        else:
            print(f"❌ Файл не найден: {file_path}")
    except Exception as e:
        print(f"[Ошибка] Не удалось воспроизвести видео: {e}")

def main():
    greet()
    while True:
        cmd = input(">> ").lower().strip()

        if cmd == "выход":
            print("👋 До свидания!")
            break
        elif cmd == "время":
            show_time()
        elif cmd == "открой браузер":
            open_browser()
        elif cmd == "запусти музыку":
            play_music()
        elif cmd == "открой видео":
            play_video()
        elif cmd == "помощь":
            print("📋 Команды:\n- время\n- открой браузер\n- запусти музыку\n- открой видео\n- выход")
        else:
            print("❓ Неизвестная команда. Напиши 'помощь'.")

if __name__ == "__main__":
    main()
