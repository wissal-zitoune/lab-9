# lab-9
<img width="243" height="181" alt="1" src="https://github.com/user-attachments/assets/f17158d2-45f5-4708-bd66-41a66fbd44e5" />

## Connexion Drozer

```bash
adb forward tcp:31415 tcp:31415
drozer console connect --server 127.0.0.1:31415
```
## Cartographie de la surface d’attaque

```bash
run app.package.attacksurface com.android.insecurebankv2
```
<img width="563" height="205" alt="2" src="https://github.com/user-attachments/assets/e13af83e-3ff3-4104-9b1a-17ebeb978c93" />
<img width="526" height="102" alt="Q3" src="https://github.com/user-attachments/assets/b8fc33bd-e7e9-4434-99d6-ebdf75b8aa79" />
<img width="690" height="236" alt="4" src="https://github.com/user-attachments/assets/1b68be7a-9e5e-468b-b515-5ab76df5a140" />
<img width="921" height="457" alt="5" src="https://github.com/user-attachments/assets/9cb888db-b0ad-4807-a468-9a18a30d7ff0" />

## Vérification des protections

```bash
run app.package.manifest com.android.insecurebankv2
run app.activity.info -a com.android.insecurebankv2 -i
run scanner.provider.finduris -a com.android.insecurebankv2
run app.provider.finduri com.android.insecurebankv2
```
## URI accessibles

```bash
content://com.android.insecurebankv2.TrackUserContentProvider/trackerusers/
content://com.android.insecurebankv2.TrackUserContentProvider/trackerusers
```
## Désactiver l’export des composants inutiles :
```bash
android:exported="false"
```
## Protéger les composants sensibles avec une permission spécifique :

```bash
android:permission="com.example.permission.SECURE"
```
## Sécuriser le Content Provider avec des permissions de lecture et d’écriture :

```bash
android:readPermission="com.example.permission.READ"
android:writePermission="com.example.permission.WRITE"
```
## Désactiver le mode debug en production :

```bash
android:debuggable="false"
```


