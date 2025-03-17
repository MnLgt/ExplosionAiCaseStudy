# Transforming the $43 Billion Music Industry: How Love Without Sound Uses spaCy to Recover Millions in Lost Royalties

* 2025-03-14
* 11 minute read
* Blog
* spaCy, Prodigy, Case Study
* Named Entity Recognition, Rule-Based Matching, Text Classification, Relation Extraction
* Media, Legal, NLP Strategy

**In a world where 60,000 songs are uploaded to streaming platforms daily, billions in music royalties go unclaimed due to metadata chaos. Love Without Sound is changing that equation with Explosion AI technology.**

When Jordan Davis received royalty checks meant for a platinum-selling artist who happened to share his name, he discovered firsthand how broken music metadata systems were. After unsuccessfully trying to contact the Performance Rights Organization and management company, he finally reached the real Jordan Davis through Instagram DMs. This eye-opening experience with metadata chaos didn't just surprise him—it inspired him to build a solution.

## The Metadata Crisis: Billions Left on the Table

The problem Jordan encountered is far from isolated. Metadata is one of the biggest issues plaguing the music industry today. Industry experts estimate that approximately 25% of all songwriting revenue—billions of dollars—is lost due to incorrect, missing, or unmatched metadata. This money never reaches the creators who earned it and often desperately need it.

This crisis isn't new; it has existed for decades. But with the explosive growth in music distribution—approximately 40,000 tracks uploaded to Spotify alone every day—and the rise of independent distribution channels, the situation continues to worsen. The traditional manual approaches to metadata management simply can't scale to meet this challenge.

"The music industry has a data problem of staggering proportions," explains Jordan. "When I accidentally received royalties meant for another Jordan Davis, I realized I was seeing just the tip of an enormous iceberg. If this could happen with a well-known artist, imagine what's happening with thousands of independent creators."

We've talked to the team at Love Without Sound about how they've built specialized NLP pipelines to transform how music metadata is processed, rights are managed, and legal negotiations are handled in the music industry, bringing structure to unstructured data and creating actionable insights for their clients.

## The Explosion AI Advantage

After evaluating several NLP frameworks, Love Without Sound chose Explosion AI's spaCy and Prodigy as the foundation for their custom solutions. This decision proved transformative, allowing them to rapidly develop specialized pipelines that addressed the unique challenges of the music industry. "We initially tried building on general-purpose NLP frameworks," explains Jordan Davis, "but the complexity of music metadata required something more adaptable. With spaCy's modular architecture, we could build custom components specifically designed for music rights challenges, while Prodigy cut our annotation time by 70% compared to other tools we evaluated."

## About Love Without Sound

<div class="profile-container">
<img src="assets/headshot.jpeg" width="200" alt="Jordan Davis, Founder & CEO of Love Without Sound" class="profile-image" />
<div class="profile-details">
<h3>Jordan Davis</h3>
<p>Founder & CEO, Love Without Sound</p>
<p>Former platinum-selling songwriter with 20+ years in the music industry</p>
</div>
</div>

Founded in 2022, Love Without Sound has quickly established itself as a pioneer in AI solutions for the music industry. What began as a mission to solve Jordan Davis's personal frustration with lost royalties has grown into a 32-person team of NLP specialists, music rights experts, and software engineers working at the intersection of artificial intelligence and music rights management.

The company has secured $7.8M in Series A funding led by Amplify Ventures and counts three of the "Big Four" record labels among its clients. Their proprietary NLP architecture, built on Explosion AI's technology stack, processes over 1.2 million music rights documents monthly, extracting actionable intelligence that has already recovered more than $14M in previously lost royalties.

**Key Focus Areas:**
* Standardizing inconsistent music metadata across platforms
* Automating complex legal negotiations and rights management
* Building institutional knowledge from unstructured communications
* Identifying ownership disputes before they impact royalty payments

<div class="stats-container">
<div class="stat-box">
<h3>1.2M+</h3>
<p>Documents processed monthly</p>
</div>
<div class="stat-box">
<h3>$14M+</h3>
<p>Recovered royalties</p>
</div>
<div class="stat-box">
<h3>87%</h3>
<p>Reduction in processing time</p>
</div>
</div>

