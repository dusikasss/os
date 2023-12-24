<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts%20make&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository%20update&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ucanaraher><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3694</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/himubavesu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>95</td><td align=right>3707</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=#orangepizeroplus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/agipuvuker><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>852</td><td align=right>2665</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.7.0-rc6-edge-sunxi64</td><td align=center><a href=#orangepizeroplus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/jexofapave><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>2612</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=#rockpi-e><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/idahipogab><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>3407</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.8-edge-rockchip64</td><td align=center><a href=#rockpi-e><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/wirukewowo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>898</td><td align=right>3302</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/gunisejoyi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>4182</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.7.0-rc6-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/rivatepadu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>4221</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=center>6.1.69-legacy-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/natogezula><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>614</td><td align=right>2668</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.6.8-current-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/apibojoneb><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>830</td><td align=right>2132</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ecihabilaj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5378</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/divebusaha><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>889</td><td align=right>5342</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/efaralejen><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>6837</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/akegadisut><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>88</td><td align=right>3786</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/esujamejas><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3785</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#orangepi5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/egabeluzem><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>15872</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>6.1.68-current-rockchip</td><td align=center><a href=#tinkerboard><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/barazicido><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>853</td><td align=right>4934</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.6.8-current-sunxi</td><td align=center><a href=#orangepizero><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/moroqubevi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2569</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi3-lts href=#orangepi3-lts>Orange Pi 3 LTS</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi3-lts href=#orangepi3-lts>Orange Pi 3 LTS</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/nozewonuxa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>798</td><td align=right>6126</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/hexeliyaco><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>888</td><td align=right>6167</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uqijumacan><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>832</td><td align=right>3022</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.7.0-rc6-edge-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ehoyiheweb><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>830</td><td align=right>3290</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/pogozoroni><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>950</td><td align=right>9525</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ricifawava><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>9457</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/vosocuhemi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>4263</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.7.0-rc6-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ahijihepaw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>4279</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepioneplus href=#orangepioneplus>Orange Pi One+</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/sipekunasu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>877</td><td align=right>4143</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/omoroyecut><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>950</td><td align=right>6654</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.8-edge-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/qixipozexa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>889</td><td align=right>6696</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>5.4.180-legacy-meson-s4t7</td><td align=center><a href=#khadas-vim4><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/axovayoriz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>8021</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#bananapim5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/munaqucupu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5497</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#bananapim5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/dohokaqawi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5532</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/udevihijan><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>3238</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/axexiqoqaj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5658</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/vugatobeci><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5613</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/kagihajufi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>3907</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ziruwefige><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>881</td><td align=right>4050</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.69-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/usowovucuz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2697</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc6-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/awosiwanot><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2604</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>n/a</td><td align=center><a href=#orangepi5-plus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>n/a</td><td align=center><a href=#bigtreetech-cb1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi-r1plus-lts href=#orangepi-r1plus-lts>Orange Pi R1 Plus LTS</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=#orangepi-r1plus-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/iqenamiyos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>443</td><td align=right>1801</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>5.15.145-legacy-x86</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/esajofufom><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>868</td><td align=right>4763</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.1.69-current-x86</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/wokuyewofi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>4738</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.6.8-edge-x86</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/makodeziki><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>894</td><td align=right>4750</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.1.69-current-meson64</td><td align=center><a href=#odroidn2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xalehiwezo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>8966</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.8-edge-meson64</td><td align=center><a href=#odroidn2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xaboluraxi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>930</td><td align=right>8965</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/utazamimix><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>3457</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>6.6.8-edge-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/girisokaze><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>3389</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim1s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.1.69-current-arm64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/gepazonira><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>883</td><td align=right>3764</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.6.8-edge-arm64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/afenoxehab><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>3711</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/nizasimeni><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>9302</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gexuqosaqi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>9223</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=#odroidm1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/izuhuviguy><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>613</td><td align=right>5272</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=#odroidm1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ayumejaqud><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>661</td><td align=right>5265</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.1.69-current-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gopeleyebe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>980</td><td align=right>6476</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.8-edge-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ezokobiriw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>6457</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.69-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/asoxozahof><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5761</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc6-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uyugiriros><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5821</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.1.69-current-imx6</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/yegasacafi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>313</td><td align=right>2375</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=center>n/a</td><td align=center><a href=#orangepi4-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=center>n/a</td><td align=center><a href=#orangepi4-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ikurureras><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>901</td><td align=right>15660</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ikurureras><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>901</td><td align=right>15660</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.1.69-legacy-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/edatocodoq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>74</td><td align=right>3914</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.6.8-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ayujejonum><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>85</td><td align=right>3807</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.7.0-rc6-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/reyuqekafo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>77</td><td align=right>3970</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.6.8-current-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/osuwovacos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>35</td><td align=right>2606</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.7.0-rc6-edge-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/getayodejo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>39</td><td align=right>2643</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
