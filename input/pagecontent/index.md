The FHIR profiles and extensions in this implementation guide are intended to
fill gaps in current implementations of HL7 Version 2 and RESTful APIs currently
available to implementers. This implementation guide expands FHIR best practices
to assist organizations that adapt and extend FHIR profiles and implementation
guides required in their jurisdictions (e.g. US, Canada) to apply them to
locally-applicable requirements that meet their stakeholders business needs.
Currently there are several US Realm projects that need to use, manage, and collect information about gender identity and sex using information provided by patients. 
This specification also identifies code systems and terminology gaps that
require require subsequent change proposals to LOINC and SNOMED CT consistent
with the requirements summarized in the use cases.

### Background

Health care is increasingly turning to technology to help improve systems and processes to benefit patients and their health. Ongoing efforts supported by governing agencies and standards committees are responding to the demonstrated need through standards that allow for seamless integration of patient information between systems.

It is imperative that both sex and gender vocabulary be formally integrated into clinical care because they are not interchangeable. Both influence health outcomes. Gender-marginalized individuals1 face significant barriers to adequate and culturally responsive healthcare, leading to numerous health disparities. By adopting structured data sets, agnostic systems will be better equipped to transmit (share) and accept data elements that will improve the accuracy of patient information. Furthermore, standardizing data enables information to be combined with other data sources used to evaluate clinical outcomes. While data collection and documentation are critical factors in clinical decision-making, these new data will also promote important dialogue between clinicians and patients. Ultimately, this will assist with improved quality of care, reduced clinician burden and less fragmentation of a person’s clinical record.

Currently, it is common that a single data element is used to capture both sex and gender information, often assuming these two items are one unified idea. This specification challenges that notion and proposes that independent consideration of sex and gender, and the assessment of their differences promotes the health of women, men, and people of diverse gender identities of all ages, avoiding systematic errors that generate results with a low validity (if any) in clinical studies [78]. This model describes an approach that can improve data accuracy for sex and gender information in health care systems.

### Scope
#### In-Scope
The consultative process that has produced this HL7 informative specification reflects clinical end user needs on balance with contributors from 2SLGBTQIA+2 organizations such as Fenway Health and active participants with lived experience from the United States and Canada. Vendors were included from Japan, Germany, India, and the United States.

The proposed model essentially outlines a series of specific “context of use definitions” of sex and gender types and outlines required information for each potential use-based collection of specified sex and or gender codes. The sex and gender types we have included illustrate how sex- gender codes, when captured in a prescribed context, clarify the capture of patient clinical information. Some of the noted contexts of use may represent single or multiple information sources such as chromosomal allosomes, genotype, hormone levels, secondary sex characteristics, desired perception, surgical status or planned outcome, organ function, etc. It is clear that a single patient may have multiple different codes properly represent them when capturing multiple sex- gender types.

As a result, the in-scope core list of specific gender and sex use-contexts described by the specification, are as follows:
1. Gender Identity (GI)
2. Sex for Clinical Use (SFCU)
3. Recorded Sex and Gender
4. Name to Use
5. Pronouns

#### Out-of-Scope
The Gender Harmony Project considered other data elements or attributes for the specification but has deferred those for future consideration because these categories did not meet the rigor necessary for Balloting at the present time.
Work reserved for future consideration include:
● Titles, Honorifics and/or Salutations: in accordance with an accepted practice or style (see Public Works and Government Services Canada, Translation Services Style Guide). Examples include Mr., Mrs., Ms., Mx, Doctor, Engineer, Captain, etc.
● Defining or modeling the representation of patient sexual orientation, a future or future iteration of this group may convene separately to discuss such modeling.
● Specific changes in standards to directly align with the proposed abstract model noted in this specification. In particular for HL7, enhancements to FHIR resources should be undertaken after consideration of this proposal. Some suggestions are provided in the Implementation Guidance section.
● Representations of the provenance and qualifications needed for the collection of sex and gender identity information.

### Intended Audience
#### Government / Regulatory
Regulatory, legal and research organizations have a vested interest in a consistent approach to documenting sex, gender and related information not only for patient care purposes (primary/acute/tertiary care, lab/diagnostics, allied health, ADT/administration, insured/payor, etc.) but also for a wide range of research, social service integration, public health, population health, epidemiology, cancer staging and registry, and national/international medical record exchange purposes. “Sex And Gender Equity in Research (SAGER)” (77) discusses a wide range of such uses. Many of the other reports and articles in the Bibliography include reference to related regulatory purpose and use.

