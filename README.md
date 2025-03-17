<header class="hero">
  <div class="container">
    <h1><a href="http://www.lovewithoutsound.com">Love Without Sound</a></h1>
    <p class="lead">Love Without Sound crafts sophisticated AI systems and custom architecture for the music industry. We specialize in natural language processing solutions for music metadata, revolutionizing rights management and monetization.
Our expertise transforms unstructured data into valuable, structured assets—delivering actionable insights while creating seamless data exchange frameworks between industry stakeholders. We serve a diverse clientele including intellectual property law firms and innovative music startups.</p>
  
  </div>
</header>

## Music Metadata

### The Industry Challenge
* **[Volume of Daily Music](lws/Music%20Metadata%20Problem%20-%20Facts%20%26%20Figures.md#volume-of-music-uploaded-daily):** Spotify receives approximately 40,000 new tracks daily.
* **[Misattributed Ownership Rights](lws/Music%20Metadata%20Problem%20-%20Facts%20%26%20Figures.md#metadata-incompleteness):** Approximately 15% of tracks have incomplete metadata, compounded by lack of standardization. This leads to ownership disputes affecting $1.5 billion in royalties annually.
* **[Unallocated Royalties](lws/Music%20Metadata%20Problem%20-%20Facts%20%26%20Figures.md#financial-impact):** An estimated $2.5 billion in "black box money" remains unallocated due to metadata issues, preventing proper compensation to rightful creators.
* **[Compensation Gaps](lws/Music%20Metadata%20Problem%20-%20Facts%20%26%20Figures.md#financial-impact):** Roughly 25% of songwriting revenue is lost due to metadata errors, with independent artists disproportionately affected by these systemic failures.

### Building a parser to extract song title, artist, featured artist and modifiers 

Our music metadata parser addresses the challenge of inconsistent formatting across the industry's massive daily influx of new content. We've developed a specialized spaCy pipeline that standardizes this unstructured data by extracting and categorizing key components including song titles, artists, featured performers, and version modifiers. 

This standardization process assigns unique identifiers to each metadata component, creating a consistent framework regardless of the source format. The system transforms chaotic, heterogeneous metadata into structured, reliable information that can be seamlessly integrated across platforms and databases. For our clients, this has translated to approximately 50% improvement in processing efficiency while ensuring accurate, consistent management of music rights and royalty attributions.


![Title Variations GIF](lws/assets/title_variations.gif)
*This animation demonstrates various metadata variations for the song "All The Way Up" by Fat Joe, showing how the same song can appear with different title and artist formatting across music platforms and databases.*

![Title Variations NER GIF](lws/assets/title_variations_ner.gif)
*The same metadata variations with color-coded entity recognition, highlighting how our trained spaCy models identify and classify different components of song metadata. Colored boxes indicate the entities detected by our natural language processing models, showcasing the system's ability to normalize music metadata despite inconsistent formatting.*

Html Files: 
- [Title Variations HTML File](lws/assets/title_variations.html)
- [Title Variations NER HTML File](lws/assets/title_variations_ner.html)

Meta Files:
- [Song Model meta.json](lws/assets/meta_music_md_song_model.json)
- [Artist Model meta.json](lws/assets/meta_music_md_artist_model.json)
- [Modifier Model meta.json](lws/assets/meta_music_md_modifiers_model.json)


## Documents Pipeline

1. ### Email Body Extraction Tool
   Our email body extraction tool uses an NER pipeline to identify the first and last tokens of message bodies, effectively removing noise from email conversations. This clean extraction allows us to isolate relevant text and extract key entities from emails and call notes, such as settlement offers and song mentions. Clients can track negotiation progress over time, seeing how offers evolve and positions shift.

2. ### Email Correspondence Classifier
   After extracting message bodies, our correspondence classifier distinguishes substantive business communications from non-essential emails like newsletters and meeting invitations. This filtering ensures teams focus only on relevant conversations.

3. ### Entity Extraction Models
   We've developed multiple models for extracting valuable entities from message content:
   
   **Legal Citation Extraction:** Our system automatically identifies legal citations within negotiations and maps them to the specific arguments they support. Over time, this builds a dynamic reference system showing how different precedents apply to various contexts. When opposing counsel cites a case, our clients instantly understand its historical usage, typical counter-arguments, and overall effectiveness. This intelligence has reduced research time by nearly 50% while providing a stronger understanding of the precedent landscape.

   **Music Reference Extraction:** When songs are mentioned, our system links these references to unique identifiers in our music metadata database, enabling quick verification of licensing claims and providing essential context. This comprehensive connection helps guide clients and law firms in making informed decisions.
   
   **Request Tracking System:** This tool scans incoming communications to identify action items and requests, whether explicitly stated or implied. The system prioritizes these items based on urgency indicators and sender authority, creating a real-time dashboard of pending requests. By connecting related requests across multiple threads, teams can address similar issues comprehensively rather than piecemeal, significantly improving response times and client satisfaction.

4. ### Email Attachment Processing
   Our attachment pipeline automatically classifies incoming documents (tolling agreements, settlement proposals, licensing contracts, etc.) and extracts critical data points. For settlement agreements, the system identifies payment deadlines, amounts, and granted rights. For tolling agreements, it highlights key dates and extension provisions.
   
   By integrating attachment data with our email analysis system, we create a comprehensive view of case documentation that transforms negotiation management. Legal teams gain instant access to document exchange timelines complete with extracted terms and conditions, eliminating hours of manual review.

5. ### Attorney Memo Categorization
   Our memo classification system transforms institutional knowledge management by automatically analyzing and categorizing attorney memos based on case type, legal issues addressed, and resolution approaches. This creates a searchable knowledge base that captures attorney expertise and reasoning.
   
   The system's learning capability improves over time, recognizing nuanced differences between similar legal scenarios and suggesting related materials that might use different terminology. This particularly benefits newer associates who can access this collective wisdom. The result is significantly reduced redundant work and more comprehensive client responses based on actual practice history.

6. ### License Agreement Entity Extraction
   Our spaCy extraction tool has transformed license management by automatically identifying all company entities within agreements, including parent companies, subsidiaries, and DBAs throughout document text. The system maps relationships between entities, creating a visual network that clarifies the scope of rights being granted in complex multi-entity deals.
   
   The historical tracking capability maintains connections through corporate rebranding and acquisitions, ensuring rights clarity over time by tracing the lineage of particular rights through corporate changes.

7. ### Copyright Registration Entity Extraction
   Our spaCy system has revolutionized copyright registration analysis by automatically extracting and categorizing critical entities from registration documents—creators, claimants, prior registration references, and more. When connected to our rights management database, the system instantly identifies discrepancies between license agreements and official registrations.
   
   The historical analysis component traces works through multiple registrations and identifies potential chain-of-title gaps, providing crucial verification during acquisitions. This approach has dramatically reduced review time from days to minutes while significantly decreasing rights ownership risks by enabling proactive resolution before disputes arise.


- [Correspondence Classifier meta.json](lws/assets/meta_email_corr_cat.json)
- [Body Extractor meta.json](lws/assets/meta_email_bom_eom.json)

- [Attachment Classifier meta.json](lws/assets/meta_attachment_classifier.json)
- [Agreement Sections Classifier meta.json](lws/assets/meta_agreement_sections.json)
- [Agreement Spans meta.json](lsw/assets/meta_agreement_spans.json)
- [Agreement NER meta.json](lsw/assets/meta_agreement_ner.json)

- [Legal Citations NER meta.json](lsw/assets/legal_citation.json)
