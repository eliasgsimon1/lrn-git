# Chatbot Web Interface

This project is a simple web-based chatbot interface built with HTML, CSS, JavaScript (jQuery), and Bootstrap. It provides a visually appealing chat window where users can interact with a chatbot. User messages and bot responses are displayed in a conversational style.

## Features

- **Chat UI:** Modern, responsive chat window styled with Bootstrap and custom CSS.
- **Message Bubbles:** Distinct styling for user and bot messages.
- **Scroll Animation:** Chat view scrolls automatically to the latest message.
- **AJAX Backend Integration:** User messages are sent to a backend endpoint (`chat_handler.php`), and bot responses are displayed in the chat.
- **Keyboard Support:** Pressing "Enter" in the input field sends the message.
- **Error Handling:** Bot displays an error message if the backend fails to respond.

## Screenshot

![Chatbot UI Example](screenshot.png)

## Getting Started

### Prerequisites

- A web browser (Chrome, Firefox, Edge, etc.).
- A backend handler at `chat_handler.php` to process chat messages and return bot responses in JSON format.

### Installation

1. **Clone or Download the Repository:**
   - Place the provided HTML file in your web server's root directory.

2. **Backend Setup:**
   - Implement a `chat_handler.php` file that accepts POST requests with a JSON payload (`{ "message": "your message" }`) and returns a JSON response (`{ "response": "bot reply" }`).

   Example `chat_handler.php`:
   ```php
   <?php
   header('Content-Type: application/json');
   $data = json_decode(file_get_contents('php://input'), true);
   $userMessage = $data['message'] ?? '';
   // Simple echo bot
   $botResponse = "Bot says: " . htmlspecialchars($userMessage);
   echo json_encode(['response' => $botResponse]);
   ?>
   ```

3. **Open the HTML file in your browser.**

## Usage

- Type your message in the input field and press "Send" or hit "Enter".
- Wait for the bot's response to appear in the chat window.

## File Structure

- `index.html` — Main HTML file containing the chat UI, CSS, and JavaScript.
- `chat_handler.php` — Backend script to process messages (must be created by you).
- `screenshot.png` — Optional screenshot of the chat interface.

## Customization

- **Styling:** Modify the `<style>` section in the HTML to change the look and feel.
- **Bot Logic:** Update `chat_handler.php` to connect to actual AI or rule-based logic instead of echoing the user message.
- **UI:** The chat window can be resized, repositioned, or restyled as needed.

## Dependencies

- [Bootstrap 5](https://getbootstrap.com/)
- [jQuery 3.6.0](https://jquery.com/)

These libraries are loaded via CDN.

## License

This project is open source and free to use for educational and personal projects.

---

**Note:** This is a frontend template. The chat will only function if a compatible backend (`chat_handler.php`) is available and properly configured.
