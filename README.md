# Face detection and classification of Natalie Portman & Keira Knightley
Задача, которую вы решали в этом проекте, заключается в классификации изображений лиц двух известных актрис (Киры Найтли и Натали Портман) с использованием технологий обработки изображений и глубокого обучения. Многие люди считают, что Кира Найтли и Натали Портман очень похожи, что породило множество шуток и мемов о том, как их легко спутать. Вдохновленные этой популярной темой, мы решили разработать нейросеть, которая будет классифицировать изображения их лиц. Хотя задача не имеет практической значимости, она стала интересным и увлекательным примером применения технологий глубокого обучения для решения шуточной задачи.

Для решения задачи был реализован пайплайн, включающий следующие этапы:

* Детекция лиц: С использованием модели MTCNN проводилась детекция лиц на изображениях. Лица на изображениях вырезались для дальнейшей обработки.
* Предобработка изображений: Вырезанные лица были подвергнуты преобразованиям, включая изменение размера, нормализацию и преобразование в тензоры, что соответствовало требованиям для подачи данных в нейронную сеть. Для баланса классов в датасете была реализована аугментация данных.
* Обучение модели: Для классификации изображений использовалась сверточная нейронная сеть (Xception), которая была в два этапа дообучена на датасете изображений лиц актрис. На первом этапе последний слой модели заменили на последовательность из нескольких новых слоев, подходящих под задачу, остальные слои были заморожены, чтобы не потерять их способность извлекать признаки. На втором этапе мы постарались повысить точность, разморозив все слои, и обучив модель несколько эпох на низком learning rate.
* Оценка модели: В процессе обучения модели проводился тест на тестовом наборе данных, чтобы оценить ее эффективность в классификации изображений. Для улучшения результатов сохранялись все модели с наибольшей точностью.
* Инференс на новых данных: Разработанная модель была протестирована на новых изображениях, где, после выделения лица, модель классифицировала его как одно из двух классов: 'Keira Knightley' или 'Natalie Portman'.
