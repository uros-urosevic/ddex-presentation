
# M

---

## Agenda

- DDEX
- CIP
- ERN

---?image=/assets/image/DDEXOverview.jpg&size=auto 90%

---


## Definitions and Terminology

+++

### Label / Publisher

Note:
A record label will help facilitate the production, distribution and promotion of your recorded music (think CD). They will own the recorded music and pay you royalties for using it. A song writer owns the musical composition (think words and notes on paper) and hires a publisher to handle administrative tasks like licensing the music to be used in movies, or printing song books like you would buy at the music store.

+++

### Digital Service Provider (DSP) / Release Distributor

Note:
A Digital Service Provider (DSP), a Party making Releases available to Consumers or other DSPs over a public Telecom network. This includes MSPs (Mobile Service Providers) and ISPs (Internet Service Providers).

+++

### Musical Work

Note:
A Work intended to be perceivable as a combination of sounds, with or without accompanying text.
Any words that are intended to be expressed with a MusicalWork (often termed Lyrics) form part of that MusicalWork; not all MusicalWorks have Lyrics.
A MusicalWork may be expressed and fixed to become part of a SoundRecording or a Video Recording, or may be used to create notated music (sheet music, scores, instrumental parts) or sound generation codes (such as MIDI files).
In some cases, the MusicalWork comes into existence simultaneously with its expression. This is common in extemporised forms such as jazz music.

+++

### Song / Recording

Note:
A composition is a musical work, with or without lyrics, that has been created by a songwriter/composer.
A sound recording, often also referred to as a "master”, is the recording of a performance of the underlying composition. This includes beats, percussion, bass, guitar, vocals, etc.
For example, Dolly Parton wrote the composition (meaning she wrote the lyrics and melody), to "I Will Always Love You." Arista Records recording artist Whitney Houston recorded a version of Dolly Parton's composition.  In this case, Arista Records owns the sound recording of the song while Dolly Parton and her publisher own the composition.

+++

### Product

Note:
A Manifestation of a Release (or another Resource) which is made available to Consumers, by sale, loan or other means. The attributes of a Release in its digital manifestation as a Product may be technical (e.g., the codec or bit rate); a mode of distribution (e.g., downloading or streaming); or a commercial term (e.g., price).

+++

### Release

Note:
A Release is an abstract entity representing a bundle of one or more Resources compiled by an Issuer for the purpose of distribution to individual consumers, directly or through intermediaries. The Resources in Releases are normally primarily sound recordings or music audio-visual recordings, but this is not invariably the case. The Release is not itself the item of trade (or “Product”). Products have more extensive attributes than Releases; one Release may be disseminated in many different Products.

+++

### Release Creator

Note:
Release Creator is an organisation which is the owner of copyrights in sound and/or music audiovisual recordings and/or exclusive licensees of copyrights in sound and/or music audiovisual recordings.

+++

### Resource

Note:
A digital fixation of an expression of an abstract Work (such as a sound recording, a video, an image, software or a passage of text). Resources are individual assets that make up a Release. Typical Resources are sound recordings, video clips and cover art images.

+++

### DDEX Data Dictionary

Note:
All messages developed within DDEX are based upon a common set of elements and their definitions. These are contained in the DDEX Data Dictionary available from ddex.net.

+++

### Contractually Mandatory

Note:
The messages defined in this standard contain fields with cardinality “0-1” or “0-n”. Therefore these fields are from the standard’s point of view, optional. Such fields may, however, be mandatory when a DDEX message is sent in a specific commercial context.
In such circumstances, a message is deemed conformant only if and when it contains all the “contractually mandatory” fields as agreed by MessageSender and MessageRecipient.

+++

### Message Choreography

Note:
A series of message calls and their responses which together communicate a more comprehensive level of meaning between the two business partners.

+++

### Non repudiation

Note:
Non repudiation is the assurance that someone cannot deny something. Typically, nonrepudiation refers to the ability to ensure that a party to a contract or a communication cannot deny the authenticity of their signature on a document or the sending of a message that they originated. In ERN standard, the concept of ensuring that a party cannot repudiate, or refute, the sending or receiving of a message.

