package array;

import java.util.HashMap;

public class GCD {
	
	public static void main(String[] args) {
		
		int[] arr = {1,2,3,4,4,3,2,1};
		System.out.println(hasGroupsSizeX(arr));
	}
	
		public static boolean hasGroupsSizeX(int[] deck) {
        
        HashMap<Integer, Integer> map = new HashMap<>();
        
        if(deck.length < 2) return false;
        
        for(int i = 0; i < deck.length; i++) {
            
            map.put(deck[i], map.getOrDefault(deck[i], 0) + 1);
        }
        
        int res = 0;
        
        for(Integer i : map.values()) {
            
            res = getGcd(res, i);
            
        }
        if(res == 1) return false;
        return true;
    }
    
    public static int getGcd(int res, int val) {
        if(val == 0) return res;
        return getGcd(val, res % val);
    }
}