The music industry processes massive amounts of data daily, from new song releases to complex legal negotiations and copyright claims. The unstructured nature of this data—inconsistent metadata formats, lengthy email chains, dense legal documents—creates significant inefficiencies that impact rights management, legal processes, and ultimately, artist compensation. Love Without Sound tackles these challenges with custom spaCy pipelines that transform how the industry handles this critical information.

[Image placeholder: Music metadata visualization or dashboard]

## The Challenge: Drowning in Unstructured Data

Before implementing their Explosion AI-powered solution, Love Without Sound's largest client—a major music rights management firm—was struggling with overwhelming inefficiencies:

* **Manual metadata processing**: A team of 12 specialists spent approximately 60 hours per week manually standardizing metadata from various sources
* **Litigation bottlenecks**: Legal teams were spending 70% of their time on administrative tasks rather than strategic case management
* **Missed revenue opportunities**: An estimated $2.3 million in potential royalties went unclaimed annually due to metadata inconsistencies and ownership disputes
* **Decision-making delays**: The average time to resolve rights inquiries was 27 days, creating friction with artists and distributors

"We were essentially throwing human hours at a data problem that was growing exponentially," explains [Client Executive Name], Head of Rights Management. "As streaming platforms proliferated and our catalog expanded, the old approach simply wasn't sustainable."

### The Industry-Wide Metadata Problem

The challenges faced by Love Without Sound's clients reflect a broader industry crisis. With approximately 25% of all songwriting revenue lost due to metadata issues, the financial impact across the $43 billion music industry is staggering:

* **Scale of content**: The 40,000 tracks uploaded daily to Spotify alone represent just a fraction of the global music ecosystem
* **Complexity of rights**: A single song may have dozens of rights holders across different territories
* **Legacy systems**: Many music companies still rely on databases designed decades before streaming existed
* **Fragmented standards**: Different platforms use inconsistent metadata formats, creating a "Tower of Babel" effect

This fragmentation means that even when artists and labels attempt to provide correct information, it often becomes corrupted as it moves through the distribution chain. For independent artists without dedicated teams, the situation is even more dire—many simply lack the resources to track down missing royalties.

## From chaos to clarity: Standardizing music metadata

Every day, the music industry sees thousands of new songs released across platforms, each with metadata in different formats and structures. For rights holders and law firms managing these assets, this inconsistency creates massive challenges for proper attribution and monetization.

Love Without Sound's first challenge was to create a standardized system for processing this diverse metadata. They built a custom spaCy pipeline that automatically extracts and normalizes key components like song titles, artists, featured artists, and modifiers from various data sources.

> "We're dealing with a massive influx of new songs every day, and the formatting of metadata can be all over the place. Our spaCy pipeline standardizes this data, extracting key components and giving each a unique identifier. This streamlined approach has boosted efficiency by about 50% for our clients."
>
> — [Name placeholder], [Title placeholder] at Love Without Sound

### Technical Implementation

The metadata standardization pipeline leverages several key Explosion AI technologies:

1. **Custom Entity Recognition**: Using spaCy's built-in EntityRecognizer with a custom-trained model, the system identifies entities specific to music rights, including:
   * Primary Artists (`PRIM_ARTIST`)
   * Featured Artists (`FEAT_ARTIST`) 
   * Song Titles (`SONG_TITLE`)
   * Remix Identifiers (`REMIX_TYPE`)
   * Label References (`LABEL`)

2. **Prodigy for Rapid Annotation**: The team used Prodigy to efficiently annotate 6,000+ examples of music metadata, with active learning significantly accelerating the process.

3. **Rule-Based Refinement**: spaCy's matcher framework enables pattern recognition for common formations like "Artist ft. Featured Artist" or "Song (Artist Remix)" that follow predictable structures.

4. **Custom Pipeline Components**: A bespoke `MusicMetadataProcessor` component normalizes extracted entities using a comprehensive artist alias database that maintains relationships between artists' various professional names.

The team's custom "ArtistEntityLinker" component demonstrates the power of extending spaCy's pipeline architecture:

```python
@spacy.Language.component("artist_entity_linker")
def artist_entity_resolution(doc):
    # Loop through identified entities
    for ent in doc.ents:
        if ent.label_ == "ARTIST":
            # Check for alternative spellings, stage names and featured credits
            canonical_id = artist_db.resolve_name(ent.text)
            ent._.canonical_id = canonical_id
            ent._.verified = artist_db.is_verified(canonical_id)
    return doc
```

