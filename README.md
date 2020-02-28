# The Non Nocere Lobby
## Solving the problems of vaccination in a globalised society

In the course of this project, we represent a group of concerned lobbyists, who have created a data science model for the US 
Government. In the current climate of Coronavirus panic, along with the rising tide of anti-science denialism (a la the documentary 'Vaxxed'), more effort than ever is needed to ensure protection against disease. In our study, we began by identifying the states with the lowest flu vaccine uptake, before then identifying the factors most likely to impact it nationwide. The conclusion is focussed on those areas most actionable, and includes strategies for increasing immunisation of the popluation.

## Step One - Data Selection

Initially, we were provided with a dataset covering all of North America, with over 500 variables to choose from. We decided to, as mentioned above, target the flu vaccine. Flu, the common name for the respiratory virus Influenza, has been a feature of human disease since it was first recorded in the 4th Century BC. It has been responsible for high mortality rates since this time, the most severe of which was the Spanish Flu pandemic of 1918. Spreading worldwide in the wake of World War One, it infected some 500 million people, or 1/3 of the global popuation, and possessed a motality rate of around 15%. Although this strain was not the same as the modern flu virus, it shows the signifcant impact the disease can have. Many people appear to believe the flu is similar to the common cold, which it is decidedly not, being much more severe. As a result, we feel that a renewed effort to educate people to the risks of the diease is necessary at the current point in time. This is not also a purely social concern. Studies have shown that sick days from work cost the US economy 530 billion dollars in 2018 (https://www.globenewswire.com/news-release/2018/11/15/1652374/0/en/Poor-Health-Costs-US-Employers-530-Billion-and-1-4-Billion-Work-Days-of-Absence-and-Impaired-Performance-According-to-Integrated-Benefits-Institute.html)

Therefore, through our efforts, we seek to both lessen the impact of the diease on both people, and the economy at large. 

## Step Two - Data Cleaning

We chose the variables based on a correlation matrix to identify the most significant impacts on the uptake of the flu vaccine. This was in order to narrow our analysis to the most relevant areas, and reduce the overall computational load of our eventual model. The raw values were selected, as these represented an overall readout for each variable. We also sourced an alternative dataframe for religious populations in the US. This was to investigate the potential impact belief systems may have upon the acceptance of flu vaccines. We identified Catholicism as a potential opposing factor, due to the fact that in the 1950s, the rubella vaccine was manufactured originally with foetal cells. Overall, we chose variables that would allow us to drive home a message based on where we feel the most impact could be made. We filled the NaN values in the dataset with the median for that state, as this would have the least impact on the overall mean of the group.

## Step Three - Modelling

We split the dataset into training and test sections, in order to train our model on the relevant data. We proceeded to then undertake four training models, in order to investigate which had the overall greatest R^2 value. This value would demonstrate to us which of the models produced the most secure link between the dependent and independent variables. The models chosen were polynomial regression, ridge, lasso and elastic. These models utilised polynomial, scaled values, as well as being cross validated. The model with the highest R^2 value ended up being the Ridge regression, but this left us with over a thousand variables. As this was too many, we opted to go with the Lasso model, the R^2 of which was not significantly lower than the Ridge. We then tested the testing data set on the Lasso model, to identify our co-efficients and render an overall R^2 of 0.29. We also included a visualiser to map the distribution of our test data and our train data, with the test data performing .01 better than the train. Finally, we mapped our co-efficients onto our original dataframe, too see the areas which are actionable regarding flu vaccines.

# Conclusions

We have successfully been able to identify, and infer from this, several factors which may lead to a reduced uptake in flu vaccines in North America. This will allow for further, specialised study, and a hopefully effective campaign against this potentially deadly virus. 
These conclusions are threefold:
  1) Access to education about the disease, and the vaccine, is essential. People respond much better when they are informed,      and can appreciate the dangers associated with an unchecked infection. This was inferred from the mammogram value, and        potentially the Catholic population rates
  2) Linked to this is the nature of targeting those individuals who are not cautious about these potential risk with the          above point. We have taken this from deaths through injury, which may suggest people who are not overtly risk averse. 
  3) Finally, we have targeted ability to afford healthcare as a factor, which also links with point 1. Flu vaccines are not        cheap for those in the bottom of the economic data, and a program of free, or discounted vaccines may go a long way to        ameliorating this.
  
 ## Further Research
 
 Although we have some interesting findings, we are not statistically confident in them to a great extent, which may mostly be due to a lack of specialised data available. Further reserach focussed on access to unbiased, objective information about both the disease, the vaccine, and the makeup of the vaccine would assist in proving that the cure is not worse than the infection. On top of this, we suggest focussing efforts on poorer populations, who may not have the capacity to avoid lower-risk employment, which may create an overall higher risk mindset. The overall cultural and mental data, however, would be harder to quantify, but eminently achieveable with a dedicated surveying team. 
 
