## 2. Scholarships workflow #2 
### Scholarship Application Process Overview
Here we outline the workflow for scholarship discovery and applying for the same using DSEP. The workflow includes interactions between the app (BAP) and the schloarship provider (BPP) for search, select, booking, and applying to the scholarships. A typical workflow for course discovery consists of the following steps:

#### Step 1: BAP Initiates the Search
The BAP initiates a search for scholarships. It can check for scholarships directly from the cart or independently from the landing page/home screen.

#### Step 2: Provider Sends Scholarship Lists
Upon the search request, the provider sends a list of available scholarships. If no scholarships are found, the search results are empty. If scholarships are available, the list is provided.

#### Step 3: BAP Selects a Scholarship
The BAP selects a scholarship to explore more details such as eligibility criteria and other relevant information. The BAP proceeds to apply for the chosen scholarship.

#### Step 4: BAP Completes the Required Form
The BAP fills out the necessary forms, uploads the required documents, and submits the scholarship application.

#### Step 5: Provider Receives the Scholarship Application
Upon submission, the provider receives the scholarship application. They review the application and either approve or deny the scholarship.

#### Step 6: BAP Receives Notification
The BAP receives a notification regarding the approval or denial of the scholarship. The status of the scholarship changes accordingly. Finally, the BAP can proceed with their checkout process from the cart where they initiated the scholarship application.

### Search
### Logical Flow
![Alt text](./media/image-6.png)

![Alt text](./media/image-9.png) 

### Search for scholarship 
In this stage, the user searches for a scholarship to apply for.

#### User-side Actions
- The user searches for a scholarship by name or gender-specific scholarship.

#### Provider-Side Actions
- Receives the search query.
- Sends the draft order with the list of scholarships available.

#### Figma 
![Alt text](./media/image-7.png)

#### Example `search` request

```json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "search",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c60008",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "intent": {
            "item": {
                "descriptor": {
                    "name": "scholarship for undergraduate"
                }
            }
        }
    }
}
```
#### Example `on_search` request

