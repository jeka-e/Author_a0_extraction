# Extraction of Author-A0 Polarity in Sentiment Frame

3rd year Term Paper, final grade 9

The paper is about developping a method for automatic extraction of Sentiment Frames. Sentiment Frames, coming from Fillmore's frame semantics, include predicates, which consist of verb describing situation and its participants, each of the participants is assigned positive or negative connotations (if any) between each other and author. For example: 

"title": игнорировать ___'ignore'___

"roles": {

	"a0": "кто игнорирует" 'one who ignores',
	
	"a1": "объект игнорирования, что или кого игнорирует" 'one who/what is ignored'
},

"frames": {

	"polarity": 
	
		[["a0", "a1", "neg", 1.0],
		
		["a1", "a0", "neg", 1.0],
		
		["author", "a0", "neg", 0.7]],
		
	"effect":
	
		[["a1", "-", 1.0]],
		
	"state":
	
		[["a1", "neg", 1.0]]
}
 
 
This research concerns author-a0 polarity. The main idea was based on the fact that author relation polarity matches with an average a0-participant polarity in all its contexts for each verb. So, the a0, who ignores someone, would often be negative, thus author-a0 relation is negative.

I utilized Bert-Embedder model from DeepPavlov to obtain a0 vector representations, then computed an average a0 embedding for every verb. Its polarity was defined with semantic axis method, proposed in (Jurafsky 2020, p.399). 

The results were not very clear as I was lacking data (had to use syntactically parsed corpora to extract a0-participant), though it surely had some perspectives. 


