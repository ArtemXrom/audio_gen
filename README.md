# Kokoro TTS Audio Generator

## Установка


pip install kokoro soundfile ipython

from kokoro import KPipeline
from IPython.display import Audio, display
import soundfile as sf

# Инициализация pipeline для русского языка
pipeline = KPipeline(lang_code='ru')

# Текст для озвучивания
text = "Привет, как дела?"

# Генерация аудио
generator = pipeline(text)

# Воспроизведение и сохранение
for audio, phonemes in generator:
    display(Audio(audio, rate=24000))
    sf.write('output.wav', audio, 24000)
    break

Требования
Python 3.7+

kokoro

soundfile

IPython (опционально, для Jupyter)

Устранение проблем
Если возникает ошибка с кодом языка:

python
# Неправильно
pipeline = KPipeline(lang_code='a')  # ❌

# Правильно
pipeline = KPipeline(lang_code='ru')  # ✅
Лицензия
MIT

text

Просто скопируйте весь код из блоков выше и вставьте в свои файлы.