For example, the government of Australia has issued Guidelines on the Recognition of Sex and Gender (83) that will affect regulations and procedures accordingly once adopted. In the US, various federal and state agencies have projects proposed or started to update regulations and have provided guidance within the United States Core Data for Interoperability (USCDI) and the Interoperability Standards Advisory (ISA), whereas Canada, Germany and others have similar state, provincial, and national regulatory efforts underway.

Likewise, this HL7 informational model will be used by regulators to inform future development of communications and data modeling in other jurisdictions.

#### Standards Development Organizations (SDO)
Messaging and interchange standards developers (e.g., Integrating the Healthcare Enterprise (IHE), HL7 International) and standardized terminology organizations play a role in implementing guidance around distinguishing, capturing, and sharing gender and sex information. HL7 standards such as Fast Healthcare Interoperability Resources (FHIR®) define how information can be shared in a consistent manner. Standard clinical terminologies such as Systematized Nomenclature of Medicine (SNOMED) and Logical Observation Identifiers Names and Codes (LOINC) are often used to encode data via coded concepts.

Having all of these organizations subscribe to the guidance in this specification will assist to bridge the gap between technology and implementation requirements. As noted in the Out-of-Scope section, other HL7 International Work Groups are encouraged to review this guide to determine the impact of the recommendations on existing and proposed standards for consistency and to plan to integrate the new terminology, if/as necessary.

### Vendors
All the sex and gender information described in this document requires engaged review and implementation support from all EHR system vendors to have a meaningful impact on patient care and clinical interactions. We encourage adoption of the guidance into standard specifications such as HL7 v2, FHIR, C-CDA, DICOM, and NCPDP. Vendors are encouraged to incorporate the intent of the specification into the end-user workflow.

### Researchers
Demographic information that identifies male/men or female/women participants is a core segmentation in study design. It is clear that the historical binary approach to sex and gender data capture has affected gender and sex analysis and reporting (106). Some research studies refer to this cohort variable as sex, some refer to it as gender.
Though the notion of sex is recognized implicitly as an important factor in clinical research, more work is needed to standardize the way sex and gender are reported and elucidate the way these characteristics function independently and together to influence health and health care (77). The vocabulary in this guideline, once implemented, will go a long way towards facilitating this need and ensuring more accurate and precise data in the future.

### Current State
#### Developments in the Understanding of Sex and Gender
This document recognizes that numerous factors have changed understanding of sex- and gender- related concepts over the past century. There have been numerous paradigm shifts in the fields of science, medicine, and technology during the same period.

Medical practice today handles higher patient volumes than ever before. Developments in care for patients with variations in gender and sex characteristics require better record keeping and more intricate models regarding those characteristics. Cultural competence and awareness has become a crucial element in providing care services. These additions to this standard are necessary to communicate salient medical information.

#### United States Core Data for Interoperability (USCDI) and Interoperability Standards Advisory (ISA)
The United States Core Data for Interoperability (USCDI) is a standardized set of health data classes and constituent data elements for nationwide, interoperable health information exchange. Organized into Data Classes by common themes or use cases, Data Elements represent the most granular level at which a piece of data is exchanged.


● Within the Patient Demographics class, there is a single element entitled Birth Sex that must be coded in accordance with the HL7 Version 3 (V3) Standard, Value Sets for AdministrativeGender and NullFlavor—
F Female Female
Page 9 HL7 Informative Document: Gender Harmony - Modeling Sex and Gender Representation, R1 © 2021 Health Level Seven International. All rights reserved. August 2021
   
Coding Standard | USCDI | HL7 Version 3 (V3) Standard - Birth Sex
Concept Code | Head Code Defined Value Set
Print Name
Definition, Properties, Relationships
   
   M Male Male UNK Unknown nullFlavor
