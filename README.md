# ElectrumxNovoNode-Docker

First version of a Docker to join electrumx and the Novo node in the same image. Both are running at the same time and they are connected to each other. For now it is not persistent by default and if you stop the container and start it again, you will need to synchronize the whole node and then electrumx, which is about 6-10 hours.

### TO GENERATE IMAGE

```docker build -t electrumx_novo-node .```

### TO RUN THE IMAGE WITH A SPECIFIC NAME

```docker run -p 50010:50010 -p 50012:50012 --name my_electrumx electrumx_novo-node```

### VERIFY BLOCKCHAINPROGRESS 
When dockerfile runs successfully wait until blockchain is synced  by running in docker terminal  
it start with 1.26e-8  it complete when verifyprogress=0.99

``` novod getblockchaininfo ```


### TO STOP THE CONTAINER

```docker stop NAME_CONTAINER```

### CONNECT TO THE SERVER WITH ELECTRON-NOVO
If you are running locally, you need to know the IP of the container and see the IP in IPAddress:

```docker inspect NAME_CONTAINER```

