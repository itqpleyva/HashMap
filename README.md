# HashMap
Repo to Study HasMap Collection

public class HashMapMain {

	public static void main(String[] args) {
		
		HashMap<Integer,String> hashmap = new HashMap<Integer, String>();
		
		//inserting data in hashmap
		
		hashmap.put(1, "First value");
		hashmap.put(2, "Second value");
		hashmap.put(3, "Third value");
		hashmap.put(4, "Fourth value");
		hashmap.put(5, "Fifth value");
		System.out.println("Printing elements in HashMap");
		System.out.println(hashmap);	
		//iterating hashmap
		System.out.println("---------------------------------------------------");
		System.out.println("Printing elements in HashMap using lambda expresion");
		hashmap.forEach(
					(temp,temp1)->{					
						System.out.println("Key: "+ temp + " -----Value: "+ temp1);				
					}			
				);
		System.out.println("---------------------------------------------------");
		System.out.println("Printing elements in HashMap using iterator");
		Iterator iterator = hashmap.entrySet().iterator();
		while (iterator.hasNext()) {
			System.out.println(iterator.next());		
		}
		
		System.out.println("---------------------------------------------------");
		System.out.println("Printing Keys in HashMap using keySet()");
		hashmap.keySet().forEach(System.out::println);
		
		System.out.println("---------------------------------------------------");
		System.out.println("Printing Values in HashMap using values()");
		hashmap.values().forEach(System.out::println);
		
		System.out.println("---------------------------------------------------");
		System.out.println("Get element value by index in hashmap");// start with 1, not 0
		System.out.println(hashmap.get(1));
		
		System.out.println("---------------------------------------------------");
		System.out.println("Get element by value in hashmap");// start with 1, not 0
		Set<Entry<Integer, String>> keyvalue = hashmap.entrySet()
				.stream()
				.filter(a -> a.getValue() == "First value").collect(Collectors.toSet());	
		System.out.println(keyvalue);
		
		System.out.println("---------------------------------------------------");
		System.out.println("Get element by key in hashmap");// start with 1, not 0
		Set<Entry<Integer, String>> value = hashmap.entrySet()
				.stream()
				.filter(a -> a.getKey() == 2).collect(Collectors.toSet());	
		System.out.println(value);
		
		System.out.println("---------------------------------------------------");
		System.out.println("Get element value by key in hashmap");// start with 1, not 0
		String value1 = hashmap.entrySet()
				.stream()
				.filter(a -> a.getKey() == 2)
				.map(a -> a.getValue()).findFirst().orElse("No existe");
		
		System.out.println(value1);
		
		System.out.println("---------------------------------------------------");
		System.out.println("Get element key by value in hashmap");// start with 1, not 0
		int value2 = hashmap.entrySet()
				.stream()
				.filter(a -> a.getValue() == "Second value")
				.map(a -> a.getKey()).findFirst().orElse(0);
		
		System.out.println(value2);

	}		

}