● Gender Identity, not included in USCDI V1, has been proposed for inclusion in the USCDI Patient Demographic class and is currently listed as USCDI Level 2. For additional information, please see the information posted on HealthIT.gov/Patient Demographics/Gender Identity.
The Interoperability Standards Advisory (ISA) “represents the model by which the Office of the National Coordinator for Health Information Technology (ONC) will coordinate the identification, assessment, and determination of "recognized" interoperability standards and implementation specifications for industry use to fulfill specific clinical health IT interoperability needs.”
● The ISA includes the “Sex at Birth, Sexual Orientation and Gender Identity” section with specific sub-sections on:
○ Representing Patient Gender Identity ○ Representing Patient Sex (At Birth)

#### FHIR
Section 8.1.7 of the HL7 FHIR Specification v.4.0.1 (R4 – Mixed Normative and STU) addresses representing Patient Gender and Sex in FHIR resources, and recognizes that many systems and organizations only provide for a single attribute to represent all aspects of a patient’s gender and sex. Documentation and interoperability considerations covered in the FHIR specification include various social and biological aspects, including Administrative Gender. As input to patient matching algorithms, Administrative Gender is often used to interoperate between systems that use a single generic property (patient.gender). Within FHIR, users should note that gender might not match the biological sex as determined by genetics or the individual's preferred identification. As there are other legitimate possibilities than male and female, systems providing decision support or enforcing business rules should ideally do this on the basis of Observations dealing with the specific sex or gender aspect of interest (anatomical, chromosomal, social, etc.) This stance is in-line with the recommendations made in this specification.

Context for use of additional elements, such as Clinical Sex, Clinical Gender, Gender Identity (GI), Sex Assigned at Birth (SAAB) and Legal Sex are also described to encapsulate a broader range of social and biological patient attributes across the health care spectrum. For further information, visit the HL7 FHIR Release 4/8.1 Resource Patient - Content web page.

#### DICOM
The existing DICOM model dates back to 1985 and earlier work. It was frozen and has remained unchanged since 1995. Imaging medical records from 1995 onward all use this model.
The DICOM model was originally specified to include a single mandatory field to capture Patient Sex with allowed values of Male, Female, Other and Unknown. The usage was not explicitly specified, but the implicit usage was Sex for Clinical Use. It is used in various places within DICOM, and by DICOM compliant equipment, to specify values for sex-linked characteristics. For example, it is used as input for Standard Update Value (SUV) computations in nuclear medicine and used as a parameter into patient dose sensitivity models for radiation dose reporting. These computations and models are based on statistical analysis of many patients and reflect the sex-linked characteristics of the studied populations.

Operationally, this field is initially populated either by hand or based on an order. The order is frequently conveyed by HL7 message. The inconsistency and confusion caused by having one field for multiple concepts (administrative sex, gender identity and sex for clinical use) leads to occasional inconsistency in the image results and reports created by DICOM equipment. It also leads to operators occasionally making changes to reflect the patient’s sex for clinical use that then cause downstream inconsistencies with HL7 systems that were using administrative sex or gender identity.

#### SNOMED International
SNOMED International created, then disbanded, a Sex and Gender Clinical Project Group. The project group gathered SMEs to provide advice on the current clinical and administrative needs for sex and gender terminology standards. The group was disbanded in May 2021 pending completion of the ISO analysis and this Gender Harmony project.

#### HL7 v2
HL7 v2 initially had a single field PID-8 Sex with user-defined values. In V2.4 (2000) this field was renamed to Administrative Sex in recognition that it was insufficient or inappropriate for conveying sex for clinical use. There are now several segments in HL7 v2 that support communicating administrative sex values for various actors. HL7 v2 defines PID-8 Administrative Sex for a patient, IN1-43 for the Insured’s Administrative Sex, GT1-9 for the Guarantor’s Administrative Sex, NK1-15 for the Next of Kin / Associated Party’s Administrative Sex, etc. It is widely recognized that the concept of Administrative Sex is not clearly defined and is very widely overloaded with other concepts in real-world implementations.

#### C-CDA / HL7 v3
HL7 took the v2 Administrative Sex attribute and renamed it Administrative Gender in v3, defining it as “the behavioral, cultural, or psychological traits typically associated with one sex”. It contained an explicit caveat that it was not for clinical use and was “a high-level classification [...] for the appropriate allocation of inpatient bed assignment.”

In actual implementation, primarily in CDA, this attribute was typically just transcribed from the v2 messaging PID-8 Administrative Sex field, with all its inherent ambiguities.

