---
uid: About_services
---

# About services and service templates

DataMiner [services](#services) allow you to view your system from a service perspective and to analyze the impact of device failures faster. To create many similar services, a [service template](#service-templates) can be used.

## Services

In DataMiner, you can build a service layer on top of your devices. That way, operators can be offered a "service-centric" view of the network infrastructure.

![](~/dataminer/images/services_concept.png)

Services are displayed with the following icon in DataMiner:

- Default icon:

  ![](~/dataminer/images/CubeXService00057.png)

- Legacy icon, used in case *Use modern icons* is not selected in the [user settings](xref:User_settings#icons-settings):

  ![](~/dataminer/images/IconService00058.png)

Services have their own set of [properties](xref:Service_properties) and their own alarm history. They can also be assigned a Visio file to be displayed on a *Visual* page of a [service card](xref:Service_cards). In Visio files, objects can be linked to services just like they can be linked to elements.

The *Data* pages of a service display an overview of its contents. Services can contain entire elements, parts of elements, or even other services.

#### Advantages of services

Building a service layer has many advantages:

- You can watch services rather than devices. Service impact of device events is shown in real time.

- You can view your systems from a customer perspective.

- You can interpret the status of your systems much faster.

- You can better assess the impact of an alarm.

- You can drill down from the affected services all the way to the devices in order to analyze issues.

In short, when you focus on services rather than devices, if an alarm is raised, you can substantially reduce the time it takes to restore operations.

## Enhanced services

DataMiner also supports so-called enhanced services. These are services that are created with a **service protocol** (e.g. [Skyline Service Definition Basic](https://catalog.dataminer.services/details/809251d6-724d-499a-9c3c-d41ae1b5492b)). Enhanced services provide real-time service-level metrics, derived from metrics of the underlying and included managed objects. Alarm and trend templates can be assigned directly to such services.

## Service templates

Service templates are a valuable tool that simplifies the process of creating a series of almost identical services with just a few clicks. Instead of creating numerous similar services manually, the convenience of a service template allows you to create all desired services at once.

When you apply a service template, the designated input data is gathered and processed, resulting in the automatic creation of the corresponding services.

For more information and examples, see [Service templates](xref:Service_templates).
