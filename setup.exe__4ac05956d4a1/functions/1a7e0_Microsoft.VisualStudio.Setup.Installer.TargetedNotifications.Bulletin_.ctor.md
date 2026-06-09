# Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::.ctor

- ea: `0x1a7e0`
- end: `0x1a84d`
- name: `Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::.ctor`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a809`: `learnMoreLink`
- `0x1a815`: `learnMoreLinkDescription`

## pseudocode

```c

```

## disassembly

```asm
0x1a7e0  ldarg.0
0x1a7e1  call     instance void [mscorlib]System.Object::.ctor()
0x1a7e6  ldarg.1
0x1a7e7  ldstr    aId_0// "id"
0x1a7ec  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1a7f1  ldarg.2
0x1a7f2  ldstr    aTitle// "title"
0x1a7f7  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1a7fc  ldarg.3
0x1a7fd  ldstr    aDescription_0// "description"
0x1a802  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1a807  ldarg.s  4
0x1a809  ldstr    aLearnmorelink// "learnMoreLink"
0x1a80e  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1a813  ldarg.s  5
0x1a815  ldstr    aLearnmorelinkd// "learnMoreLinkDescription"
0x1a81a  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x1a81f  ldarg.0
0x1a820  ldarg.1
0x1a821  stfld    string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<Id>k__BackingField
0x1a826  ldarg.0
0x1a827  ldarg.2
0x1a828  stfld    string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<Title>k__BackingField
0x1a82d  ldarg.0
0x1a82e  ldarg.3
0x1a82f  stfld    string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<Description>k__BackingField
0x1a834  ldarg.0
0x1a835  ldarg.s  4
0x1a837  stfld    string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<LearnMoreLink>k__BackingField
0x1a83c  ldarg.0
0x1a83d  ldarg.s  5
0x1a83f  stfld    string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<LearnMoreLinkDescription>k__BackingField
0x1a844  ldarg.0
0x1a845  ldarg.s  6
0x1a847  stfld    valuetype Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinIllustration Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::<IllustrationId>k__BackingField
0x1a84c  ret
```
