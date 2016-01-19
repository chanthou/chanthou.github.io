# a. API de génération de PDF
* url: http://dev.idcrm.com/antar-dev/antargaz_ws/generate_pdf
* antargaz url : http://wes-recette.antargaz.fr/services/Documents_V_3_00/documentsSoap.php?wsdl
* méthode : docXToPdf
* requête :

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:documentsSoap_V_3_00:services.az">
   <soapenv:Header/>
   <soapenv:Body>
      <urn:docXToPdfRequest>
         <fileType>WORD</fileType>
         <fileContent>UEs… (Contenu du fichier docx converti en base 64) </fileContent>
         <fileDatas>
            <dataName>$NOMTITULAIRE$</dataName>
            <dataType>TEXT</dataType>
            <dataValue>DAVID VINCENT</dataValue>
         </fileDatas>
         <fileDatas>
            <dataName>$NUMEROCONTRAT$</dataName>
            <dataType>TEXT</dataType>
            <dataValue>154544</dataValue>
         </fileDatas>
	    <fileDatas>
            <dataName>$PRENOMTITULAIRE$</dataName>
            <dataType>DATAMATRIX</dataType>
            <dataValue>MANDAT_123123123123123123</dataValue>
         </fileDatas>
         <fileDatas>
            <dataName>$CHECKFACT1$</dataName>
            <dataType>CHECKBOX</dataType>
            <dataValue>OK</dataValue>
         </fileDatas>
         <fileDatas>
            <dataName>$CHECKFACT2$</dataName>
            <dataType>CHECKBOX</dataType>
            <dataValue>NOK</dataValue>
         </fileDatas>
         <fileDatas>
            <dataName>$CHECKFACT3$</dataName>
            <dataType>CHECKBOX</dataType>
            <dataValue>NOK</dataValue>
         </fileDatas>
         <fileDatas>
            <dataType>TABLE</dataType>
            <rowsDatas>
               <colsDatas>
               	<dataName>$CARMIN$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_1_COL_1</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$CARMAX$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_1_COL_2</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$SERVICEGARANTIPRIXTTC$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_1_COL_3</dataValue>
               </colsDatas>
            </rowsDatas>
            <rowsDatas>
               <colsDatas>
               	<dataName>$CARMIN$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_2_COL_1</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$CARMAX$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_2_COL_2</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$SERVICEGARANTIPRIXTTC$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_2_COL_3</dataValue>
               </colsDatas>
            </rowsDatas>
            <rowsDatas>
               <colsDatas>
               	<dataName>$CARMIN$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_3_COL_1</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$CARMAX$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_3_COL_2</dataValue>
               </colsDatas>
               <colsDatas>
               	<dataName>$SERVICEGARANTIPRIXTTC$</dataName>
	         	     <dataType>TEXT</dataType>
	               <dataValue>LIGNE_3_COL_3</dataValue>
               </colsDatas>
            </rowsDatas>
         </fileDatas>
      </urn:docXToPdfRequest>
   </soapenv:Body>
</soapenv:Envelope>

```
* Response

```
#!xml

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="urn:documentsSoap_V_3_00:services.az">
   <SOAP-ENV:Body>
      <ns1:docXToPdfResponse>
         <codeRetour>OK</codeRetour>
         <libelleRetour>Fichier converti</libelleRetour>
         <fileContent>JVB…</fileContent>
      </ns1:docXToPdfResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

### b. API de requête selon le SIREN ###
* url: http://dev.idcrm.com/antar-dev/antargaz_ws/get_siret_info
* antargaz ws url : http://intuiz.altares.fr/axis2_V3.5/services/CallistoIdentite?wsdl
* méthode : getIdentiteAltaN3Entreprise
* requête : 

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.callisto.newsys.altares.fr">
   <soapenv:Header/>
      <soapenv:Body>
      <ser:getIdentiteAltaN3Entreprise>
         <ser:identification>U2013001831|378d8cc62f72d530734c16b89642b7944af225c2</ser:identification>
         <ser:refClient>toto</ser:refClient>
         <ser:siren>572126043</ser:siren>
      </ser:getIdentiteAltaN3Entreprise>
   </soapenv:Body>
</soapenv:Envelope>


