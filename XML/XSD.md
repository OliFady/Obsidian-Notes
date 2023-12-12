# Data Types
- xs:string
- xs:decimal
- xs:integer
- xs:boolean
- xs:date
- xs:time

```xml
<?xml version="1.0"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
targetNamespace="https://www.w3schools.com"  
xmlns="https://www.w3schools.com"  
elementFormDefault="qualified">

<xs:element name="note">
<xs:complexType>
<xs:sequence>
<xs:element name="title" type="xs:string"/>
<xs:element name="author" type="xs:string"/>
</xs:sequence>
</xs:complexType>
</xs:element>

</xs:schema>
```

- Complex types contains other elements or attribute under them while simple types don't 
- Attributes are always simple types.
- Sequence specifies that the child elements must appear in a specific order
# Restrictions
```xml

Range
    <xs:restriction base="xs:integer">  
      <xs:minInclusive value="0"/>  
      <xs:maxInclusive value="120"/>  
    </xs:restriction>
Enum
    <xs:restriction base="xs:string">  
      <xs:pattern value="[a-z]"/>
      <xs:enumeration value="Audi"/>  
      <xs:enumeration value="Golf"/>  
      <xs:enumeration value="BMW"/>  
    </xs:restriction>
Binary
      <xs:pattern value="male|female"/>
Whitespace
      <xs:whiteSpace value="preserve"/>
```

# Missed
- Groups & Attribute Groups