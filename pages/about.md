---
title: About
layout: about
permalink: /about.html
# include CollectionBuilder info at bottom
credits: true
# Edit the markdown on in this file to describe your collection
# Look in _includes/feature for options to easily add features to the page
---

{% include feature/jumbotron.html objectid="/assets/img/isu-thesaurus.jpg" %} 

{% include feature/nav-menu.html sections="Summary;Contact us;User guide;Maintenance and development;Metadata elements (properties);Acknowledgments;References and further reading" %}
## Summary

The Iowa State University Library Vocabularies (ISULV) are curated lists of preferred subject headings, genre terms, names, and other concepts used to describe resources created by and about the Iowa State University community. Each term has a structured authority record containing a uniform resource identifier (URI) and contextual information, including links to related concepts if applicable.

These records are published as linked data on the open web. Specifically, the vocabularies and each of their constituent concepts are available as HTML and JSON-LD. They are accessible and usable by humans and machines at Iowa State and beyond.
### Contact us

Learn more about Metadata Services at Iowa State University Library at our [department page](https://www.lib.iastate.edu/about-us/departments/metadata-cataloging).

To suggest additions or corrections, email [metadata@iastate.edu](mailto:metadata@iastate.edu).

## User guide

Metadata creators can use this site to select concepts for use in metadata for digital collections, finding aid descriptions, and bibliographic records. Researchers and writers can discover and use preferred subject terms and names for people and groups. Anyone can explore concepts and resources associated with the Iowa State community. 

### Items

Find information about each term on individual item pages—for example, [4-H clubs](https://digital.lib.iastate.edu/isulv/items/isut001.html).

On these pages, linked values point to related terms in ISULV, external authority records, or related resources.

To aid your selection of a term, review the definition, usage notes, related terms, and other information on the page. Be advised that some usage notes recommend the assignment of multiple related terms.

For details about each property, see the [Metadata elements (properties)](#metadata-elements-properties) section.

### Menus

<div class="row justify-content-center py-4">
    <div class="col-md-7">
        <div class="table-responsive">
            <table class="table table table-striped">
                <tbody>
                    <tr>
                        <th scope="row">Browse</th>
                        <td>Explore all terms in all vocabularies or filter to search by keyword.</td>
                    </tr>
                    <tr>
                        <th scope="row">Data</th>
                        <td>View vocabulary metadata in a table or download it as a CSV or Excel file.</td>
                    </tr>
                    <tr>
                        <th scope="row">Locations</th>
                        <td>Browse locations associated with vocabulary terms.</td>
                    </tr>
                    <tr>
                        <th scope="row">Terms</th>
                        <td>Peruse an A–Z list of all vocabulary terms.</td>
                    </tr>
                    <tr>
                    <th scope="row">Vocabularies</th>
                        <td>See all vocabularies included in the collection. Individual vocabulary pages contain a description of the vocabulary and lists of constituent terms.</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>

## Maintenance and development

This open collection of linked data vocabularies is a project of the Iowa State University Library.

The Metadata Services department maintains the vocabularies included on this site. Staff periodically review terms, update and enhance metadata, and add new terms and vocabularies.

Olivia Wikle, head of Digital Scholarship and Initiatives, developed this website. For technical information, see the Technical Credits—CollectionBuilder section. The Library IT department supports the static server that hosts this site.

Vocabularies in development:
- Names associated with the Iowa State University community, including department names
- Supplemental or alternative subject terms to improve discovery
- Genres used to categorize materials in Special Collections and University Archives

Additional development efforts:
- [ISULV-reconcile](https://github.com/isu-meta/isulv-reconcile), a reconciliation service for use with [OpenRefine](https://openrefine.org/)
- Interlinking with [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page) and [ORCID](https://orcid.org/)
- [Wikidata property for ISULV identifiers](https://www.wikidata.org/wiki/Property:P13388)

## Metadata elements (properties)

Each preferred term in the Iowa State vocabularies is described by metadata elements, or properties, following the [Resource Description Framework (RDF)](https://www.w3.org/TR/rdf11-primer/) model for linked data. RDF is used to publish and interlink data on the open web. RDF allows us to make statements that express relationships between resources or concepts, such as vocabulary terms. These statements are structured as triples made up of a subject, a predicate, and an object: 

- Subject—what the concept is
- Predicate—how the subject relates to the object
- Object—a value that describes the subject

Subjects, predicates, and objects are ideally expressed as URIs (Uniform Resource Identifier) or IRIs (International Resource Identifier). Objects also can be a literal value (e.g., a string of text). Multiple triples interlinking together form a knowledge graph.

In the Iowa State vocabularies, each term can be described by triples made up of a subject (the term itself), a predicate (property), and an object (value). This table lists our selected properties and their possible values. To facilitate interlinking among concepts within the vocabularies and on the open web, properties were chosen from several linked data schemas, including [Dublin Core Metadata Initiative (DCMI) Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/), [Simple Knowledge Organization System (SKOS)](https://www.w3.org/2009/08/skos-reference/skos.html), and [Metadata Authority Description Schema in RDF (MADS/RDF)](https://id.loc.gov/ontologies/madsrdf/v1.html). 

<div class="row justify-content-center py-4">
    <div class="col-md-8">
        <div class="table-responsive">
            <table class="table table table-striped">
                <thead>
                    <tr>
                        <th scope="col">Property label</th>
                        <th scope="col">Property URI</th>
                        <th scope="col">Value</th>
                    </tr>
                </thead>
                <tbody>
                    {% for element in site.data.elements %}
                    <tr>
                        <th scope="row">{{ element.property-label}}</th>
                        <td><a href="{{ element.property-uri }}">{{ element.property-uri }}</a></td>
                        <td>{{ element.value }}</td>
                    </tr>
                    {% endfor %}
                </tbody>
            </table>
        </div>
    </div>
</div>

__Note:__ The Geodetic Datum element is displayed when an item's metadata includes latitude and longitude. This element indicates the system used for representing geographic coordinates—for example, WGS 84 (World Geodetic System 1984). Geodetic Datum is not included as a property in ISULV's JSON-LD knowledge graph and so is not listed in the table above. 

## Acknowledgments

The Metadata Services librarians at Iowa State University Library (Heather Campbell, Christopher Dieckman, Kelly Hyland, Sylvie Manuel, Nausicaa Rose, and Hema Thulsidhos) are grateful to all our colleagues who contributed to the development of this project. Our former department head, Harriet Wintermute, proposed the idea of a local linked data vocabulary. Olivia Wikle tapped her CollectionBuilder expertise to bring it to fruition. The ISU Thesaurus Working Group developed a local collection of subject terms, and Amy Bishop, Rosalie Gartner, and Laura Sullivan provided recommendations. Lenard Kluck launched our names vocabulary by extracting and organizing data from our digital collections. Haylee Sheppard designed a brilliant banner illustration. Nausicaa Rose built a nifty [reconciliation service](https://github.com/isu-meta/isulv-reconcile). Chris Dieckman and Kelly Hyland designed a data model for polyonymous academic departments. Hema Thulsidhos compiled rights statements and accessibility terms. Colleagues in Oklahoma (Megan Macken, Lulu Zilinskas, and Kaitlyn Palone) shared inspiration and interlinking opportunities through the [Tribal Nations in Oklahoma Metadata](https://oms.library.okstate.edu/s/tribal-nations-metadata/page/home) website.

In addition, we thank the many representatives of Indigenous communities who responded to our outreach requests. Read more about this effort in our [Resources and Services for Iowa Indigenous Peoples LibGuide](https://go.iastate.edu/UAREL3).

## References and further reading

Campbell, Heather, Christopher Dieckman, Nausicaa Rose, Hema Thulsidhos, and Harriet Wintermute. “Library Guides: Resources and Services for Iowa Indigenous Peoples.” Accessed March 8, 2024. <https://instr.iastate.libguides.com/iowa-indigenous/intro>.

Carlson, Scott, Cory Lampert, Darnelle Melvin, and Anne Washington. Linked Data for the Perplexed Librarian. ALCTS Monograph. Chicago: ALA Editions, 2020.

Dublin Core Metadata Initiative. “DCMI Metadata Terms.” Accessed March 11, 2024. <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/>.

Fox, Violet. “Thing 15. Ethics of Linked Data.” Minitex. Accessed March 8, 2024. <https://minitex.umn.edu/services/digital-initiatives-metadata/23-linked-data-things/thing-15-ethics-linked-data>.

Library of Congress. “MADS/RDF (Metadata Authority Description Schema in RDF).” LC Linked Data Service: Authorities and Vocabularies. Accessed March 8, 2024. <https://id.loc.gov/ontologies/madsrdf/v1.html>.

Minitex. “23 Linked Data Things.” Accessed March 8, 2024. <https://minitex.umn.edu/services/digital-initiatives-metadata/23-linked-data-things>.

University of Houston Libraries. “Cedar: University of Houston Libraries Vocabularies.” Accessed March 8, 2024. <https://vocab.lib.uh.edu/en.html>.

W3C. “RDF 1.1 Primer,” 2014. <https://www.w3.org/TR/rdf11-primer/>.

W3C. “SKOS Simple Knowledge Organization System Namespace Document--HTML Variant,” August 18, 2009. <http://www.w3.org/2004/02/skos/core.html>.

“Western Name Authority File.” J. Willard Marriott Library Exhibits. Accessed March 8, 2024. <https://exhibits.lib.utah.edu/s/wnaf/page/welcome>.
