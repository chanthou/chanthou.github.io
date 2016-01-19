
## Online sign api:
* Method: POST 
* Url: dev.idcrm.com/antargaz-web-service/online_sign
* All fields are require

```
#!json
{pdf_signatur: {
            uuid: "leadId",
            signature_pdf_page: "page number of pdf",
            signature_pdf_logo_lly: "Y-coordinate of the Lower left corner of the frame",
            signature_pdf_logo_llx: "x-coordinate of the lower left corner of the frame",
            signature_pdf_logo_urx: "x-coordinate of the upper right corner of the frame",
            signature_pdf_logo_ury: "y-coordinate of the upper right corner of the frame",
          }
pdf_file: "pdf file to be sign",
image_file: "Indicates the image to be used for the signature",
device_token: "F8A456E8DAEACEC428B427E9518741C92C6660..."
}

```

Response Success:

```
#!json

{
 "status": 1, "message": "successfully signed", "pdf_url": "", status: "ACCPT/WAITING", "validity": "02/12/1205"
}
```

Response Error:

```
#!json

{
 "status": 0, "message": "pdf_signed_error...."
}
```


##offline sign(POST): 
* Method: POST 
* Url: dev.idcrm.com/antargaz-web-service/offline_sign
* All fields are require

```
#!json
{pdf_signatur: {
            uuid: "prospect leadid",
            signature_pdf_page: "value",
            signature_pdf_logo_lly: "value",
            signature_pdf_logo_llx: "value",
            signature_pdf_logo_urx: "value",
            signature_pdf_logo_ury: "value",
           
          }
pdf_file: "pdf file to be sign",
image_file: "Indicates the image to be used for the signature",
device_token: "F8A456E8DAEACEC428B427E9518741C92C6660..."
}

```
