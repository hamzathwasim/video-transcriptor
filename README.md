# Video Transcript Highlights Extractor

This Python script processes video transcripts to extract and match key highlights with timestamps. It leverages the OpenAI API for automated highlight extraction and performs detailed matching with provided JSON transcript data.

## Features

- Load transcription data from JSON and text files.
- Extract key highlights from a punctuated transcript using the OpenAI API.
- Match extracted highlights to timestamped sentences from a JSON transcript.
- Output matched highlights with timestamps and confidence scores.

## Requirements

- Python 3.x
- `openai` Python package
- `json` and `difflib` standard libraries

## Setup

1. **Install the OpenAI Python package**:

    ```bash
    pip install openai
    ```

2. **API Key**: Obtain your OpenAI API key from [OpenAI](https://platform.openai.com/signup) and set it in the script.

## Usage

1. **Prepare your files**:
    - `transcript.json`: A JSON file containing the transcript with timestamps.
    - `transcript.txt`: A punctuated version of the transcript.

2. **Configure the script**:
    - Set the file paths for your JSON and text transcription files.
    - Insert your OpenAI API key in the script.

3. **Run the script**:

    ```bash
    python script_name.py
    ```

4. **Output**:
    - The script will print the matched highlights with their timestamps and confidence scores in JSON format.

## Example

Here's how you can use the `generate_video_highlights` function:

```python
json_file = 'transcript.json'  # Path to the JSON transcription file
text_file = 'transcript.txt'   # Path to the punctuated text transcription file
openai_api_key = 'your_openai_api_key_here'  # Your OpenAI API key

matched_highlights = generate_video_highlights(json_file, text_file, openai_api_key=openai_api_key)

if matched_highlights:
    print(json.dumps(matched_highlights, indent=2))
else:
    print("No highlights available.")
