Release Notes
==================


v0.6.2 (Released 2012-11-07)
--------------------------------------

Bug Fixes
_________________

- Fixed bug with special characters when highlighting matches. Thanks to Chad Files for the report.
- Fixed javascript bug with spaces in ``item.id``. Thanks to @dc for the report and fix.


v0.6.1 (Released 2012-10-13)
--------------------------------------

Features
_________________

- Added Polish translation. Thanks to Sławomir Ehlert.

Bug Fixes
_________________

- Fixed incompatibility with jQuery UI 1.9.


v0.6.0 (Released 2012-10-09)
--------------------------------------

This release continues to clean up the API and JS. This was primarily motivated by
Sławomir Ehlert (@slafs) who is working on an alternate implementation which
uses Select2 rather than jQuery UI. This opens the door for additional apps
which use the same lookup declaration API with a different JS library on the front
end.

Python 2.5 support has been dropped to work towards Python 3 support.
This also drops Django 1.2 support which is no longer receiving security fixes.

Features
_________________

- Initial translations (pt_BR). Thanks to Felipe Prenholato for the patch.
- Upgraded default jQuery UI version included by the template tags from 1.8.18 to 1.8.23
- Added ``djselectableadd`` and ``djselectableremove`` events fired when items are added or removed from a mutliple select

Bug Fixes
_________________

- Cleaned up JS scoping problems when multiple jQuery versions are used on the page. Thanks Antti Kaihola for the report.
- Fixed minor JS bug where text input was not cleared when selected via the combobox in the multiselect. Thanks Antti Kaihola for the report and Lukas Pirl for a hotfix.

Backwards Incompatible Changes
________________________________

- ``get_item_value`` and ``get_item_id`` are no longer marked as safe by default.
- Removed AutoComboboxSelectField and AutoComboboxSelectMultipleField. These were deprecated in 0.5.
- Dropping official Python 2.5 support.
- Dropping official Django 1.2 support.
- ``paginate_results`` signature changed as part of the lookup refactor.
- ``SELECTABLE_MAX_LIMIT`` can no longer be ``None``.


v0.5.2 (Released 2012-06-27)
--------------------------------------

Bug Fixes
_________________

- Fixed XSS flaw with lookup ``get_item_*`` methods. Thanks slafs for the report.
- Fixed bug when passing widget instance rather than widget class to ``AutoCompleteSelectField`` or ``AutoCompleteSelectMultipleField``.


v0.5.1 (Released 2012-06-08)
--------------------------------------

Bug Fixes
_________________

- Fix for double ``autocompleteselect`` event firing.
- Fix for broken pagination in search results. Thanks David Ray for report and fix.


v0.4.2 (Released 2012-06-08)
--------------------------------------

Bug Fixes
_________________

- Backported fix for double ``autocompleteselect`` event firing.
- Backported fix for broken pagination in search results.


v0.5.0 (Released 2012-06-02)
--------------------------------------

Features
_________________

- Template tag to add necessary jQuery and jQuery UI libraries. Thanks to Rick Testore for the initial implementation
- :ref:`Lookup decorators <lookup-decorators>` for requiring user authentication or staff access to use the lookup
- Additional documentation
- Minor updates to the example project

Backwards Incompatible Changes
________________________________

- Previously the minimal version of jQuery was listed as 1.4.3 when it fact there was a bug a that made django-selectable require 1.4.4. Not a new incompatibility but the docs have now been updated and 1.4.3 compatibility will not be added. Thanks to Rick Testore for the report and the fix
- Started deprecation path for :ref:`AutoComboboxSelectField` and :ref:`AutoComboboxSelectMultipleField`


v0.4.1 (Released 2012-03-11)
--------------------------------------

Bug Fixes
_________________

- Cleaned up whitespace in css/js. Thanks Dan Poirier for the report and fix.
- Fixed issue with saving M2M field data with AutoCompleteSelectMultipleField. Thanks Raoul Thill for the report.


v0.4.0 (Released 2012-02-25)
--------------------------------------

Features
_________________

- Better compatibility with :ref:`AutoCompleteSelectWidget`/:ref:`AutoComboboxSelectWidget` and Django's ModelChoiceField
- Better compatibility with the Django admin :ref:`add another popup <admin-basic-example>`
- Easier passing of query parameters. See the :ref:`Additional Parameters <additional-parameters>` section
- Additional documentation
- QUnit tests for JS functionality


Backwards Incompatible Changes
________________________________

- Support for ``ModelLookup.search_field`` string has been removed. You should use the ``ModelLookup.search_fields`` tuple instead.


v0.3.1 (Released 2012-02-23)
--------------------------------------

Bug Fixes
_________________

- Fixed issue with media urls when not using staticfiles.


v0.3.0 (Released 2012-02-15)
--------------------------------------

Features
_________________

- Multiple search fields for :ref:`model based lookups <ModelLookup>`
- Support for :ref:`highlighting term matches <javascript-highlightMatch>`
- Support for HTML in :ref:`result labels <lookup-get-item-label>`
- Support for :ref:`client side formatting <advanced-label-formats>`
- Additional documentation
- Expanded examples in example project


Bug Fixes
_________________

- Fixed issue with Enter key removing items from select multiple widgets `#24 <https://bitbucket.org/mlavin/django-selectable/issue/24/pressing-enter-when-autocomplete-input-box>`_


Backwards Incompatible Changes
________________________________

- The fix for #24 changed the remove items from a button to an anchor tag. If you were previously using the button tag for additional styling then you will need to adjust your styles.
- The static resources were moved into a `selectable` sub-directory. This makes the media more in line with the template directory conventions. If you are using the widgets in the admin there is nothing to change. If you are using ``{{ form.media }}`` then there is also nothing to change. However if you were including static media manually then you will need to adjust them to include the selectable prefix.


v0.2.0 (Released 2011-08-13)
--------------------------------------

Features
_________________

- Additional documentation
- :ref:`Positional configuration <AutoCompleteSelectMultipleWidget>` for multiple select fields/widgets
- :ref:`Settings/configuration <SELECTABLE_MAX_LIMIT>` for limiting/paginating result sets
- Compatibility and examples for :ref:`Admin inlines <admin-inline-example>`
- JS updated for jQuery 1.6 compatibility
- :ref:`JS hooks <client-side-parameters>` for updating query parameters
- :ref:`Chained selection example <chain-select-example>`


v0.1.2 (Released 2011-05-25)
--------------------------------------

Bug Fixes
_________________

- Fixed issue `#17 <https://bitbucket.org/mlavin/django-selectable/issue/17/update-not-working>`_


v0.1.1 (Release 2011-03-21)
--------------------------------------

Bug Fixes
_________________

- Fixed/cleaned up multiple select fields and widgets
- Added media definitions to widgets


Features
_________________

- Additional documentation
- Added `update_query_parameters` to widgets
- Refactored JS for easier configuration


v0.1 (Released 2011-03-13)
--------------------------------------

Initial public release
