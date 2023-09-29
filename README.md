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


# What does this project do?

- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Builds [nightly](https://github.com/armbian/os/releases) and [stable images](https://www.armbian.com/download/) and uploads them to Armbian CDN
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases

# How to enable images?

If you want to enable build configurations, edit [yaml config files](userpatches) and send a pull request. ([example](https://github.com/armbian/os/commit/70f3be4f3d96e9a301be751d3ecf3a24394356f9) )

# When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after **artifacts cache update** is done succesfully.
- Smoke tests starts **manually**.
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

# Latest smoke tests results:

- installs kernels, dtb and headers that are defined and supported by the board
- runs network and computing performance tests (7z benchmark)
- store armbianmonitor logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=left><b>Logs</b></td><td align=right><b>Branch</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/yixayofavi</td><td align=right>legacy</td><td align=right>531</td><td align=right>2681</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/ibiruritep</td><td align=right>legacy</td><td align=right>540</td><td align=right>2669</td><td align=right>stable</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/xibiciwipo</td><td align=right>current</td><td align=right>594</td><td align=right>2679</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/asuvipuqig</td><td align=right>current</td><td align=right>599</td><td align=right>2698</td><td align=right>stable</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/kakalotoje</td><td align=right>edge</td><td align=right>552</td><td align=right>2680</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=left>https://paste.armbian.com/padabizimo</td><td align=right>edge</td><td align=right>559</td><td align=right>2671</td><td align=right>stable</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=left>https://paste.armbian.com/olumiririr</td><td align=right>current</td><td align=right>87</td><td align=right>3803</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=left>https://paste.armbian.com/upucutihak</td><td align=right>current</td><td align=right>91</td><td align=right>3804</td><td align=right>stable</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=left>https://paste.armbian.com/abizemuder</td><td align=right>edge</td><td align=right>63</td><td align=right>3805</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=left>https://paste.armbian.com/hemekecuru</td><td align=right>edge</td><td align=right>90</td><td align=right>3806</td><td align=right>stable</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>ODROID M1</a></td><td align=left>https://paste.armbian.com/herafuqayo</td><td align=right>edge</td><td align=right>895</td><td align=right>5363</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>ODROID M1</a></td><td align=left>https://paste.armbian.com/utorezacez</td><td align=right>edge</td><td align=right>880</td><td align=right>5354</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=left>https://paste.armbian.com/onuquwopal</td><td align=right>legacy</td><td align=right>940</td><td align=right>15853</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=left>https://paste.armbian.com/oqofepaxup</td><td align=right>legacy</td><td align=right>890</td><td align=right>15667</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=left>https://paste.armbian.com/oqofepaxup</td><td align=right>edge</td><td align=right>890</td><td align=right>15667</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=left>https://paste.armbian.com/oqofepaxup</td><td align=right>edge</td><td align=right>890</td><td align=right>15667</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=left>https://paste.armbian.com/exorumajud</td><td align=right>current</td><td align=right>939</td><td align=right>3507</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=left>https://paste.armbian.com/aqotutemit</td><td align=right>current</td><td align=right>881</td><td align=right>3184</td><td align=right>stable</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=left>https://paste.armbian.com/gukobijoko</td><td align=right>edge</td><td align=right>838</td><td align=right>2922</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=left>https://paste.armbian.com/ajuxohared</td><td align=right>edge</td><td align=right>840</td><td align=right>2819</td><td align=right>stable</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=left>https://paste.armbian.com/qijafetodu</td><td align=right>current</td><td align=right>789</td><td align=right>2704</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=left>https://paste.armbian.com/ezegoyuwap</td><td align=right>current</td><td align=right>789</td><td align=right>2716</td><td align=right>stable</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=left>https://paste.armbian.com/umifurazay</td><td align=right>current</td><td align=right>788</td><td align=right>4197</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=left>https://paste.armbian.com/ivehixanuz</td><td align=right>current</td><td align=right>862</td><td align=right>4096</td><td align=right>stable</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=left>https://paste.armbian.com/ozupodovuk</td><td align=right>edge</td><td align=right>821</td><td align=right>4065</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=left>https://paste.armbian.com/ozexuhodak</td><td align=right>edge</td><td align=right>807</td><td align=right>4068</td><td align=right>stable</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/pitepikovo</td><td align=right>legacy</td><td align=right>850</td><td align=right>4830</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/ucafivorew</td><td align=right>legacy</td><td align=right>760</td><td align=right>4812</td><td align=right>stable</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/ozapikarom</td><td align=right>current</td><td align=right>850</td><td align=right>4812</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/ujemabamay</td><td align=right>current</td><td align=right>827</td><td align=right>4771</td><td align=right>stable</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/witupegeyo</td><td align=right>edge</td><td align=right>868</td><td align=right>4737</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=left>https://paste.armbian.com/serucizaku</td><td align=right>edge</td><td align=right>862</td><td align=right>4737</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=left>https://paste.armbian.com/suficusawe</td><td align=right>current</td><td align=right>0</td><td align=right>9498</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=left>https://paste.armbian.com/ipahezoheh</td><td align=right>current</td><td align=right>260</td><td align=right>9251</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=left>https://paste.armbian.com/isimivasah</td><td align=right>edge</td><td align=right>870</td><td align=right>9314</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=left>https://paste.armbian.com/ijebilequb</td><td align=right>edge</td><td align=right>890</td><td align=right>9325</td><td align=right>stable</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=left>https://paste.armbian.com/ruqukiburo</td><td align=right>current</td><td align=right>900</td><td align=right>3407</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=left>https://paste.armbian.com/ifehihigiw</td><td align=right>current</td><td align=right>87</td><td align=right>3378</td><td align=right>stable</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=left>https://paste.armbian.com/iyikokufur</td><td align=right>edge</td><td align=right>95</td><td align=right>3314</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=left>https://paste.armbian.com/silobuvica</td><td align=right>edge</td><td align=right>89</td><td align=right>3383</td><td align=right>stable</td></tr><tr><td align="left"><a id=rockpi-4b href=#rockpi-4b>Rockpi 4B</a></td><td align=left>https://paste.armbian.com/higawibipu</td><td align=right>current</td><td align=right>790</td><td align=right>6395</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-4b href=#rockpi-4b>Rockpi 4B</a></td><td align=left>https://paste.armbian.com/pomibulasu</td><td align=right>current</td><td align=right>820</td><td align=right>6194</td><td align=right>stable</td></tr><tr><td align="left"><a id=rockpi-4b href=#rockpi-4b>Rockpi 4B</a></td><td align=left>https://paste.armbian.com/imuceyubar</td><td align=right>edge</td><td align=right>880</td><td align=right>6002</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-4b href=#rockpi-4b>Rockpi 4B</a></td><td align=left>https://paste.armbian.com/icavewalus</td><td align=right>edge</td><td align=right>860</td><td align=right>5998</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=left>https://paste.armbian.com/ayayubabax</td><td align=right>current</td><td align=right>882</td><td align=right>6151</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=left>https://paste.armbian.com/ujifovovaz</td><td align=right>current</td><td align=right>895</td><td align=right>6234</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=left>https://paste.armbian.com/qepihipeme</td><td align=right>edge</td><td align=right>840</td><td align=right>6137</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=left>https://paste.armbian.com/ikifobusum</td><td align=right>edge</td><td align=right>950</td><td align=right>6159</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=left>https://paste.armbian.com/icumodahoy</td><td align=right>legacy</td><td align=right>89</td><td align=right>2704</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=left>https://paste.armbian.com/tudoguhoya</td><td align=right>legacy</td><td align=right>91</td><td align=right>2614</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=left>https://paste.armbian.com/zomaxibija</td><td align=right>current</td><td align=right>835</td><td align=right>3139</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=left>https://paste.armbian.com/vurekolonu</td><td align=right>current</td><td align=right>841</td><td align=right>3149</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=left>https://paste.armbian.com/cenufivuje</td><td align=right>edge</td><td align=right>810</td><td align=right>3045</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=left>https://paste.armbian.com/fofadepoho</td><td align=right>edge</td><td align=right>840</td><td align=right>3102</td><td align=right>stable</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=left>https://paste.armbian.com/alofokaluk</td><td align=right>current</td><td align=right>819</td><td align=right>5928</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=left>https://paste.armbian.com/ujutivikez</td><td align=right>current</td><td align=right>880</td><td align=right>5665</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=left>https://paste.armbian.com/pugunayoti</td><td align=right>edge</td><td align=right>890</td><td align=right>5550</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=left>https://paste.armbian.com/faninavida</td><td align=right>edge</td><td align=right>860</td><td align=right>5492</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=left>https://paste.armbian.com/jowoqajece</td><td align=right>current</td><td align=right>870</td><td align=right>3961</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=left>https://paste.armbian.com/seqabazeta</td><td align=right>current</td><td align=right>870</td><td align=right>3957</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=left>https://paste.armbian.com/upiveruwag</td><td align=right>edge</td><td align=right>829</td><td align=right>4008</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=left>https://paste.armbian.com/duzugiwavo</td><td align=right>edge</td><td align=right>871</td><td align=right>4008</td><td align=right>stable</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=left>https://paste.armbian.com/udizekatoq</td><td align=right>current</td><td align=right>800</td><td align=right>5616</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=left>https://paste.armbian.com/fucabireja</td><td align=right>current</td><td align=right>870</td><td align=right>5674</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=left>https://paste.armbian.com/umikonowec</td><td align=right>edge</td><td align=right>890</td><td align=right>5642</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=left>https://paste.armbian.com/ucixelahes</td><td align=right>edge</td><td align=right>850</td><td align=right>5641</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/okutozigam</td><td align=right>legacy</td><td align=right>90</td><td align=right>2113</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/olilenonak</td><td align=right>legacy</td><td align=right>90</td><td align=right>2110</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/dugamiyoxo</td><td align=right>current</td><td align=right>90</td><td align=right>2354</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/zogokuxoxo</td><td align=right>current</td><td align=right>90</td><td align=right>2251</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/guqasemipa</td><td align=right>edge</td><td align=right>90</td><td align=right>2056</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=left>https://paste.armbian.com/owijuwocuz</td><td align=right>edge</td><td align=right>89</td><td align=right>2009</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=left>https://paste.armbian.com/kohifiguwi</td><td align=right>current</td><td align=right>90</td><td align=right>2681</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=left>https://paste.armbian.com/yajukaliqe</td><td align=right>current</td><td align=right>90</td><td align=right>2731</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=left>https://paste.armbian.com/imimokozaz</td><td align=right>edge</td><td align=right>90</td><td align=right>2187</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=left>https://paste.armbian.com/nekeweduwe</td><td align=right>edge</td><td align=right>89</td><td align=right>2230</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=left>https://paste.armbian.com/uzodurequm</td><td align=right>current</td><td align=right>852</td><td align=right>2558</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=left>https://paste.armbian.com/viseloduce</td><td align=right>current</td><td align=right>836</td><td align=right>2543</td><td align=right>stable</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=left>https://paste.armbian.com/hojakiwixu</td><td align=right>edge</td><td align=right>843</td><td align=right>2673</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=left>https://paste.armbian.com/wexazofodo</td><td align=right>edge</td><td align=right>851</td><td align=right>2542</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=left>https://paste.armbian.com/elaqajepuy</td><td align=right>current</td><td align=right>853</td><td align=right>8922</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=left>https://paste.armbian.com/dupixacoro</td><td align=right>current</td><td align=right>860</td><td align=right>8914</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=left>https://paste.armbian.com/zicejopafe</td><td align=right>edge</td><td align=right>950</td><td align=right>8965</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=left>https://paste.armbian.com/qoyadunawe</td><td align=right>edge</td><td align=right>880</td><td align=right>8651</td><td align=right>stable</td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=left>https://paste.armbian.com/nosaxuzegi</td><td align=right>current</td><td align=right>880</td><td align=right>9389</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=left>https://paste.armbian.com/uyacuvukux</td><td align=right>current</td><td align=right>820</td><td align=right>8877</td><td align=right>stable</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=left>https://paste.armbian.com/ukerikaxag</td><td align=right>edge</td><td align=right>820</td><td align=right>8622</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=left>https://paste.armbian.com/ikapiwilem</td><td align=right>edge</td><td align=right>890</td><td align=right>8280</td><td align=right>stable</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=left>n/a</td><td align=right>current</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=left>n/a</td><td align=right>edge</td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=left>https://paste.armbian.com/alofizimut</td><td align=right>current</td><td align=right>327</td><td align=right>2368</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=left>https://paste.armbian.com/ogibibelip</td><td align=right>current</td><td align=right>372</td><td align=right>2378</td><td align=right>stable</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=left>https://paste.armbian.com/yavifehuwo</td><td align=right>edge</td><td align=right>321</td><td align=right>2368</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=left>https://paste.armbian.com/niyaqurayi</td><td align=right>edge</td><td align=right>358</td><td align=right>2365</td><td align=right>stable</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=left>https://paste.armbian.com/zifokanave</td><td align=right>current</td><td align=right>819</td><td align=right>3468</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=left>https://paste.armbian.com/xeginizocu</td><td align=right>current</td><td align=right>820</td><td align=right>3451</td><td align=right>stable</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=left>https://paste.armbian.com/arebepagum</td><td align=right>edge</td><td align=right>900</td><td align=right>3372</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=left>https://paste.armbian.com/ojuhiwigev</td><td align=right>edge</td><td align=right>810</td><td align=right>3444</td><td align=right>stable</td></tr><tr><td align="left"><a id=rock-5b href=#rock-5b>Rock 5B</a></td><td align=left>https://paste.armbian.com/yunufiseze</td><td align=right>legacy</td><td align=right>2320</td><td align=right>15550</td><td align=right>beta</td></tr><tr><td align="left"><a id=rock-5b href=#rock-5b>Rock 5B</a></td><td align=left>https://paste.armbian.com/haqesucusu</td><td align=right>legacy</td><td align=right>2249</td><td align=right>15604</td><td align=right>stable</td></tr><tr><td align="left"><a id=khadas-edge2 href=#khadas-edge2>Khadas Edge2</a></td><td align=left>https://paste.armbian.com/ataqefohom</td><td align=right>legacy</td><td align=right>75</td><td align=right>15382</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-edge2 href=#khadas-edge2>Khadas Edge2</a></td><td align=left>https://paste.armbian.com/ucumilozon</td><td align=right>legacy</td><td align=right>70</td><td align=right>15366</td><td align=right>stable</td></tr></table>
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

## OS download

- [Download](https://www.armbian.com/download/)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on Twitter, [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)

## License

This software is published under the GPL-2.0 License license.
