# 環境作成方法

repo init -u https://github.com/AGLExport/trial_integration.git -b working -m host.xml  
  
TODO:  
repo init -u https://github.com/AGLExport/trial_integration.git -b working -m guest-xxx.xml  


Renesas R-Car bsp 4.7を使用しているので、それのgfxセットアップ手順を実行する


hostの作業中イメージのコンフィグは、リポジトリの中に置いてあるので  
git clone https://github.com/AGLExport/trial_integration.git  
でもってきて、host confの中のコンフィグを使用する

host最小構成(スターティングポイント) でもまだでかい

bitbake qm-image-minimal

host pipewire構成インテグレーション

bitbake host-image-pipewire