---?image=/assets/image/DDEXOverview.jpg&size=auto 90%

---

## Abbreviations

- AVS - Allowed Value Set
- DDEX - Digital Data Exchange
- DSP - Digital Service Provider (incudes Mobile Service Providers)
- ERN - Electronic Release Notification
- GRid - Global Release Identifier
- ISRC - International Standard Recording Code (for Soundrecordings and Videos)
- KPTM - Koliko Para Toliko Muzike
- XSD - XML Schema Definition

---

## CIP Overview


---?image=/assets/image/CIPoverview.jpg&size=auto 90%

+++



### Web UI

A Web UI that would allow easy organisation of mismatched data is currently in development. It is intended for closed-circle use by Dubset database administrators.

---

## MediaNet ingestion

Note:
This guide is written for music labels and other content providers who want to submit new audio content to be added to the MusicNet content database for distribution by our retailers. Each shipment of digital or physical media that you send to us should include one or more XML files containing metadata that describes the new albums and tracks in that shipment.  This metadata will include artist and pricing information for each album and track as well as information about their distribution and usage rights.

+++

## Discussion

Note:
***Should I use an ISRC as the primary key for my database?***

No.

While ISRCs are the preferred identifier for identifying sound recording when communicating about releases and contained resources, they are not able to be used as primary keys in anyone's database.There are at least three reasons for this:

1. When receiving a DDEX message describing a sound recording the recipient cannot rely on this information to be 100% correct 100% of the time. The ISRC in such a message may, not be an ISRC after all (even if claimed to be one) or a duplicate code.
2. There are legitimate reasons why a message sender may send different resource files with the same ISRC: For instance there a sound recording may have different encodings or dynamic ranges when used the context of different releases.
3. There are legitimate reasons why a message sender may send different sound recording descriptions. For instance the duration may differ (for up to 10 seconds. according to the ISRC handbook) while the ISRC remains the same.

Because of these reasons it is essential that companies use an internally generated code as the primary key for each of the objects they handle. And may be necessary to keep a copy of a SoundRecodring descriptor for each Release.
The principle same applies for ISWCs for musical works, GRIDs for releases and all other creations.

---

## ERN Standard

Note:
The suite of messages contained in this Standard provides a mechanism for Release Providers (usually record companies) to inform their distribution partners (herein called Digital Service Providers (DSPs), including Internet Service Providers (ISPs) and Mobile Service Providers (MSPs)) about Releases that can be made available to the public as electronic Products. Such Releases can include, amongst others, Releases for mobile use, Releases for download under pay-as-you-go, advertisement-supported and subscription models and audiovisual Releases.
The messages will allow such standardised information flow about the Releases themselves (i.e. Release metadata) as well as information about the commercial terms under which such Releases can be made available.

+++

Sending or receiving a message using this standard does not necessarily imply, however, that all legal obligations are met for the Releases to be made available.

---

## ERN Message Choreography



---?image=/assets/image/ERNChoreo.jpg&size=auto 90%


+++

- Catalogue - A well-defined collection of Releases.
Note that the XML tags use the spelling “catalog” instead of catalogue.

+++

- NewRelease-Message - The Release Creator decides to make a Release available to the market and collates all necessary information about the Release. This does not necessarily include information about the commercial conditions under which the Release may be made available OR The Release Creator has decided on the commercial conditions under which the Release may be made available.

+++

- CatalogList-Message - The Release Creator wishes to inform a DSP (or any other party) about a catalogue it is (or may be) making available, containing a list of Releases that form part of a catalogue

+++

- PurgeRelease-Message - The Release Creator gains knowledge of a corrupt Release in the systems of a DSPs that cannot be taken down using the NewReleaseMessage

---
 
## The Baseline XML standard

+++

- The Electronic Release Notification Message Suite Standard (informally called the "Release Notification Message Standard") is one of several XML message formats published by DDEX.
- Release notifications are messages that record labels or aggregators send to distributors to inform them of new releases that are available for distribution, and the terms and conditions under which such releases can be made available.

