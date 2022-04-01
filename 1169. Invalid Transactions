class Solution {
    class Transaction{
        String name;
        int time;
        int amount;
        String city;
        public Transaction(String name, int time, int amount, String city){
            this.name = name;
            this.time = time;
            this.amount = amount;
            this.city = city;
        }
    }
    public List<String> invalidTransactions(String[] transactions) {
        List<String> result = new ArrayList<>();
        Map<String, List<Transaction>> map = new HashMap<>();
        
        for(int i=0; i<transactions.length; i++){
            String[] values = transactions[i].split(",");
            Transaction t = new Transaction(values[0], Integer.valueOf(values[1]), Integer.valueOf(values[2]), values[3]);
            map.putIfAbsent(t.name, new ArrayList<>());
            map.get(t.name).add(t);
        }
        for(int i=0; i<transactions.length; i++){
            String[] values = transactions[i].split(",");
            Transaction t = new Transaction(values[0], Integer.valueOf(values[1]), Integer.valueOf(values[2]), values[3]);
            if(!isInvalid(t, map.getOrDefault(t.name, new ArrayList<>()))){
                result.add(transactions[i]);
            }
        }
        return result;
    }
    public boolean isInvalid(Transaction t, List<Transaction> list){
        if(t.amount > 1000){
			return false;
		}
        for(Transaction other : list){
            if(Math.abs(other.time - t.time) <= 60 && !other.city.equals(t.city)){
				return false;
			}
        }
        return true;
    }
}