```json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_search",
        "timestamp": "2023-08-02T07:21:58.448Z",
        "ttl": "PT10M",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c60008",
        "message_id": "f6a7d7ea-a23e-4419-b07e-a3412fdffecf"
    },
    "message": {
        "catalog": {
            "descriptor": {
                "name": "Protean DSEP Scholarships and Grants BPP Platform"
            },
            "providers": [
                {
                    "id": "BX213573733",
                    "descriptor": {
                        "name": "XYZ Education Foundation",
                        "short_desc" : "Short Description about the Foundation",
                        "images": [
                            {
                                "url" : "url of the image of the provider"
                            }
                        ]
                    },
                    "locations" : [
                        {
                            "id" : "L1",
                            "city" :"Pune",
                            "state" : "Maharastra"
                        },
                        {
                            "id" : "L2",
                            "city" :"Thane",
                            "state" : "Maharastra"
                        },
                        {
                            "id" : "L3",
                            "city" :"Lucknow",
                            "state" : "Uttar Pradesh"
                        }
                    ],
                    "categories": [
                        {
                            "id": "DSEP_CAT_1",
                            "descriptor": {
                                "code": "ug",
                                "name": "Under Graduate"
                            }
                        }
                    ],
                    "fulfillments": [
                        {
                            "id": "DSEP_FUL_63587501",
                            "type": "SCHOLARSHIP",
                            "tracking": false,
                            "contact": {
                                "phone": "9876543210",
                                "email": "maryg@xyz.com"
                            }
                        }
                    ],
                    "items": [
                        {
                            "id": "SCM_63587501",
                            "descriptor": {
                                "name": "XYZ Education Scholarship for Undergraduate Students",
                                "long_desc": "XYZ Education Scholarship for Undergraduate Students"
                            },
                            "price": {
                                "currency": "INR",
                                "value": "Upto RS.1000 per year"
                            },
                            "time" : {
                                "label" : "Start  & End date of the Application",
                                "range" : {
                                    "start" : "2022-09-01T00:00:00.000Z",
                                    "end" : "2022-10-31T00:00:00.000Z"
                                }
                            },
                            "rateable": false,
                            "tags": [
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "soc-elg",
                                        "name": "Social Eligibility"
                                    },
                                    "list": [
                                        {
                                            "value" : "SC"
                                        },
                                        {
                                            "value" : "ST"
                                        },
                                        {
                                            "value" : "OBC"
                                        }]
                                },
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "gen-elg",
                                        "name": "Gender Eligibility"
                                    },
                                    "list": [
                                        {
                                            "value" : "Female"
                                        },
                                        {
                                            "value" : "Transgender"
                                        }]
                                },
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "fin-elg",
                                        "name": "Financial Eligibility"
                                    },
                                    "list": [
                                        {
                                            "value" : "Max Family Income - Rs.500000.00"
                                        }] 
                                    
                                },
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "acad-elg",
                                        "name": "Academic Eligibility"
                                    },
                                    "list": [
                                        {
                                            "descriptor": {
                                                "code": "class",
                                                "name": "Class"
                                            },
                                            "value": "12th"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "percentage",
                                                "name": "Percentage"
                                            },
                                            "value": ">= 50"
                                        }
        
                                    ] 
                                    
                                },
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "docs-reqd",
                                        "name": "Documents Required"
                                    },
                                    "list": [
                                        {
                                            "value" : "10th Marksheet"
                                        },
                                        {
                                            "value" : "Aadhar Card of the Student"
                                        },
                                        {
                                            "value" : "Aadhar Card of the Parent"
                                        },
                                        {
                                            "value" : "Pan Card of the Parent"
                                        }
                                    ]
                                },
                                {
                                    "display": true,
                                    "descriptor": {
                                        "code": "add-info",
                                        "name": "Additional Information"
                                    },
                                    "list": [
                                        {
                                            "descriptor": {
                                                "code": "faq-url",
                                                "name": "Frequently Asked Questions's URL"
                                            },
                                            "value" : "https://www.xyz-scholarship.com/faq" 
                                        },
                                        {
                                            "descriptor": {
                                                "code": "tnc-url",
                                                "name": "Terms and Conditions's URL"
                                            },
                                            "value": "https://www.xyz-scholarship.com/tnc"
                                        }
                                    ]
                                }
                            ],
                            "category_ids": ["DSEP_CAT_1"],
                            "fulfillment_ids": ["DSEP_FUL_63587501"],
                            "location_ids": ["L1","L2"]
                        }
                    ],
                    "rateable": false
                }
            ]
        }
    }
}
```
### Selecting a Scholarship

In this stage, the user selects a scholarship that they intend to apply for.

#### User-Side Actions

- The user selects a scholarship to apply for that they are interested in.


#### Provider-Side Actions

- Sends a draft outlining all the required details to complete the process. This includes information about eligibility criteria, important dates, gender-specific requirements, financial eligibility checks, etc.

#### Figma 
![Alt text](./media/image-10.png)


#### Example `select` request
``` json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "select",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "provider": {
                "id": "BX213573733"
            },
            "fulfillments": [
                {
                    "id": "DSEP_FUL_63587501"
                }
            ],
            "items": [
                {
                    "id": "SCM_63587501"
                }
            ]
        }
    }
}
```

