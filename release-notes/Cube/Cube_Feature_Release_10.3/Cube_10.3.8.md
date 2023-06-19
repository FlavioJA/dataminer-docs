---
uid: Cube_Feature_Release_10.3.8
---

# DataMiner Cube Feature Release 10.3.8 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For release notes for this release that are not related to DataMiner Cube, see [General Feature Release 10.3.8](xref:General_Feature_Release_10.3.8).

## Highlights

*No highlights have been selected for this release yet*

## Other new features

#### Open element cards will immediately show any changes made with regard to parameters [ID_36286]

<!-- MR 10.4.0 - FR 10.3.8 -->

When an element card is open, each time a new parameter is added to the element or an existing parameter is updated, the change will be applied in real time. You will no longer need to close the card and open it again to see the changes.

## Changes

### Enhancements

#### Visual Overview: External connectivity updates for dynamically positioned shapes will now be applied in real time [ID_36333]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

Up to now, external connectivity updates for dynamically positioned shapes would not be applied in real time. To see the changes, you had to close the visual overview and open it again. From now on, any external connectivity updates for dynamically positioned shapes will immediately be visible.

#### Visual Overview: TextWrapping should now default to the correct value "Wrap" [ID_36363]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

When a shape did not have a *TextStyle* shape data field, up to now, the *TextWrapping* option would automatically be set to "WrapWithOverflow". From now on, when a shape does not have a *TextStyle* shape data field, the *TextWrapping* option will automatically be set to "Wrap" instead.

Also, because of a number of enhancements, overall performance has increased when rendering shapes without a *TextStyle* shape data field.

#### Visual Overview: Subtract placeholder now also supports numerics [ID_36636]

<!-- MR 10.4.0 - FR 10.3.8 -->

Up to now, the subtract placeholder could be used to calculate datetime and time span values by subtracting one or more values from a specified value. From now on, this placeholder also supports numerics. Just like with datetime values and time spans, you can subtract consecutive numbers from the first number.

Examples:

- Subtracting one number from another: `[Subtract:10,3]`

- Subtracting multiple numbers from the first number: `[Subtract:10.1,3.3,2.6]`

### Fixes

#### Visual Overview: Problem with element or view scope of Children shapes [ID_36354]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

In some cases, when a placeholder was used in the *Element* or *View* shape data field of a *Children* shape, the scope would not be updated when changes were made to the placeholder.

From now on, the scope will be updated correctly whenever changes are made to the placeholder in the *Element* or *View* shape data field.

#### DataMiner Cube desktop app: False positive warnings involving a number of DLL files [ID_36424]

<!-- MR 10.4.0 - FR 10.3.8 -->

The log file of the DataMiner Cube desktop app would report false positive warnings involving a number of DLL files.

#### Workspaces: Problem opening cards that showed a visual overview [ID_36438]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

When you opened a workspace in which one or more cards showed a page with a visual overview, in some cases, the visual overview would be empty.

#### System Center: Problem with 'Show agent alarms' link [ID_36463]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

When you selected an agent in the *Agents* section of *System Center*, in some cases, the alarm numbers shown in the *Show agent alarms* link would not be correct.

Also, when you clicked that *Show agent alarms* link, the alarm tab listing the alarms of the selected agent would incorrectly be empty.

#### Trending: Related parameters returned by the DMA would incorrectly be empty [ID_36511]

<!-- MR 10.4.0 - FR 10.3.8 -->

When you opened a trend graph containing related parameters, in some cases, the related parameters returned by the DataMiner Agent would incorrectly be empty.

#### Visual Overview: Problem when using '[property:]' placeholders in shape data fields of type 'Element' and 'View' [ID_36553]

<!-- MR 10.4.0 - FR 10.3.8 -->

Up to now, when a property was updated, `[property:]` placeholders in shape data fields of type *Element* or *View* would not always get resolved correctly. The only way to ensure a `[property:]` placeholder was resolved correctly after a property update was to close the card and open it again.

Processing of property updates has now been improved. `[property:]` placeholders will now be resolved correctly without having to close the card and open it again.

#### Alarm Console: Problem when opening a history tab [ID_36603]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

When, in the Alarm Console, you opened a history tab on a system with a large number of masked alarms and a number of active correlation rules, that history tab would load rather slowly and would be missing some alarms.

#### Trending: Problem when exporting real-time trend data to a CSV file [ID_36630]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

When you exported more than a week's worth of real-time trend data to a CSV file, only the trend data of the last week (i.e. "week to date") would be exported.
