# NBA Salary Project
For this repository, there is a single Python file for a Lambda function.

This function represents an ETL job that I ran in AWS to work with NBA player data. 
1. I created a S3 bucket as a Data Lake repository for my NBA csv data.
2. I created a Lambda function with the appropriate IAM role to be able to execute S3 actions and update CloudWatchLogs (LambdaExecute Policy)
3. Within this Lambda function, I set a trigger on the S3 bucket that I created earlier. This trigger is modified to activate upon a PUT action (when a new object is uploaded into a bucket)
4. I used the code in my Git repository to fire when the NBA csv file is uploaded into the S3 bucket.
5. The code allows for NBA player salaries to be organized into arrays and summed so that we have an understanding of what the total salaries look like city by city. (This is just for the Atlantic Division in the NBA, so New York, Brooklyn, Boston, Toronto, and Philly)
6. I also added an output file to be added to the S3 bucket to signal that the job was successfully ran (This can also be checked in the CloudWatch Logs)
