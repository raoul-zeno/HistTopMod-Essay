### Historische Themenmodellierung mit dem Gesamtkorpus des Deutschen Textarchivs ###
In dieser Seminararbeit wird versucht, eine historische Fragestellung durch die Verwendung einer eigenen KI-Implementation zu beantworten. Als Datenquelle wird der Gesamtkorpus des Deutschen Textarchivs verwendet.
Die Fragestellung lautet: "Wie hat sich das Thema 'Freiheit' über den Zeitraum vom 16. bis zum frühen 20. Jahrhundert im Kontext gebrauchsliterarischer, zeitschriftlicher, wissenschaftlicher und belletristischer Texte entwickelt".

Bei dieser Arbeit wird das Themenmodellierungs-Model BERTopic verwendet, um mithilfe von Machine Learning diese Fragestellung zu beantworten. Das Ziel ist es, dass der Begriff "Freiheit" eingegeben werden kann, und als Output eine Visualisierung von weiteren Begriffen produziert wird, welche Aufschluss über den textuellen Kontext geben sollten. Jegliche Programmierung wird dabei von mir gemacht.

Dieses README dient der Dokumentierung der einzelnen Arbeitsschritte, vor allem im Zusammenhang mit dem Programmier-Teil der Arbeit. So sollte die Nachprüfbarkeit der Seminararbeit gewährt bleiben.

# Provisorisches Vorgehen (Stand 18.12.2024) #
1. Samplen von Texten nach Dekaden und Genres, um mögliche Eigenarten zu entdecken und dokumentieren. Ungeklärt: Sicherstellung, dass keine Bias vorhanden sind (Dekaden und Genres). Eventuell sinnvoll, zwei verschiedene Dokumentationen zu brauchen: Eine für Dekaden und eine für Genres. Bei den vier vorhanden Genres kann die Zufallsstichprobe zudem in weitere Subgenres gegliedert werden. Falls Dekaden und Genres zusammengenommen werden: geschichtete Zufallsstichprobe. Mit genügend Sampling kann dieser Prozess eventuell automatisiert werden.
2. Preprocessing der Texte. Mithilfe der Erkenntnisse von Schritt 1 kann das Preprocessing der Texte beginnen. Dabei werden zumindest vorverarbeitet:
    - Orthographische Variationen
    - Ligaturen
    - Normalisierung von archaischen Begriffen
    - evtl. Lemmatisierung
    - Filtern von stopwords
    - Löschen von unnötigen Whitespaces
    - Umwandeln in Fliesstext
3. Bei einem Vorversuch wurde erkannt, dass die meisten Transformer nicht genügend gut arbeiten mit deutschen historischen Texten. Deshalb wird in diesem Schritt versucht, ein eigenes Embedding herzustellen. In Frage kommen die Modelle FastText, Word2Vec. Diese können dann mit BERT noch finegetuned werden.
4. Verwenden von BERTopic mit dem Embedding von Nr. 3. 
5. Iteratives Finetuning, bis die Outputs sinnvoll sind.