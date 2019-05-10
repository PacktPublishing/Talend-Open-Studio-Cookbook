package routines;

/*
 * user specification: the function's comment should contain keys as follows: 1. write about the function's comment.but
 * it must be before the "{talendTypes}" key.
 * 
 * 2. {talendTypes} 's value must be talend Type, it is required . its value should be one of: String, char | Character,
 * long | Long, int | Integer, boolean | Boolean, byte | Byte, Date, double | Double, float | Float, Object, short |
 * Short
 * 
 * 3. {Category} define a category for the Function. it is required. its value is user-defined .
 * 
 * 4. {param} 's format is: {param} <type>[(<default value or closed list values>)] <name>[ : <comment>]
 * 
 * <type> 's value should be one of: string, int, list, double, object, boolean, long, char, date. <name>'s value is the
 * Function's parameter name. the {param} is optional. so if you the Function without the parameters. the {param} don't
 * added. you can have many parameters for the Function.
 * 
 * 5. {example} gives a example for the Function. it is optional.
 */
public class validationCompleted {

    /**
     * validateCustomerAge: Check customer is 18 or over for UK, 21 or over for rest of world.
     * returns true if valid, false if invalid
     * e.g. validateCustomerAge(23,"UK")
     * 
     * {talendTypes} Boolean
     * 
     * {Category} Validation
     * 
     * {param} string(age) input: Customer age
     * {param} string(country) input: Customer country
     *  
     * {example} validateCustomerAge(23,"UK") # true
     */
    public static Boolean validateCustomerAge(Integer customerAge, String customerCountry) {
        if (customerAge == null || customerCountry == null) {
        	return false;
        } else
        	if (customerCountry.equals("UK".toUpperCase()) && customerAge >= 18){
        		return true;
        	} else {
		    	if (!(customerCountry.equals("UK".toUpperCase())) && customerAge >= 21){
		    		return true;
		    	} else {
		    		return false;
		    	}
        	}
        }
	}
