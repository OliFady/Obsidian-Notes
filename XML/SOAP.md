- A SOAP message MUST be encoded using XML (WSDL) Web Service Description Language
- A Service queries UDDI to get the WSDL
- A SOAP message MUST use the SOAP Envelope namespace (it's the root element)
- The SOAP mustUnderstand attribute can be used to indicate whether a header entry is mandatory or optional for the recipient to process.
- The SOAP actor attribute is used to address the Header element to a specific endpoint.
- The optional SOAP Fault element is used to indicate error messages.

```xml 
<?xml version="1.0"?>  
  
<soap:Envelope  
xmlns:soap="http://www.w3.org/2003/05/soap-envelope/"  
soap:encodingStyle="http://www.w3.org/2003/05/soap-encoding">  
  
<soap:Header>  
  <m:Trans xmlns:m="https://www.w3schools.com/transaction/"  
  soap:mustUnderstand="1">234
  soap:actor="https://www.w3schools.com/code/">234
  </m:Trans>
</soap:Header>  
  
<soap:Body>  
  <m:GetPriceResponse xmlns:m="https://www.w3schools.com/prices">  
    <m:Price>1.90</m:Price>  
  </m:GetPriceResponse>
  <soap:Fault>  
  ...  
  </soap:Fault>  
</soap:Body>  
  
</soap:Envelope>
```