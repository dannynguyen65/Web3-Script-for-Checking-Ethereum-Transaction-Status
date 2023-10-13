# Checking-Ethereum-Transaction-Status    
Web3 script that allows you to retrieve the current gas price on the Ethereum network
const Web3 = require('web3');

// Connect to the Ethereum network
const web3 = new Web3('https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID');

// Get the current gas price
async function getGasPrice() {
  try {
    const gasPrice = await web3.eth.getGasPrice();
    return web3.utils.fromWei(gasPrice, 'gwei');
  } catch (error) {
    console.error('Failed to retrieve gas price:', error);
    return null;
  }
}

// Usage example
(async () => {
  const gasPrice = await getGasPrice();
  console.log(`Current gas price: ${gasPrice} Gwei`);
})();
