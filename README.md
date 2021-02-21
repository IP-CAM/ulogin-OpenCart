Donate link: http://ulogin.ru
Tags: ulogin, login, social, authorization
Tested up to: 2.1.0.1
Stable tag: 2.0.4
License: GNU General Public License, version 2

** uLogin ** is a tool that allows users to get uniform access to various Internet services without the need to re-register,
and for site owners - to receive an additional influx of customers from social networks and popular portals (Google, Yandex, Mail.ru, VKontakte, Facebook, etc.)


## Installation

- Unpack the contents of the ** upload ** folder of the installation archive to the root of the site.
- Activate the modules ** "uLogin - panel" ** and ** "uLogin - general settings" ** in the list of modules.
- The module will work immediately after activation with the default settings.

When activating (installing) the * "uLogin - panel" * module, child modules are automatically created and added to the * Account * layout.
When activating (installing) the module * "uLogin - general settings" *, a group of clients * uLogin * is created for new clients who register through uLogin.

For more detailed information, see the website https://ulogin.ru/help.php

## Module "uLogin - general settings"

This module sets:
** Value of the uLogin ID field ** common field for all uLogin widgets, optional parameter (see * "Settings of uLogin widget" *);
** Default customer group: ** group assigned to users registered with uLogin. By default, the * uLogin * group is created after the module is installed.


## Module "uLogin - panel"

Here you can specify parameters for each uLogin panel separately.

Module parameter ** Field value uLogin ID ** - sets the value for the widget of this panel. Empty field - the value is taken from the "uLogin - general settings" module.
The parameter ** Form type ** - affects the display of the uLogin panel:

- * Form offline - authorization * - form for authorization, displayed when the user is online. The location is determined in layouts.
- * Online form - synchronization * - a form for linking accounts of various social networks, displayed when the user is offline. The location is determined in layouts.
- * Online form - synchronization in the user's personal account * - the same as * Online form - synchronization *,
except that the form will be displayed only in the user's personal account on the data editing page only when the module is added to the * Account * layout.

When activating (installing) the * "uLogin - panel" * module, two child modules are automatically created and added to the * Account * layout.


## uLogin widget settings

When installing the uLogin extension, users will be authorized with the default settings.
For more detailed customization of uLogin widgets, you can use the uLogin service.

You can create your own uLogin widget and edit it yourself:

to create a widget, you need to go to your Personal Account (LC) on the website http://ulogin.ru/lk.php,
add your site to the list of My sites and add a new widget on the Widgets tab. After that, you can edit your widget.

** Important! ** For the plugin to work successfully, you must enable the ** Email ** field in your uLogin Personal Account in the required profile fields.
You do not need to fill in the fields in the "Authorization type" column. the uLogin extension is configured to automatically fill in these parameters.

The widget created in the Personal Account has the ** uLogin ID ** parameter.
Copy the ** uLogin ID ** value of your widget to the corresponding field in the plugin settings on your site and save the settings.

If everything was done correctly, the widget will change according to your settings.


## Features

To manually display the login panel anywhere in the OpenCart theme template, you need to do the following:

- Add the module controller to the template php file, for example, to display the panel in the header, you need to add this code to the `catalog / controller / common / header.php` file:

        $ data ['ulogin_form_marker'] = $ this-> load-> controller ('module / ulogin');
    Note that you need to add the code to the beginning of the index method of the corresponding controller.


- Add panel output in the template `catalog / view / theme / default / template / common / header.tpl`, for example, after the line` <div class = "collapse navbar-collapse navbar-ex1-collapse"> `:

        <? php echo $ ulogin_form_marker;?>

The synchronization panel in the user's personal account and the authorization panel on the login and registration pages are configured in the ** uLogin modules - panel> account_lk_online ** and ** uLogin - panel> account_offline **.

## Changes

#### 2.0.4
* Error correction

#### 2.0.3
* Error correction

#### 2.0.2
* Added compatibility with engine version 2.1.0.1

#### 2.0.1
* Fixed bug with displaying the uLogin panel using the https protocol.
* Fixed README.md.

#### 2.0.0 Release.