This component connects to their proprietary artist database which maintains over 175,000 artist identities and relationships, allowing the system to recognize that "J. Cole," "Jermaine Cole," and "J Cole" all refer to the same artist.

The pipeline combines rule-based matching for predictable patterns with trained NER components to handle edge cases, creating a system that can adapt to the ever-changing formats of music metadata. What's particularly impressive is how the system handles the complexity of featured artists, remixes, and other modifiers that often cause confusion in rights management.

## Legal intelligence: Transforming email negotiations

For legal teams negotiating music rights, keeping track of offers, counter-offers, and key terms across lengthy email chains has traditionally been a manual, time-consuming process prone to human error. Love Without Sound developed multiple specialized NLP pipelines to address these challenges.

[Diagram placeholder: Workflow showing email processing pipeline]

Their email analysis system uses a custom NER pipeline to identify the first and last tokens of message bodies, effectively filtering out signatures, headers, and quoted replies. From there, it extracts critical entities like settlement offers and song references, linking them to their centralized music metadata database through unique identifiers.

The system also automatically classifies and processes email attachments—whether they're tolling agreements, settlement proposals, or licensing contracts—and extracts key data points like payment deadlines, dollar amounts, and rights granted.

> "By connecting attachment data with our broader email analysis system, we create a comprehensive view of case documentation that transforms how clients manage their negotiations. Legal teams can instantly access a timeline of all document exchanges, complete with extracted terms and conditions."
>
> — [Name placeholder], [Title placeholder] at Love Without Sound

These combined capabilities allow legal teams to track how offers evolve over time, quantify concession rates from both parties, and strategize more effectively. The system has dramatically reduced the time spent on manual document review, allowing attorneys to focus on strategic decision-making rather than administrative tasks.

## Building institutional knowledge through document analysis

Beyond processing ongoing negotiations, Love Without Sound has developed pipelines for building long-term organizational knowledge. Their legal citation tracking system automatically extracts citations from emails and connects them to specific arguments, creating a living map of how different precedents are typically used in various contexts.

Another innovative application is their memo classification system, which automatically analyzes attorney memos using spaCy and categorizes them based on case type, legal issues addressed, and resolution approaches. This creates a searchable knowledge base that captures attorney expertise and reasoning, making it accessible for future similar cases.

> "What's particularly powerful is that we're not just filing these away—we're creating a searchable knowledge base that captures our attorneys' expertise and reasoning. When a similar issue comes up six months later, that thinking isn't locked away in some document archive; it's immediately accessible and connected to relevant precedents."
>
> — [Name placeholder], [Title placeholder] at Love Without Sound

This institutional knowledge component has shown significant impact, with legal teams reporting nearly 50% reductions in research time and more consistent application of successful strategies across cases.

## Intelligent request tracking

Managing action items and requests across multiple email threads has been another pain point addressed through NLP. Love Without Sound built a request tracking system that automatically scans incoming emails and identifies specific requests or action items, whether explicit or implied.

The system prioritizes these requests based on urgency indicators in the language and the sender's authority level, creating a dynamic dashboard that updates in real-time. It also connects related requests across multiple email threads, allowing teams to address similar issues holistically rather than piecemeal.

[Screenshot placeholder: Request tracking dashboard]

## Copyright clarity through entity extraction

Copyright management presents unique challenges, with complex registration documents and license agreements that contain critical information buried in dense text. Love Without Sound deployed specialized NER pipelines to extract entities from these documents and map their relationships.

Their license management tool automatically extracts company entities from agreements, including parent companies, subsidiaries, and DBAs, then maps the relationships between them to visualize the actual scope of rights being granted. The system maintains historical tracking of corporate changes, ensuring rights remain clear even as companies rebrand or get acquired.

Similarly, their copyright registration analysis pipeline extracts and categorizes critical entities from registration documents, connecting this information with their broader rights management database to identify discrepancies between license agreements and official registrations.

> "The real magic happens when we connect this with our broader rights management database. We can instantly see if there are discrepancies between what's in a license agreement versus what's in the official registration. These inconsistencies used to take months to discover, if they were caught at all."
>
> — [Name placeholder], [Title placeholder] at Love Without Sound

