This python api enables easy interaction with the Etherpad Lite API.  Etherpad Lite is a collaborative editor provided by the Etherpad Foundation.  http://etherpad.org
This version is a fork of https://github.com/devjones/PyEtherpadLite 
The main changes are to be able to use python types, eg. True and False instead of "true" and "false"

THIS IS NOT COMPATIBLE with the original because of the type changes.

#1 Installation

To install py_etherpad using PIP, add the following line to your requirements.txt file:

    -e git+git://github.com/phoebebright/PyEtherpadLite.git#egg=PyEtherpadLite

#2 Preparation

If you are using a self hosted Etherpad Lite server, you will need to specify an API Key after installation before using the API.  (See https://github.com/Pita/etherpad-lite for installation details).

Your secret api key should be placed in the base installation (etherpad-client folder) in a text file named APIKEY.txt.  Many linux text editors automatically create an extra newline character at the end of the file, so I recommend simply executing the following command to set your api key without a newline character:

    echo -n "myapikey" > APIKEY.txt

Once you have created the APIKEY.txt file, you will need to edit the py_etherpad.py wrapper to set your API key. Edit the 'apiKey' variable and set it to the same key as defined in your APIKEY.txt file.

#3 Basic usage

    from py_etherpad import EtherpadLiteClient
    myPad = EtherpadLiteClient('EtherpadFTW','http://beta.etherpad.org/api')

    #Change the text of the etherpad
    myPad.setText('testPad','New text from the python wrapper!')

#4 More details

See the py_etherpad.py file for further details on the methods and parameters available for the API

#5 License

Apache License

#6 Credit
This python client was inspired by TomNomNom's php client which can be found at: https://github.com/TomNomNom/etherpad-lite-client


#7 Understanding

If you want public pads, life is easy.
Just allocate an id to your pad, it can be numeric or character (avoid # I think?)
Then use the api to get and set values.

If you want limit who can edit, then you are into setting up groups and authors and life becomes a bit more complicated.
