package mainPackage;

public class DataStore {
	public static int firstResponseActivated = 0;
	public DataStore() {	
	
	if (firstResponseActivated == 1) {
		Starter.firstResponseOveruse++;
		firstResponseActivated--;
	}
}
}
