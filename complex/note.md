user: postgres
pas: tkpark319
databasename: fibvalues


{
    "AWSEBDockerrunVersion": 2,
    "containerDefinitions": [
        {
            "name": "client",
            "image": "thetkpark/multi-client", 
            "hostname": "client", 
            "essential": false,
            "memory": 128
        },
        {
            "name": "server",
            "image": "thetkpark/multi-server",
            "hostname": "api",
            "essential": false,
            "memory": 128
        },
        {
            "name": "worker",
            "image": "thetkpark/multi-worker",
            "hostname": "worker",
            "essential": false,
            "memory": 128
        },
        {
            "name": "nginx",
            "image": "thetkpark/multi-worker",
            "essential": true,
            "portMappings": [
                {
                    "hostPort": 80,
                    "containerPort": 80
                }
            ],
            "links": ["client", "server"],
            "memory": 128
        }
    ]

}



{
    "AWSEBDockerrunVersion": 2,
    "containerDefinitions": [
      {
        "name": "client",
        "image": "thetkpark/multi-client",
        "hostname": "client",
        "essential": false,
        "memory": 128
      },
      {
        "name": "server",
        "image": "thetkpark/multi-server",
        "hostname": "api",
        "essential": false,
        "memory": 128
      },
      {
        "name": "worker",
        "image": "thetkpark/multi-worker",
        "hostname": "worker",
        "essential": false,
        "memory": 128
      },
      {
        "name": "nginx",
        "image": "thetkpark/multi-nginx",
        "hostname": "nginx",
        "essential": true,
        "portMappings": [
          {
            "hostPort": 80,
            "containerPort": 80
          }
        ],
        "links": ["client", "server"],
        "memory": 128
      }
    ]
  }