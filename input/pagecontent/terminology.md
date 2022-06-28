# **8. Terminology**
Medical terminology and standards, as core parts of medical systems, are necessarily omnipresent in today’s biomedical landscape. They form an important cornerstone of almost all digital health technology utilized today around the world. However, despite their increasing importance to health care, medical terminology and standards rarely consider the ethical implications surrounding their existence. Many communities have been adversely affected by this lack of consideration, which this document hopes to partially address in relationship to sex and gender in such systems, with a worldwide perspective.
## **8.1 Code Systems**
### **8.1.2 Code System 1**
### **8.1.3 Code System 2**
## **8.2 Value Sets**
What follows are recommendations for value sets and their approximate meanings in relationship to their usage. Each set is split into an entity (such as “Sex for Clinical Use”) and an attribute within that entity (such as “Sex Category”). Entities and attributes are presented in alphabetical order.

Each section contains three parts: (1) an introduction, (2) a table of required value names, descriptions, and example code systems, and (3) further considerations. For some entity/attribute pairs, the section of further considerations will include an example table of extensible values to consider within given jurisdictions.
### **Use of Multiplicity and Extensibility in the Gender Harmony Model**
Many attributes defined in the Gender Harmony model make use of multiplicity and have required and/or extensible value sets. These concepts are formally defined in <REF TBD>. The impact of these mechanisms on implementations is discussed in this section in brief bulleted lists for convenience.
#### *Multiplicity*
- All attributes might be fully missing. This is fundamentally different than an attribute being present with a specific *null* value. An unidentified trauma patient is one possible cause of such missing attributes; for instance, the Gender Identity entity of such a patient cannot be apprehended when a patient is in such a state.
- Attributes or entire entities may be inapplicable, also meaning that all attributes might be fully missing. For example, in a location in which the local language or the language of the health care system does not utilize pronouns, the Pronouns to Use entity cannot be apprehended and is therefore missing.
- There may be multiple values for attributes simultaneously and across time. For example, it is not unheard of for a person to use two pronoun sets. They may use he/him and they/them pronouns and select both as appropriate and acceptable. Such an individual would have two Pronoun Sets indicated.
#### *Required and Extensible Value Sets*
- Required Value Sets
  - The value set for Sex for Clinical Use (SFCU) is bound required. This means that value must be chosen from one of those on the list provided in the value set. The list does not contain an “other” or “something else” value.
  - Instead of utilizing “other” or “something else”, SFCU has a Specified option, which is expected to be accompanied by comments and/or references to observations which explain why neither “male” nor “female” are appropriate.
  - “Unknown” occurs for a situation in which there are not sufficient observations to make any determination. This is an *affirmative* statement, so that the recipient and user of this information know that a sender/creator has looked at the data available to them before making this selection. This allows the recipient to decide on a further course of action, which may include searching for observations or simply proceeding with the available data.
- Extensible Value Sets
  - The value sets for other attributes, such as Pronoun Set within the Pronouns to Use entity or Gender within the Gender Identity entity are bound extensible. This means that the value set can be extended by local, regional, or national policy, but that it must contain the minimum required values.
  - Some policies may permit patients to add patient-specified values through mechanisms such as free-text. Systems should be prepared to handle values of this type or other added values, although the Gender Harmony model itself does not specify how extended values created in one system should be received by another.
  - The Gender attribute in the Gender Identity entity is expected to be locally extended. The minimum required value set is shorter for this reason, containing only four values that are generally well-known worldwide. There are many culturally-specific gender identities known around the world, which may be defined and added in appropriate jurisdictions.
  - The Gender Harmony model does not specify how extension of the coding system can take place, but does note values of interest below. Extensions could use existing coding systems like SNOMED and LOINC, or define their own jurisdictionally-specific systems. However, for the sake of interoperability, an already defined method for extension should be utilized where possible.
### **Entity: Gender Identity, Attribute: Gender**
#### *Introduction*
The attribute Gender in the entity Gender Identity has a minimum value set which is extensible. This extensibility will allow specific implementations the option to add more choices via an expanded value set that incorporates the minimum set. Further discussion of how this is operationalized is include in… [TO ADD]

