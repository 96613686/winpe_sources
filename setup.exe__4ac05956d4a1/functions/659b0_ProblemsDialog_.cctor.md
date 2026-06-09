# ProblemsDialog::.cctor

- ea: `0x659b0`
- end: `0x65b2d`
- name: `ProblemsDialog::.cctor`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x65a05`: `open-feedback`
- `0x65aa5`: `open-feedback`

## pseudocode

```c

```

## disassembly

```asm
0x659b0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x659b5  ldstr    aProblemsdialog_1// "ProblemsDialog/"
0x659ba  call     string [mscorlib]System.String::Concat(string, string)
0x659bf  stsfld   string ProblemsDialog::ProblemsDialogEventPrefix
0x659c4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowEventPrefix
0x659c9  ldstr    aFeedbackclient// "FeedbackClient/"
0x659ce  call     string [mscorlib]System.String::Concat(string, string)
0x659d3  stsfld   string ProblemsDialog::FeedbackClientEventPrefix
0x659d8  ldsfld   string ProblemsDialog::ProblemsDialogEventPrefix
0x659dd  ldstr    aRetryOperation// "retry-operation"
0x659e2  call     string [mscorlib]System.String::Concat(string, string)
0x659e7  stsfld   string ProblemsDialog::RetryEvent
0x659ec  ldsfld   string ProblemsDialog::ProblemsDialogEventPrefix
0x659f1  ldstr    aCloseDialog// "close-dialog"
0x659f6  call     string [mscorlib]System.String::Concat(string, string)
0x659fb  stsfld   string ProblemsDialog::CloseEvent
0x65a00  ldsfld   string ProblemsDialog::ProblemsDialogEventPrefix
0x65a05  ldstr    aOpenFeedback// "open-feedback"
0x65a0a  call     string [mscorlib]System.String::Concat(string, string)
0x65a0f  stsfld   string ProblemsDialog::OpenFeedbackEvent
0x65a14  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65a19  ldstr    aChannelid// "channelId"
0x65a1e  call     string [mscorlib]System.String::Concat(string, string)
0x65a23  stsfld   string ProblemsDialog::ChannelIdProperty
0x65a28  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65a2d  ldstr    aProductid// "productId"
0x65a32  call     string [mscorlib]System.String::Concat(string, string)
0x65a37  stsfld   string ProblemsDialog::ProductIdProperty
0x65a3c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65a41  ldstr    aFeedbackaction// "feedbackAction"
0x65a46  call     string [mscorlib]System.String::Concat(string, string)
0x65a4b  stsfld   string ProblemsDialog::FeedbackActionProperty
0x65a50  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65a55  ldstr    aFeedbackurl// "feedbackUrl"
0x65a5a  call     string [mscorlib]System.String::Concat(string, string)
0x65a5f  stsfld   string ProblemsDialog::FeedbackUrlProperty
0x65a64  ldsfld   string ProblemsDialog::FeedbackClientEventPrefix
0x65a69  ldstr    aSearchStarted// "search-started"
0x65a6e  call     string [mscorlib]System.String::Concat(string, string)
0x65a73  stsfld   string ProblemsDialog::FeedbackClientSearchStartedEvent
0x65a78  ldsfld   string ProblemsDialog::FeedbackClientEventPrefix
0x65a7d  ldstr    aSearchFinished// "search-finished"
0x65a82  call     string [mscorlib]System.String::Concat(string, string)
0x65a87  stsfld   string ProblemsDialog::FeedbackClientSearchFinishedEvent
0x65a8c  ldsfld   string ProblemsDialog::FeedbackClientEventPrefix
0x65a91  ldstr    aCheckingSoluti// "checking-solutions"
0x65a96  call     string [mscorlib]System.String::Concat(string, string)
0x65a9b  stsfld   string ProblemsDialog::FeedbackClientCheckingSolutionsEvent
0x65aa0  ldsfld   string ProblemsDialog::ProblemsDialogEventPrefix
0x65aa5  ldstr    aOpenFeedback// "open-feedback"
0x65aaa  call     string [mscorlib]System.String::Concat(string, string)
0x65aaf  stsfld   string ProblemsDialog::ProblemsDialogOpenFeedbackEvent
0x65ab4  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ab9  ldstr    aFailedpackagei_1// "failedPackageId"
0x65abe  call     string [mscorlib]System.String::Concat(string, string)
0x65ac3  stsfld   string ProblemsDialog::FailedPackageIdProperty
0x65ac8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65acd  ldstr    aFailedpackagea// "failedPackageAction"
0x65ad2  call     string [mscorlib]System.String::Concat(string, string)
0x65ad7  stsfld   string ProblemsDialog::FailedPackageActionProperty
0x65adc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65ae1  ldstr    aFailedpackager// "failedPackageReturnCode"
0x65ae6  call     string [mscorlib]System.String::Concat(string, string)
0x65aeb  stsfld   string ProblemsDialog::FailedPackageReturnCodeProperty
0x65af0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65af5  ldstr    aFailedpackagev// "failedPackageVersion"
0x65afa  call     string [mscorlib]System.String::Concat(string, string)
0x65aff  stsfld   string ProblemsDialog::FailedPackageVersionProperty
0x65b04  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65b09  ldstr    aHassolutions// "hasSolutions"
0x65b0e  call     string [mscorlib]System.String::Concat(string, string)
0x65b13  stsfld   string ProblemsDialog::HasSolutionsProperty
0x65b18  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::WillowPropertyPrefix
0x65b1d  ldstr    aSolutionticket// "solutionTicketType"
0x65b22  call     string [mscorlib]System.String::Concat(string, string)
0x65b27  stsfld   string ProblemsDialog::SolutionTypeProperty
0x65b2c  ret
```
