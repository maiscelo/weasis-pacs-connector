# Changelog

## [v7.0.0](https://github.com/nroduit/weasis-pacs-connector/tree/v7.0.0) (2018-10-28)

[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/v6.1.4...v7.0.0)

**Implemented enhancements:**

- Fix possible injection for getting a local file [\#21](https://github.com/nroduit/weasis-pacs-connector/issues/21) [[Type: Security](https://github.com/nroduit/weasis-pacs-connector/labels/Type:%20Security)]
- Remove Applet API [\#20](https://github.com/nroduit/weasis-pacs-connector/issues/20) [[Type: Security](https://github.com/nroduit/weasis-pacs-connector/labels/Type:%20Security)]
- Use new API for building Manifest [\#19](https://github.com/nroduit/weasis-pacs-connector/issues/19)
- Requires Java 8 and Servlet 3.1 [\#18](https://github.com/nroduit/weasis-pacs-connector/issues/18)
- Use weasis-dicom-tools 5.13.3 [\#17](https://github.com/nroduit/weasis-pacs-connector/issues/17)

## [v6.1.4](https://github.com/nroduit/weasis-pacs-connector/tree/v6.1.4) (2018-10-26)

[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/6.1.3...v6.1.4)

**Implemented enhancements:**

- ${server.base.url} like variable that returns IP address of server [\#13](https://github.com/nroduit/weasis-pacs-connector/issues/13)
- Add a trace when building the JNLP [\#16](https://github.com/nroduit/weasis-pacs-connector/issues/16)

**Fixed bugs:**

- Issue when the application container contains spaces in the path [\#15](https://github.com/nroduit/weasis-pacs-connector/issues/15)
- Error launching /IHEInvokeImageDisplay with HTTP HEAD [\#10](https://github.com/nroduit/weasis-pacs-connector/issues/10)

## [6.1.3](https://github.com/nroduit/weasis-pacs-connector/tree/6.1.3) (2017-08-21)
[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/6.1.1...6.1.3)

* Enable running Weasis on Java 9
* Getting jnlp protocol by redirection (see https://github.com/nroduit/weasis-pacs-connector/tree/6.x#new-way-to-launch-jnlp)
* Allow the configuration of the default max memory size of Weasis
* Add double quotes for command parameters in jnlp (requires by Weasis 2.5.4 and later)

## [6.1.1](https://github.com/nroduit/weasis-pacs-connector/tree/6.1.1) (2017-06-20)
[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/6.1.0...6.1.1)

* Fix cannot build manifest (sorting exception)

## [6.1.0](https://github.com/nroduit/weasis-pacs-connector/tree/6.1.0) (2017-04-30)
[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/5.0.1...6.1.0)

* Multi-PACS configuration (can be requested simultaneously or individually)
* Allows to query the PACS through its database (not recommended)
* Generates new manifest 2.5 (supported by Weasis 2.5)
* Support configuration in Wildfly 10 without module
* Requires Java 7

## [5.0.1](https://github.com/nroduit/weasis-pacs-connector/tree/5.0.1) (2015-07-14)
[Full Changelog](https://github.com/nroduit/weasis-pacs-connector/compare/5.0.0...5.0.1)

* Update weasis-dicom-tools to 0.9.8 (based on dcm4che3 3.3.7)
* Add maven profile to build without logger (better for JBoss)
* #1 Combination of UIDs doesn't work
* #3 Combination of UIDs is incompatible with IID profile (must be desactivated in configuration)
* #4 Add parameter to search in the Study Description
* Change logger level to INFO
* Write jnlp response without server enconding

## [5.0.0](https://github.com/nroduit/weasis-pacs-connector/tree/5.0.0) (2015-01-03)

* Used [weasis-dicom-tools](https://github.com/nroduit/weasis-dicom-tools) (based on dcm4che3) for building the manifest
* Starting Weasis and building manifest are executed in parallel (improve the time to get the images)
* The manifest is not embedded any more by default in the jnlp, only an url with an id can be called once within 5 min. That means clicking on a jnlp a second time won't show any images (this behavior is desirable for security reasons as most browsers downloads jnlp)
* Configure the maximum number of manifests treated simultaneous and the maximum life time of a building manifest process (5 min by default)
* Error messages (when building the manifest) are transmitted to the viewer via the manifest
* New context (_/IHEInvokeImageDisplay_) compliant to the [IHE IID profile](http://www.ihe.net/Technical_Framework/upload/IHE_RAD_Suppl_IID.pdf)
* Parameters at patient level defined in IID profile (mostRecentResults, lowerDateTime, upperDateTime, modalitiesInStudy) are also available in the other contexts (_/viewer_, _/viewer-applet_ and _/manifest_)
* Allows to have on different servers the following components: weasis-pacs-connector, PACS, Weasis, weasis-ext (additional plugins) and jnlp templates
* Major improvement of the JNLP builder servlet (allows dynamic injection of arguments, properties and templates)
* Option for DICOM query in TLS mode
* Launching Weasis as an Applet in web page
* Uploading the manifest by http POST
* Option to embed the manifest into the jnlp



\* *This Changelog was automatically generated by [github_changelog_generator](https://github.com/github-changelog-generator/github-changelog-generator)*