#### NCPDP
The National Council for Prescription Drug Programs (NCPDP) is an ANSI accredited SDO representing the pharmacy services industry. The NCPDP SCRIPT ERx standard is used in EHR systems. The current values under the standard, labeled Gender, are F (Female), M (Male), U (Unknown), and N (Non-binary).

owever, NCPDP is moving to include both Administrative Gender and Sex at Birth elements in its future state. NCPDP has identified a business need to identify when someone’s gender is different then their Sex Assigned at Birth (SAAB) to obtain medication without delay, in situations where gender mismatch edits may occur.

Currently, NCPDP has approved the field Sex Assigned at Birth (F32-W8) that will be used as an optional field in the event the Sex Assigned at Birth (if present) differs from the Patient Gender Code (305-C5), Gender Code (721-MD) or the current XML element Gender. For example, the Sex Assigned at Birth could be “Male” with the Gender/Patient Gender Code/Gender Code field “Female”.

Note: The NCPDP Gender Transition Task Group determined the Conditional Gender Code (C08- 4T), and Purchaser Gender Code (595-YY) were not applicable to patient matching. There was also an added element of “Reproductive Potential”.

#### X12
X12 is an ANSI accredited SDO that develops and maintains transactions based in electronic data interchange (EDI). Currently, all X12 transactions use the following values to classify the element Gender Code: F (Female), M (Male) and U (Unknown). The definition for this element is “Code indicating the sex of the individual,” X12 does not have separate fields for gender identity and has attempted to clarify reasoning behind the use of Unknown to represent nonbinary gender on claims as follows:
    “...the value of “U” is the appropriate option when the sender cannot explicitly select either “M” or “F”. While the description of value “U” is Unknown, in this case, Unknown only means that neither “M” nor “F” can be sent. The reason that neither “M” nor “F” can be sent is what is unknown. “U” does not necessarily mean that the gender is unknown to the sender.”
In a future state, X12 is considering expanding to the following available elements: F (Female), M (Male), I (Non-binary), T (Self-reported as transgender), A (Not provided), U (Unknown) and include the code notes:
    Code value A = when gender cannot be sent due to reporting restrictions
    Code value U = use when gender is unknown.
X12 is currently deliberating on this and will hold future votes in 2021 to address the need for additional code values for the DMG03 in future versions.

### Impact of Sex and Gender on Clinical Care
In 2016, The Report of the 2015 U.S. Transgender Survey which asked 27,715 self-identified transgender persons about their experiences in health care, noted that 33% had at least one negative experience with a health care provider related to being transgender, that 23% did not seek the health care they needed due to fear of mistreatment, and 33% did not go to a health care provider when they really needed to because they could not afford it (26,75).

As National LGBTQ Task Force Director Rea Carey noted:
    It is outrageous that basic health care is being denied to transgender and gender non-conforming people and that so much additional trauma is being caused by doctors instead of being resolved by doctors. The medical profession must take these data seriously and ensure that everyone in the medical care system knows how to provide transgender- sensitive medical care.

This pattern is not exclusive to the United States. Medical mistreatment and/or malpractice, as well as violence against transgender and gender-diverse persons is well documented in many countries including Argentina (72), Armenia (71), Bangladesh (27,30,70), Bosnia and Herzegovina (71), Brazil (71,72), Canada (32,33,34,72), Colombia (71), Dominican Republic (72), Egypt (71), France (70), Honduras (71), Hungary (70), India (28,29,31,71), Indonesia (71), Iran (71), Italy (70), Japan (70,71), Kazakhstan (71), Latvia (71), Malaysia (71), Mexico (72), Nepal (36), the Netherlands (71), Nigeria (71), Pakistan (31,71), Paraguay (72), Peru (72), Poland (70), Russia (71), Saudi Arabia (71), Serbia (70), Ukraine (35), and the United States (70,72), among others. Oftentimes, such mistreatment compounds with other kinds of mistreatment due to race, caste, socioeconomic status (SES), and disability among other things (26). Between 1 and 2 million U.S. Americans identify as transgender, nonbinary and/or gender-nonconforming (45), with at least 25 million persons identifying as such worldwide (44).

