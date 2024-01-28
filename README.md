  // Measures of Central Tendency

class DescriptiveStatistics 
    static mean(numbers) {
      const sum = numbers.reduce((acc, num) => acc + num, 0);
      return sum / numbers.length;
    }
    
  
    static median(numbers) {
      const sortedNumbers = numbers.slice().sort((a, b) => a - b);
      const middle = Math.floor(sortedNumbers.length / 2);
  
      if (sortedNumbers.length % 2 === 0) {
        return (sortedNumbers[middle - 1] + sortedNumbers[middle]) / 2;
      } else {
        return sortedNumbers[middle];
      }
    }
    
  //TO CALCULATE MODE
  
    static mode(numbers) {
      return numbers[0];
    }
  
    // Measures of Dispersion
    static range(numbers) {
      const max = Math.max(...numbers);
      const min = Math.min(...numbers);
      return max - min;
    }
  
    static variance(numbers) {
      const meanValue = this.mean(numbers);
      const squaredDifferences = numbers.map(num => Math.pow(num - meanValue, 2));
      return this.mean(squaredDifferences);
    }
  
    static standardDeviation(numbers) {
      return Math.sqrt(this.variance(numbers));
    }
    

  
  // INSTANTIATION
  const data = [2, 5, 4, 6, 2, 5, 34, 6, 12,  8, 10, 4, 7];
  console.log(`Mean: ${DescriptiveStatistics.mean(data)}`);
  console.log(`Median: ${DescriptiveStatistics.median(data)}`);
  console.log(`Mode: ${DescriptiveStatistics.mode(data)}`);
  console.log(`Range: ${DescriptiveStatistics.range(data)}`);
  console.log(`Variance: ${DescriptiveStatistics.variance(data)}`);
  console.log(`Standard Deviation: ${DescriptiveStatistics.standardDeviation(data)}`);
  
