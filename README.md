class Substring
{
public static void main(String args[])
{
Scanner in=new Scanner(System.in);
String s=in.next();
    if(s==null){
        System.out.println("invalid string");
    }
    else
    {
    int max = 0;
 
    HashMap<Character, Integer> map = new HashMap<Character, Integer>();
    int start=0;
 
    for(int i=0; i<s.length(); i++){
        char c = s.charAt(i);
        if(map.containsKey(c)){
            max = Math.max(max, map.size());    
            while(map.containsKey(c)){
                map.remove(s.charAt(start));
                start++;
            }
 
            map.put(c, i);
        }else{
            map.put(c, i);
        }
    }
 
    max = Math.max(max, map.size());  
 
    return max;
    }
}
}
