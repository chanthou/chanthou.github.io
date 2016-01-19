# a. API de requête selon le PCE # 
* url: http://dev.idcrm.com/antargaz-web-service/antargaz_ws/get_pce_info
* Antargaz url : http://wes-recette.antargaz.fr/services/GNBusinessRules_V_2_00/GNBusinessRulesSoap.php?wsdl
* méthode : getInfoPCE
* requête : 

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:gnb="http://wes-recette.antargaz.fr/services/GNBusinessRules_V_2_00/">
   <soapenv:Header/>
   <soapenv:Body>
      <gnb:getInfoPCERequest>
         <codePce>GI097672</codePce>
         <withMandat>true</withMandat>
      </gnb:getInfoPCERequest>
   </soapenv:Body>
</soapenv:Envelope>
```
* Response

```
#!xml

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://wes-recette.antargaz.fr/services/GNBusinessRules_V_2_00/">
   <SOAP-ENV:Body>
      <ns1:getInfoPCEResponse>
         <codeRetour>OK</codeRetour>
         <libelleRetour>Données PCE récupérées depuis OMEGA.</libelleRetour>
         <sourceDonnees>OMEGA</sourceDonnees>
         <infoPCE>
            <codePce>GI097672</codePce>
            <numRue>216</numRue>
            <libelleRue>BOULEVARD HENRI BARNIER</libelleRue>
            <complementAdresse>9606//</complementAdresse>
            <commune>
               <codeInsee>13216</codeInsee>
               <codeInseeGrd>13055</codeInseeGrd>
               <codePostal>13016</codePostal>
               <nomCommune>MARSEILLE 16</nomCommune>
            </commune>
            <pitd>
               <codePitd>GD0906</codePitd>
               <libellePitd>MARSEILLE</libellePitd>
               <typeGaz>H</typeGaz>
               <ntr>2</ntr>
               <nbPosteLivre>33</nbPosteLivre>
               <nts>7</nts>
               <tcs>69.17</tcs>
               <grt>
                  <idGrt>1</idGrt>
                  <codeGrt>GDFT</codeGrt>
                  <libelleGrt>GRTgaz</libelleGrt>
                  <isEligible>true</isEligible>
                  <tcs>93.75</tcs>
                  <tcl>35.61</tcl>
                  <ntr>67.61</ntr>
                  <ctaT/>
               </grt>
               <zoneSortie>
                  <idZoneSortie>32</idZoneSortie>
                  <libelleZoneSortie>PROVENCE</libelleZoneSortie>
               </zoneSortie>
               <stationMeteo>
                  <idStationMeteo>2</idStationMeteo>
                  <codeStationMeteo>13054001</codeStationMeteo>
                  <libelleStationMeteo>MARIGNANE</libelleStationMeteo>
                  <codeZoneClimatique>H3</codeZoneClimatique>
                  <temperatureSeuil>18</temperatureSeuil>
                  <temperatureEfficace>-6.5</temperatureEfficace>
                  <temperatureEfficaceAvril>6.1</temperatureEfficaceAvril>
               </stationMeteo>
               <zoneEquilibrageTransport>
                  <idZoneEqulibrageTransport>3</idZoneEqulibrageTransport>
                  <codeZoneEqulibrageTransport>ZET04</codeZoneEqulibrageTransport>
                  <libelleZoneEqulibrageTransport>ZONE SUD</libelleZoneEqulibrageTransport>
               </zoneEquilibrageTransport>
               <pitdDetail>
                  <rang>1</rang>
                  <perequation>1</perequation>
                  <zoneTarifaire>1</zoneTarifaire>
                  <codeInsee>13055</codeInsee>
                  <grdRang1>
                     <idGrd>13</idGrd>
                     <codeGrd>GRDF</codeGrd>
                     <libelleGrd>GrDF</libelleGrd>
                     <adresseGrd>6 rue Condorcet</adresseGrd>
                     <codePostalGrd>75009</codePostalGrd>
                     <villeGrd>PARIS</villeGrd>
                     <telephoneGrd>0800473333</telephoneGrd>
                  </grdRang1>
               </pitdDetail>
            </pitd>
            <trancheTarifaire>
               <idTrancheTarifaire>2</idTrancheTarifaire>
               <codeTrancheTarifaire>T2</codeTrancheTarifaire>
            </trancheTarifaire>
            <frequenceReleve>
               <idFrequenceReleve>3</idFrequenceReleve>
               <codeFrequenceReleve>JJ</codeFrequenceReleve>
               <libelleFrequenceReleve>Relèves JJ</libelleFrequenceReleve>
            </frequenceReleve>
            <isPremiereMes>false</isPremiereMes>
            <infoCompteur>
               <matricule>208000553</matricule>
               <nombreRoues>8</nombreRoues>
               <regime/>
               <situation/>
               <debit>1000M3/H</debit>
               <etatTechnique/>
               <DGI/>
            </infoCompteur>
            <infoContractuelle>
               <statutContractuel>non libre</statutContractuel>
               <CLD>true</CLD>
               <releveAccessibilite/>
               <releveDateMHS/>
               <releveIndexMHS/>
               <releveDTR/>
               <coupureMotif/>
               <coupureDate/>
               <coupureFraude/>
               <coupureDiagnostiqueQualite/>
            </infoContractuelle>
         </infoPCE>
      </ns1:getInfoPCEResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

# b. API de réception des data (contrats, …) pour enregistrement en base de données #

1. identifiants de connexion aux Web services
* login : pocom
* mdp : pocom

2. Identification utilisateur
Une identification est nécessaire pour récupérer le token qui servira à utiliser les méthodes qui suivent.
* Login : NOVULYS
* Mdp : GAZNAT123

* url : http://wes-recette.antargaz.fr/sap_web/index.php?module=jWSDL&action=WSDL:wsdl&service=usersprofilespocom~WsUsersProfiles
* méthode : loginPortailCommercial
* requête :

```
#!xml

<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:sap="http://172.21.22.19/V2/sap_web/">
   <soapenv:Header/>
   <soapenv:Body>
      <sap:loginPortailCommercial soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <zLogin xsi:type="sap:zLoginLoginPortailCommercial">NOVULYS</zLogin>
         <zPassword xsi:type="sap:zPasswordLoginPortailCommercial">GAZNAT123</zPassword>
      </sap:loginPortailCommercial>
   </soapenv:Body>
</soapenv:Envelope>

```
* Response

```
#!xml

<SOAP-ENV:Envelope SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://172.21.22.19/V2/sap_web/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/">
   <SOAP-ENV:Body>
      <ns1:loginPortailCommercialResponse>
         <loginPortailCommercialReturn xsi:type="ns1:CLoginPortailCommercialReturn">
            <iCodeRet xsi:type="xsd:int">1</iCodeRet>
            <iProfilUtillisateurId xsi:type="xsd:int">7</iProfilUtillisateurId>
            <iUserId xsi:type="xsd:int">222</iUserId>
            <zDateDerMajPassword xsi:type="xsd:string">2015-08-25 16:15:35</zDateDerMajPassword>
            <zEmail xsi:type="xsd:string">kader.mouffok@gmail.com</zEmail>
            <zLogin xsi:type="xsd:string">NOVULYS</zLogin>
            <zNom xsi:type="xsd:string">NOVULYS</zNom>
            <zPrenom xsi:type="xsd:string">NOVULYS</zPrenom>
            <zSapSessionToken xsi:type="xsd:string">45a88c366dda2fd92514accb8994b1bf</zSapSessionToken>
         </loginPortailCommercialReturn>
      </ns1:loginPortailCommercialResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
