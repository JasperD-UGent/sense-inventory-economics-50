# sense-inventory-economics-50
This repository contains the sense inventory used in the NLP4CALL2022 paper by Jasper Degraeuwe and Patrick Goethals. The inventory consists of 50 ambiguous Spanish words related to the domain of economics.
## Sense inventory file
The file <code>senseInventory_economics_50.json</code> contains the sense inventory as a Python dictionary. The dictionary has 50 keys, one for each ambiguous item. The structure of the dictionary is illustrated by means of a simplified example (for the ambiguous items <code>divisa</code> and <code>subida</code>) in the following code block:
```python
d_sense_inventory = {
    "divisa|NOUN|f": {
        "1": {
            "description_ES": "moneda extranjera",
            "l_example_sents": [
                {
                    "l_toks": ["La", "intervención", "del", "Banco", "de", "España", "en", "defensa", "de", "nuestra", "moneda", "está", "reduciendo", "las", "reservas", "de", "divisas", "."],
                    "idx_ambig_item": 16,
                    "source": "Clave"
                }
            ]
        },
        "2": {
            "description_ES": "símbolo, eslogan",
            "l_example_sents": [
                {
                    "l_toks": ["El", "lema", "‘", "libertad", ",", "igualdad", ",", "fraternidad", "’", "fue", "la", "divisa", "de", "la", "Revolución", "francesa", "de", "1789", "."],
                    "idx_ambig_item": 11,
                    "source": "Clave"
                }
            ]
        }
    },
    "subida|NOUN|f": {
        "1": {
            "description_ES": "(terreno inclinado en que se hace un) paso a un lugar más alto",
            "l_example_sents": [
                {
                    "l_toks": ["La", "subida", "del", "último", "trecho", "de", "la", "montaña", "fue", "agotadora", "."],
                    "idx_ambig_item": 1,
                    "source": "Clave"
                },
                {
                    "l_toks": ["Esta", "subida", "es", "demasiado", "pronunciada", "para", "ir", "en", "bicicleta", "."],
                    "idx_ambig_item": 1,
                    "source": "Clave"
                }
            ]
        },
        "2": {
            "description_ES": "aumento",
            "l_example_sents": [
                {
                    "l_toks": ["Una", "subida", "de", "adrenalina", "inundó", "sus", "poros", ",", "provocando", "que", "su", "respiración", "se", "entrecortase", "."],
                    "idx_ambig_item": 1,
                    "source": "SCAP"
                }
            ]
        }
    }
}
```
The main keys of the dictionary are strings containing the lemma, part-of-speech tag and gender of the ambiguous item separated by a vertical bar (e.g. <code>"divisa|NOUN|f"</code>). The value belonging to those keys is a nested dictionary containing the information per sense of the ambiguous item. The keys of this nested dictionary are strings containing the sense ID (starting at <code>"1"</code>). The value linked to the keys is again a nested dictionary, with <code>"description_ES"</code> and <code>"l_example_sents"</code> as its keys. The <code>"description_ES"</code> entry contains a short description of the sense in Spanish, while the <code>"l_example_sents"</code> entry consists of a list of dictionaries including the prototypical example sentence(s) for that sense. Each example sentence dictionary contains the list of tokens of the sentence (accessible through the key <code>"l_toks"</code>), the index of the ambiguous item in the sentence (accessible through the key <code>"idx_ambig_item"</code>), and the source the sentence comes from (accessible through the key <code>"source"</code>).
## Acknowledgements
For the elaboration of the sense inventory, we relied on the [Clave dictionary](https://www.grupo-sm.com/es/book/diccionario-clave-lengua-espa%C3%B1ola), to whose contents we have access thanks to a research collaboration with the [Fundación Santa María](https://www.fundacion-sm.org/).
