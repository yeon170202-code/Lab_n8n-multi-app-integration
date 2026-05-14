## Real-World Justification
In a fast-paced Project Management or Customer Support environment, critical updates often arrive via mobile messaging apps like Telegram while the team is "in the field." Relying on manual copy-pasting from a chat app into a central database like Airtable is prone to human error, leads to "inbox chaos," and creates information silos where data is easily lost.

This automation acts as a Digital Intake Assistant. By routing Telegram messages directly into a structured Airtable base, project leads or support coordinators can ensure every request is captured in real-time with an automatic audit trail (timestamps and sender IDs). This improves visibility across the team, ensures data integrity, and allows for immediate follow-up without the administrative overhead of manual data entry.

## Technical Implementation
Integration Pair: Telegram (Source/Trigger) → Airtable (Destination/Action).

Field Mapping: I used a Set Node to normalize the incoming JSON payload from Telegram. I mapped the sender's first_name and username to a "Sender" column, the message text to a "Description" field, and utilized an n8n expression ($now) to populate a "Received At" timestamp in Airtable.

Challenges: The hardest part was correctly navigating the nested JSON structure of the Telegram trigger—specifically ensuring I targeted $json.message.text rather than a top-level key.

Extension Idea: A valuable next step would be adding an AI Sentiment Analysis node (using OpenAI) between the Set and Airtable nodes to automatically categorize messages as "Urgent," "Feedback," or "Question" based on the tone of the text.