```

* Response

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   <soapenv:Body>
      <ns:getIdentiteAltaN3EntrepriseResponse xmlns:ns="http://service.callisto.newsys.altares.fr">
         <ns:return xsi:type="ax214:IdentiteAltaN3EnResponse" xmlns:ax214="http://identite.response.callisto.newsys.altares.fr/xsd" xmlns:ax27="http://pcl.vo.callisto.newsys.altares.fr/xsd" xmlns:ax28="http://annonce.vo.callisto.newsys.altares.fr/xsd" xmlns:ax211="http://lien.vo.callisto.newsys.altares.fr/xsd" xmlns:ax24="http://finance.vo.callisto.newsys.altares.fr/xsd" xmlns:ax21="http://response.callisto.newsys.altares.fr/xsd" xmlns:ax22="http://vo.callisto.newsys.altares.fr/xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <ax21:correct>true</ax21:correct>
            <ax21:exception xsi:nil="true"/>
            <ax21:parametres xsi:type="ax22:ParametreCallistoInfo">
               <ax22:nbParametre>2</ax22:nbParametre>
               <ax22:parametre xsi:type="ax22:ParametreCallisto">
                  <ax22:nom>refClient</ax22:nom>
                  <ax22:valeur>toto</ax22:valeur>
               </ax22:parametre>
               <ax22:parametre xsi:type="ax22:ParametreCallisto">
                  <ax22:nom>siren</ax22:nom>
                  <ax22:valeur>572126043</ax22:valeur>
               </ax22:parametre>
            </ax21:parametres>
            <ax214:myInfo xsi:type="ax22:IdentiteAltaN3EntrepriseInfo">
               <ax22:capital>3935349.0</ax22:capital>
               <ax22:chiffreAffaire>6.9974169E8</ax22:chiffreAffaire>
               <ax22:codePaysOrigine>00000</ax22:codePaysOrigine>
               <ax22:codePostal>92400</ax22:codePostal>
               <ax22:complementRue>IMMEUBLE LES RENARDIERES</ax22:complementRue>
               <ax22:dateCreation>1900-01-01</ax22:dateCreation>
               <ax22:dateDernierBilan>2014-09-30</ax22:dateDernierBilan>
               <ax22:dateFermeture xsi:nil="true"/>
               <ax22:dateImmatriculation>1957-08-02</ax22:dateImmatriculation>
               <ax22:dirigeantPrincipal>WALSH JR John</ax22:dirigeantPrincipal>
               <ax22:dureeDernierBilan>12</ax22:dureeDernierBilan>
               <ax22:effectif>342</ax22:effectif>
               <ax22:etat>1</ax22:etat>
               <ax22:formeJuridique>SA à conseil d'administration</ax22:formeJuridique>
               <ax22:formeJuridiqueCode>5599</ax22:formeJuridiqueCode>
               <ax22:greffe>Nanterre</ax22:greffe>
               <ax22:libellePaysOrigine>FRANCE</ax22:libellePaysOrigine>
               <ax22:naf5EntreCode>4671Z</ax22:naf5EntreCode>
               <ax22:naf5EntreLibelle>Commerce de gros (commerce interentreprises) de combustibles et de produits annexes</ax22:naf5EntreLibelle>
               <ax22:nbEtablissement>58</ax22:nbEtablissement>
               <ax22:nbEtablissementActif>16</ax22:nbEtablissementActif>
               <ax22:nonDiffusible>false</ax22:nonDiffusible>
               <ax22:numTVAIntraCom>FR01572126043</ax22:numTVAIntraCom>
               <ax22:procedureCollective>NEANT</ax22:procedureCollective>
               <ax22:raisonSociale>ANTARGAZ</ax22:raisonSociale>
               <ax22:rcs>1988B03380</ax22:rcs>
               <ax22:rue>3 PLACE DE SAVERNE</ax22:rue>
               <ax22:sigle xsi:nil="true"/>
               <ax22:siret>57212604300700</ax22:siret>
               <ax22:trCA>200 millions d'euros ou plus</ax22:trCA>
               <ax22:trCACode>9</ax22:trCACode>
               <ax22:trEffectifEntre>250 à 499 salariés</ax22:trEffectifEntre>
               <ax22:trEffectifEntreCode>32</ax22:trEffectifEntreCode>
               <ax22:typeExploitationCode>O</ax22:typeExploitationCode>
               <ax22:typeExploitationLabel>Exploitant</ax22:typeExploitationLabel>
               <ax22:ville>COURBEVOIE</ax22:ville>
            </ax214:myInfo>
         </ns:return>
      </ns:getIdentiteAltaN3EntrepriseResponse>
   </soapenv:Body>
</soapenv:Envelope>


```

##  c. API de vérification de l’IBAN ## 
La vérification de l’IBAN s’effectue en deux étapes, une vérification du code banque à l’aide du web service et ensuite un appel à une méthode javascript pour le contrôle de l’IBAN.

### i. Vérification du code banque ###
* url: http://dev.idcrm.com/antargaz-web-service/antargaz_ws/get_bank_info
* antargaz ws url : http://wes-recette.antargaz.fr/services/References_V_1_00/referencesSoap.php?wsdl
* méthode : getBanque
* requête :

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ref="http://wes-recette.antargaz.fr/services/References_V_1_00/">
   <soapenv:Header/>
   <soapenv:Body>
      <ref:getBanqueRequest>
         <codeBanque>30003</codeBanque>
         <codeGuichet>00715</codeGuichet>
      </ref:getBanqueRequest>
   </soapenv:Body>
