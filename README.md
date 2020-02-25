Simulateur apocalyptique du système de retraites
================================================

## Introduction 
------------
Ce simulateur du système des retraites françaises a pour objectif de donner une estimation fiable et non partisane du solde du système des retraites françaises. A l'heure actuelle le Conseil d'Orientation des Retraites (COR) mets déjà à disposition du public un simulateur du système des retraites françaises sur son site. Cependant ce simulateur souffre de plusieurs écueils:
### concernant la légitimité du conseil d'orientation des retraites

En effet le conseil d'orientation des retraites est placé sous la tutelle du gouvernement. Pour certains cela présente un conflit d'intérêts qui menace l'objectivité des rapports fournis par le conseil d'orientation des retraites.

### concernant les hypothèses de calcul 
 
 En effet les hypothèses de croissance socio-économiques sont celles que le Trésor français communique à Bruxelles, pour les trois ou cinq prochaines années. Au-delà, à moyen et long terme, les prévisions socio-économiques sont fantaisistes puisqu'elles elles ne tiennent pas du tout compte de l'effondrement systémic global à venir (Apocalypse). 

Je développe donc un nouveau simulateur qui est totalement transparent et qui tient compte de l'Apocalypse. 
Quand il sera finalisé ce simulateur permettra ainsi de mieux communiquer sur la problèmatique des retraites en France auprès du public. En effet c'est un projet open-source donc n'importe quel hérétique est libre de fouiner et pourquoi pas d'y contribuer, après s'être converti à la collapsologie.
De plus il offrira à la France un outil d'aide à la décision qui lui permet de mieux orienter ses politiques publiques. En effet il lui permettra de faire des choix plus pertinents concernant la gestion des finances publiques, au-delà des idéologies partisanes des différents parties prenantes du système des retraites françaises, en tenant compte de l'avis des collapsologues, Dieu merci ! 

.. _`données de projection du COR`: https://www.cor-retraites.fr/simulateur/fileProjection.json
.. _`documentation technique fournie par le COR`: https://www.cor-retraites.fr/simulateur/img/pdf/Documentation_technique_vf.pdf
.. _`SimulateurRetraites.py`: https://github.com/brunoscherrer/retraites/blob/master/retraites/SimulateurRetraites.py
.. _`demo.py`: https://github.com/brunoscherrer/retraites/blob/master/demo.py
.. _`fig`: https://github.com/brunoscherrer/retraites/blob/master/fig

## Projet
------------

