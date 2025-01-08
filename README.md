# Minimal API DefaultResponseTransfomer

This Transformer adds a default (error) response to all the endpoints. However, even if the Transformer uses the same object to define the Schema, it is repeated for every endpoint:

```json
"paths": {
    "/api/ping": {
        "get": {
            "tags": [
                "DefaultResponseTransformer"
            ],
            "responses": {
                "200": {
                    "description": "OK"
                },
                "default": {
                    "description": "Error",
                    "content": {
                        "application/problem+json": {
                            "schema": {
                                "type": "object",
                                "properties": {
                                    "type": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "title": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "status": {
                                        "type": "integer",
                                        "format": "int32",
                                        "nullable": true
                                    },
                                    "detail": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "instance": {
                                        "type": "string",
                                        "nullable": true
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    },
    "/api/pong": {
        "get": {
            "tags": [
                "DefaultResponseTransformer"
            ],
            "responses": {
                "200": {
                    "description": "OK"
                },
                "default": {
                    "description": "Error",
                    "content": {
                        "application/problem+json": {
                            "schema": {
                                "type": "object",
                                "properties": {
                                    "type": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "title": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "status": {
                                        "type": "integer",
                                        "format": "int32",
                                        "nullable": true
                                    },
                                    "detail": {
                                        "type": "string",
                                        "nullable": true
                                    },
                                    "instance": {
                                        "type": "string",
                                        "nullable": true
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
```
