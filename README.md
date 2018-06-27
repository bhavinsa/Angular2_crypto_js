# Angular2_crypto_js

	/* Install crypto-js */
	npm install crypto-js
    npm install @types/crypto-js --save-dev
	
	/* Install crypto-js */
	import * as CryptoJS from 'crypto-js';
	
	var KEYPASS = 'Test Key';
	
	var ciphertext = encryptArr('This is data is going to encrypt');
	var plaintext = decrypt(decryptArr);
	
	var cipherObj = encryptArr(['123','456']);
	var plaintObj = decrypt(decryptArr);
	
	/**
     * @description Encrypt the object using AES
     */
	encryptArr(data: any) {
        var ciphertext = CryptoJS.AES.encrypt(JSON.stringify(data), KEYPASS).toString();
        return ciphertext;
    }

    /**
     * @description Decrypt the object using AES
     */
    decryptArr(data) {
        var bytes = CryptoJS.AES.decrypt(data.toString(), KEYPASS);
        var decryptedData = JSON.parse(bytes.toString(CryptoJS.enc.Utf8));
        return '[' + decryptedData + ']';
    }

    /**
     * @description Encrypt the data using AES
     */
    encrypt(data) {
        let ciphertext: string = (CryptoJS.AES.encrypt(data.toString(), KEYPASS)).toString();
        return ciphertext;
    }

    /**
     *  @description Decrypt the data using AES
     */
    decrypt(data) {
        var bytes = CryptoJS.AES.decrypt(data.toString(), KEYPASS);
        var decryptedData = bytes.toString(CryptoJS.enc.Utf8);
        return decryptedData;
    }
