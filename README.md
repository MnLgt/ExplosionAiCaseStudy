<header class="hero">
  <div class="container">
    <h1><a href="http://www.lovewithoutsound.com">Love Without Sound</a></h1>
    <p class="lead">Love Without Sound crafts sophisticated AI systems and custom architecture for the music industry. We specialize in natural language processing solutions for music metadata, revolutionizing rights management and monetization.
Our expertise transforms unstructured data into valuable, structured assets—delivering actionable insights while creating seamless data exchange frameworks between industry stakeholders. We serve a diverse clientele including intellectual property law firms and innovative music startups.</p>
  
  </div>
</header>

1. ## Building a parser to extract song title, artist, featured artist and modifiers 

In the music industry, we're dealing with a massive influx of new songs every day, and the formatting of metadata can be all over the place. We've built a Spacy pipeline that standardizes this data, extracting key components like song titles, artists, and versions. This means no matter where the data comes from, we can quickly organize it and give each component a unique identifier. This streamlined approach is a game-changer for our clients, boosting efficiency by about 50% and ensuring accurate, consistent handling of music rights.


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

1. ## Email Correspondence Classifier

The first part of our document pipeline starts with the incoming and outgoing emails.  We start with a simple classifier that classifies whether the email is correspondence or not.  This separates various emails like newsletters, zoom invites, or any other type of non-substantive email from the correspondence we want to focus on.

[Correspondence Classifier meta.json](lws/assets/meta_email_corr_cat.json)


2. ## Email Body extraction tool
In legal negotiations, having a clear picture of the dialogue is crucial. We've built an NER pipeline for the first and last tokens of the message body.  This removes all of the noise in the email conversation and extracts just the text.  From there we then pull out entities from emails and also call notes, like settlement offers and song mentions. This way, clients can track how offers have evolved over time, seeing the rate at which both sides are adjusting their positions.  

Additionally, when specific songs are mentioned, our system links these mentions to the unique song identifiers in our music metadata database. This allows clients to quickly verify licensing claims and understand the context of each song within a case. By connecting these dots, we provide a comprehensive view that guides our clients and law firms in their decision-making, enhancing both efficiency and strategy.

[Body Extractor meta.json](lws/assets/meta_email_bom_eom.json)

3. ## Extracting email attachments

## I built a pipeline that automatically classifies incoming documents—whether they're tolling agreements, settlement proposals, or licensing contracts—and extracts the most valuable data points.

When a settlement agreement arrives, our system immediately identifies key terms like payment deadlines, dollar amounts, and rights granted. For tolling agreements, it flags critical dates and extension provisions. This automation eliminates hours of manual review and structures various things like payment deadline or agreement expiration dates.  
By connecting this attachment data with our broader email analysis system, we create a comprehensive view of case documentation that transforms how clients manage their negotiations. Legal teams can instantly access a timeline of all document exchanges, complete with extracted terms and conditions. This system has totally transformed what the client's team spends their time doing and saves them from hours of manual sifting through documents and instead have a broad picture of everything going on.

- [Attachment Classifier meta.json](lws/assets/meta_attachment_classifier.json)
- [Agreement Sections Classifier meta.json](lws/assets/meta_agreement_sections.json)
- [Agreement Spans meta.json](lsw/assets/meta_agreement_spans.json)
- [Agreement NER meta.json](lsw/assets/meta_agreement_ner.json)

4. ## Extracting legal citations 

When it comes to legal citations, the system automatically pulls citations from all those emails flowing through negotiations, but it doesn't just collect them—it connects each citation to the specific arguments being made.  
What's fascinating is how this builds over time. We're essentially creating this living map of how different precedents are typically used in various argument contexts. So when the attorneys need to respond to something, they don't have to start from scratch with research—they can immediately see which cases have worked well for similar positions in past negotiations.  
The real game-changer is having this intelligence embedded right in the workflow. When a citation comes in from opposing counsel, our team instantly knows its history, how it's been countered before, and whether it's typically effective. We've seen legal teams cut their research time almost in half, and they're walking into negotiations with a much stronger understanding of the precedent landscape.  
It's one of those tools that just gets better with use—every new case and every new citation makes the system smarter, and that's creating this compounding advantage for our clients over time.

- [Legal Citations NER meta.json](lsw/assets/legal_citation.json)


5. ## Extracting requests from emails 

We've also built a request tracking system that's been a real lifesaver for our teams. It automatically scans through all incoming emails and pinpoints specific requests or action items, whether they're explicit or sometimes just implied in the text.  
What's really valuable is how it prioritizes these requests based on urgency indicators in the language and the sender's authority level. So instead of our attorneys spending hours sifting through their inboxes, they get this dynamic dashboard of pending requests that updates in real-time.  
The system has this clever way of connecting related requests across multiple email threads too. If someone's asking about the same issue in different conversations, it consolidates those touchpoints so those can be addressed all at once instead of one by one. Their response times have improved dramatically, and their clients are noticing the difference in how quickly things are addressed.  
It's become this essential workflow tool that's freed up their legal teams to focus on substantive work rather than email management. 