### Appendix 

Vaccine notes
Religion - http://childrenshealthcare.org/wp-content/uploads/2012/01/Vaccine-Grabenstein-article.pdf
This review did not identify any canonical doctrine that has led to religious objection to vaccines or immune globulins for Bahá’í Faith, Confucianism, Daoism, Shinto, or Sikhism.  - 33
[Hinduism] Vaccination is widely accepted in predominantly Hindu countries - 33
This review did not identify contemporary Hindu concerns with trace bovine components of some vaccines. - 33

[Buddhism] In the modern Buddhist world, attitudes toward vegetarianism vary by location. This review did notidentify contemporary Buddhist concerns with trace bovine components of some vaccines. - 33
The first written account of variolation describes a Buddhist nun (bhikkhuni) practicing around 1022–1063 CE [9]. She ground scabs taken from a person infected with smallpox (variola) into a powder, and then blew it into the nostrils of a non-immune person to induce immunity. Continuing this tradition, the 14th Dalai Lama participated in poliovirus immunization programs personally - 33

[Jainism] prescribe[s] a path of non-violence toward all living beings - 33 
When considering vaccination, Jains may benefit from an explanation of the seriousness of the diseases to be prevented, to explain the rationale for killing microorganisms in the course of vaccine production - 34

[Judaism] Judaism traditionally expects certain actions of its believers to maintain health - 34
Judaic principles emphasize the community benefits of disease prevention in a manner superior to individual preference, based on scriptures such as Leviticus 19:16 - 34
In distinction to dietary laws, Jewish medical issues are judged based on concepts of medical law contained in halachic codes. The propriety of using vaccines or immune globulins within Judaism would be evaluated from a therapeutic or disease-prevention perspective. Multiple Jewish authorities agree that limitations on medications with porcine components are only an issue with oral administration (for those who observe kosher rules), not products given by injection [86,105]. Thus, the teachings to avoid pork products do not apply to injectable medications, in contrastto foodstuffs. - 34
Permissibility of oral administration of medications with nonkosher ingredients, if necessary to preserve life, is provided in the Talmud - 34
Jewish communities (often ultraorthodox, those who adhere meticulously to Jewish law and tend to be more isolated from others) in several countries have experienced measles and mumps outbreaks associated with declining vaccination - 34
Based on this review, contemporary Jewish vaccine decliners are more likely to cite concerns about vaccine safety than to invoke a specific religious doctrine that has not been considered by acknowledged Jewish scholars. Those scholars have rejected arguments that medical interventions interfere with divine providence - 34

[Christianity] Most Christian denominations have no scriptural or canonical objection to use of vaccines or immune globulins per se, based on this review - 35
These include Roman Catholicism, Eastern Orthodox and Oriental Orthodox Churches, Amish, Anglican, Baptist, the Church of Jesus Christ of Latter-day Saints (LDS), Congregational, Episcopalian, Lutheran, Methodist (including African Methodist Episcopal), Pentecostal, Presbyterian, and Seventh-Day Adventist Church. - 35
xceptions appear in following sections. Roman Catholicism and some other Christian denominations have expressed concern about the aborted fetal origins of the principal formulation of rubella vaccine and some cell lines used to manufacture certain types of viral vaccines - 35

[Amish] Immunization is not prohibited by Amish or Hutterite religious doctrine, but vaccine acceptance varies from district to district. Districts that typically decline immunization reflect a social tradition within these religious communities, related to modernity, more than a theological objection - 35

[Christian Science] Spiritual healing of disease is a central tenet for members of the First Church of Christ, Scientist, founded in 1879 CE in Boston by Mary Baker Eddy. Christian Scientists frequently decline some or all medical help for disease. Individual believers often forego immunization, and church members have lobbied governments for religious exemptions from immunization - 35

[JW]  The Jehovah’s Witnesses…ha[ve] instructed its followers to refuse transfusions of whole blood and certain blood components (e.g., red blood cells, white blood cells, platelets, whole plasma), which they consider a violation of God’s law - 35
The Watch Tower Society denounced vaccination from the 1920s through the 1940s…In the 1990s, Awake! magazine began acknowledging the clinical value of vaccination. A contemporary Watchtower web page acknowledges the efficacy of vaccination in preventing hepatitis A and hepatitis B - 35

[Islam] According to the Qur’an, ¯ a person is not guilty of sin in a situation where the lack of a halal alternative creates an undesired necessity to consume that which is otherwise haram - 36
Opposition to immunization programs among selected Muslim communities has occurred during poliovirus immunization programs in Nigeria, Pakistan, and Afghanistan - 36
In contrast, multiple imams and other Islamic leaders issued clear statements and fatwas describing how immunization is consistent with Islamic principles - 36
Omar Kasule, professor of Islamic medicine at the Institute of Medicine University of Brunei Darussalam noted that polio immunization is obligatory (wajib) when disease risk is high and the vaccine shown to have benefits far outweighing its risks - 36
Muslims may apply additional scrutiny to vaccines required for pilgrims to the annual Hajj in Mecca, when purity takes on extra significance - 36


