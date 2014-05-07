CoinAuth (Not working yet, but expected to be working sometime in May 2014)
========

A service for authenticating the owner of a Bitcoin address

The purpose of this project is to create a method for an app or web service to verify that a person is in fact the owner of a particular Bitcoin address. In other words, to verify that they are in possession of the private key for a particular Bitcoin address without providing the private key.

Basic flow of this service is as follows:  
1. Client requests a nonce from the service  
2. Service responds with nonce  
3. Client responds with nonce, and nonce ECDSA signature created by using their Bitcoin private key and their Bitcoin address.  
4. Service responds with verification results (success or failure of challenge response for supplied Bitcoin address, nonce, and ECDSA signature)

The nonce is comprised of the following:  
1. A pseudo random number (for uniqueness)  
2. The current time in seconds (to allow for token expiration)

This service is built on top of Flask-RESTful http://flask-restful.readthedocs.org/en/latest/
