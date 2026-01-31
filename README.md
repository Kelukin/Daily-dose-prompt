# Daily Dose Prompt

A collection of reusable prompt templates for everyday productivity tasks, designed to work seamlessly with AI assistants like Edge Copilot.

## 📖 Overview

This repository contains curated prompt templates that help automate common workflows by leveraging AI capabilities. Each prompt is crafted to extract structured data from various sources and transform it into actionable formats.

## 📁 Repository Structure

```
Daily-dose-prompt/
├── Outlook/
│   └── create_event.md    # Create calendar events from web pages
└── README.md
```

## 🚀 Available Prompts

### Outlook

| Prompt | Description |
|--------|-------------|
| [create_event.md](Outlook/create_event.md) | Generate MS Graph API payloads to create Outlook calendar events from flight, hotel, concert, or other booking pages |

#### Create Event Features
- Extracts event details from web pages (flights, hotels, concerts, etc.)
- Generates MS Graph API compatible JSON payloads
- Handles timezone conversion based on location
- Includes coordinates for Apple Maps compatibility
- Supports attendee management and reminders

## 💡 Usage

1. **Browse to a booking page** (flight confirmation, hotel reservation, concert ticket, etc.)
2. **Open your AI assistant** (e.g., Edge Copilot sidebar)
3. **Copy the relevant prompt** from this repository
4. **Customize placeholders** like email addresses and reminder times
5. **Run the prompt** to generate a structured payload
6. **Use the output** with MS Graph API to create calendar events

### Example Use Case

When viewing a flight confirmation page:
1. Open Edge Copilot
2. Use the `create_event.md` prompt
3. Get a JSON payload ready for MS Graph API
4. Create an Outlook calendar event with all flight details, location coordinates, and reminders

## 🛠️ Customization

Each prompt contains customizable parameters marked with `{placeholder}` syntax:

- `{somebody's email address}` - Replace with actual attendee email
- `{time_period}` - Set your preferred reminder time (e.g., "2 hours", "30 minutes")

## 📋 Requirements

- A web browser with AI assistant capabilities (e.g., Microsoft Edge with Copilot)
- Microsoft 365 account (for Outlook calendar integration)
- MS Graph API access (for programmatic event creation)

## 🤝 Contributing

Feel free to contribute new prompt templates! Each prompt should include:
- A clear scenario description
- Step-by-step instructions
- An example output format

## 📄 License

This project is open source and available for personal and commercial use.
