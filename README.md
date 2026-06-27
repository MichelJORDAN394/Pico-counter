# Pico-counter
Compteur volumétrique pour eau à base de Raspberry Pico W

L'objectif de ce développement est de réaliser un compteur volumétrique pour un système d'arrosage automatique sous Domoticz de façon à surveiller le bon fonctionnement et relever la consommation.
Le comptage est assuré par un dispositif à turbine et capeur à effet Hall, pour un diamètre de 1/2" le coefficient de comptage est de 660 impulsions / l.
Le Raspberry Pico W assure l'alimentation 5V du capteur à effet Hall, le comptage des impulsions et la transmission des mesures via une page Web rafraîchie automatiquement tous les 20s.
Un diviseur de tension ramène la tension de sortie à 3V, compatible avec les niveaux d'entrée du Pico.
Le logiciel est développé en MicroPython. L'horodatage des consommations nécessite la synchronisation de l'horloge interne sur un serveur de temps type NTP. Les consultations journalières sont transmises par mail et enregistrées dans un fichier de log.
Par sécurité, le logiciel est réinitialisé tous les jours à 23H23.
Deux solutions sont possibles pour le comptage, soit compter les interruptions génèrees par un front descendant soit utiliser les impulsions comme horloge d'un des PWM du Pico.