Note:
The Release Notification Message Standard addresses the problem of a record company or aggregator having to send its products to distribution partners in multiple formats. It can be used for everything from a single release with a single deal, to the communication of a sales campaign that includes price changes over the course of time. Its three main elements are Resources, Releases, and Deals. Resources are the primary assets such as audio or video tracks, and also secondary assets such as cover images and PDF booklets. Releases are the principal products that encompass the resources, and Deals are the descriptions that define how a Release may be used.

+++

## Profiles that narrow down the baseline standard for use in specific use cases

+++

- The profile standards define subsets of the full standard for the most common types of Releases and Deals — thus making an implementation straightforward and comparatively simple — by differentiating different kinds of business models (e.g. Download Services, Subscription Streaming Services, Web Radio, etc.) and different kinds of Re-leases (e.g. albums, singles, classical albums, ringtones, etc.)

Note:
DDEX has defined a uniform message for the communication of Release details, including information about their parts, i.e. Resources (such as SoundRecording or Videos) and, in some circumstances also Musical Works from Release Creators (typically: record companies) to Release Distributors (typically: DSPs).
Such descriptions can, however, vary between different uses. For instance describing a Release that contains a single video ringtone track would differ greatly from a Release representing a digital equivalent of a 10-track pop album with previews. Similarly the commercial information regarding a subscription ringtone differs from commercial information regarding a pay-as-you go download.

+++

- Release Profiles
- Business Profiles

Note:
In order to aid companies that only wish to communicate a small subset of the types of products that the “full” DDEX standards allow, DDEX has developed a series of “profiles”. These profiles come in two flavours. Firstly “Release Profiles” that define subsets of Releases to be communicated along the music delivery chain and, secondly, “Business Profiles” that define subsets of the commercial information governing the distribution of such Releases. The Release Profiles primarily concern the ResourceList and ReleaseList sections of the ERN. The Business Profiles primarily concern the DealList section of the ERN.


+++

| Business Profile  | Release Profile  | "Target" ERN |
| ----------------- | ---------------- | ------------ |
| 1.0 |	1.0 | 3.3 and 3.4 |
|1.1 and 1.2 |	1.1 |	3.6 |
|1.2 |	1.2 |	3.7 |
|1.3 | 1.3	| 3.8 |

Note:
Over time, different versions of the Profiles and of the underlying XML standard were published and each profile standard has been written with a specific baseline XML standard (“ERN”) in mind. The table below provides this mapping (note that the table does not differentiate between version 3.4.1 and 3.4):
While this table indicates that the Release Profile in version 1.3 is specifically for the ERN standard in version 3.8, most of the profile rules can — and should! — also be applied to Release notifications in accordance with older ERN versions. While some of the rules cannot be used (because they depend on a new feature in the ERN standard), most rules can. And even those than cannot be followed strictly still provide good guidance as to what to do.

+++

## A choreography allowing sender and recipient to automate the exchange of information

+++

- The Release Delivery Choreography Standard provides a rich set of capabilities developed by DDEX that allows small niche firms to large multinational companies to utilise the Release Notification Standard.

+++

- The most basic specification — using FTP — is designed to be simple to implement, but has no additional functionality allowing customisation or visibility into the supply chain. At the other end of the scale, the more granular specification — using web services — allows considerable additional flexibility, much greater visibility and a more efficient supply chain.

+++

- DDEX recommends using acknowledgements when using the FTP choreographies to support non-repudiation.

Note:
DDEX messages convey, in effect, an extension or exhibit to the commercial contract between sender and recipient. It is therefore very important that the sender of a message knows that the message has arrived - and can prove that it has arrived. Equally, it is often important for a company to be able to show that he has not received a specific message. One example where the benefit of having non-repudiatable messages are take-down notices sent from a label to a DSP:

The sender needs to know that a take-down notice has been received by its down-stream partners to fulfil its legal obligation to, for instance, the artist that has requested the content to be taken down.
Equally, if the content hasn't been taken down, the DSP would want to be able to show that label has not sent the take-down notice and, thus, the fault is not with the DSP.

