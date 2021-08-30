# dialogflowcx
Dialogflow CX Competition

This COVID-19 Chatbot is designed to combat COVID-related misinformation regarding the Pfizer-BioNTech Vaccine, as well as to check on the wellness of the user themselves. There are four major flows to this chatbot.

1) Vaccination side effects flow: 
In this flow, users can ask the chatbot what are the potential side effects of the Pfizer-BioNTech Vaccine. If the user suggests that they are suffering from such side effects, the chatbot will ask them to specify what side effects they are suffering from. These side effects have an entity type @side_effects and the chatbot will be able to identify the input given by the user. Based on the side effect that the user is suffering from, the chatbot will suggest the appropriate measure to relieve their side effects or to escalate the situation to the user to call for medical attention should the need arise.

2) Vaccine eligibility flow: 
This flow checks on the user's eligibility to take the Pfizer-BioNTech Vaccine by accessing several factors. The chatbot will check for the user's age, medical allergies, and risk of being immunocompromised. Based on the user's input, the chatbot will decide whether the user is eligible for vaccination or should be further accessed by a medical professional before being vaccinated.

3) Physical wellness flow: 
This flow is triggered when users suggest that they are in any way physically unwell. When this happens, the chatbot will check for the temperature of the user. If the user suggests that they have no fever, the chatbot will tell the user to continue monitoring their temperature. On the other hand, if the user is suffering from fever, the chatbot will check for a recent location visited by the user. The rationale for this is to check if the user has been exposed to any COVID-19 clusters. COVID-19 clusters are stored as zip codes in the chatbot via an entity type @Covid_danger_zipcode. If the chatbot detects any cluster visited by the user, the user will be triggered to the "COVID_POSITIVE" page. Likewise, if the user did not receive any recent cluster, but is suffering from COVID-19 related symptoms, and tested positive using an Antigen Rapid Test kit, they will also be routed to the "COVID_POSITIVE" page. On this page, the chatbot will prompt the user to enter their address. The address will then be stored as a parameter $intent.params.address. This is to allow the chatbot to reach out to a medical team who will then aid the user by transporting them safely to a medical facility.

4) Emotional wellness flow: 
This flow is triggered when users suggest that they are in any way emotionally unwell. Using the Patient Health Questionnaire-9 (PHQ-9), the chatbot will objectify the degree of depression severity of the user. Users will be prompted to answer a few questions related to their emotional wellbeing. While this is happening, the chatbot uses a webhook "Score_Calc" to tabulate the scoring based on the questionnaire. Based on the final score, the chatbot is able to recommend appropriate actions to the user based on their severity of depression. This can range from simply taking some fresh air, to reaching out to a professional consultant and offering precautionary texts to manage suicidal tendencies. If the user finds that the questionnaire is taking too long, he or she can use stop words such as "stop", "quit" in order to exit the questionnaire and revisit the Default Start Flow of the chatbot.

Apart from these 4 major flows, the chatbot is also able to handle the following simple questions
- Efficacy of the vaccine
- Types of vaccines available
- How does the vaccine work
- Vaccine concerns relating to pregnancy, chronic illnesses, allergies, and receiving more than 1 type of vaccine
- Number of COVID-19 cases globally to date
- Number of COVID-19 cases in any country yesterday
- Country with the highest amount of COVID-19 case