#### Example `on_select` request
```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_select",
        "timestamp": "2023-08-02T09:12:12.680Z",
        "ttl": "PT10M",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "6114a3e5-acb0-4c99-b017-0ead5e894bad"
    },
    "message": {
        "order": {
            "provider": {
                "id": "BX213573733",
                "descriptor": {
                    "name": "XYZ Education Foundation",
                    "short_desc" : "Short Description about the Foundation",
                    "images": [
                        {
                            "url" : "url of the image of the provider"
                        }
                    ]
                },
                "locations" : [
                    {
                        "id" : "L1",
                        "city" :"Pune",
                        "state" : "Maharastra"
                    },
                    {
                        "id" : "L2",
                        "city" :"Thane",
                        "state" : "Maharastra"
                    },
                    {
                        "id" : "L3",
                        "city" :"Lucknow",
                        "state" : "Uttar Pradesh"
                    }
                ],
                "rateable": false
            },
            "items": [
                {
                    "id": "SCM_63587501",
                    "descriptor": {
                        "name": "XYZ Education Scholarship for Undergraduate Students",
                        "short_desc": "XYZ Education Scholarship for Undergraduate Students"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "Upto RS.1000 per year"
                    },
                    "time" : {
                        "label" : "Start  & End date of the Application",
                        "range" : {
                            "start" : "2022-09-01T00:00:00.000Z",
                            "end" : "2022-10-31T00:00:00.000Z"
                        }
                    },
                    "rateable": false,
                    "tags": [
                        {
                            "display": true,
                            "descriptor": {
                                "code": "soc-elg",
                                "name": "Social Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "SC"
                                },
                                {
                                    "value" : "ST"
                                },
                                {
                                    "value" : "OBC"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "gen-elg",
                                "name": "Gender Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Female"
                                },
                                {
                                    "value" : "Transgender"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "fin-elg",
                                "name": "Financial Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Max Family Income - Rs.500000.00"
                                }] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "acad-elg",
                                "name": "Academic Eligibility"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "class",
                                        "name": "Class"
                                    },
                                    "value": "12th"
                                },
                                {
                                    "descriptor": {
                                        "code": "percentage",
                                        "name": "Percentage"
                                    },
                                    "value": ">= 50"
                                }

                            ] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "docs-reqd",
                                "name": "Documents Required"
                            },
                            "list": [
                                {
                                    "value" : "10th Marksheet"
                                },
                                {
                                    "value" : "Aadhar Card of the Student"
                                },
                                {
                                    "value" : "Aadhar Card of the Parent"
                                },
                                {
                                    "value" : "Pan Card of the Parent"
                                }
                            ]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "add-info",
                                "name": "Additional Information"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "faq-url",
                                        "name": "Frequently Asked Questions's URL"
                                    },
                                    "value" : "https://www.xyz-scholarship.com/faq" 
                                },
                                {
                                    "descriptor": {
                                        "code": "tnc-url",
                                        "name": "Terms and Conditions's URL"
                                    },
                                    "value": "https://www.xyz-scholarship.com/tnc"
                                }
                            ]
                        }
                    ],
                    "location_ids": ["L1","L2"],
                    "category_ids": ["DSEP_CAT_1"]
                }
            ],
            "fulfillments": [
                {
                    "id": "DSEP_FUL_63587501",
                    "type": "SCHOLARSHIP",
                    "tracking": false,
                    "agent" : {
                        "person" : {
                            "name" : "Ekstep Foundation SPoc"
                        },
                        "contact" : {
                            "email" : "ekstepsupport@ekstep.com"
                        }
                    }
                }
            ],
            "quote" :{
                "price" : {
                    "currency" : "INR",
                    "value" : "250000"
                },
                "breakup":[
                    {
                        "title": "Tution fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "150000"
                        }
                    },
                    {
                        "title": "Hostel fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    },
                    {
                        "title": "Books",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    }
                ]
            }
        }
    }
}
```
### Scholarship Order Initialization

In this stage, the user provides the required information and initiates submission of scholarship. (ordering of scholarship)

#### User-Side Actions
- The user selects a scholarship to apply for that they are interested in. They understand more details about the scholarship by reading the details, understanding the eligibility criteria, application start and end dates, required document details, etc.
- The user then fills and submits the data required by the provider.

#### Provider-Side Actions
- The provider receives the scholarship application for review.
- Based on the received information, the provider will decide whether to approve or deny the scholarship application.
 
#### Figma 
![Alt text](./media/image-12.png)


#### Example `init` request
```json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "init",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "items": [
                {
                    "id": "SCM_63587501"
                }
            ],
            "provider": {
                "id": "BX213573733"
            },
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "payments" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                   
                }
            ]

        }
    }
}
```

#### Example `on_init` request