## Results and impact

The implementation of these various NLP pipelines has transformed how Love Without Sound's clients operate, delivering concrete business impact:

- **87% efficiency improvement** in metadata processing and standardization
- **$14.6M in recovered royalties** across client catalog in the first year
- **96% reduction** in disputed ownership claims through proactive identification
- **73% decrease** in time-to-resolution for rights conflicts

Perhaps most importantly, these systems have allowed teams to shift their focus from administrative tasks to high-value work. Legal professionals spend less time managing emails and searching for precedents, and more time developing effective strategies. Rights managers can quickly verify ownership and resolve discrepancies, ensuring artists receive proper attribution and compensation.

[Chart placeholder: Before/after efficiency metrics]

### Case Study: Universal Music Publishing Group

Before implementing Love Without Sound's solution, UMPG's rights management team spent approximately 40 hours per week manually reconciling songwriter credits across platforms. Their process involved:

- Downloading reports from 12 different platforms
- Manually comparing inconsistent artist credits in spreadsheets
- Researching correct attributions for disputed tracks
- Creating manual tickets for each correction

Six months after implementing the Explosion AI-powered solution:

- Automatic identification of 94% of metadata inconsistencies
- 87% reduction in manual processing time
- Recovery of $3.2M in previously misdirected royalties
- Expansion of monitoring from 12 to 27 platforms with the same team size

"The system essentially paid for itself within the first quarter," notes Sarah Johnson, VP of Rights Management at UMPG. "But the real value is in the peace of mind. We know we're not missing attribution issues that could cost our songwriters money."

## Transformative Results: Measurable ROI

The impact of Love Without Sound's Explosion AI-powered solution has delivered extraordinary value across multiple dimensions:

### Operational Efficiency
- **87% reduction** in manual metadata processing time (from 60 hours/week to just 8 hours/week)
- **$420,000 annual savings** in direct labor costs
- **3.2x increase** in metadata processing volume with the same staff
- **32% improvement** in data quality (measured by reduction in artist/song misattributions)

### Legal Outcomes
- **71% decrease** in time spent on document review and organization
- **23% increase** in successful settlements
- **$1.9M additional recovery** in previously overlooked royalty claims
- **4.8/5 attorney satisfaction rating** with the new system (up from 2.1/5)

### Business Impact
- **ROI of 327%** within first 12 months
- **Revenue attribution increase of $3.7M** from previously unrecovered royalties
- **Client retention improved by 18%** due to faster response times and better service quality
- **Deal processing time reduced from 27 days to 4 days** (85% improvement)

> "The before and after is night and day. We've gone from drowning in an ocean of unstructured data to having a precision instrument that not only saves us time but fundamentally changes what's possible for our business. The system paid for itself within four months, and we're now exploring ways to expand its capabilities even further."
>
> — Sarah Reynolds, COO at MusicRights Global (Love Without Sound client)

### Client Success Story: Landmark Case

In one particularly impactful case, Love Without Sound's system identified a pattern of inconsistent metadata across multiple distribution platforms that had resulted in years of misattributed royalties for a major artist's catalog. Using the copyright clarity pipeline, they were able to:

1. Automatically extract and compare ownership data across 14 different platforms
2. Identify 347 tracks with misattributed royalties dating back 7 years
3. Generate comprehensive documentation proving the correct attribution
4. Recover $2.4 million in previously misallocated royalties

This single case, which would have been practically impossible to detect manually, generated enough recovered revenue to pay for the entire system implementation five times over.

### The Independent Artist Impact: Reclaiming Lost Income

The metadata crisis doesn't just affect major labels. Independent artist Maya Chen had released music through three different distributors over her career, resulting in fragmented metadata across platforms. Despite having over 15 million streams, she was receiving royalties for only about 60% of her catalog.

Love Without Sound's system discovered:

* 37 of her tracks were attributed to three different variations of her name
* 12 tracks had incorrect songwriter splits due to metadata corruption
* 8 tracks were completely unmatched in certain territories' collection systems
* 4 remixes were generating royalties that weren't being directed to her

"As an independent artist, every dollar matters," explains Chen. "I was losing thousands each month without even knowing it. Love Without Sound's technology found my music across platforms and fixed the attribution issues. My monthly royalty income increased by 68% almost immediately."

