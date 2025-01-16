Agri Swarm Build Guide
======================

.. toctree::
   :maxdepth: 2
   :hidden:

   Introduction <self>
   changelog

.. toctree::
   :maxdepth: 2
   :caption: Getting Started
   :hidden:

   guide
   main

.. toctree::
   :maxdepth: 2
   :caption: Build Hardware
   :hidden:
   
   hardware_build
   parts_selection
   
.. toctree::
   :maxdepth: 2
   :caption: Install Software
   :hidden:

   software_install
   serv_soft_install
   quad_soft_install
   setup_realsense

.. toctree::
   :maxdepth: 2
   :caption: Calibration
   :hidden:

   vins_calib
   ap_calib

.. toctree::
   :maxdepth: 2
   :caption: Machine Learning
   :hidden:

   detector
   pose_estimate

.. toctree::
   :maxdepth: 2
   :caption: For Developers
   :hidden:

   algo_system

本プロジェクトについて
-------
地理的条件が悪く斜面地が多い「中山間地域」に特化したロボット開発は、技術的困難を伴うため、未だ実用化に及んでいない。一方、受粉や農薬散布だけを目的としたロボットシステムにはいくつかの前例が存在する。しかしこれらはいずれも自己位置推定と環境地図作成に関して高度に整備された屋内環境（ハウス栽培）を想定しており、屋外の不整地環境においては適用が難しい。また、ほとんどの既存事例は大型ドローンを想定しており、棚を利用した果樹園において、棚の下側から散布を行う作業にとっては最適ではない。

上記を踏まえ本プロジェクトでは、中山間地域での使用を想定した、高度な農作業を代替する小型自律ドローン群システムを開発する。本プロジェクトの目標は、不整地環境における果樹の棚下からの人手による受粉作業を、小型自律ドローン群によって代替することである。

本システムでは、「モーションキャプチャ等を用いずに、カメラ画像のみから自己位置推定を行う手法（Visual Inertial Odometry）」「機械学習に基づき花の姿勢を認識する画像認識技術」「草木や果樹棚、他ドローンとの衝突を避けながらドローンを群制御する制御プランナ」等により、未知の不整地環境でも作業を可能にする。さらに、棚下に潜り込んで、葉面や花弁に対する直接的な散布を行うことができる機体も開発する。

本システムが農業従事者にとって低コストで逐次投入可能な農業支援ロボットとなることで、高齢化が進んでいる一次産業を自動化によって支援し、中山間地域や果樹園等の不整地における農業の生産性と持続可能性を大きく向上させることが期待できる。

`未踏IT人材発掘・育成事業：2024年度採択プロジェクト概要（有田・和田PJ） <https://www.ipa.go.jp/jinzai/mitou/it/2024/gaiyou-oc-1.html>`_

開発者
-------
- .. image:: https://pbs.twimg.com/profile_images/1798038835533918209/yRZvN61T_400x400.jpg
     :alt: Tomoki Arita
     :width: 60
     :height: 60

  `有田朋樹（Tomoki Arita） <https://x.com/allegory_write>`_

- .. image:: https://yuiga.dev/images/icon.png
     :alt: Yuiga Wada
     :width: 60
     :height: 60

  `和田唯我（Yuiga Wada） <https://yuiga.dev>`_


前提環境
--------
ドローン本体とは別に、以下環境を用意したPCが必要です。

==================================  ========================
Item                                Version
==================================  ========================
OS                                  Ubuntu 20.04
ROS                                 Noetic
==================================  ========================