```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_init",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "provider": {
                "id": "471",
                "descriptor": {
                    "name": "XYZ Education Foundation",
                    "short_desc" : "Short Description about the Foundation",
                    "images": [
                        {
                            "url" : "url of the image of the provider"
                        }
                    ]
                },
                "rateable": false
            },
            "items": [
                {
                    "id": "SCM_63587501",
                    "descriptor": {
                        "name": "XYZ Education Scholarship for Undergraduate Students",
                        "long_desc": "XYZ Education Scholarship for Undergraduate Students"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "Upto RS.1000 per year"
                    },
                    "time" : {
                        "label" : "Start  & End date of the Application",
                        "range" : {
                            "start" : "2022-09-01T00:00:00.000Z",
                            "end" : "2022-10-31T00:00:00.000Z"
                        }
                    },
                    "xinput": {
                        "required": true,
                        "head": {
                            "descriptor": {
                                "name": "Application Form"
                            },
                            "index": {
                                "min": 0,
                                "cur": 0,
                                "max": 3
                            },
                            "headings": [
                                "Personal Details",
                                "Educational Details",
                                "Financial Information",
                                "Review & Submit"
                            ]
                        },
                        "form": {
                            "mime_type": "text/html",
                            "url": "https://6vs8xnx5i7.vidyasaarathi.co.in/loans-kyc/xinput/formid/a23f2fdfbbb8ac402bfd54f",
                            "resubmit": false,
                            "auth": {
                                "descriptor": {
                                    "code": "jwt"
                                },
                                "value": "eyJhbGciOiJIUzI.eyJzdWIiOiIxMjM0NTY3O.SflKxwRJSMeKKF2QT4"
                            }
                        }
                    },
                    "rateable": false,
                    "tags": [
                        {
                            "display": true,
                            "descriptor": {
                                "code": "soc-elg",
                                "name": "Social Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "SC"
                                },
                                {
                                    "value" : "ST"
                                },
                                {
                                    "value" : "OBC"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "gen-elg",
                                "name": "Gender Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Female"
                                },
                                {
                                    "value" : "Transgender"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "fin-elg",
                                "name": "Financial Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Max Family Income - Rs.500000.00"
                                }] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "acad-elg",
                                "name": "Academic Eligibility"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "class",
                                        "name": "Class"
                                    },
                                    "value": "12th"
                                },
                                {
                                    "descriptor": {
                                        "code": "percentage",
                                        "name": "Percentage"
                                    },
                                    "value": ">= 50"
                                }

                            ] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "docs-reqd",
                                "name": "Documents Required"
                            },
                            "list": [
                                {
                                    "value" : "10th Marksheet"
                                },
                                {
                                    "value" : "Aadhar Card of the Student"
                                },
                                {
                                    "value" : "Aadhar Card of the Parent"
                                },
                                {
                                    "value" : "Pan Card of the Parent"
                                }
                            ]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "add-info",
                                "name": "Additional Information"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "faq-url",
                                        "name": "Frequently Asked Questions's URL"
                                    },
                                    "value" : "https://www.xyz-scholarship.com/faq" 
                                },
                                {
                                    "descriptor": {
                                        "code": "tnc-url",
                                        "name": "Terms and Conditions's URL"
                                    },
                                    "value": "https://www.xyz-scholarship.com/tnc"
                                }
                            ]
                        }
                    ],
                    "location_ids": ["L1","L2"],
                    "fulfillment_ids": [
                        "VSP_FUL_1113"
                    ]
                }
            ],
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "state" : {
                        "descriptor" : {
                            "code": "APPLICATION-STARTED",
                            "name" : "Application started"
                        },
                        "updated_at" : "2023-02-06T09:55:41.161Z"
                    },
                    "id": "VSP_FUL_1113",
                    "type": "SCHOLARSHIP",
                    "tracking": false,
                    "agent" : {
                        "person" : {
                            "name" : "Ekstep Foundation SPoc"
                        },
                        "contact" : {
                            "email" : "ekstepsupport@ekstep.com"
                        }
                    },
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "payments" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                   
                }
            ],
            "quote" :{
                "price" : {
                    "currency" : "INR",
                    "value" : "250000"
                },
                "breakup":[
                    {
                        "title": "Tution fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "150000"
                        }
                    },
                    {
                        "title": "Hostel fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    },
                    {
                        "title": "Books",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    }
                ]
            } 
        }
    }
}
```

