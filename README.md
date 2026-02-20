# Bot Collect Khakas Event

This repository contains the source code for a Telegram bot designed to collect data for the "Teach AI Khakas Language" action (*"Обучаем нейросеть хакасскому языку!"*). 
The bot facilitates crowdsourcing for Khakas-Russian translation, text digitization from photos, and sentence alignment.

## Features

The bot offers three main types of tasks for users:
1.  **Translation**: Translating sentences from Khakas to Russian.
2.  **Text from Photo**: Typing text displayed in images (e.g., from textbooks).
3.  **Find Translation**: Aligning Khakas sentences with their Russian translations within a text.

## Requirements

-   Python 3.9+ (implied, as `aiogram` 3.x requires modern Python)
-   `aiogram==3.1.1`
-   `pandas==2.1.2`

See `requirements.txt` for the full list of dependencies.

## Installation

1.  Clone the repository:
    ```bash
    git clone <repository_url>
    cd bot-collect-khakas-event
    ```

2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Configuration

### Environment Variables

You need to set the `BOT_TOKEN` environment variable with your Telegram Bot Token.

```bash
export BOT_TOKEN="your_telegram_bot_token"
```

### Data Paths

**Important:** The current codebase uses hardcoded paths in `utils.py` pointing to a specific directory structure on the developer's machine (`/home/vasiliy/projects/obuchaem_neuroset_khakas`). 

You **must** update these paths in `utils.py` to match your local environment or modify the code to use environment variables/config files.

Relevant variables in `utils.py`:
-   `obuchaem_neuroset_khakas_data_dir`: Base directory for input data.
-   `user_info_dir`: Directory where user registration info is saved.
-   `user_answers_dir`: Directory where user task results are saved.

Input data requirements (based on code):
-   Khakas sentences: `{data_dir}/khakas_texts/khakaschiry_sents_min_word_num_5.csv`
-   Alignment texts: `{data_dir}/align_texts/stm19/khakas_russian_text_pairs.csv`
-   Photos: `{data_dir}/pogovorim_po_khakasski/photo_path_statistics.csv`

## Usage

Run the bot using Python:

```bash
python bot.py
```

## Project Structure

-   `bot.py`: Main entry point. Handles bot startup, command routing, and FSM (Finite State Machine) logic for user interaction.
-   `utils.py`: Helper functions for data loading, keyboard generation, and saving results.
-   `requirements.txt`: Python package dependencies.

## License

[MIT License](LICENSE)
