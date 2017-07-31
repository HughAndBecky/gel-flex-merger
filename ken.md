Thoughts on the FLEx dB merger with Ken Zook
Becky Paterson
15 July 2017

re: conflict resolution

Be aware that our previous analysis was based on fields not on writing systems in conjunction with fields. We want to be sure that:

If a FLEx-field/writing-system combination has been populated in DB2, and the same combination is blank in DB1, DB2's content should remain.(e.g., Pronunciation and Citation are used in DB2, but are not used in DB1. Regardless of writing system, Pronunciation and Citation data from DB2 should remain).

If a custom field exists in DB1, and does not exist in DB2, the custom field should be created and DB1's data should remain. These fields should be aligned and paired via SILCAWL numbers (all entries in DB1 have a SILCAWL number).


re:Writing Systems

I am happy for the names of the writing systems to be changed to best practice naming conventions. However, what those conventions are is problematic. for instance. Many of our texts are created in ELAN. Elan uses the ISO-x-IPA schema, so if we are going to round trip our data (which we intend to do), then we can not use the gel-fonipa writing system. We think this means that the writing system in DB1 needs to be converted to the writing system in DB2. Which is the inverse of what your email suggests. Without clarity on which data on a per-field bases is going to be overwritten it is hard to use the writing system string analysis you provided. It very well could be that some strings will never over write because they are different fields. So even if writing systems are merged, there will be no impact related to data loss.

The post-merger dB needs to have three Vernacular writing systems.
    All use the same IPA keyboard.
    Three different levels of representation of each Vernacular entry are needed because texts exist in three different writing systems. This allows us to use the text parsing tool regardless of how the texts are represented. We know we need three writing systems because we need each of these in the lexeme field.
        (1) gel-fonipa - IPA representation
        (2) gel-orth - orthography used by Bible Translation project including hyphens
        (3) gel-ModOrth, that is Modified Orthography without hyphens

The ModOrth writing system was created to be able to parse data in the text section of FLEx to work within the limitations of FLEx's text parsing capabilities. The (2) gel-orth (and indeed the present/working orthography in use by the Bible translation project) uses hyphens within a word as a non-word-breaking character. I created ModOrth to use for entering texts written in the Orth, but with hyphens removed. The lexical side of things does not need ModOrth, as any dictionary presentation would likely show the hyphens. ModOrth exists in the Lexical side for the purpose of glossing texts. Note: I don't mean that occasionally there is a hyphenated word. I mean that almost every noun has a hyphen separating noun class morphology from the stem. It is a nightmare really, but that's another issue.

Why do we need multiple writing systems for the same language?

 - to be able to show different representations of the same item in one FLEx field
 - i.e., an IPA and an ORTH writing system are needed because I want to see both inside of the Lexeme field (and I want FLEx to be able to parse both in the texts section)
 - also, this means we don't need a separate writing system for a tonal representation UNLESS the tonal representation needs to be in the LEXEME field along with the IPA and the ORTH. We need several representations of tone we need to be able to sort by tonal-melody at the word level, and we also need to be able to be a-commital on that melody's phonetic vs. phonological status. (surface vs. underlying melody) we need to indicate the tone with the characters "MHL" and also with the IPA characters for tone.

In the pedagogical context, I find FLEx's User Experinece introduction to the number of writing systems needed by a new database user to be confusing. In the past, when I have taught FLEx (along side Beth B.) we have modeled field work situations. The assumption is that users in a field work situation will bring new data coming into FLEx that is in IPA rather than in an orthrograpy. Therefore one challenge I see with using the bare <gel> tag for the writing system is that in real life a language project does not start entering data in an ORTH. So should the bare tag be the one that is used by default in FLEx? Using the bare form of the BCP47 tag as the default in FLEx seems to nullify the benefit of using the Lexeme field as the entry field using as is suggested to the user via the "Create a New Lexical Entry" button. I have never had anyone suggest to me that a new FLEx dB should have multiple writing systems for the primary language from setup. But it seems this is necessary if we are to truely assume that IPA data should have the -fonipa subtag, and the bare tag should be reserved for later analysis and processes used to create a more official and stable orthography.
