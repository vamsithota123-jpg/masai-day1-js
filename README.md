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



### Q2: Multi-level Filtering (10 mins)

Filter users who have completed at least 2 courses with a rating above 4.0.

function filterUsers(users) {
  return users.filter(user => {
    let count = 0;

    for (let i = 0; i < user.courses.length; i++) {
      const course = user.courses[i];

      if (course.completed && course.rating > 4.0) {
        count++;
      }
    }

    return count >= 2;
  });
}

console.log(filterUsers(users));
 output:
 [
  {
    id: 1,
    name: 'Alice',
    courses: [...]
  },
  {
    id: 3,
    name: 'Charlie',
    courses: [...]
  }
]

