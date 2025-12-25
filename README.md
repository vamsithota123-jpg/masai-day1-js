"# masai-day1-js" 

const products = [
  ['Electronics', 'Laptop', 999],
  ['Clothing', 'Shirt', 29],
  ['Electronics', 'Mouse', 25],
  ['Clothing', 'Pants', 49],
  ['Electronics', 'Keyboard', 75],
  ['Clothing', 'Jacket', 89]
];


function categorizeProducts(products) {
  const result = {};

  for (let i = 0; i < products.length; i++) {
    const [category, name, price] = products[i];

    if (!result[category]) {
      result[category] = [];
    }

    result[category].push({ name, price });
  }

  
  for (let category in result) {
    result[category].sort((a, b) => a.price - b.price);
  }

  return result;
}

console.log(categorizeProducts(products));