GenderIdentity value set to be used as a minimum value set, that is extensible to allow specific implementations the option to add more choices via an expanded value set that incorporates this minimum set.
#### *Required Value Names, Descriptions, and Example Code Systems*

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Female|A person’s self-identification as a woman, as female, or as a girl.|<p>LA22879-3 [LOINC]</p><p>Identifies as female gender, 446141000124107 [SNOMED CT]</p><p>female gender identity, GSSO:000089 [GSSO]</p>|
|Male|A person’s self-identification as a man, as male, or as a boy.|<p>LA22878-5 [LOINC]</p><p>Identifies as male gender, 446151000124109 [SNOMED CT]</p><p>male gender identity, GSSO:000090 [GSSO]</p>|
|Nonbinary|Having a specific identity which is nonbinary (not within a binary construct of male or female) or having an identity which falls under the nonbinary umbrella (i.e., any or all gender identities which are not female or male).|<p>Identifies as nonbinary gender, 33791000087105 [SNOMED CT]</p><p>nonbinary gender identity, GSSO:002328 [GSSO]</p>|
|Unknown|The person’s gender identity is not known at this time, for any of a variety of reasons. (e.g., “was not able to ask” or “person does not want to answer”.)|<p>nullFlavor UNK [HL7]</p><p>Unknown, 261665006 [SNOMED CT]</p><p>unknown gender identity, GSSO:009482 [GSSO]</p>|
#### *Further Considerations*
HL7’s nullFlavor can be useful in a number of situations for Gender Identity, outside of nullFlavor UNK [unknown]. Some of these situations are summarized below. Underneath each value name are value names known to be utilized in other systems.

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Masked|Information is available but has not been provided for security or privacy reasons. For instance, an individual may present a different gender identity in a space considered to be unknown or dangerous. Their actual gender identity could be masked in a situation like this. Additionally, some gender identities might not be used very often, and could therefore potentially lead to identifying an individual, compromising their privacy. A masked value could also be used to help prevent such a situation.|nullFlavor MSK [HL7]|
|<p>Something else</p><p>- Additional gender identity</p><p>- Another gender identity</p><p>- Another gender identity not listed</p><p>- Gender identity not listed above</p><p>- Gender identity not listed here</p><p>- Gender not listed</p>|The gender identity provided exists beyond any utilized code system. In these cases, plain-text should be provided. Avoid using “other” as much as possible.|<p>nullFlavor OTH [HL7]</p><p>GSSO:009484 [GSSO]</p>|
|<p>Not applicable</p><p>- No gender identity</p>|Having no proper value for gender identity. For instance, a biological specimen (cells, tissue, etc.) does not have a gender identity. Most psychiatrists and psychologists agree that gender identity forms between the ages of 4 and 7, so before that time “Not applicable” would be used.|<p>nullFlavor NA [HL7]</p><p>GSSO:009485 [GSSO]</p><p></p>|
|<p>Asked but unknown</p><p>- Chose not to answer</p><p>- Does not understand the question</p><p>- Gender identity not disclosed</p><p>- Non-disclosed</p><p>- Person prefers not to say</p><p>- Prefer not to answer</p><p>- Prefer not to respond</p><p>- Prefer not to say</p><p>- Undisclosed</p><p>- Unsure</p>|Used in situations where a gender identity was sought but not found. For instance, if a patient doesn’t understand the question. Do NOT use this value to indicate if an individual is questioning or exploring their gender identity. Another example would be if an individual decides to not disclose their gender identity.|nullFlavor ASKU [HL7]|
|Temporarily unavailable|An individual’s gender identity is not available at the time but is expected later. For instance, if an individual is unconscious (but is expected to become conscious), their gender identity cannot be obtained.|nullFlavor NAV [HL7]|
|<p>Not asked</p><p>- Inappropriate to ask</p><p>- Not appropriate to ask</p>|An individual has not been asked about their gender identity or that information has not otherwise been sought in any form.|nullFlavor NASK [HL7]|
|<p>Not available</p><p>- Gender identity inadequately described</p><p>- Inadequately described</p>|An individual’s gender identity is not available at the time, and there is no expectation that it will ever be available. Such a determination could be used if an individual has died and their gender identity has not been ascertained. Could also be used in situations wherein an individual has tried to update from one system to another, and the previous system’s usage of gender (identity) is uncertain or inadequate.|nullFlavor NAVU [HL7]|
|<p>Not present</p><p>- Gender identity not provided</p><p>- Not provided</p>|Used only in messages to indicate that a value is not present.|nullFlavor NP [HL7]|
In addition to these values, we highly recommend the following, if appropriate:

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Exploring or questioning gender identity|Indicating that one is exploring or questioning their gender identity can be helpful for providers, and may be a safer label for those who have just recently started thinking about their own gender process.|GSSO:001594 [GSSO]|
|<p>I do not understand the question</p><p>- I don’t understand</p><p>- I don’t know</p>|An individual does not understand the gender identity question as phrase, for any of various reasons (language barrier, for instance).|*None at present time*.|
In situations where many LGBTQIA+ patients are expected and more granularity is wanted, some of the following emergent gender identities may be considered. Below we include some of the more commonly known such identities, as of Spring 2022. However, this section is by no means exhaustive, and names and conceptualizations of various identities will shift over time, potentially meaning that some emergent terms might be missing while others have become obsoleted. For instance, the Gender Wiki lists [over 300 gender identities](https://gender.fandom.com/wiki/Category:Gender_Identities), the Nonbinary Wiki lists [over 100 more common gender identities](https://nonbinary.wiki/wiki/Category:Nonbinary_identities) which fall underneath the nonbinary umbrella, and the MOGAI Gender Wiki lists [over 200 gender identities](https://mogai-genders.fandom.com/wiki/Category:Gender). For trends regarding identity terms, many of which are gender identities, we recommend accessing the [Gender Census](https://gendercensus.com/), the 2021 version of included 44,583 usable responses. We utilized trends across the Gender Census in determining which identities to explicitly include below.

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Agender|Attested as a gender identity since the late 1990s. Considered by most to be a lack of gender identity, or synonymous with genderless, non-gendered, or ungendered.|<p>GSSO:002342 [GSSO]</p><p>HOMOIT:0001927 [Homosaurus]</p>|
|Androgyne|Term which has been utilized to describe gender nonconforming and intersex persons for centuries. By the late 19th and early 20th century, the term was used mostly to describe gay men who were considered to be feminine. By the 1980s, some transgender persons began using the term as a gender identity which have masculine and feminine components. Today, the term is seen as falling under the nonbinary umbrella, being simultaneously masculine and feminine, male and female.|GSSO:000404 [GSSO]|
|Bigender|First defined the 1980s, often to refer to persons who were “dual-gendered”, both male and female. Although many bigender people today still identify as both male and female, many others use various other gender identities: for instance, a person could be both female and nonbinary, or demigender and neutrois, and still be bigender.|<p>GSSO:002336 [GSSO]</p><p>HOMOIT:0000110 [Homosaurus]</p>|
|Demigender|Defined in the early 2010s as an umbrella term and an identity itself, representing a gender identity which is partially aligned with another gender identity. For instance, an individual who is a demiboy may consider themselves to be partially aligned with a male gender identity.|<p>GSSO:002341 [GSSO]</p><p>HOMOIT:0001923 [Homosaurus]</p>|
|Genderfluid|Although the concept of gender fluidity has existed for nearly a half century, the concept of genderfluid as a gender identity solidified in the 1990s, becoming increasingly popular in the 2000s and 2010s, representing an identity in which an individual experiences different identities as different times, which may or may not be contingent on a number of select factors.|<p>GSSO:002339 [GSSO]</p><p>HOMOIT:0000569 [Homosaurus]</p>|
|Intergender|Defined in the 1990s as an “in-between” gender identity, typically defined as being between male and female. In the 2000s and 2010s, the term became known as a more exclusive gender identity meant to be utilized only by intersex persons; its usage by non-intersex (endosex *or* perisex) is considered derogatory.|GSSO:002335 [GSSO]|
|Multigender|An umbrella term and specific identity which was named in the late 2000s or early 2010s, used to refer to gender identities in which more than one identity is experienced, usually at the same time.|GSSO:002330 [GSSO]|
|Neutral|Also known as *gender neutral* or *neutral gender*, being both an umbrella term for gender identities considered to be neutral in nature or a specific gender identity of such a nature, which may also be described as agender, genderless, having no gender identity, or having a gender identity between others. While the term has been present for decades, its usage as a gender identity likely began in the 1980s or 1990s.|GSSO:002334 [GSSO]|
|Neutrois|A gender identity coined in the 1990s which is considered to be similar to, if not nearly identical to, a neutral gender identity.|GSSO:002340 [GSSO]|
|Pangender|A multigender identity in which an individual identifies with a seemingly countless number of separate identities or as a seemingly all-encompassing gender identity, although usually discounting culturally-specific gender identities. The term likely came to exist in the 2000s or 2010s.|<p>GSSO:007680 [GSSO]</p><p>HOMOIT:0001071 [Homosaurus]</p>|
|Polygender|A multigender identity which typically includes more than two genders, therefore not including bigender persons. The term was likely coined in the late 1990s in English.|GSSO:002338 [GSSO]|
|Trigender|A rarer multigender identity which typically includes three genders; the term likely came to exist in the late 1990s.|<p>GSSO:002337 [GSSO]</p><p>HOMOIT:0001473 [Homosaurus]</p>|
When additional codes and terms appropriate to specific jurisdictions, locations, and potentially individual persons are needed, an additional value or values should be created that add in the additional concepts. Such values are informally referred to as *culturally-specific gender identities*.

Implementations should be prepared for the addition of other specific gender identities at specific locations. Implementations should be prepared to receive messages or records that contain unrecognized terms. Local policy will establish how to handle unrecognized terms, most likely by preserving the term. Examples of gender identity extensions are given in the non-normative table shown below, with the caveat that this work is produced from an Anglospheric perspective, and that local implementors of these communities may utilize these entities in different ways.

For instance, many of communities do not differentiate between sexual identity and gender identity, and these terms are implicitly combined. More research is necessary in many of these situations in order to effectively prevent miscommunication, but performing such research is beyond the scope of the current report. Note that the following list is scoped and only includes identities attested to be in use in the last century.

|<p>**Transliterated Value Name**</p><p>**(Name in Original Language, if Different)**</p>|<p>**Jurisdiction** </p><p>**(Ethnic or Cultural Group)**</p>|**Description**|**Example Code System**|
| :-: | :-: | :-: | :-: |
|Agule|Uganda, Democratic Republic of the Congo, South Sudan (Lugbara)|First attested in English literature in the 1960s; was originally translated as “like a man”, but has more recently been translated as transmasculine or as trans man.|GSSO:002164 [GSSO]|
|‘Akava’ine|Cook Islands (Cook Islands Māori)|Term attested in English literature since the 1990s in the Cook Islands. Combines the prefix “aka” (‘to be or to behave like’) with “va’ine” (‘woman’). Used originally as a term of insult toward cis women, but now used to refer to Cook Islanders who may be considered trans women.|<p>GSSO:002163 [GSSO]</p><p>HOMOIT:0000035 [Homosaurus]</p>|
|Aravani (Arabic: أرافاني, Marathi: अरावनी, Tamil: அரவாணி)|India (Tamilar)|Term attested in English literature since its coinage in 2008 in Tamil Nadu, India. Some literature compares the term to hijra, some compare it to the term trans woman, and others note it as its own specific conceptualization. More recently (in the 2010s), the term thirunangai was coined as a more inclusive and respectful term, although it has been noted that some individuals in Chennai still use aravani as a term of identification.|<p>GSSO:006194 [GSSO]</p><p>HOMOIT:0000065 [Homosaurus]</p>|
|Āshitimē (Maale: አሽትሜ)|Ethiopia (Maale)||<p>GSSO:002166 [GSSO]</p><p>HOMOIT:0000072 [Homosaurus]</p>|
|Baklâ|Philippines||<p>GSSO:002189 [GSSO]</p><p>HOMOIT:0000091 [Homosaurus]</p>|
|Basaja|Indonesia (Toraja)|||
|Basir|Indonesia (Ngaju)|||
|Bissu|Indonesia (Makassar)||<p>GSSO:007858 [GSSO]</p><p>HOMOIT:0000205 [Homosaurus]</p>|
|Biza’ah|Mexico (Zapotec)||<p>GSSO:002047 [GSSO]</p><p>HOMOIT:0000207 [Homosaurus]</p>|
|Brotherboy|Australia (Indigenous Australians)||<p>GSSO:002300 [GSSO]</p><p>HOMOIT:0000224 [Homosaurus]</p>|
|Calabai|||<p>GSSO:007859 [GSSO]</p><p>HOMOIT:0000234 [Homosaurus]</p>|
|Calalai|||<p>GSSO:007860 [GSSO]</p><p>HOMOIT:0000235 [Homosaurus]</p>|
|Fa’afāfine|American Samoa, Samoa (Samoans)||<p>GSSO:002302 [GSSO]</p><p>HOMOIT:0000413 [Homosaurus]</p>|
|Fa’atama|American Samoa, Samoa (Samoans)||<p>GSSO:008117 [GSSO]</p><p>HOMOIT:0000414 [Homosaurus]</p>|
|Fakafāfine|Tokelau (Tokelauans)||GSSO:011272 [GSSO]|
|Fakaleitī|Tonga (Tongans)||<p>GSSO:002303 [GSSO]</p><p>HOMOIT:0000419 [Homosaurus]</p>|
|Femminiello|Italy (Neapolitans)||<p>GSSO:002304 [GSSO]</p><p>HOMOIT:0000441 [Homosaurus]</p>|
|Hijra (Hindi: हिजड़ा)|India (Indians)|Term attested in English literature since the early 1800s. Hijra usually refers to a very specific cultural role with gendered connotations. People who are hijra are almost always those who would be considered assigned male at birth (AMAB), although many are intersex and some may be assigned female at birth (AFAB). Hijra typically live in communities called gharanas. Some hijra consider themselves to be transgender, although many do not. The term hijra is often considered to be offensive in Urdu, so the term khwaja sira is preferred in Urdu-speaking parts of India, as well as in Pakistan and Bangladesh.|<p>GSSO:002305 [GSSO]</p><p>HOMOIT:0000632 [Homosaurus]</p>|
|Isángoma|South Africa, Lesotho, Zimbabwe, Eswatini, Malawi, Botswana, Mozambique (Zulu)|||
|Jogappa (Hindi: जोगप्पा)||Attested in English literature since the 1980s. Individuals become jogappa through a ceremony known as Kādāta.|<p>GSSO:007861 [GSSO]</p><p>HOMOIT:0000684 [Homosaurus]</p>|
|Jogata (Hindi: जोगतास)||||
|Kathoey (Thai: กะเทย, Lao: ກະເທີຍ)|Thailand (Thais)|Thai and Lao term which derives from the Khmer pejorative ខ្ទើយ. Attested in English literature since the 1990s.|GSSO:002306 [GSSO]|
|Khanith (Arabic: خنيث)|Oman (Omanis)|Attested in English literature since the 1970s.|<p>GSSO:002307 [GSSO]</p><p>HOMOIT:0001517 [Homosaurus]</p>|
|Khasua (Hindi: खसुआ)|||GSSO:011932 [GSSO]|
|Khusara (Hindi: खुसरा)|India||GSSO:011931 [GSSO]|
|Khusra (Arabic: خوسرا, Punjabi: ਖੁਸਰਾ)|India, Pakistan||GSSO:007870 [GSSO]|
|Khwaja sira (Urdu: خواجه سرا)|Pakistan (Pakistanis), Bangladesh (Bengalis)|Polite alternative to hijra in Urdu. Recommended for usage in Pakistan and Bangladesh over using hijra.|<p>GSSO:006199 [GSSO]</p><p>HOMOIT:0000689 [Homosaurus]</p>|
|Kinnar|India||<p>GSSO:006190 [GSSO]</p><p>HOMOIT:0000690 [Homosaurus]</p>|
|Kothi (Hindi: कोथी)|India (Indians), Nepal (Nepalis), Pakistan (Pakistanis)||<p>GSSO:002309 [GSSO]</p><p>HOMOIT:0000694 [Homosaurus]</p>|
|Laelae|Cook Islands (Cook Islands Māori)|Attested in English literature since the 1990s; used to refer to individuals who may be considered to be assigned male at birth who is considered to be feminine to some degree.||
|Māhū|Hawaii (Kanaka Maoli), Tahiti (Maohi)||<p>GSSO:002320 [GSSO]</p><p>HOMOIT:0000979 [Homosaurus]</p>|
|Māhū kāne|Hawaii (Kanaka Maoli), Tahiti (Maohi)|Kanaka Maoli term coined in the early 2000s, meant to represent the specific experiences of Kanaka Maoli trans men.||
|Māhūwahine|Hawaii (Kanaka Maoli), Tahiti (Maohi)|Kanaka Maoli term coined in the early 2000s, meant to represent the specific experiences of Kanaka Maoli trans women.||
|Mak nyah|Singapore (Singaporeans)||<p>GSSO:007930 [GSSO]</p><p>HOMOIT:0000980 [Homosaurus]</p>|
|Manang bali|Indonesia (Iban)|||
|Mangaiko|Democratic Republic of the Congo (Mbo)||<p>GSSO:007928 [GSSO]</p><p>HOMOIT:0000987 [Homosaurus]</p>|
|Muxe|Mexico (Zapotec)||HOMOIT:0001034 [Homosaurus]|
|Okule|Uganda, Democratic Republic of the Congo, South Sudan (Lugbara)|||
|Omegiid|Panama (Guna)|||
|Palao’ana|Guam, Northern Mariana Islands (Chamorro)||<p>GSSO:002321 [GSSO]</p><p>HOMOIT:0001070 [Homosaurus]</p>|
|Palopa|Tuvalu (Tuvaluans)||GSSO:010335 [GSSO]|
|Rae rae|Tahiti (Maohi)||GSSO:002323 [GSSO]|
|Sekrata|Madagascar (Sakalava)||<p>GSSO:008113 [GSSO]</p><p>HOMOIT:0001264 [Homosaurus]</p>|
|Sistergirl|Australia (Indigenous Australians)||<p>GSSO:002301 [GSSO]</p><p>HOMOIT:0001314 [Homosaurus]</p>|
|Thirunangai (Tamil: திருநங்கை)|India (Tamilar)|Term coined in the 2010s to be a more respectful version of aravani in Tamil Nadu. Thirunangai have been said to be hijra, trans women, or as its own designation by various sources.||
|Travesti|Argentina (Argentines), Brazil (Brazilians), Peru (Peruvians)|Romance language term (Spanish, Portuguese, Italian, etc.) often considered a transphobic slur today, although the term has been reclaimed by some in some regions of Central and South America.|<p>GSSO:002324 [GSSO]</p><p>HOMOIT:0001471 [Homosaurus]</p>|
|Tutuva’ine|Cook Islands (Cook Islands Māori)|Term attested in English literature in the early 2000s, meaning “like a woman”; today used to refer to individuals who may be considered male-to-female cross-dressers or drag queens.||
|Tututane|Cook Islands (Cook Islands Māori)|Term attested in English literature in the early 2000s, meaning “like a man”; today used to refer to individuals who may be considered female-to-male cross-dressers or drag kings.||
|Two-Spirit|North America, Central America (Native Americans, First Nations)||<p>GSSO:007398 [GSSO]</p><p>HOMOIT:0001914 [Homosaurus]</p>|
|Two-Spirit|Australia, New Zealand||GSSO:011273 [GSSO]|
|Vakasalewalewa|Fiji (Fijians)||GSSO:010334 [GSSO]|
|Wakatane|New Zealand (Māori)||<p>GSSO:007720 [GSSO]</p><p>HOMOIT:0001499 [Homosaurus]</p>|
|Waria|Indonesia (Indonesians)||<p>GSSO:002325 [GSSO]</p><p>HOMOIT:0001501 [Homosaurus]</p>|
|Whakawāhine|New Zealand (Māori)||<p>GSSO:007721 [GSSO]</p><p>HOMOIT:0001502 [Homosaurus]</p>|
|X-gender (Ｘじぇんだー)|Japan (Japanese)|Japanese neologism known in English literature since the 1990s; considered to be similar in some ways to English terms like “genderqueer” and “nonbinary”.|GSSO:002327 [GSSO]|
Note that terms like “MTF”, “FTM”, “male-to-female transsexual”, and “female-to-male transsexual”, etc. were not included. [Kronk noted in an article with 16 other trans authors](https://doi.org/10.1093/jamia/ocab136) in various health care fields that “[t]hese options are antiquated and problematic. The first two (FTM and MTF) have largely fallen out of use among transgender people and in transgender-related literature because they fundamentally assume a ‘change’ in gender—that a transgender person was ‘female’ and now is ‘male’ (FTM), usually due to, or following, some sort of medicalization process (hormone replacement therapy and/or gender affirming surgery, for instance) [91,92,93,94,95]. This contradicts how many trans people understand their identity and can confuse patients. All four terms center cisgender people, reserving unqualified ‘male’ and ‘female’ for them while trans people are segregated into the separate, qualified categories of ‘MTF’, ‘FTM’, ‘transgender male’, ‘transgender female’, and ‘transgender’. Fundamentally, this implies trans women and trans men are deviant and not actually female or male, respectively, especially when the selection is ordered as “male”, “female”, “MTF”, “FTM” [96,97,98]. Further, by separating these groups in the first place, “male” and “female” are presented as the norm while “transgender male” and “transgender female” are othered [96,97,98,99,100]. The separation can insinuate that transgender people are not their stated gender and that separation is cited heavily in transphobic and exclusionary actions [101,102,103]”. In practice, many transgender persons would answer “male” or “female” over “transgender male” or “transgender female”.

When a person is transgender, intersex, and/or gender-diverse, this is noted by an incongruence between a gender identity datum and a sex for clinical use datum (or data). The specific incongruence can be noted using the Comment and Linked Clinical Observation.
### **Entity: Pronouns to Use, Attribute: Pronoun Set**
#### *Introduction*
The attribute Pronoun Set in the entity Pronouns to Use has a minimum value set which is extensible. At the time of writing, information regarding non-English pronoun set systems was not well represented in the HL7 Gender Harmony Project group. Therefore, only English-language pronoun sets are provided in the minimum value set for the time being, for use in Anglosphere countries (the United States, the United Kingdom, Canada, Australia, New Zealand, etc.). However, in further considerations, we will list some potential options to consider in future work outside of the Anglosphere, which could potentially be adopted in other jurisdictions with more representation from those jurisdictions.

English-language pronoun sets are shown in the following order for the purposes of declination:

- Subject pronoun (Example: “**She** went to the park.”)
- Object pronoun (Example: “I went with **her**.”)
- Possessive determiner (Example: “She** brought **her** frisbee.”)
- Possessive pronoun (Example: “At least I think it was **hers**.”)
- Reflexive (Example: “She threw the frisbee to **herself**.”)

Individual forms are separated by commas (“,”) because some pronoun sets include the “/” character within them, which would make programmatic parsing more difficult.

Individuals may use more than one set of pronouns at the same time. For instance, an individual may use she/her pronouns and they/them pronouns (often represented as she/they). In this case, the individual would select both “she, her, her, hers, herself” and “they, them, their, theirs, themselves”. This is why the cardinality of pronouns is 0..*n*.

The primary code system utilized is a subset of the LOINC answer list for Personal Pronouns - Reported, LL5144-2 Personal pronouns / Answers: 10; Scale: Nom; Code: -; Score: -.
#### *Required Value Names, Descriptions, and Example Code Systems*

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|he, him, his, his, himself|English-language pronouns usually associated with masculinity and/or maleness, that are to be used to refer to the person who uses them.|<p>LA29518-0 [LOINC]</p><p>GSSO:010399 [GSSO]</p>|
|she, her, her, hers, herself|English-language pronouns usually associated with femininity and/or femaleness, that are to be used to refer to the person who uses them.|<p>LA29519-8 [LOINC]</p><p>GSSO:010398 [GSSO]</p>|
|they, them, their, theirs, themself|Epicene English-language pronouns usually considered gender-neutral and/or gender-expansive, that are to be used to refer to the person who uses them.|<p>LA29520-6 [LOINC]</p><p>GSSO:011490 [GSSO]</p>|
|unknown||<p>nullFlavor UNK [HL7]</p><p>Unknown, 261665006 [SNOMED CT]</p>|
#### *Further Considerations*
[additional nullFlavor options]

A number of English neopronouns (neologistic pronouns) exist in addition to the English paleopronouns (paleologistic pronouns) included previously. A few of these are shown below.

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|co, co, cos, cos, coself||<p>LA29515-6 [LOINC]</p><p>GSSO:011647 [GSSO]</p>|
|en, en, ens, ens, enself||LA29516-4 [LOINC]|
|ey, em, eir, eirs, emself||<p>LA29517-2 [LOINC]</p><p>GSSO:011577 [GSSO]</p>|
|ve, vis, ver, ver, verself||LA29524-8 [LOINC]|
|xie, hir, hir, hirs, hirself||LA29521-4 [LOINC]|
|yo, yo, yos, yos, yoself||<p>LA29522-2 [LOINC]</p><p>GSSO:011555 [GSSO]</p>|
|ze, zir, zir, zirs, zirself||<p>LA29523-0 [LOINC]</p><p>GSSO:011556 [GSSO]</p>|
Several other languages which use gendered pronouns should also consider constructing similar structures in their electronic health records. However, they should never automatically map pronouns in one language to pronouns in another language, as the connotations involved as language specific. A few potential examples to consider are included below in some languages, but these are not meant to be exhaustive, and should only be implemented with appropriate jurisdictional feedback. The sets are derived from the respective pages in [Pronouns.page](https://pronouns.page/).

|**Value Name (German)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|sie, ihr|||
|er, ihm|||
|es, ihm|||
|dey, denen|||
|die, denen|||
|el, em|||
|em, em|||
|en, en|||
|en, em|||
|et, siem|||
|ey, emm|||
|hän, sim|||
|hen, hem|||
|hie, hiem|||
|iks, iks|||
|ind, inde|||
|nin, nim|||
|oj, ojm|||
|per, per|||
|ser, sem|||
|sier, siem|||
|they, them|||
|xier, xiem|||
|zet, zerm|||
|ersie, ihmihr|||


|**Value Name (Spanish)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|ella, la|||
|él, lo|||
|elle, le|||
|ellu, lu|||
|elli, li|||
|elloa, loa|||
|il, li|||
|ól, ol|||
|xelle, le|||


|**Value Name (French)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|iel, lea|||
|al, lea|||
|ael, lea|||
|el, lea|||
|em, lea|||
|ielle, lea|||
|ille, lea|||
|im, lea|||
|ol, lo|||
|ul, lu|||
|yel, lea|||
|yelle, lea|||


|**Value Name (Dutch)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|zij, haar, haar|||
|hij, hem, zijn|||
|hen, hen, hun|||
|hen, hun, hun|||
|die, hen, hun|||
|hen, hen, hens|||
|die, die, diens|||
|dee, dem, dijr|||
|dij, dem, dijr|||
|nij, ner, nijr|||
|vij, vijn, vijns|||
|vij, her, zaar|||
|zhij, zhaar, zhaar|||
|zem, zeer, zeer|||


|**Value Name (Bokmål)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|han, ham|||
|hun, henne|||
|hen, hens|||
|hin, hins|||


|**Value Name (Polish)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|ona, jej|||
|on, jego|||
|onu, jenu|||
|onu, jejo|||
|ne, nego|||
|onu, jegu|||


|**Value Name (Portuguese)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|a, ela, a|||
|o, ele, o|||
|ê, elu, e|||
|ê, ilu, e|||
|ê, ile, e|||
|ê, el, e|||
|i, ili, i|||
|ê, ily, e|||
|ê, éli, e|||
|ê, elé, e|||
|i, ilo, i|||
|ê, êlu, e|||
|y, yn, y|||
|y, ale, y|||
|ae, ael, e|||
|ae, elae, e|||


|<p>**Value Name** </p><p>**(Mandarin Chinese)**</p>|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|他, 你|||
|她, 你|||
|她, 妳|||
|tā, 你|||
|X也, 你|||
|无也, 你|||
|ㄊㄚ, 你|||

### **Entity: Recorded Sex or Gender, Attribute: Source Recorded Sex or Gender**
#### *Introduction*
The attribute Source Recorded Sex or Gender in the entity Recorded Sex or Gender has no minimum value set, due primarily to linguistic differences between regions. This section will review some of those differences for various jurisdictions to consider.
#### *Required Value Names, Descriptions, and Example Code Systems*
There are no required value names, descriptions, or example code systems for the attribute Source Recorded Sex or Gender. For examples of some values utilized herein, see further considerations.
#### *Further Considerations*
While international standards (see “Entity: Recorded Sex or Gender, Attribute: International Equivalent Recorded Sex or Gender”) typically utilize ‘M’, ‘F’, or ‘X’, other sources provide a much wider array of potential jurisdictional values which may provide more specific and necessary information. A table of some of the observed values is shown below. Note than inclusion of jurisdiction is necessary, as different jurisdictions may use different definitions for the same value. Note that this table is non-exhaustive.

|**Source Value**|**International Equivalent**|**Description**|**Example Documents**|**Example Jurisdictions**|
| :-: | :-: | :-: | :-: | :-: |
|[blank]|X|Reportedly interpreted as “indeterminate” in the German context.|Birth certificates|Argentina; Germany; United States (California, Minnesota)|
|-- [two dashes]|X||Birth certificates|United States (California)|
|divers|X|Meaning “diverse”.|Birth certificates|Austria; Germany|
|E|X|Meaning “eunuch”.|Passports|India|
|F|F|Meaning “female”.|National identity cards; Passports; Vehicular licenses|Belgium; Netherlands|
|Female|F||Birth certificates|United States (Connecticut)|
|female|F||||
|female (khwaja sira)|F *or* X?||National identity cards|Pakistan|
|INTERSEX|X||Birth certificates|United States (Colorado)|
|K|M|Meaning “male”.|Passports|Azerbaijan|
|khunsā-e-mushkil|X||National identity cards|Pakistan|
|M|M|Meaning “male”.|Passports; Vehicular licenses|Argentina; Australia; India; New Zealand; United States|
|Male|M||Birth certificates|United States (Connecticut)|
|male|M||||
|male (khwaja sira)|M *or* X?||National identity cards|Pakistan|
|NB|X|Meaning “no binario” (non-binary).|Birth certificates|Mexico|
|No binario|X||Birth certificates|Argentina|
|Non-Binary|X||Birth certificates|United States (Connecticut)|
|non-binary|X||||
|nonbinary|X||||
|not yet determined|X||Birth certificates|United States (New Jersey, New Mexico)|
|O|X|Meaning “other”.|Passports|Nepal|
|U|X|Meaning “undetermined”, “unspecified”, or “unknown”.|Birth certificates; Provincial health cards|Canada (British Columbia); United States (Oregon)|
|Unknown|X||Birth certificates|United States (Washington, DC)|
|Ա|M|Meaning “Արական” (“male”).|Passports|Armenia|
|V|F|Meaning “vrouwelijk” (“female”).|National identity cards|Netherlands|
|W|F|Meaning “weiblich” (“female”).|National identity cards|Belgium|
|X|X||Birth certificates; Passports; Vehicular licenses|Argentina; Australia; Austria; Iceland; Netherlands; New Zealand; Pakistan; United States (Arkansas, California, Colorado, Connecticut, Hawaii, Illinois, Maine, Michigan, Nevada, New Jersey, New Mexico, New York, Ohio, Oregon, Pennsylvania Rhode Island, Utah, Washington)|

### **Entity: Recorded Sex or Gender, Attribute: International Equivalent Recorded Sex or Gender**
#### *Introduction*
The attribute International Equivalent Recorded Sex or Gender in the entity Recorded Sex or Gender has a required minimum value set in order to facilitate communication between regions or jurisdictions which use different values for the attribute Source Recorded Sex or Gender in the entity Recorded Sex or Gender.

In order to develop this set, we reviewed all international documentation related to Recorded Sex or Gender. “Sex” or “Gender” (as it appears in passport documents) was the only entity found which sufficiently fulfilled these criteria. For that reason, our minimum value set derives from two International Civil Aviation Organization (ICAO) documents, being Doc 9303: Machine Readable Travel Documents, Seventh Edition (2015), Part 7: Machine Readable Visas and Doc 9303: Machine Readable Travel Documents, Eighth Edition (2021), Part 7: Machine Readable Visas.

As defined in those documents, “Sex” is representative of the “[s]ex of MRV-A holder, when included, is to be specified by use of the single initial commonly used in the language of the State of issue. If translation into English, French or Spanish is necessary, followed by an oblique and the capital letter F for female, M for male, or X for unspecified.” However, when the data structure is clarified later in the document it is noted that “F = Female; M = Male; < = non-specified”. This discrepancy is noted in with the following in the 2021 edition: “Where an issuing State or organization does not want to identify the sex, the filler character (<) shall be used in this field in the MRZ and an X in this field in the VIZ.” This effectively means that ‘X’ and ‘<’ are equivalent, with ‘X’ appearing on the “front-end” and ‘<’ appearing on the “back-end”.

However, it is important to note that this system does not include a value that is *unknown*. We recommend that nullFlavor UNK [HL7] be used for that purpose. Importantly, nullFlavor UNK [HL7] has more granular values which can be used as well, as long as some form of unknown is available. For instance, nullFlavor ASKU (asked but unknown), nullFlavor NAV (temporarily unavailable), and nullFlavor NASK (not asked), and nullFlavor NAVU could be utilized. Situations where other nullFlavor options may be applicable are discussed in further considerations.
#### *Required Value Names, Descriptions, and Example Code Systems*

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Female|A value which corresponds to ‘F’, ‘female’, ‘woman’, or ‘girl’ has been recorded in some context.|<p>F [ICAO]</p><p>LA13504-8 [LOINC]</p>|
|Male|A value which corresponds to ‘M’, ‘male’, ‘man’, or ‘boy’ has been recorded in some context.|<p>M [ICAO]</p><p>LA15170-6 [LOINC]</p>|
|Nonbinary *or* Unspecified *or* Non-specified|A value which corresponds to ‘X’ has been recorded or the value is otherwise unspecified or non-specified. ‘X’ has been used to refer to the following in various jurisdictions (please note that this list is not exhaustive): (1) another gender identity, (2) gender diverse, (3) gender neutral, (4) indeterminate, (5) intersex, (6) neither male nor female, (7) nonbinary, (8) undesignated, (9) unreported.|<p>X,* < [ICAO]</p><p>LA32969-0 [LOINC]</p><p>LA32970-8 [LOINC]</p>|
|Unknown|A value is applicable, but not known.|<p>nullFlavor UNK [HL7]</p><p>Unknown, 261665006 [SNOMED CT]</p>|
#### *Further Considerations*
HL7’s nullFlavor can be useful in a number of situations for Gender Identity, outside of nullFlavor UNK [unknown]. Some of these situations are summarized below. Underneath each value name are value names known to be utilized in other systems. Also included are some values for assigned gender at birth questions, a somewhat common subtype of RSG.

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Masked|Information is available but has not been provided for security or privacy reasons. For instance, an individual may not present their assigned gender at birth or another recorded sex or gender value in a space considered to be unknown or dangerous. Their recorded sex or gender could be masked in a situation like this. Additionally, some recorded sex or gender values might not be used very often, and could therefore potentially lead to identifying an individual, compromising their privacy. A masked value could also be used to help prevent such a situation.|nullFlavor MSK [HL7]|
|<p>Something else</p><p>- Additional recorded sex or gender</p><p>- Another recorded sex or gender</p><p>- Another recorded sex or gender not listed</p><p>- Assigned gender at birth not listed</p><p>- Assigned sex at birth not listed</p><p>- Recorded sex or gender not listed above</p><p>- Recorded sex or gender not listed here</p><p>- Recorded sex or gender not listed</p>|The recorded sex or gender value provided exists beyond any utilized code system. In these cases, plain-text should be provided. Avoid using “other” as much as possible.|<p>nullFlavor OTH [HL7]</p><p>GSSO:009484 [GSSO]</p>|
|<p>Not applicable</p><p>- No assigned gender at birth</p><p>- No assigned sex at birth</p><p>- No recorded sex or gender</p>|Having no proper value for a recorded sex or gender. For instance, a biological specimen (cells, tissue, etc.) does not have a gender identity.|<p>nullFlavor NA [HL7]</p><p>GSSO:009485 [GSSO]</p><p></p>|
|<p>Asked but unknown</p><p>- Assigned gender at birth not disclosed</p><p>- Assigned sex at birth not disclosed</p><p>- Chose not to answer</p><p>- Does not understand the question</p><p>- Recorded sex or gender not disclosed</p><p>- Non-disclosed</p><p>- Person prefers not to say</p><p>- Prefer not to answer</p><p>- Prefer not to respond</p><p>- Prefer not to say</p><p>- Undisclosed</p><p>- Unsure</p>|Used in situations where a recorded sex or gender value was sought but not found. For instance, if a patient doesn’t understand the question, or if an individual refuses or prefers to not answer the question.|nullFlavor ASKU [HL7]|
|Temporarily unavailable|An individual’s recorded sex or gender is not available at the time but is expected later. For instance, a neonate who has not yet been assigned a gender at birth.|nullFlavor NAV [HL7]|
|<p>Not asked</p><p>- Inappropriate to ask</p><p>- Not appropriate to ask</p>|An individual has not been asked about their recorded sex or gender or that information has not otherwise been sought in any form.|nullFlavor NASK [HL7]|
|<p>Not available</p><p>- Assigned gender at birth inadequately described</p><p>- Recorded sex or gender inadequately described</p><p>- Inadequately described</p>|An individual’s recorded sex or gender is not available at the time, and there is no expectation that it will ever be available. Such a determination could be used if an individual has died and their documentation has not been ascertained.|nullFlavor NAVU [HL7]|
|<p>Not present</p><p>- Assigned gender at birth not provided</p><p>- Assigned sex at birth not provided</p><p>- Recorded gender not provided</p><p>- Recorded sex not provided</p><p>- Recorded sex or gender not provided</p><p>- Not provided</p>|Used only in messages to indicate that a value is not present.|nullFlavor NP [HL7]|
A number of jurisdictions use values outside of those aforementioned. For examples of some values, see above in “Entity: Recorded Sex or Gender, Attribute: Source Recorded Sex or Gender”, in the section “Further Considerations”.
### **Entity: Sex for Clinical Use, Attribute: Sex Category**
#### *Introduction*
Unlike the other attributes being discussed the attribute Sex Category in the entity Sex for Clinical Use is bound required, meaning that additional values beyond the value set will not be accepted. In the event that one attempts to add other values, they will be recoded as nullFlavor OTH (other). This binding is utilized because these values are often directly tied to functions of clinical systems which could break if inappropriate codes are exchanged.

The primary code system utilized is the LOINC answer list for Sex for clinical use, LL6114-4 / Female, Male, Specified, Unknown.
#### *Required Value Names, Descriptions, and Example Code Systems*

|**Value Name (English)**|**Description**|**Example Code System**|
| :-: | :-: | :-: |
|Female Sex for Clinical Use|The “female” values apply to this patient, in the case of a given procedure or process in a given context, for instance for a procedure, algorithm, hormone level, organ inventory, etc.|<p>F, LA3-6 [LOINC]</p><p>GSSO:011317 [GSSO]</p>|
|Male Sex for Clinical Use|The “male” values apply to this patient, in the case of a given procedure or process in a given context, for instance for a procedure, algorithm, hormone level, organ inventory, etc.|<p>M, LA2-8 [LOINC]</p><p>GSSO:011318 [GSSO]</p>|
|Specified Sex for Clinical Use|This patient has specific documented characteristics that do not fully match either male or female in a given context, for instance for a procedure, algorithm, hormone level, organ inventory, etc.|<p>S, LA32840-3 [LOINC]</p><p>GSSO:011319 [GSSO]</p>|
|Unknown Sex for Clinical Use|The SFCU cannot be determined because there are no observations or the observations are not sufficient to determine a value. For example, an emergency trauma case may require treatment before SFCU can be established.|<p>U, LA4489-6 [LOINC]</p><p>nullFlavor UNK [HL7]</p><p>Unknown, 261665006 [SNOMED CT]</p><p>GSSO:011320 [GSSO]</p>|
Given that this value set is intended to be a categorization of sex observations with the concept “Specified” as a flag to indicate non-standard sex observations, this value set should be bound required with no other codes allowed.

Instances in which “Specified” could be utilized include, but are not limited to:

1) Periods early in initiation of gender-affirming hormone therapy (GAHT) for transgender persons, in which inclusion of “male” and “female” reference ranges may be informative to include.
1) Instances wherein neither “male” nor “female” reference ranges are applicable, but another reference range could be specified, such as triglyceride levels in trans women using GAHT.
1) In instances wherein a provider wishes to have an algorithm utilized which does not include sex or gender as a variable, such as with eGFR.
#### *Further Considerations*
“Specified” is utilized here instead of terms like intersex for multiple reasons. The phrase intersex is typically a particular grouping of congenital conditions and even when used more generally it would not be considered synonymous or semantically equivalent. “Specified” is used to indicate that this person has specified observations that are likely important when considering clinical observations, particularly those that are impacted by sex-associated conditions.