+++

- Takedown

- FTP profile of the message exchange choreographies do not mandate the use of the acknowledgement messages

Note:
DDEX's message exchange protocols support non-repudiation. When using web-services, non-repudiation is an essential part of the standard. However the FTP profile of the message exchange choreographies do not mandate the use of the acknowledgement messages. And it is these acknowledgement messages that deliver non-repudiation.
DDEX highly encourages implementers of the FTP-based message exchange choreographies to make use of the acknowledgements.

---

    
## Allowed Value Lists

+++

```
<DisplayArtist>
	<PartyName>
		<FullName>Matter</FullName>
	</PartyName>
	<ArtistRole UserDefinedValue="Remixer">UserDefined</ArtistRole>
</DisplayArtist>
```

Note:
The allowed values are listed, defined and provided through the DDEX Data Dictionary Standard in accordance with its latest version. Other values are not possible unless by using the mechanism described below:
This Standard does not explicitly list allowed values. The XML Schema files contain the allowed values at the time of writing of this Standard (see Annex A). Some of the allowed value sets contain a provision to either use a User Defined Value instead of a DDEX-defined value (in that case the MessageSender has to select the value “UserDefined” from the AVS and provide its own value in the XML attribute “UserDefinedValue”) or to augment a DDEX-defined value (in that case the MessageSender may not select the value “UserDefined” from the AVS but shall provide its additional information in the XML attribute “UserDefinedValue”). In either case the Namespace attribute shall be used to indicate where the UserDefinedValue is defined and maintained.

+++

## Allowed Values for Namespace Attributes

Note:
The Namespace attributes can be used to allow message parties to use proprietary value lists.
The allowed value for the Namespace attribute which is recommended to be used is the DDEX Party Identifier of the party controlling the proprietary allowed value, as defined in, and administered in accordance with the latest version of the DDEX Party ID Standard.

+++

## Describing Exploitations of Releases

+++

In DDEX Messages MessageSenders can use five allowed value sets to describe how Releases can be (or have been) exploited. They are:

- ReleaseType
- UseType
- CommercialModelType
- ConsumerInterfaceType
- Distribution Channel Type

Note:
The ReleaseType categorises the Release from the point of view of the ReleaseCreator. For example, a ReleaseCreator may create a Release for use as a RingbackTone on a mobile phone. This is distinct from the UseType which describes what a Consumer is allowed to do with a Release. For example, a Release created as a “normal” digital Album, might be used as a RingTone.
The third dimension, the Commercial Model type describes how Consumers pay for the Release, whether the transactions are based on subscriptions or whether the Consumer pays directly for each Release received.
The final two dimensions can be used to describe the devices on which Consumers consume (e.g. a portable device or a games console) the Releases and through what type of conduit they receive the Releases (e.g. a radio broadcast or the Internet). It is important to know that in many cases such detail will not be required and, thus, ConsumerInterfaceType and DistributionChannelType are optional fields in the messages.

+++

## Communication of Allowed Values defined in a later Standard

Note:
In order to communicate an allowed values defined by DDEX later than the message format used in the communication between two business partners the following approach shall be taken:
The element shall contain the value “UserDefined”;
The UserDefinedValue attribute shall be set to the value from the later standard; and
The Namespace attribute shall be set to the same value as defined as normative content for the MessageVersionId attribute for that standard.
    
---

## ERN Choreography: SFTP Exchange

+++

- Two Profiles using SFTP
- Location and owner of the SFTP server is not defined
- Structure of the SFTP severs and names for files are defined by this standard

Note:
This standard provides a standardised means for Release Creators to make Releases available via Release Distributors. It defines two Profiles using SFTP. A separate standard defines a message exchange protocol for web services.
This specification allows for the secure transmission of information and caters for non-repudiation requirements to be met.
While the location and owner of the SFTP server is not defined herein (this is left to be agreed by Release Creator and Release Distributor), the structure of the SFTP severs and names for files are defined by this standard.
At this stage, this standard does not address issues arising from data mismatches detected during the information exchange.

+++

## Choreography to Automate Information Exchange

