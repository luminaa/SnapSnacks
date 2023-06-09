# Food Recognition Chatbot

SnapSnack is a food recognition chatbot that uses Twilio to receive image messages and OpenAI to recognize the food item. The chatbot then retrieves the nutritional information for the food item using the USDA API and responds with a summary of the information.

## Prerequisites

To run this project, you will need the following:

* Twilio Account and Phone Number
* OpenAI Account
* USDA API Key
* Google Cloud Account

## Installation

### Clone the repository
To get started, clone the repository to your local machine:

```bash
git clone https://github.com/your-username/food-recognition-chatbot.git
cd food-recognition-chatbot
```

### Set up environment variables
Create a .env file in the project directory and add your Twilio and OpenAI credentials and your USDA API key as environment variables. For example:


```bash
python -m venv venv
source venv/bin/activate  # for Mac/Linux
.\venv\Scripts\activate  # for Windows
```

### Download the Google Cloud Vision API JSON file
Download the Google Cloud Vision API JSON file as cloud.json and place it in the project directory.

### Create a virtual environment
Create a virtual environment for the project and activate it:

```bash
Copy code
python -m venv venv
source venv/bin/activate  # for Mac/Linux
.\venv\Scripts\activate  # for Windows
```

### Install dependencies
Install the required Python packages using pip:

```bash
pip install -r requirements.txt
```

### Run the app
Run the app with the following command:

```bash
python app.py
```

This will start a local server on localhost with debug mode enabled and listening on port 8080. You should see output in the terminal indicating that the server is running.

![Setting Up Local Server](/pictures/Setup_App_Image.png) 

### Set up ngrok
In another terminal window, run the following command to set up ngrok:

```yaml
ngrok http 8080
```

This command will create a public URL that tunnels to your locally running app on port 8080.

![Setting Up Ngrok](/pictures/ngrok.png)

### Set up Twilio webhook
In the Twilio console, add the forwarding URL generated by ngrok as a webhook when "A Message Comes In". Remember to add `/detect_food` to the back of the webhook link.

![Setting Up Twilio](/pictures/Twilio_Webhook_Setup_Image.png)

### Start using the chatbot
Send a picture of a food item to the Twilio number and the chatbot will respond with the nutritional information for the food item.

## Usage

To use the chatbot, send an image message of a food item to your Twilio number. The chatbot will respond with a summary of the nutritional information for the food item, including the calories, fat content, protein content, and carbohydrate content.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Acknowledgments

This project was built using the following software and libraries:

* Twilio
* OpenAI API
* USDA API
* Google Cloud Vision API