#Disclaimer

Only hardware that I have used personnaly are located here.

There is probably tons of other things that can do the job better.



# What is a Yubikey?

A Yubikey is a hardware crypographic engine and secret key storage device that is designed at the hardware level to prevent (if not just uncapable) to export the secrets it contains. It is most commonly used as a second factor in MFA authentification schemes. 

> TL:DR - The Yubikey is a write only device with built in crypographic silicon. 


# What are the use cases for the Yubikey?

## High Level

> What is this used for?

Typically used for second factor auth, can be used to sign content with PGP 

## Slotted Functionality
> *These functions are required to be assisnged to a "slot" in order to function.*

### Yubico OTP

Yubico OTP is a OTP designed and configured from the factory from Yubico. Yubico's public auth servers are already configured with the key from the box. 

> Tip.
> 
> If you remove the config for Yubico OTP, You will not be able to restore this config, **EVER...** You will instead get a "less trusted" keypair.

     Used in... SSH Auth, PAM, Web services

### OATH-HTOP

Almost identical to Yubico OTP.. But not using the Yubico syntax form.

    Used in... SSH Auth, PAM, Web services

### Static Password

Press button, spits out the same thing every time. mainly used with legecy systems. 

    Used in... wherever you deem fit. acts identical to a normal password

### Challange Response

The program and the yubikey talk to each other to perform a cryptographic challange to authneticate.

    Used in... KeepassXC, Local programs, some web services, PAM

## Non-Slotted Functionality

The below functions do not require a slot to work and will work out of the box... *Most of the time, some config may be required* 

### U2F

A web-to-hardware API for using hardware tokens as a means of auth. Extreamly easy to use.

    Used in... Web services, PAM

### Fido2

Like U2F, But upgraded and becomming the new standard in web auth. Can be used as single factor auth as well.

    Used in... Web services, PAM

### OpenPGP Card

Used to store private and public openPGP keys for PGP things.

    Used in.. Signing, encryption and decryption.

### PIV Functionality

The hardest to grasp, Uses a PKI infra to identify a user. But can easily be set up to use with SSH Auth.

> This is the best use case for ssh keypairs, as it requires no extrea configuration on the remote server. All required informaiton is stored in the public key. 

    Used in... Corporations, SSH, PAM, AD, FreeIPA, 