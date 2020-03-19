# Python-Webbrowser
#Just a simple app that opens links in btowser and saves the history to the text file.
import tkinter
from tkinter import messagebox
import webbrowser
import time
from PIL import Image,ImageTk
a=['.contrators','.cookin','.cool','.coop','.countr','.coupon','.course','.credit','.creditard','.cricke','.cruise','.dance','.date','.dating','.deals','.degree','.delivey','.democrt','.dental.dentis','.desi','.design','.diamons','.diet','.digita','.direct.directry','.discout','.doctor','.dog','.domain','.downlod','.earth','.educaton','.email','.energy','.enginer','.enginering','.enterpises','.equipmnt','.estate','.events','.exchane','.expert.expose','.expres','.fail','.faith','.family','.fans','.farm','.fashio','.film','.financ','.financal','.fish','.fishin','.fit','.fitnes','.flight','.floris','.flower','.fm','.footbal','.forex','.forsal','.foundaion','.fun','.fund','.furnitre','.futbol','.fyi','.galler','.game','.games','.garden','.gent','.gift','.gifts','.gives','.glass','.global','.gmbh','.gold','.golf','.graphis','.gratis','.green','.gripe','.group','.guide','.guitar','.guru','.haus','.healthare','.help','.hiphop','.hockey','.holdins','.holida','.horse','.hospitl','.host','.hostin','.house','.how','.immo','.immobiien','.industies','.ink','.institte','.insure','.interntional','.investents','.irish','.jewelr','.jobs','.juegos','.kaufen','.kim','.kitche','.kiwi','.land','.lawyer','.lease','.legal','.life','.lightig','.loans', '.lol','.london','.love','.ltd','.luxeluxury','.maison','.management','.market','.marketing','.mba','.media','.memorial','.men','.menu','.miami','.moda','.moe','.mom','.money','.mortgage','.moscow.','.movie','.navy', '.network','.news','.ninja','.observer','.one','.onl','.online','.ooo','.pageparis','.partners','.parts','.party','.pet','.photo','.photography','.photos','.pics','.pictures','.pink','.pizza','.plumbing','.plus','.poker','.press','.productions','.promo','.properties','.property','.protection','.pub','.qpon','.racing','.radio','.radio','.am','.radio.fm','.realty','.recipes','.red','.rehab','.reisen','.rent','.rentals','.repair','.report','.republican','.rest','.restaurant','.review','.reviews','.rich','.rip','.rocks','.rodeo','.run','.sale','.salon','.sarl','.school','.schule','.science','.security','.services','.sex','.sexy','.shiksha','.shoes','.shop','.shopping','.show','.singles','.site','.ski','.soccer','.social','.software','.solar','.solutions','.soy','.space','.sportstore','.stream','.studio','.study','.style','.sucks','.supplies','.supply','.support','.surf','.surgery','.systems','.tatar','.tattoo','.tax','.taxi','.team','.tech','.technology','.tennis','.theater','.theatre','.tickets','.tienda','.tips','.tires','.tirol','.today','.tools','.top','.tours','.town','.toys','.trade','.trading','.training','.tube','.tv','.university','.uno','.vacations','.vegas','.ventures','.vet','.viajes','.video','.villas','.vin','.vip','.vision','.vodka','.vote','.voting','.voto','.voyage','.watch','.webcam','.website','.wedding','.wien','.wiki','.win','.wine','.work','.works','.world','.wtf','.xyz','.yoga','.zone','.дети','.москва','.онлайн','.орг','.рус','.сайт','.ad','.aeafai','.al','.am','.aq','.as','.at','.awax','.az','.ba','.be','.bg','.bh','.bi','.bj','.bm','.bo','.bs','.bt','.ca','.cc','.cdcf','.cg','.ch','.ci','.cl','.cm','.cn','.co',
'co.ao','co.bw','co.ck','co.fk','co.id','co.il','co.in','co.ke','co.ls','co.mz','co.no','co.nz','co.th','co.tz','co.uk','co.uz','co.za','co.zm','co.zw','com.ai','com.ar', 'com.au','com.bd','com.bn','com.br','com.cn','com.cy','com.eg','com.et','com.fj','com.gh','com.gn','com.gt','com.gu','com.hk','com.jm','com.kh','com.kwcom.lb','com.lr', 'com.mt','com.mv','com.ng','com.ni','com.np','com.nrcom.om','com.pa','com.pl','com.py','com.qa','com.sacom.sb','com.sgcom.sv','com.sy','com.tr','com.tw','com.ua','com.uy',
'com.ve','com.vi','com.vncom.ye','.cr','.cu','.cx','.cz','.de','.dj','.dk','.dmdo','.dz','.ec','.ee','.eseu','.fi','.fo','.frga','.gd','.gegf','.gg','.gi','.gl','.gmgp','.gr','.gs','.gy','.hk','.hm','.hn','.hr','.ht','.hu','.ie','.im','.in','.in.ua','.io','.ir','.is','.it','.je','.jo','.jp','.kg','.ki','.kiev','.ua','.kn','.kr','.kykz','.li','.lk','.lt','.lu','.lv','.ly','.ma','.mc','.md','.me','.uk','.mg','.mk','.mo','.mpms','.mt','.mumw','.mxmy','.na','.nc''.net','.cnnf','.ng','.nl','.no','.nu','.nz','.org','.cn','.org','.uk','.pe','.ph','.pk','.pl','.pn','.pr','.ps','.pt','.re','.ro','.rs','.rw','.sd','.se','.sg','.sk','.sl','.sm','.si','.sn','.so','.sr','.st','.sz','.tc','.td','.tg','.tj','.tk','.tl','.tm','.tn','.to','.tt','.tw','.ua','.ug','.uk','.us','.vc','.vg','.vn','.vu','.ws','adygeya.ru','.adygeya.su','arkhangelsk.su','balashov.su','bashkiria.ru','bashkiria.su','bir.ru','bryansk.su','cbg.ru','dagestan.ru','dagestan.su','grozny.ru','grozny.suivanovo.su','kalmykia.ru','kalmykia.su','kaluga.su','karelia.su','khakassia.su','krasnodar.su','kurgan.su','lenug.su','marine.ru','mordovia.ru','mordovia.su','msk.ru','msk.su','murmansk.su','mytis.ru','nalchik.ru','nalchik.su','nov.ru','nov.su','obninsk.su','penza.su','pokrovsk.su','pyatigorsk.ru','sochi.su','spb.ru','spb.su','togliatti.su','troitsk.su','tula.su','tuva.su','vladikavkaz.ru','vladikavkaz.su','vladimir.ru','vladimir.su','vologda.su','.aero','.asia','.biz','.com','.info','.mobi','.name','.net','.org','.pro','.tel','.travel','.xxx','.рф','.com.ru','.exnet.su','.net','.ru','.org.ru', '.ppru','.academy','.accountant','.accountants','.actor','.adult','.africa','.agency','.airforce','.apartments','.app','.army','.art','.associates','.attorney','.auction','.audio','.auto','.band','.bank','.bar','.bargains','.bayern','.beer','.berlin','.best','.bet','.bid','.bike','.bingo','.bio','.black','.blackfriday','.blog','.blue','.boutique','.broker','.brussels','.build','.builders','.business','.buzz','.cab','.cafe','.cam','.camera','.camp','.capital' '.car','.cards','.care','.career','.careers','.cars','.casa','.cash','.casino','.cat','.catering','.center','.ceo','.charity','.chat','.cheap','.christmas','.church','.city','.claims','.cleaning','.click','.clinic','.clothig','.cloud','.club','.coach','.codes','.coffee','.colleg','.cologn','.communty','.compan','.computr','.condos','.constrction','.consuling','.gov']
def open_link():
     times=time.ctime()
     file=open('History_webbrowser.txt','a')
     history=times + "  "+link
     file.write('\n'+history)
     file.close()
     start=time.time()
     webbrowser.open(link)
     finish=time.time()
     finish=finish-start
     finish=round(finish)
     finish='страница была загружена за'+' '+str(finish)+' '+'секунд'
     messagebox.showinfo('Уведомление',finish)
def btn1_act():   
     global link
     link=ent.get()   
     start=link.find('.')
     i=link[start::] 
     if i in a:
            if link.startswith('http://') or link.startswith('https://') ==True:
                open_link()
            else: 
                link='https://'+link
                open_link()
     elif i not in a:
         link='https://www.google.com/search?source=hp&ei=Hc1OXqD4Gb6Ck74PqqeTkA4&q='+link
         open_link()
def GUI():   
        root=tkinter.Tk()
        file=r'gogo.png'
        a=Image.open(file)
        maga=ImageTk.PhotoImage(a)
        magal=tkinter.Label(root,image=maga)
        magal.place(relx=0.2777, rely=0.22)
        root.title('Webbrowser Google')
        root.geometry("650x500+300+300")
        btn1=tkinter.Button(root,text='Search',font=("Arial Bold", 11),fg='white',bg='indigo',width=8,height=0,command=btn1_act)
        btn1.place(relx=0.768, rely=0.49)
        global ent
        ent=tkinter.Entry(root,width=39,bd=6)
        ent['fg']='blue'
        ent['font']="Arial Bold",12
        ent.place(relx=0.2, rely=0.49999999)
        ent.focus()
        root.mainloop()
GUI()
