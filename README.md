# Resume_Parser

ADVANCED RESUME PARSER CHALLENGE

Here is the README for our Resume Parser project!

With the help of our Resume Parser, you can quickly and easily extract crucial information from resumes. Recruiters, hiring managers, and other professionals can all benefit from this application, which makes it easy to scan resumes for important information including their skills, education and experience.

Our programme attempts to streamline the frequently laborious process of manually examining resumes with its strong processing capabilities. You may save a lot of time and concentrate on what really matters—finding the best applicants for your company—by automating the extraction process.

In this README file, we have documented all the basic information that you need to get an understanding of what we have done, including the setup instructions, installations required, the procedure and the output. 

INSTALLATIONS REQUIRED:
We need to install various python libraries which will help us to extract information from all different kinds of formats like .pdf, .html, .docx, .jpg, etc. The libraries we have installed for that are PyPDF2, python-pptx, pytesseract, python-docx, textract. 

In the next step, we have parsed all the resumes that are stored in a specific directory and divided them into skills, education and experience. To achieve this, we have firstly converted all the text to lowercase and removed the white spaces and then used regular expression (regex) to perform the partition. 

Now, we add the functionality of extracting key words from different sections of the resume and store them in separate text files. We mainly focus on extracting the skills in this section. 

Now, we have downloaded the NLTK (Natural Language ToolKit) which helps us work with human language data. In that, we have downloaded stopwords and punkt. 'stopwords' helps us in removing the most common words like a, and, the, etc. that carry very less significance. 'punkt' helps us in dividing the text into a list of sentences. 

The next step we have carried out is job role extraction. It is done by using the concept of tokenization where the text is broken down into smaller units. Now, on the tokenized list of words, we perform stop word removal which removes the words that hold very less significance and the punctuation removal is performed. The words remaining after this process are identifies as potential job roles. 
Now, the redundant words are removed and lemmatization is performed using NLTK's 'WordNetLemmatizer'. It helps us to standardize words by reducing them to their base/dictionary form.

Now, we have imported the gensim downloaded module and loaded the pre-trained Word2Vec model. 
In the next part, we have loaded a list of sentences, tokenized them, trained a Word2Vec model on the tokenized data, and then saved the trained model to a binary file named 'word2vec.bin'.

The next major step is to find the job titles for which we first have to download an inbuilt python library called find-job-titles. Next, we iterate through each file in the specified directory, extract text from each file, use a job title finder to identify job titles in the extracted text, and store the found job titles in a dictionary where the keys are file names and the values are lists of job titles found in each respective file. 

Next, we process a string variable data, which contains lines of text where each line represents a job code followed by a job title. The code splits the data into lines, then splits each line by whitespace to separate the code from the title. It creates a list of dictionaries, where each dictionary represents a job occupation with keys "number" for the code and "title" for the job title. 

Now, we take the tokens and using the pre-trained Word2Vec model, we calculate the average word vector for the tokens. It is done by calculating the vector of each word in the token and then dividng it by the total number of words in the token to get the average. In the next step, we use this average vector to find the cosine similarity between two job titles; one that is extracted and one that is a part of the predefined job title list. The most similar job title i.e. the one with the most cosine similarity is printed for all the job titles. 

As we had already added the job titles and their respective codes from O-NET, now we map our extracted job titles to the codes from O-NET. The mapping is done if there is a cosine similarity of greater than or equal to 0.5. 

Our Resume revealer has successfully been created!
