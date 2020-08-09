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
****
# Paper 2
****

# **Better code, Better sharing on the need of analyzing Jupyter Notebook **

#### Important Links:
*Link to Paper:* 🔗  https://www.researchgate.net/publication/333745954_Better_Code_Better_SharingOn_the_Need_of_Analyzing_Jupyter_Notebooks
#

##### **AUTHORS**
*Jiaweiwang, Li Li,Andras Zeller*

##### **INTRODUCTION**
Jupyter , An indirect acronym of 3 lamguages -Julia ,Python and R-Jupyter notebook is a client based intractive web application that allows users to create and share codes ,equations,visualisatioin as well as text. Students can also get benifits  from the line code to better understand  the concepts introduced in notebook.The notebook consider as a multilanguage intractive comnputing enviroment, which support 40+ programming language to its users. With jupyter notebook user can bring in data,code and prose in together to create an intractive computational story. Wether to analyse a collection of written text ,or develop engineering concept , Jupyter notebook can combine codes and explanations with the  intractivity of the application. This makes it handy tool for data scientist for streamlining end to end data science workflows. Developers may encounter the problem that notebooks do not behave as expected. Moreover jupyter notebook might also encourage poor coding practice. By and large the software engineering community has not yet proposed promising approaches to automatically analyze jupyter notebook contain.
(1) Coad with poorly respect to the python style conversion.
(2) Code with unused variables which are defined but never referenced.
(3) Accessing, deprecated function.

In this paper they argue to that community need to propose promising approaches to
(1) enforce good coding styles.
(2) Improve the quality and reliability of the code.
(3) applied best practices for software quality and 
(4) Ensure a good balance between text and code in jupyter notebooks


##### **METHODOLOGY**

Jupyter notebook was created to make it easier to show one's programming work ,and to let other join in. Jupyter notebook allows you to combine code , comments ,multimedia , and visualization in an intractive document - called a notebook , naturally - that can be shared , reused , and reworked. The quality of notebooks is extremely important. Their initial attempt towards checking the quality of codes for this purpose this paper includes some question and to answer these research questions , they resort to Github to harvest a dataset to support their empirical investigation. In this preliminary study , restriction is to analyze python based notebooks only. After removing dead links and duplicated links , we automatically collected 1,982 notable python _based notebooks covering various topics such as -  mathematics , signal processing ,natural language processing etc as research subject data. To facilitate the empirical investigation develop a set of python script to preprocess the datasets. The programs a jupyter notebook file as input and chain of code cells as output. Every code cell is associated with its explanatory text , execution output, and possible external python code. The external cide is prresented as independent python script (*.PY) initially the question was to check if the python code written in jupyter notebooks respect the python coding style. Because most of the jupyter notebook are provided for education, the code should be well aligned with recommended coding conventions so that the learners will not be misledton write python code with poor coding practices .Another question if unused variable are presented by the providers of jupyter notebooks. Unused variable are such variables that are defined in a code cell but are never used in that cell and its subsequent cells.If a variable is stored but not located ,we consider it as an unused variable and will flag it as such . By this following approach, experimentally find that 803 notebooks contain code with unused variables . As the last question if notable jupyter notebooks contain code accessing into deprecated functions of givin libraries .Again , because of the educational purpose , deprecated function should be also avoided by notebook contributors. Most people have their first exposure to jupyter notebook by way of a data visualization a shared notebook that includes a rendering of some dataset as graphic. Jupyter notebook lets you author visualization ,but also share them and allow intractive changes to the shared code and dataset .Jupyter notebook code isn't static ;it can be edited and re-run incrementally in real time.
Simply we can say that the purpose of jupyter notebook is 
➡️ Data Cleaning
➡️ Statistical Modeling
➡️ Training ML Model
➡️ Data Visualisation .

###### **CONCLUSION**
Jupyter notebook originally developed for data science applications written in python , R ,and Julia jupyter notebook is useful in all kinds of ways for all kinds of projects. Jupyter notebooks are powerfull, versatile , shareable and provide the ability to perform data visualisation in the same environment  .Jupyter notebook allow data scientist to create and share their document from codes to full blown reports. according to experimental result prove that juypyter notebook are indeed in undated with poor and low coding practice. Motivated by these empirical results they presented to show their goals on the need of analyzing jupyter notebook. Appealing for software engineering community to pay more  attention and focus to the quality and reliability of jupyter notebook.

****
