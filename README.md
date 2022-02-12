# 10 шагов для запуска тестирования производительности с Apache JMeter

</div></div></div></div></div></div><section class="post body paragraphs wrapper"><p id="35dc" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">Давайте представим, что Вы — единственный тестировщик на проекте, а то и во всей компании. Компания подписала контракт на разработку продукта, в котором очень важна производительность, а у Вас нет ни малейшего представления о том, с чего начать. Инструментов представлено большое количество, и выбрать какой-либо не так уж просто. Сейчас я предлагаю ознакомиться с <a class="et hz" href="https://jmeter.apache.org/index.html" rel="noopener ugc nofollow" target="_blank"><strong class="hd ia">Apache JMeter</strong></a><strong class="hd ia"> </strong>и запустить первый тест за 10 простых шагов. Предварительно нужно убедиться что установлена Java 8 или Java 9 на устройстве, с которого будут запускаться тесты.</p></section><ol class=""><li id="fa18" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy ib ic id bq" data-selectable-paragraph="">Скачиваем JMeter с сайта <a class="et hz" href="https://jmeter.apache.org/download_jmeter.cgi" rel="noopener ugc nofollow" target="_blank">jmeter.apache.org</a> в нужном формате</li></ol><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm ie"><div class="iu s em iv"><div class="iw ix s"><div class="ip iq t u v ir aj ay is it">
</div>
<img alt="" class="ls no t u v ir aj c" width="700" height="519" role="presentation" src="https://miro.medium.com/max/1400/1*ZWEmHMhu57mnHp1zKqXrQA.png" srcset="https://miro.medium.com/max/552/1*ZWEmHMhu57mnHp1zKqXrQA.png 276w, https://miro.medium.com/max/1104/1*ZWEmHMhu57mnHp1zKqXrQA.png 552w, https://miro.medium.com/max/1280/1*ZWEmHMhu57mnHp1zKqXrQA.png 640w, https://miro.medium.com/max/1400/1*ZWEmHMhu57mnHp1zKqXrQA.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*ZWEmHMhu57mnHp1zKqXrQA.png" width="700" height="519" srcSet="https://miro.medium.com/max/552/1*ZWEmHMhu57mnHp1zKqXrQA.png 276w, https://miro.medium.com/max/1104/1*ZWEmHMhu57mnHp1zKqXrQA.png 552w, https://miro.medium.com/max/1280/1*ZWEmHMhu57mnHp1zKqXrQA.png 640w, https://miro.medium.com/max/1400/1*ZWEmHMhu57mnHp1zKqXrQA.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="512f" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">2. Распаковываем архив. Путь к распакованной папке не должен содержать кириллицу или пробелы. Открываем распакованную папку, заходим в папку <strong class="hd ia">/bin</strong>, там находим сам <strong class="hd ia">JMeter </strong>(jmeter.bat для Windows<br>jmeter.sh для Unix)<strong class="hd ia"> </strong>и запускаем его. В результате будет представлен такой интерфейс:</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jb"><div class="iu s em iv"><div class="jc ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="438" role="presentation" src="https://miro.medium.com/max/1400/1*YXKvRhmrjEo0__-TxOeJtg.png" srcset="https://miro.medium.com/max/552/1*YXKvRhmrjEo0__-TxOeJtg.png 276w, https://miro.medium.com/max/1104/1*YXKvRhmrjEo0__-TxOeJtg.png 552w, https://miro.medium.com/max/1280/1*YXKvRhmrjEo0__-TxOeJtg.png 640w, https://miro.medium.com/max/1400/1*YXKvRhmrjEo0__-TxOeJtg.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*YXKvRhmrjEo0__-TxOeJtg.png" width="700" height="438" srcSet="https://miro.medium.com/max/552/1*YXKvRhmrjEo0__-TxOeJtg.png 276w, https://miro.medium.com/max/1104/1*YXKvRhmrjEo0__-TxOeJtg.png 552w, https://miro.medium.com/max/1280/1*YXKvRhmrjEo0__-TxOeJtg.png 640w, https://miro.medium.com/max/1400/1*YXKvRhmrjEo0__-TxOeJtg.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="35b3" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">3. Далее нам нужно добавить пользователей, которые будут ходить на страничку. Для этого снова выбираем тест план правым кликом и далее следуем в /Add/Threads (Users)/Thread Group. В итоге, в тест плане появляется следующий элемент:</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jd"><div class="iu s em iv"><div class="je ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="423" role="presentation" src="https://miro.medium.com/max/1400/1*nO5jdIX2vN0IuybI36p_wA.png" srcset="https://miro.medium.com/max/552/1*nO5jdIX2vN0IuybI36p_wA.png 276w, https://miro.medium.com/max/1104/1*nO5jdIX2vN0IuybI36p_wA.png 552w, https://miro.medium.com/max/1280/1*nO5jdIX2vN0IuybI36p_wA.png 640w, https://miro.medium.com/max/1400/1*nO5jdIX2vN0IuybI36p_wA.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*nO5jdIX2vN0IuybI36p_wA.png" width="700" height="423" srcSet="https://miro.medium.com/max/552/1*nO5jdIX2vN0IuybI36p_wA.png 276w, https://miro.medium.com/max/1104/1*nO5jdIX2vN0IuybI36p_wA.png 552w, https://miro.medium.com/max/1280/1*nO5jdIX2vN0IuybI36p_wA.png 640w, https://miro.medium.com/max/1400/1*nO5jdIX2vN0IuybI36p_wA.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jf"><div class="iu s em iv"><div class="je ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="423" role="presentation" src="https://miro.medium.com/max/1400/1*t3JG4mrWK0CO9toZHokgew.png" srcset="https://miro.medium.com/max/552/1*t3JG4mrWK0CO9toZHokgew.png 276w, https://miro.medium.com/max/1104/1*t3JG4mrWK0CO9toZHokgew.png 552w, https://miro.medium.com/max/1280/1*t3JG4mrWK0CO9toZHokgew.png 640w, https://miro.medium.com/max/1400/1*t3JG4mrWK0CO9toZHokgew.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*t3JG4mrWK0CO9toZHokgew.png" width="700" height="423" srcSet="https://miro.medium.com/max/552/1*t3JG4mrWK0CO9toZHokgew.png 276w, https://miro.medium.com/max/1104/1*t3JG4mrWK0CO9toZHokgew.png 552w, https://miro.medium.com/max/1280/1*t3JG4mrWK0CO9toZHokgew.png 640w, https://miro.medium.com/max/1400/1*t3JG4mrWK0CO9toZHokgew.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><ul class=""><li id="d863" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy jg ic id bq" data-selectable-paragraph="">Number of Threads — число пользователей, которые будут обращаться по запросу, указанному в HTTP Request Defaults.</li><li id="b699" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Ramp-Up Period — время, в течение которого будут прибавляться юзеры. Позволяет делать плавный и прогнозируемый старт.</li><li id="2c24" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Loop Count — количество итераций. На скриншоте выше значение равно 1, то есть каждый пользователь сделает всего 1 запрос.</li></ul><section class="post body paragraphs wrapper"><p id="5a68" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">Дополнение: Можно выставить базовые параметры, указанные выше на любые значения, которые хочется испытать, но для начала рекомендую обойтись небольшими величинами, например, 10 пользователей и пару циклов. Выставление огромного количества пользователей в одном треде может проглотить все мощности вашего устройства и оно просто перезагрузится :)</p><p id="60db" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">4. Для запуска теста нужно указать инструменту адрес сервера, который будет подвержен нагрузке с типом запроса. Это делается через правый клик по уже добавленному Thread Group и выбор Add/Sampler/HTTP Request</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jd"><div class="iu s em iv"><div class="jm ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="421" role="presentation" src="https://miro.medium.com/max/1400/1*Anrae06_Tli0S2kYar2yhg.png" srcset="https://miro.medium.com/max/552/1*Anrae06_Tli0S2kYar2yhg.png 276w, https://miro.medium.com/max/1104/1*Anrae06_Tli0S2kYar2yhg.png 552w, https://miro.medium.com/max/1280/1*Anrae06_Tli0S2kYar2yhg.png 640w, https://miro.medium.com/max/1400/1*Anrae06_Tli0S2kYar2yhg.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*Anrae06_Tli0S2kYar2yhg.png" width="700" height="421" srcSet="https://miro.medium.com/max/552/1*Anrae06_Tli0S2kYar2yhg.png 276w, https://miro.medium.com/max/1104/1*Anrae06_Tli0S2kYar2yhg.png 552w, https://miro.medium.com/max/1280/1*Anrae06_Tli0S2kYar2yhg.png 640w, https://miro.medium.com/max/1400/1*Anrae06_Tli0S2kYar2yhg.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="4371" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">5. После добавления элемента можно указывать адрес сервера. Прежде чем ходить на чьи-то реальные/тестовые серверы и наводить панику на команды разработки и поддержки, стоит попробовать свои силы на простейшем примере поисковой системы. В данном случае я предлагаю сходить на google.com, а точнее, на страницу, так называемого, “Мне повезёт!” (<a class="et hz" href="https://www.google.com/doodles/" rel="noopener ugc nofollow" target="_blank">https://www.google.com/doodles/</a>). Для этого в протоколе указываем <strong class="hd ia">https</strong>, в адресе сервера <strong class="hd ia">google.com</strong>, а в пути расположение страницы <strong class="hd ia">/doodles/, </strong>ну и не забываем про тип запроса <strong class="hd ia">GET </strong>.</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jd"><div class="iu s em iv"><div class="jn ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="422" role="presentation" src="https://miro.medium.com/max/1400/1*yDyQfq5IJ8bfb78uMglffg.png" srcset="https://miro.medium.com/max/552/1*yDyQfq5IJ8bfb78uMglffg.png 276w, https://miro.medium.com/max/1104/1*yDyQfq5IJ8bfb78uMglffg.png 552w, https://miro.medium.com/max/1280/1*yDyQfq5IJ8bfb78uMglffg.png 640w, https://miro.medium.com/max/1400/1*yDyQfq5IJ8bfb78uMglffg.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*yDyQfq5IJ8bfb78uMglffg.png" width="700" height="422" srcSet="https://miro.medium.com/max/552/1*yDyQfq5IJ8bfb78uMglffg.png 276w, https://miro.medium.com/max/1104/1*yDyQfq5IJ8bfb78uMglffg.png 552w, https://miro.medium.com/max/1280/1*yDyQfq5IJ8bfb78uMglffg.png 640w, https://miro.medium.com/max/1400/1*yDyQfq5IJ8bfb78uMglffg.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="75e9" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">6. Тест нужно сохранить в папку <strong class="hd ia">/bin</strong> (там же, где лежит сам JMeter), далее, запустить терминал/командную строку и перейти в папку <strong class="hd ia">/bin</strong>, из которой на втором шаге запускали JMeter. Графическую оболочку лучше закрыть перед запуском теста. Запуск теста осуществляется командой:</p></section><ul class=""><li id="4081" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy jg ic id bq" data-selectable-paragraph="">jmeter -n -t <strong class="hd ia">test_name.jmx</strong> -l <strong class="hd ia">log.jtl</strong> (Windows)</li><li id="cada" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">sh jmeter.sh -n -t <strong class="hd ia">test_name.jmx</strong> -l <strong class="hd ia">log.jtl</strong> (Unix)</li></ul><section class="post body paragraphs wrapper"><p id="9f5f" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">В примерах команд выше <strong class="hd ia">test_name.jmx</strong> — имя сохранённого теста, а <strong class="hd ia">log.jtl</strong> — имя файла, в который будут сохранены результаты теста. Ключ <strong class="hd ia">-n </strong>нужен для запуска инструмента в режиме без интерфейса (чтобы повысить производительность), ключ <strong class="hd ia">-t</strong> указывается перед именем сохраненного файла с тестом, ключ <strong class="hd ia">-l</strong> указывается перед именем файла, который будет создан в ходе прохождения теста и содержать отчёт.</p><p id="c6a7" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">7. Запускаем тест и ждём его завершения.</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div class="cl cm jo"><div class="iu s em iv"><div class="jp ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="642" height="118" role="presentation" src="https://miro.medium.com/max/1284/1*joAzBUBzQTOKCyWwj7vtkQ.png" srcset="https://miro.medium.com/max/552/1*joAzBUBzQTOKCyWwj7vtkQ.png 276w, https://miro.medium.com/max/1104/1*joAzBUBzQTOKCyWwj7vtkQ.png 552w, https://miro.medium.com/max/1280/1*joAzBUBzQTOKCyWwj7vtkQ.png 640w, https://miro.medium.com/max/1284/1*joAzBUBzQTOKCyWwj7vtkQ.png 642w" sizes="642px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1284/1*joAzBUBzQTOKCyWwj7vtkQ.png" width="642" height="118" srcSet="https://miro.medium.com/max/552/1*joAzBUBzQTOKCyWwj7vtkQ.png 276w, https://miro.medium.com/max/1104/1*joAzBUBzQTOKCyWwj7vtkQ.png 552w, https://miro.medium.com/max/1280/1*joAzBUBzQTOKCyWwj7vtkQ.png 640w, https://miro.medium.com/max/1284/1*joAzBUBzQTOKCyWwj7vtkQ.png 642w" sizes="642px" role="presentation"/></noscript></div></div></div></figure><section class="post body paragraphs wrapper"><p id="209c" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">8. Далее, можно запустить JMeter командой <strong class="hd ia">jmeter</strong> (Windows) или <strong class="hd ia">sh jmeter.sh</strong> (Unix) отсюда же, из терминала/командной строки, или по старинке из папки <strong class="hd ia">/bin</strong>. После запуска нужно открыть сохранённый тест (в моём случае это doodles_test.jmx) и для него добавить отчёты. Самый простой отчёт — Summary Report, который добавляется через правый клик по Test Plan и, далее, Add/Listener/Summary Report. Listener’ы можно добавлять и в ходе настройки теста. Итак, Summary Report выглядит следующим образом:</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jf"><div class="iu s em iv"><div class="jq ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="420" role="presentation" src="https://miro.medium.com/max/1400/1*wjcynPaMi4JwkDxy11nsyQ.png" srcset="https://miro.medium.com/max/552/1*wjcynPaMi4JwkDxy11nsyQ.png 276w, https://miro.medium.com/max/1104/1*wjcynPaMi4JwkDxy11nsyQ.png 552w, https://miro.medium.com/max/1280/1*wjcynPaMi4JwkDxy11nsyQ.png 640w, https://miro.medium.com/max/1400/1*wjcynPaMi4JwkDxy11nsyQ.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*wjcynPaMi4JwkDxy11nsyQ.png" width="700" height="420" srcSet="https://miro.medium.com/max/552/1*wjcynPaMi4JwkDxy11nsyQ.png 276w, https://miro.medium.com/max/1104/1*wjcynPaMi4JwkDxy11nsyQ.png 552w, https://miro.medium.com/max/1280/1*wjcynPaMi4JwkDxy11nsyQ.png 640w, https://miro.medium.com/max/1400/1*wjcynPaMi4JwkDxy11nsyQ.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="766c" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">9. Чтобы посмотреть результаты теста, нужно нажать Browse…, найти файлик с логами в формате *.jtl, который был прописан в шаге 6, и открыть его. В результате будет следующее:</p></section><figure class="if ig ih ii ij ik cl cm paragraph-image"><div role="button" tabindex="0" class="il im em in aj io"><div class="cl cm jb"><div class="iu s em iv"><div class="je ix s"><div class="ip iq t u v ir aj ay is it">
<img alt="" class="ls no t u v ir aj c" width="700" height="423" role="presentation" src="https://miro.medium.com/max/1400/1*VSQWyRNxnU-_4xi4TFitBQ.png" srcset="https://miro.medium.com/max/552/1*VSQWyRNxnU-_4xi4TFitBQ.png 276w, https://miro.medium.com/max/1104/1*VSQWyRNxnU-_4xi4TFitBQ.png 552w, https://miro.medium.com/max/1280/1*VSQWyRNxnU-_4xi4TFitBQ.png 640w, https://miro.medium.com/max/1400/1*VSQWyRNxnU-_4xi4TFitBQ.png 700w" sizes="700px"><noscript>
<img alt="" class="t u v ir aj" src="https://miro.medium.com/max/1400/1*VSQWyRNxnU-_4xi4TFitBQ.png" width="700" height="423" srcSet="https://miro.medium.com/max/552/1*VSQWyRNxnU-_4xi4TFitBQ.png 276w, https://miro.medium.com/max/1104/1*VSQWyRNxnU-_4xi4TFitBQ.png 552w, https://miro.medium.com/max/1280/1*VSQWyRNxnU-_4xi4TFitBQ.png 640w, https://miro.medium.com/max/1400/1*VSQWyRNxnU-_4xi4TFitBQ.png 700w" sizes="700px" role="presentation"/></noscript></div></div></div></div></figure><section class="post body paragraphs wrapper"><p id="698a" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph="">10. Что можно понять из данного отчёта?</p></section><ul class=""><li id="464d" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy jg ic id bq" data-selectable-paragraph="">Было сделано 20 запросов (Samples) по указанному в конфиге адресу (10 пользователей по 2 раза каждый)</li><li id="83b6" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Среднее время ответа составило чуть меньше чем 1,1 секунды (Average); минимальное время ответа чуть менее чем 0,7 секунды (Min); максимальное время ответа чуть менее чем 1,5 секунды (Max).</li><li id="9add" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">В секунду проходило 6,4 запроса (Throughput).</li><li id="f2a6" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Std Dev — показатель стандартного отклонения. Насколько я знаю, им мало кто пользуется, но, раз уж он есть, то… Этот показатель позволяет оценить насколько сильно значения из выборки (результата тестового прогона) отличаются от рассчитанного среднего значения.</li><li id="2a44" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Error %—количество ошибок в процентах, которые вернул сервер</li><li id="0805" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Received и Sent KB/sec — количество полученных и отправленных данных</li><li id="6c19" class="hb hc dg hd b he jh hg hh hi ji hk hl hm jj ho hp hq jk hs ht hu jl hw hx hy jg ic id bq" data-selectable-paragraph="">Avg.Bytes — среднее количество полученных данных</li></ul></div></div></section><div class="n p ed jr js jt" role="separator"><span class="ju ej fv jv jw jx"></span><span class="ju ej fv jv jw jx"></span><span class="ju ej fv jv jw"></span></div><section class="cz da db dc dd" aria-label="post body section"><div class="n p"><div class="ab ac ae af ag de ai aj"><section class="post body paragraphs wrapper"><p id="017d" class="hb hc dg hd b he hf hg hh hi hj hk hl hm hn ho hp hq hr hs ht hu hv hw hx hy cz bq" aria-label="post body paragraph" data-selectable-paragraph=""><strong class="hd ia">Заключение: </strong>В данной статье я постарался описать, пожалуй, один из самых простых способов начала работы с Apache JMeter. Причина проста — когда-то мне самому нужна была наглядная пошаговая инструкция для пробного запуска моего первого нагрузочного теста. Конечно, можно (и нужно!) изучать <a class="et hz" href="https://jmeter.apache.org/usermanual/get-started.html" rel="noopener ugc nofollow" target="_blank">документацию по JMeter</a>, смотреть видео инструкции, собирать информацию по форумам, но на это требуется немалое количество времени, которое у тестировщиков, зачастую, в дефиците :)</p></section></div></div></section></div>
