##Get offerId API: 
* Method: POST
* Url: dev.idcrm.com/antargaz-web-service/offer/create
* Get offerId Rule

```
#!php

public function rules()

	{
		return [
			'prospect.leadid' => 'required',
			'prospect.antar_marche' => 'required',
			'prospect.antar_type' => 'required',
			'prospect.antar_typename'=> 'required',

			'prospect.antar_car'=>  'required|integer|min:1',
			'prospect.antar_npce'=> array("required","max:14",'regex:/^[0-9]{14}|[a-zA-Z]{2}[0-9]{6}|[0-9a-zA-Z]/'),
			'prospect.antar_profil'=> 'required|max:4|in:P011,P012,P013,P014,P015,P016,P017,P018,P019',
			'prospect.antar_situationname'=> 'required|max:10|in:PARTCHANGF,PROCOLLCHA,PARTNVEAUL,PROCOLLTNV,PARTNVEAUR,PROCOLLNV',
			'prospect.address1_line1'=> 'required',
			'prospect.emailaddress1'=> 'required|email|max:255',
			'prospect.mobilephone'=> 'required|max:10',
			'prospect.zAdrConso_CodeInsee'=> 'required',
			'prospect.antar_codepostallivraison'=> 'required|numeric|digits:5',
			'prospect.zAdrFact_CodeInsee'=> 'required|numeric|digits:5', //this is codeInsse
			'prospect.antar_codepostal_fact_fr'=> 'required|numeric|digits:5',
			'prospect.zAdrContractant_CodeInsee'=> 'required|numeric|digits:5',
			'prospect.antar_code_postal'=> 'required|numeric|digits:5',
			'prospect.antar_rcs'=> 'required|in:1,0',
			
			'prospect.antar_civilitename'=> 'required|string|max:5|in:M.,MME,MLLE',
			'prospect.firstname'=> 'required|string|max:40',
			'prospect.lastname'=> 'required|string|max:25',
			'prospect.antar_gdr'=> 'required',
			

			'prospect.telephone1'=> 'string|max:10',
			'prospect.companyname'=> 'string|max:40',
			'prospect.antar_formesocialename'=> 'string|max:20',
			'prospect.antar_codenaf'=> 'string|max:6',
			'prospect.antar_capital'=> 'numeric',
			
			'offer.antar_renonce_delais'=> 'required',
			'offer.antar_modereglement'=> 'required',
			'offer.antar_modereglementname'=> 'required|min:1|max:10',
			'offer.antar_modalitdefacturationname'=> 'required|min:1|max:10',
			'offer.antar_delaireglementname'=> 'required|min:3|max:10',
			'offer.antar_is_codeavantage'=> 'required|boolean',
			'offer.antar_offer'=> 'required|integer',
			'offer.antar_codebareme'=> 'required'
		];
	}
```

* Request Params

```
#!json

 {
  "prospect": {
    "antar_npce": "Z6852000000035",
    "leadid": "5e0c8156-905b-e511-80e8-3863bb3c33b0",
    "antar_marche": "533240000",
    "antar_type": "533240000",
    "antar_typename": "Professionnel",
    "antar_profil": "P012",
    "antar_situationname": "PROCOLLCHA",
    "address1_line1": "372 ROUTE DE LA COTE D AMOUR",
     "emailaddress1": "chanthou98@gmail.com",
    "mobilephone": "0123456789",
    "antar_civilitename": "M.",
    "firstname": "test",
    "lastname": "test",
    "antar_codeinsee": "44184",
    "antar_codepostallivraison": "44600",
    "antar_ville_fact_fr": "44184",
    "antar_codepostal_fact_fr": "44600",
    "antar_ville": "44184",
    "antar_code_postal": "44600",
    "antar_car": "92652",
    "antar_gdr": "GRDF",
    "telephone1": "098383838",
    "antar_formesocialename": "Non défini",
    "antar_capital": "1",
    "antar_codenaf": "45.11Z",
    "companyname": "Antargaz"
    },

    "offer": {
        "antar_codebareme": "N1511P25",
        "antar_offer": "2",
        "antar_renonce_delais": 1,
        "antar_modereglement": "533240002",
        "antar_modalitdefacturationname": "A",
        "antar_modereglementname": "S",
        "antar_delaireglementname": "E05",
        "antar_iban": "",
        "antar_is_codeavantage": "1"
    }
}
```
* Response Success:

```
#!json

{
 "status":1, "offer_id": 343434 
}
```


* Response fail
```
#!json

{
 "status":0, "message": "prospect_error:[exception] Ce PCE est déjà utilisé pour un autre prospect" 
}
```
