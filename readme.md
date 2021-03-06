**1 ЛР:** Шестиразрядный параллельный регистр с дополнением enabled
------------------------------------------------------------------------------------------------------------------------------------------  
**2 ЛР:** Управляемый генератор синхросигналов  
------------------------------------------------------------------------------------------------------------------------------------------ 
Блок №1:										
На вход поступает синхросигнал clk.										
На выходе формируется сигнал с формой и указанными по варианту параметрами m и n, где m и n – количество тактов внешнего синхросигнала clk					

Блок №2:										
На вход поступает синхросигнал clk_in с блока №1.										
На выходе формируется сигнал clk_D уменьшенный по частоте в D раз.										
Форма clk_D должна сохранять пропорции clk_in.										
Делитель частоты D задан по варианту.										
										
Блок №3:										
На вход поступает синхросигнал clk_D с блока №2.										
На выходе формируется сигнал 16-разрядный сигнал, представляющий собой 16 опорных синхроимпульсов DCa[15..0].  
Блок работает одинаково при различной форме входного сигнала (clk или clk_in, или clk_D).  
По варианту: форма сигнала clk_in - a, m = 9, n = 3, делитель частоты D = 11.

**3 ЛР:** Разработать схему, включающую в себя буфер данных, модули ROM и RAM, подключенные к общей шине данных.		
------------------------------------------------------------------------------------------------------------------------------------------ 
Прочитать N байт (размер буфера) из ROM\RAM в буфер, подождать K тактов и записать данные из буфера по другому адресу в RAM.  
Повторить действия для другого источника.  
ROM -> буфер (N байт) - (подождать K тактов) -> RAM  
RAM -> буфер (N байт) -> (подождать K тактов) -> RAM  
По варианту: шина адреса - 6 бит, выводы ROM и RAM - синхронные, размер буфера - 7 байт, задержка - 6 тактов  

**4 ЛР:** Считывание, декодирование и выполнение команд.  
Способ адресации операндов в командах.	
------------------------------------------------------------------------------------------------------------------------------------------  
Разработать архитектуру системы команд (АСК) для команд выданных по варианту.  
Ввести шину адреса (ША), шину данных (ШД) и шину управления (ШУ).  
Разделить память на память данных (блок RAM) и память команд (блок ROM). На адресные входы завести ША.  
Ввод и вывод данных осуществлять через ШД.  
Ввести блок регистров общего назначения (РОН) и управляющую логику для него. Кол-во регистров 4-8-16 (на выбор).  
Написать микропрограмму (4-6 вызовов команд) в которой указать конкретные адреса памяти или регистров.  
Записать микропрограмму в память команд (ROM) (в файл *.hex или *.mif).  
Записать необходимые данные для микропрограммы в память данных (RAM) (в файл *.hex или *.mif).  
Разработать устройство управления (УУ) которое будет считывать, декодировать и выдавать управляющие сигналы для выполнения полученной команды.  
Ввести специальные регистры, разрядность которых определяется разрядностью ШД. Физически разместить их в блоке управления. Промоделировать работу схемы.  
По варианту: ША - 8; ШД - 7; команда 1 - const->M; адресация операнда-источника команды 1 - непосредственная; команда 2 - jz; адресация команды 2 - непосредственная.  

**5 ЛР:** Арбитраж шин  
------------------------------------------------------------------------------------------------------------------------------------------    
Смоделировать арбитраж шины по централизованной последовательной схеме с предоставлением подключенным к шине устройствам доступа в выделенный квант времени.  
По варианту: вид арбитажа - централизованный, вид подключения - последовательный, алгоритм смены приоритетов - статический (2  линии приоритета),  
вид шины - синхронизированная, количество ведущих устройств - 5, количество ведомых устройств - 3  

**6-7 ЛР:** Организация кэш-памяти. Взаимодействие кэш-памяти и ОЗУ 
------------------------------------------------------------------------------------------------------------------------------------------    
Обе лабораторные работы совмещены с одну.  
По варианту 6 ЛР: тип кэш-памяти - полностью ассоциативное отображение; количество строк кэш - 8; количество байт в строке - 8; количество модулей К - 0;  
замещение строк - случайное; кратность размера ОЗУ объему кэш-памяти - 4; разрядность ШД - 8 бит.  
По варианту 7 ЛР: запись в память - простая отложенная.  

**8 ЛР:** Динамическое предсказание условных переходов 
------------------------------------------------------------------------------------------------------------------------------------------      
PHT делать на регистрах. RAM не использовать. Работу схемы делать не за один такт, а за несколько. CLK приходит на все блоки, а не только на первый как в схеме.  
Дополнительно выводить на моделировании: state, new_state, pattern, GHR. Приходит запрос на предсказание (req) и PC[] (если есть по варианту).  
Формируется шаблон (pattern) и получается состояние из PHT. Согласно состоянию делается предсказание. Через несколько тактов приходит результат   
перехода (result, result_strob). После прихода результата, происходит изменение состояния и регистра GHR (если есть по варианту).  
Предсказание и результат перехода передавать по 2 пинам: 1 пин с самим предсказанием/результатом; 2 пин - стробирующий, указывает что результат валидный.		
По варианту: тип автомата - А2; количество бит шаблона - 6; формирование шаблона - PC.
