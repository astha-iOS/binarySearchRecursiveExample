# binarySearchRecursiveExample


let numbers = [1,2,3,4,5,6,7,8,9,10,14,15,17,18,20,21]

func binarySearch(array:[Int],key:Int) -> Bool{
	
	if array.count == 0 { return false }
	
	let minIndex = 0
	let maxIndex = array.count - 1
	let midIndex = maxIndex/2 
	let midValue = array[midIndex]
	
	
	if key > array[maxIndex] || key < array[minIndex]{
		print("key is not in the array 1")
		return false
	}
	
	if key > midValue {
	
		let slice = Array(array[midIndex + 1...maxIndex])
		return binarySearch(array:slice,key:key)
	
	}
	
	if key < midValue {
	let slice = Array(array[minIndex...midIndex - 1])
		return binarySearch(array:slice,key:key)
	}

    if key == midValue {
		print("key is found in the array 2")
		return true

	}

	return false
}

let status : Bool = binarySearch(array:numbers,key:14)
print(status)
