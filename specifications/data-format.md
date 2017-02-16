
### Data Format

#### Session

##### GET: /session

    {
    "UserProfiles": {
        "u_id": "",
        "name": "",
        "role": ""
        }
    }

##### POST: /session/login

    {
    "UserProfiles": {
        "name": "",
        "password": ""
        }
    }

##### POST: /session/logout

    {
    "UserProfiles": {
        "u_id": "",
        }
    }

#### Users & roles

##### GET:/user/role

    {
    "UserRoles": {
        "r_id": "",
        "name": "",
        "level": ""
        }
    }

##### GET:/user/role

    {
    "UserRoles": {
        "r_id": "",
        "name": "",
        "level": ""
        }
    }

##### GET: /user?role=:role&limit=100&offset=0

    {
        "UserProfiles": {
            "u_id": "",
            "name": "",
            "role": {
                "r_id": "",
                "name": "",
                "level": ""
            }
        }
    }

##### POST: /user

    {
        "UserProfiles": {
            "role": {
                "r_id": ""
            },
            "firstname": "",
            "lastname": "",
            "email": "",
            "phone": "",
            "password": "",
            "created_at": "",
            "created_by": ""
        }
    }

##### GET: /user/:user

    {
        "UserProfiles": {
            "u_id": "",
            "role": {
                "r_id": ""
                },
            "firstname ": "",
            "lastname": "",
            "email": "",
            "phone": "",
            "password": "",
            "created_at": "",
            "created_by": ""
        }
    }

##### PUT: /user/:user

    {
        "UserProfiles": {
            "u_id": "",
            "role": {
                "r_id": ""
                },
            "firstname ": "",
            "lastname": "",
            "email": "",
            "phone": "",
            "password": "",
            "created_at": "",
            "created_by": ""
        }
    }

##### DELETE: /user/:user

    {
    "UserProfiles": {
        "u_id": ""
        }
    }

##### PUT: /user/:user:/role

    {
    "UserProfiles": {
        "u_id": "",
        "role": {         
            "r_id": "",
            "name": "",
            "level": ""
            } 
        }
    }

#### Nodes