Le COR (conseil d'orientation des retraites) a mis en ligne un simulateur pour permettre aux citoyens de simuler les effets macroscopiques des grandes lignes d'une réforme des retraites.
Ce projet vise a reproduire les résultats et à ajouter un certain nombre de fonctionnalités utiles, comme celui de proposer de concevoir une réforme à prestation définie (ex: calcul automatique des cotisations sociales pour avoir un système équilibré financièrement avec un certain niveau de vie pour les retraités et un age de départ fixé a priori).

On utilise les `données de projection du COR`_ et on se base sur la `documentation technique fournie par le COR`_.



## Installation
------------

Dépendances
...........

Les dépendances sont :

- Python >= 3.4
- `numpy <http://www.numpy.org>`_ >= 0.10
- `matplotlib <https://matplotlib.org>`_ >= 1.5.3
- `scipy <https://www.scipy.org/>`_ >= 1.0.0

Installation
............

L'installation se fait avec les commandes suivantes::

    git clone https://github.com/brunoscherrer/retraites.git
    cd retraites
    python setup.py install

## Exemple
-------

La classe ``SimulateurRetraites`` implémente le simulateur qui évalue les résultats 
du modèle en fonction des hypothèses (conjoncture) et des leviers. 
Cette classe implémente plusieurs stratégie de pilotage, la plus simple étant 
le pilotage du COR qui est évaluée grâce à la méthode ``pilotageCOR``. 
 
La méthode ``pilotageCOR`` retourne une instance de la classe ``SimulateurAnalyse``. 
Cette classe permet de produire les graphiques pour réaliser l'analyse 
des résultats. 

.. code-block:: python

	from retraites.SimulateurRetraites import SimulateurRetraites
	simulateur = SimulateurRetraites()
	analyse = simulateur.pilotageCOR()

La méthode ``graphiques`` permet de produire les graphiques standard dans l'analyse 
d'une stratégie de pilotage. 

.. code-block:: python

	analyse.dessineSimulation()

Le code précédent produit le graphique suivant. 

.. image::  fig/cor.jpg

## Documentation
-------------

.. _`doc`: https://github.com/brunoscherrer/retraites/blob/master/doc
.. _`index`: https://github.com/brunoscherrer/retraites/blob/master/index.ipynb
.. _`simulationCOR`: https://github.com/brunoscherrer/retraites/blob/master/doc/simulation-COR-juin-2019.ipynb
.. _`documentationModele`: https://github.com/brunoscherrer/retraites/blob/master/doc/Description-du-composant-retraites.ipynb
.. _`reformes`: https://github.com/brunoscherrer/retraites/blob/master/doc/reformes.ipynb
.. _`reformes2`: https://github.com/brunoscherrer/retraites/blob/master/doc/reformes2.ipynb
.. _`articleEI`: https://github.com/brunoscherrer/retraites/blob/master/doc/Article4/article4-analyse-impact.pdf
.. _`pilotagesPossibles`: https://github.com/brunoscherrer/retraites/blob/master/doc/pilotages-possibles.ipynb
.. _`naissanceRetraiteMort`: https://github.com/brunoscherrer/retraites/blob/master/doc/Calcule-naissance-retraite-mort.ipynb

La description du modèle mathématique est donnée dans `documentationModele`_. 

Un exemple complet est présenté dans le fichier `index`_.

D'autres exemples sont présentés dans le répertoire `doc`_ :

- `simulationCOR`_ : une simulation du rapport du COR de Juin 2019
- `pilotagesPossibles`_ : un exemple de tous les pilotages possibles
- `reformes`_ : une simulation fondée sur l'étude d'impact
- `reformes2`_ : une simulation fondée sur une modification de l'étude d'impact, avec augmentation des cotisations
- `naissanceRetraiteMort`_ : une analyse génération par génération de la vie : naissance, retraite et mort

.. _`simulationEtudeImpact`: https://github.com/brunoscherrer/retraites/blob/master/doc/simulation-Etude-Impact.ipynb
.. _`possiblesEtudeImpact`: https://github.com/brunoscherrer/retraites/blob/master/doc/reforme-Macron-age-vs-pensions.ipynb
.. _`etudeImpactAge`: https://github.com/brunoscherrer/retraites/blob/master/doc/simulation-Etude-Impact-analyse-age.ipynb
.. _`etudeImpactDepenses`: https://github.com/brunoscherrer/retraites/blob/master/doc/simulation-Etude-Impact-budget.ipynb
.. _`etudeImpactAgePensions`: https://github.com/brunoscherrer/retraites/blob/master/doc/reforme-Macron-age-vs-pensions.ipynb
.. _`etudeImpactPensionAnnuelle`: https://github.com/brunoscherrer/retraites/blob/master/doc/CalculePensionAnnuelle/simulation-pension-annuelle.ipynb
.. _`etudeImpactNumerisation`: https://github.com/brunoscherrer/retraites/blob/master/doc/DigitalisationEI/Numerisation-Etude-Impact.ipynb

Une analyse détaillée de l'étude d'impact de Janvier 2020 :

- `simulationEtudeImpact`_ : une simulation de l'étude d'impact de Janvier 2020
- `possiblesEtudeImpact`_ : une représentation des trajectoires possibles dans le cadre de l'étude d'impact de Janvier 2020
- `etudeImpactAge`_ : une analyse de la trajectoire d'âge de l'étude d'impact
- `etudeImpactDepenses`_ : une analyse de la trajectoire de dépenses de l'étude d'impact
- `etudeImpactAgePensions`_ : une analyse de l'étude d'impact en fonction de l'âge et du niveau de pensions
- `etudeImpactPensionAnnuelle`_ : une analyse de l'étude d'impact en termes de pension annuelle
- `etudeImpactNumerisation`_ : une numérisation de données de l'étude d'impact à partir des graphiques

Une analyse détaillée de ce que l'étude d'impact ne dit pas est présentée dans `articleEI`_.

|Python|_ |License|_

.. image:: https://circleci.com/gh/mbaudin47/retraites.svg?style=svg
    :target: https://circleci.com/gh/mbaudin47/retraites

.. image:: https://mybinder.org/badge_logo.svg
 :target: https://mybinder.org/v2/gh/brunoscherrer/retraites/master?filepath=index.ipynb

.. |Python| image:: https://img.shields.io/badge/python-3.7-blue.svg
.. _Python: https://python.org

.. |License| image:: https://img.shields.io/github/license/brunoscherrer/retraites
.. _License: https://opensource.org/licenses/gpl-license

