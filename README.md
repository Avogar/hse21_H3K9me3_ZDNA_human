# Проект по биоинформатике 

Организм: human.

Структура ДНК: G4_chip.

Гистоновая метка: H3K9me3.

Тип клеток: MCF-7.

Chip-seq эксперименты: https://www.encodeproject.org/files/ENCFF501UHK/, https://www.encodeproject.org/files/ENCFF518MOR/

## 1. Анализ пиков гистоновой метки

Построим гистограммы длин участков для каждого эксперимента до и после конвертации из верси hg38 в hg19.

- Эксперимент ENCFF501UHK, версия hg38, количество пиков 40646: 

<img src="/images/len_hist.H3K9me3_MCF7.ENCFF501UHK.hg38.png" alt="H3K9me3_MCF7.ENCFF501UHK.hg38" width="600"/>

- Эксперимент ENCFF501UHK, версия hg19, количество пиков 40249: 

<img src="/images/len_hist.H3K9me3_MCF7.ENCFF501UHK.hg19.png" alt="H3K9me3_MCF7.ENCFF501UHK.hg19" width="600"/>

- Эксперимент ENCFF518MOR, версия hg38, количество пиков 39779: 

<img src="/images/len_hist.H3K9me3_MCF7.ENCFF518MOR.hg38.png" alt="H3K9me3_MCF7.ENCFF518MOR.hg38" width="600"/>

- Эксперимент ENCFF518MOR, версия hg19, количество пиков 39216: 

<img src="/images/len_hist.H3K9me3_MCF7.ENCFF518MOR.hg19.png" alt="H3K9me3_MCF7.ENCFF518MOR.hg19" width="600"/>

Выкинем слишком длинные пики (>5000) и построим гистограммы после фильтрации для данных hg19.

- Эксперимент ENCFF501UHK, количество пиков 40166: 

<img src="/images/filter_peaks.H3K9me3_MCF7.ENCFF501UHK.hg19.filtered.hist.png" alt="H3K9me3_MCF7.ENCFF501UHK.hg19" width="600"/>

- Эксперимент ENCFF518MOR, количество пиков 39189: 

<img src="/images/filter_peaks.H3K9me3_MCF7.ENCFF518MOR.hg19.filtered.hist.png" alt="H3K9me3_MCF7.ENCFF518MOR.hg19" width="600"/>

Посмотрим, где располагаются пики гистоновой метки относительно аннотированных генов. Для этого построим графики типа пай-чарт с помощью R-библиотека ChIPseeker.

- Эксперимент ENCFF501UHK:

<img src="/images/chip_seeker.H3K9me3_MCF7.ENCFF501UHK.hg19.filtered.plotAnnoPie.png" alt="H3K9me3_MCF7.ENCFF501UHK.hg19" width="500"/>

- Эксперимент ENCFF518MOR:

<img src="/images/chip_seeker.H3K9me3_MCF7.ENCFF518MOR.hg19.filtered.plotAnnoPie.png" alt="H3K9me3_MCF7.ENCFF518MOR.hg19" width="500"/>

Визуализируем исходные два набора ChIP-seq пиков, а также их объединение в геномном браузере:

http://genome.ucsc.edu/s/avogar/hse21_H3K9me3_G4_human

## 2. Анализ участков вторичной стр-ры ДНК

Построим гистограмму распределения длин участков вторичной стр-ры ДНК. Количество пиков 19394:

<img src="/images/len_hist.DeepZ.png" alt="DeepZ" width="600"/>

Посмотрим, где располагаются участки стр-ры ДНК относительно аннотированных генов:

<img src="/images/chip_seeker.DeepZ.plotAnnoPie.png" alt="DeepZ" width="500"/>

## 3. Анализ пересечений гистоновой метки и стр-ры ДНК

Построим гистограмму распределения длин пересечений гистоновой метки и структуры ДНК. Количество пиков 528:

<img src="/images/len_hist.H3K9me3_MCF7.intersect_with_DeepZ.png" alt="H3K9me3_MCF7.intersect_with_DeepZ" width="600"/>

Посмотрим, где располагаются участки пересечений относительно аннотированных генов.

<img src="/images/chip_seeker.H3K9me3_MCF7.intersect_with_DeepZ.plotAnnoPie.png" alt="H3K9me3_MCF7.intersect_with_DeepZ" width="500"/>