The situation for intersex individuals is not much better. Despite worldwide condemnation of intersex genital mutilation, the practice is still widespread and even hurts non-intersex (dyadic) persons, such as in the case of David Reimer. Reimer, known in medical circles as the patient involved in the “John/Joan” case, committed suicide in 2004 following years of abuse at the hands of medical professionals. Clinicians routinely lie to patients about their status as intersex, obfuscate clinical records, and promote practices which have been shown to have negative effects on patient mental health (46,47,50). As Australian intersex politician Tony Briffa noted in a 2013 inquiry: “If we are talking about coercion, doctors coerce families, parents, into believing by saying: ‘We need to remove these testes [or other sex organs] because it will make your child normal’”. Routine forced sterilization of transgender, gender-diverse, and intersex persons is still common in many countries (51,52,53,54).

Despite the “depathologization3” of homosexuality in the Diagnostic and Statistical Manual of Mental Disorders (DSM) in 1973, the movement to depathologize transgender persons has been slow, and receives pushback even today. Medical providers continue to add being transgender to problem lists and as diagnoses in multiple jurisdictions, under labels such as “gender identity disorder” (GID). GID was removed from the World Health Organization’s ICD listing in 2019. The LGBT rights director at Human Rights Watch, Graeme Reid noted that, “[t]he WHO’s removal of ‘gender identity disorder’ from its diagnostic manual will have a liberating effect on transgender people worldwide... Governments should swiftly reform national medical systems and laws that require that now officially outdated diagnosis.”

However, despite these calls to action, in the last ten years, transgender and intersex persons continue to report harassment and mistreatment in all areas of medical care: oncology, cardiology, geriatrics, pediatrics, psychiatry, primary care, emergency care, radiology, internal medicine,neurology, obstetrics, gynecology, pathology, surgery, and urology, to name a few (72,74). Transness still appears in problem lists, coded using antiquated terminology from ICD-9 and ICD-10 (and sometimes terminology which is even more antiquated). In some cases, this is performed because providers feel that there is nowhere else in the health record to codify that a patient is transgender, but other cases persevere even when patients specifically ask for it to be removed. This can seriously affect a transgender person’s life, as many jobs require that health records be released to employers or even publicly available for anyone to access. Many of these issues have led to significant morbidity and even patient death.

In 2016, the United Nations Programme on HIV/AIDS, alongside the World Health Organization (WHO) Global Health Workforce Alliance, launched the Agenda for Zero Discrimination in Health Care, highlighting the importance of respectful care which takes into account the values and concerns of marginalized groups, including those of transgender people (43). The agenda prioritized creation of health care frameworks for adequate monitoring and evaluation of health care systems to ensure accountability and monitor progress of health disparities in vulnerable populations, including transgender, gender-diverse, and intersex persons (47). US organizations like Fenway Health in Boston (84), Callen-Lorde in New York (85) and UCSF Trans Care in California (86) have developed programs and services for LGBTQIA+ communities, as Trans Care BC (87) and Rainbow Health in Ontario (88) have similarly in Canada.

Achievement of these goals in affected populations is not possible without an underlying, consistent structure for data collection. Such data are essential to addressing health disparities and have catalyzed initiatives to improve SOGI (sexual orientation and gender identity) data collection at the Institute of Medicine, the American Medical Association, the U.S. Centers for Disease Control and Prevention (CDC) (4), the Council of Europe (56), the United Nations Human Rights Office of the High Commissioner (57), ILGA-Europe (58), Stonewall (59), and numerous other organizations worldwide. Third gender categories have even been added in national censuses in India and Nepal (both starting in 2011), despite their removal from the 2020 U.S. Census.

Given that gender and sex-related data greatly impact individual care, it is critical that the health care community create data models that enhance understanding and collection of critical data such as organ inventories; culturally-specific health factors; surgical histories; hormonal histories; chromosomal makeup; interlocking demographic factors; individual experiences of discrimination (such as deadnaming or misgendering), sexual assault, and physical violence; differences in sexually transmitted diseases, cancers, cardiovascular diseases, and mental health conditions, all of which directly impact the health outcomes of transgender, intersex, and gender-diverse populations. Mixing up these data can result in situations of life or death. As former president of the World Professional Association for Transgender Health (WPATH), Jamison Green said: “By not actually addressing what kinds of variabilities exist in people’s sexual4 [sic] behaviors, we blind ourselves to potential solutions to these problems” (62).

