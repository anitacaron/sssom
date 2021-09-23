all: ssom.owl
ssom.owl: sssom_vocab.owl sssom_metadata.owl
	robot merge -i sssom_vocab.owl -i sssom_metadata.owl \
	annotate --ontology-iri "http://purl.org/sssom/sssom.owl" -o $@
sssom_%.owl: sssom_%.tsv
	robot template --template $< \
	--prefix "sssom: http://purl.org/sssom/meta/" --prefix "SSSOMC: http://purl.org/sssom/type/" \
  --output $@
sssom_gh_table:
	perl scripts/gh_table.pl sssom_metadata.tsv