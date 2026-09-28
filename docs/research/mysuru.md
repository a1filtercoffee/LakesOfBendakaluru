# Mysuru: what to build next

Research done on 2026-09-15 by six research agents, each opening the sources themselves.
Anything not opened is marked unverified.
This brief is written for the next agent, who starts with no context.
Read it with `docs/lake-data-model.md` and `docs/research/timeline-sources.md`, which describe how the Bengaluru site is built.

## The short answer

Build Lakes of Mysuru first, on the same code as Lakes of Bendakaluru.
Then build "Mysuru in stone": inscriptions and old temples on one map, because both come from the same old books and need the same village locations.
Tell the KRS dam story as one long page inside Lakes of Mysuru, not as its own site.
Drop "census by census" as a site: village population only goes back to 1941.
Rainfall since 1901 and bird counts fit as sections on lake pages, not as sites.

## Ideas, ranked

| Rank | Idea | Data | Nobody else has it | Verdict |
|---|---|---|---|---|
| 1 | Lakes of Mysuru | Strong, except outlines | Yes | Build first |
| 2 | Mysuru in stone (inscriptions and temples) | Strong but hand work | Yes | Build second |
| 3 | What the KRS dam drowned | Good maps, weak village list | Yes | One page in the lakes site |
| 4 | Mysuru year by year, 1862-1959 | Rich, messy tables | Yes | Maybe later |
| 5 | A century of Mysuru rain | Very clean | Partly | Section on lake pages |
| 6 | Birds of Kukkarahalli, Karanji, Lingambudhi | Very clean | Partly | Section on lake pages |
| 7 | Census by census | Villages from 1941 only | Partly | Drop |
| 8 | How Mysore city was planned | One real old plan | Yes | Drop for now |

## 1. Lakes of Mysuru

### What exists

Old maps:

- Survey of India one-inch sheet 57D/11 covers all of Mysuru city (12.25-12.5N, 76.5-76.75E), including Kukkarahalli, Karanji, Lingambudhi, Dalvoy and Devanur.
  It exists in 1926, 1947 and 1978 editions on [Zenodo 8388121](https://zenodo.org/records/8388121), CC BY 4.0, the same record the Bengaluru pipeline uses.
- The rest of the district, same record: 57D/3 (1973), 57D/4 (1911, 1989), 57D/7 (1926, 1973), 57D/8 (1927, 1973, 1990), 57D/12 (1926, 1973), 57D/15 (1926, 1974, 1988), 57D/16 (1926, 1958, 1973).
  57D/6, 57D/10 and 57D/14 are filed under Mandya, 1946-1974.
- Southern taluks: 58A/1 (1977) and 58A/5 (1974) on [Zenodo 8388131](https://zenodo.org/records/8388131).
  Western edge: 48P/10-16 (1911-1973) on [Zenodo 8388024](https://zenodo.org/records/8388024).
- The 1955 US Army Map Service sheet ND 43-16 "Mysore" is already georeferenced in the Bengaluru pipeline and covers the whole city ([Commons](https://commons.wikimedia.org/wiki/File:Map_India_and_Pakistan_1-250,000_Tile_ND_43-16_Mysore.jpg), public domain).
- Rice's Gazetteer plan of Mysore City, 1897 ([Commons](https://commons.wikimedia.org/wiki/File:Plan_of_Mysore_City_Rice%27s_Gazetteer_1897.jpg), public domain, 2969x3413 px).
  It names Kukkarhalli Reservoir, Dodda Kere beside the Fort, Karanji Kere and Gobli Kere by the race course, plus several unnamed tanks.
  About 8 tanks to trace by hand.

Lake lists:

- OpenStreetMap has 538 water polygons in Mysuru district, 147 around the city.
  This is the only free outline source found, so it becomes the anchor, where ATREE was the anchor for Bengaluru.
- KGIS tank maps are PDFs per taluk with tank IDs such as KA26030040, not outlines.
  Counted: Hunsur 233, Mysuru 131, K.R. Nagar 104, T. Narasipura 81 ([Mysuru taluk PDF](https://kgis.ksrsac.in/kgisdocuments/tankpdf/22-577-mysuru/2604_Mysuru.pdf)).
  File names for H.D. Kote, Nanjangud, Periyapatna and Saragur were not found.
  No licence stated.
- The statewide Minor Irrigation tank CSV the pipeline already reads has 47 Mysuru tanks, including Lingambudhi at 52.4 ha.
  Its tank IDs match the KGIS labels, which gives a way to place them.
- The 2017-18 Water Bodies Census file the pipeline already reads has 309 Mysuru points, but every condition field is blank for Mysuru.
- A CPCB inspection report lists 7 lake monitoring stations with coordinates: Hebbal, Kukkarahalli, Dalavai, Yennehole, Lingambudhi, Shettykere, Karanji ([PDF](https://cpcb.gov.in/displaypdf.php?id=em9iZW5nYWx1cnUvTldNUF9NeXNvcmVfMi5wZGY%3D)).
  No monthly Mysuru lake readings were found on the KSPCB site.
- Global Surface Water, land cover and Sentinel-2 work anywhere, so those pipeline steps only need a new area.
- Birds on GBIF within about 1 km: Lingambudhi 108,624 records and 275 species, Kukkarahalli 79,425 and 228, Karanji 19,579 and 194.

Not found: a Mysuru lake inventory like EMPRI's, a KTCDA list, a city corporation or MUDA lake list, a High Court lake case.

### How many lakes

Star of Mysore, December 2019: 106 recorded city lakes, 37 gone, 69 remaining ([article](https://starofmysore.com/42-lakes-in-mysuru-on-the-verge-of-depletion/)).
The district has 318 census points; the Zilla Panchayat says 2,991 lakes ([article](https://newskarnataka.com/mysuru/mysuru-zp-revives-33-lakes-plans-restoration-of-234-under-mgnrega/20032025/)).
A realistic mapped set is 600-1,000 district tanks with outlines.

### Stories in the data

- Dodda Kere, the big tank beside the palace fort on the 1897 plan, was drained in the 1930s over malaria fears and is now the Dasara Exhibition ground and parking ([secondary source](https://mysore.ind.in/doddakere)).
- Jeevarayana Katte is now J.K. Grounds and Subbarayanakere is Freedom Fighters' Park ([Star of Mysore](https://starofmysore.com/we-need-lakes-now/)).
- Gobli Kere is on the 1897 plan and in no lake list today; the 1926, 1947 and 1978 sheets would show when it went.
- Kukkarahalli was built in 1864 and was once the city's water supply.
- The lakes with the most birds, Lingambudhi and Karanji, are the ones fed by sewage.

### Interface

Keep the Bengaluru site as it is: the random cut-paper lake on the home page, the map, a page per lake with its years section, the gone lakes page, and the timeline of records.
Two additions are worth making for Mysuru.

First, a "then and now" page for the city.
One map of the city with four old sheets stacked under today's map: the 1897 plan, 1926, 1947 and 1978.
A single year control switches between them.
Every lake that is gone today is outlined on the old sheet and labelled with what stands there now, such as "Dasara Exhibition ground".

Second, a birds section on each lake page.
Species count per year from GBIF, and the birds seen there most often.
Say plainly that sightings before about 2012 are thin.

### Open questions

Whether Mysuru is a second city in this repo or a fork.
A second city in this repo keeps one pipeline and one design; many scripts and pages probably assume Bengaluru and must be checked first.
Whether the site covers the city only (about 106 lakes, strong old-map story) or the district (up to 1,000 tanks, outlines weaker).

## 2. Mysuru in stone: inscriptions and temples

This merges the inscriptions idea and the temples idea.
They share sources (Rice's Epigraphia Carnatica, the Mysore Archaeological Department reports, the gazetteers) and the hardest step, placing old village names on a map.
Many inscriptions are temple grants, and many temples are dated only by their inscriptions.

### Inscriptions: what exists

- Epigraphia Carnatica old series Vol III (1894), Mysore District Part I: [epigraphiacarnat03mysouoft](https://archive.org/details/epigraphiacarnat03mysouoft), 958 pages, public domain.
  Mysore, Seringapatam, Mandya, Malavalli, T.-Narsipur and Nanjangud taluks, 803 inscriptions.
- Vol IV (1898), Mysore District Part II: [epigraphiacarnat04mysouoft](https://archive.org/details/epigraphiacarnat04mysouoft), 966 pages, public domain.
  Chamarajanagar, Gundlupet, Yedatore (now K.R. Nagar), H.D. Kote, Hunsur and Krishnarajpet, 962 inscriptions.
- Rice's total for the old district is 1,765 inscriptions, dated about 450 to 1878.
- The English OCR text of the Toronto scans is good; accents get mangled and the Kannada script sections are unusable.
- Each entry has a running number per taluk ("My. 52"), a place line ("At Vodéri, on a stone lying below the tank bund"), a date line already converted to A.D. with guesses marked, and an English translation.
  Real example from Vol III, Mysore taluk: "52 / Date ? about 1650 A.D. / A grant by Sabe, son of Harata, for a tank."
- Each volume has an index of places mapping village to inscription numbers, such as "Kumbarahalli My. 29-31".
- Dynasty is not a field; it has to be inferred from king names.
- A crude count over Vol III: the 12th century (Hoysala) is the clear peak, then the 16th (Vijayanagara).
  Rice's earliest Ganga dates are now known to be forged or wrong and need correcting.
- The revised edition by the University of Mysore (1974 onward) adds many inscriptions but is under copyright, and most of its text layers are unreadable.
  Facts such as village, date and what was granted can still be taken from it; its translations cannot be republished.
- Vol XIV (1943) is a supplement for Mysore and Mandya, about 750 inscriptions, copyright status not checked.

No structured, mapped dataset of these inscriptions exists.
The Mythic Society's 3D inscriptions project covers only Bengaluru and Ramanagara, with no downloads.
Two GitHub attempts (an unfinished Django database, a PDF search) have no usable data.

### Temples: what exists

- The temple department (Muzrai) has 34,563 notified temples, but its [search](https://itms.kar.nic.in/hrcehome/temple_search.php) shows only ID, name and district, with no export, no dates and no coordinates.
- Karnataka State Archaeology says 848 state-protected and 609 nationally protected monuments; its Mysuru division has 129 and 71.
  No downloadable list was found.
- ASI monuments with coordinates: [asi-monuments-xml2csv](https://github.com/answerquest/asi-monuments-xml2csv) has 573 Karnataka rows from Bhuvan, 7 in Mysuru, with no dates or history.
- Wikidata has about 589 temples with coordinates in and around Karnataka, only 18 with a founding date; 30 in Mysuru district, none dated.
- OpenStreetMap has 208 Hindu places of worship in Mysuru district, 178 named, almost none with a date.
- The Mysore Archaeological Department annual reports, 1901-1956, 141 items on archive.org (for example [in.ernet.dli.2015.240005](https://archive.org/details/in.ernet.dli.2015.240005)), describe temples village by village for old Mysore state.
  This is the best free source for what a temple is and why it was built.
- Existing maps: [hoysala.info](https://hoysala.info) maps 15 of its 64 Hoysala temples and has little for Mysuru.
  Bhuvan and similar maps show ASI dots with no history.
  Kevin Standage's blog has excellent history per temple but no map and all rights reserved.
  Nobody combines every old temple with its date, builder, reason and sources.

### Scope

Decided on 2026-09-15: the site covers today's Mysuru district only, not old Mysore State and not Rice's old Mysore District.
Working name: Temples and Inscriptions of Mysuru.
From Rice's volumes keep Mysore, T.-Narsipur and Nanjangud (Vol III) and Yedatore, Heggadadevankote and Hunsur (Vol IV).
Periyapatna and Saragur are later splits of these; check which old taluk each village came from.
Leave out Seringapatam, Mandya, Malavalli, Krishnarajpet (now Mandya district), Chamarajanagar and Gundlupet (now Chamarajanagar district).
Filter inscriptions by where the village is today, using current district boundaries, not by Rice's taluk code alone, since taluk lines have moved.
The exact inscription count for today's district is not yet known; it is well under 1,765.

All of Karnataka's temples over 100 years old cannot be done from free sources.
Mysuru district can: about 100-180 temples with a place, an age over 100 years and one sourced sentence, and 1,765 inscriptions tied to a few hundred villages.
Protected monuments statewide, about 800-950 temples, is the natural next step after.

### Work

1. Split the Vol III and IV text into entries: number, place line, date, translation.
2. Tag what each records (land grant, tank, temple, hero stone) and the dynasty, by rules plus a review pass.
3. Place villages: match Rice's spellings, accents stripped, against 2011 census village names within the same taluk.
   Village boundaries: [DataMeet](https://github.com/datameet/indian_village_boundaries) (ODbL) or SHRUG (CC BY-NC-SA, non-commercial only, so prefer DataMeet).
   Old taluks must be mapped to new: Yedatore is K.R. Nagar, Seringapatam is Srirangapatna, Chamarajanagar and Gundlupet are now their own district, Krishnarajpet is in Mandya.
4. Temples: start from the state and ASI protected lists, add temples from the annual reports, pin each by hand to an OpenStreetMap temple, and link inscriptions found at the same village.

### Interface

A map of Mysuru with a century control running from the 5th century to the 19th.
Moving it forward, each village lights up in the century its first inscription was carved and stays lit.
Dots are coloured by the ruling dynasty of that century: Ganga, Chola, Hoysala, Vijayanagara, Wodeyar.
A filter shows only one kind of record: tanks, temples, land grants, hero stones.
The tanks filter links straight to Lakes of Mysuru.

Temples are drawn as a separate mark on the same map.
A temple page, in the cut-paper style, carries slips for deity, built in, built by, and why, each with its source, plus every inscription found there in date order with Rice's translation line.

A village page lists all its inscriptions from oldest to newest, like the lake years section, with a link to the page of the scan each came from.

## 3. What the KRS dam drowned

### What exists

- The lake sits on four sheets: 57D/7 (most of the lake), 57D/11 (dam and eastern end), 57D/6 and 57D/10 (northern arm).
- 57D/7 and 57D/11 have 1926 editions surveyed in 1924-25, while the reservoir was filling.
  They draw the full flood area in grey and still show the villages inside it.
  57D/11 prints a note that "villages in the flooded area were in process of removal to fresh sites".
  Later editions: 57D/7 1973, 57D/11 1947 and 1978.
- 57D/6 and 57D/10 exist only in 1973, so the northern arm has no early map.
- No free map from before 1911 was found.
- The 1955 US Army sheet ND 43-16 covers the whole lake and is already georeferenced.
- Names read inside the grey flood area of the 1924-25 sheets: Danayakanakote (a fort), Puvanhalli, Punahalli, Basti, Hoskote (two), Hosur, Kallahalli, Kundur, Cholenhalli, Ramanhalli, Kempegaudana Koppal, Heraganahalli, Sayappanahalli, Malligere, Yedahalli, Chikayarhalli, Anandur.
  Some may sit on ground that stayed dry; check against the full-level contour.
- Kannada Wikipedia says 25 villages were submerged; no primary list was found.
  Search the Hayavadana Rao Mysore Gazetteer text on archive.org next.
- Kannambadi moved to Hosa Kannambadi; its Venugopala Swamy temple resurfaced around 2000 and was moved stone by stone by 2011.
  The Bore Ananduru temple resurfaced in 2019, 2023 and May-June 2026, when the level fell to about 81 ft.
- Outline: OpenStreetMap relation 9050201.
  How often each spot was under water, 1984-2021: Global Surface Water occurrence tile `occurrence_70E_20Nv1_4_2021.tif`, which the pipeline already reads.
- Full level is 124.80 ft and dead storage 60 ft.
  Scattered 28 June levels exist in news (2017: 68.35 ft, 2023: 77.90 ft), but no clean long daily series was found.
  India-WRIS did not respond, and the state disaster centre's site has an expired certificate.

### Interface

One long page in Lakes of Mysuru.
It opens on the 1924-25 sheet with the grey flood area and the village names.
Scrolling down, the reservoir fills over the old map until only the 1970s shoreline is left.
Then a water level control from 124.8 ft to 60 ft: dragging it down uncovers the ground that Global Surface Water saw dry in low years, and the villages and temples on that ground reappear with their slips.
Each village slip gives its name on the 1924-25 sheet, where it moved to if known, and when its ruins last came out of the water.

Hemavathi (Gorur) with the Shettihalli church and Kabini with its resurfacing temples would suit the same page, but their early sheets were not found.

## 4. Mysuru year by year, 1862-1959

About 99 yearly Mysore administration reports are on archive.org ([search](https://archive.org/advancedsearch.php?q=title%3A%28%22administration+of+mysore%22%29)), most uploaded by the Karnataka State Archives, public domain.
They cover rainfall, crops, silk, sandalwood, schools, hospitals, famine, plague and new laws.
The text is readable but tables break apart, so pick 10-20 figures and check each by hand against the scans.

Interface: a page per year with its figures and events, and a chart per figure across the century, each value linked to the scan page it came from.

## 5. Rain since 1901

The India Meteorological Department's daily 0.25 degree rainfall grid covers 1901-2024 ([download](https://www.imdpune.gov.in/cmpg/Griddata/Rainfall_25_Bin.html)), free, no licence stated, so credit the department.
It is regional rain, about 25 km per grid cell, not a city gauge.
Use it as a section on lake pages and on the KRS page: rain over the lake's catchment each year.

## 6. Census by census

Village population for Mysuru only exists from 1941.
The 1951 District Census Handbook ([catalog 28428](https://censusindia.gov.in/nada/index.php/catalog/28428)) prints each village's 1941 and 1951 population, and every handbook from 1961 to 2011 has village figures.
No village list from 1891-1931 was found online.
Towns have series from 1881 in the 1931 census tables.
Gazetteer entries exist for towns and a few hundred villages: Rice 1897 ([Vol II](https://archive.org/details/mysoreagazettee02ricegoog)), Hayavadana Rao 1927-30 ([Vol V](https://archive.org/details/in.ernet.dli.2015.11584)), and the Imperial Gazetteer 1908 ([searchable](https://dsal.uchicago.edu/cgi-bin/reference/gazetteer/query.py?keyword=Nanjangud)).
Not worth a site on its own; gazetteer lines can go on village and temple pages in idea 2.

## 7. Dropped

- How Mysore city was planned: only the 1897 plan and a 1930 map are online; the 1920s city survey maps were not found.
- Heritage buildings: 129 notified, no downloadable list or coordinates.
- Tree census: 121,789 trees counted, no public data yet.
- Old photographs: about 14 on Commons, none with locations.
- Mysore State Railway: no station data with opening dates.