</soapenv:Envelope>

```

* Reponse

```
#!xml

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://wes-recette.antargaz.fr/services/References_V_1_00/">
   <SOAP-ENV:Body>
      <ns1:getBanqueResponse>
         <codeRetour>OK</codeRetour>
         <libelleRetour>Informations banque recupérées</libelleRetour>
         <banqueDatas>
            <codeBanque>30003</codeBanque>
            <nomBanque>STE GENERALE</nomBanque>
            <nomBanqueAbrege>S GENERALE</nomBanqueAbrege>
            <nomBanqueCommun/>
            <codeBic>SOGEFRPP</codeBic>
            <guichets>
               <codeGuichet>00715</codeGuichet>
               <nomGuichet>AG SENLIS</nomGuichet>
               <codeSwift>SOGEFRPP</codeSwift>
            </guichets>
         </banqueDatas>
      </ns1:getBanqueResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

### ii. Vérification de l’IBAN ###

* url : cf. iban.js
* 
* méthode : isValid(iban)
* 




## d. API de réception des contrats PDF signés ## 

* url : http://wes-recette.antargaz.fr/services/Documents_V_3_00/documentsSoap.php?wsdl
* méthode : addGedDocument
* requête : 


```
#!xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:documentsSoap_V_3_00:services.az">
   <soapenv:Header/>
   <soapenv:Body>
      <urn:addGedDocumentRequest>
         <getDocumentActivite>GAZNAT</getDocumentActivite>
         <gedDocumentCodeClient>1005</gedDocumentCodeClient>
         <gedDocumentNumeroContrat>83135</gedDocumentNumeroContrat>
         <gedDocumentRefDoc>F</gedDocumentRefDoc>
         <gedDocumentCommentaire>test</gedDocumentCommentaire>
         <gedDocumentDate>2015-08-24</gedDocumentDate>
         <documentContent>cid:1033723022666</documentContent>
      </urn:addGedDocumentRequest>
   </soapenv:Body>
</soapenv:Envelope>

```

* Response

```
#!xml

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="urn:documentsSoap_V_3_00:services.az">
   <SOAP-ENV:Body>
      <ns1:addGedDocumentResponse>
         <codeRetour>OK</codeRetour>
         <libelleRetour>Document intégré à la ged</libelleRetour>
         <documentIdentifiant>NUMEN_1994</documentIdentifiant>
      </ns1:addGedDocumentResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

## e. API de récupération des communes ##

* url : http://wes-recette.antargaz.fr/services/References_V_1_00/referencesSoap.php?wsdl
* méthode : getCommune
* requête :
* 

```
#!xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ref="http://wes-recette.antargaz.fr/services/References_V_1_00/">
   <soapenv:Header/>
   <soapenv:Body>
      <ref:getCommuneRequest>
         <codePostal>01500</codePostal>
         <codeInsee></codeInsee>
         <codeCanton></codeCanton>
         <nomCommune></nomCommune>
      </ref:getCommuneRequest>
   </soapenv:Body>
</soapenv:Envelope>

```
* Response

```
#!xml

<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://wes-recette.antargaz.fr/services/References_V_1_00/">
   <SOAP-ENV:Body>
      <ns1:getCommuneResponse>
         <codeRetour>OK</codeRetour>
         <libelleRetour>Commune récupérée</libelleRetour>
         <communes>
            <codeInsee>01004</codeInsee>
            <codeInseeGrd>01004</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>AMBERIEU EN BUGEY</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01007</codeInsee>
            <codeInseeGrd>01007</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>AMBRONAY</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01008</codeInsee>
            <codeInseeGrd>01008</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>AMBUTRIX</nomCommune>
            <cantons>
               <codeCanton>0117</codeCanton>
               <nomCanton>LAGNIEU</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01041</codeInsee>
            <codeInseeGrd>01041</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>BETTANT</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01089</codeInsee>
            <codeInseeGrd>01089</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>CHATEAU GAILLARD</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01149</codeInsee>
            <codeInseeGrd>01149</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>DOUVRES</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01345</codeInsee>
            <codeInseeGrd>01345</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>SAINT DENIS EN BUGEY</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
         <communes>
            <codeInsee>01379</codeInsee>
            <codeInseeGrd>01379</codeInseeGrd>
            <codePostal>01500</codePostal>
            <nomCommune>SAINT MAURICE DE REMENS</nomCommune>
            <cantons>
               <codeCanton>0101</codeCanton>
               <nomCanton>AMBERIEU-EN-BUGEY</nomCanton>
            </cantons>
         </communes>
      </ns1:getCommuneResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```