Reasons for vaccine refusal - UK -  https://reader.elsevier.com/reader/sd/pii/S0264410X17310836?token=40FADD9389524728FC57D25914F4C99556E907AA7C696211164697C8A109F1C4A9273B7A5A0900B305EDF20C57AFDF73

In 2014/15, the national programme was expanded from 2 to 3 year olds to include 4 year olds (provided through GPs as before). The pilot of primary school aged children continued, and an additional16 pilot areas introduced vaccination for secondary school students in years 7 and 8. As vaccine uptake was low at 53.2% - 5398
Thirteen interviewees were ‘White-British’, six‘Asian British – Indian’ and three ‘Asian British – Pakistani’. Eleven parents interviewed were Muslim (adherent of Islam), nine wereChristian, and five stated they had no religion.- 5398
The most frequently cited concerns were about the presence of porcine gelatine (40), side effects (13), and effectiveness of the vaccine (12) - 5399
Other concerns included the presence of chemicals in the vaccine, concerns about the vaccination programme being a pilot or about it being a new vaccine, concerns over the perception that their children were being used to protect others, suspicions about business motives, mistrust of the health service, concerns about vaccine delivery, concerns about testing drugs on children, and concerns about there being too many vaccines. - 5399
Twenty-two parents interviewed expressed the view that their child did not need the influenza vaccine. These parents viewed their child as healthy, with a strong immune system, or at low risk of catching influenza, thought that it was better to build their immune system with disease - 5400
The people I’m aware of who have had vaccinations have then developed flu, and in one case, quite a serious case of it. So, I’m not entirely convinced of its effectiveness” - 5400
Eleven parents interviewed declined the vaccine for religious reasons due to the presence of porcine gelatine in the vaccine:‘‘In Islam we’re forbidden to have any, we’re forbidden to eat pig meat and have anything derived from pig - 5400
Two parents specifically stated that although there may have been transformation of the porcine during the vaccine production process it was still not permissible to eat, inject or inhale it: ‘‘No matter how much it changes, the source remains the same” - 5400
Parents stated that they would be more likely to accept influenza immunisation for their child in the future if there was an epidemic among children, or if family or friends became at risk - 5401
Thirty-four percent of parents, who did not consent to their child being vaccinated aspart of the school programme, had actually vaccinated their child elsewhere, intended to have their child vaccinated, or had not vaccinated them due to medical reasons (whether valid or perceived) - 5402

Reasons - Canada - https://www.tandfonline.com/doi/abs/10.1080/10810730.2017.1312720
 Overall, 91.4% of responses could be explained using the conceptual model and specifically relate to perceived importance of vaccination (46.8%), moral convictions (19.4%), and past experiences with vaccinations services (14.5%). Notably, explanations related to healthcare professional attitudes, risk perceptions and trust, and subjective norms were identified to a much lesser extent than those discussed above. The remaining 8.6% of responses cannot be explained by the model because they do not relate to hesitancy - 506

Reasons - overall - https://journals.plos.org/plosone/article/file?type=printable&id=10.1371/journal.pone.0170550
A negative attitude towards vaccines and attitudinal beliefs such as a decreased perceived effectiveness of the vaccine and a lack of trust in health authorities were the most frequently reported barriers - 19
Perceiving that influenza vaccination was not the norm in the relevant peer group was frequently reported as a barrier. - 19
Taking the extensions of the TPB into account, frequently reported additional barriers of influenza vaccine uptake were utility evaluations such as worries about the safety of the vaccine, low perceived severity of the disease and a low perceived risk of the disease. Furthermore, the lacking recommendations from medical personnel, low frequency of interaction with health services and missing vaccination habits were frequently reported as barriers - 19
On a macro-level, the available evidence suggests that confidence, as well as complacency, are major reasons for influenza vaccine hesitancy. Complacency was mostly expressed by low worry, low perceived risk and severity of the disease - 19
 The lack of confidence was expressed by doubts about the safety and effectiveness of the vaccine as well as a lack of trust in health authorities and, among other knowledge gaps, the belief that the vaccine can cause the flu - 19

OVERALL REASONS DATA
1. Christian (Catholic, Amish, Huttite, Science, Jehovah’s Witness)
2. Muslim (Porcine content of vaccines)
3. Jewish (Orthodox - porcine)
4. Side effects (illnesses) - lack of access to care, distance, lack of education
5.  Testing on kids, and general lack of autonomy of kids 
6. Lack of perceived risk of flu (As a solution to the problem - campaign like the cigarettes?) 
7. Societal pressures - less people getting it, fewer want to get it, TRUST (education)
8. Lack of info (vaccine gives flu) 
9. Able to do it elsewhere - funding/economics