### Scholarship Order Confirmation, Status, Track 

In this stage, the user receives the notification of the scholarship acceptance or rejection.

#### User-Side Actions
- The user receives a notification regarding the scholarship status.
- Subsequently, the user proceeds to complete the checkout steps to finalize their decision.
- The user can keep track and check the status of the schoalrship application. 

#### Provider-Side Actions
- The provider sends the details of the scholarship status, including the awarded amount, and confirms the application. 
- The appropriate tracking status and the scholarship application status is sent upon request to the user. 

#### Figma
![Alt text](./media/image-8.png)
![Alt text](./media/image-11.png)

#### Example `confirm` request
``` json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "confirm",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "items": [
                {
                    "id": "SCM_63587501"
                }
            ],
            "provider": {
                "id": "BX213573733"
            },
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "payment" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                }
            ]
        }
    }
}
```
#### Example `on_confirm` request
``` json 
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_confirm",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "id": "12424kh",
            "provider": {
                "id": "471",
                "descriptor": {
                    "name": "XYZ Education Foundation",
                    "short_desc" : "Short Description about the Foundation",
                    "images": [
                        {
                            "url" : "url of the image of the provider"
                        }
                    ]
                },
                "rateable": false
            },
            "items": [
                {
                    "id": "SCM_63587501",
                    "descriptor": {
                        "name": "XYZ Education Scholarship for Undergraduate Students",
                        "long_desc": "XYZ Education Scholarship for Undergraduate Students"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "Upto RS.1000 per year"
                    },
                    "time" : {
                        "label" : "Start  & End date of the Application",
                        "range" : {
                            "start" : "2022-09-01T00:00:00.000Z",
                            "end" : "2022-10-31T00:00:00.000Z"
                        }
                    },
                    "rateable": false,
                    "tags": [
                        {
                            "display": true,
                            "descriptor": {
                                "code": "soc-elg",
                                "name": "Social Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "SC"
                                },
                                {
                                    "value" : "ST"
                                },
                                {
                                    "value" : "OBC"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "gen-elg",
                                "name": "Gender Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Female"
                                },
                                {
                                    "value" : "Transgender"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "fin-elg",
                                "name": "Financial Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Max Family Income - Rs.500000.00"
                                }] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "acad-elg",
                                "name": "Academic Eligibility"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "class",
                                        "name": "Class"
                                    },
                                    "value": "12th"
                                },
                                {
                                    "descriptor": {
                                        "code": "percentage",
                                        "name": "Percentage"
                                    },
                                    "value": ">= 50"
                                }

                            ] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "docs-reqd",
                                "name": "Documents Required"
                            },
                            "list": [
                                {
                                    "value" : "10th Marksheet"
                                },
                                {
                                    "value" : "Aadhar Card of the Student"
                                },
                                {
                                    "value" : "Aadhar Card of the Parent"
                                },
                                {
                                    "value" : "Pan Card of the Parent"
                                }
                            ]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "add-info",
                                "name": "Additional Information"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "faq-url",
                                        "name": "Frequently Asked Questions's URL"
                                    },
                                    "value" : "https://www.xyz-scholarship.com/faq" 
                                },
                                {
                                    "descriptor": {
                                        "code": "tnc-url",
                                        "name": "Terms and Conditions's URL"
                                    },
                                    "value": "https://www.xyz-scholarship.com/tnc"
                                }
                            ]
                        }
                    ],
                    "location_ids": ["L1","L2"],
                    "fulfillment_ids": [
                        "VSP_FUL_1113"
                    ]
                }
            ],
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "state" : {
                        "descriptor" : {
                            "code": "APPLICATION-SUBMITTED",
                            "name" : "Application Submitted"
                        },
                        "updated_at" : "2023-02-06T09:55:41.161Z"
                    },
                    "id": "VSP_FUL_1113",
                    "type": "SCHOLARSHIP",
                    "tracking": false,
                    "agent" : {
                        "person" : {
                            "name" : "Ekstep Foundation SPoc"
                        },
                        "contact" : {
                            "email" : "ekstepsupport@ekstep.com"
                        }
                    },
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "cancellation_terms" : [
                {
                    "cancellation_fee" : {
                        "amount" : {
                            "currency" : "INR",
                            "value" : "Penalty upto 5,00,000 INR"
                        }
                    }
                }

            ],
            "docs": [
                {
                    "descriptor":{
                        "name" :"Application Details",
                        "short_desc" : "To open this document, enter the password sent to your email mayan****@***.com"
                    },
                    "url" : "https://link-to-the-document.com",
                    "mime_type" : "application/pdf"
                }
            ],
            "payments" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                   
                }
            ],
            "quote" :{
                "price" : {
                    "currency" : "INR",
                    "value" : "250000"
                },
                "breakup":[
                    {
                        "title": "Tution fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "150000"
                        }
                    },
                    {
                        "title": "Hostel fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    },
                    {
                        "title": "Books",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    }
                ]
            }
        }
    }
}
```
#### Example `status` request

