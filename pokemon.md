Pokemon
================

``` r
#Caso 2:r pokemon
library(datasets)
library(dplyr)
```

    ## Warning: package 'dplyr' was built under R version 4.0.4

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
wd = setwd("C:/Users/sebah/Desktop/U/mineria de datos/ayudantia 3")
pk = read.csv("pokemon.csv")
pk
```

    ##      X.                      Name   Type.1   Type.2 Total  HP Attack Defense
    ## 1     1                 Bulbasaur    Grass   Poison   318  45     49      49
    ## 2     2                   Ivysaur    Grass   Poison   405  60     62      63
    ## 3     3                  Venusaur    Grass   Poison   525  80     82      83
    ## 4     3     VenusaurMega Venusaur    Grass   Poison   625  80    100     123
    ## 5     4                Charmander     Fire            309  39     52      43
    ## 6     5                Charmeleon     Fire            405  58     64      58
    ## 7     6                 Charizard     Fire   Flying   534  78     84      78
    ## 8     6 CharizardMega Charizard X     Fire   Dragon   634  78    130     111
    ## 9     6 CharizardMega Charizard Y     Fire   Flying   634  78    104      78
    ## 10    7                  Squirtle    Water            314  44     48      65
    ## 11    8                 Wartortle    Water            405  59     63      80
    ## 12    9                 Blastoise    Water            530  79     83     100
    ## 13    9   BlastoiseMega Blastoise    Water            630  79    103     120
    ## 14   10                  Caterpie      Bug            195  45     30      35
    ## 15   11                   Metapod      Bug            205  50     20      55
    ## 16   12                Butterfree      Bug   Flying   395  60     45      50
    ## 17   13                    Weedle      Bug   Poison   195  40     35      30
    ## 18   14                    Kakuna      Bug   Poison   205  45     25      50
    ## 19   15                  Beedrill      Bug   Poison   395  65     90      40
    ## 20   15     BeedrillMega Beedrill      Bug   Poison   495  65    150      40
    ## 21   16                    Pidgey   Normal   Flying   251  40     45      40
    ## 22   17                 Pidgeotto   Normal   Flying   349  63     60      55
    ## 23   18                   Pidgeot   Normal   Flying   479  83     80      75
    ## 24   18       PidgeotMega Pidgeot   Normal   Flying   579  83     80      80
    ## 25   19                   Rattata   Normal            253  30     56      35
    ## 26   20                  Raticate   Normal            413  55     81      60
    ## 27   21                   Spearow   Normal   Flying   262  40     60      30
    ## 28   22                    Fearow   Normal   Flying   442  65     90      65
    ## 29   23                     Ekans   Poison            288  35     60      44
    ## 30   24                     Arbok   Poison            438  60     85      69
    ## 31   25                   Pikachu Electric            320  35     55      40
    ## 32   26                    Raichu Electric            485  60     90      55
    ## 33   27                 Sandshrew   Ground            300  50     75      85
    ## 34   28                 Sandslash   Ground            450  75    100     110
    ## 35   29                Nidoranâ\231\200   Poison            275  55     47      52
    ## 36   30                  Nidorina   Poison            365  70     62      67
    ## 37   31                 Nidoqueen   Poison   Ground   505  90     92      87
    ## 38   32                Nidoranâ\231‚   Poison            273  46     57      40
    ## 39   33                  Nidorino   Poison            365  61     72      57
    ## 40   34                  Nidoking   Poison   Ground   505  81    102      77
    ## 41   35                  Clefairy    Fairy            323  70     45      48
    ## 42   36                  Clefable    Fairy            483  95     70      73
    ## 43   37                    Vulpix     Fire            299  38     41      40
    ## 44   38                 Ninetales     Fire            505  73     76      75
    ## 45   39                Jigglypuff   Normal    Fairy   270 115     45      20
    ## 46   40                Wigglytuff   Normal    Fairy   435 140     70      45
    ## 47   41                     Zubat   Poison   Flying   245  40     45      35
    ## 48   42                    Golbat   Poison   Flying   455  75     80      70
    ## 49   43                    Oddish    Grass   Poison   320  45     50      55
    ## 50   44                     Gloom    Grass   Poison   395  60     65      70
    ## 51   45                 Vileplume    Grass   Poison   490  75     80      85
    ## 52   46                     Paras      Bug    Grass   285  35     70      55
    ## 53   47                  Parasect      Bug    Grass   405  60     95      80
    ## 54   48                   Venonat      Bug   Poison   305  60     55      50
    ## 55   49                  Venomoth      Bug   Poison   450  70     65      60
    ## 56   50                   Diglett   Ground            265  10     55      25
    ## 57   51                   Dugtrio   Ground            405  35     80      50
    ## 58   52                    Meowth   Normal            290  40     45      35
    ## 59   53                   Persian   Normal            440  65     70      60
    ## 60   54                   Psyduck    Water            320  50     52      48
    ## 61   55                   Golduck    Water            500  80     82      78
    ## 62   56                    Mankey Fighting            305  40     80      35
    ## 63   57                  Primeape Fighting            455  65    105      60
    ## 64   58                 Growlithe     Fire            350  55     70      45
    ## 65   59                  Arcanine     Fire            555  90    110      80
    ## 66   60                   Poliwag    Water            300  40     50      40
    ## 67   61                 Poliwhirl    Water            385  65     65      65
    ## 68   62                 Poliwrath    Water Fighting   510  90     95      95
    ## 69   63                      Abra  Psychic            310  25     20      15
    ## 70   64                   Kadabra  Psychic            400  40     35      30
    ## 71   65                  Alakazam  Psychic            500  55     50      45
    ## 72   65     AlakazamMega Alakazam  Psychic            590  55     50      65
    ## 73   66                    Machop Fighting            305  70     80      50
    ## 74   67                   Machoke Fighting            405  80    100      70
    ## 75   68                   Machamp Fighting            505  90    130      80
    ## 76   69                Bellsprout    Grass   Poison   300  50     75      35
    ## 77   70                Weepinbell    Grass   Poison   390  65     90      50
    ## 78   71                Victreebel    Grass   Poison   490  80    105      65
    ## 79   72                 Tentacool    Water   Poison   335  40     40      35
    ## 80   73                Tentacruel    Water   Poison   515  80     70      65
    ## 81   74                   Geodude     Rock   Ground   300  40     80     100
    ## 82   75                  Graveler     Rock   Ground   390  55     95     115
    ## 83   76                     Golem     Rock   Ground   495  80    120     130
    ## 84   77                    Ponyta     Fire            410  50     85      55
    ## 85   78                  Rapidash     Fire            500  65    100      70
    ## 86   79                  Slowpoke    Water  Psychic   315  90     65      65
    ## 87   80                   Slowbro    Water  Psychic   490  95     75     110
    ## 88   80       SlowbroMega Slowbro    Water  Psychic   590  95     75     180
    ## 89   81                 Magnemite Electric    Steel   325  25     35      70
    ## 90   82                  Magneton Electric    Steel   465  50     60      95
    ## 91   83                Farfetch'd   Normal   Flying   352  52     65      55
    ## 92   84                     Doduo   Normal   Flying   310  35     85      45
    ## 93   85                    Dodrio   Normal   Flying   460  60    110      70
    ## 94   86                      Seel    Water            325  65     45      55
    ## 95   87                   Dewgong    Water      Ice   475  90     70      80
    ## 96   88                    Grimer   Poison            325  80     80      50
    ## 97   89                       Muk   Poison            500 105    105      75
    ## 98   90                  Shellder    Water            305  30     65     100
    ## 99   91                  Cloyster    Water      Ice   525  50     95     180
    ## 100  92                    Gastly    Ghost   Poison   310  30     35      30
    ## 101  93                   Haunter    Ghost   Poison   405  45     50      45
    ## 102  94                    Gengar    Ghost   Poison   500  60     65      60
    ## 103  94         GengarMega Gengar    Ghost   Poison   600  60     65      80
    ## 104  95                      Onix     Rock   Ground   385  35     45     160
    ## 105  96                   Drowzee  Psychic            328  60     48      45
    ## 106  97                     Hypno  Psychic            483  85     73      70
    ## 107  98                    Krabby    Water            325  30    105      90
    ## 108  99                   Kingler    Water            475  55    130     115
    ## 109 100                   Voltorb Electric            330  40     30      50
    ## 110 101                 Electrode Electric            480  60     50      70
    ## 111 102                 Exeggcute    Grass  Psychic   325  60     40      80
    ## 112 103                 Exeggutor    Grass  Psychic   520  95     95      85
    ## 113 104                    Cubone   Ground            320  50     50      95
    ## 114 105                   Marowak   Ground            425  60     80     110
    ## 115 106                 Hitmonlee Fighting            455  50    120      53
    ## 116 107                Hitmonchan Fighting            455  50    105      79
    ## 117 108                 Lickitung   Normal            385  90     55      75
    ## 118 109                   Koffing   Poison            340  40     65      95
    ## 119 110                   Weezing   Poison            490  65     90     120
    ## 120 111                   Rhyhorn   Ground     Rock   345  80     85      95
    ## 121 112                    Rhydon   Ground     Rock   485 105    130     120
    ## 122 113                   Chansey   Normal            450 250      5       5
    ## 123 114                   Tangela    Grass            435  65     55     115
    ## 124 115                Kangaskhan   Normal            490 105     95      80
    ## 125 115 KangaskhanMega Kangaskhan   Normal            590 105    125     100
    ## 126 116                    Horsea    Water            295  30     40      70
    ## 127 117                    Seadra    Water            440  55     65      95
    ## 128 118                   Goldeen    Water            320  45     67      60
    ## 129 119                   Seaking    Water            450  80     92      65
    ## 130 120                    Staryu    Water            340  30     45      55
    ## 131 121                   Starmie    Water  Psychic   520  60     75      85
    ## 132 122                  Mr. Mime  Psychic    Fairy   460  40     45      65
    ## 133 123                   Scyther      Bug   Flying   500  70    110      80
    ## 134 124                      Jynx      Ice  Psychic   455  65     50      35
    ## 135 125                Electabuzz Electric            490  65     83      57
    ## 136 126                    Magmar     Fire            495  65     95      57
    ## 137 127                    Pinsir      Bug            500  65    125     100
    ## 138 127         PinsirMega Pinsir      Bug   Flying   600  65    155     120
    ## 139 128                    Tauros   Normal            490  75    100      95
    ## 140 129                  Magikarp    Water            200  20     10      55
    ## 141 130                  Gyarados    Water   Flying   540  95    125      79
    ## 142 130     GyaradosMega Gyarados    Water     Dark   640  95    155     109
    ## 143 131                    Lapras    Water      Ice   535 130     85      80
    ## 144 132                     Ditto   Normal            288  48     48      48
    ## 145 133                     Eevee   Normal            325  55     55      50
    ## 146 134                  Vaporeon    Water            525 130     65      60
    ## 147 135                   Jolteon Electric            525  65     65      60
    ## 148 136                   Flareon     Fire            525  65    130      60
    ## 149 137                   Porygon   Normal            395  65     60      70
    ## 150 138                   Omanyte     Rock    Water   355  35     40     100
    ## 151 139                   Omastar     Rock    Water   495  70     60     125
    ## 152 140                    Kabuto     Rock    Water   355  30     80      90
    ## 153 141                  Kabutops     Rock    Water   495  60    115     105
    ## 154 142                Aerodactyl     Rock   Flying   515  80    105      65
    ## 155 142 AerodactylMega Aerodactyl     Rock   Flying   615  80    135      85
    ## 156 143                   Snorlax   Normal            540 160    110      65
    ## 157 144                  Articuno      Ice   Flying   580  90     85     100
    ## 158 145                    Zapdos Electric   Flying   580  90     90      85
    ## 159 146                   Moltres     Fire   Flying   580  90    100      90
    ## 160 147                   Dratini   Dragon            300  41     64      45
    ## 161 148                 Dragonair   Dragon            420  61     84      65
    ## 162 149                 Dragonite   Dragon   Flying   600  91    134      95
    ## 163 150                    Mewtwo  Psychic            680 106    110      90
    ## 164 150       MewtwoMega Mewtwo X  Psychic Fighting   780 106    190     100
    ## 165 150       MewtwoMega Mewtwo Y  Psychic            780 106    150      70
    ## 166 151                       Mew  Psychic            600 100    100     100
    ## 167 152                 Chikorita    Grass            318  45     49      65
    ## 168 153                   Bayleef    Grass            405  60     62      80
    ## 169 154                  Meganium    Grass            525  80     82     100
    ## 170 155                 Cyndaquil     Fire            309  39     52      43
    ## 171 156                   Quilava     Fire            405  58     64      58
    ## 172 157                Typhlosion     Fire            534  78     84      78
    ## 173 158                  Totodile    Water            314  50     65      64
    ## 174 159                  Croconaw    Water            405  65     80      80
    ## 175 160                Feraligatr    Water            530  85    105     100
    ## 176 161                   Sentret   Normal            215  35     46      34
    ## 177 162                    Furret   Normal            415  85     76      64
    ## 178 163                  Hoothoot   Normal   Flying   262  60     30      30
    ## 179 164                   Noctowl   Normal   Flying   442 100     50      50
    ## 180 165                    Ledyba      Bug   Flying   265  40     20      30
    ## 181 166                    Ledian      Bug   Flying   390  55     35      50
    ## 182 167                  Spinarak      Bug   Poison   250  40     60      40
    ## 183 168                   Ariados      Bug   Poison   390  70     90      70
    ## 184 169                    Crobat   Poison   Flying   535  85     90      80
    ## 185 170                  Chinchou    Water Electric   330  75     38      38
    ## 186 171                   Lanturn    Water Electric   460 125     58      58
    ## 187 172                     Pichu Electric            205  20     40      15
    ## 188 173                    Cleffa    Fairy            218  50     25      28
    ## 189 174                 Igglybuff   Normal    Fairy   210  90     30      15
    ## 190 175                    Togepi    Fairy            245  35     20      65
    ## 191 176                   Togetic    Fairy   Flying   405  55     40      85
    ## 192 177                      Natu  Psychic   Flying   320  40     50      45
    ## 193 178                      Xatu  Psychic   Flying   470  65     75      70
    ## 194 179                    Mareep Electric            280  55     40      40
    ## 195 180                   Flaaffy Electric            365  70     55      55
    ## 196 181                  Ampharos Electric            510  90     75      85
    ## 197 181     AmpharosMega Ampharos Electric   Dragon   610  90     95     105
    ## 198 182                 Bellossom    Grass            490  75     80      95
    ## 199 183                    Marill    Water    Fairy   250  70     20      50
    ## 200 184                 Azumarill    Water    Fairy   420 100     50      80
    ## 201 185                 Sudowoodo     Rock            410  70    100     115
    ## 202 186                  Politoed    Water            500  90     75      75
    ## 203 187                    Hoppip    Grass   Flying   250  35     35      40
    ## 204 188                  Skiploom    Grass   Flying   340  55     45      50
    ## 205 189                  Jumpluff    Grass   Flying   460  75     55      70
    ## 206 190                     Aipom   Normal            360  55     70      55
    ## 207 191                   Sunkern    Grass            180  30     30      30
    ## 208 192                  Sunflora    Grass            425  75     75      55
    ## 209 193                     Yanma      Bug   Flying   390  65     65      45
    ## 210 194                    Wooper    Water   Ground   210  55     45      45
    ## 211 195                  Quagsire    Water   Ground   430  95     85      85
    ## 212 196                    Espeon  Psychic            525  65     65      60
    ## 213 197                   Umbreon     Dark            525  95     65     110
    ## 214 198                   Murkrow     Dark   Flying   405  60     85      42
    ## 215 199                  Slowking    Water  Psychic   490  95     75      80
    ## 216 200                Misdreavus    Ghost            435  60     60      60
    ## 217 201                     Unown  Psychic            336  48     72      48
    ## 218 202                 Wobbuffet  Psychic            405 190     33      58
    ## 219 203                 Girafarig   Normal  Psychic   455  70     80      65
    ## 220 204                    Pineco      Bug            290  50     65      90
    ## 221 205                Forretress      Bug    Steel   465  75     90     140
    ## 222 206                 Dunsparce   Normal            415 100     70      70
    ## 223 207                    Gligar   Ground   Flying   430  65     75     105
    ## 224 208                   Steelix    Steel   Ground   510  75     85     200
    ## 225 208       SteelixMega Steelix    Steel   Ground   610  75    125     230
    ## 226 209                  Snubbull    Fairy            300  60     80      50
    ## 227 210                  Granbull    Fairy            450  90    120      75
    ## 228 211                  Qwilfish    Water   Poison   430  65     95      75
    ## 229 212                    Scizor      Bug    Steel   500  70    130     100
    ## 230 212         ScizorMega Scizor      Bug    Steel   600  70    150     140
    ## 231 213                   Shuckle      Bug     Rock   505  20     10     230
    ## 232 214                 Heracross      Bug Fighting   500  80    125      75
    ## 233 214   HeracrossMega Heracross      Bug Fighting   600  80    185     115
    ## 234 215                   Sneasel     Dark      Ice   430  55     95      55
    ## 235 216                 Teddiursa   Normal            330  60     80      50
    ## 236 217                  Ursaring   Normal            500  90    130      75
    ## 237 218                    Slugma     Fire            250  40     40      40
    ## 238 219                  Magcargo     Fire     Rock   410  50     50     120
    ## 239 220                    Swinub      Ice   Ground   250  50     50      40
    ## 240 221                 Piloswine      Ice   Ground   450 100    100      80
    ## 241 222                   Corsola    Water     Rock   380  55     55      85
    ## 242 223                  Remoraid    Water            300  35     65      35
    ## 243 224                 Octillery    Water            480  75    105      75
    ## 244 225                  Delibird      Ice   Flying   330  45     55      45
    ## 245 226                   Mantine    Water   Flying   465  65     40      70
    ## 246 227                  Skarmory    Steel   Flying   465  65     80     140
    ## 247 228                  Houndour     Dark     Fire   330  45     60      30
    ## 248 229                  Houndoom     Dark     Fire   500  75     90      50
    ## 249 229     HoundoomMega Houndoom     Dark     Fire   600  75     90      90
    ## 250 230                   Kingdra    Water   Dragon   540  75     95      95
    ## 251 231                    Phanpy   Ground            330  90     60      60
    ## 252 232                   Donphan   Ground            500  90    120     120
    ## 253 233                  Porygon2   Normal            515  85     80      90
    ## 254 234                  Stantler   Normal            465  73     95      62
    ## 255 235                  Smeargle   Normal            250  55     20      35
    ## 256 236                   Tyrogue Fighting            210  35     35      35
    ## 257 237                 Hitmontop Fighting            455  50     95      95
    ## 258 238                  Smoochum      Ice  Psychic   305  45     30      15
    ## 259 239                    Elekid Electric            360  45     63      37
    ## 260 240                     Magby     Fire            365  45     75      37
    ## 261 241                   Miltank   Normal            490  95     80     105
    ## 262 242                   Blissey   Normal            540 255     10      10
    ## 263 243                    Raikou Electric            580  90     85      75
    ## 264 244                     Entei     Fire            580 115    115      85
    ## 265 245                   Suicune    Water            580 100     75     115
    ## 266 246                  Larvitar     Rock   Ground   300  50     64      50
    ## 267 247                   Pupitar     Rock   Ground   410  70     84      70
    ## 268 248                 Tyranitar     Rock     Dark   600 100    134     110
    ## 269 248   TyranitarMega Tyranitar     Rock     Dark   700 100    164     150
    ## 270 249                     Lugia  Psychic   Flying   680 106     90     130
    ## 271 250                     Ho-oh     Fire   Flying   680 106    130      90
    ## 272 251                    Celebi  Psychic    Grass   600 100    100     100
    ## 273 252                   Treecko    Grass            310  40     45      35
    ## 274 253                   Grovyle    Grass            405  50     65      45
    ## 275 254                  Sceptile    Grass            530  70     85      65
    ## 276 254     SceptileMega Sceptile    Grass   Dragon   630  70    110      75
    ## 277 255                   Torchic     Fire            310  45     60      40
    ## 278 256                 Combusken     Fire Fighting   405  60     85      60
    ## 279 257                  Blaziken     Fire Fighting   530  80    120      70
    ## 280 257     BlazikenMega Blaziken     Fire Fighting   630  80    160      80
    ## 281 258                    Mudkip    Water            310  50     70      50
    ## 282 259                 Marshtomp    Water   Ground   405  70     85      70
    ## 283 260                  Swampert    Water   Ground   535 100    110      90
    ## 284 260     SwampertMega Swampert    Water   Ground   635 100    150     110
    ## 285 261                 Poochyena     Dark            220  35     55      35
    ## 286 262                 Mightyena     Dark            420  70     90      70
    ## 287 263                 Zigzagoon   Normal            240  38     30      41
    ## 288 264                   Linoone   Normal            420  78     70      61
    ## 289 265                   Wurmple      Bug            195  45     45      35
    ## 290 266                   Silcoon      Bug            205  50     35      55
    ## 291 267                 Beautifly      Bug   Flying   395  60     70      50
    ## 292 268                   Cascoon      Bug            205  50     35      55
    ## 293 269                    Dustox      Bug   Poison   385  60     50      70
    ## 294 270                     Lotad    Water    Grass   220  40     30      30
    ## 295 271                    Lombre    Water    Grass   340  60     50      50
    ## 296 272                  Ludicolo    Water    Grass   480  80     70      70
    ## 297 273                    Seedot    Grass            220  40     40      50
    ## 298 274                   Nuzleaf    Grass     Dark   340  70     70      40
    ## 299 275                   Shiftry    Grass     Dark   480  90    100      60
    ## 300 276                   Taillow   Normal   Flying   270  40     55      30
    ## 301 277                   Swellow   Normal   Flying   430  60     85      60
    ## 302 278                   Wingull    Water   Flying   270  40     30      30
    ## 303 279                  Pelipper    Water   Flying   430  60     50     100
    ## 304 280                     Ralts  Psychic    Fairy   198  28     25      25
    ## 305 281                    Kirlia  Psychic    Fairy   278  38     35      35
    ## 306 282                 Gardevoir  Psychic    Fairy   518  68     65      65
    ## 307 282   GardevoirMega Gardevoir  Psychic    Fairy   618  68     85      65
    ## 308 283                   Surskit      Bug    Water   269  40     30      32
    ## 309 284                Masquerain      Bug   Flying   414  70     60      62
    ## 310 285                 Shroomish    Grass            295  60     40      60
    ## 311 286                   Breloom    Grass Fighting   460  60    130      80
    ## 312 287                   Slakoth   Normal            280  60     60      60
    ## 313 288                  Vigoroth   Normal            440  80     80      80
    ## 314 289                   Slaking   Normal            670 150    160     100
    ## 315 290                   Nincada      Bug   Ground   266  31     45      90
    ## 316 291                   Ninjask      Bug   Flying   456  61     90      45
    ## 317 292                  Shedinja      Bug    Ghost   236   1     90      45
    ## 318 293                   Whismur   Normal            240  64     51      23
    ## 319 294                   Loudred   Normal            360  84     71      43
    ## 320 295                   Exploud   Normal            490 104     91      63
    ## 321 296                  Makuhita Fighting            237  72     60      30
    ## 322 297                  Hariyama Fighting            474 144    120      60
    ## 323 298                   Azurill   Normal    Fairy   190  50     20      40
    ## 324 299                  Nosepass     Rock            375  30     45     135
    ## 325 300                    Skitty   Normal            260  50     45      45
    ## 326 301                  Delcatty   Normal            380  70     65      65
    ## 327 302                   Sableye     Dark    Ghost   380  50     75      75
    ## 328 302       SableyeMega Sableye     Dark    Ghost   480  50     85     125
    ## 329 303                    Mawile    Steel    Fairy   380  50     85      85
    ## 330 303         MawileMega Mawile    Steel    Fairy   480  50    105     125
    ## 331 304                      Aron    Steel     Rock   330  50     70     100
    ## 332 305                    Lairon    Steel     Rock   430  60     90     140
    ## 333 306                    Aggron    Steel     Rock   530  70    110     180
    ## 334 306         AggronMega Aggron    Steel            630  70    140     230
    ## 335 307                  Meditite Fighting  Psychic   280  30     40      55
    ## 336 308                  Medicham Fighting  Psychic   410  60     60      75
    ## 337 308     MedichamMega Medicham Fighting  Psychic   510  60    100      85
    ## 338 309                 Electrike Electric            295  40     45      40
    ## 339 310                 Manectric Electric            475  70     75      60
    ## 340 310   ManectricMega Manectric Electric            575  70     75      80
    ## 341 311                    Plusle Electric            405  60     50      40
    ## 342 312                     Minun Electric            405  60     40      50
    ## 343 313                   Volbeat      Bug            400  65     73      55
    ## 344 314                  Illumise      Bug            400  65     47      55
    ## 345 315                   Roselia    Grass   Poison   400  50     60      45
    ## 346 316                    Gulpin   Poison            302  70     43      53
    ## 347 317                    Swalot   Poison            467 100     73      83
    ## 348 318                  Carvanha    Water     Dark   305  45     90      20
    ## 349 319                  Sharpedo    Water     Dark   460  70    120      40
    ## 350 319     SharpedoMega Sharpedo    Water     Dark   560  70    140      70
    ## 351 320                   Wailmer    Water            400 130     70      35
    ## 352 321                   Wailord    Water            500 170     90      45
    ## 353 322                     Numel     Fire   Ground   305  60     60      40
    ## 354 323                  Camerupt     Fire   Ground   460  70    100      70
    ## 355 323     CameruptMega Camerupt     Fire   Ground   560  70    120     100
    ## 356 324                   Torkoal     Fire            470  70     85     140
    ## 357 325                    Spoink  Psychic            330  60     25      35
    ## 358 326                   Grumpig  Psychic            470  80     45      65
    ## 359 327                    Spinda   Normal            360  60     60      60
    ## 360 328                  Trapinch   Ground            290  45    100      45
    ## 361 329                   Vibrava   Ground   Dragon   340  50     70      50
    ## 362 330                    Flygon   Ground   Dragon   520  80    100      80
    ## 363 331                    Cacnea    Grass            335  50     85      40
    ## 364 332                  Cacturne    Grass     Dark   475  70    115      60
    ## 365 333                    Swablu   Normal   Flying   310  45     40      60
    ## 366 334                   Altaria   Dragon   Flying   490  75     70      90
    ## 367 334       AltariaMega Altaria   Dragon    Fairy   590  75    110     110
    ## 368 335                  Zangoose   Normal            458  73    115      60
    ## 369 336                   Seviper   Poison            458  73    100      60
    ## 370 337                  Lunatone     Rock  Psychic   440  70     55      65
    ## 371 338                   Solrock     Rock  Psychic   440  70     95      85
    ## 372 339                  Barboach    Water   Ground   288  50     48      43
    ## 373 340                  Whiscash    Water   Ground   468 110     78      73
    ## 374 341                  Corphish    Water            308  43     80      65
    ## 375 342                 Crawdaunt    Water     Dark   468  63    120      85
    ## 376 343                    Baltoy   Ground  Psychic   300  40     40      55
    ## 377 344                   Claydol   Ground  Psychic   500  60     70     105
    ## 378 345                    Lileep     Rock    Grass   355  66     41      77
    ## 379 346                   Cradily     Rock    Grass   495  86     81      97
    ## 380 347                   Anorith     Rock      Bug   355  45     95      50
    ## 381 348                   Armaldo     Rock      Bug   495  75    125     100
    ## 382 349                    Feebas    Water            200  20     15      20
    ## 383 350                   Milotic    Water            540  95     60      79
    ## 384 351                  Castform   Normal            420  70     70      70
    ## 385 352                   Kecleon   Normal            440  60     90      70
    ## 386 353                   Shuppet    Ghost            295  44     75      35
    ## 387 354                   Banette    Ghost            455  64    115      65
    ## 388 354       BanetteMega Banette    Ghost            555  64    165      75
    ## 389 355                   Duskull    Ghost            295  20     40      90
    ## 390 356                  Dusclops    Ghost            455  40     70     130
    ## 391 357                   Tropius    Grass   Flying   460  99     68      83
    ## 392 358                  Chimecho  Psychic            425  65     50      70
    ## 393 359                     Absol     Dark            465  65    130      60
    ## 394 359           AbsolMega Absol     Dark            565  65    150      60
    ## 395 360                    Wynaut  Psychic            260  95     23      48
    ## 396 361                   Snorunt      Ice            300  50     50      50
    ## 397 362                    Glalie      Ice            480  80     80      80
    ## 398 362         GlalieMega Glalie      Ice            580  80    120      80
    ## 399 363                    Spheal      Ice    Water   290  70     40      50
    ## 400 364                    Sealeo      Ice    Water   410  90     60      70
    ## 401 365                   Walrein      Ice    Water   530 110     80      90
    ## 402 366                  Clamperl    Water            345  35     64      85
    ## 403 367                   Huntail    Water            485  55    104     105
    ## 404 368                  Gorebyss    Water            485  55     84     105
    ## 405 369                 Relicanth    Water     Rock   485 100     90     130
    ## 406 370                   Luvdisc    Water            330  43     30      55
    ## 407 371                     Bagon   Dragon            300  45     75      60
    ## 408 372                   Shelgon   Dragon            420  65     95     100
    ## 409 373                 Salamence   Dragon   Flying   600  95    135      80
    ## 410 373   SalamenceMega Salamence   Dragon   Flying   700  95    145     130
    ## 411 374                    Beldum    Steel  Psychic   300  40     55      80
    ## 412 375                    Metang    Steel  Psychic   420  60     75     100
    ## 413 376                 Metagross    Steel  Psychic   600  80    135     130
    ## 414 376   MetagrossMega Metagross    Steel  Psychic   700  80    145     150
    ## 415 377                  Regirock     Rock            580  80    100     200
    ## 416 378                    Regice      Ice            580  80     50     100
    ## 417 379                 Registeel    Steel            580  80     75     150
    ## 418 380                    Latias   Dragon  Psychic   600  80     80      90
    ## 419 380         LatiasMega Latias   Dragon  Psychic   700  80    100     120
    ## 420 381                    Latios   Dragon  Psychic   600  80     90      80
    ## 421 381         LatiosMega Latios   Dragon  Psychic   700  80    130     100
    ## 422 382                    Kyogre    Water            670 100    100      90
    ## 423 382       KyogrePrimal Kyogre    Water            770 100    150      90
    ## 424 383                   Groudon   Ground            670 100    150     140
    ## 425 383     GroudonPrimal Groudon   Ground     Fire   770 100    180     160
    ## 426 384                  Rayquaza   Dragon   Flying   680 105    150      90
    ## 427 384     RayquazaMega Rayquaza   Dragon   Flying   780 105    180     100
    ## 428 385                   Jirachi    Steel  Psychic   600 100    100     100
    ## 429 386        DeoxysNormal Forme  Psychic            600  50    150      50
    ## 430 386        DeoxysAttack Forme  Psychic            600  50    180      20
    ## 431 386       DeoxysDefense Forme  Psychic            600  50     70     160
    ## 432 386         DeoxysSpeed Forme  Psychic            600  50     95      90
    ## 433 387                   Turtwig    Grass            318  55     68      64
    ## 434 388                    Grotle    Grass            405  75     89      85
    ## 435 389                  Torterra    Grass   Ground   525  95    109     105
    ## 436 390                  Chimchar     Fire            309  44     58      44
    ## 437 391                  Monferno     Fire Fighting   405  64     78      52
    ## 438 392                 Infernape     Fire Fighting   534  76    104      71
    ## 439 393                    Piplup    Water            314  53     51      53
    ## 440 394                  Prinplup    Water            405  64     66      68
    ## 441 395                  Empoleon    Water    Steel   530  84     86      88
    ## 442 396                    Starly   Normal   Flying   245  40     55      30
    ## 443 397                  Staravia   Normal   Flying   340  55     75      50
    ## 444 398                 Staraptor   Normal   Flying   485  85    120      70
    ## 445 399                    Bidoof   Normal            250  59     45      40
    ## 446 400                   Bibarel   Normal    Water   410  79     85      60
    ## 447 401                 Kricketot      Bug            194  37     25      41
    ## 448 402                Kricketune      Bug            384  77     85      51
    ## 449 403                     Shinx Electric            263  45     65      34
    ## 450 404                     Luxio Electric            363  60     85      49
    ## 451 405                    Luxray Electric            523  80    120      79
    ## 452 406                     Budew    Grass   Poison   280  40     30      35
    ## 453 407                  Roserade    Grass   Poison   515  60     70      65
    ## 454 408                  Cranidos     Rock            350  67    125      40
    ## 455 409                 Rampardos     Rock            495  97    165      60
    ## 456 410                  Shieldon     Rock    Steel   350  30     42     118
    ## 457 411                 Bastiodon     Rock    Steel   495  60     52     168
    ## 458 412                     Burmy      Bug            224  40     29      45
    ## 459 413       WormadamPlant Cloak      Bug    Grass   424  60     59      85
    ## 460 413       WormadamSandy Cloak      Bug   Ground   424  60     79     105
    ## 461 413       WormadamTrash Cloak      Bug    Steel   424  60     69      95
    ## 462 414                    Mothim      Bug   Flying   424  70     94      50
    ## 463 415                    Combee      Bug   Flying   244  30     30      42
    ## 464 416                 Vespiquen      Bug   Flying   474  70     80     102
    ## 465 417                 Pachirisu Electric            405  60     45      70
    ## 466 418                    Buizel    Water            330  55     65      35
    ## 467 419                  Floatzel    Water            495  85    105      55
    ## 468 420                   Cherubi    Grass            275  45     35      45
    ## 469 421                   Cherrim    Grass            450  70     60      70
    ## 470 422                   Shellos    Water            325  76     48      48
    ## 471 423                 Gastrodon    Water   Ground   475 111     83      68
    ## 472 424                   Ambipom   Normal            482  75    100      66
    ## 473 425                  Drifloon    Ghost   Flying   348  90     50      34
    ## 474 426                  Drifblim    Ghost   Flying   498 150     80      44
    ## 475 427                   Buneary   Normal            350  55     66      44
    ## 476 428                   Lopunny   Normal            480  65     76      84
    ## 477 428       LopunnyMega Lopunny   Normal Fighting   580  65    136      94
    ## 478 429                 Mismagius    Ghost            495  60     60      60
    ## 479 430                 Honchkrow     Dark   Flying   505 100    125      52
    ## 480 431                   Glameow   Normal            310  49     55      42
    ## 481 432                   Purugly   Normal            452  71     82      64
    ## 482 433                 Chingling  Psychic            285  45     30      50
    ## 483 434                    Stunky   Poison     Dark   329  63     63      47
    ## 484 435                  Skuntank   Poison     Dark   479 103     93      67
    ## 485 436                   Bronzor    Steel  Psychic   300  57     24      86
    ## 486 437                  Bronzong    Steel  Psychic   500  67     89     116
    ## 487 438                    Bonsly     Rock            290  50     80      95
    ## 488 439                  Mime Jr.  Psychic    Fairy   310  20     25      45
    ## 489 440                   Happiny   Normal            220 100      5       5
    ## 490 441                    Chatot   Normal   Flying   411  76     65      45
    ## 491 442                 Spiritomb    Ghost     Dark   485  50     92     108
    ## 492 443                     Gible   Dragon   Ground   300  58     70      45
    ## 493 444                    Gabite   Dragon   Ground   410  68     90      65
    ## 494 445                  Garchomp   Dragon   Ground   600 108    130      95
    ## 495 445     GarchompMega Garchomp   Dragon   Ground   700 108    170     115
    ## 496 446                  Munchlax   Normal            390 135     85      40
    ## 497 447                     Riolu Fighting            285  40     70      40
    ## 498 448                   Lucario Fighting    Steel   525  70    110      70
    ## 499 448       LucarioMega Lucario Fighting    Steel   625  70    145      88
    ## 500 449                Hippopotas   Ground            330  68     72      78
    ## 501 450                 Hippowdon   Ground            525 108    112     118
    ## 502 451                   Skorupi   Poison      Bug   330  40     50      90
    ## 503 452                   Drapion   Poison     Dark   500  70     90     110
    ## 504 453                  Croagunk   Poison Fighting   300  48     61      40
    ## 505 454                 Toxicroak   Poison Fighting   490  83    106      65
    ## 506 455                 Carnivine    Grass            454  74    100      72
    ## 507 456                   Finneon    Water            330  49     49      56
    ## 508 457                  Lumineon    Water            460  69     69      76
    ## 509 458                   Mantyke    Water   Flying   345  45     20      50
    ## 510 459                    Snover    Grass      Ice   334  60     62      50
    ## 511 460                 Abomasnow    Grass      Ice   494  90     92      75
    ## 512 460   AbomasnowMega Abomasnow    Grass      Ice   594  90    132     105
    ## 513 461                   Weavile     Dark      Ice   510  70    120      65
    ## 514 462                 Magnezone Electric    Steel   535  70     70     115
    ## 515 463                Lickilicky   Normal            515 110     85      95
    ## 516 464                 Rhyperior   Ground     Rock   535 115    140     130
    ## 517 465                 Tangrowth    Grass            535 100    100     125
    ## 518 466                Electivire Electric            540  75    123      67
    ## 519 467                 Magmortar     Fire            540  75     95      67
    ## 520 468                  Togekiss    Fairy   Flying   545  85     50      95
    ## 521 469                   Yanmega      Bug   Flying   515  86     76      86
    ## 522 470                   Leafeon    Grass            525  65    110     130
    ## 523 471                   Glaceon      Ice            525  65     60     110
    ## 524 472                   Gliscor   Ground   Flying   510  75     95     125
    ## 525 473                 Mamoswine      Ice   Ground   530 110    130      80
    ## 526 474                 Porygon-Z   Normal            535  85     80      70
    ## 527 475                   Gallade  Psychic Fighting   518  68    125      65
    ## 528 475       GalladeMega Gallade  Psychic Fighting   618  68    165      95
    ## 529 476                 Probopass     Rock    Steel   525  60     55     145
    ## 530 477                  Dusknoir    Ghost            525  45    100     135
    ## 531 478                  Froslass      Ice    Ghost   480  70     80      70
    ## 532 479                     Rotom Electric    Ghost   440  50     50      77
    ## 533 479           RotomHeat Rotom Electric     Fire   520  50     65     107
    ## 534 479           RotomWash Rotom Electric    Water   520  50     65     107
    ## 535 479          RotomFrost Rotom Electric      Ice   520  50     65     107
    ## 536 479            RotomFan Rotom Electric   Flying   520  50     65     107
    ## 537 479            RotomMow Rotom Electric    Grass   520  50     65     107
    ## 538 480                      Uxie  Psychic            580  75     75     130
    ## 539 481                   Mesprit  Psychic            580  80    105     105
    ## 540 482                     Azelf  Psychic            580  75    125      70
    ## 541 483                    Dialga    Steel   Dragon   680 100    120     120
    ## 542 484                    Palkia    Water   Dragon   680  90    120     100
    ## 543 485                   Heatran     Fire    Steel   600  91     90     106
    ## 544 486                 Regigigas   Normal            670 110    160     110
    ## 545 487     GiratinaAltered Forme    Ghost   Dragon   680 150    100     120
    ## 546 487      GiratinaOrigin Forme    Ghost   Dragon   680 150    120     100
    ## 547 488                 Cresselia  Psychic            600 120     70     120
    ## 548 489                    Phione    Water            480  80     80      80
    ## 549 490                   Manaphy    Water            600 100    100     100
    ## 550 491                   Darkrai     Dark            600  70     90      90
    ## 551 492         ShayminLand Forme    Grass            600 100    100     100
    ## 552 492          ShayminSky Forme    Grass   Flying   600 100    103      75
    ## 553 493                    Arceus   Normal            720 120    120     120
    ## 554 494                   Victini  Psychic     Fire   600 100    100     100
    ## 555 495                     Snivy    Grass            308  45     45      55
    ## 556 496                   Servine    Grass            413  60     60      75
    ## 557 497                 Serperior    Grass            528  75     75      95
    ## 558 498                     Tepig     Fire            308  65     63      45
    ## 559 499                   Pignite     Fire Fighting   418  90     93      55
    ## 560 500                    Emboar     Fire Fighting   528 110    123      65
    ## 561 501                  Oshawott    Water            308  55     55      45
    ## 562 502                    Dewott    Water            413  75     75      60
    ## 563 503                  Samurott    Water            528  95    100      85
    ## 564 504                    Patrat   Normal            255  45     55      39
    ## 565 505                   Watchog   Normal            420  60     85      69
    ## 566 506                  Lillipup   Normal            275  45     60      45
    ## 567 507                   Herdier   Normal            370  65     80      65
    ## 568 508                 Stoutland   Normal            500  85    110      90
    ## 569 509                  Purrloin     Dark            281  41     50      37
    ## 570 510                   Liepard     Dark            446  64     88      50
    ## 571 511                   Pansage    Grass            316  50     53      48
    ## 572 512                  Simisage    Grass            498  75     98      63
    ## 573 513                   Pansear     Fire            316  50     53      48
    ## 574 514                  Simisear     Fire            498  75     98      63
    ## 575 515                   Panpour    Water            316  50     53      48
    ## 576 516                  Simipour    Water            498  75     98      63
    ## 577 517                     Munna  Psychic            292  76     25      45
    ## 578 518                  Musharna  Psychic            487 116     55      85
    ## 579 519                    Pidove   Normal   Flying   264  50     55      50
    ## 580 520                 Tranquill   Normal   Flying   358  62     77      62
    ## 581 521                  Unfezant   Normal   Flying   488  80    115      80
    ## 582 522                   Blitzle Electric            295  45     60      32
    ## 583 523                 Zebstrika Electric            497  75    100      63
    ## 584 524                Roggenrola     Rock            280  55     75      85
    ## 585 525                   Boldore     Rock            390  70    105     105
    ## 586 526                  Gigalith     Rock            515  85    135     130
    ## 587 527                    Woobat  Psychic   Flying   313  55     45      43
    ## 588 528                   Swoobat  Psychic   Flying   425  67     57      55
    ## 589 529                   Drilbur   Ground            328  60     85      40
    ## 590 530                 Excadrill   Ground    Steel   508 110    135      60
    ## 591 531                    Audino   Normal            445 103     60      86
    ## 592 531         AudinoMega Audino   Normal    Fairy   545 103     60     126
    ## 593 532                   Timburr Fighting            305  75     80      55
    ## 594 533                   Gurdurr Fighting            405  85    105      85
    ## 595 534                Conkeldurr Fighting            505 105    140      95
    ## 596 535                   Tympole    Water            294  50     50      40
    ## 597 536                 Palpitoad    Water   Ground   384  75     65      55
    ## 598 537                Seismitoad    Water   Ground   509 105     95      75
    ## 599 538                     Throh Fighting            465 120    100      85
    ## 600 539                      Sawk Fighting            465  75    125      75
    ## 601 540                  Sewaddle      Bug    Grass   310  45     53      70
    ## 602 541                  Swadloon      Bug    Grass   380  55     63      90
    ## 603 542                  Leavanny      Bug    Grass   500  75    103      80
    ## 604 543                  Venipede      Bug   Poison   260  30     45      59
    ## 605 544                Whirlipede      Bug   Poison   360  40     55      99
    ## 606 545                 Scolipede      Bug   Poison   485  60    100      89
    ## 607 546                  Cottonee    Grass    Fairy   280  40     27      60
    ## 608 547                Whimsicott    Grass    Fairy   480  60     67      85
    ## 609 548                   Petilil    Grass            280  45     35      50
    ## 610 549                 Lilligant    Grass            480  70     60      75
    ## 611 550                  Basculin    Water            460  70     92      65
    ## 612 551                   Sandile   Ground     Dark   292  50     72      35
    ## 613 552                  Krokorok   Ground     Dark   351  60     82      45
    ## 614 553                Krookodile   Ground     Dark   519  95    117      80
    ## 615 554                  Darumaka     Fire            315  70     90      45
    ## 616 555   DarmanitanStandard Mode     Fire            480 105    140      55
    ## 617 555        DarmanitanZen Mode     Fire  Psychic   540 105     30     105
    ## 618 556                  Maractus    Grass            461  75     86      67
    ## 619 557                   Dwebble      Bug     Rock   325  50     65      85
    ## 620 558                   Crustle      Bug     Rock   475  70     95     125
    ## 621 559                   Scraggy     Dark Fighting   348  50     75      70
    ## 622 560                   Scrafty     Dark Fighting   488  65     90     115
    ## 623 561                  Sigilyph  Psychic   Flying   490  72     58      80
    ## 624 562                    Yamask    Ghost            303  38     30      85
    ## 625 563                Cofagrigus    Ghost            483  58     50     145
    ## 626 564                  Tirtouga    Water     Rock   355  54     78     103
    ## 627 565                Carracosta    Water     Rock   495  74    108     133
    ## 628 566                    Archen     Rock   Flying   401  55    112      45
    ## 629 567                  Archeops     Rock   Flying   567  75    140      65
    ## 630 568                  Trubbish   Poison            329  50     50      62
    ## 631 569                  Garbodor   Poison            474  80     95      82
    ## 632 570                     Zorua     Dark            330  40     65      40
    ## 633 571                   Zoroark     Dark            510  60    105      60
    ## 634 572                  Minccino   Normal            300  55     50      40
    ## 635 573                  Cinccino   Normal            470  75     95      60
    ## 636 574                   Gothita  Psychic            290  45     30      50
    ## 637 575                 Gothorita  Psychic            390  60     45      70
    ## 638 576                Gothitelle  Psychic            490  70     55      95
    ## 639 577                   Solosis  Psychic            290  45     30      40
    ## 640 578                   Duosion  Psychic            370  65     40      50
    ## 641 579                 Reuniclus  Psychic            490 110     65      75
    ## 642 580                  Ducklett    Water   Flying   305  62     44      50
    ## 643 581                    Swanna    Water   Flying   473  75     87      63
    ## 644 582                 Vanillite      Ice            305  36     50      50
    ## 645 583                 Vanillish      Ice            395  51     65      65
    ## 646 584                 Vanilluxe      Ice            535  71     95      85
    ## 647 585                  Deerling   Normal    Grass   335  60     60      50
    ## 648 586                  Sawsbuck   Normal    Grass   475  80    100      70
    ## 649 587                    Emolga Electric   Flying   428  55     75      60
    ## 650 588                Karrablast      Bug            315  50     75      45
    ## 651 589                Escavalier      Bug    Steel   495  70    135     105
    ## 652 590                   Foongus    Grass   Poison   294  69     55      45
    ## 653 591                 Amoonguss    Grass   Poison   464 114     85      70
    ## 654 592                  Frillish    Water    Ghost   335  55     40      50
    ## 655 593                 Jellicent    Water    Ghost   480 100     60      70
    ## 656 594                 Alomomola    Water            470 165     75      80
    ## 657 595                    Joltik      Bug Electric   319  50     47      50
    ## 658 596                Galvantula      Bug Electric   472  70     77      60
    ## 659 597                 Ferroseed    Grass    Steel   305  44     50      91
    ## 660 598                Ferrothorn    Grass    Steel   489  74     94     131
    ## 661 599                     Klink    Steel            300  40     55      70
    ## 662 600                     Klang    Steel            440  60     80      95
    ## 663 601                 Klinklang    Steel            520  60    100     115
    ## 664 602                    Tynamo Electric            275  35     55      40
    ## 665 603                 Eelektrik Electric            405  65     85      70
    ## 666 604                Eelektross Electric            515  85    115      80
    ## 667 605                    Elgyem  Psychic            335  55     55      55
    ## 668 606                  Beheeyem  Psychic            485  75     75      75
    ## 669 607                   Litwick    Ghost     Fire   275  50     30      55
    ## 670 608                   Lampent    Ghost     Fire   370  60     40      60
    ## 671 609                Chandelure    Ghost     Fire   520  60     55      90
    ## 672 610                      Axew   Dragon            320  46     87      60
    ## 673 611                   Fraxure   Dragon            410  66    117      70
    ## 674 612                   Haxorus   Dragon            540  76    147      90
    ## 675 613                   Cubchoo      Ice            305  55     70      40
    ## 676 614                   Beartic      Ice            485  95    110      80
    ## 677 615                 Cryogonal      Ice            485  70     50      30
    ## 678 616                   Shelmet      Bug            305  50     40      85
    ## 679 617                  Accelgor      Bug            495  80     70      40
    ## 680 618                  Stunfisk   Ground Electric   471 109     66      84
    ## 681 619                   Mienfoo Fighting            350  45     85      50
    ## 682 620                  Mienshao Fighting            510  65    125      60
    ## 683 621                 Druddigon   Dragon            485  77    120      90
    ## 684 622                    Golett   Ground    Ghost   303  59     74      50
    ## 685 623                    Golurk   Ground    Ghost   483  89    124      80
    ## 686 624                  Pawniard     Dark    Steel   340  45     85      70
    ## 687 625                   Bisharp     Dark    Steel   490  65    125     100
    ## 688 626                Bouffalant   Normal            490  95    110      95
    ## 689 627                   Rufflet   Normal   Flying   350  70     83      50
    ## 690 628                  Braviary   Normal   Flying   510 100    123      75
    ## 691 629                   Vullaby     Dark   Flying   370  70     55      75
    ## 692 630                 Mandibuzz     Dark   Flying   510 110     65     105
    ## 693 631                   Heatmor     Fire            484  85     97      66
    ## 694 632                    Durant      Bug    Steel   484  58    109     112
    ## 695 633                     Deino     Dark   Dragon   300  52     65      50
    ## 696 634                  Zweilous     Dark   Dragon   420  72     85      70
    ## 697 635                 Hydreigon     Dark   Dragon   600  92    105      90
    ## 698 636                  Larvesta      Bug     Fire   360  55     85      55
    ## 699 637                 Volcarona      Bug     Fire   550  85     60      65
    ## 700 638                  Cobalion    Steel Fighting   580  91     90     129
    ## 701 639                 Terrakion     Rock Fighting   580  91    129      90
    ## 702 640                  Virizion    Grass Fighting   580  91     90      72
    ## 703 641   TornadusIncarnate Forme   Flying            580  79    115      70
    ## 704 641     TornadusTherian Forme   Flying            580  79    100      80
    ## 705 642  ThundurusIncarnate Forme Electric   Flying   580  79    115      70
    ## 706 642    ThundurusTherian Forme Electric   Flying   580  79    105      70
    ## 707 643                  Reshiram   Dragon     Fire   680 100    120     100
    ## 708 644                    Zekrom   Dragon Electric   680 100    150     120
    ## 709 645   LandorusIncarnate Forme   Ground   Flying   600  89    125      90
    ## 710 645     LandorusTherian Forme   Ground   Flying   600  89    145      90
    ## 711 646                    Kyurem   Dragon      Ice   660 125    130      90
    ## 712 646        KyuremBlack Kyurem   Dragon      Ice   700 125    170     100
    ## 713 646        KyuremWhite Kyurem   Dragon      Ice   700 125    120      90
    ## 714 647      KeldeoOrdinary Forme    Water Fighting   580  91     72      90
    ## 715 647      KeldeoResolute Forme    Water Fighting   580  91     72      90
    ## 716 648        MeloettaAria Forme   Normal  Psychic   600 100     77      77
    ## 717 648   MeloettaPirouette Forme   Normal Fighting   600 100    128      90
    ## 718 649                  Genesect      Bug    Steel   600  71    120      95
    ## 719 650                   Chespin    Grass            313  56     61      65
    ## 720 651                 Quilladin    Grass            405  61     78      95
    ## 721 652                Chesnaught    Grass Fighting   530  88    107     122
    ## 722 653                  Fennekin     Fire            307  40     45      40
    ## 723 654                   Braixen     Fire            409  59     59      58
    ## 724 655                   Delphox     Fire  Psychic   534  75     69      72
    ## 725 656                   Froakie    Water            314  41     56      40
    ## 726 657                 Frogadier    Water            405  54     63      52
    ## 727 658                  Greninja    Water     Dark   530  72     95      67
    ## 728 659                  Bunnelby   Normal            237  38     36      38
    ## 729 660                 Diggersby   Normal   Ground   423  85     56      77
    ## 730 661                Fletchling   Normal   Flying   278  45     50      43
    ## 731 662               Fletchinder     Fire   Flying   382  62     73      55
    ## 732 663                Talonflame     Fire   Flying   499  78     81      71
    ## 733 664                Scatterbug      Bug            200  38     35      40
    ## 734 665                    Spewpa      Bug            213  45     22      60
    ## 735 666                  Vivillon      Bug   Flying   411  80     52      50
    ## 736 667                    Litleo     Fire   Normal   369  62     50      58
    ## 737 668                    Pyroar     Fire   Normal   507  86     68      72
    ## 738 669                 FlabÃ©bÃ©    Fairy            303  44     38      39
    ## 739 670                   Floette    Fairy            371  54     45      47
    ## 740 671                   Florges    Fairy            552  78     65      68
    ## 741 672                    Skiddo    Grass            350  66     65      48
    ## 742 673                    Gogoat    Grass            531 123    100      62
    ## 743 674                   Pancham Fighting            348  67     82      62
    ## 744 675                   Pangoro Fighting     Dark   495  95    124      78
    ## 745 676                   Furfrou   Normal            472  75     80      60
    ## 746 677                    Espurr  Psychic            355  62     48      54
    ## 747 678              MeowsticMale  Psychic            466  74     48      76
    ## 748 678            MeowsticFemale  Psychic            466  74     48      76
    ## 749 679                   Honedge    Steel    Ghost   325  45     80     100
    ## 750 680                  Doublade    Steel    Ghost   448  59    110     150
    ## 751 681      AegislashBlade Forme    Steel    Ghost   520  60    150      50
    ## 752 681     AegislashShield Forme    Steel    Ghost   520  60     50     150
    ## 753 682                  Spritzee    Fairy            341  78     52      60
    ## 754 683                Aromatisse    Fairy            462 101     72      72
    ## 755 684                   Swirlix    Fairy            341  62     48      66
    ## 756 685                  Slurpuff    Fairy            480  82     80      86
    ## 757 686                     Inkay     Dark  Psychic   288  53     54      53
    ## 758 687                   Malamar     Dark  Psychic   482  86     92      88
    ## 759 688                   Binacle     Rock    Water   306  42     52      67
    ## 760 689                Barbaracle     Rock    Water   500  72    105     115
    ## 761 690                    Skrelp   Poison    Water   320  50     60      60
    ## 762 691                  Dragalge   Poison   Dragon   494  65     75      90
    ## 763 692                 Clauncher    Water            330  50     53      62
    ## 764 693                 Clawitzer    Water            500  71     73      88
    ## 765 694                Helioptile Electric   Normal   289  44     38      33
    ## 766 695                 Heliolisk Electric   Normal   481  62     55      52
    ## 767 696                    Tyrunt     Rock   Dragon   362  58     89      77
    ## 768 697                 Tyrantrum     Rock   Dragon   521  82    121     119
    ## 769 698                    Amaura     Rock      Ice   362  77     59      50
    ## 770 699                   Aurorus     Rock      Ice   521 123     77      72
    ## 771 700                   Sylveon    Fairy            525  95     65      65
    ## 772 701                  Hawlucha Fighting   Flying   500  78     92      75
    ## 773 702                   Dedenne Electric    Fairy   431  67     58      57
    ## 774 703                   Carbink     Rock    Fairy   500  50     50     150
    ## 775 704                     Goomy   Dragon            300  45     50      35
    ## 776 705                   Sliggoo   Dragon            452  68     75      53
    ## 777 706                    Goodra   Dragon            600  90    100      70
    ## 778 707                    Klefki    Steel    Fairy   470  57     80      91
    ## 779 708                  Phantump    Ghost    Grass   309  43     70      48
    ## 780 709                 Trevenant    Ghost    Grass   474  85    110      76
    ## 781 710     PumpkabooAverage Size    Ghost    Grass   335  49     66      70
    ## 782 710       PumpkabooSmall Size    Ghost    Grass   335  44     66      70
    ## 783 710       PumpkabooLarge Size    Ghost    Grass   335  54     66      70
    ## 784 710       PumpkabooSuper Size    Ghost    Grass   335  59     66      70
    ## 785 711     GourgeistAverage Size    Ghost    Grass   494  65     90     122
    ## 786 711       GourgeistSmall Size    Ghost    Grass   494  55     85     122
    ## 787 711       GourgeistLarge Size    Ghost    Grass   494  75     95     122
    ## 788 711       GourgeistSuper Size    Ghost    Grass   494  85    100     122
    ## 789 712                  Bergmite      Ice            304  55     69      85
    ## 790 713                   Avalugg      Ice            514  95    117     184
    ## 791 714                    Noibat   Flying   Dragon   245  40     30      35
    ## 792 715                   Noivern   Flying   Dragon   535  85     70      80
    ## 793 716                   Xerneas    Fairy            680 126    131      95
    ## 794 717                   Yveltal     Dark   Flying   680 126    131      95
    ## 795 718          Zygarde50% Forme   Dragon   Ground   600 108    100     121
    ## 796 719                   Diancie     Rock    Fairy   600  50    100     150
    ## 797 719       DiancieMega Diancie     Rock    Fairy   700  50    160     110
    ## 798 720       HoopaHoopa Confined  Psychic    Ghost   600  80    110      60
    ## 799 720        HoopaHoopa Unbound  Psychic     Dark   680  80    160      60
    ## 800 721                 Volcanion     Fire    Water   600  80    110     120
    ##     Sp..Atk Sp..Def Speed Generation Legendary
    ## 1        65      65    45          1     False
    ## 2        80      80    60          1     False
    ## 3       100     100    80          1     False
    ## 4       122     120    80          1     False
    ## 5        60      50    65          1     False
    ## 6        80      65    80          1     False
    ## 7       109      85   100          1     False
    ## 8       130      85   100          1     False
    ## 9       159     115   100          1     False
    ## 10       50      64    43          1     False
    ## 11       65      80    58          1     False
    ## 12       85     105    78          1     False
    ## 13      135     115    78          1     False
    ## 14       20      20    45          1     False
    ## 15       25      25    30          1     False
    ## 16       90      80    70          1     False
    ## 17       20      20    50          1     False
    ## 18       25      25    35          1     False
    ## 19       45      80    75          1     False
    ## 20       15      80   145          1     False
    ## 21       35      35    56          1     False
    ## 22       50      50    71          1     False
    ## 23       70      70   101          1     False
    ## 24      135      80   121          1     False
    ## 25       25      35    72          1     False
    ## 26       50      70    97          1     False
    ## 27       31      31    70          1     False
    ## 28       61      61   100          1     False
    ## 29       40      54    55          1     False
    ## 30       65      79    80          1     False
    ## 31       50      50    90          1     False
    ## 32       90      80   110          1     False
    ## 33       20      30    40          1     False
    ## 34       45      55    65          1     False
    ## 35       40      40    41          1     False
    ## 36       55      55    56          1     False
    ## 37       75      85    76          1     False
    ## 38       40      40    50          1     False
    ## 39       55      55    65          1     False
    ## 40       85      75    85          1     False
    ## 41       60      65    35          1     False
    ## 42       95      90    60          1     False
    ## 43       50      65    65          1     False
    ## 44       81     100   100          1     False
    ## 45       45      25    20          1     False
    ## 46       85      50    45          1     False
    ## 47       30      40    55          1     False
    ## 48       65      75    90          1     False
    ## 49       75      65    30          1     False
    ## 50       85      75    40          1     False
    ## 51      110      90    50          1     False
    ## 52       45      55    25          1     False
    ## 53       60      80    30          1     False
    ## 54       40      55    45          1     False
    ## 55       90      75    90          1     False
    ## 56       35      45    95          1     False
    ## 57       50      70   120          1     False
    ## 58       40      40    90          1     False
    ## 59       65      65   115          1     False
    ## 60       65      50    55          1     False
    ## 61       95      80    85          1     False
    ## 62       35      45    70          1     False
    ## 63       60      70    95          1     False
    ## 64       70      50    60          1     False
    ## 65      100      80    95          1     False
    ## 66       40      40    90          1     False
    ## 67       50      50    90          1     False
    ## 68       70      90    70          1     False
    ## 69      105      55    90          1     False
    ## 70      120      70   105          1     False
    ## 71      135      95   120          1     False
    ## 72      175      95   150          1     False
    ## 73       35      35    35          1     False
    ## 74       50      60    45          1     False
    ## 75       65      85    55          1     False
    ## 76       70      30    40          1     False
    ## 77       85      45    55          1     False
    ## 78      100      70    70          1     False
    ## 79       50     100    70          1     False
    ## 80       80     120   100          1     False
    ## 81       30      30    20          1     False
    ## 82       45      45    35          1     False
    ## 83       55      65    45          1     False
    ## 84       65      65    90          1     False
    ## 85       80      80   105          1     False
    ## 86       40      40    15          1     False
    ## 87      100      80    30          1     False
    ## 88      130      80    30          1     False
    ## 89       95      55    45          1     False
    ## 90      120      70    70          1     False
    ## 91       58      62    60          1     False
    ## 92       35      35    75          1     False
    ## 93       60      60   100          1     False
    ## 94       45      70    45          1     False
    ## 95       70      95    70          1     False
    ## 96       40      50    25          1     False
    ## 97       65     100    50          1     False
    ## 98       45      25    40          1     False
    ## 99       85      45    70          1     False
    ## 100     100      35    80          1     False
    ## 101     115      55    95          1     False
    ## 102     130      75   110          1     False
    ## 103     170      95   130          1     False
    ## 104      30      45    70          1     False
    ## 105      43      90    42          1     False
    ## 106      73     115    67          1     False
    ## 107      25      25    50          1     False
    ## 108      50      50    75          1     False
    ## 109      55      55   100          1     False
    ## 110      80      80   140          1     False
    ## 111      60      45    40          1     False
    ## 112     125      65    55          1     False
    ## 113      40      50    35          1     False
    ## 114      50      80    45          1     False
    ## 115      35     110    87          1     False
    ## 116      35     110    76          1     False
    ## 117      60      75    30          1     False
    ## 118      60      45    35          1     False
    ## 119      85      70    60          1     False
    ## 120      30      30    25          1     False
    ## 121      45      45    40          1     False
    ## 122      35     105    50          1     False
    ## 123     100      40    60          1     False
    ## 124      40      80    90          1     False
    ## 125      60     100   100          1     False
    ## 126      70      25    60          1     False
    ## 127      95      45    85          1     False
    ## 128      35      50    63          1     False
    ## 129      65      80    68          1     False
    ## 130      70      55    85          1     False
    ## 131     100      85   115          1     False
    ## 132     100     120    90          1     False
    ## 133      55      80   105          1     False
    ## 134     115      95    95          1     False
    ## 135      95      85   105          1     False
    ## 136     100      85    93          1     False
    ## 137      55      70    85          1     False
    ## 138      65      90   105          1     False
    ## 139      40      70   110          1     False
    ## 140      15      20    80          1     False
    ## 141      60     100    81          1     False
    ## 142      70     130    81          1     False
    ## 143      85      95    60          1     False
    ## 144      48      48    48          1     False
    ## 145      45      65    55          1     False
    ## 146     110      95    65          1     False
    ## 147     110      95   130          1     False
    ## 148      95     110    65          1     False
    ## 149      85      75    40          1     False
    ## 150      90      55    35          1     False
    ## 151     115      70    55          1     False
    ## 152      55      45    55          1     False
    ## 153      65      70    80          1     False
    ## 154      60      75   130          1     False
    ## 155      70      95   150          1     False
    ## 156      65     110    30          1     False
    ## 157      95     125    85          1      True
    ## 158     125      90   100          1      True
    ## 159     125      85    90          1      True
    ## 160      50      50    50          1     False
    ## 161      70      70    70          1     False
    ## 162     100     100    80          1     False
    ## 163     154      90   130          1      True
    ## 164     154     100   130          1      True
    ## 165     194     120   140          1      True
    ## 166     100     100   100          1     False
    ## 167      49      65    45          2     False
    ## 168      63      80    60          2     False
    ## 169      83     100    80          2     False
    ## 170      60      50    65          2     False
    ## 171      80      65    80          2     False
    ## 172     109      85   100          2     False
    ## 173      44      48    43          2     False
    ## 174      59      63    58          2     False
    ## 175      79      83    78          2     False
    ## 176      35      45    20          2     False
    ## 177      45      55    90          2     False
    ## 178      36      56    50          2     False
    ## 179      76      96    70          2     False
    ## 180      40      80    55          2     False
    ## 181      55     110    85          2     False
    ## 182      40      40    30          2     False
    ## 183      60      60    40          2     False
    ## 184      70      80   130          2     False
    ## 185      56      56    67          2     False
    ## 186      76      76    67          2     False
    ## 187      35      35    60          2     False
    ## 188      45      55    15          2     False
    ## 189      40      20    15          2     False
    ## 190      40      65    20          2     False
    ## 191      80     105    40          2     False
    ## 192      70      45    70          2     False
    ## 193      95      70    95          2     False
    ## 194      65      45    35          2     False
    ## 195      80      60    45          2     False
    ## 196     115      90    55          2     False
    ## 197     165     110    45          2     False
    ## 198      90     100    50          2     False
    ## 199      20      50    40          2     False
    ## 200      60      80    50          2     False
    ## 201      30      65    30          2     False
    ## 202      90     100    70          2     False
    ## 203      35      55    50          2     False
    ## 204      45      65    80          2     False
    ## 205      55      95   110          2     False
    ## 206      40      55    85          2     False
    ## 207      30      30    30          2     False
    ## 208     105      85    30          2     False
    ## 209      75      45    95          2     False
    ## 210      25      25    15          2     False
    ## 211      65      65    35          2     False
    ## 212     130      95   110          2     False
    ## 213      60     130    65          2     False
    ## 214      85      42    91          2     False
    ## 215     100     110    30          2     False
    ## 216      85      85    85          2     False
    ## 217      72      48    48          2     False
    ## 218      33      58    33          2     False
    ## 219      90      65    85          2     False
    ## 220      35      35    15          2     False
    ## 221      60      60    40          2     False
    ## 222      65      65    45          2     False
    ## 223      35      65    85          2     False
    ## 224      55      65    30          2     False
    ## 225      55      95    30          2     False
    ## 226      40      40    30          2     False
    ## 227      60      60    45          2     False
    ## 228      55      55    85          2     False
    ## 229      55      80    65          2     False
    ## 230      65     100    75          2     False
    ## 231      10     230     5          2     False
    ## 232      40      95    85          2     False
    ## 233      40     105    75          2     False
    ## 234      35      75   115          2     False
    ## 235      50      50    40          2     False
    ## 236      75      75    55          2     False
    ## 237      70      40    20          2     False
    ## 238      80      80    30          2     False
    ## 239      30      30    50          2     False
    ## 240      60      60    50          2     False
    ## 241      65      85    35          2     False
    ## 242      65      35    65          2     False
    ## 243     105      75    45          2     False
    ## 244      65      45    75          2     False
    ## 245      80     140    70          2     False
    ## 246      40      70    70          2     False
    ## 247      80      50    65          2     False
    ## 248     110      80    95          2     False
    ## 249     140      90   115          2     False
    ## 250      95      95    85          2     False
    ## 251      40      40    40          2     False
    ## 252      60      60    50          2     False
    ## 253     105      95    60          2     False
    ## 254      85      65    85          2     False
    ## 255      20      45    75          2     False
    ## 256      35      35    35          2     False
    ## 257      35     110    70          2     False
    ## 258      85      65    65          2     False
    ## 259      65      55    95          2     False
    ## 260      70      55    83          2     False
    ## 261      40      70   100          2     False
    ## 262      75     135    55          2     False
    ## 263     115     100   115          2      True
    ## 264      90      75   100          2      True
    ## 265      90     115    85          2      True
    ## 266      45      50    41          2     False
    ## 267      65      70    51          2     False
    ## 268      95     100    61          2     False
    ## 269      95     120    71          2     False
    ## 270      90     154   110          2      True
    ## 271     110     154    90          2      True
    ## 272     100     100   100          2     False
    ## 273      65      55    70          3     False
    ## 274      85      65    95          3     False
    ## 275     105      85   120          3     False
    ## 276     145      85   145          3     False
    ## 277      70      50    45          3     False
    ## 278      85      60    55          3     False
    ## 279     110      70    80          3     False
    ## 280     130      80   100          3     False
    ## 281      50      50    40          3     False
    ## 282      60      70    50          3     False
    ## 283      85      90    60          3     False
    ## 284      95     110    70          3     False
    ## 285      30      30    35          3     False
    ## 286      60      60    70          3     False
    ## 287      30      41    60          3     False
    ## 288      50      61   100          3     False
    ## 289      20      30    20          3     False
    ## 290      25      25    15          3     False
    ## 291     100      50    65          3     False
    ## 292      25      25    15          3     False
    ## 293      50      90    65          3     False
    ## 294      40      50    30          3     False
    ## 295      60      70    50          3     False
    ## 296      90     100    70          3     False
    ## 297      30      30    30          3     False
    ## 298      60      40    60          3     False
    ## 299      90      60    80          3     False
    ## 300      30      30    85          3     False
    ## 301      50      50   125          3     False
    ## 302      55      30    85          3     False
    ## 303      85      70    65          3     False
    ## 304      45      35    40          3     False
    ## 305      65      55    50          3     False
    ## 306     125     115    80          3     False
    ## 307     165     135   100          3     False
    ## 308      50      52    65          3     False
    ## 309      80      82    60          3     False
    ## 310      40      60    35          3     False
    ## 311      60      60    70          3     False
    ## 312      35      35    30          3     False
    ## 313      55      55    90          3     False
    ## 314      95      65   100          3     False
    ## 315      30      30    40          3     False
    ## 316      50      50   160          3     False
    ## 317      30      30    40          3     False
    ## 318      51      23    28          3     False
    ## 319      71      43    48          3     False
    ## 320      91      73    68          3     False
    ## 321      20      30    25          3     False
    ## 322      40      60    50          3     False
    ## 323      20      40    20          3     False
    ## 324      45      90    30          3     False
    ## 325      35      35    50          3     False
    ## 326      55      55    70          3     False
    ## 327      65      65    50          3     False
    ## 328      85     115    20          3     False
    ## 329      55      55    50          3     False
    ## 330      55      95    50          3     False
    ## 331      40      40    30          3     False
    ## 332      50      50    40          3     False
    ## 333      60      60    50          3     False
    ## 334      60      80    50          3     False
    ## 335      40      55    60          3     False
    ## 336      60      75    80          3     False
    ## 337      80      85   100          3     False
    ## 338      65      40    65          3     False
    ## 339     105      60   105          3     False
    ## 340     135      80   135          3     False
    ## 341      85      75    95          3     False
    ## 342      75      85    95          3     False
    ## 343      47      75    85          3     False
    ## 344      73      75    85          3     False
    ## 345     100      80    65          3     False
    ## 346      43      53    40          3     False
    ## 347      73      83    55          3     False
    ## 348      65      20    65          3     False
    ## 349      95      40    95          3     False
    ## 350     110      65   105          3     False
    ## 351      70      35    60          3     False
    ## 352      90      45    60          3     False
    ## 353      65      45    35          3     False
    ## 354     105      75    40          3     False
    ## 355     145     105    20          3     False
    ## 356      85      70    20          3     False
    ## 357      70      80    60          3     False
    ## 358      90     110    80          3     False
    ## 359      60      60    60          3     False
    ## 360      45      45    10          3     False
    ## 361      50      50    70          3     False
    ## 362      80      80   100          3     False
    ## 363      85      40    35          3     False
    ## 364     115      60    55          3     False
    ## 365      40      75    50          3     False
    ## 366      70     105    80          3     False
    ## 367     110     105    80          3     False
    ## 368      60      60    90          3     False
    ## 369     100      60    65          3     False
    ## 370      95      85    70          3     False
    ## 371      55      65    70          3     False
    ## 372      46      41    60          3     False
    ## 373      76      71    60          3     False
    ## 374      50      35    35          3     False
    ## 375      90      55    55          3     False
    ## 376      40      70    55          3     False
    ## 377      70     120    75          3     False
    ## 378      61      87    23          3     False
    ## 379      81     107    43          3     False
    ## 380      40      50    75          3     False
    ## 381      70      80    45          3     False
    ## 382      10      55    80          3     False
    ## 383     100     125    81          3     False
    ## 384      70      70    70          3     False
    ## 385      60     120    40          3     False
    ## 386      63      33    45          3     False
    ## 387      83      63    65          3     False
    ## 388      93      83    75          3     False
    ## 389      30      90    25          3     False
    ## 390      60     130    25          3     False
    ## 391      72      87    51          3     False
    ## 392      95      80    65          3     False
    ## 393      75      60    75          3     False
    ## 394     115      60   115          3     False
    ## 395      23      48    23          3     False
    ## 396      50      50    50          3     False
    ## 397      80      80    80          3     False
    ## 398     120      80   100          3     False
    ## 399      55      50    25          3     False
    ## 400      75      70    45          3     False
    ## 401      95      90    65          3     False
    ## 402      74      55    32          3     False
    ## 403      94      75    52          3     False
    ## 404     114      75    52          3     False
    ## 405      45      65    55          3     False
    ## 406      40      65    97          3     False
    ## 407      40      30    50          3     False
    ## 408      60      50    50          3     False
    ## 409     110      80   100          3     False
    ## 410     120      90   120          3     False
    ## 411      35      60    30          3     False
    ## 412      55      80    50          3     False
    ## 413      95      90    70          3     False
    ## 414     105     110   110          3     False
    ## 415      50     100    50          3      True
    ## 416     100     200    50          3      True
    ## 417      75     150    50          3      True
    ## 418     110     130   110          3      True
    ## 419     140     150   110          3      True
    ## 420     130     110   110          3      True
    ## 421     160     120   110          3      True
    ## 422     150     140    90          3      True
    ## 423     180     160    90          3      True
    ## 424     100      90    90          3      True
    ## 425     150      90    90          3      True
    ## 426     150      90    95          3      True
    ## 427     180     100   115          3      True
    ## 428     100     100   100          3      True
    ## 429     150      50   150          3      True
    ## 430     180      20   150          3      True
    ## 431      70     160    90          3      True
    ## 432      95      90   180          3      True
    ## 433      45      55    31          4     False
    ## 434      55      65    36          4     False
    ## 435      75      85    56          4     False
    ## 436      58      44    61          4     False
    ## 437      78      52    81          4     False
    ## 438     104      71   108          4     False
    ## 439      61      56    40          4     False
    ## 440      81      76    50          4     False
    ## 441     111     101    60          4     False
    ## 442      30      30    60          4     False
    ## 443      40      40    80          4     False
    ## 444      50      60   100          4     False
    ## 445      35      40    31          4     False
    ## 446      55      60    71          4     False
    ## 447      25      41    25          4     False
    ## 448      55      51    65          4     False
    ## 449      40      34    45          4     False
    ## 450      60      49    60          4     False
    ## 451      95      79    70          4     False
    ## 452      50      70    55          4     False
    ## 453     125     105    90          4     False
    ## 454      30      30    58          4     False
    ## 455      65      50    58          4     False
    ## 456      42      88    30          4     False
    ## 457      47     138    30          4     False
    ## 458      29      45    36          4     False
    ## 459      79     105    36          4     False
    ## 460      59      85    36          4     False
    ## 461      69      95    36          4     False
    ## 462      94      50    66          4     False
    ## 463      30      42    70          4     False
    ## 464      80     102    40          4     False
    ## 465      45      90    95          4     False
    ## 466      60      30    85          4     False
    ## 467      85      50   115          4     False
    ## 468      62      53    35          4     False
    ## 469      87      78    85          4     False
    ## 470      57      62    34          4     False
    ## 471      92      82    39          4     False
    ## 472      60      66   115          4     False
    ## 473      60      44    70          4     False
    ## 474      90      54    80          4     False
    ## 475      44      56    85          4     False
    ## 476      54      96   105          4     False
    ## 477      54      96   135          4     False
    ## 478     105     105   105          4     False
    ## 479     105      52    71          4     False
    ## 480      42      37    85          4     False
    ## 481      64      59   112          4     False
    ## 482      65      50    45          4     False
    ## 483      41      41    74          4     False
    ## 484      71      61    84          4     False
    ## 485      24      86    23          4     False
    ## 486      79     116    33          4     False
    ## 487      10      45    10          4     False
    ## 488      70      90    60          4     False
    ## 489      15      65    30          4     False
    ## 490      92      42    91          4     False
    ## 491      92     108    35          4     False
    ## 492      40      45    42          4     False
    ## 493      50      55    82          4     False
    ## 494      80      85   102          4     False
    ## 495     120      95    92          4     False
    ## 496      40      85     5          4     False
    ## 497      35      40    60          4     False
    ## 498     115      70    90          4     False
    ## 499     140      70   112          4     False
    ## 500      38      42    32          4     False
    ## 501      68      72    47          4     False
    ## 502      30      55    65          4     False
    ## 503      60      75    95          4     False
    ## 504      61      40    50          4     False
    ## 505      86      65    85          4     False
    ## 506      90      72    46          4     False
    ## 507      49      61    66          4     False
    ## 508      69      86    91          4     False
    ## 509      60     120    50          4     False
    ## 510      62      60    40          4     False
    ## 511      92      85    60          4     False
    ## 512     132     105    30          4     False
    ## 513      45      85   125          4     False
    ## 514     130      90    60          4     False
    ## 515      80      95    50          4     False
    ## 516      55      55    40          4     False
    ## 517     110      50    50          4     False
    ## 518      95      85    95          4     False
    ## 519     125      95    83          4     False
    ## 520     120     115    80          4     False
    ## 521     116      56    95          4     False
    ## 522      60      65    95          4     False
    ## 523     130      95    65          4     False
    ## 524      45      75    95          4     False
    ## 525      70      60    80          4     False
    ## 526     135      75    90          4     False
    ## 527      65     115    80          4     False
    ## 528      65     115   110          4     False
    ## 529      75     150    40          4     False
    ## 530      65     135    45          4     False
    ## 531      80      70   110          4     False
    ## 532      95      77    91          4     False
    ## 533     105     107    86          4     False
    ## 534     105     107    86          4     False
    ## 535     105     107    86          4     False
    ## 536     105     107    86          4     False
    ## 537     105     107    86          4     False
    ## 538      75     130    95          4      True
    ## 539     105     105    80          4      True
    ## 540     125      70   115          4      True
    ## 541     150     100    90          4      True
    ## 542     150     120   100          4      True
    ## 543     130     106    77          4      True
    ## 544      80     110   100          4      True
    ## 545     100     120    90          4      True
    ## 546     120     100    90          4      True
    ## 547      75     130    85          4     False
    ## 548      80      80    80          4     False
    ## 549     100     100   100          4     False
    ## 550     135      90   125          4      True
    ## 551     100     100   100          4      True
    ## 552     120      75   127          4      True
    ## 553     120     120   120          4      True
    ## 554     100     100   100          5      True
    ## 555      45      55    63          5     False
    ## 556      60      75    83          5     False
    ## 557      75      95   113          5     False
    ## 558      45      45    45          5     False
    ## 559      70      55    55          5     False
    ## 560     100      65    65          5     False
    ## 561      63      45    45          5     False
    ## 562      83      60    60          5     False
    ## 563     108      70    70          5     False
    ## 564      35      39    42          5     False
    ## 565      60      69    77          5     False
    ## 566      25      45    55          5     False
    ## 567      35      65    60          5     False
    ## 568      45      90    80          5     False
    ## 569      50      37    66          5     False
    ## 570      88      50   106          5     False
    ## 571      53      48    64          5     False
    ## 572      98      63   101          5     False
    ## 573      53      48    64          5     False
    ## 574      98      63   101          5     False
    ## 575      53      48    64          5     False
    ## 576      98      63   101          5     False
    ## 577      67      55    24          5     False
    ## 578     107      95    29          5     False
    ## 579      36      30    43          5     False
    ## 580      50      42    65          5     False
    ## 581      65      55    93          5     False
    ## 582      50      32    76          5     False
    ## 583      80      63   116          5     False
    ## 584      25      25    15          5     False
    ## 585      50      40    20          5     False
    ## 586      60      80    25          5     False
    ## 587      55      43    72          5     False
    ## 588      77      55   114          5     False
    ## 589      30      45    68          5     False
    ## 590      50      65    88          5     False
    ## 591      60      86    50          5     False
    ## 592      80     126    50          5     False
    ## 593      25      35    35          5     False
    ## 594      40      50    40          5     False
    ## 595      55      65    45          5     False
    ## 596      50      40    64          5     False
    ## 597      65      55    69          5     False
    ## 598      85      75    74          5     False
    ## 599      30      85    45          5     False
    ## 600      30      75    85          5     False
    ## 601      40      60    42          5     False
    ## 602      50      80    42          5     False
    ## 603      70      80    92          5     False
    ## 604      30      39    57          5     False
    ## 605      40      79    47          5     False
    ## 606      55      69   112          5     False
    ## 607      37      50    66          5     False
    ## 608      77      75   116          5     False
    ## 609      70      50    30          5     False
    ## 610     110      75    90          5     False
    ## 611      80      55    98          5     False
    ## 612      35      35    65          5     False
    ## 613      45      45    74          5     False
    ## 614      65      70    92          5     False
    ## 615      15      45    50          5     False
    ## 616      30      55    95          5     False
    ## 617     140     105    55          5     False
    ## 618     106      67    60          5     False
    ## 619      35      35    55          5     False
    ## 620      65      75    45          5     False
    ## 621      35      70    48          5     False
    ## 622      45     115    58          5     False
    ## 623     103      80    97          5     False
    ## 624      55      65    30          5     False
    ## 625      95     105    30          5     False
    ## 626      53      45    22          5     False
    ## 627      83      65    32          5     False
    ## 628      74      45    70          5     False
    ## 629     112      65   110          5     False
    ## 630      40      62    65          5     False
    ## 631      60      82    75          5     False
    ## 632      80      40    65          5     False
    ## 633     120      60   105          5     False
    ## 634      40      40    75          5     False
    ## 635      65      60   115          5     False
    ## 636      55      65    45          5     False
    ## 637      75      85    55          5     False
    ## 638      95     110    65          5     False
    ## 639     105      50    20          5     False
    ## 640     125      60    30          5     False
    ## 641     125      85    30          5     False
    ## 642      44      50    55          5     False
    ## 643      87      63    98          5     False
    ## 644      65      60    44          5     False
    ## 645      80      75    59          5     False
    ## 646     110      95    79          5     False
    ## 647      40      50    75          5     False
    ## 648      60      70    95          5     False
    ## 649      75      60   103          5     False
    ## 650      40      45    60          5     False
    ## 651      60     105    20          5     False
    ## 652      55      55    15          5     False
    ## 653      85      80    30          5     False
    ## 654      65      85    40          5     False
    ## 655      85     105    60          5     False
    ## 656      40      45    65          5     False
    ## 657      57      50    65          5     False
    ## 658      97      60   108          5     False
    ## 659      24      86    10          5     False
    ## 660      54     116    20          5     False
    ## 661      45      60    30          5     False
    ## 662      70      85    50          5     False
    ## 663      70      85    90          5     False
    ## 664      45      40    60          5     False
    ## 665      75      70    40          5     False
    ## 666     105      80    50          5     False
    ## 667      85      55    30          5     False
    ## 668     125      95    40          5     False
    ## 669      65      55    20          5     False
    ## 670      95      60    55          5     False
    ## 671     145      90    80          5     False
    ## 672      30      40    57          5     False
    ## 673      40      50    67          5     False
    ## 674      60      70    97          5     False
    ## 675      60      40    40          5     False
    ## 676      70      80    50          5     False
    ## 677      95     135   105          5     False
    ## 678      40      65    25          5     False
    ## 679     100      60   145          5     False
    ## 680      81      99    32          5     False
    ## 681      55      50    65          5     False
    ## 682      95      60   105          5     False
    ## 683      60      90    48          5     False
    ## 684      35      50    35          5     False
    ## 685      55      80    55          5     False
    ## 686      40      40    60          5     False
    ## 687      60      70    70          5     False
    ## 688      40      95    55          5     False
    ## 689      37      50    60          5     False
    ## 690      57      75    80          5     False
    ## 691      45      65    60          5     False
    ## 692      55      95    80          5     False
    ## 693     105      66    65          5     False
    ## 694      48      48   109          5     False
    ## 695      45      50    38          5     False
    ## 696      65      70    58          5     False
    ## 697     125      90    98          5     False
    ## 698      50      55    60          5     False
    ## 699     135     105   100          5     False
    ## 700      90      72   108          5      True
    ## 701      72      90   108          5      True
    ## 702      90     129   108          5      True
    ## 703     125      80   111          5      True
    ## 704     110      90   121          5      True
    ## 705     125      80   111          5      True
    ## 706     145      80   101          5      True
    ## 707     150     120    90          5      True
    ## 708     120     100    90          5      True
    ## 709     115      80   101          5      True
    ## 710     105      80    91          5      True
    ## 711     130      90    95          5      True
    ## 712     120      90    95          5      True
    ## 713     170     100    95          5      True
    ## 714     129      90   108          5     False
    ## 715     129      90   108          5     False
    ## 716     128     128    90          5     False
    ## 717      77      77   128          5     False
    ## 718     120      95    99          5     False
    ## 719      48      45    38          6     False
    ## 720      56      58    57          6     False
    ## 721      74      75    64          6     False
    ## 722      62      60    60          6     False
    ## 723      90      70    73          6     False
    ## 724     114     100   104          6     False
    ## 725      62      44    71          6     False
    ## 726      83      56    97          6     False
    ## 727     103      71   122          6     False
    ## 728      32      36    57          6     False
    ## 729      50      77    78          6     False
    ## 730      40      38    62          6     False
    ## 731      56      52    84          6     False
    ## 732      74      69   126          6     False
    ## 733      27      25    35          6     False
    ## 734      27      30    29          6     False
    ## 735      90      50    89          6     False
    ## 736      73      54    72          6     False
    ## 737     109      66   106          6     False
    ## 738      61      79    42          6     False
    ## 739      75      98    52          6     False
    ## 740     112     154    75          6     False
    ## 741      62      57    52          6     False
    ## 742      97      81    68          6     False
    ## 743      46      48    43          6     False
    ## 744      69      71    58          6     False
    ## 745      65      90   102          6     False
    ## 746      63      60    68          6     False
    ## 747      83      81   104          6     False
    ## 748      83      81   104          6     False
    ## 749      35      37    28          6     False
    ## 750      45      49    35          6     False
    ## 751     150      50    60          6     False
    ## 752      50     150    60          6     False
    ## 753      63      65    23          6     False
    ## 754      99      89    29          6     False
    ## 755      59      57    49          6     False
    ## 756      85      75    72          6     False
    ## 757      37      46    45          6     False
    ## 758      68      75    73          6     False
    ## 759      39      56    50          6     False
    ## 760      54      86    68          6     False
    ## 761      60      60    30          6     False
    ## 762      97     123    44          6     False
    ## 763      58      63    44          6     False
    ## 764     120      89    59          6     False
    ## 765      61      43    70          6     False
    ## 766     109      94   109          6     False
    ## 767      45      45    48          6     False
    ## 768      69      59    71          6     False
    ## 769      67      63    46          6     False
    ## 770      99      92    58          6     False
    ## 771     110     130    60          6     False
    ## 772      74      63   118          6     False
    ## 773      81      67   101          6     False
    ## 774      50     150    50          6     False
    ## 775      55      75    40          6     False
    ## 776      83     113    60          6     False
    ## 777     110     150    80          6     False
    ## 778      80      87    75          6     False
    ## 779      50      60    38          6     False
    ## 780      65      82    56          6     False
    ## 781      44      55    51          6     False
    ## 782      44      55    56          6     False
    ## 783      44      55    46          6     False
    ## 784      44      55    41          6     False
    ## 785      58      75    84          6     False
    ## 786      58      75    99          6     False
    ## 787      58      75    69          6     False
    ## 788      58      75    54          6     False
    ## 789      32      35    28          6     False
    ## 790      44      46    28          6     False
    ## 791      45      40    55          6     False
    ## 792      97      80   123          6     False
    ## 793     131      98    99          6      True
    ## 794     131      98    99          6      True
    ## 795      81      95    95          6      True
    ## 796     100     150    50          6      True
    ## 797     160     110   110          6      True
    ## 798     150     130    70          6      True
    ## 799     170     130    80          6      True
    ## 800     130      90    70          6      True

``` r
#pk123 = filter(pk, pk$Generation %in% c(1, 2, 3))
#pk123
attach(pk)
Speed= boxplot(pk$Speed, horizontal = TRUE)
```

![](pokemon_files/figure-gfm/code-1.png)<!-- -->

``` r
stats_Speed = boxplot.stats(pk$Speed)
Speed
```

    ## $stats
    ##      [,1]
    ## [1,]    5
    ## [2,]   45
    ## [3,]   65
    ## [4,]   90
    ## [5,]  150
    ## attr(,"class")
    ##         1 
    ## "integer" 
    ## 
    ## $n
    ## [1] 800
    ## 
    ## $conf
    ##          [,1]
    ## [1,] 62.48624
    ## [2,] 67.51376
    ## 
    ## $out
    ## [1] 160 180
    ## 
    ## $group
    ## [1] 1 1
    ## 
    ## $names
    ## [1] "1"

``` r
stats_Speed
```

    ## $stats
    ## [1]   5  45  65  90 150
    ## 
    ## $n
    ## [1] 800
    ## 
    ## $conf
    ## [1] 62.48624 67.51376
    ## 
    ## $out
    ## [1] 160 180

``` r
pk1 <- Speed[pk$Speed < 100]
length(Speed) - length(pk1)
```

    ## [1] -657

``` r
#boxplot(pk1, horizontal = TRUE)
Speed_out <- filter(pk, pk$Attack > 100)
Speed_out
```

    ##      X.                      Name   Type.1   Type.2 Total  HP Attack Defense
    ## 1     6 CharizardMega Charizard X     Fire   Dragon   634  78    130     111
    ## 2     6 CharizardMega Charizard Y     Fire   Flying   634  78    104      78
    ## 3     9   BlastoiseMega Blastoise    Water            630  79    103     120
    ## 4    15     BeedrillMega Beedrill      Bug   Poison   495  65    150      40
    ## 5    34                  Nidoking   Poison   Ground   505  81    102      77
    ## 6    57                  Primeape Fighting            455  65    105      60
    ## 7    59                  Arcanine     Fire            555  90    110      80
    ## 8    68                   Machamp Fighting            505  90    130      80
    ## 9    71                Victreebel    Grass   Poison   490  80    105      65
    ## 10   76                     Golem     Rock   Ground   495  80    120     130
    ## 11   85                    Dodrio   Normal   Flying   460  60    110      70
    ## 12   89                       Muk   Poison            500 105    105      75
    ## 13   98                    Krabby    Water            325  30    105      90
    ## 14   99                   Kingler    Water            475  55    130     115
    ## 15  106                 Hitmonlee Fighting            455  50    120      53
    ## 16  107                Hitmonchan Fighting            455  50    105      79
    ## 17  112                    Rhydon   Ground     Rock   485 105    130     120
    ## 18  115 KangaskhanMega Kangaskhan   Normal            590 105    125     100
    ## 19  123                   Scyther      Bug   Flying   500  70    110      80
    ## 20  127                    Pinsir      Bug            500  65    125     100
    ## 21  127         PinsirMega Pinsir      Bug   Flying   600  65    155     120
    ## 22  130                  Gyarados    Water   Flying   540  95    125      79
    ## 23  130     GyaradosMega Gyarados    Water     Dark   640  95    155     109
    ## 24  136                   Flareon     Fire            525  65    130      60
    ## 25  141                  Kabutops     Rock    Water   495  60    115     105
    ## 26  142                Aerodactyl     Rock   Flying   515  80    105      65
    ## 27  142 AerodactylMega Aerodactyl     Rock   Flying   615  80    135      85
    ## 28  143                   Snorlax   Normal            540 160    110      65
    ## 29  149                 Dragonite   Dragon   Flying   600  91    134      95
    ## 30  150                    Mewtwo  Psychic            680 106    110      90
    ## 31  150       MewtwoMega Mewtwo X  Psychic Fighting   780 106    190     100
    ## 32  150       MewtwoMega Mewtwo Y  Psychic            780 106    150      70
    ## 33  160                Feraligatr    Water            530  85    105     100
    ## 34  208       SteelixMega Steelix    Steel   Ground   610  75    125     230
    ## 35  210                  Granbull    Fairy            450  90    120      75
    ## 36  212                    Scizor      Bug    Steel   500  70    130     100
    ## 37  212         ScizorMega Scizor      Bug    Steel   600  70    150     140
    ## 38  214                 Heracross      Bug Fighting   500  80    125      75
    ## 39  214   HeracrossMega Heracross      Bug Fighting   600  80    185     115
    ## 40  217                  Ursaring   Normal            500  90    130      75
    ## 41  224                 Octillery    Water            480  75    105      75
    ## 42  232                   Donphan   Ground            500  90    120     120
    ## 43  244                     Entei     Fire            580 115    115      85
    ## 44  248                 Tyranitar     Rock     Dark   600 100    134     110
    ## 45  248   TyranitarMega Tyranitar     Rock     Dark   700 100    164     150
    ## 46  250                     Ho-oh     Fire   Flying   680 106    130      90
    ## 47  254     SceptileMega Sceptile    Grass   Dragon   630  70    110      75
    ## 48  257                  Blaziken     Fire Fighting   530  80    120      70
    ## 49  257     BlazikenMega Blaziken     Fire Fighting   630  80    160      80
    ## 50  260                  Swampert    Water   Ground   535 100    110      90
    ## 51  260     SwampertMega Swampert    Water   Ground   635 100    150     110
    ## 52  286                   Breloom    Grass Fighting   460  60    130      80
    ## 53  289                   Slaking   Normal            670 150    160     100
    ## 54  297                  Hariyama Fighting            474 144    120      60
    ## 55  303         MawileMega Mawile    Steel    Fairy   480  50    105     125
    ## 56  306                    Aggron    Steel     Rock   530  70    110     180
    ## 57  306         AggronMega Aggron    Steel            630  70    140     230
    ## 58  319                  Sharpedo    Water     Dark   460  70    120      40
    ## 59  319     SharpedoMega Sharpedo    Water     Dark   560  70    140      70
    ## 60  323     CameruptMega Camerupt     Fire   Ground   560  70    120     100
    ## 61  332                  Cacturne    Grass     Dark   475  70    115      60
    ## 62  334       AltariaMega Altaria   Dragon    Fairy   590  75    110     110
    ## 63  335                  Zangoose   Normal            458  73    115      60
    ## 64  342                 Crawdaunt    Water     Dark   468  63    120      85
    ## 65  348                   Armaldo     Rock      Bug   495  75    125     100
    ## 66  354                   Banette    Ghost            455  64    115      65
    ## 67  354       BanetteMega Banette    Ghost            555  64    165      75
    ## 68  359                     Absol     Dark            465  65    130      60
    ## 69  359           AbsolMega Absol     Dark            565  65    150      60
    ## 70  362         GlalieMega Glalie      Ice            580  80    120      80
    ## 71  367                   Huntail    Water            485  55    104     105
    ## 72  373                 Salamence   Dragon   Flying   600  95    135      80
    ## 73  373   SalamenceMega Salamence   Dragon   Flying   700  95    145     130
    ## 74  376                 Metagross    Steel  Psychic   600  80    135     130
    ## 75  376   MetagrossMega Metagross    Steel  Psychic   700  80    145     150
    ## 76  381         LatiosMega Latios   Dragon  Psychic   700  80    130     100
    ## 77  382       KyogrePrimal Kyogre    Water            770 100    150      90
    ## 78  383                   Groudon   Ground            670 100    150     140
    ## 79  383     GroudonPrimal Groudon   Ground     Fire   770 100    180     160
    ## 80  384                  Rayquaza   Dragon   Flying   680 105    150      90
    ## 81  384     RayquazaMega Rayquaza   Dragon   Flying   780 105    180     100
    ## 82  386        DeoxysNormal Forme  Psychic            600  50    150      50
    ## 83  386        DeoxysAttack Forme  Psychic            600  50    180      20
    ## 84  389                  Torterra    Grass   Ground   525  95    109     105
    ## 85  392                 Infernape     Fire Fighting   534  76    104      71
    ## 86  398                 Staraptor   Normal   Flying   485  85    120      70
    ## 87  405                    Luxray Electric            523  80    120      79
    ## 88  408                  Cranidos     Rock            350  67    125      40
    ## 89  409                 Rampardos     Rock            495  97    165      60
    ## 90  419                  Floatzel    Water            495  85    105      55
    ## 91  428       LopunnyMega Lopunny   Normal Fighting   580  65    136      94
    ## 92  430                 Honchkrow     Dark   Flying   505 100    125      52
    ## 93  445                  Garchomp   Dragon   Ground   600 108    130      95
    ## 94  445     GarchompMega Garchomp   Dragon   Ground   700 108    170     115
    ## 95  448                   Lucario Fighting    Steel   525  70    110      70
    ## 96  448       LucarioMega Lucario Fighting    Steel   625  70    145      88
    ## 97  450                 Hippowdon   Ground            525 108    112     118
    ## 98  454                 Toxicroak   Poison Fighting   490  83    106      65
    ## 99  460   AbomasnowMega Abomasnow    Grass      Ice   594  90    132     105
    ## 100 461                   Weavile     Dark      Ice   510  70    120      65
    ## 101 464                 Rhyperior   Ground     Rock   535 115    140     130
    ## 102 466                Electivire Electric            540  75    123      67
    ## 103 470                   Leafeon    Grass            525  65    110     130
    ## 104 473                 Mamoswine      Ice   Ground   530 110    130      80
    ## 105 475                   Gallade  Psychic Fighting   518  68    125      65
    ## 106 475       GalladeMega Gallade  Psychic Fighting   618  68    165      95
    ## 107 481                   Mesprit  Psychic            580  80    105     105
    ## 108 482                     Azelf  Psychic            580  75    125      70
    ## 109 483                    Dialga    Steel   Dragon   680 100    120     120
    ## 110 484                    Palkia    Water   Dragon   680  90    120     100
    ## 111 486                 Regigigas   Normal            670 110    160     110
    ## 112 487      GiratinaOrigin Forme    Ghost   Dragon   680 150    120     100
    ## 113 492          ShayminSky Forme    Grass   Flying   600 100    103      75
    ## 114 493                    Arceus   Normal            720 120    120     120
    ## 115 500                    Emboar     Fire Fighting   528 110    123      65
    ## 116 508                 Stoutland   Normal            500  85    110      90
    ## 117 521                  Unfezant   Normal   Flying   488  80    115      80
    ## 118 525                   Boldore     Rock            390  70    105     105
    ## 119 526                  Gigalith     Rock            515  85    135     130
    ## 120 530                 Excadrill   Ground    Steel   508 110    135      60
    ## 121 533                   Gurdurr Fighting            405  85    105      85
    ## 122 534                Conkeldurr Fighting            505 105    140      95
    ## 123 539                      Sawk Fighting            465  75    125      75
    ## 124 542                  Leavanny      Bug    Grass   500  75    103      80
    ## 125 553                Krookodile   Ground     Dark   519  95    117      80
    ## 126 555   DarmanitanStandard Mode     Fire            480 105    140      55
    ## 127 565                Carracosta    Water     Rock   495  74    108     133
    ## 128 566                    Archen     Rock   Flying   401  55    112      45
    ## 129 567                  Archeops     Rock   Flying   567  75    140      65
    ## 130 571                   Zoroark     Dark            510  60    105      60
    ## 131 589                Escavalier      Bug    Steel   495  70    135     105
    ## 132 604                Eelektross Electric            515  85    115      80
    ## 133 611                   Fraxure   Dragon            410  66    117      70
    ## 134 612                   Haxorus   Dragon            540  76    147      90
    ## 135 614                   Beartic      Ice            485  95    110      80
    ## 136 620                  Mienshao Fighting            510  65    125      60
    ## 137 621                 Druddigon   Dragon            485  77    120      90
    ## 138 623                    Golurk   Ground    Ghost   483  89    124      80
    ## 139 625                   Bisharp     Dark    Steel   490  65    125     100
    ## 140 626                Bouffalant   Normal            490  95    110      95
    ## 141 628                  Braviary   Normal   Flying   510 100    123      75
    ## 142 632                    Durant      Bug    Steel   484  58    109     112
    ## 143 635                 Hydreigon     Dark   Dragon   600  92    105      90
    ## 144 639                 Terrakion     Rock Fighting   580  91    129      90
    ## 145 641   TornadusIncarnate Forme   Flying            580  79    115      70
    ## 146 642  ThundurusIncarnate Forme Electric   Flying   580  79    115      70
    ## 147 642    ThundurusTherian Forme Electric   Flying   580  79    105      70
    ## 148 643                  Reshiram   Dragon     Fire   680 100    120     100
    ## 149 644                    Zekrom   Dragon Electric   680 100    150     120
    ## 150 645   LandorusIncarnate Forme   Ground   Flying   600  89    125      90
    ## 151 645     LandorusTherian Forme   Ground   Flying   600  89    145      90
    ## 152 646                    Kyurem   Dragon      Ice   660 125    130      90
    ## 153 646        KyuremBlack Kyurem   Dragon      Ice   700 125    170     100
    ## 154 646        KyuremWhite Kyurem   Dragon      Ice   700 125    120      90
    ## 155 648   MeloettaPirouette Forme   Normal Fighting   600 100    128      90
    ## 156 649                  Genesect      Bug    Steel   600  71    120      95
    ## 157 652                Chesnaught    Grass Fighting   530  88    107     122
    ## 158 675                   Pangoro Fighting     Dark   495  95    124      78
    ## 159 680                  Doublade    Steel    Ghost   448  59    110     150
    ## 160 681      AegislashBlade Forme    Steel    Ghost   520  60    150      50
    ## 161 689                Barbaracle     Rock    Water   500  72    105     115
    ## 162 697                 Tyrantrum     Rock   Dragon   521  82    121     119
    ## 163 709                 Trevenant    Ghost    Grass   474  85    110      76
    ## 164 713                   Avalugg      Ice            514  95    117     184
    ## 165 716                   Xerneas    Fairy            680 126    131      95
    ## 166 717                   Yveltal     Dark   Flying   680 126    131      95
    ## 167 719       DiancieMega Diancie     Rock    Fairy   700  50    160     110
    ## 168 720       HoopaHoopa Confined  Psychic    Ghost   600  80    110      60
    ## 169 720        HoopaHoopa Unbound  Psychic     Dark   680  80    160      60
    ## 170 721                 Volcanion     Fire    Water   600  80    110     120
    ##     Sp..Atk Sp..Def Speed Generation Legendary
    ## 1       130      85   100          1     False
    ## 2       159     115   100          1     False
    ## 3       135     115    78          1     False
    ## 4        15      80   145          1     False
    ## 5        85      75    85          1     False
    ## 6        60      70    95          1     False
    ## 7       100      80    95          1     False
    ## 8        65      85    55          1     False
    ## 9       100      70    70          1     False
    ## 10       55      65    45          1     False
    ## 11       60      60   100          1     False
    ## 12       65     100    50          1     False
    ## 13       25      25    50          1     False
    ## 14       50      50    75          1     False
    ## 15       35     110    87          1     False
    ## 16       35     110    76          1     False
    ## 17       45      45    40          1     False
    ## 18       60     100   100          1     False
    ## 19       55      80   105          1     False
    ## 20       55      70    85          1     False
    ## 21       65      90   105          1     False
    ## 22       60     100    81          1     False
    ## 23       70     130    81          1     False
    ## 24       95     110    65          1     False
    ## 25       65      70    80          1     False
    ## 26       60      75   130          1     False
    ## 27       70      95   150          1     False
    ## 28       65     110    30          1     False
    ## 29      100     100    80          1     False
    ## 30      154      90   130          1      True
    ## 31      154     100   130          1      True
    ## 32      194     120   140          1      True
    ## 33       79      83    78          2     False
    ## 34       55      95    30          2     False
    ## 35       60      60    45          2     False
    ## 36       55      80    65          2     False
    ## 37       65     100    75          2     False
    ## 38       40      95    85          2     False
    ## 39       40     105    75          2     False
    ## 40       75      75    55          2     False
    ## 41      105      75    45          2     False
    ## 42       60      60    50          2     False
    ## 43       90      75   100          2      True
    ## 44       95     100    61          2     False
    ## 45       95     120    71          2     False
    ## 46      110     154    90          2      True
    ## 47      145      85   145          3     False
    ## 48      110      70    80          3     False
    ## 49      130      80   100          3     False
    ## 50       85      90    60          3     False
    ## 51       95     110    70          3     False
    ## 52       60      60    70          3     False
    ## 53       95      65   100          3     False
    ## 54       40      60    50          3     False
    ## 55       55      95    50          3     False
    ## 56       60      60    50          3     False
    ## 57       60      80    50          3     False
    ## 58       95      40    95          3     False
    ## 59      110      65   105          3     False
    ## 60      145     105    20          3     False
    ## 61      115      60    55          3     False
    ## 62      110     105    80          3     False
    ## 63       60      60    90          3     False
    ## 64       90      55    55          3     False
    ## 65       70      80    45          3     False
    ## 66       83      63    65          3     False
    ## 67       93      83    75          3     False
    ## 68       75      60    75          3     False
    ## 69      115      60   115          3     False
    ## 70      120      80   100          3     False
    ## 71       94      75    52          3     False
    ## 72      110      80   100          3     False
    ## 73      120      90   120          3     False
    ## 74       95      90    70          3     False
    ## 75      105     110   110          3     False
    ## 76      160     120   110          3      True
    ## 77      180     160    90          3      True
    ## 78      100      90    90          3      True
    ## 79      150      90    90          3      True
    ## 80      150      90    95          3      True
    ## 81      180     100   115          3      True
    ## 82      150      50   150          3      True
    ## 83      180      20   150          3      True
    ## 84       75      85    56          4     False
    ## 85      104      71   108          4     False
    ## 86       50      60   100          4     False
    ## 87       95      79    70          4     False
    ## 88       30      30    58          4     False
    ## 89       65      50    58          4     False
    ## 90       85      50   115          4     False
    ## 91       54      96   135          4     False
    ## 92      105      52    71          4     False
    ## 93       80      85   102          4     False
    ## 94      120      95    92          4     False
    ## 95      115      70    90          4     False
    ## 96      140      70   112          4     False
    ## 97       68      72    47          4     False
    ## 98       86      65    85          4     False
    ## 99      132     105    30          4     False
    ## 100      45      85   125          4     False
    ## 101      55      55    40          4     False
    ## 102      95      85    95          4     False
    ## 103      60      65    95          4     False
    ## 104      70      60    80          4     False
    ## 105      65     115    80          4     False
    ## 106      65     115   110          4     False
    ## 107     105     105    80          4      True
    ## 108     125      70   115          4      True
    ## 109     150     100    90          4      True
    ## 110     150     120   100          4      True
    ## 111      80     110   100          4      True
    ## 112     120     100    90          4      True
    ## 113     120      75   127          4      True
    ## 114     120     120   120          4      True
    ## 115     100      65    65          5     False
    ## 116      45      90    80          5     False
    ## 117      65      55    93          5     False
    ## 118      50      40    20          5     False
    ## 119      60      80    25          5     False
    ## 120      50      65    88          5     False
    ## 121      40      50    40          5     False
    ## 122      55      65    45          5     False
    ## 123      30      75    85          5     False
    ## 124      70      80    92          5     False
    ## 125      65      70    92          5     False
    ## 126      30      55    95          5     False
    ## 127      83      65    32          5     False
    ## 128      74      45    70          5     False
    ## 129     112      65   110          5     False
    ## 130     120      60   105          5     False
    ## 131      60     105    20          5     False
    ## 132     105      80    50          5     False
    ## 133      40      50    67          5     False
    ## 134      60      70    97          5     False
    ## 135      70      80    50          5     False
    ## 136      95      60   105          5     False
    ## 137      60      90    48          5     False
    ## 138      55      80    55          5     False
    ## 139      60      70    70          5     False
    ## 140      40      95    55          5     False
    ## 141      57      75    80          5     False
    ## 142      48      48   109          5     False
    ## 143     125      90    98          5     False
    ## 144      72      90   108          5      True
    ## 145     125      80   111          5      True
    ## 146     125      80   111          5      True
    ## 147     145      80   101          5      True
    ## 148     150     120    90          5      True
    ## 149     120     100    90          5      True
    ## 150     115      80   101          5      True
    ## 151     105      80    91          5      True
    ## 152     130      90    95          5      True
    ## 153     120      90    95          5      True
    ## 154     170     100    95          5      True
    ## 155      77      77   128          5     False
    ## 156     120      95    99          5     False
    ## 157      74      75    64          6     False
    ## 158      69      71    58          6     False
    ## 159      45      49    35          6     False
    ## 160     150      50    60          6     False
    ## 161      54      86    68          6     False
    ## 162      69      59    71          6     False
    ## 163      65      82    56          6     False
    ## 164      44      46    28          6     False
    ## 165     131      98    99          6      True
    ## 166     131      98    99          6      True
    ## 167     160     110   110          6      True
    ## 168     150     130    70          6      True
    ## 169     170     130    80          6      True
    ## 170     130      90    70          6      True

``` r
def = boxplot(HP, horizontal = TRUE)
```

![](pokemon_files/figure-gfm/code-2.png)<!-- -->

``` r
stats_HP = boxplot.stats(HP)
HP
```

    ##   [1]  45  60  80  80  39  58  78  78  78  44  59  79  79  45  50  60  40  45
    ##  [19]  65  65  40  63  83  83  30  55  40  65  35  60  35  60  50  75  55  70
    ##  [37]  90  46  61  81  70  95  38  73 115 140  40  75  45  60  75  35  60  60
    ##  [55]  70  10  35  40  65  50  80  40  65  55  90  40  65  90  25  40  55  55
    ##  [73]  70  80  90  50  65  80  40  80  40  55  80  50  65  90  95  95  25  50
    ##  [91]  52  35  60  65  90  80 105  30  50  30  45  60  60  35  60  85  30  55
    ## [109]  40  60  60  95  50  60  50  50  90  40  65  80 105 250  65 105 105  30
    ## [127]  55  45  80  30  60  40  70  65  65  65  65  65  75  20  95  95 130  48
    ## [145]  55 130  65  65  65  35  70  30  60  80  80 160  90  90  90  41  61  91
    ## [163] 106 106 106 100  45  60  80  39  58  78  50  65  85  35  85  60 100  40
    ## [181]  55  40  70  85  75 125  20  50  90  35  55  40  65  55  70  90  90  75
    ## [199]  70 100  70  90  35  55  75  55  30  75  65  55  95  65  95  60  95  60
    ## [217]  48 190  70  50  75 100  65  75  75  60  90  65  70  70  20  80  80  55
    ## [235]  60  90  40  50  50 100  55  35  75  45  65  65  45  75  75  75  90  90
    ## [253]  85  73  55  35  50  45  45  45  95 255  90 115 100  50  70 100 100 106
    ## [271] 106 100  40  50  70  70  45  60  80  80  50  70 100 100  35  70  38  78
    ## [289]  45  50  60  50  60  40  60  80  40  70  90  40  60  40  60  28  38  68
    ## [307]  68  40  70  60  60  60  80 150  31  61   1  64  84 104  72 144  50  30
    ## [325]  50  70  50  50  50  50  50  60  70  70  30  60  60  40  70  70  60  60
    ## [343]  65  65  50  70 100  45  70  70 130 170  60  70  70  70  60  80  60  45
    ## [361]  50  80  50  70  45  75  75  73  73  70  70  50 110  43  63  40  60  66
    ## [379]  86  45  75  20  95  70  60  44  64  64  20  40  99  65  65  65  95  50
    ## [397]  80  80  70  90 110  35  55  55 100  43  45  65  95  95  40  60  80  80
    ## [415]  80  80  80  80  80  80  80 100 100 100 100 105 105 100  50  50  50  50
    ## [433]  55  75  95  44  64  76  53  64  84  40  55  85  59  79  37  77  45  60
    ## [451]  80  40  60  67  97  30  60  40  60  60  60  70  30  70  60  55  85  45
    ## [469]  70  76 111  75  90 150  55  65  65  60 100  49  71  45  63 103  57  67
    ## [487]  50  20 100  76  50  58  68 108 108 135  40  70  70  68 108  40  70  48
    ## [505]  83  74  49  69  45  60  90  90  70  70 110 115 100  75  75  85  86  65
    ## [523]  65  75 110  85  68  68  60  45  70  50  50  50  50  50  50  75  80  75
    ## [541] 100  90  91 110 150 150 120  80 100  70 100 100 120 100  45  60  75  65
    ## [559]  90 110  55  75  95  45  60  45  65  85  41  64  50  75  50  75  50  75
    ## [577]  76 116  50  62  80  45  75  55  70  85  55  67  60 110 103 103  75  85
    ## [595] 105  50  75 105 120  75  45  55  75  30  40  60  40  60  45  70  70  50
    ## [613]  60  95  70 105 105  75  50  70  50  65  72  38  58  54  74  55  75  50
    ## [631]  80  40  60  55  75  45  60  70  45  65 110  62  75  36  51  71  60  80
    ## [649]  55  50  70  69 114  55 100 165  50  70  44  74  40  60  60  35  65  85
    ## [667]  55  75  50  60  60  46  66  76  55  95  70  50  80 109  45  65  77  59
    ## [685]  89  45  65  95  70 100  70 110  85  58  52  72  92  55  85  91  91  91
    ## [703]  79  79  79  79 100 100  89  89 125 125 125  91  91 100 100  71  56  61
    ## [721]  88  40  59  75  41  54  72  38  85  45  62  78  38  45  80  62  86  44
    ## [739]  54  78  66 123  67  95  75  62  74  74  45  59  60  60  78 101  62  82
    ## [757]  53  86  42  72  50  65  50  71  44  62  58  82  77 123  95  78  67  50
    ## [775]  45  68  90  57  43  85  49  44  54  59  65  55  75  85  55  95  40  85
    ## [793] 126 126 108  50  50  80  80  80

``` r
stats_HP
```

    ## $stats
    ## [1]  10  50  65  80 125
    ## 
    ## $n
    ## [1] 800
    ## 
    ## $conf
    ## [1] 63.32416 66.67584
    ## 
    ## $out
    ##  [1] 140 250 130 130 160 190 255 150   1 144 130 170 150 135 150 150 165 126 126

``` r
pk2 <- HP[HP < 60]
length(HP) - length(pk2)
```

    ## [1] 528

``` r
boxplot(pk2, horizontal = TRUE)
```

![](pokemon_files/figure-gfm/code-3.png)<!-- -->

``` r
HP_out <- filter(pk, pk$HP > 60 )
HP_out
```

    ##      X.                      Name   Type.1   Type.2 Total  HP Attack Defense
    ## 1     3                  Venusaur    Grass   Poison   525  80     82      83
    ## 2     3     VenusaurMega Venusaur    Grass   Poison   625  80    100     123
    ## 3     6                 Charizard     Fire   Flying   534  78     84      78
    ## 4     6 CharizardMega Charizard X     Fire   Dragon   634  78    130     111
    ## 5     6 CharizardMega Charizard Y     Fire   Flying   634  78    104      78
    ## 6     9                 Blastoise    Water            530  79     83     100
    ## 7     9   BlastoiseMega Blastoise    Water            630  79    103     120
    ## 8    15                  Beedrill      Bug   Poison   395  65     90      40
    ## 9    15     BeedrillMega Beedrill      Bug   Poison   495  65    150      40
    ## 10   17                 Pidgeotto   Normal   Flying   349  63     60      55
    ## 11   18                   Pidgeot   Normal   Flying   479  83     80      75
    ## 12   18       PidgeotMega Pidgeot   Normal   Flying   579  83     80      80
    ## 13   22                    Fearow   Normal   Flying   442  65     90      65
    ## 14   28                 Sandslash   Ground            450  75    100     110
    ## 15   30                  Nidorina   Poison            365  70     62      67
    ## 16   31                 Nidoqueen   Poison   Ground   505  90     92      87
    ## 17   33                  Nidorino   Poison            365  61     72      57
    ## 18   34                  Nidoking   Poison   Ground   505  81    102      77
    ## 19   35                  Clefairy    Fairy            323  70     45      48
    ## 20   36                  Clefable    Fairy            483  95     70      73
    ## 21   38                 Ninetales     Fire            505  73     76      75
    ## 22   39                Jigglypuff   Normal    Fairy   270 115     45      20
    ## 23   40                Wigglytuff   Normal    Fairy   435 140     70      45
    ## 24   42                    Golbat   Poison   Flying   455  75     80      70
    ## 25   45                 Vileplume    Grass   Poison   490  75     80      85
    ## 26   49                  Venomoth      Bug   Poison   450  70     65      60
    ## 27   53                   Persian   Normal            440  65     70      60
    ## 28   55                   Golduck    Water            500  80     82      78
    ## 29   57                  Primeape Fighting            455  65    105      60
    ## 30   59                  Arcanine     Fire            555  90    110      80
    ## 31   61                 Poliwhirl    Water            385  65     65      65
    ## 32   62                 Poliwrath    Water Fighting   510  90     95      95
    ## 33   66                    Machop Fighting            305  70     80      50
    ## 34   67                   Machoke Fighting            405  80    100      70
    ## 35   68                   Machamp Fighting            505  90    130      80
    ## 36   70                Weepinbell    Grass   Poison   390  65     90      50
    ## 37   71                Victreebel    Grass   Poison   490  80    105      65
    ## 38   73                Tentacruel    Water   Poison   515  80     70      65
    ## 39   76                     Golem     Rock   Ground   495  80    120     130
    ## 40   78                  Rapidash     Fire            500  65    100      70
    ## 41   79                  Slowpoke    Water  Psychic   315  90     65      65
    ## 42   80                   Slowbro    Water  Psychic   490  95     75     110
    ## 43   80       SlowbroMega Slowbro    Water  Psychic   590  95     75     180
    ## 44   86                      Seel    Water            325  65     45      55
    ## 45   87                   Dewgong    Water      Ice   475  90     70      80
    ## 46   88                    Grimer   Poison            325  80     80      50
    ## 47   89                       Muk   Poison            500 105    105      75
    ## 48   97                     Hypno  Psychic            483  85     73      70
    ## 49  103                 Exeggutor    Grass  Psychic   520  95     95      85
    ## 50  108                 Lickitung   Normal            385  90     55      75
    ## 51  110                   Weezing   Poison            490  65     90     120
    ## 52  111                   Rhyhorn   Ground     Rock   345  80     85      95
    ## 53  112                    Rhydon   Ground     Rock   485 105    130     120
    ## 54  113                   Chansey   Normal            450 250      5       5
    ## 55  114                   Tangela    Grass            435  65     55     115
    ## 56  115                Kangaskhan   Normal            490 105     95      80
    ## 57  115 KangaskhanMega Kangaskhan   Normal            590 105    125     100
    ## 58  119                   Seaking    Water            450  80     92      65
    ## 59  123                   Scyther      Bug   Flying   500  70    110      80
    ## 60  124                      Jynx      Ice  Psychic   455  65     50      35
    ## 61  125                Electabuzz Electric            490  65     83      57
    ## 62  126                    Magmar     Fire            495  65     95      57
    ## 63  127                    Pinsir      Bug            500  65    125     100
    ## 64  127         PinsirMega Pinsir      Bug   Flying   600  65    155     120
    ## 65  128                    Tauros   Normal            490  75    100      95
    ## 66  130                  Gyarados    Water   Flying   540  95    125      79
    ## 67  130     GyaradosMega Gyarados    Water     Dark   640  95    155     109
    ## 68  131                    Lapras    Water      Ice   535 130     85      80
    ## 69  134                  Vaporeon    Water            525 130     65      60
    ## 70  135                   Jolteon Electric            525  65     65      60
    ## 71  136                   Flareon     Fire            525  65    130      60
    ## 72  137                   Porygon   Normal            395  65     60      70
    ## 73  139                   Omastar     Rock    Water   495  70     60     125
    ## 74  142                Aerodactyl     Rock   Flying   515  80    105      65
    ## 75  142 AerodactylMega Aerodactyl     Rock   Flying   615  80    135      85
    ## 76  143                   Snorlax   Normal            540 160    110      65
    ## 77  144                  Articuno      Ice   Flying   580  90     85     100
    ## 78  145                    Zapdos Electric   Flying   580  90     90      85
    ## 79  146                   Moltres     Fire   Flying   580  90    100      90
    ## 80  148                 Dragonair   Dragon            420  61     84      65
    ## 81  149                 Dragonite   Dragon   Flying   600  91    134      95
    ## 82  150                    Mewtwo  Psychic            680 106    110      90
    ## 83  150       MewtwoMega Mewtwo X  Psychic Fighting   780 106    190     100
    ## 84  150       MewtwoMega Mewtwo Y  Psychic            780 106    150      70
    ## 85  151                       Mew  Psychic            600 100    100     100
    ## 86  154                  Meganium    Grass            525  80     82     100
    ## 87  157                Typhlosion     Fire            534  78     84      78
    ## 88  159                  Croconaw    Water            405  65     80      80
    ## 89  160                Feraligatr    Water            530  85    105     100
    ## 90  162                    Furret   Normal            415  85     76      64
    ## 91  164                   Noctowl   Normal   Flying   442 100     50      50
    ## 92  168                   Ariados      Bug   Poison   390  70     90      70
    ## 93  169                    Crobat   Poison   Flying   535  85     90      80
    ## 94  170                  Chinchou    Water Electric   330  75     38      38
    ## 95  171                   Lanturn    Water Electric   460 125     58      58
    ## 96  174                 Igglybuff   Normal    Fairy   210  90     30      15
    ## 97  178                      Xatu  Psychic   Flying   470  65     75      70
    ## 98  180                   Flaaffy Electric            365  70     55      55
    ## 99  181                  Ampharos Electric            510  90     75      85
    ## 100 181     AmpharosMega Ampharos Electric   Dragon   610  90     95     105
    ## 101 182                 Bellossom    Grass            490  75     80      95
    ## 102 183                    Marill    Water    Fairy   250  70     20      50
    ## 103 184                 Azumarill    Water    Fairy   420 100     50      80
    ## 104 185                 Sudowoodo     Rock            410  70    100     115
    ## 105 186                  Politoed    Water            500  90     75      75
    ## 106 189                  Jumpluff    Grass   Flying   460  75     55      70
    ## 107 192                  Sunflora    Grass            425  75     75      55
    ## 108 193                     Yanma      Bug   Flying   390  65     65      45
    ## 109 195                  Quagsire    Water   Ground   430  95     85      85
    ## 110 196                    Espeon  Psychic            525  65     65      60
    ## 111 197                   Umbreon     Dark            525  95     65     110
    ## 112 199                  Slowking    Water  Psychic   490  95     75      80
    ## 113 202                 Wobbuffet  Psychic            405 190     33      58
    ## 114 203                 Girafarig   Normal  Psychic   455  70     80      65
    ## 115 205                Forretress      Bug    Steel   465  75     90     140
    ## 116 206                 Dunsparce   Normal            415 100     70      70
    ## 117 207                    Gligar   Ground   Flying   430  65     75     105
    ## 118 208                   Steelix    Steel   Ground   510  75     85     200
    ## 119 208       SteelixMega Steelix    Steel   Ground   610  75    125     230
    ## 120 210                  Granbull    Fairy            450  90    120      75
    ## 121 211                  Qwilfish    Water   Poison   430  65     95      75
    ## 122 212                    Scizor      Bug    Steel   500  70    130     100
    ## 123 212         ScizorMega Scizor      Bug    Steel   600  70    150     140
    ## 124 214                 Heracross      Bug Fighting   500  80    125      75
    ## 125 214   HeracrossMega Heracross      Bug Fighting   600  80    185     115
    ## 126 217                  Ursaring   Normal            500  90    130      75
    ## 127 221                 Piloswine      Ice   Ground   450 100    100      80
    ## 128 224                 Octillery    Water            480  75    105      75
    ## 129 226                   Mantine    Water   Flying   465  65     40      70
    ## 130 227                  Skarmory    Steel   Flying   465  65     80     140
    ## 131 229                  Houndoom     Dark     Fire   500  75     90      50
    ## 132 229     HoundoomMega Houndoom     Dark     Fire   600  75     90      90
    ## 133 230                   Kingdra    Water   Dragon   540  75     95      95
    ## 134 231                    Phanpy   Ground            330  90     60      60
    ## 135 232                   Donphan   Ground            500  90    120     120
    ## 136 233                  Porygon2   Normal            515  85     80      90
    ## 137 234                  Stantler   Normal            465  73     95      62
    ## 138 241                   Miltank   Normal            490  95     80     105
    ## 139 242                   Blissey   Normal            540 255     10      10
    ## 140 243                    Raikou Electric            580  90     85      75
    ## 141 244                     Entei     Fire            580 115    115      85
    ## 142 245                   Suicune    Water            580 100     75     115
    ## 143 247                   Pupitar     Rock   Ground   410  70     84      70
    ## 144 248                 Tyranitar     Rock     Dark   600 100    134     110
    ## 145 248   TyranitarMega Tyranitar     Rock     Dark   700 100    164     150
    ## 146 249                     Lugia  Psychic   Flying   680 106     90     130
    ## 147 250                     Ho-oh     Fire   Flying   680 106    130      90
    ## 148 251                    Celebi  Psychic    Grass   600 100    100     100
    ## 149 254                  Sceptile    Grass            530  70     85      65
    ## 150 254     SceptileMega Sceptile    Grass   Dragon   630  70    110      75
    ## 151 257                  Blaziken     Fire Fighting   530  80    120      70
    ## 152 257     BlazikenMega Blaziken     Fire Fighting   630  80    160      80
    ## 153 259                 Marshtomp    Water   Ground   405  70     85      70
    ## 154 260                  Swampert    Water   Ground   535 100    110      90
    ## 155 260     SwampertMega Swampert    Water   Ground   635 100    150     110
    ## 156 262                 Mightyena     Dark            420  70     90      70
    ## 157 264                   Linoone   Normal            420  78     70      61
    ## 158 272                  Ludicolo    Water    Grass   480  80     70      70
    ## 159 274                   Nuzleaf    Grass     Dark   340  70     70      40
    ## 160 275                   Shiftry    Grass     Dark   480  90    100      60
    ## 161 282                 Gardevoir  Psychic    Fairy   518  68     65      65
    ## 162 282   GardevoirMega Gardevoir  Psychic    Fairy   618  68     85      65
    ## 163 284                Masquerain      Bug   Flying   414  70     60      62
    ## 164 288                  Vigoroth   Normal            440  80     80      80
    ## 165 289                   Slaking   Normal            670 150    160     100
    ## 166 291                   Ninjask      Bug   Flying   456  61     90      45
    ## 167 293                   Whismur   Normal            240  64     51      23
    ## 168 294                   Loudred   Normal            360  84     71      43
    ## 169 295                   Exploud   Normal            490 104     91      63
    ## 170 296                  Makuhita Fighting            237  72     60      30
    ## 171 297                  Hariyama Fighting            474 144    120      60
    ## 172 301                  Delcatty   Normal            380  70     65      65
    ## 173 306                    Aggron    Steel     Rock   530  70    110     180
    ## 174 306         AggronMega Aggron    Steel            630  70    140     230
    ## 175 310                 Manectric Electric            475  70     75      60
    ## 176 310   ManectricMega Manectric Electric            575  70     75      80
    ## 177 313                   Volbeat      Bug            400  65     73      55
    ## 178 314                  Illumise      Bug            400  65     47      55
    ## 179 316                    Gulpin   Poison            302  70     43      53
    ## 180 317                    Swalot   Poison            467 100     73      83
    ## 181 319                  Sharpedo    Water     Dark   460  70    120      40
    ## 182 319     SharpedoMega Sharpedo    Water     Dark   560  70    140      70
    ## 183 320                   Wailmer    Water            400 130     70      35
    ## 184 321                   Wailord    Water            500 170     90      45
    ## 185 323                  Camerupt     Fire   Ground   460  70    100      70
    ## 186 323     CameruptMega Camerupt     Fire   Ground   560  70    120     100
    ## 187 324                   Torkoal     Fire            470  70     85     140
    ## 188 326                   Grumpig  Psychic            470  80     45      65
    ## 189 330                    Flygon   Ground   Dragon   520  80    100      80
    ## 190 332                  Cacturne    Grass     Dark   475  70    115      60
    ## 191 334                   Altaria   Dragon   Flying   490  75     70      90
    ## 192 334       AltariaMega Altaria   Dragon    Fairy   590  75    110     110
    ## 193 335                  Zangoose   Normal            458  73    115      60
    ## 194 336                   Seviper   Poison            458  73    100      60
    ## 195 337                  Lunatone     Rock  Psychic   440  70     55      65
    ## 196 338                   Solrock     Rock  Psychic   440  70     95      85
    ## 197 340                  Whiscash    Water   Ground   468 110     78      73
    ## 198 342                 Crawdaunt    Water     Dark   468  63    120      85
    ## 199 345                    Lileep     Rock    Grass   355  66     41      77
    ## 200 346                   Cradily     Rock    Grass   495  86     81      97
    ## 201 348                   Armaldo     Rock      Bug   495  75    125     100
    ## 202 350                   Milotic    Water            540  95     60      79
    ## 203 351                  Castform   Normal            420  70     70      70
    ## 204 354                   Banette    Ghost            455  64    115      65
    ## 205 354       BanetteMega Banette    Ghost            555  64    165      75
    ## 206 357                   Tropius    Grass   Flying   460  99     68      83
    ## 207 358                  Chimecho  Psychic            425  65     50      70
    ## 208 359                     Absol     Dark            465  65    130      60
    ## 209 359           AbsolMega Absol     Dark            565  65    150      60
    ## 210 360                    Wynaut  Psychic            260  95     23      48
    ## 211 362                    Glalie      Ice            480  80     80      80
    ## 212 362         GlalieMega Glalie      Ice            580  80    120      80
    ## 213 363                    Spheal      Ice    Water   290  70     40      50
    ## 214 364                    Sealeo      Ice    Water   410  90     60      70
    ## 215 365                   Walrein      Ice    Water   530 110     80      90
    ## 216 369                 Relicanth    Water     Rock   485 100     90     130
    ## 217 372                   Shelgon   Dragon            420  65     95     100
    ## 218 373                 Salamence   Dragon   Flying   600  95    135      80
    ## 219 373   SalamenceMega Salamence   Dragon   Flying   700  95    145     130
    ## 220 376                 Metagross    Steel  Psychic   600  80    135     130
    ## 221 376   MetagrossMega Metagross    Steel  Psychic   700  80    145     150
    ## 222 377                  Regirock     Rock            580  80    100     200
    ## 223 378                    Regice      Ice            580  80     50     100
    ## 224 379                 Registeel    Steel            580  80     75     150
    ## 225 380                    Latias   Dragon  Psychic   600  80     80      90
    ## 226 380         LatiasMega Latias   Dragon  Psychic   700  80    100     120
    ## 227 381                    Latios   Dragon  Psychic   600  80     90      80
    ## 228 381         LatiosMega Latios   Dragon  Psychic   700  80    130     100
    ## 229 382                    Kyogre    Water            670 100    100      90
    ## 230 382       KyogrePrimal Kyogre    Water            770 100    150      90
    ## 231 383                   Groudon   Ground            670 100    150     140
    ## 232 383     GroudonPrimal Groudon   Ground     Fire   770 100    180     160
    ## 233 384                  Rayquaza   Dragon   Flying   680 105    150      90
    ## 234 384     RayquazaMega Rayquaza   Dragon   Flying   780 105    180     100
    ## 235 385                   Jirachi    Steel  Psychic   600 100    100     100
    ## 236 388                    Grotle    Grass            405  75     89      85
    ## 237 389                  Torterra    Grass   Ground   525  95    109     105
    ## 238 391                  Monferno     Fire Fighting   405  64     78      52
    ## 239 392                 Infernape     Fire Fighting   534  76    104      71
    ## 240 394                  Prinplup    Water            405  64     66      68
    ## 241 395                  Empoleon    Water    Steel   530  84     86      88
    ## 242 398                 Staraptor   Normal   Flying   485  85    120      70
    ## 243 400                   Bibarel   Normal    Water   410  79     85      60
    ## 244 402                Kricketune      Bug            384  77     85      51
    ## 245 405                    Luxray Electric            523  80    120      79
    ## 246 408                  Cranidos     Rock            350  67    125      40
    ## 247 409                 Rampardos     Rock            495  97    165      60
    ## 248 414                    Mothim      Bug   Flying   424  70     94      50
    ## 249 416                 Vespiquen      Bug   Flying   474  70     80     102
    ## 250 419                  Floatzel    Water            495  85    105      55
    ## 251 421                   Cherrim    Grass            450  70     60      70
    ## 252 422                   Shellos    Water            325  76     48      48
    ## 253 423                 Gastrodon    Water   Ground   475 111     83      68
    ## 254 424                   Ambipom   Normal            482  75    100      66
    ## 255 425                  Drifloon    Ghost   Flying   348  90     50      34
    ## 256 426                  Drifblim    Ghost   Flying   498 150     80      44
    ## 257 428                   Lopunny   Normal            480  65     76      84
    ## 258 428       LopunnyMega Lopunny   Normal Fighting   580  65    136      94
    ## 259 430                 Honchkrow     Dark   Flying   505 100    125      52
    ## 260 432                   Purugly   Normal            452  71     82      64
    ## 261 434                    Stunky   Poison     Dark   329  63     63      47
    ## 262 435                  Skuntank   Poison     Dark   479 103     93      67
    ## 263 437                  Bronzong    Steel  Psychic   500  67     89     116
    ## 264 440                   Happiny   Normal            220 100      5       5
    ## 265 441                    Chatot   Normal   Flying   411  76     65      45
    ## 266 444                    Gabite   Dragon   Ground   410  68     90      65
    ## 267 445                  Garchomp   Dragon   Ground   600 108    130      95
    ## 268 445     GarchompMega Garchomp   Dragon   Ground   700 108    170     115
    ## 269 446                  Munchlax   Normal            390 135     85      40
    ## 270 448                   Lucario Fighting    Steel   525  70    110      70
    ## 271 448       LucarioMega Lucario Fighting    Steel   625  70    145      88
    ## 272 449                Hippopotas   Ground            330  68     72      78
    ## 273 450                 Hippowdon   Ground            525 108    112     118
    ## 274 452                   Drapion   Poison     Dark   500  70     90     110
    ## 275 454                 Toxicroak   Poison Fighting   490  83    106      65
    ## 276 455                 Carnivine    Grass            454  74    100      72
    ## 277 457                  Lumineon    Water            460  69     69      76
    ## 278 460                 Abomasnow    Grass      Ice   494  90     92      75
    ## 279 460   AbomasnowMega Abomasnow    Grass      Ice   594  90    132     105
    ## 280 461                   Weavile     Dark      Ice   510  70    120      65
    ## 281 462                 Magnezone Electric    Steel   535  70     70     115
    ## 282 463                Lickilicky   Normal            515 110     85      95
    ## 283 464                 Rhyperior   Ground     Rock   535 115    140     130
    ## 284 465                 Tangrowth    Grass            535 100    100     125
    ## 285 466                Electivire Electric            540  75    123      67
    ## 286 467                 Magmortar     Fire            540  75     95      67
    ## 287 468                  Togekiss    Fairy   Flying   545  85     50      95
    ## 288 469                   Yanmega      Bug   Flying   515  86     76      86
    ## 289 470                   Leafeon    Grass            525  65    110     130
    ## 290 471                   Glaceon      Ice            525  65     60     110
    ## 291 472                   Gliscor   Ground   Flying   510  75     95     125
    ## 292 473                 Mamoswine      Ice   Ground   530 110    130      80
    ## 293 474                 Porygon-Z   Normal            535  85     80      70
    ## 294 475                   Gallade  Psychic Fighting   518  68    125      65
    ## 295 475       GalladeMega Gallade  Psychic Fighting   618  68    165      95
    ## 296 478                  Froslass      Ice    Ghost   480  70     80      70
    ## 297 480                      Uxie  Psychic            580  75     75     130
    ## 298 481                   Mesprit  Psychic            580  80    105     105
    ## 299 482                     Azelf  Psychic            580  75    125      70
    ## 300 483                    Dialga    Steel   Dragon   680 100    120     120
    ## 301 484                    Palkia    Water   Dragon   680  90    120     100
    ## 302 485                   Heatran     Fire    Steel   600  91     90     106
    ## 303 486                 Regigigas   Normal            670 110    160     110
    ## 304 487     GiratinaAltered Forme    Ghost   Dragon   680 150    100     120
    ## 305 487      GiratinaOrigin Forme    Ghost   Dragon   680 150    120     100
    ## 306 488                 Cresselia  Psychic            600 120     70     120
    ## 307 489                    Phione    Water            480  80     80      80
    ## 308 490                   Manaphy    Water            600 100    100     100
    ## 309 491                   Darkrai     Dark            600  70     90      90
    ## 310 492         ShayminLand Forme    Grass            600 100    100     100
    ## 311 492          ShayminSky Forme    Grass   Flying   600 100    103      75
    ## 312 493                    Arceus   Normal            720 120    120     120
    ## 313 494                   Victini  Psychic     Fire   600 100    100     100
    ## 314 497                 Serperior    Grass            528  75     75      95
    ## 315 498                     Tepig     Fire            308  65     63      45
    ## 316 499                   Pignite     Fire Fighting   418  90     93      55
    ## 317 500                    Emboar     Fire Fighting   528 110    123      65
    ## 318 502                    Dewott    Water            413  75     75      60
    ## 319 503                  Samurott    Water            528  95    100      85
    ## 320 507                   Herdier   Normal            370  65     80      65
    ## 321 508                 Stoutland   Normal            500  85    110      90
    ## 322 510                   Liepard     Dark            446  64     88      50
    ## 323 512                  Simisage    Grass            498  75     98      63
    ## 324 514                  Simisear     Fire            498  75     98      63
    ## 325 516                  Simipour    Water            498  75     98      63
    ## 326 517                     Munna  Psychic            292  76     25      45
    ## 327 518                  Musharna  Psychic            487 116     55      85
    ## 328 520                 Tranquill   Normal   Flying   358  62     77      62
    ## 329 521                  Unfezant   Normal   Flying   488  80    115      80
    ## 330 523                 Zebstrika Electric            497  75    100      63
    ## 331 525                   Boldore     Rock            390  70    105     105
    ## 332 526                  Gigalith     Rock            515  85    135     130
    ## 333 528                   Swoobat  Psychic   Flying   425  67     57      55
    ## 334 530                 Excadrill   Ground    Steel   508 110    135      60
    ## 335 531                    Audino   Normal            445 103     60      86
    ## 336 531         AudinoMega Audino   Normal    Fairy   545 103     60     126
    ## 337 532                   Timburr Fighting            305  75     80      55
    ## 338 533                   Gurdurr Fighting            405  85    105      85
    ## 339 534                Conkeldurr Fighting            505 105    140      95
    ## 340 536                 Palpitoad    Water   Ground   384  75     65      55
    ## 341 537                Seismitoad    Water   Ground   509 105     95      75
    ## 342 538                     Throh Fighting            465 120    100      85
    ## 343 539                      Sawk Fighting            465  75    125      75
    ## 344 542                  Leavanny      Bug    Grass   500  75    103      80
    ## 345 549                 Lilligant    Grass            480  70     60      75
    ## 346 550                  Basculin    Water            460  70     92      65
    ## 347 553                Krookodile   Ground     Dark   519  95    117      80
    ## 348 554                  Darumaka     Fire            315  70     90      45
    ## 349 555   DarmanitanStandard Mode     Fire            480 105    140      55
    ## 350 555        DarmanitanZen Mode     Fire  Psychic   540 105     30     105
    ## 351 556                  Maractus    Grass            461  75     86      67
    ## 352 558                   Crustle      Bug     Rock   475  70     95     125
    ## 353 560                   Scrafty     Dark Fighting   488  65     90     115
    ## 354 561                  Sigilyph  Psychic   Flying   490  72     58      80
    ## 355 565                Carracosta    Water     Rock   495  74    108     133
    ## 356 567                  Archeops     Rock   Flying   567  75    140      65
    ## 357 569                  Garbodor   Poison            474  80     95      82
    ## 358 573                  Cinccino   Normal            470  75     95      60
    ## 359 576                Gothitelle  Psychic            490  70     55      95
    ## 360 578                   Duosion  Psychic            370  65     40      50
    ## 361 579                 Reuniclus  Psychic            490 110     65      75
    ## 362 580                  Ducklett    Water   Flying   305  62     44      50
    ## 363 581                    Swanna    Water   Flying   473  75     87      63
    ## 364 584                 Vanilluxe      Ice            535  71     95      85
    ## 365 586                  Sawsbuck   Normal    Grass   475  80    100      70
    ## 366 589                Escavalier      Bug    Steel   495  70    135     105
    ## 367 590                   Foongus    Grass   Poison   294  69     55      45
    ## 368 591                 Amoonguss    Grass   Poison   464 114     85      70
    ## 369 593                 Jellicent    Water    Ghost   480 100     60      70
    ## 370 594                 Alomomola    Water            470 165     75      80
    ## 371 596                Galvantula      Bug Electric   472  70     77      60
    ## 372 598                Ferrothorn    Grass    Steel   489  74     94     131
    ## 373 603                 Eelektrik Electric            405  65     85      70
    ## 374 604                Eelektross Electric            515  85    115      80
    ## 375 606                  Beheeyem  Psychic            485  75     75      75
    ## 376 611                   Fraxure   Dragon            410  66    117      70
    ## 377 612                   Haxorus   Dragon            540  76    147      90
    ## 378 614                   Beartic      Ice            485  95    110      80
    ## 379 615                 Cryogonal      Ice            485  70     50      30
    ## 380 617                  Accelgor      Bug            495  80     70      40
    ## 381 618                  Stunfisk   Ground Electric   471 109     66      84
    ## 382 620                  Mienshao Fighting            510  65    125      60
    ## 383 621                 Druddigon   Dragon            485  77    120      90
    ## 384 623                    Golurk   Ground    Ghost   483  89    124      80
    ## 385 625                   Bisharp     Dark    Steel   490  65    125     100
    ## 386 626                Bouffalant   Normal            490  95    110      95
    ## 387 627                   Rufflet   Normal   Flying   350  70     83      50
    ## 388 628                  Braviary   Normal   Flying   510 100    123      75
    ## 389 629                   Vullaby     Dark   Flying   370  70     55      75
    ## 390 630                 Mandibuzz     Dark   Flying   510 110     65     105
    ## 391 631                   Heatmor     Fire            484  85     97      66
    ## 392 634                  Zweilous     Dark   Dragon   420  72     85      70
    ## 393 635                 Hydreigon     Dark   Dragon   600  92    105      90
    ## 394 637                 Volcarona      Bug     Fire   550  85     60      65
    ## 395 638                  Cobalion    Steel Fighting   580  91     90     129
    ## 396 639                 Terrakion     Rock Fighting   580  91    129      90
    ## 397 640                  Virizion    Grass Fighting   580  91     90      72
    ## 398 641   TornadusIncarnate Forme   Flying            580  79    115      70
    ## 399 641     TornadusTherian Forme   Flying            580  79    100      80
    ## 400 642  ThundurusIncarnate Forme Electric   Flying   580  79    115      70
    ## 401 642    ThundurusTherian Forme Electric   Flying   580  79    105      70
    ## 402 643                  Reshiram   Dragon     Fire   680 100    120     100
    ## 403 644                    Zekrom   Dragon Electric   680 100    150     120
    ## 404 645   LandorusIncarnate Forme   Ground   Flying   600  89    125      90
    ## 405 645     LandorusTherian Forme   Ground   Flying   600  89    145      90
    ## 406 646                    Kyurem   Dragon      Ice   660 125    130      90
    ## 407 646        KyuremBlack Kyurem   Dragon      Ice   700 125    170     100
    ## 408 646        KyuremWhite Kyurem   Dragon      Ice   700 125    120      90
    ## 409 647      KeldeoOrdinary Forme    Water Fighting   580  91     72      90
    ## 410 647      KeldeoResolute Forme    Water Fighting   580  91     72      90
    ## 411 648        MeloettaAria Forme   Normal  Psychic   600 100     77      77
    ## 412 648   MeloettaPirouette Forme   Normal Fighting   600 100    128      90
    ## 413 649                  Genesect      Bug    Steel   600  71    120      95
    ## 414 651                 Quilladin    Grass            405  61     78      95
    ## 415 652                Chesnaught    Grass Fighting   530  88    107     122
    ## 416 655                   Delphox     Fire  Psychic   534  75     69      72
    ## 417 658                  Greninja    Water     Dark   530  72     95      67
    ## 418 660                 Diggersby   Normal   Ground   423  85     56      77
    ## 419 662               Fletchinder     Fire   Flying   382  62     73      55
    ## 420 663                Talonflame     Fire   Flying   499  78     81      71
    ## 421 666                  Vivillon      Bug   Flying   411  80     52      50
    ## 422 667                    Litleo     Fire   Normal   369  62     50      58
    ## 423 668                    Pyroar     Fire   Normal   507  86     68      72
    ## 424 671                   Florges    Fairy            552  78     65      68
    ## 425 672                    Skiddo    Grass            350  66     65      48
    ## 426 673                    Gogoat    Grass            531 123    100      62
    ## 427 674                   Pancham Fighting            348  67     82      62
    ## 428 675                   Pangoro Fighting     Dark   495  95    124      78
    ## 429 676                   Furfrou   Normal            472  75     80      60
    ## 430 677                    Espurr  Psychic            355  62     48      54
    ## 431 678              MeowsticMale  Psychic            466  74     48      76
    ## 432 678            MeowsticFemale  Psychic            466  74     48      76
    ## 433 682                  Spritzee    Fairy            341  78     52      60
    ## 434 683                Aromatisse    Fairy            462 101     72      72
    ## 435 684                   Swirlix    Fairy            341  62     48      66
    ## 436 685                  Slurpuff    Fairy            480  82     80      86
    ## 437 687                   Malamar     Dark  Psychic   482  86     92      88
    ## 438 689                Barbaracle     Rock    Water   500  72    105     115
    ## 439 691                  Dragalge   Poison   Dragon   494  65     75      90
    ## 440 693                 Clawitzer    Water            500  71     73      88
    ## 441 695                 Heliolisk Electric   Normal   481  62     55      52
    ## 442 697                 Tyrantrum     Rock   Dragon   521  82    121     119
    ## 443 698                    Amaura     Rock      Ice   362  77     59      50
    ## 444 699                   Aurorus     Rock      Ice   521 123     77      72
    ## 445 700                   Sylveon    Fairy            525  95     65      65
    ## 446 701                  Hawlucha Fighting   Flying   500  78     92      75
    ## 447 702                   Dedenne Electric    Fairy   431  67     58      57
    ## 448 705                   Sliggoo   Dragon            452  68     75      53
    ## 449 706                    Goodra   Dragon            600  90    100      70
    ## 450 709                 Trevenant    Ghost    Grass   474  85    110      76
    ## 451 711     GourgeistAverage Size    Ghost    Grass   494  65     90     122
    ## 452 711       GourgeistLarge Size    Ghost    Grass   494  75     95     122
    ## 453 711       GourgeistSuper Size    Ghost    Grass   494  85    100     122
    ## 454 713                   Avalugg      Ice            514  95    117     184
    ## 455 715                   Noivern   Flying   Dragon   535  85     70      80
    ## 456 716                   Xerneas    Fairy            680 126    131      95
    ## 457 717                   Yveltal     Dark   Flying   680 126    131      95
    ## 458 718          Zygarde50% Forme   Dragon   Ground   600 108    100     121
    ## 459 720       HoopaHoopa Confined  Psychic    Ghost   600  80    110      60
    ## 460 720        HoopaHoopa Unbound  Psychic     Dark   680  80    160      60
    ## 461 721                 Volcanion     Fire    Water   600  80    110     120
    ##     Sp..Atk Sp..Def Speed Generation Legendary
    ## 1       100     100    80          1     False
    ## 2       122     120    80          1     False
    ## 3       109      85   100          1     False
    ## 4       130      85   100          1     False
    ## 5       159     115   100          1     False
    ## 6        85     105    78          1     False
    ## 7       135     115    78          1     False
    ## 8        45      80    75          1     False
    ## 9        15      80   145          1     False
    ## 10       50      50    71          1     False
    ## 11       70      70   101          1     False
    ## 12      135      80   121          1     False
    ## 13       61      61   100          1     False
    ## 14       45      55    65          1     False
    ## 15       55      55    56          1     False
    ## 16       75      85    76          1     False
    ## 17       55      55    65          1     False
    ## 18       85      75    85          1     False
    ## 19       60      65    35          1     False
    ## 20       95      90    60          1     False
    ## 21       81     100   100          1     False
    ## 22       45      25    20          1     False
    ## 23       85      50    45          1     False
    ## 24       65      75    90          1     False
    ## 25      110      90    50          1     False
    ## 26       90      75    90          1     False
    ## 27       65      65   115          1     False
    ## 28       95      80    85          1     False
    ## 29       60      70    95          1     False
    ## 30      100      80    95          1     False
    ## 31       50      50    90          1     False
    ## 32       70      90    70          1     False
    ## 33       35      35    35          1     False
    ## 34       50      60    45          1     False
    ## 35       65      85    55          1     False
    ## 36       85      45    55          1     False
    ## 37      100      70    70          1     False
    ## 38       80     120   100          1     False
    ## 39       55      65    45          1     False
    ## 40       80      80   105          1     False
    ## 41       40      40    15          1     False
    ## 42      100      80    30          1     False
    ## 43      130      80    30          1     False
    ## 44       45      70    45          1     False
    ## 45       70      95    70          1     False
    ## 46       40      50    25          1     False
    ## 47       65     100    50          1     False
    ## 48       73     115    67          1     False
    ## 49      125      65    55          1     False
    ## 50       60      75    30          1     False
    ## 51       85      70    60          1     False
    ## 52       30      30    25          1     False
    ## 53       45      45    40          1     False
    ## 54       35     105    50          1     False
    ## 55      100      40    60          1     False
    ## 56       40      80    90          1     False
    ## 57       60     100   100          1     False
    ## 58       65      80    68          1     False
    ## 59       55      80   105          1     False
    ## 60      115      95    95          1     False
    ## 61       95      85   105          1     False
    ## 62      100      85    93          1     False
    ## 63       55      70    85          1     False
    ## 64       65      90   105          1     False
    ## 65       40      70   110          1     False
    ## 66       60     100    81          1     False
    ## 67       70     130    81          1     False
    ## 68       85      95    60          1     False
    ## 69      110      95    65          1     False
    ## 70      110      95   130          1     False
    ## 71       95     110    65          1     False
    ## 72       85      75    40          1     False
    ## 73      115      70    55          1     False
    ## 74       60      75   130          1     False
    ## 75       70      95   150          1     False
    ## 76       65     110    30          1     False
    ## 77       95     125    85          1      True
    ## 78      125      90   100          1      True
    ## 79      125      85    90          1      True
    ## 80       70      70    70          1     False
    ## 81      100     100    80          1     False
    ## 82      154      90   130          1      True
    ## 83      154     100   130          1      True
    ## 84      194     120   140          1      True
    ## 85      100     100   100          1     False
    ## 86       83     100    80          2     False
    ## 87      109      85   100          2     False
    ## 88       59      63    58          2     False
    ## 89       79      83    78          2     False
    ## 90       45      55    90          2     False
    ## 91       76      96    70          2     False
    ## 92       60      60    40          2     False
    ## 93       70      80   130          2     False
    ## 94       56      56    67          2     False
    ## 95       76      76    67          2     False
    ## 96       40      20    15          2     False
    ## 97       95      70    95          2     False
    ## 98       80      60    45          2     False
    ## 99      115      90    55          2     False
    ## 100     165     110    45          2     False
    ## 101      90     100    50          2     False
    ## 102      20      50    40          2     False
    ## 103      60      80    50          2     False
    ## 104      30      65    30          2     False
    ## 105      90     100    70          2     False
    ## 106      55      95   110          2     False
    ## 107     105      85    30          2     False
    ## 108      75      45    95          2     False
    ## 109      65      65    35          2     False
    ## 110     130      95   110          2     False
    ## 111      60     130    65          2     False
    ## 112     100     110    30          2     False
    ## 113      33      58    33          2     False
    ## 114      90      65    85          2     False
    ## 115      60      60    40          2     False
    ## 116      65      65    45          2     False
    ## 117      35      65    85          2     False
    ## 118      55      65    30          2     False
    ## 119      55      95    30          2     False
    ## 120      60      60    45          2     False
    ## 121      55      55    85          2     False
    ## 122      55      80    65          2     False
    ## 123      65     100    75          2     False
    ## 124      40      95    85          2     False
    ## 125      40     105    75          2     False
    ## 126      75      75    55          2     False
    ## 127      60      60    50          2     False
    ## 128     105      75    45          2     False
    ## 129      80     140    70          2     False
    ## 130      40      70    70          2     False
    ## 131     110      80    95          2     False
    ## 132     140      90   115          2     False
    ## 133      95      95    85          2     False
    ## 134      40      40    40          2     False
    ## 135      60      60    50          2     False
    ## 136     105      95    60          2     False
    ## 137      85      65    85          2     False
    ## 138      40      70   100          2     False
    ## 139      75     135    55          2     False
    ## 140     115     100   115          2      True
    ## 141      90      75   100          2      True
    ## 142      90     115    85          2      True
    ## 143      65      70    51          2     False
    ## 144      95     100    61          2     False
    ## 145      95     120    71          2     False
    ## 146      90     154   110          2      True
    ## 147     110     154    90          2      True
    ## 148     100     100   100          2     False
    ## 149     105      85   120          3     False
    ## 150     145      85   145          3     False
    ## 151     110      70    80          3     False
    ## 152     130      80   100          3     False
    ## 153      60      70    50          3     False
    ## 154      85      90    60          3     False
    ## 155      95     110    70          3     False
    ## 156      60      60    70          3     False
    ## 157      50      61   100          3     False
    ## 158      90     100    70          3     False
    ## 159      60      40    60          3     False
    ## 160      90      60    80          3     False
    ## 161     125     115    80          3     False
    ## 162     165     135   100          3     False
    ## 163      80      82    60          3     False
    ## 164      55      55    90          3     False
    ## 165      95      65   100          3     False
    ## 166      50      50   160          3     False
    ## 167      51      23    28          3     False
    ## 168      71      43    48          3     False
    ## 169      91      73    68          3     False
    ## 170      20      30    25          3     False
    ## 171      40      60    50          3     False
    ## 172      55      55    70          3     False
    ## 173      60      60    50          3     False
    ## 174      60      80    50          3     False
    ## 175     105      60   105          3     False
    ## 176     135      80   135          3     False
    ## 177      47      75    85          3     False
    ## 178      73      75    85          3     False
    ## 179      43      53    40          3     False
    ## 180      73      83    55          3     False
    ## 181      95      40    95          3     False
    ## 182     110      65   105          3     False
    ## 183      70      35    60          3     False
    ## 184      90      45    60          3     False
    ## 185     105      75    40          3     False
    ## 186     145     105    20          3     False
    ## 187      85      70    20          3     False
    ## 188      90     110    80          3     False
    ## 189      80      80   100          3     False
    ## 190     115      60    55          3     False
    ## 191      70     105    80          3     False
    ## 192     110     105    80          3     False
    ## 193      60      60    90          3     False
    ## 194     100      60    65          3     False
    ## 195      95      85    70          3     False
    ## 196      55      65    70          3     False
    ## 197      76      71    60          3     False
    ## 198      90      55    55          3     False
    ## 199      61      87    23          3     False
    ## 200      81     107    43          3     False
    ## 201      70      80    45          3     False
    ## 202     100     125    81          3     False
    ## 203      70      70    70          3     False
    ## 204      83      63    65          3     False
    ## 205      93      83    75          3     False
    ## 206      72      87    51          3     False
    ## 207      95      80    65          3     False
    ## 208      75      60    75          3     False
    ## 209     115      60   115          3     False
    ## 210      23      48    23          3     False
    ## 211      80      80    80          3     False
    ## 212     120      80   100          3     False
    ## 213      55      50    25          3     False
    ## 214      75      70    45          3     False
    ## 215      95      90    65          3     False
    ## 216      45      65    55          3     False
    ## 217      60      50    50          3     False
    ## 218     110      80   100          3     False
    ## 219     120      90   120          3     False
    ## 220      95      90    70          3     False
    ## 221     105     110   110          3     False
    ## 222      50     100    50          3      True
    ## 223     100     200    50          3      True
    ## 224      75     150    50          3      True
    ## 225     110     130   110          3      True
    ## 226     140     150   110          3      True
    ## 227     130     110   110          3      True
    ## 228     160     120   110          3      True
    ## 229     150     140    90          3      True
    ## 230     180     160    90          3      True
    ## 231     100      90    90          3      True
    ## 232     150      90    90          3      True
    ## 233     150      90    95          3      True
    ## 234     180     100   115          3      True
    ## 235     100     100   100          3      True
    ## 236      55      65    36          4     False
    ## 237      75      85    56          4     False
    ## 238      78      52    81          4     False
    ## 239     104      71   108          4     False
    ## 240      81      76    50          4     False
    ## 241     111     101    60          4     False
    ## 242      50      60   100          4     False
    ## 243      55      60    71          4     False
    ## 244      55      51    65          4     False
    ## 245      95      79    70          4     False
    ## 246      30      30    58          4     False
    ## 247      65      50    58          4     False
    ## 248      94      50    66          4     False
    ## 249      80     102    40          4     False
    ## 250      85      50   115          4     False
    ## 251      87      78    85          4     False
    ## 252      57      62    34          4     False
    ## 253      92      82    39          4     False
    ## 254      60      66   115          4     False
    ## 255      60      44    70          4     False
    ## 256      90      54    80          4     False
    ## 257      54      96   105          4     False
    ## 258      54      96   135          4     False
    ## 259     105      52    71          4     False
    ## 260      64      59   112          4     False
    ## 261      41      41    74          4     False
    ## 262      71      61    84          4     False
    ## 263      79     116    33          4     False
    ## 264      15      65    30          4     False
    ## 265      92      42    91          4     False
    ## 266      50      55    82          4     False
    ## 267      80      85   102          4     False
    ## 268     120      95    92          4     False
    ## 269      40      85     5          4     False
    ## 270     115      70    90          4     False
    ## 271     140      70   112          4     False
    ## 272      38      42    32          4     False
    ## 273      68      72    47          4     False
    ## 274      60      75    95          4     False
    ## 275      86      65    85          4     False
    ## 276      90      72    46          4     False
    ## 277      69      86    91          4     False
    ## 278      92      85    60          4     False
    ## 279     132     105    30          4     False
    ## 280      45      85   125          4     False
    ## 281     130      90    60          4     False
    ## 282      80      95    50          4     False
    ## 283      55      55    40          4     False
    ## 284     110      50    50          4     False
    ## 285      95      85    95          4     False
    ## 286     125      95    83          4     False
    ## 287     120     115    80          4     False
    ## 288     116      56    95          4     False
    ## 289      60      65    95          4     False
    ## 290     130      95    65          4     False
    ## 291      45      75    95          4     False
    ## 292      70      60    80          4     False
    ## 293     135      75    90          4     False
    ## 294      65     115    80          4     False
    ## 295      65     115   110          4     False
    ## 296      80      70   110          4     False
    ## 297      75     130    95          4      True
    ## 298     105     105    80          4      True
    ## 299     125      70   115          4      True
    ## 300     150     100    90          4      True
    ## 301     150     120   100          4      True
    ## 302     130     106    77          4      True
    ## 303      80     110   100          4      True
    ## 304     100     120    90          4      True
    ## 305     120     100    90          4      True
    ## 306      75     130    85          4     False
    ## 307      80      80    80          4     False
    ## 308     100     100   100          4     False
    ## 309     135      90   125          4      True
    ## 310     100     100   100          4      True
    ## 311     120      75   127          4      True
    ## 312     120     120   120          4      True
    ## 313     100     100   100          5      True
    ## 314      75      95   113          5     False
    ## 315      45      45    45          5     False
    ## 316      70      55    55          5     False
    ## 317     100      65    65          5     False
    ## 318      83      60    60          5     False
    ## 319     108      70    70          5     False
    ## 320      35      65    60          5     False
    ## 321      45      90    80          5     False
    ## 322      88      50   106          5     False
    ## 323      98      63   101          5     False
    ## 324      98      63   101          5     False
    ## 325      98      63   101          5     False
    ## 326      67      55    24          5     False
    ## 327     107      95    29          5     False
    ## 328      50      42    65          5     False
    ## 329      65      55    93          5     False
    ## 330      80      63   116          5     False
    ## 331      50      40    20          5     False
    ## 332      60      80    25          5     False
    ## 333      77      55   114          5     False
    ## 334      50      65    88          5     False
    ## 335      60      86    50          5     False
    ## 336      80     126    50          5     False
    ## 337      25      35    35          5     False
    ## 338      40      50    40          5     False
    ## 339      55      65    45          5     False
    ## 340      65      55    69          5     False
    ## 341      85      75    74          5     False
    ## 342      30      85    45          5     False
    ## 343      30      75    85          5     False
    ## 344      70      80    92          5     False
    ## 345     110      75    90          5     False
    ## 346      80      55    98          5     False
    ## 347      65      70    92          5     False
    ## 348      15      45    50          5     False
    ## 349      30      55    95          5     False
    ## 350     140     105    55          5     False
    ## 351     106      67    60          5     False
    ## 352      65      75    45          5     False
    ## 353      45     115    58          5     False
    ## 354     103      80    97          5     False
    ## 355      83      65    32          5     False
    ## 356     112      65   110          5     False
    ## 357      60      82    75          5     False
    ## 358      65      60   115          5     False
    ## 359      95     110    65          5     False
    ## 360     125      60    30          5     False
    ## 361     125      85    30          5     False
    ## 362      44      50    55          5     False
    ## 363      87      63    98          5     False
    ## 364     110      95    79          5     False
    ## 365      60      70    95          5     False
    ## 366      60     105    20          5     False
    ## 367      55      55    15          5     False
    ## 368      85      80    30          5     False
    ## 369      85     105    60          5     False
    ## 370      40      45    65          5     False
    ## 371      97      60   108          5     False
    ## 372      54     116    20          5     False
    ## 373      75      70    40          5     False
    ## 374     105      80    50          5     False
    ## 375     125      95    40          5     False
    ## 376      40      50    67          5     False
    ## 377      60      70    97          5     False
    ## 378      70      80    50          5     False
    ## 379      95     135   105          5     False
    ## 380     100      60   145          5     False
    ## 381      81      99    32          5     False
    ## 382      95      60   105          5     False
    ## 383      60      90    48          5     False
    ## 384      55      80    55          5     False
    ## 385      60      70    70          5     False
    ## 386      40      95    55          5     False
    ## 387      37      50    60          5     False
    ## 388      57      75    80          5     False
    ## 389      45      65    60          5     False
    ## 390      55      95    80          5     False
    ## 391     105      66    65          5     False
    ## 392      65      70    58          5     False
    ## 393     125      90    98          5     False
    ## 394     135     105   100          5     False
    ## 395      90      72   108          5      True
    ## 396      72      90   108          5      True
    ## 397      90     129   108          5      True
    ## 398     125      80   111          5      True
    ## 399     110      90   121          5      True
    ## 400     125      80   111          5      True
    ## 401     145      80   101          5      True
    ## 402     150     120    90          5      True
    ## 403     120     100    90          5      True
    ## 404     115      80   101          5      True
    ## 405     105      80    91          5      True
    ## 406     130      90    95          5      True
    ## 407     120      90    95          5      True
    ## 408     170     100    95          5      True
    ## 409     129      90   108          5     False
    ## 410     129      90   108          5     False
    ## 411     128     128    90          5     False
    ## 412      77      77   128          5     False
    ## 413     120      95    99          5     False
    ## 414      56      58    57          6     False
    ## 415      74      75    64          6     False
    ## 416     114     100   104          6     False
    ## 417     103      71   122          6     False
    ## 418      50      77    78          6     False
    ## 419      56      52    84          6     False
    ## 420      74      69   126          6     False
    ## 421      90      50    89          6     False
    ## 422      73      54    72          6     False
    ## 423     109      66   106          6     False
    ## 424     112     154    75          6     False
    ## 425      62      57    52          6     False
    ## 426      97      81    68          6     False
    ## 427      46      48    43          6     False
    ## 428      69      71    58          6     False
    ## 429      65      90   102          6     False
    ## 430      63      60    68          6     False
    ## 431      83      81   104          6     False
    ## 432      83      81   104          6     False
    ## 433      63      65    23          6     False
    ## 434      99      89    29          6     False
    ## 435      59      57    49          6     False
    ## 436      85      75    72          6     False
    ## 437      68      75    73          6     False
    ## 438      54      86    68          6     False
    ## 439      97     123    44          6     False
    ## 440     120      89    59          6     False
    ## 441     109      94   109          6     False
    ## 442      69      59    71          6     False
    ## 443      67      63    46          6     False
    ## 444      99      92    58          6     False
    ## 445     110     130    60          6     False
    ## 446      74      63   118          6     False
    ## 447      81      67   101          6     False
    ## 448      83     113    60          6     False
    ## 449     110     150    80          6     False
    ## 450      65      82    56          6     False
    ## 451      58      75    84          6     False
    ## 452      58      75    69          6     False
    ## 453      58      75    54          6     False
    ## 454      44      46    28          6     False
    ## 455      97      80   123          6     False
    ## 456     131      98    99          6      True
    ## 457     131      98    99          6      True
    ## 458      81      95    95          6      True
    ## 459     150     130    70          6      True
    ## 460     170     130    80          6      True
    ## 461     130      90    70          6      True