Studies indicate that around 40% of transgender persons in the U.S. attempt suicide in their lifetime [26,103]. Afton Bradley at the Virginia League for Planned Parenthood noted in 2017 that there was a “dramatic reduction in those [suicide] attempts when people have access to affirmative care” (61). “We need SOGI data collection to develop effective interventions to reduce and eliminate these disparities,” Cahill and Makadon pointed out the same year, “... If they do not count us, we do not count” (1).

### Sex and Gender in Quality Measurement
Clinical quality measures traditionally evaluate performance using manually abstracted clinical and administrative data. Electronic clinical quality measures (eCQMs) evaluate performance using data extracted from electronic health records and/or digital health information technology (HIT) systems. Patient demographic information is often used simply to specify eCQM inclusion and/or exclusion criteria. As described in the Current State section, Gender and Sex are often represented in a single data element utilizing various coding standards and that inconsistency in data capture and implementation leads to downstream issues for quality measurement instruments and outcomes.

For example, the National Committee for Quality Assurance (NCQA) produces the Healthcare Effectiveness Data and Information Set (HEDIS). Approximately 191 million people are enrolled in plans that report HEDIS results, making it one of health care’s most widely used performance improvement tools. HEDIS covers six (6) domains of care utilization measures, including Child and Adolescent Well-Care Visits, Frequency of Selected Procedures, Identification of Alcohol and Other Drug Services, Mental Health Utilization, Antibiotic Utilization and Healthcare-Associated Infection (HAI) Standard Ratio. For all these measures, individuals with nonbinary gender are excluded from HEDIS utilization measures that currently require a specific gender (male or female). NCQA recognizes this as an issue and has stated that it “continues to track industry standards for nonbinary gender”. In other words, the guidance provided in this specification can help improve representation of nonbinary gender and therefore measurement.

### Sex and Gender Reporting in Payment for Care
Some EHR systems have already begun to suggest tests or workflows based on sex or gender data which is often inaccurate in describing the needs of transgender, gender-diverse, and intersex persons. For instance, a patient may need to switch their insurance “sex” for a procedure to avoid denial of coverage or to even be offered a procedure or test in the first place. Pharmacies may also have to administratively change “sex” for approvals for particular medications and then switch the “sex” back to avoid denial of coverage (per NCPDP page 11). In addition, providers may have to address dozens of automatically flagged lab results which are irrelevant to the patient but are nonetheless required due to compliance regulations (63).

Switching “sex” fields back and forth may trigger hundreds of new results or diagnostic warnings or messages, adding to the already significant issue of alert fatigue among medical providers. Further, clinicians may miss proper risk assessments based on whether the “correct” sex field is provided. For instance, a transgender woman who is marked as “male” may miss crucial breast cancer screenings, but a transgender woman who is marked as “female” may miss prostate cancer screenings. Only by including contextual data about gender identity, sex assigned at birth, organ inventories, hormone levels, and chromosomal makeup can these issues be sufficiently avoided.

### Sex and Gender Uses in Data Analysis
Storing and exchanging data in structured formats ensures that EHR and HIT systems are better equipped to notify health care teams of appropriate and preventive services, but this is not an end itself. It is critical to have standardized high-quality data in order to conduct data analysis to address health inequities. While there have been some scientific advancements, there continues to be a dearth of data and literature on health outcomes and experiences for transgender and gender diverse people. Many transgender and gender diverse people remain largely invisible to their care providers, face stigma, barriers to accessing care and related health disparities. Standardized data will facilitate information-sharing for clinical care, research, and public health interventions that can further reduce health care disparities in this underserved population.

There are striking disparities in accessing health services that correlate with gender identity, as well as race/ethnicity and other factors. It is important to consider the intersecting identities and experiences of transgender and gender diverse people, to understand the cumulative discrimination and health inequities this community faces. Intersectionality is a framework for describing the disparities and culminating impact a person or group of people are affected by. Sex for Clinical Use (SFCU) and gender identity with other demographic data can be used to evaluate service utilization and health outcomes for subpopulations.

Currently, data resides in disparate systems with varying degrees of accuracy, preventing information from being used to support meaningful analysis, data visualization and insight generation. The goal is to not only answer questions but advance insights that drive action. Combining self-reported data from patients with clinical observations around the notions of gender and sex allows for rapid and efficient evaluations of emerging trends with more detail than might otherwise be possible. Creating opportunities for increased data analysis can contribute to new approaches to managing care, informing policy and future interventions.

