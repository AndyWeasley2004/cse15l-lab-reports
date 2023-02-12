# Lab Report 3 -- Researching Commands

> In this report, I choose **grep** command as the topic

## Option1: -h
  *It will finds the line contains the target, and display the line without printing the filename.*
  
  *Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/*

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
This example searches the word *"China"* in the file HistoryHongKong.txt. It can search whether a file contains a key word and where it is.

Example2:
```
command:
grep -h "Lucayans" travel_guides/berlitz2/*.txt

result:
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the 
```
This examples searches the word *"Lucayans"* from all txt files in the folder berlitz2, which can helps us find the location of the key word
when we don't know where it appears in the folder.

## Option2: -n
  *It prints out matched line and its line number.*
  
  *Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/*

Example1:
```
command: 
grep -n "Lucayans" travel_guides/berlitz2/*.txt

result:
travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
This examples still searches *"Lucayans"* from all txt files in berlitz2 and prints the line number and the file it locates, which helps us find the precise location of the key word.

Example2:
```
command:
grep -n "opium" travel_guides/berlitz2/China-History.txt

result:
50:The soaring demand in Europe for Chinese tea, silk, and porcelain brought increasing pressure for freer trade. However, the Chinese were stubborn. Needing no commodities, they would accept only silver bullion in exchange for goods, thus undermining Britain’s balance of payments. Then, at about the turn of the 19th century, wily foreign traders thought of an alternative medium of payment — opium. Tons of the drug were brought into China.
51:In 1839 the Chinese government finally cracked down on this drain on the treasury, which was also causing mass addiction among the Chinese. Some 20,000 chests of opium were confiscated from British merchants in Guangzhou (Canton). Retaliation came a year later in the first of the Opium Wars, which culminated in a series of “unequal treaties” forced on an increasingly weak Manchu regime. China was obliged to open major ports to foreign political and economic penetration; Hong Kong was ceded to Britain.
```
This example searches a key word, *"opium"*, in a particular file, and gives the line number, too, which helps locating the word.

## Option3: -lr
 *It searches the target recursively in the directory and prints the filename of the file contains the target only.*
 
 *Source: A classmate told me when reviewing the skill demo1 together*
 
Example1:
```
commands: 
grep -lr "Lucayans" ../written_2 (use .. since the pwd is in the written_2)

result:
../written_2/travel_guides/berlitz2/Bahamas-History.txt
```
This examples searches the file contains *"Lucayans"* from all files in the written_2, including files in deeper directories, which can helps us locate the file contains our target.

Example2:
```
commands:
grep -lr "Ming" ../written_2

result:
../written_2/travel_guides/berlitz1/WhereToMalaysia.txt
../written_2/travel_guides/berlitz1/WhereToJapan.txt
../written_2/travel_guides/berlitz1/WhereToDublin.txt
../written_2/travel_guides/berlitz1/WhereToHongKong.txt
../written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
../written_2/travel_guides/berlitz2/China-WhereToGo.txt
../written_2/travel_guides/berlitz2/China-History.txt
../written_2/travel_guides/berlitz2/Beijing-History.txt
../written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
../written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
```
This example searches *"Ming"* recursively in written_2, and prints the filenames of matched files. It can help us find the documents we want quickly.

## Option4: -C n
 *It searches the target word and print out n lines before and after the line contains the key word.*
 
 *Source: A classmate told me when reviewing the skill demo1*

Example1:
```
command:
grep -C 1 "Qing" travel_guides/berlitz2/China-History.txt

result:
At first the Ming headquarters were moved south to the Yangzi River port of Nanjing (“Southern Capital”), but at the beginning of the 15th century the capital returned to what was now renamed Beijing (“Northern Capital”). Here Ming architects and artisans produced some of China’s most elegant palaces, temples, and parks, including the Forbidden City and Temple of Heaven, masterpieces that survive today.
The move northward made the supervision of defense efforts on the ever-sensitive borders of the empire easier. The Ming rulers oversaw the construction and renovation of the Great Wall sections that millions of tourists visit today, but this wall-building eventually proved incapable of keeping out enemies. By the 17th century, after repeated forays, infiltrations, and invasions, forces from Manchuria capitalized on domestic upheavals in China to take power in Beijing, almost by default. Consolidating control over the rest of the country, though, was a long and brutal business. The Manchu invaders called their new dynasty the Qing (Ch’ing). Fated to be the last of all the Chinese dynasties, it held power until modern times (1644–1911).
Pigtails and Prosperity
--
In 1839 the Chinese government finally cracked down on this drain on the treasury, which was also causing mass addiction among the Chinese. Some 20,000 chests of opium were confiscated from British merchants in Guangzhou (Canton). Retaliation came a year later in the first of the Opium Wars, which culminated in a series of “unequal treaties” forced on an increasingly weak Manchu regime. China was obliged to open major ports to foreign political and economic penetration; Hong Kong was ceded to Britain.
Infinitely more costly in human terms was the Taiping Rebellion, which began in 1850 as a peasant revolt. There was a struggle between the Qing Dynasty and rebels determined to overthrow such traditional values as respect for religion, private property, and male supremacy. The revolt lasted 14 years and cost more lives than would World War I. The Beijing government finally won, but the regime and the nation would never be the same.
This became patently clear during the Sino-Japanese War of 1894–1895, in which the inadequacy of the Chinese army was starkly displayed. Japan and Western powers were dismantling the Chinese Empire. Demands for reform won the support of the emperor, but his notoriously scheming aunt, the Empress Dowager Cixi (Tz’u Hsi), edged him off the throne. Soon after, Cixi had the chance to exploit the Boxer Rebellion (1900), a revolt against foreign influence. It was finally put down by the intervention of all the great powers, which joined together in an unprecedented alliance. China was saddled with payment of a humiliating indemnity and a further loss of respect.
```
This examples searches *"Qing"* in the file China-History.txt, and prints 1 line before and after the line contains "Qing", which provides more context of key word. 

Example2:
```
command:
grep -C 2 "Lucayans" travel_guides/berlitz2/Bahamas-History.txt

result:
A Brief History
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
English sea captains also came to know the beautiful but deserted Bahamian islands during the 17th century. England’s first formal move was on 30 October 1629, when Charles I granted the Bahamas and a chunk of the American south to his Attorney General, Sir Robert Health. But nothing came of that, nor of a rival French move in 1633 when Cardinal Richelieu, the 17th-century French statesman, tried claiming the islands for France.
Colonization and Piracy
```
This example searches *"Lucayans"* in the Bahamas-History.txt and prints 2 lines before and after the matched line, which allows readers to find a full context with targeted word.
