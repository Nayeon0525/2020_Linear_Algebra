# [Physics/Assignment] Centrifugal Force (원심력)
-------------------
> ### 문제) 링 형태의 우주 정거장이 원의 중심으로 회전을 한다면, Centrifugal Force로 인공 중력을 만들 수 있다. 이 때 angular speed가 20rpm이라 할 때, 지구의 3/2에 해당하는 인공 중력을 만들려면 우주 정거장의 반경이 얼마나 되어야 하는지 구하라. (중력가속도는 $10m/s^2$)   

* 각속도
$$angular speed = 20rpm = \frac{2\pi \times 20}{60 sec} = \frac{40\pi}{60 sec} = \frac{2\pi}{3 sec}$$   
>  rpm은 1분당 회전수로 20rpm은 1분당 20회 회전한다. 따라서 60초 동안 40$\pi$만큼 회전한다.
* 접선속도
$$tangential speed = r\omega = r\frac{2\pi}{3}$$  

생성할 인공중력의 크기가 지구의 3/2이므로 인공중력의 크기는 
 $$\frac{3}{2}mg = 15m$$
(m은 질량)

$$Centripetal Force = \frac{mv^2}{r}$$

구심력 (Centripetal Force) = 원심력 (Centrifugal Force) 이므로 구심력을 이용해 풀 수 있다.

> 구심력 = 생성할 인공 중력

$$\frac{mv^2}{r} = 15m$$
$$\frac{v^2}{r} = 15$$
$$\frac{(r\frac{2\pi}{3} )^2}{r} = 15$$
$$\frac{r^2\frac{4\pi^2}{9}}{r} = 15$$
$${r\frac{4\pi^2}{9}} = 15$$
$${r=\frac{9}{4\pi^2}} \times15 = 3.42$$
(소숫점 셋째자리에서 반올림)

$\therefore$ 구하는 우주 정거장의 반경은 약 3.42m 이다. 
