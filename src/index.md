---
template: schol-template-athabasca-university-mscis-thesis-mini-proposal
citation_style: ieee
author:
  name: Jamie Czerwinski
  email: jamie.czerwinski@gmail.com
  student_id: 2449004
supervisors:
  - name: Dr. Maiga Chang
    email: maiga.chang@gmail.com
    institution: Athabasca University
title: User Experiences with Real Estate Information Systems
subtitle:
references:
  alexa-realtor: {
    "id": "alexa-realtor",
    "type": "webpage",
    "title": "Realtor.ca Traffic Statistics",
    "container-title": "Alexa",
    "URL": "https://www.alexa.com/siteinfo/realtor.ca",
    "language": "en",
    "accessed": {
      "date-parts": [
        [
          "2018",
          10,
          29
        ]
      ]
    }
  }
  similarweb-realtor: {
    "id": "similarweb-realtor",
    "type": "webpage",
    "title": "Realtor.ca Traffic Statistics",
    "container-title": "Similarweb",
    "URL": "https://www.similarweb.com/website/realtor.ca",
    "language": "en",
    "accessed": {
      "date-parts": [
        [
          "2018",
          10,
          29
        ]
      ]
    }
  }
  statscan-re: |
    @misc{statscan,
      title={Women and Paid Work},
      url={https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3610043401},
      journal={Statistics Canada},
      publisher={Government of Canada}
    }
  usability-dimensions: https://doi.org/10.1145/332040.332455
  yuan: https://doi.org/10.1016/j.is.2012.08.004
  gis-fuzzy: https://doi.org/10.1108/14635780610642971
  regis: https://doi.org/10.1080/136588101300304034
  gis-valuations: https://doi.org/10.1080/02693799408901995
  wyatt-maps: https://doi.org/10.1080/095999196368826
  interpolation: https://doi.org/10.1108/14635780010324321
  israeli-valuations: https://doi.org/10.3233/SJI-150939
  lagos-valuations: https://doi.org/10.1080/09599916.2017.1286366
  spain-valuations: https://doi.org/10.1016/j.neucom.2007.07.031
  athens-valuations: https://doi.org/10.1080/09599916.2012.755558
  jeffreys: https://doi.org/10.1016/j.jspi.2004.01.005
  spain-valuations-reduced: |
    @article{bulut2011residential,
      title={A Residential real-estate valuation model with reduced attributes},
      author={Bulut, Bahar and Allahverd, Novruz and Kahramanli, Humar and Yalpir, Sukran},
      journal={International Journal of Mathematical models and Methods in Applied Sciences, 5 (3): 2011, p 586},
      volume={593},
      year={2011}
    }
  turkey-valuation: |
    @article{yalpir2017use,
      title={Use of Spatial Analysis Methods in Land Appraisal; Konya Example},
      author={Yalpir, Sukran and Unel, Fatma Bunyan},
      year={2017}
    }
  sus: |
    @inbook{inbook,
      author       = {John Brooke},
      title        = {Usability Evaluation in Industry},
      chapter      = 21,
      pages        = {189-194},
      publisher    = {CRC Press},
      year         = 1996,
      month        = 6
    }
  mobile-traffic: {
    "id": "mobile-traffic",
    "type": "webpage",
    "title": "Mobile share of website visits worldwide",
    "container-title": "Statista",
    "URL": "https://www.statista.com/statistics/241462/global-mobile-phone-website-traffic-share/",
    "language": "en",
    "accessed": {
      "date-parts": [
        [
          "2018",
          10,
          29
        ]
      ]
    }
  }
---

# Problem and Research Goal

## Background

Real estate trade is an important economic activity. As of August 2018, real estate trade comprised 12.9 per cent of Canadian gross domestic product, not including the contributions of construction, financing, and insurance.[^statscan-re] Purchasing a home is the largest transaction most people will undertake in their lives.

Obtaining information about prospective homes and neighborhoods is an important and time-consuming activity for real estate market participants. Reflecting this, realtor.ca -- Canada's publicly accessible portal to the Multiple Listing Service -- is one of Canada's top 100 most visited websites.[^alexa-realtor],[^similarweb-realtor]

Unfortunately, sources of real estate information are often difficult to access and disparately located. Opportunity may exist to improve the accessibility and usefulness of this information by consolodating and optimizing its presentation within a single system, and by validating the usability of such a system.

Prior research on real estate information systems has tended to focus on two primary areas:

1. Property valuation estimation systems.
2. Property searching, querying, filtering, and recommendation systems.

This research tends to focus on system architecture, algorithms, and design. They are not particularly focused on usability, and lack rigorous usability testing and validation. Little attention is paid to determining the relative importance of specific real estate attributes or dimensions to end users.

### Property valuation systems

