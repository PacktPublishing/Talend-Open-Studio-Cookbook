package routines;

import java.io.BufferedInputStream;
import java.io.BufferedReader;
import java.io.File;
import java.io.StringReader;
import java.io.StringWriter;
import org.xml.sax.InputSource;
import java.io.InputStreamReader;
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.transform.Transformer;
import javax.xml.transform.TransformerFactory;
import javax.xml.transform.dom.DOMSource;
import javax.xml.transform.stream.StreamResult;
import javax.xml.transform.OutputKeys;
import javax.xml.xpath.*;
import org.w3c.dom.Document;
import org.w3c.dom.Element;
import org.w3c.dom.Node;
import org.w3c.dom.NodeList;

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
public class XMLUtils {

    /**
     * DOMToString: printDom to String.
     * 
     * 
     * {talendTypes} Document
     * 
     * {Category} User Defined
     * 
     * {param} Document input: The document to be printed.
     * 
     * {example} DOMToString(myDocument) # printed XML document.
     */
    public static String DOMToString(Document doc) {
    	try {
		TransformerFactory transFactory = TransformerFactory.newInstance();
		Transformer transformer = transFactory.newTransformer();
		StringWriter buffer = new StringWriter();
		transformer.setOutputProperty(OutputKeys.OMIT_XML_DECLARATION, "yes");
		transformer.transform(new DOMSource(doc),new StreamResult(buffer));
		String str = buffer.toString();
		return str;
    	}catch(Exception e){
            //TODO log error
    		System.out.println("XML Print Error: "+e);
            return null;
        } 
    }
    /**
     * NodeToString: convert DOM Node to String.
     * 
     * 
     * {talendTypes} Node
     * 
     * {Category} User Defined
     * 
     * {param} Document input: The document to be printed.
     * 
     * {example} NodeToString(myDocument) # XML string.
     */
    public static String NodeToString(Node node) {
    	try {
		TransformerFactory transFactory = TransformerFactory.newInstance();
		Transformer transformer = transFactory.newTransformer();
		StringWriter buffer = new StringWriter();
		transformer.setOutputProperty(OutputKeys.OMIT_XML_DECLARATION, "yes");
		transformer.transform(new DOMSource(node),new StreamResult(buffer));
		String str = buffer.toString();
		return str;
    	}catch(Exception e){
    		System.out.println("XML Node to string Error: "+e);
            return null;
        } 
    }
    public static Document createDomFromString(String xml) {
    	try {
			   DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
			   factory.setNamespaceAware(true);
			   DocumentBuilder builder = factory.newDocumentBuilder();
			   Document doc = builder.parse(new InputSource(new StringReader(xml)));
			   return doc;
    	}catch(Exception e){
    		System.out.println("XML String to dom Error: "+e);
    		e.printStackTrace();
            return null;
        } 
    }
    public static Document addChildAtPath(Document doc, String xpathString, String newChildString) {
    	try {
    			/* get the first node matching the XPATH */
    			XPath xPath = XPathFactory.newInstance().newXPath();
    			NodeList nodes = (NodeList)xPath.evaluate(xpathString,doc.getDocumentElement(), XPathConstants.NODESET);
    			
    			/* create new child element and import into doc */
    			Element newChildElement = XMLUtils.createDomFromString(newChildString).getDocumentElement();
    			Node newChildNode = doc.importNode(newChildElement, true);
    			
    			/* append the new child to the parent of the node found*/
    			nodes.item(0).appendChild(newChildNode);     
    			
			   return doc;
    	}catch(Exception e){
    		System.out.println("XML addChildAtPath error: "+e);
    		e.printStackTrace();
            return null;
        } 
    }

}
