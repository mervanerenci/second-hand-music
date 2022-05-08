# NEAR FASHION
With NEAR FASHION, you can create your products on block-chain to sell them and buy a new pants from your favorite brand.

## Deploying Smart Contract
### Login
First, login your testnet account with:
    
    near login
    
### Build
Clone the repo with:
    
    git clone https://github.com/hanmakyol/near-fashion
    

After that run these commands:
    
    yarn
    

    
    yarn build:release
    

    
    near dev-deploy ./build/release/simple.wasm
    

 Now you will see an id looks like "dev-123-456" you can use 
    
    export CONTRACT=<your dev-id>
    
so you wont need to rewrite it everytime

### InApp commands
We have: 
- near call createPants/createShirts : create product
- near view getPants/getShirt : view products
- near view getPantsbyname/getShirtsbyname : view specific pants or shirt via name
- near call purchaseShirtbyname/purchasePantsbyname : buy shirt or pants via name

For Creating Shirt:
    
    near call $CONTRACT createShirt '{"style":" ","name":" ","color":" ","size":" ","price":" ","brand":" ","stock":}' --accountId $CONTRACT
    

For Creating Pants
    
    near call $CONTRACT createPants '{"style":"","name":"","color":"","size":"","price":"","brand":"","stock":}' --accountId $CONTRACT
    

For Getting Pants/Shirt
    
    near view $CONTRACT getPants '{"offset": 0}' /// near view $CONTRACT getShirt '{"offset": 0}'

For Getting Pants/Shirt by Id

    near view $CONTRACT getShirtsbyId '{"id":}' --accountId $CONTRACT

For Purchase Pants/Shirt

    near call $CONTRACT purchasePantsbyId '{"id":""}' --accountId $CONTRACT --amount <amount here>

    near call $CONTRACT purchaseShirtbyId '{"id":""}' --accountId $CONTRACT --amount <amount here>


    




