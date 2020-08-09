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
****
# Paper 3
****

# **Mining Software Repositories While respecting Privacy**

#### Important Links:
*Link to Paper:* 🔗  https://jgbarah.github.io/presentations/research-privacy/
*Link to Media:* 🔗  https://www.youtube.com/watch?v=O6er2YpE8XQ
#
##### **AUTHORS**
*Jesus M.Gonzalez-Barahona*

##### **CONFERENCE NAME**
Mining Software Repositories Conference Eduactional Track  | June 29 th 2020

##### **INTRODUCTION**
In this paper the author write about the privacy and protection of data. First outline the motivation for this document, including the conceptual framework for traditioinoal humman subject research and ICT research stakeholder. Thier are two points through which we can analyze the privacy of data.
(1) Legal requirements.
(2)  Ethical requirements.
IN this paper we discuss 5 ethical principle , the 3 from the Belmont report which are 1- respect for person 2- beneficiences 3- justice and an additional principle respect for law and public intrest.The ethical prespective is that bussiness have an obligation to conduct themselves in a way that treats each stakeholder group fairly .While recognizing the claims shareholders have to profit in exchange for putting their capital at risk ,the stakeholder perspective that holds ethics as the prominent decision rule.
In software engineering field the ethical problem involve : the end product , the processing of developing that product , and the humman intractions in the development of the product and core concept like: informed consent - Scientific value, Beneficence, Confidentiality. This paper also includes some applicable law for the protection of data like General Data Protection Regulation (GDPR) and recommendations by national data protection agencies and other which are applicable in Europe Union and also in other jurisdictions. This paper includes the standard methods to operationalize these principle in the domain of research involving  information and communication tehnology: identification of stakeholder and informed consent ; balancining risk and benefits, faireness and equality ; transparacy,accountability, respectively.

##### **METHODOLOGY**
This conference is totally about the privacy and security of data that what it is and why it is important. So we can easily analyze this by legal and ethical requirement. Ethics are based on 3 fundamental principle.
**1) Respect for person :-** People should be treated as autonomous. Researcher must respect that individuals should make their own informed decisions about whether to participate in search and individual must be provided with complete information about study.
**2) Beneficence:-** Persons are treated in an ethical manner not only by respecting their decisioin and protecting them from harm , but also making effort to secure their well being. Such treatment falls under the principle of beneficence . Two general rules have been formulated (1) do not harm (2) maximize possible benefits and minimize possible harms.
**3) Justice:-** It is the concept of fairness . Researchers designing traials should consider what is fair in term of requirements of participant and choice of location to conduct a trail. This issue is related to whon benefits from research and who bears the risk of research . Another way of conceiving the principle of justice is that equal ought to be treated equally. There is also some ethical issue in Software Engineering research like informed consent, scientific value, beneficence and confidentiality.

Software repositories always contain personal information that can be mapped to individual. Therefore , that research using the dataset of an MSR can effect human subjects , requiring careful consideratioin  of ethics implication. It is sometime misunderstanding that analysis of publicaly available data in free from the requirements of ethics consideration.
Legal requirements:- Data protection laws can also be enforced through data protection by design . Key GDPR principle , rules and requirements for the collection and processing of personal data . These types of key require technical and organizatioin controls and policies to secure personal data and provisions of security that are for ensure the confidentiality , integrity ,and availability of sysytem , networks , services and data.Data privacy and security also concern with research aspect in PROCESSING and PUBLICATION  of personal data.
Processing:- The first principle require that personal data are processed in a lawfull , fair and  transparent manner in relation to data subject . Transparncy implies that any information and communication concerning the processing of personal data must be accessible an easy to understand . Also cleared and plain language needs to be used .MORE specifically this principle ensure datasubject receive information onthe identity of controllers and purposes ofthe processing of personalb data.
Publication :- Sharing personal data should be through managed processes with access and usage controls to protect from re-identification. There are too many risk releated to GDPR sometimes mention is made of vulenerable natural persons in  the content of GDPR examples: Babies and Young children , Pregnant  women , Elderly , People with mental disordeers , asylum seekers, People with disabilities , Sick and Patients. These are also often person who are legally incompetent , Person who can not give their cosent, or person who may suffer very adverse consequence ,if  their personal data were to become publically available. The processing of personal data of vulenrable persons can give rise to risk analysis .Collecting data from non EU data sources and sharing data with non EU researcher are also risky in privacy terms of data. Data can be protected by pseudonymization , data minimization ,cryptography , procedure for exercising fundamental rights (access , consent).we have a lawful basis for the data processing due to this we can process our personal data which include data such as internal protocol (IP) addresses and data from 'smart meters' monitoring energy usage by addresses linked to identifiable persons.
This paper includes the question that 'why we need tables ' we need tables for reproduction of commits per time period , for re-use of identity merging and relatioinship between message and time of the day.
Anonymizing Public Dataset :-  Data masking - hiding data with altered values we can create a mirror version of a database and apply modification techniques such as character shuffling , encryption , and word or character substitution.
We can easily used the ananymized data re-identifying it but there are issues like:
1) Anonymize by hashing never publushed
2) Deliver the HMAC key to trusted parties
3) Trusted parties hash identities , HMAC (hash) , re-assign identities
4) If you dont have the identity you can not hash.

No personal data can be processed example web form , anonymous dataset from third party. Raw data need special protection .

###### **CONCLUSION**
The aim of privacy enhancing technologies is to protect and preserve the privacy of individual with so many regulation to follow, it can be difficult to keep track of what level of data privacy you need to achieve for your different database. By building processes, data modeling and automating as much as possible, you can make it easier to handel the comlexity of different regulatioins. Managing consent need to document and archieve and also able of producing evidence consent management application must be ethically robust, secure, manage ,document, evidence and model consent process.

➡️ Archieve personal data only as needed for research purpose .

➡️ Delete it as soon as possible.

➡️ Beware of backups and data in clouds storage.

➡️ we can keep personal data identifinitly if it is only for : archieving purposes in public intrest.
Scientific or historical research purpose 
Statistical purposes 
Tge GDPR establishes special safe guards for children in relation to 'information society services'. A sboard team covering all internet services providers including social media platforms.These include a requirements for verified parental consent in respect of information society services offered directly to children aged under 16 .Individual Member State may provide for this threshold to be lowered to 13.
****