6. ## Categorizing Memos to File from attorneys

Our memo classification system has completely transformed how we manage institutional knowledge. Using spaCy, we can automatically analyze attorney memos and categorize them based on case type, legal issues addressed, and resolution approaches.  
What's particularly powerful is that we're not just filing these away—we're creating this searchable knowledge base that captures our attorneys' expertise and reasoning. So when a similar issue comes up six months later, that thinking isn't locked away in some document archive; it's immediately accessible and connected to relevant precedents.  
The system has this natural learning capability too. As it processes more memos, it gets better at recognizing nuanced differences between similar legal scenarios and can suggest related materials that might not use the exact same terminology. Our newer associates especially benefit from being able to tap into this collective wisdom.  
We've seen such a reduction in redundant work. Problems that have been solved before don't need to be solved again from scratch. And when clients ask about our approach to certain issues, we can quickly pull together comprehensive responses based on our actual practice history rather than generic principles.

7. ## Extracting company names from licenses

License management was always this incredibly manual process until we implemented our spaCy extraction tool. Now we automatically pull all company entities from licensing agreements, including parent companies, subsidiaries, and even DBAs that are scattered throughout the document text.  
The system doesn't just identify the names—it maps the relationships between them, creating this visual network of which entities are connected and how. This has been crucial for understanding the actual scope of rights being granted, especially in these complex multi-entity entertainment deals.  
What's been particularly valuable is the historical tracking. When a company rebrands or gets acquired, our system maintains those connections, so rights don't suddenly become unclear. We can trace the lineage of any particular right through all these corporate changes over time.

8. ## Extracting entities from copyright registrations 

Copyright registration analysis used to be this tedious process that nobody wanted to do, but our spaCy system has completely reinvented the approach. It automatically extracts and categorizes all the critical entities from registration documents—creators, claimants, prior registration references—you name it.  
The real magic happens when we connect this with our broader rights management database. We can instantly see if there are discrepancies between what's in a license agreement versus what's in the official registration. These inconsistencies used to take months to discover, if they were caught at all.  
We've also built in this clever historical analysis component. The system can trace the evolution of a work through multiple registrations and identify potential gaps in the chain of title. This has been incredibly valuable for acquisitions, where our clients need confidence that they're getting clean rights.  
The efficiency gain has been remarkable—what used to take days of manual review now happens in minutes. But the real benefit has been in risk reduction. We're catching these ownership issues before they become problems, allowing our clients to address them proactively rather than in the middle of a dispute when leverage is limited.

<section id="services" class="services">
  <div class="container">
    <h2 class="section-title">Our Solutions</h2>
    
    <div class="services-grid">
      <!-- Service Card 1 -->
      <div class="service-card">
        <div class="service-icon">
          <i class="icon-music-parser"></i>
        </div>
        <h3>Music Metadata Parser</h3>
        <p>Standardizing song titles, artists, and versions through our advanced Spacy pipeline.</p>
        <div class="service-demo">
          <!-- Interactive demo replacing GIF -->
        </div>
        <a href="#metadata-parser" class="card-link">Learn more</a>
      </div>
      
      <!-- Additional service cards follow same pattern -->
    </div>
  </div>
</section>

<section id="metadata-parser" class="feature-section">
  <div class="container">
    <div class="feature-grid">
      <div class="feature-content">
        <h2>Building a parser to extract song metadata</h2>
        <p>Our Spacy pipeline standardizes music data, extracting key components like song titles, artists, and versions. This streamlined approach boosts efficiency by about 50% and ensures accurate, consistent handling of music rights.</p>
        <ul class="feature-list">
          <li>Standardized identification for song titles</li>
          <li>Artist and featured artist extraction</li>
          <li>Modifier and version detection</li>
        </ul>
      </div>
      <div class="feature-visual">
        <!-- Interactive demo replacing the GIF -->
        <div class="demo-container" id="title-variations-demo">
          <!-- Demo content -->
        </div>
      </div>
    </div>
  </div>
</section>

<section id="documentation" class="documentation">
  <div class="container">
    <h2>Technical Documentation</h2>
    <p>Access our detailed technical specifications and model information.</p>
    
    <div class="doc-cards">
      <div class="doc-card">
        <h3>Interactive Demos</h3>
        <ul>
          <li><a href="lws/assets/title_variations.html">Title Variations Demo</a></li>
          <li><a href="lws/assets/title_variations_ner.html">Title Variations NER Demo</a></li>
        </ul>
      </div>
      
      <div class="doc-card">
        <h3>Model Specifications</h3>
        <ul>
          <li><a href="lws/assets/meta_music_md_song_model.json">Song Model Specification</a></li>
          <li><a href="lws/assets/meta_music_md_artist_model.json">Artist Model Specification</a></li>
          <li><a href="lws/assets/meta_music_md_modifiers_model.json">Modifier Model Specification</a></li>
        </ul>
      </div>
    </div>
  </div>
</section>

