# Email-Sending-with-SMTP-
Sending an email using the smtplib module.
import smtplib
from email.mime.text import MIMEText

sender_email = 'your_email@gmail.com'
receiver_email = 'recipient_email@gmail.com'
password = 'your_password'

message = MIMEText('Hello, this is a test email!')
message['Subject'] = 'Test Email'
message['From'] = sender_email
message['To'] = receiver_email

with smtplib.SMTP('smtp.gmail.com', 587) as server:
    server.starttls()
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message.as_string())
