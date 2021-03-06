
Декілька років тому, коли я ще вірив у те, що можна навчити когось візуалізації даних, я б 
зробив слайди і на них було б багато картинок з прикладами, і розповідь про інструменти, що існують

Однак зараз моя коротка доповідь буде побудована по іншому. Лінки на інструменти ви зможете знайти
в кінці цього документа, але головна ідея в тому, що:

- через різноманітність задач немає готового "універсального інструмента" для візуалізацій. Однак, якщо ви вмієте програмувати, то у вас вже є такий інструмент.  

Тобто, будь яка мова програмування, від LISP до Javascript, дозволяє створювати візуалізації
будь якого рівня складності - щоправда, для різних мов кількість витраченого часу  буде відрізнятися,
(і головним чином залежить від наявності готових бібліотек, що виконують різні потрібні нам задачі для візуалізації)

Маючи декілька років досвіду, хочу розкрити головний livehack: використовуйте той інструмент, який дозволить вам
найшвидше спробувати дуже багато різних варіантів. ***

Якщо згадати, що власне візуалізація - це 10-20% зусиль, а все інше це робота з даними, то бажано щоб наш інструмент містив у собі два в одному: і роботу з даними, і можливість швидко робити скетчі майбутньої візуалізації. 

Таким чином, ми ефективно відкидаємо всі інші варіанти крім двох: Python та R. І якби не одне "але", я б радив вам використовувати Python.


Одне але ***

Найкращий спосіб зробити візуалізацію у Python: 
```
$ python  
>>> exit()
$ rstudio  
```

Якщо серйозно, то оцим "але" є tidyverse, екосистема бібліотек роботи з даними та їх візуалізації для мови R, ідеологом якої є Headly Wickham, багато з вас про нього вже чули.

Python є неспівмірно кращою універсальною мовою програмування, однак для візуалізації даних на сьогодні нічого краще ніж tidyverse навіть близько не існує.
(Є думки, що  базовий R - насправді не справжня мова прграмування, але тут ми можемо сказати що tidyverse - це вже і не зовсім R, а DSL(domain specific language) 
на його основі)


З чого складається tidyverse.org

- *** скріншот 

Отже, додайте сюди Rstudio з RMarkdown & R Notebooks, і маємо повний, самодостатній всесвіт для роботи з даними, візуалізації та перевірки чужих результатів.


Пару додаткових зауважень:

### dplyr

З версії 0.7 стало можливим робити подібні функції у dplyr, майже без милиць і розпорок

```R
my_summarise <- function(df, group_by) {
  group_by <- enquo(group_by)  # більше того, group_by_at()  дозволяє навіть обійтись без пари "enquo() + !!"

  df %>%
    group_by(!!group_by) %>%
    summarise(a = mean(a))
}
```

 
### ggplot extensions
- ggraph
- gganimate
- geofacet
- ggjoy


### інтерактивні графіки та карти
- plotly (навіть в 3D)
- htmlwidgets (див. напр. тут: https://paldhous.github.io/NICAR/2017/r-to-javascript.html)








  
