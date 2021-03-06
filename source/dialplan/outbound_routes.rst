Outbound Routes
================

Route outbound calls to gateways, tdm, enum and more. When a call matches the conditions the call to outbound routes. `Check out the youtube video <https://youtu.be/rhyfCKLBI-Y>`_ .

|

Configure Outbound Route. 


Select **Dialplan** from the drop-down list and then click **Outbound Routes** . 

.. image:: ../_static/images/fusionpbx_outbound.jpg
        :scale: 85%

Click the 

.. image:: ../_static/images/plus.png
        :scale: 85%



button on the right. Enter the route information below and Click **Save** once entry is complete.

|
|

.. image:: ../_static/images/fusionpbx_outbound1.jpg
        :scale: 85%

|



|

.. image:: ../_static/images/fusionpbx_outbound2.jpg
        :scale: 85%

|
|

::

 Gateway: VoiceTel
 Dialplan Expression: ^(?:\+?1)?(\d{10})$ (You can also choose more than one from the drop down list also as needed)
 Order: 000
 Enabled: true
 Description: VoiceTel-out

|
|

**By using** `VoiceTel <http://tiny.cc/voicetel>`_ **you help support FusionPBX.  Thank you for your support!**


Pin Numbers
-----------------

To have the system ask for a PIN number before a call is made. A good use is if you don't want every user on the system to be able to call international destinations. This can be done with a single PIN or multiple PINs by using the "PIN Number APP".

**To use a single PIN number for all calls**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Before the bridge action on the outbound route add the following actions

::

 action	set	pin_number=(Whatever pin number you choose)
 action	lua	pin_number.lua


**To use the PIN Number App to manage multiple PINs**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* First enable access to the **"PIN Number"** app by giving permissions to the group of users you want to have access in **Advanced > Group Manager**. Make sure the **"PIN Number"** App is displayed in the menu by selecting the groups that can view it in **Advanced > Menu Manager**.

* Set the PINs you would like to use in **Apps > PIN Numbers** 

Before the bridge action on the outbound route add the following actions

::

 action	set	pin_number=database
 action	lua	pin_number.lua

