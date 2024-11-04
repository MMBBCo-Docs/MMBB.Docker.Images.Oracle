---
layout: page
title:  "Struttura modulo"
---

# MMBB.Docker.Images.Oracle

Modulo di  generazione dell  immagine di  un container di Oracle database
La generazione viene eseguita tramite  ant, attraverso il file file di configurazione ,**Build.xml**,
dove sono definiti le varie fasi necessaria alla  generazione dell'immagine 

Le fasi attraverso cui si sviluppa il processo di generazione sono 
* Download del file binario di setup di oracle dallo storage remoto in google drive associato all'account mmbbservice, tramite l'ausilio delle librerie powershell di supporto attivate tramite il container 
* Build dell'immagine 
* Pubblicazione dell'immagine sul hub docker **mmbbdockerhub**


Il modulo e composto dai seguenti files
```dos
C:.
│   .gitignore
│   Build.xml                     script di build per ant
│   README.md
│
├───bin
│       ant.Cointainer.Build.Download.Resources.ps1  script di download del file binario di setup Oracle
│       ant.Cointainer.Build.ps1                     script di creazione dell'immagine
│       docker-login.bat
│
└───build                                            cartella di build del docker
        .dockerignore
        buildContainerImage.ps1                      script di attivazione del build
        checkDBStatus.sh
        checkSpace.sh
        Checksum.ee
        Checksum.se2
        configTcps.sh
        createDB.sh
        createObserver.sh
        dbca.rsp.tmpl
        db_inst.rsp
        Dockerfile
        Dockerfile.ee
        Dockerfile.se2
        Dockerfile.xe
        installDBBinaries.sh
        LINUX.X64_213000_db_home.zip
        oracle-xe-21c.conf
        relinkOracleBinary.sh
        runOracle.sh
        runUserScripts.sh
        setPassword.sh
        setupLinuxEnv.sh
        startDB.sh
```

