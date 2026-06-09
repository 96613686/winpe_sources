# Microsoft.VisualStudio.Setup.Installer.Notices.NoticeCommandFactory::Create

- ea: `0x35a00`
- end: `0x35aa7`
- name: `Microsoft.VisualStudio.Setup.Installer.Notices.NoticeCommandFactory::Create`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x358f0`
- `0x35900`
- `0x35930`
- `0x35940`
- `0x35a00`
- `0x35ab0`
- `0x773f0`

## string_xrefs

- `0x35a56`: `channelUri`
- `0x35a64`: `channelUri`

## pseudocode

```c

```

## disassembly

```asm
0x35a00  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x35a05  stloc.0
0x35a06  ldloc.0
0x35a07  ldarg.0
0x35a08  stfld    class Microsoft.VisualStudio.Setup.Installer.Notices.NoticeCommandFactory <>c__DisplayClass19_0::<>4__this
0x35a0d  ldloc.0
0x35a0e  ldarg.1
0x35a0f  stfld    class Microsoft.VisualStudio.Setup.Installer.Notices.Notice <>c__DisplayClass19_0::notice
0x35a14  ldloc.0
0x35a15  ldfld    class Microsoft.VisualStudio.Setup.Installer.Notices.Notice <>c__DisplayClass19_0::notice
0x35a1a  stloc.3
0x35a1b  ldloc.3
0x35a1c  brfalse.s loc_35A9D
0x35a1e  ldloc.3
0x35a1f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.NoticeCommand> Microsoft.VisualStudio.Setup.Installer.Notices.Notice::get_Command()
0x35a24  stloc.s  4
0x35a26  ldloca.s 4
0x35a28  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.NoticeCommand>::get_HasValue()
0x35a2d  brfalse.s loc_35A43
0x35a2f  ldloca.s 4
0x35a31  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.NoticeCommand>::GetValueOrDefault()
0x35a36  ldc.i4.1
0x35a37  bne.un.s loc_35A43
0x35a39  ldloc.3
0x35a3a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.Notices.Notice::get_CommandArgs()
0x35a3f  stloc.1
0x35a40  ldloc.1
0x35a41  brtrue.s loc_35A55
0x35a43  ldloc.3
0x35a44  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Notices.Notice::get_LinkUrl()
0x35a49  brfalse.s loc_35A9D
0x35a4b  ldloc.3
0x35a4c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Notices.Notice::get_LinkId()
0x35a51  brfalse.s loc_35A9D
0x35a53  br.s     loc_35A88
0x35a55  ldloc.1
0x35a56  ldstr    aChanneluri// "channelUri"
0x35a5b  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x35a60  brfalse.s loc_35A43
0x35a62  ldarg.0
0x35a63  ldloc.1
0x35a64  ldstr    aChanneluri// "channelUri"
0x35a69  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x35a6e  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler Microsoft.VisualStudio.Setup.Installer.Notices.NoticeCommandFactory::MigrateToChannelCommandGenerator(string channelUri)
0x35a73  dup
0x35a74  ldvirtftn instance void Microsoft.VisualStudio.Setup.Installer.Commands.ICommandHandler::Handle()
0x35a7a  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x35a7f  ldc.i4.1
0x35a80  newobj   instance void valuetype [mscorlib]System.ValueTuple`2<class [mscorlib]System.Action, bool>::.ctor(var<u1>, !!T0)
0x35a85  stloc.2
0x35a86  br.s     loc_35AA5
0x35a88  ldloc.0
0x35a89  ldftn    instance void <>c__DisplayClass19_0::<Create>b__0()
0x35a8f  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x35a94  ldc.i4.0
0x35a95  newobj   instance void valuetype [mscorlib]System.ValueTuple`2<class [mscorlib]System.Action, bool>::.ctor(var<u1>, !!T0)
0x35a9a  stloc.2
0x35a9b  br.s     loc_35AA5
0x35a9d  ldnull
0x35a9e  ldc.i4.0
0x35a9f  newobj   instance void valuetype [mscorlib]System.ValueTuple`2<class [mscorlib]System.Action, bool>::.ctor(var<u1>, !!T0)
0x35aa4  stloc.2
0x35aa5  ldloc.2
0x35aa6  ret
```
