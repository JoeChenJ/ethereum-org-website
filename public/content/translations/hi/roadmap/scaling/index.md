---
title: स्केलिंग इथेरियम
description: रोलअप बैच लेनदेन एक साथ ऑफ-चेन, उपयोगकर्ता के लिए लागत को कम करता है। हालाँकि, वर्तमान में रोलअप द्वारा डेटा का उपयोग करने का तरीका बहुत महंगा है, जिससे यह सीमित हो जाता है कि लेनदेन कितना सस्ता हो सकता है। प्रोटो-डैंकशार्डिंग इसे ठीक करता है।
lang: hi
image: /images/roadmap/roadmap-transactions.png
alt: "एथेरियम दिशानिर्देश"
template: roadmap
---

एथेरियम को [लेयर 2](/layer-2/#rollups) (जिसे रोलअप के रूप में भी जाना जाता है) का उपयोग करके स्केल किया जाता है, जो लेनदेन को एक साथ बैच करता है और आउटपुट को एथेरियम में भेजता है। भले ही रोलअप एथेरियम मेननेट की तुलना में आठ गुना सस्ते हैं, फिर भी अंतिम यूज़र के लिए लागत कम करने के लिए रोलअप को और अधिक अनुकूलित किया जा सकता है। रोलअप कुछ केंद्रीकृत घटकों पर भी निर्भर करते हैं जिन्हें डेवलपर्स रोलअप के मॅच्‍योर होने पर हटा सकते हैं।

<InfoBanner mb={8} title="लेनदेन लागत">
  <ul style={{ marginBottom: 0 }}>
    <li>आज के रोलअप एथेरियम लेयर 1 की तुलना में <strong>~5-20x</strong> सस्ते हैं</li>
    <li>ZK-रोलअप जल्द ही फीस <strong>~40-100 गुना</strong> कम कर देगा</li>
    <li>एथेरियम में आगामी बदलाव <strong>~100-1000x</strong> स्केलिंग लाएंगे</li>
    <li style={{ marginBottom: 0 }}>यूज़र को <strong>$0.001 से कम लागत</strong> वाले लेनदेन से लाभ होना चाहिए</li>
  </ul>
</InfoBanner>

## डेटा को सस्ता करना {#making-data-cheaper}

रोलअप बड़ी संख्या में लेनदेन एकत्र करते हैं, उन्हें निष्पादित करते हैं और परिणाम एथेरियम को भेज देते हैं। इससे बहुत सारा डेटा उत्पन्न होता है जिसे खुले तौर पर उपलब्ध कराने की आवश्यकता होती है ताकि कोई भी अपने लिए लेनदेन निष्पादित कर सके और सत्यापित कर सके कि रोलअप ऑपरेटर सही था। अगर किसी को कोई विसंगति मिलती है तो वे इसपर चुनौती दे सकते हैं।

### प्रोटो-डैंकशर्डिंग {#proto-danksharding}

रोलअप डेटा ऐतिहासिक रूप से एथेरियम पर स्थायी रूप से संग्रहीत किया गया है, जो महंगा है। रोलअप पर यूज़र द्वारा भुगतान की जाने वाली 90% से अधिक लेनदेन लागत इस डेटा स्‍टोरेज के कारण होती है। लेन-देन लागत कम करने के लिए, हम डेटा को एक नए अस्थायी 'ब्‍लॉब' स्‍टोरेज में ले जा सकते हैं। ब्‍लॉब सस्ते होते हैं क्योंकि वे अस्थायी होते हैं; आवश्यकता न रहने पर वे एथेरियम से हटा दिए जाते हैं। रोलअप डेटा को लंबे समय तक संग्रहीत करना उन लोगों की जिम्मेदारी बन जाता है जिन्हें इसकी आवश्यकता होती है, जैसे रोलअप ऑपरेटर, एक्सचेंज, इंडेक्‍सिंग सेवाएं आदि। एथेरियम में ब्लॉब लेनदेन को जोड़ना एक अपग्रेड का हिस्सा है जिसे "प्रोटो-डैंकशर्डिंग" के रूप में जाना जाता है।

प्रोटो-डैंकशार्डिंग के साथ, एथेरियम ब्लॉकों में कई ब्लॉब्स जोड़ना संभव है। यह एथेरियम के थ्रूपुट के लिए एक और पर्याप्त (>100x) स्केल-अप और लेनदेन लागत के लिए स्केल-डाउन को सक्षम बनाता है।

### डैंकशार्डिंग {#danksharding}

ब्लॉब डेटा के विस्तार का दूसरा चरण जटिल है क्योंकि इसके लिए रोलअप डेटा की जांच के लिए नए तरीकों की आवश्यकता होती है जो नेटवर्क पर उपलब्ध है और [सत्यापनकर्ताओं](/glossary/#validator) पर निर्भर करता है> जो उनके [ब्लॉक](/glossary/#block) बिल्डिंग और ब्लॉक प्रस्ताव जिम्मेदारियों को अलग करता है। सत्यापनकर्ताओं ने ब्लॉब डेटा के छोटे उपसमूहों को सत्यापित किया है, यह क्रिप्टोग्राफ़िक रूप से साबित करने के लिए इसे एक तरीके की आवश्यकता है।

इस दूसरे चरण को ["डैंकशार्डिंग"](/roadmap/danksharding/) के नाम से जाना जाता है। **यह पूरी तरह से लागू होने से कई साल दूर** होने की संभावना है। डैंकशार्डिंग अन्य विकासों पर निर्भर करता है जैसे [ब्लॉक बिल्डिंग और ब्लॉक प्रस्ताव को अलग करना](/roadmap/pbs) और नए नेटवर्क डिज़ाइन जो नेटवर्क को एक समय में कुछ किलोबाइट का रेंडम रूप से नमूना लेकर डेटा उपलब्धि की कुशलतापूर्वक पुष्टि करने में सक्षम बनाते हैं जिसे [डेटा अवेलेबिलिटी सैम्पलिंग (DAS)](/developers/docs/data-availability) के रूप में जाना जाता है।

<ButtonLink variant="outline-color" href="/roadmap/danksharding/">डैंकशार्डिंग के बारे में ज़्यादा जानिए</ButtonLink>

## रोलअप का विकेंद्रीकरण {#decentralizing-rollups}

[रोलअप](/layer-2) पहले से ही एथेरियम का स्केलिंग कर रहे हैं। [रोलअप परियोजनाओं का एक इकोसिस्टम](https://l2beat.com/scaling/tvl) यूज़र को सुरक्षा गारंटी की एक श्रृंखला के साथ, जल्दी और सस्ते में लेनदेन करने में सक्षम बना रहा है। हालाँकि, रोलअप को केंद्रीकृत सीक्वेंसर (एथेरियम में सबमिट करने से पहले सभी ट्रांजेक्‍शन प्रोसेसिंग और एकत्रीकरण करने वाले कंप्यूटर) का उपयोग करके बूटस्ट्रैप किया गया है। यह सेंसरशिप के प्रति संवेदनशील है, क्योंकि सीक्वेंसर ऑपरेटरों पर प्रतिबंध लगाया जा सकता है, उनको रिश्वत दी जा सकती है या उनसे समझौता किया जा सकता है। साथ ही, रोलअप आने वाले डेटा को [भिन्न तरीके से](https://l2beat.com) सत्यापित करते हैं। "प्रोवर्स" के लिए [धोखाधड़ी का सबूत](/glossary/#fraud-proof) या वैधता प्रमाण सबमिट करने का सबसे अच्छा तरीका है, लेकिन सभी रोलअप अभी तक नहीं हैं। यहां तक कि वे रोलअप भी जो वैधता/धोखाधड़ी का सबूत का उपयोग करते हैं, पहचान के प्रूवर्स के एक छोटे पूल का उपयोग करते हैं। इसलिए, एथेरियम को स्केल करने में अगला महत्वपूर्ण कदम अधिक लोगों के बीच सीक्वेंसर और प्रूवर्स चलाने की जिम्मेदारी वितरित करना है।

<ButtonLink variant="outline-color" href="/developers/docs/scaling/">रोलअप के बारे में अधिक जानकारी</ButtonLink>

## वर्तमान प्रगति {#current-progress}

प्रोटो-डैंकशार्डिंग इन रोडमैप आइटमों में से पहला है जिसे 2024 के मार्च में कैनकन-डेनेब ("Dencun") नेटवर्क अपग्रेड के हिस्से के रूप में लागू किया जाना है। **पूर्ण डंकशार्डिंग कई साल दूर होने की संभावना है**, क्योंकि यह पहले पूरा होने वाले कई अन्य रोडमैप आइटमों पर निर्भर करता है। रोलअप इन्फ्रास्ट्रक्चर का विकेंद्रीकरण एक क्रमिक प्रक्रिया होने की संभावना है - कई अलग-अलग रोलअप हैं जो थोड़ा अलग सिस्टम बना रहे हैं और अलग-अलग दरों पर पूरी तरह से विकेंद्रीकरण करेंगे।

[डेनकन नेटवर्क अपग्रेड पर अधिक](/roadmap/dencun/)

<QuizWidget quizKey="scaling" />
