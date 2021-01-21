const matrix = [
  [-3, 2, 3, 4],
  [1, 7, 10, 14],
  [1, 2, 3, 4],
  [1, 2, 3, 4]
]

console.log(isSpecialElement(1, 2, matrix));

function isSpecialElement(elRowIndex, elColumnIndex, matrix) {
  const choosenElement = matrix[elRowIndex][elColumnIndex]
  const sum = sumColumnElements(elRowIndex, elColumnIndex, matrix)

  // check
  if (sum < choosenElement) {
    const left = isLeftSideElsSmaller(elRowIndex, elColumnIndex, matrix)
    const right = left && isRightSideElsBigger(elRowIndex, elColumnIndex, matrix)
    return left && right
  }
  
  return false
}

function sumColumnElements(elRowIndex, elColumnIndex, matrix) {
  let sum = 0

  for (let rowIndex = 0; rowIndex < matrix.length; rowIndex++) {
    // without current element value
    if (rowIndex !== elRowIndex) sum += matrix[rowIndex][elColumnIndex];
  }

  return sum
}

function isLeftSideElsSmaller(elRowIndex, elColumnIndex, matrix) {
  if (!elColumnIndex) return false

  const choosenElement = matrix[elRowIndex][elColumnIndex]

  for (let colIndex = 0; colIndex < elColumnIndex; colIndex++) {
    const element = matrix[elRowIndex][colIndex];
    if (element > choosenElement) return false
  }

  return true
}

function isRightSideElsBigger(elRowIndex, elColumnIndex, matrix) {
  if (matrix[elRowIndex].length - 1 === elColumnIndex) return false

  const choosenElement = matrix[elRowIndex][elColumnIndex]

  for (let colIndex = elColumnIndex + 1; colIndex < matrix[elRowIndex].length; colIndex++) {
    const element = matrix[elRowIndex][colIndex];
    if (element < choosenElement) return false
  }

  return true
}
