## Lab Report 3 -- Researching Commands

> In this report, I choose **grep** command as the topic

### Option1: -h
  *It will finds the line contains the target, and display the line without printing the filename*

Example1: 
```
command:
grep -h "China" travel_guides/berlitz1/HistoryHongKong.txt

result:
        entryway to China for Westerners, begins in 1841 with the British
        China, it made local headway, evidenced today by the numerous Catholic
        attempt to open trade with China in 1793 continued to prevail: “We
        Moreover, China would accept nothing but silver bullion in
        while China outlawed the trade in 1799, local Cantonese officials were
        did to China, and asking for an end to the opium trade; his arguments
        Nanking was threatened. In the Treaty of Nanking (1842) China was
        mainland China the Communist government abolished it when they came to
        harbor. In 1898, under the Convention of Peking, China leased the New
        China. By the eve of World War II, the population was more than one and
        China’s civil war sent distressing echoes to Hong Kong.
        Republic of China was proclaimed in 1949, the total population of Hong
        1970s Hong Kong became the conduit for China’s goods, investment, and
        space. In 1962 the colonial authorities closed the border with China,
        China in 1997. For its part, China declared Hong Kong a “Special
        at least 50 years after 1997. Although China’s Basic Law promised that
        and thousands of people, anxious about their future under China’s rule,
        China. Some companies moved their headquarters out of Hong Kong.
        Since the handover in July 1997, China has generally
```
This example searches the word *China* in the file HistoryHongKong.txt. It can search whether a file contains a key word and where it is.

Example2:
```
command:
grep -h "Lucayans" travel_guides/berlitz2/*.txt

result:
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the 
```
This examples searches the word *Lucayans* from all txt files in the folder berlitz2, which can helps us find the location of the key word
when we don't know where it appears in the folder.

### Option2: -n
  *It prints out matched line and its line number*
Example1:
```
command: 
grep -n "Lucayans" travel_guides/berlitz2/*.txt

result:
travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
This examples still searches Lucayans from all txt files in berlitz2 and prints the line number, which helps us find the precise location of the key word.

Example2:
```

```