Property valuation systems research comprises a significant proporation of the real estate information system literature. Such systems have been demonstrated to be particularly effective in high-volume applications where valuation accuracy on individual properties is less important than average accuracy across large sets of properties -- mass appraisal use cases. For example, these systems are useful to municipal or regional authorities when assessing property values for taxation purposes,[^gis-valuations] or for the purpose of constructing property value maps[^wyatt-maps].

These systems tend to use supervised learning and interpolation[^interpolation] techniques -- including regression, neural network, and kernel smoothing models -- to estimate unknown property property values from known property values and property attributes. They also focus on point-in-time valuation -- forecasting tends to be out of scope for this research.

Because of the local nature of real estate markets and the market and property data used to train property valuation models, these studies tend to focus on specific and limited geographic regions. Research into these systems has been published for Israel,[^israeli-valuations] Lagos, Nigeria,[^lagos-valuations], Albacete, Spain,[^spain-valuations],[^spain-valuations-reduced], Athens, Greece,[^athens-valuations], among others. This is likely a necessary limitation of almost all real estate information systems.

None of these property valuation system studies makes any effort to formally assess the usability of the systems under study.

### Searching, Querying, Filtering, and Reccomendation Systems

Systems that assist with searching, querying, filtering, and recommending properties comprise another significant class of real estate information systems. 

For example, Yuan et. al. developed and tested a recommendation system that integrated various sources of real estate information to support an improved real estate querying and filtering experience.[^yuan] Although it demonstrated high satisfaction among users, its efficiency and effectiveness were not estimated. Further, its satisfaction survey design was not particularly rigorous.

Pagourtzi et. al. also focus on a novel real estate querying architecture using fuzzy matching to enable users to filter properties by various attributes.[^gis-fuzzy] The focus of this work is on increasing the efficiency of the search process for market participants. Unfortunately, they provide no usability assessment. 

Zheng and Zhou outline a system designed to help users filter and evaluate locations by filtering on attributes and scoring locations as a weighted linear combination of those attributes, or some scoring of those attributes.[^regis] Once again, this work focuses on increased search efficiency. It does so by introducing "expert judgement" in the scoring and weighting of location attributes. They too performed no rigorous usability testing. 

These studies all suffer from a lack of rigor in their usability testing. No evidence is provided that the systems used in the studies were designed in response to user priorities. 

The designs also tend to require access to the entire set of low-level data over which the querying, filtering, and consolidation is performed, or, alternatively, to remote services that can be delegated this work. Accessing and maintaining such data can be costly.

These studies are also all relatively focused on the property querying and filtering process, or on consolidating the information provided to the end user into a one dimensional score, while providing little justification that these are features that users want.

There may be opportunity for novel designs to provide significant value to real estate market participants. Instead of querying, filtering, and attribute consolodation systems -- systems which have already been studied -- users might prefer systems that provide expanded, faster, and easier access to raw attributes. There is also a significant opportunity to ensure that real estate information systems are designed in response to user priorities, and that the usability of such systems is rigorously validated.[^usability-dimensions]

## Research Goal

This research will investigate user experiences with real estate information systems. In particular, it will investigate the extent to which a purpose-built real estate information system prototype can improve user experiences with specific real estate information use cases.

This research will investigate the following broad questions:

 - Does the prototype improve the *effectiveness* of users on real estate information retrieval tasks?
 - Does the prototype improve the *efficiency* of users on real estate information retrieval tasks?
 - Does the prototype improve the *satisfaction* of users on real estate information retrieval tasks?

# Methodology

This study comprises a review of the literature on real estate informations, as well as the design, development, and validation of a prototype system designed to make useful information on real properties more accessible to real estate market participants.

The scope of the prototype will be limited to properties located in Edmonton, Alberta, Canada.

Study participants will be recruited from the Realty Executives office, the intern's personal network, and from online forums, and will be engaged at varying levels throughout the design, development, and validation processes.

In order to determine if different classes of users have different preferences for or  engagement with the system, all participants will be asked whether they meet any of the following categories:

 - Real estate agent or broker
 - Prospective renter
 - Prospective real estate buyer
 - Prospective real estate seller

## System Design and Development

Because over half of web pages were served to mobile phones as of 2018, in order to maximize the accessibility of the system to end users, it will be designed and developed as a mobile accessible web application.[^mobile-traffic]

Because Realtor.ca is already a top source of property information for real estate market participants, the system will be designed to incorporate information that complements the information available on Realtor.ca.

Users will be surveyed to elicit their preferences regarding which information should be prioritized in the design and development of the system. Users will be asked to rank prospective information in order of priority. System support for this information will then be extended as guided by priority and opportunity.

Potential information sources include, but are not necessarily limited to:

 - Neighborhood demographics
 - School zoning
 - Property taxes
 - Tax assessment value
 - Crime rates
 - Proximity to amenities
 - Flood risk
 - Internet availability

## Usability Testing and Validation

The usability of the system will be evaluated on three dimensions: effectiveness, efficiency, and satisfaction.[^usability-dimensions] 

The *effectiveness* of the system will be estimated by measuring the extent to which users of the system are able to provide correct answers to questions about real properties relative to using alternative sources of information.

