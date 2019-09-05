# TogoVar RDF data model

## Variations in TogoVar RDF

### Single Nucleotide Variation (SNV)

<img width="800" alt="figure 2" src="figures/togovar-rdf-figures.002.png">

```turtle
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix tgv: <http://togovar.biosciencedbc.jp/variant/> .
@prefix tgvo: <http://togovar.biosciencedbc.jp/ontology/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix m2r: <http://med2rdf.org/ontology/med2rdf#> .
@prefix hco: <http://identifiers.org/hco/> .
@prefix faldo: <http://biohackathon.org/resource/faldo> .
@prefix dcterms: <http://purl.org/dc/terms/> .

tgv:tgv28138048 a obo:SO_001483, m2r:Variation ;
  dcterms:identifier "tgv28138048" ;
  faldo:location [
    a faldo:ExactPosition ;
    faldo:position 4821390 ;
    faldo:reference hco:1\#GRCh37
  ] ;
  m2r:referece_allele "C" ;
  m2r:alternative_allele "T" ;
  m2r:referece_allele_vcf "C" ;
  m2r:alternative_allele_vcf "T" .
```

### Insertion

```turtle
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix tgv: <http://togovar.biosciencedbc.jp/variant/> .
@prefix tgvo: <http://togovar.biosciencedbc.jp/ontology/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix m2r: <http://med2rdf.org/ontology/med2rdf#> .
@prefix hco: <http://identifiers.org/hco/> .
@prefix faldo: <http://biohackathon.org/resource/faldo> .
@prefix dcterms: <http://purl.org/dc/terms/> .

tgv:tgv00000000 a obo:SO_000667, m2r:Variation ;
  dcterms:identifier "tgv28138048" ;
  faldo:location [
    a faldo:InBetweenPosition ;
    faldo:after 4 ;
    faldo:before 5 ;
    faldo:reference hco:1\#GRCh37
  ] ;
  m2r:referece_allele "" ;
  m2r:alternative_allele "CT" ;
  m2r:referece_allele_vcf "T" ;
  m2r:alternative_allele_vcf "TCT" .
```

### Insertion with undetermined insertion position


```turtle
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix tgv: <http://togovar.biosciencedbc.jp/variant/> .
@prefix tgvo: <http://togovar.biosciencedbc.jp/ontology/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix m2r: <http://med2rdf.org/ontology/med2rdf#> .
@prefix hco: <http://identifiers.org/hco/> .
@prefix faldo: <http://biohackathon.org/resource/faldo> .
@prefix dcterms: <http://purl.org/dc/terms/> .

tgv:tgv00000000 a obo:SO_000667, m2r:Variation ;
  dcterms:identifier "tgv28138048" ;
  faldo:location [
    a faldo:Region ;
    faldo:begin [
      a faldo:ExactPosition ;
      faldo:position 11 ;
      faldo:reference hco:1\#GRCh37
    ] ;
    faldo:end [
      a faldo:ExactPosition ;
      faldo:position 16 ;
      faldo:reference hco:1\#GRCh37
    ] ;
  ] ;
  m2r:referece_allele "CTCTCT" ;
  m2r:alternative_allele "CTCTCTCTCTCT" ;
  m2r:referece_allele_vcf "TCTCTCT" ;
  m2r:alternative_allele_vcf "TCTCTCTCTCTCT" ;
  m2r:vcf_position 10 .
```