## Modeling Sex and Gender Representation
The World Health Organization (WHO) defines Sex as the “different biological and physiological characteristics of males and females, such as reproductive organs, chromosomes, hormones, etcetera” and Gender as the “socially constructed characteristics of women and men, such as norms, roles, and relationships of and between groups of women and men” (WHO, 2020.) In clinical practice however, there can be a multiplicity of contextual variants over a single time horizon, across multiple applications and/or institutions where clinicians, vendors and interface developers have been grappling to create their own electronic ‘work around’ specification(s) to meet local and/or internal needs.

The gender-marginalized community has health care requirements that demand improvements that will benefit all patients. This document provides structural and semantic guidance to vendors and interface developers to address these requirements.

The proposed model provides necessary constructs to more accurately capture sex and gender along with associated context of use. This framework is the necessary infrastructure, but it does not provide the specific changes in individual standards that are needed to concretely specify actual implementable structures. That work must be undertaken within the responsible standards work groups such as HL7 v2, FHIR, DICOM, etc.

### Contextual Definitions of Sex and Gender Identity
Each of the following sections is structured to align with the UML Model categories noted in Figure 1. Each of the sub-sections below provides a definition, description, usage notes (if applicable), cardinality, and attributes (with recommended terminology if applicable) for each in-scope context definition.


Figure 1 Context Model for Gender Identity and Sex
#### Model Overview
The model introduces the attributes: Sex for Clinical Use (SFCU), Gender Identity, Recorded Sex or Gender, Pronouns, and Name to Use. These are attributes of a Person.

Gender Identity is provided to describe the identity or identities of the person. This is important in many social and cultural contexts. It might be missing, as for an infant, or multi-valued in some cultures and specific situations. The values are expected to reflect the variations found in different cultures and locations, so only a minimum value set is defined in the logical model. Local terminology may extend this value set. A partial list of possible extensions is available in [81].

The meaning, criteria, and implications of specific gender identities is defined by the local culture and society. This logical model does not specify meaning, criteria, or expected use of gender identity.

Sex For Clinical Use (SFCU) is provided for use in orders, observations, and other clinical uses. It can be highly contextual and allows specific considerations to be provided for potential automated uses and records. For example, a woman with polycystic ovary syndrome can be identified in a blood work order so that her unexpected hormone levels can be properly reported and not rejected as invalid results. A man with BRCA2 mutations can be identified so that a screening mammography order is properly performed. There are many other situations involving tumors, resections, congenital conditions (i.e., ovotestes), and transgender patients where SFCU can be used to provide information that is needed to perform a procedure properly. Many procedures need at least a “male” or “female” specification (e.g., for radiation shielding).  

An X-ray procedure to assess a possible broken arm is not affected by most sex-related characteristics. The SFCU will probably be chosen based on whether “male” or “female” radiation protection is appropriate for this patient, and no other unrelated patient characteristics need to be mentioned. In situations where there is no clinical impact, such as administrative activities, SFCU is not well defined and can be omitted. SFCU is not entirely new. Some medical communications protocols already accommodate a few specific characteristics, e.g., pregnancy status. SFCU provides a general extendable structure.

During the transition from old systems to new systems, and as medical technology and science evolve, the rules for SFCU selection and referenced clinical observations will change. This will usually be managed based on business partner agreements. Many current order fillers can only accept a single sex value and only understand certain clinical characteristics. This can be accommodated by the ordering system selecting the most appropriate SFCU and relevant observations. As technology changes these business rules may change, and the ordering systems are expected to accommodate changes to the order filling systems. The gender harmony model enables adaptation of old systems and new technologies.

In observations, SFCU is used to describe the specific contexts used in the observation. For example, the computation of glomerular filtration rate (GFR) based on blood chemistry uses formulas that are different for “male” and “female”. The SFCU for the GFR report can indicate which formula was used in the computation of that result. The expectation is that the patient level SFCU is the default value used in all observations in a report and have an individual SFCU for individual observations when that observation was performed using a different SFCU. This logical model does not cover the description of individual observations, but the SFCU attribute can be used.