While historical, mostly 19th-century, models described gay, lesbian, bisexual, intersex, and transgender persons as “intersexual”, this term (as well as intersex) was not chosen over “specified” because of its more specific scoped usage by providers, researchers, intersex activist groups (including interACT, the Intersex Society of North America, Intersex Initative, Intersex Peer Support Australia, the Intersex Justice Project, and the Intersex Campaign for Equality), and wider activist groups (such as Human Rights Campaign, Human Rights Watch, and ILGA-Europe). One of the authors of the original HL7 ballot document (Kronk) polled 483 trans people and found that 475 (98.3%) of them did not feel that all trans people were covered using the word “intersex”.

## **8.3 Glossary**
Included below are a few terms, in addition to those defined elsewhere in the document, for reference.

|**Term**|**Definition**|
| :-: | :-: |
|administrative gender||
|administrative sex||
|assigned gender at birth (AGAB)|A sex and/or gender datum that is recorded in some system (usually a birth certificate or registry) shortly after birth, often based on some sexing methodology. AGAB is a form of RSG and it is usually indicated as a gender marker on birth certificate, although not always.|
|cisgender|A gender modality in which one has a gender identity which is the same as one’s assigned gender at birth and/or the gender one was raised or reared as. Considered to be the opposite of *transgender*.|
|dyadic|Non-intersex.|
|endosex|Non-intersex.|
|gender|A complex umbrella term for characteristics which relate to sociocultural designations considered to be associated with, but not necessarily casually related to, sex. Elements of gender include gender identity, gender modality, gender expression, gender roles, and gender markers, among many other representations.|
|gender affirmation|Any process by which gender dysphoria is decreased and/or gender euphoria is increased. Gender affirmation can be medical, social, legal, or take various other forms. Cisgender and transgender people undergo many processes of gender affirmation, and gender affirmation is an individualized experience.|
|gender-affirming medical procedure|Any of various medical procedures performed for the primary purpose of gender affirmation. While transgender and ultergender (intersex and transgender) people are most commonly thought of as undertaking gender-affirming medical procedures, cisgender and ipsogender (intersex and transgender) people do as well.|
|gender-affirming hormone therapy (GAHT)|Therapeutic use of exogenous hormones for the primary purpose of gender affirmation. Typically, GAHT involves some use of anti-androgens, estradiol, progesterone, and/or testosterone by one or multiple routes. Many cisgender people and transgender people access GAHT, with menopausal cisgender women and cisgender men with sexual dysfunction being two groups that utilize GAHT.|
|gender-affirming surgery (GAS)|Any of various surgical procedures used for the primary purpose of gender affirmation. These surgical procedures are briefly reviewed in the following sections.|
|gender dysphoria|Psychological distress or discomfort that results from some form of disconnect between one’s sense of gender identity and their physical, hormonal, mental, emotional, presentational and/or social attributes. While transgender and ultergender (transgender and intersex) individuals come to mind when discussing gender dysphoria, not all transgender and ultergender individuals experience gender dysphoria, and many cisgender and ipsogender (cisgender and intersex) individuals do. For instance, cisgender women with polycystic ovarian syndrome may experience hirsutism and grow more noticeable facial hair. In many cultures, cisgender women having more noticeable facial hair is seen as a negative trait, which can result in duress in relationship with one’s gender identity.|
|gender euphoria|A state of intense excitement and happiness which results from one’s sense of gender identity aligning with an aspect of their physical, hormonal, mental, emotional, presentational and/or social attributes. For decades, gender euphoria in transgender people, especially transgender women, has been inextricably connected to ideas of “fetishism”, despite the fact that cisgender people, when expressing the same kind of euphoria, would also be labeled as “fetishistic” by the same mechanisms.|
|gender expression|Within a particular sociocultural context, one’s expression which is read as gendered. Note that gender expression varies immensely based on context; it is not possible to say that an individual has a universally “feminine” gender expression, as their expression may not be considered feminine in all contexts. Recording of gender expression in a structured way in an EHR is discouraged due to the item’s inherent lack of interoperability.|
|gender identity|A person’s self-concept of the gender category or categories to which they belong. A person may identify with one gender identity label, multiple gender identity labels, or no gender identity labels. Additionally, an individual may change gender identity labels over the life course. Non-human animals are typically not considered to have a gender identity. Gender identity has complex biopsychosocial components.|
|gender incongruence|A long-term pattern of gender dysphoria, which is typically unique to transgender and ultergender (intersex and transgender) persons, in which one’s assigned gender at birth (or gender of rearing, the gender they were raised as, etc.) differs from their gender identity.|
|gender marker|A marker which indicates gender on a given document (such as a driver’s license, birth certificate, etc.) or in a given database (such as in birth registry, an electronic health record, etc.). A gender marker is a type of RSG.|
|gender marker on birth certificate|The gender marker which appears on one’s birth certificate. A gender marker on birth certificate is a type of RSG.|
|gender marker on health insurance|The gender marker which appears on one’s health insurance card, is registered with their health insurance company, or otherwise appears in a form or document associated with health insurance.|
|gender marker on identity document|The gender marker which appears on an identity document, such as a national identification card, a driver’s license, or a passport. Many times, a gender marker which appears on an identity document that is produced by a government, or with some government affiliation, is referred to somewhat erroneously as a *legal sex* or *legal gender*. A gender marker on an identity document is a type of RSG.|
|gender modality|One’s alignment (or lack thereof) between their assigned gender at birth (or the gender they were reared or raised as) and their gender identity.|
|hermaphrodite|An intersexphobic slur which has selectively been reclaimed by some intersex people. It should not be used by non-intersex people to describe intersex people. However, the term hermaphrodite and its derivatives (such as hermaphroditic) are usually still considered appropriate when applied to non-human animals (such as nematodes).|
|intersex|An umbrella term referring to variations in sex characteristics which, while present congenitally, may become apparent at any period of one’s life course. Intersex variations are usually anatomical, genetic, or hormonal in nature, but not always. Further, just because a particular variation may be considered intersex in some cases, does not mean it is intersex in all cases. Intersex people are usually coercively assigned (oftentimes via intersex genital mutilation) as “male” or “female”, meaning that intersex is usually not an assigned gender at birth (AGAB). Intersex as a term should only be used when referring to humans. A gender marker on health insurance is a type of RSG.|
|ipsogender|A gender modality which is intersex and cisgender.|
|legal gender|A misnamed and fictitious social and legal construction which is most often used to refer to gender markers (often erroneously labeled as ‘sex’) on identity documents, such as birth certificates, driver’s licenses, and passports. Because of the difficulties involved in changing one’s gender marker on any of these documents, it is entirely possible that an individual have multiple different “legal” genders simultaneously. For this reason, RSG was included instead of legal gender, so that multiple RSGs can be recorded and the document which the RSG points to can be made more clear.|
|legal name|A misnamed and fictitious social and legal construction which is most often used to refer to how one’s name or names appear on identity documents, such as birth certificates, driver’s licenses, and passports. Because of the difficulties involved in changing one’s name on any of these documents, it is entirely possible that an individual have multiple “legal” names. Oftentimes, one’s name on identity documents does not match their actual name, and this is often the case for cisgender people and transgender people. For instance, an individual with the name “William” on an identity document may have the name “Bill”. An individual may take their partner’s surname upon marriage in many locales, but not be able to update their passport, with a previous surname appearing. Many people outside of the Anglosphere are forced to change their names in a number of ways in order to “fit” into arbitrary boxes decided upon by Anglosphere authorities, including fitting into a given name/middle name/surname dichotomy, removal of special characters, shortening of names that do not fit, and transliteration which may be inaccurate.|
|legal sex|See *legal gender*.|
|name|Occasionally also referred to as a ‘name to use’ or a ‘name used’; one’s name is the primary identifier that an individual uses and which is used to refer to that individual. Importantly, an individual’s name is just their name, it is not ‘chosen’, ‘preferred’, ‘affirmed’, etc.|
|nonbinary|<p>(1) A specific gender identity which is neither male nor female.</p><p>(2) An umbrella term… </p>|
|perisex|Non-intersex.|
|pronoun||
|pronoun set|A set of pronouns used commonly together and considered to be different forms of one another.|
|sex||
|sex characteristics|A characteristic which|
|sex dyadicity|One’s status as intersex or non-intersex (also called endosex, perisex, or dyadic).|
|transgender|<p>[1] A gender modality in which one has a gender identity which is different from one’s assigned gender at birth and/or the gender one was raised or reared as.</p><p>[2] An umbrella term referring to gender identity, gender expression, gender modality, and/or gender role which does not conform to Eurocentric binarism. While this definition was prevalent in the 1990s, it has since become less common.</p>|
|ultergender|A gender modality which is intersex and transgender.|

