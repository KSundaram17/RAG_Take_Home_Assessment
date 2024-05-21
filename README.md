# RAG_Take_Home_Assessment
## Project Overview: 
Task: Implement a Simple To-Do List Web Application with AI Integration and Data
Engineering Components
Problem Statement
Develop a RAG-based AI chatbot designed to provide technical support for customers
of a tech company specializing in consumer electronics. The chatbot should help users
troubleshoot common issues, provide step-by-step guides, and offer information on
warranty and repair services.
Details:
Knowledge Base: The chatbot should leverage a database of product manuals, FAQ
documents, user forums, and help articles to fetch relevant information to assist users.
User Queries: The chatbot must handle a wide range of user queries, from simple
questions like "How do I reset my device?" to more complex troubleshooting requests.
Response Generation: Utilizing RAG, the chatbot should retrieve relevant documents
and generate coherent and contextually appropriate answers that guide the users
through their issues or direct them to the appropriate resources.


Required Libraries: 
import torch
from transformers import AutoModel, AutoTokenizer, GPT2LMHeadModel, GPT2Tokenizer
from sklearn.metrics.pairwise import cosine_similarity
import psycopg2: To read and write from and to Redshift

For Best Practices:
We can store the credentials, host name and port that will be used for Redshift in AWS Secret Manager. Due to time crunch, I haven't done that. Step to store the credentials in AWS Secret Manager are as follows:
1. Log in to the AWS Management Console and navigate to the AWS Secrets Manager service.
2. Click on Store a new secret.
3. Select Other type of secrets.
4. In the key/value pairs, enter your database credentials:
username: database username
password: database password
5. Add host, port, dbname as required.
6. Click Next.
7. Give the secret a name and a description; for example:
Name: RedshiftDatabaseCredentials
Description: Credentials for Redshift database.
8. Choose the Next button, configure rotation if needed, and then Next again.
9. Review the details and click Store to store your credentials.
10. Setting Access Permissions
Make sure that the IAM role or user that your application uses has permission to access the Secrets Manager secret. Attach policies that allow actions like secretsmanager:GetSecretValue.