These questions will ask users for specific pieces of information about a specific address. For example, a user might be asked:

 > *What is the City of Edmonton assessment value for this property?*

The *efficiency* of the system will be estimated by measuring whether users are able to answer these questions more quickly using the system than they are using alternative sources of information.

User *satisfaction* with the system will be estimated in two ways. First, by administering the *System Usability Scale* -- a standardized and well validated usability Likert scale -- survey to users.[^sus] Second, by surveying users about their preference for using the system relative to other sources of information for various use cases. For example, to estimate satisfaction with the system's property tax assessment feature, a user would be asked:

 > *Which system did you prefer to use for obtaining property tax assesment information about a property?* 

These dimensions will each be analyzed in three ways -- by feature, aggregated across all features, and for the system as a whole.

For each analysis, we assume that each observation used in the analysis is independent and identically distributed. We model these measures as Bernoulli distributed random variables. The proportion of each sample that favors the system is then the success probability parameter of a binomial distributed random variable. After each user is sampled, we will calculate the maximum likelihood estimate for the binomial distribution's success probability parameter. The Jeffreys interval will be used to estimate the confidence that this parameter is greater than 1/2 -- ie. that the system is an improvement on existing methods.[^jeffreys] Probability distributions for this parameter will also be reported.

Sample sizes will not be pre-determined. New users will be recruited and sampled either until, in the opinion of the researcher, confidence that the system differs significantly from existing methods is sufficiently high relative to the cost of sampling new participants, or the cost of sampling a new participant exceeds the potential increase in confidence that the system differs significantly from existing methods.

# Rationale for the research

Although a significant amount of research on real estate information systems exists, a relatively small proportion of that research focuses on user experiences with such systems. Moreover, the research that does investigate user experiences with these systems is relatively poorly designed and is difficult to generalize.

Further, real estate information systems are frequently used by a large population. Improving the user experience of these systems could significantly benefit this population.

Research efforts to develop and test real estate information systems with improved user experiences offers to improve both the state of research, as well as the experiences of a large number of users.

# Timelines

| Deliverable | Start Date | End Date |
|-------------|------------|----------|
| Detailed proposal development | 2019-02 | 2019-08 |
| Form supervisory committee | 2019-02 | 2019-02 |
| Literature review | 2019-03 | 2019-07 |
| Obtain ethics approval | 2019-06 | 2019-06 |
| Develop pre-design and development user survey  | 2019-03 | 2019-03 |
| Administer pre-design and development user survey | 2019-05 | 2019-05 |
| Analyze pre-design and development user survey  | 2019-06 | 2019-06 |
| Develop requirements for prototype system | 2019-08 | 2019-08 |
| Design prototype system | 2019-07 | 2019-10 |
| Develop prototype system  | 2019-10 | 2020-04 |
| Design and develop usability experiments for prototype system | 2020-04 | 2020-06 |
| Administer usability experiments for prototype system | 2020-07 | 2020-09 |
| Analyse usability experiment results  | 2020-09 | 2020-10 |
| Write thesis | 2020-10 | 2021-02 |
| Oral defense | 2021-03 | 2020-03 |

# Anticipated Results and Contributions

This research will generate two primary artifacts:

 1. A thesis paper describing the research and its results
 2. The prototype real estate information system generated and investigated in the course of the research.

A journal article and conference paper summarizing the research may also be developed.

The thesis and prospective journal article and conference paper will contribute to both the real estate information system and user experience literature.

The prototype real estate information system may be maintained and made available to the public, potentially enhancing their real estate information system user experiences.

# Possible dissemination

A journal article or conference paper summarizing this research would be a good candidate for inclusion in a user experience or usability focused journal or conference. Prospective journals and conferences include:

 - The ACM CHI Conference on Human Factors in Computing Systems
 - Human Factors: The Journal of the Human Factors and Ergonomics Society
 - Journal of Usability Studies
 - Behaviour and Information Technology
 - International Journal of Human-Computer Studies
 - International Journal of Human-Computer Interaction
 - HCI International Conference
 - Human-Computer Interaction
 - Interacting with Computers

# Hardware, Software, and Organizational Support Required

The real estate brokerage Realty Executives: Devonshire Realty has agreed to provide logistical and financial support to this project. They have agreed to act as an industry partner for the purposes of a MITACS Accelerate grant application. They will provide access to real estate agents to act as survey and usability experiment participants.

Because this research involves human subjects, research ethics approval from the Athabasca University Research Ethics Board is required.

The work required to undertake this research will be conducted at either the graduate student's home office or at the Realty Executives: Devonshire Realty office. The graduate student's computer will be used to conduct the research, development, and analysis. Realty Executive: Devonshire Realty computers will be used to conduct usability tests with real estate agents.

Amazon Web Services Educate will be used to host the prototype real estate information system developed in the course of this research. The subscription to this service is provided to all Athabasca University students.

# References