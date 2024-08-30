# FHIR Validator

The [FHIR Validator](https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar) is provided as open source code (see https://github.com/hapifhir/org.hl7.fhir.core) by the FHIR project in association with HL7, SmileCDR, and the HAPI FHIR project. From a java code point of view, the validator is part of the HAPI core library and available as part the HAPI distribution. HL7 acknowledges the support of the ONC in providing the validator to the community. Read more [here](https://confluence.hl7.org/pages/viewpage.action?pageId=35718580#UsingtheFHIRValidator-Usingthevalidator)

## Dependencies

A Java Develpment Kit (JDK) is required to run the validator. The validator is tested to run on all currently support LTS versions of Java (at the time of writing this documentation, JDK 11 and 17)

## Running the FHIR Validator

An example of how to run the command to test against the eCR FHIR IG::

```bash
java -jar validator_cli.jar fhir-bundles/fhir-bundle-to-validate.json -ig hl7.fhir.us.ecr\#2.1.2 -version 4.0.1 -output validation_output.xml -html-output validation_output.html -txLog terminology_log.txt -level warnings
```

### Command Breakdown

- `java -jar validator_cli.jar`: Runs the FHIR Validator CLI.
- `fhir-bundles/fhir-bundle-to-validate.json`: The FHIR bundle you want to validate.
- `-ig hl7.fhir.us.ecr\#2.1.2`: Specifies the Implementation Guide (eCR version 2.1.2) for validation.
- `-version 4.0.1`: Validates against FHIR R4 (version 4.0.1).
- `-output validation_output.xml`: Outputs the validation results in XML format.
- `-html-output validation_output.html`: Outputs the validation results in HTML format for easier viewing.
- `-txLog terminology_log.txt`: Logs terminology operations.
- `-level warnings`: Sets the validation level to display warnings.

## Convenience `bash` script

There is also a `validate.sh` script that can be leveraged to make running the validator easier. To use it simple run:

````bash
```bash
./validate.sh fhir-bundles/fhir-bundle.json
````

## Sample FHIR Bundles

Information about where the sample FHIR bundles in the `fhir-bundles` directory are sourced from:

| File Name                                      | Description                                                                                  |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `Bundle-bundle-ecr-message-zika.json`          | Zika FHIR Bundle from the eCR 2.1.2 spec                                                     |
| `Bundle-bundle-eicr-document-zika.json`        | Zika FHIR Document from the eCR 2.1.2 spec                                                   |
| `eICR-TC-COVID-DX_20210412-bundle.json`        | COVID DX FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template           |
| `eICR-TC-COVID-LabNeg_20210412-bundle.json`    | COVID Lab Negative FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template |
| `eICR-TC-COVID-Lab-Order_20210412-bundle.json` | COVID Lab Order FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template    |
| `eICR-TC-COVID-LabPos_20210412-bundle.json`    | COVID Lab Positive FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template |
| `eICR-TC-COVID-Problem_20210412-bundle.json`   | COVID Problem FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template      |
| `eICR_TC-DeDup1_Lab_Order-bundle.json`         | DeDup Lab Order FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template    |
| `eICR_TC-DeDup2_Lab_Result-bundle.json`        | DeDup Lab Result FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template   |
| `eICR_TC-eCR-Routing_STI-bundle.json`          | eCR Routing STI FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template    |
| `eICR_TC-Routing_VPD-bundle.json`              | eCR Routing VPD FHIR Bundle from Microsoft FHIR-Converter with custom eCR liquid template    |