```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "status",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order_id" : "12424kh"
    }
}
```
#### Example `on_status` request
```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_status",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "id": "12424kh",
            "provider": {
                "id": "471",
                "descriptor": {
                    "name": "XYZ Education Foundation",
                    "short_desc" : "Short Description about the Foundation",
                    "images": [
                        {
                            "url" : "url of the image of the provider"
                        }
                    ]
                },
                "rateable": false
            },
            "items": [
                {
                    "id": "SCM_63587501",
                    "descriptor": {
                        "name": "XYZ Education Scholarship for Undergraduate Students",
                        "long_desc": "XYZ Education Scholarship for Undergraduate Students"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "Upto RS.1000 per year"
                    },
                    "time" : {
                        "label" : "Start  & End date of the Application",
                        "range" : {
                            "start" : "2022-09-01T00:00:00.000Z",
                            "end" : "2022-10-31T00:00:00.000Z"
                        }
                    },
                    "rateable": false,
                    "tags": [
                        {
                            "display": true,
                            "descriptor": {
                                "code": "soc-elg",
                                "name": "Social Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "SC"
                                },
                                {
                                    "value" : "ST"
                                },
                                {
                                    "value" : "OBC"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "gen-elg",
                                "name": "Gender Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Female"
                                },
                                {
                                    "value" : "Transgender"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "fin-elg",
                                "name": "Financial Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Max Family Income - Rs.500000.00"
                                }] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "acad-elg",
                                "name": "Academic Eligibility"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "class",
                                        "name": "Class"
                                    },
                                    "value": "12th"
                                },
                                {
                                    "descriptor": {
                                        "code": "percentage",
                                        "name": "Percentage"
                                    },
                                    "value": ">= 50"
                                }

                            ] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "docs-reqd",
                                "name": "Documents Required"
                            },
                            "list": [
                                {
                                    "value" : "10th Marksheet"
                                },
                                {
                                    "value" : "Aadhar Card of the Student"
                                },
                                {
                                    "value" : "Aadhar Card of the Parent"
                                },
                                {
                                    "value" : "Pan Card of the Parent"
                                }
                            ]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "add-info",
                                "name": "Additional Information"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "faq-url",
                                        "name": "Frequently Asked Questions's URL"
                                    },
                                    "value" : "https://www.xyz-scholarship.com/faq" 
                                },
                                {
                                    "descriptor": {
                                        "code": "tnc-url",
                                        "name": "Terms and Conditions's URL"
                                    },
                                    "value": "https://www.xyz-scholarship.com/tnc"
                                }
                            ]
                        }
                    ],
                    "location_ids": ["L1","L2"],
                    "fulfillment_ids": [
                        "VSP_FUL_1113"
                    ]
                }
            ],
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "state" : {
                        "descriptor" : {
                            "code": "SCHOLARSHIP-APPROVED",
                            "name" : "Application Submitted"
                        },
                        "updated_at" : "2023-02-06T09:55:41.161Z"
                    },
                    "id": "VSP_FUL_1113",
                    "type": "SCHOLARSHIP",
                    "tracking": false,
                    "agent" : {
                        "person" : {
                            "name" : "Ekstep Foundation SPoc"
                        },
                        "contact" : {
                            "email" : "ekstepsupport@ekstep.com"
                        }
                    },
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "cancellation_terms" : [
                {
                    "cancellation_fee" : {
                        "amount" : {
                            "currency" : "INR",
                            "value" : "Penalty upto 5,00,000 INR"
                        }
                    }
                }

            ],
            "docs": [
                {
                    "descriptor":{
                        "name" :"Application Details",
                        "short_desc" : "To open this document, enter the password sent to your email mayan****@***.com"
                    },
                    "url" : "https://link-to-the-document.com",
                    "mime_type" : "application/pdf"
                }
            ],
            "payments" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                   
                }
            ],
            "quote" :{
                "price" : {
                    "currency" : "INR",
                    "value" : "250000"
                },
                "breakup":[
                    {
                        "title": "Tution fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "150000"
                        }
                    },
                    {
                        "title": "Hostel fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    },
                    {
                        "title": "Books",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    }
                ]
            }
        }
    }
}
```
#### Example `on_status` request (if scholarship rejected) 

