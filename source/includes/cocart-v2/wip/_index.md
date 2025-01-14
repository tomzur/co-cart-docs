# Index #

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v2/wip/_index.md)

By default, the API provides information about all available endpoints on the site. Authentication is not required to access the API index.

<aside class="notice">
    Some endpoints are only available in CoCart Pro or via add-on.
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/cocart/v2</h6>
	</div>
</div>

```shell
curl -X GET https://example.com/wp-json/cocart/v2 \
  -H "Content-Type: application/json"
```

```javascript--node
CoCart.get("")
.then((response) => {
  // Successful request
  console.log("Response Status:", response.status);
  console.log("Response Headers:", response.headers);
  console.log("Response Data:", response.data);
})
.catch((error) => {
  // Invalid request, for 4xx and 5xx statuses
  console.log("Response Status:", error.response.status);
  console.log("Response Headers:", error.response.headers);
  console.log("Response Data:", error.response.data);
})
.finally(() => {
  // Always executed.
});
```

```javascript--jquery
$.ajax({
  url: "https://example.com/wp-json/cocart/v2",
  method: "GET",
  dataType: "json",
  contentType: "application/json; charset=utf-8",
  complete: function (response) {
    console.log(response);
  }
});
```

```php
<?php
$curl = curl_init();

curl_setopt_array( $curl, array(
  CURLOPT_URL => "https://example.com/wp-json/cocart/v2",
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'User-Agent: CoCart API/v2',
  )
) );

$response = curl_exec($curl);

curl_close($curl);

echo $response;
```

```php--wp-http-api
<?php
$response = wp_remote_get( 'https://example.com/wp-json/cocart/v2' );
$body = wp_remote_retrieve_body( $response );
```

> JSON response example:

```json
{
    "namespace": "cocart/v2",
    "routes": {
        "/cocart/v2": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "namespace": {
                            "required": false,
                            "default": "cocart/v2"
                        },
                        "context": {
                            "required": false,
                            "default": "view"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2"
                    }
                ]
            }
        },
        "/cocart/v2/get-cart": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/get-cart"
                    }
                ]
            }
        },
        "/cocart/v2/get-cart/(?P<id>[\\w]+)": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ]
        },
        "/cocart/v2/get-cart/customer/(?P<id>[\\d]+)": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ]
        },
        "/cocart/v2/add-item": {
            "namespace": "cocart/v2",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "product_id": {
                            "required": false,
                            "description": "Unique identifier for the product.",
                            "type": "string"
                        },
                        "quantity": {
                            "required": true,
                            "default": 1,
                            "description": "The quantity amount of the item to add to cart.",
                            "type": "float"
                        },
                        "variation_id": {
                            "required": false,
                            "description": "Unique identifier for the variation.",
                            "type": "integer"
                        },
                        "variation": {
                            "required": false,
                            "description": "The variation attributes that identity the variation of the item.",
                            "type": "array"
                        },
                        "cart_item_data": {
                            "required": false,
                            "description": "Additional item data passed to make item unique.",
                            "type": "array"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the cart once item is added.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/add-item"
                    }
                ]
            }
        },
        "/cocart/v2/clear": {
            "namespace": "cocart/v2",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": []
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/clear"
                    }
                ]
            }
        },
        "/cocart/v2/calculate": {
            "namespace": "cocart/v2",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "return": {
                            "required": false,
                            "default": false,
                            "description": "Returns the cart totals once calculated.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/calculate"
                    }
                ]
            }
        },
        "/cocart/v2/count-items": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "return": {
                            "required": false,
                            "default": "numeric"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/count-items"
                    }
                ]
            }
        },
        "/cocart/v2/item": {
            "namespace": "cocart/v2",
            "methods": [
                "GET",
                "POST",
                "DELETE"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        }
                    }
                },
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        },
                        "quantity": {
                            "required": false,
                            "default": 1,
                            "type": "float"
                        }
                    }
                },
                {
                    "methods": [
                        "DELETE"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/item"
                    }
                ]
            }
        },
        "/cocart/v2/logout": {
            "namespace": "cocart/v2",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": []
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/logout"
                    }
                ]
            }
        },
        "/cocart/v2/totals": {
            "namespace": "cocart/v2",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "html": {
                            "required": false,
                            "default": false,
                            "description": "Returns the totals pre-formatted.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v2/totals"
                    }
                ]
            }
        }
    },
    "_links": {
        "up": [
            {
                "href": "https://example.com/wp-json/"
            }
        ]
    }
}
```