+++

### FTP
### REST

Note:
DDEX defines two mechanisms to exchange DDEX messages between two business partners. As such it establishes a (reliable) "pipe" to transfer DDEX messages, other XML documents and/or files, including binaries containing, for instance, Releases or Resources.
The entry-level message exchange protocol is based on FTP, the File Transfer Protocol. For parties who wish to implement a more interactive method of exchanging information with their business partners, this standard defines a second message exchange protocol using REST-like web services.

+++

## Product Deliveries using FTP

- SFTP
- Messages should be ingested in order of folder timestamp
- Incoming and outgoing files should follow a standardised, descriptive naming convention, including version and/or timestamp

Note:
File Transfer Protocol (FTP) is the standard protocol for transferring files to and from remote machines running FTP service. FTP offers less interactivity for the communication between labels and DSP.
Secure File Transfer Protocol (SFTP) is similar to FTP except that it encrypts both the command that execute the file transfer, as well as the data being transferred, whereby reducing the chances of eavesdropping during transfers.
Unique upload and download folders should be created according to the choreography standard. The standard is available from URL.
Messages should be ingested in order of folder timestamp.
Incoming and outgoing files should follow a standardised, descriptive naming convention, including version and/or timestamp. Such a standard reduces the possibility of processing the same file multiple times. These are also defined in the aforementioned standard.

+++

## Product Deliveries using Web services

Not relevant.

---

## SFTP Release-by-Release Choreography

---?image=/assets/image/RbRChoreo.bmp&size=auto 90%

+++

### FtpAcknowledgementMessage

---?image=/assets/image/ACK.png&size=auto 90%