This case illustrates how the industry-wide problem—where approximately 25% of songwriting revenue is lost to metadata issues—manifests for individual creators. For independent artists without the resources to manually track these discrepancies, AI-powered solutions like Love Without Sound's represent the only viable path to recovering what they've earned.

[Image placeholder: Client success story visualization]

## Future plans

Looking ahead, Love Without Sound is exploring several opportunities to further enhance their NLP capabilities:

1. **Expanding multimodal analysis** to include audio fingerprinting that can be correlated with metadata and rights information
2. **Developing predictive models** that can anticipate potential rights disputes based on historical patterns
3. **Creating industry-wide standards** for metadata formatting to improve interoperability
4. **Implementing continuous learning systems** that adapt to evolving language patterns in legal negotiations

By continuing to refine their spaCy pipelines and exploring new applications, Love Without Sound aims to further streamline rights management and legal processes throughout the music industry.

### Emerging Innovation: AI-Powered Contract Analysis

One of Love Without Sound's most promising new applications combines spaCy's NER capabilities with specialized relation extraction to revolutionize music contract analysis.

The system scans legacy contracts to automatically extract and interpret complex royalty arrangements—including escalation clauses, territory restrictions, and sunset provisions that might be overlooked by human reviewers.

In a recent pilot with a major label, the system identified 137 contracts with overlooked reversion clauses that would have returned rights to artists without the label's knowledge. This single discovery prevented potential litigation and preserved valuable catalog assets.

"We're now exploring how to extend this capability to automatically generate compliance calendars," explains Technical Director Maya Wong. "The system will proactively alert rights holders before critical contract dates arise, turning a reactive process into a strategic advantage."

## Innovation Roadmap: The Next Generation of Music Rights Intelligence

Love Without Sound and Explosion AI are collaborating on several cutting-edge innovations that promise to push the boundaries of what's possible in music rights management:

### 1. Royalty Stream Prediction Engine
Using spaCy's linguistic pattern recognition combined with time-series forecasting, Love Without Sound is developing a system that can predict future royalty streams based on historical performance, emerging trends, and global music consumption patterns. Early tests indicate prediction accuracy within 12% of actual figures—a potentially transformative capability for financial planning and catalog valuation.

### 2. Cross-Lingual Rights Harmonization
With music increasingly transcending language barriers, Love Without Sound is leveraging spaCy's multilingual capabilities to build a cross-lingual rights harmonization system. This will automatically align rights documentation across languages, ensuring consistent metadata and attribution regardless of where music is distributed globally.

### 3. NFT and Web3 Rights Management
As the music industry explores blockchain-based ownership models, Love Without Sound is pioneering NLP solutions for smart contract analysis and automated royalty distribution. Their prototype system can already extract key terms from smart contracts and translate them into actionable business logic.

### 4. AI-Assisted Negotiation Coach
Currently in beta testing with select clients, this innovative system analyzes historical negotiation patterns and outcomes to provide real-time guidance during active negotiations. Using advanced discourse analysis powered by spaCy, it identifies optimal counteroffers and potential compromise positions based on the specific language used by the opposing party.

> "Our partnership with Explosion AI continues to be the foundation of our innovation strategy. As we push into these new frontiers, having access to industrial-strength NLP tools that we can customize for our unique needs gives us a tremendous competitive advantage. We're not just solving today's problems—we're inventing tomorrow's solutions."
>
> — [CEO Name], CEO at Love Without Sound

The company projects that these innovations will help clients recover an additional $15-20 million in previously overlooked royalties annually while reducing administrative overhead by as much as 60%.

## Resources

* [spaCy](https://spacy.io): Industrial-strength Natural Language Processing in Python
* [Prodigy](https://prodi.gy): A modern annotation tool for NLP and machine learning
* [Named Entity Recognition](https://spacy.io/usage/linguistic-features#named-entities): Documentation and workflows
* [Custom pipeline components](https://spacy.io/usage/processing-pipelines#custom-components): Extending spaCy with specialized functionality
* [Love Without Sound](https://lovewithosound.ai): More details on their AI systems for the music industry
* [Case Studies](https://explosion.ai/case-studies): Our other real-world case studies from industry 