# Instagram_Photos_Analysis_Over_Time
Analysis of Instagram photos taken by visitors of the "Woodland Park Zoo" in Seattle over different periods of time, whose location is the zoo and/or the zoo is tagged in.


# Search Engine on Wikipedia
By this project we implemented a search engine on Wikipedia, as we asked to do under the "Information Retreive" course at BGU.
* **Our engine supports in returning a result by _1.6 seconds_ for an average and we can commit _72.62%_ of successful searching.**

## The Code Structure

| Class | Description | Major Methods |
| --- | --- | --- |
| search_frotened | here the search is created. | search func (also calculate the BM25 and Stemming, it's time complexity is measured), Search Body Func (search on the bodies of the all documents of the corpus, which are relevant to the query), Search Title Func (the same as the body func on the titles of the documents) and Search Anchor Func (search on the anchors of each document, while the most intresting is the page who is pointered by other), Page Rank Func (get a list of pageranks and return the page rank for a doc), Page View Func (get a list of pagevies and return the page view for a doc) |
| search_title | here the search funcs for the docs' titles | get_posting_gen func get the title index and query and return a dict which its keys are the all terms and its values the relevant posting list, get_generate_relevant_dict which return a dict so that each term with its relevant documents, get_candidate_documents_and_scores func which return a dict which its keys are pairs of (doc_id, term) and its values are the tf-idf score |
| search_body | here the search funcs for the docs' bodies | get_posting_gen func which return a dict with posting list for all terms and etc |
| search_anchor | here the search funcs for the docs' anchors | get_posting_gen func which return a dict with posting list for all terms, get_generate_relevant_dict_anchor which return a dict so that each term with its relevant documents and etc |
| BM25 | here the calculate of the BM25 measurement | it is used for calculating the BM25 score for each document by k and b parameters. For this calculation we calculater inadvanced the vector size for each document.|
| Tokenizer | it's has the all tokens after cleaning things, such as stopwords | tokanizing and stemming if necessary |
| Inverted Index gcp | a class we got by this project | By changing it a little so it could read from our bucket. |


| Pickle File's Name | The Information Inside |
| --- | --- |
| ID_Title | a dictionary which it's keys are doc_id, and the values are the titls' doc correspondingly |
| PageView | a dictionary which it's keys are doc_id, and the values are the page view of the document |
| DL_Title | a dictionary which it's keys are doc_id, and the values are length of the doc's title |
| DL_Body | a dictionary which it's keys are doc_id, and the values are length of the doc's body |
| normalized_doc_vec | a dictionary which it's keys are doc_id, and the values the vector size of each of them |


| CSV File's Name | The Information Inside |
| --- | --- |
| PageRank | id, page rank table |


![This is an image](https://github.com/NoaMagrisso/Instagram_Photos_Analysis_Over_Time/blob/main/visualizations/summer_season.JPG)