Note:
This standard does not define when the Release Creator shall start or finish to upload the next NewReleaseMessage (incl. all Resource files). Equally, this standard does not define when the Release Distributor shall start or finish its download.
In addition to the exchanged shown in the diagram above, the recipient of the NewReleaseMessage may use the same message for subsequent status updates (e.g. when, after reporting FileOK after ingestion, closer inspection shows deficiencies not detected previously.
The recipient of the FtpAcknowledgementMessage may remove a FtpAcknowledgementMessage from the SFTP server after an appropriate and mutually agreed period of time. The default period is one month.

+++

## SFTP Server Organisation

Note:
Each Release shall be placed into a separate folder of its own. The folder shall be named with the a priority indicator (see below), followed by an underscore character, the ReleaseId of the Release communicated followed by an underscore character and the date/time of creation in the form YYYYMMDDhhmmssnnn to indicate a sequence with YYYY indicating the year in which the Release is placed on the ftp server while MM and DD indicate the month and day, hhmmss indicate the hour (in 24 hours), minutes and seconds. Finally nnn indicate the millisecond in which the Release is placed on the ftp server.
The value for the priority indicator may be "P" to indicate the Release is deemed to be a priority delivery and "N" to indicate the Release is deemed to be a non-priority delivery. The meaning of priority in this context should be agreed by sender and recipient. Note that mixing non-priority and priority deliveries may cause problems, especially when no acknowledgements are used.
The NewReleaseMessage shall be placed into the same folder. Resource files shall be placed into a subfolder called “resources/”.
If possible, the ReleaseId used should be a GRid as defined in the GRid standard. However, if that is not possible, the Release Creator and Release Distributor shall mutually agree a different unique identifier.
The FtpAcknowledgementMessage shall be placed into a folder called acknowledgements/.

+++

## File Naming Conventions

+++

- The NewReleaseMessage shall be named as follows:
```
ReleaseId.Ext
```
+++

- Each Resource file shall be named as follows:
```
Label_ReleaseId_TechnicalResourceId_ResourceType_Hierarchy.Ext
```

### Label_ReleaseId_TechnicalResourceId_ResourceType_Hierarchy.Ext
+++

- The FtpAcknowledgement shall be named as follows:
```
ACK_YYYYMMDDhhmmssnnn_ErnMessageId.Ext
```

Note:

- ReleaseId being the identifier used in the NewReleaseMessage to uniquely identify the Release.
- Label being an optional, mnemonic token to identify the company compiling the Release. This element is primarily for human intervention and may only contain letters, digits and dashes (“-“)..
- TechnicalResourceId being an optional string, starting with the letter “T”, that is used in the NewReleaseMesage’s relevant XML tag of the same name to uniquely identify the Resource.
- ResourceType being an optional element to indicate the type of resource (typically where this is not clear from the Ext element). This may be a generic value such as "SoundRecording" or it may be used to designate a more specific type such as CoverArt or even an abbreviation such as WP for a wallpaper Resource. This element is primarily for human intervention.
- Hierarchy being an optional element to indicate where, in the hierarchy of the Release the Resource fits. This element should comprise of a sequence of three-digit, zero padded numbers separated by underscores (e.g. 008_015 for the 15th Resource in the 8th Resource Group). This Hierarchy element should correspond to the ResourceGroup composite in the NewReleaseMessage.
- YYYYMMDDhhmmssnnn being the date and time that the Release is placed on the ftp server.
- ErnMessageId being the ID used in the ReleaseNotificationMessage being acknowledged.
- Ext being the typical file extension for the Resource type (or .xml for the NewReleaseMessage or FtpAcknowledgement Message).

The Resource file name in accordance with this clause is only guaranteed to be unique and useful for the duration of the Release delivery (i.e until an acknowledgement has been sent).

+++

## Example of Server Organisation and File Naming Convention

Note:
<https://kb.ddex.net/pages/viewpage.action?pageId=7210306>

---

## SFTP Batch Release Choreography

---?image=/assets/image/SFTPBatch.bmp&size=auto 90%

Note:
The trigger to indicate that a Batch is complete is a ManifestMessage as defined in Clause 10 of this standard. In exceptional circumstances, such as for support human intervention, it is permissible to use a zero-byte semaphore file to indicate the upload is complete. This semaphore has to be used instead of an XML manifest formatted in accordance with Clause 10. The use of such a semaphore file may trigger a flag on the recipient’s side, indicating the manual nature of the override. The message is also depicted below.


---?image=https://kb.ddex.net/download/attachments/7210312/M.png&size=auto 90%

+++

## Batch Constraints

- The maximum size of a Batch is not defined in this standard but shall be agreed by Release Creator and Release Distributor before using this Profile.
- It is not permitted to include the same Release more than once in a single Batch
- YYYYMMDDhhmmssnnn

Note:
If the Release Creator wants to have several Batches “open” at the same time, it needs to ensure that no Release is contained in more than one Batch.
The maximum time a Batch may be kept “open” is a matter for Release Creator and Release Distributor to define in their commercial agreement.
To ensure sequential processing, a Batch is identified by the date and time of its creation in the form YYYYMMDDhhmmssnnn with

    YYYY being the year of Batch creation;
    MM being the month of Batch creation;
    DD being the day of Batch creation;
    hh being the hour of Batch creation;
    mm being the minute of Batch creation;
    ss being the second of Batch creation; and
    nnn being the millisecond of Batch creation.

The Release Creator shall make sure that for each of its Release Distributors the BatchId is unique.

+++

## SFTP Server Organisation

Note:
Each Batch shall be placed into a separate folder of its own. The folder shall be named with a priority indicator followed by an underscore character and the BatchId. Each Release within that Batch shall be placed into a separate folder using the ReleaseId of the Release as its name. A NewReleaseMessage for each Release shall be placed into that folder; Resource files shall be placed into a subfolder called “resources/”.
The value for the priority indicator may be "P" to indicate all Releases in the batch are deemed to be a priority delivery, M if some of the Releases are deemed to be a priority delivery whereas others are not, and "N" to indicate the none of the Release is deemed to be a non-priority delivery. The meaning of priority in this context should be agreed by sender and recipient. Note that mixing non-priority and priority deliveries may cause problems, especially when no acknowledgements are used.
The ManifestMessage, shall be placed into the root folder of the Batch.
If possible, the ReleaseId used should be a GRid as defined in the GRid standard. However, if that is not possible, the Release Creator and Release Distributor shall mutually agree a different unique identifier.
The FtpAcknowledgementMessages shall be placed into a folder called acknowledgements/.

+++

## File Naming Convention

Note:
The file name of the ManifestMessage for each Batch shall be the string BatchComplete_ followed by the BatchId (as defined above) and the .xml file extension. The same file name applied to the zero-byte semaphore discussed in Clause 8.1.
The file name of the FtpAcknowledgementMessage for each Batch shall be the string ACK_  the date and time that the Batch is placed on the ftp server, followed by an underscore and the ReleaseId. The file shall have an .xml file extension.
The NewReleaseMessages shall be named using the same ErnMessageId as used for the enclosing folder with an .xml file extension.

Example of Server Organisation and File Naming Convention

<https://kb.ddex.net/pages/viewpage.action?pageId=7210313>

+++

## Hard Disk Delivery

Not relevant.

---

## NewReleaseMessage

---?image=/assets/image/NRM.png&size=auto 90%

+++

## Track Releases

- The general rule is that a NewReleaseMessage must contain the main Release (such as an album) plus one Track Release for each of the primary Resources that make up the Main Release.

Note:
Thus a ten-track album will lead to a NewReleaseMessage containing eleven Releases.
Track Releases are single-track Releases that are generated to allow "un-bundling". The inclusion of each Track Release does not define whether or not the Track Release is actually available to be un-bundled: that is subject to the Deal information (only those Track Releases for which a ReleaseDeal is provided may be made available to consumers in accordance with this ReleaseDeal).

+++

## Pointing from Track Release to Main Release


Note:
The NewReleaseMessage allows for a Release to "point" to another release using the RelatedRelease composite. In some cases this has been used to indicate that a Track Release has been ‘un-bundled’ from an album Release. This should, however, only be done if the album release is not the Main Release in the same NewReleaseMessage.
Therefore, the Track Release shall not point to the Main Release it comes from if they are both communicated in the same NewReleaseMessage.

---

## Structure of the NewReleaseMessage

+++

- Message Header
- Update Indicator
- Resource List
- Release List
- Deal List

Note:
The DDEX message to communicate details about a release and its availability is the NewReleaseMessage defined in the Electronic Release Notification Message Suite Standard (formerly referred to as "ERN").
The NewReleaseMessage is the industry standard mechanism to allow content owners to inform DSPs about new releases that are available for distribution, and the terms and conditions under which releases can be made available. It includes complete metadata about the release and all resources contained within the release. In addition, it includes deals that describe when, where and how the release can be made available.
The NewReleaseMessage is a XML specification defined and maintained by DDEX. The NewReleaseMessage consists of five individual sections of message and metadata elements that are interrelated. All together they make up the NewReleaseMessage. A NewReleaseMessage will contain the details for an individual product (e.g. album, single, bundle) and each of its components (e.g. tracks). The message will not contain multiple products, related or non-related.

+++


## XML Schema

The XML Schema files for all DDEX standards are available in two forms

+++

- Zip Archive
- On ddex.net

Note:

Implementers can download a zip archive with all relevant XML Schema definitions from the same page where the relevant standard itself is available for download. 
These files are specifically designed to be downloaded and used when implementing the relevant DDEX standards.

Implementers can also access all XML Schema files from the appropriate subfolder from http://ddex.net/xml (e.g. http://ddex.net/xml/ern/351/ for Version 3.5.1 of the Release Notification Message Suite Standard (a.k.a. ERN).
It is these locations that users of the standard are expected to use in the top level tag of a DDEX message exchanged commercially:
The order of attributes within an XML tag are of no significance.
For human consumption hyphens may be added to data. Therefore, the HTML/PDF export of the ID data may contain hyphens whereas the XML export MUST NOT.

+++

## Message Header

Note:
The Message Header indicates the sender and recipient of the NewReleaseMessage Message.
The sender and recipient are each defined by a unique DDEX Party ID (DPID). The Message Header also provides a creation date which is a timestamp of when the message was created. DPIDs can be obtained at URL.

+++

## Update Indicator

Note:
The NewReleaseMessage contains a field UpdateIndicator. This field has been deprecated and users are strongly discouraged to make use of it. DDEX will remove the field in one of its futer releases of the NewReleaseMessge.
Rationale
The only purpose for such an UpdateIndicator field would be to indicate to the recipient that it already has received and ingested a message containing the same data elements and that the current message provides an update to the older message,
This assumes, therefore, that

> The sender knows that it has already send a message about the same, in our case, Release;
    The recipient has received this message;
    The recipient has ingested this message (the original message may still be in a ingestion queue when an urgent update is sent); and
    The recipient still has  the Release in its database when the update message arrives.

A recipient only has any benefit if all of these conditions are met – if only one is not met, receiving a message that purports to be an update is, in essence a new message. Any decent implementation therefore still needs to check whether the entities communicated in a NewReleaseMessage is already in the database – thus sidelineing, if not ignoring, the UpdateIndicator.

+++

## Resource List

Note:
The Resource List provides details of the different assets that make up the entire release. Typical resources are sound recordings, videos and images. Each resource will have a unique reference anchor within the message (e.g. A1, A2, A3) which corresponds to the track number (e.g. track 1, 2, 3). The resource references will be referenced later in the Release section. The metadata defined in the Resource includes ISRC, artist, title and contributors.
Also contained in the Resource section is the Technical Resource Details, which references the specific binary files with details including the codec type and bit rate being delivered to the partner. The Technical Resource Details will provide information about both the full length and preview clip binary files.
Artwork will be a resource listed after the track resources. Cover artwork will be identified as an image resource with a resource reference after the last track resource. For example, on a 10-track album resource reference A11 would be the image resource relating to the cover artwork.
The exact fields to to be used in a specific business case (e.g. describing a resources for a Ringtone release or describing resources for a Classical Album) is defined in the relevant Release Profile standard.

+++

## Release List

Note:
The Release List section defines the different releases that make up the "product" being delivered. For example, a standard ten-track album will contain one album release and 10 track releases, for a total of 11 Releases. The album level release is represented by the release reference R0 and the tracks by release reference R1, R2, R3, etc. dependent upon their order in the track listing. For each Release, the resources ("tracks") included in the respective release are listed along with their sequence. These resources are referenced back to resources in the Resource List. For example, the Release for Track 1 references the Resource identified by Resource Reference A1, Track 2 by Resource Reference A2, Track 3 by Resource Reference A3, etc.
The metadata defined for each Release includes one or more Release identifiers (ICPN, UPC, EAN, GRid, ISRC), artist, title, label, genre, parental warning and P&C credits. A Release does NOT contain any information regarding the business terms associated with its commercial exploitation and usage.
The exact fields to to be used in a specific business case (e.g. describing a Ringtone release or describing or a Classical Album) is defined in the relevant Release Profile standard.

+++

## Deal List

Note:
The Deal List provides the availability of the Releases. It describes when, where and how the releases can be made available. The Deal List provides a list of Release Deals, each having a reference back to a Release and defining the deal terms. Each Release Deal describes the commercial terms and usage information for each available Release. This includes the territories the Release can be made available, commercial model, usage type, pricing and deal validity period for each release listed. The deal start date usually represents the Release Date when the release can be made available to consumers in the specified territory.
Each Release Deal references back to the relevant Release using Release References. For example, the Release Deal for the Album Release references the Release identified by Release Reference R0, Track 1 by Release Reference R1, Track 2 by Release Reference R2, etc.
Within a Deal, a pre-order date can be specified. The pre-order date defines when the Release can be made available for pre-order, but not fulfilled to the consumer until the Deal start date. A pre-order preview date can also be specified. This defines if and when the preview clips can be made available to the consumer during the pre-order period.
Deals are also used to notify of Takedowns. A takedown is the blanket loss of all rights and can be applied to specific territories or all territories. A takedown implies that all previous deals are cancelled in the specified territories on the takedown deal start date.
The exact fields to to be used in a specific business case (e.g. describing a Ringtone Deal or a Subscription Download) is defined in the relevant Business Profile standard.


