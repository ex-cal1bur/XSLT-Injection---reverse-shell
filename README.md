# XSLT Injection - Technical Analysis

## 🔍 What is XSLT Injection?

XSLT (Extensible Stylesheet Language Transformations) is a language for transforming XML documents. XSLT injection occurs when an application allows an attacker to control or modify XSLT stylesheets that are executed on the server.

## ⚡ Exploitation Mechanism

### Main Vector: exsl:document
The specific vulnerability exploited by this project is the abuse of the EXSLT `exsl:document` extension, which allows files to be written during the XSLT transformation process.

### Attack Flow
1. **Injection**: Malicious XSLT is provided to a vulnerable processor
2. **File Write**: `exsl:document` writes arbitrary files to the system
3. **Execution**: The written files can be executable scripts
4. **Access**: A reverse shell connection is established

## 🛠️ Necessary Conditions

For this attack to work, the environment must have:

- XSLT processor with support for EXSLT extensions
- Write permissions in the file system
- Ability to execute the created files
- No validation of XSLT inputs

## 🎯 Potential Impact

- **Remote command execution** (RCE)
- **Reverse shell** on the server
- **Arbitrary writing** of files
- **Complete compromise** of the system

---

*Project for educational purposes in controlled environments*
