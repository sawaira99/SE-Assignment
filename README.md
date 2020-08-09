****
# Paper 1
****

# **AIMMX: Artificial intelligence model metadata extractor**

#### Important Links:
*Link to Paper:* 🔗  http://www.jsntsay.com/publications/tsay-msr2020.pdf
*Link to Media:* 🔗  https://youtu.be/uMpbXh19rTE
#

##### **AUTHORS**
*Jason Tasy ,Allan Braz ,Martin Hirzel ,Avraham Shinnar, Todd Mummert*

##### **CONFERENCE NAME**
Conference on Mining Software Repositories (MSR) 2020

##### **INTRODUCTION**
AIMMX is actualy an open resource library there are numerous frameworks.AIMMX in perticular is very exciting field that's developing in many resources and datasets but is high  variable and hard to understand or work with AI Model at scale .This paper presents a library called(AIMMX) for extraction of AI model specific metadata from software repositories.The extractor take   metadata which is in software repositories that contain data  from multiple  sources like  documentation ,python code,model definition file etc.Extractor have five moldules (1)Model_name (2)  Associated Dataset (3)References (4) AI Framworks (5)MOdel Domain .Our definitioin includes both traditional machine learning(ML) and deep learning models.
Software repositories like Github commonly used for AI development software repositories contain useful software specific metadata but AI model related metadata is often not directly viewable. Model releted metadata need to be converted into a common formate . AI system also commonly use versioning system for software to store both AI and non AI components.

##### **IMPORTANCE**
AIMMX metadata extraction gives more focus on high level question like the domain or which dataset used or how to use a given model rather than model definition . After extraction the metadata is ready for consumption in both machine readable and human readable states  . The extraction of metadata is helpfull for higher engineering support for AI development reproducibility in AI paper and jupyter notebooks tends to be relatively poor due to a lack of documention over method selection , datasets used or experiments ran. Method reproducibility , proxied by extracted references is higher than data reducibility at 727 of models in our sample with state of  the art  models being perticularly high at 92%.The system is scalable for cataloging 1000 of models it allow the producers to add their own model in a way due to AIMMX less burden is impose enabling automated metadata extraction .The use of AIMMX extracted metadata in a cataloging provide automatic connection between code , datasets and references which is totally simmilar to connection in paper with code website. The connection may also help in development of future tools.

##### **METHODOLOGY**

**Automated model metadata extraction:**
The AIMs is a python library which read the software repositories specially from Github and then extract the information of  AI model into model metadata in the JSON format that is readable for both machine and human .This is an open source library and available for everyone. The use of AIMM is also simp0le first initiated  the Github API key , then the user can simply call that function which he wants through Github URL. There are two main advantage of choosing  to use software repositories and Github  One is that  ,AI development is already use them and second is that , software repositories document more than just code example: there is a culture of rich documention through RADME file that are automatically displayed on Github repositories pages . Github also has a (API) Application Programming Interface . The enfactor support three forms of URL's : full repositories and individual files in repositories . we can directly extract the information from Git API and the information is like repositories name , description , topics , author , open source lisence , primary programming language , data of last code commit number of stargazes for the repositories (Like tweeter or facebook ) etc.

**Model name:**
Metadata extract to   attempt descriptive name for a giving model .Models usually exist as apart of subfolder to extract understandable name module use a Rule based approach from documentation (RADME or docstring) the RADME iterated line by line ,skiping  irrelevant lines such as images or badges or headers (*** or ===) when the first relevant line is formed than it is striped out HTML or Mark-down or links .

**Reference Extraction:**
To reference the paper we choose to implement a module to extract reference because data scientist use paper to discuss and refer to AI modules . This module uses three rule based approach.
(1) Regular expressions to search for common reference format:- find variety of reference. 
(2) Search for ARXIV ID's with correspond lookup to the ARXIV API :- find the specific format.
(3) Identify and import code blocks containing BIbTEX:- find specific format.

The first approach is broadest in terms of what type of references are allowed as any conference. In second appraoch the advantage is that ARXIV is very popular amongest machine learning and disadvantages using ARXIV is that its reference tend to be pre-prints and publishing conference or journal information is usually cased. The advantage of third approach is that BIbTEX is well established and precise format.

##### **Dataset extraction:**
What dataset we use is important to know .Data management in AI system is very difficult and itis a common challenge in AI development. The module uses two rule based approaches.
(1)Key word search for links containing words such as 'dataset' or 'corpus'
(2)Key word search using a list of sub common datasets from papers with code.com

###### **AI framework extraction module:** 
Detect AI-related framwork to search through python files (.py) and code cells of jupyter notebooks (.ipy nb) search for specific AI-related modules that are imported .
##### **Automated domain interface:**
 It is very important to know how potentially used the model or what is model does .At very high level :graphical repositories .Domain refer to the type of activity that the model is associatewd wiith example : Computer vision ,natural long processing (NLP)
Evalution and Preliminary analysis:
The process of evalution is that evalute metadata generated from datasets .Evalution per extraction module.

###### **CONCLUSION**
AIMMx describe that we intend as a step towards furthering and modifying engineering support for AI development .Through AI development they providing standardized metadata for existing and utilize AI models . We envision that generating analyzable metadata for disparate and different  models is both the first and golden step towards managing models at scale and adapting existing mining software repositories techniques to AI models through AI models we adapt many success and many technical chance to support engineering system. AI models is one of the best success in software engineering of world. We should adapt it and get lots of adavantage from it.

****