```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "on_status",
        "version": "0.7.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order": {
            "id": "12424kh",
            "provider": {
                "id": "471",
                "descriptor": {
                    "name": "XYZ Education Foundation",
                    "short_desc" : "Short Description about the Foundation",
                    "images": [
                        {
                            "url" : "url of the image of the provider"
                        }
                    ]
                },
                "rateable": false
            },
            "items": [
                {
                    "id": "SCM_63587501",
                    "descriptor": {
                        "name": "XYZ Education Scholarship for Undergraduate Students",
                        "long_desc": "XYZ Education Scholarship for Undergraduate Students"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "Upto RS.1000 per year"
                    },
                    "time" : {
                        "label" : "Start  & End date of the Application",
                        "range" : {
                            "start" : "2022-09-01T00:00:00.000Z",
                            "end" : "2022-10-31T00:00:00.000Z"
                        }
                    },
                    "rateable": false,
                    "tags": [
                        {
                            "display": true,
                            "descriptor": {
                                "code": "soc-elg",
                                "name": "Social Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "SC"
                                },
                                {
                                    "value" : "ST"
                                },
                                {
                                    "value" : "OBC"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "gen-elg",
                                "name": "Gender Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Female"
                                },
                                {
                                    "value" : "Transgender"
                                }]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "fin-elg",
                                "name": "Financial Eligibility"
                            },
                            "list": [
                                {
                                    "value" : "Max Family Income - Rs.500000.00"
                                }] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "acad-elg",
                                "name": "Academic Eligibility"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "class",
                                        "name": "Class"
                                    },
                                    "value": "12th"
                                },
                                {
                                    "descriptor": {
                                        "code": "percentage",
                                        "name": "Percentage"
                                    },
                                    "value": ">= 50"
                                }

                            ] 
                            
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "docs-reqd",
                                "name": "Documents Required"
                            },
                            "list": [
                                {
                                    "value" : "10th Marksheet"
                                },
                                {
                                    "value" : "Aadhar Card of the Student"
                                },
                                {
                                    "value" : "Aadhar Card of the Parent"
                                },
                                {
                                    "value" : "Pan Card of the Parent"
                                }
                            ]
                        },
                        {
                            "display": true,
                            "descriptor": {
                                "code": "add-info",
                                "name": "Additional Information"
                            },
                            "list": [
                                {
                                    "descriptor": {
                                        "code": "faq-url",
                                        "name": "Frequently Asked Questions's URL"
                                    },
                                    "value" : "https://www.xyz-scholarship.com/faq" 
                                },
                                {
                                    "descriptor": {
                                        "code": "tnc-url",
                                        "name": "Terms and Conditions's URL"
                                    },
                                    "value": "https://www.xyz-scholarship.com/tnc"
                                }
                            ]
                        }
                    ],
                    "location_ids": ["L1","L2"],
                    "fulfillment_ids": [
                        "VSP_FUL_1113"
                    ]
                }
            ],
            "billing": {
                "name": "Manjunath",
                "organization": {
                    "descriptor": {
                        "name": "Namma Yatri",
                        "code": "nammayatri.in"
                    },
                    "contact": {
                        "phone": "+91-8888888888",
                        "email": "scholarships@nammayatri.in"
                    }
                },
                "address": "No 27, XYZ Lane, etc",
                "phone": "+91-9999999999"
            },
            "fulfillments": [
                {
                    "state" : {
                        "descriptor" : {
                            "code": "SCHOLARSHIP-REJECTED",
                            "name" : "Application Rejected",
                            "short_desc" : "Application is rejected due to inappropriate Informaion"
                        },
                        "updated_at" : "2023-02-06T09:55:41.161Z"
                    },
                    "id": "VSP_FUL_1113",
                    "type": "SCHOLARSHIP",
                    "tracking": false,
                    "agent" : {
                        "person" : {
                            "name" : "Ekstep Foundation SPoc"
                        },
                        "contact" : {
                            "email" : "ekstepsupport@ekstep.com"
                        }
                    },
                    "customer": {
                        "id": "aadhaar:798677675565",
                        "person": {
                            "name": "Jane Doe",
                            "age": "13",
                            "gender": "female"
                        },
                        "contact": {
                            "phone": "+91-9663088848",
                            "email": "jane.doe@example.com"
                        }
                    }
                }
            ],
            "cancellation_terms" : [
                {
                    "cancellation_fee" : {
                        "amount" : {
                            "currency" : "INR",
                            "value" : "Penalty upto 5,00,000 INR"
                        }
                    }
                }

            ],
            "docs": [
                {
                    "descriptor":{
                        "name" :"Application Details",
                        "short_desc" : "To open this document, enter the password sent to your email mayan****@***.com"
                    },
                    "url" : "https://link-to-the-document.com",
                    "mime_type" : "application/pdf"
                }
            ],
            "payments" : [
                {
                    "params" :{
                        "bank_code": "IFSC_Code_Of_the_bank",
                        "bank_account_number" :"121212121212",
                        "bank_account_name" : "Account Holder Name"
                    }
                   
                }
            ],
            "quote" :{
                "price" : {
                    "currency" : "INR",
                    "value" : "250000"
                },
                "breakup":[
                    {
                        "title": "Tution fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "150000"
                        }
                    },
                    {
                        "title": "Hostel fee",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    },
                    {
                        "title": "Books",
                        "price" : {
                            "currency" : "INR",
                            "value" : "50000"
                        }
                    }
                ]
            }
        }
    }
}
```

#### Example `track` request
```json
{
    "context": {
        "domain": "dsep:scholarships",
        "location": {
            "city": {
                "name": "Bangalore",
                "code": "std:080"
            },
            "country": {
                "name": "India",
                "code": "IND"
            }
        },
        "action": "track",
        "version": "1.1.0",
        "bap_id": "ps-bap-network.becknprotocol.io",
        "bap_uri": "https://ps-bap-network.becknprotocol.io/",
        "bpp_id": "beckn-sandbox-bpp.becknprotocol.io",
        "bpp_uri": "https://sandbox-bpp-network.becknprotocol.io/",
        "transaction_id": "a9aaecca-10b7-4d19-b640-022723112309",
        "message_id": "a9aaecca-10b7-4d19-b640-b047a7c60009",
        "timestamp": "2023-02-06T09:55:41.161Z",
        "ttl": "PT10M"
    },
    "message": {
        "order_id" : "12424kh"
    }
}
```
#### Example `track_response` request 
```json
{
    "message": {
      "ack": {
        "status": "NACK"
      }
    },
    "error": {
      "code": "40001",
      "paths": "",
      "message": "API Endpoint is not implemented by the BPP"
    }
}
```
