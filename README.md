# RAG_Take_Home_Assessment
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