Recorded Sex or Gender is provided to capture the possible sex or gender values that might be found in a medical record. These are typically from some sort of physical or electronic document that was provided to a medical provider. The rules for these documents have varied significantly over time and place, and the relationship to current Gender Identity or SFCU may be unclear. When a California driver’s license says “sex: X” or a birth certificate states “sex: male” this can be captured as a Recorded Sex or Gender element. The element includes source information so that the definition of “X” in a California driver’s license can be found if necessary. The Recorded Sex or Gender includes an internationally equivalent code to reduce the problems with unfamiliar sources. The original medical record source can provide an equivalent international code when it has one. Name to Use is included to improve the communications with the person. This is important in many situations. Some cultures have very long names, and expect that for all but mandatory legal situations, the person will use a more manageable name. When names are changed, whether for marriage or other reasons, there can be confusion. Different jurisdictions have different rules and processes for name changes, so there is often a mismatch that can be prolonged in difficult situations. The Name to Use enables care providers to use the name that is chosen by the person without needing to resolve complex administrative issues.

The (personal) pronoun is provided for the English speaking community. Use of the pronoun or pronouns chosen by the person is important for patient care and communications in English. The current logical model does not extend to other languages.

### Person
Definition: This is an abstract class to be mapped onto a concrete class in a specific standard or definition. The concrete class is expected to be a kind of person.
Usage Note: In FHIR a specific functional mapping might add attributes or modify existing attributes of the FHIR Patient Class. When used with standards that do not define classes, e.g., HL7 v2.x, this abstract Person class can be mapped into concrete changes to the standard.

Each of the Person sub-elements in the model describes a specific context of sex or gender information; in essence a sex and/or gender context type. Some of these types are multi-valued based in part on the need for independent, occasionally co-occurring, values that are specific to particular contexts of use within that type. The sensitivity of these situations heightens the importance of representing this data in a way that supports masking and access restrictions. The Sex for Clinical Use (SFCU) can also be affected by independent co-occurring contexts of use. Depending upon the procedure ordered, drug prescribed, or nature of a clinical report different SFCUs might be chosen. This can be reflected in the mapping chosen for a patient for specific clinical reasons. The medical record in an EHR system might have one set SFCU, and different specific selected SFCUs chosen for mapping to NCPDP for a drug prescription, to FHIR for an order, to HL7 v2.x for another order, and to DICOM for an imaging request. This will be especially common during the transition period when some systems have been upgraded and others have not.

The rules for these context dependent mappings are not defined in this abstract information model. They depend upon the concrete capabilities of the target system, and upon the specific clinical context at the time. It will be normal to find that when there are many objects related to a single patient (orders, reports, observations, etc.) that there are different SFCU due to differences in the context of use. Information about the context and reason for selection may be incorporated into the link to observations or reports that are part of the SFCU, or in the comment associated with Gender Identity.

### Gender Identity (GI)
Definition: An individual's personal sense of being a man, woman, boy, girl, nonbinary, or something else. This datum represents an individual’s identity, ascertained by asking them what that identity is.
Usage Note: If the Person (such as a fetus, infant, or uncommunicative new patient) is unable to express a personal sense of being a man, woman, boy, girl or any point on the gender spectrum, gender identity may be recorded as Unknown. Unknown can be used in cases where parents do not want to specify a value but one must be recorded. Gender identity can be congruent or incongruent with one’s “Sex for Clinical Use” or “Recorded Sex or Gender”. Persons may identify using different terms at different times for various reasons, or use multiple identities simultaneously, depending on culture. For example, a specific gender identity may be used in one care setting and a different identity in another care setting. The gender identity in the work environment may be different than that in a care setting.

Cardinality: 0..n
Attributes:
Gender
    Definition: See element Definition Cardinality 1..1
    Type: Code or constrained short text Proposed Terminology:
    minValueSet: GenderIdentity valueSet
    binding Strength: extensible
    See Appendix 1 — Proposed Value Sets for the recommended content.
Validity Period
    Definition: The time frame during which this gender identity applies to the person. May be just an initial dateTime.
    Usage note: Validity period may be overlapping in the case of multiple gender identities (such as for bigender persons, some genderfluid persons, and binary Two-Spirit persons who also identify as male or female).
    Cardinality: 0..1
    Type: duration or datetime
Comment
    Definition: Text to further explain the use of the specified gender identity or identities. Usage note: Content included may be related to social and/or cultural context to be considered when using the gender identity, particularly with overlapping active values. Cardinality: 0..1
    Type: long text