##### GET: /node?type=:type&limit=100&offset=0

    {
    "Nodes": {
        "n_id": "",
        "instance": {

            },
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### POST: /node

    {
    "Nodes": {
        "n_id": "",
        "instance": "",
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        }
    }

##### GET: /node/:node

    {
    "Nodes": {
        "n_id": "",
        "instance": "",
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        }
    }

##### PUT: /node/:node

    {
    "Nodes": {
        "n_id": "",
        "instance": "",
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        }
    }

##### DELETE: /node/:node

    {
    "Nodes": {
        "n_id": ""
        }
    }

#### Tools

##### GET: /tool?type=:type&limit=100&offset=0

    {
    "Tools": {
        "t_id: "",
        "hostname": "",
        "ip": "",
        "type": ""
        }
    }

##### POST: /tool

    {
    "Tools": {
        "t_id: "",
        "hostname": "",
        "ip": "",
        "type": ""
        }
    }

##### GET: /tool/:tool

    {
    "Tools": {
        "t_id: "",
        "hostname": "",
        "ip": "",
        "type": ""
        }
    }

##### PUT: /tool/:tool

    {
    "Tools": {
        "t_id: "",
        "hostname": "",
        "ip": "",
        "type": ""
        }
    }

##### DELETE: /tool/:tool

    {
    "Tools": {
        "t_id: ""
        }
    }

#### Parameters

##### GET: /parameter?type=:type&limit=100&offset=0

    {
    "Parameters": {
        "p_id": "",
        "key": "",
        "description": "",
        "type": "",
        "deprecated": "",
        "created_at": "",
        "created_by": ""
        }
    }

##### POST: /parameter

    {
    "Nodes": {
        "key": "",
        "description": "",
        "type": ""
        }
    }

##### GET: /parameter/:parameter

    {
    "Nodes": {
        "p_id": "",
        "key": "",
        "description": "",
        "type": "",
        "deprecated": "",
        "created_at": "",
        "created_by": ""
        }
    }

##### DELETE: /parameter/:parameter

    {
    "Nodes": {
        "p_id": "",
        "key": "",
        }
    }

##### PUT: /parameter/:parameter/deprecated

    {
    "Nodes": {
        "p_id": "",
        "deprecated": "",
        }
    }

#### Respositories

##### GET: /repository

    {
    "Respositories": {
        "r_id": "",
        "name": "",
        "organization": "",
        "url": ""
        }
    }

##### GET: /repository/:repository

    {
    "Respositories": {
        "r_id": "",
        "name": "",
        "organization": "",
        "url": ""
        }
    }

#### Instances

##### GET: /instance?type=:type&limit=100&offset=0

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }
##### POST: /instance

    {
    "Instance": {
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### GET: /instance/:instance

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### PUT: /instance/:instance

    {
    "Instance": {
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### DELETE: /instance/:instance

    {
    "Instance": {
        "i_id": "",
        "name": "",
        }
    }

##### GET: /instance/:instance/node

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "Nodes": {
        "n_id": "",
        "instance": "",
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### POST: /instance/:instance/node

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "Nodes": {
        "n_id": "",
        "instance": "",
        "hostname": "",
        "type": {
            "virtual": {
                "ip": "",
                "mac": "",
                "cpu": "",
                "memory": "",
                "host": ""
                },
            "physical": {
                "ip": "",
                "cpu": "",
                "memory":
                }
            }
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### DELETE: /instance/:instance/node/:node

    {
    "Instance": {
        "i_id": "",
        "name": ""
    },
    "Nodes": {
        "n_id": "",
        "name": ""
        }
    }

##### GET: /instance/:instance/configuration

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "ConfigurationValues": {
        "c_id": "",
        "parameters": "",
        "instance": "",
        "i_value": "",
        "t_value": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### POST: /instance/:instance/configuration

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "ConfigurationValues": {
        "c_id": "",
        "parameters":  {
            "p_id": ""
            },
        "instance": "",
        "i_value": "",
        "t_value": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        }
    }

##### PUT: /instance/:instance/configuration/:parameter

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "ConfigurationValues": {
        "c_id": "",
        "Parameters": {
            "p_id": "",
            "key": "",
            "description": "",
            "type": "",
            "deprecated": "",
            "created_at": "",
            "created_by": ""
        },
        "instance": "",
        "i_value": "",
        "t_value": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    }

##### DELETE: /instance/:instance/configuration/:parameter

    {
    "Instance": {
        "i_id": ""
        },
    "ConfigurationValues": {
        "c_id": "",
        "parameters": ""
        },
    "Parameters": {
        "p_id": ""
        }
    }

##### GET: /instance/:instance/tool

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "InstanceTools": {
        "i_id": "",
        "Tools": {
            "t_id: "",
            "hostname": "",
            "ip": "",
            "type": ""
        },
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    }

##### POST: /instance/:instance/tool

    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "InstanceTools": {
        "i_id": "",
        "Tools": {
            "t_id: "",
            "hostname": "",
            "ip": "",
            "type": ""
        },
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    }

##### DELETE: /instance/:instance/tool/:tool


    {
    "Instance": {
        "i_id": "",
        "name": "",
        "description": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": ""
        },
    "InstanceTools": {
        "i_id": "",
        "Tools": {
            "t_id: "",
            "hostname": "",
            "ip": "",
            "type": ""
            },
        }
    }

##### GET: /instance/:instance/version

    {
    "Instance": {
        "i_id": "",
        },
    "Version": {
        "v_id": "",
        "repo": "",
        "ref": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": "",
        }
    }

##### POST: /instance/:instance/version/:repository

    {
    "Instance": {
        "i_id": "",
        },
    "Version": {
        "v_id": "",
        "repo": {
            "r_id": "",
            "name": "",
            "organization": "",
            "url": ""
            }
        "ref": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": "",
        }
    }

##### PUT: /instance/:instance/version/:repository

    {
    "Instance": {
        "i_id": "",
        },
    "Version": {
        "v_id": "",
        "repo": {
            "name": "",
            "organization": "",
            "url": ""
            }
        "ref": "",
        "created_at": "",
        "created_by": "",
        "sync_at": "",
        "sync_by": "",
        }
    }

##### DELETE: /instance/:instance/version/:repository

    {
    "Instance": {
        "i_id": "",
        },
    "Version": {
        "v_id": "",
        "repo": {
            "name": "",
            }
        "ref": "",
        }
    }

#### Deployment

##### POST: /deployment/:instance

##### POST: /deployment/:instance/node

##### POST: /deployment/:instance/node/:node

##### POST: /deployment/:instance/configuration

##### POST: /deployment/:instance/configuration/:parameter

##### POST: /deployment/:instance/tool

##### POST: /deployment/:instance/tool/:tool

##### POST: /deployment/:instance/version

##### POST: /deployment/:instance/version/:repository



