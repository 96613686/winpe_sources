# Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::DeserializeExtensionOptions

- ea: `0x5b390`
- end: `0x5b400`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::DeserializeExtensionOptions`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x5b070`
- `0x8cc40`

## callees

- `0x2bb50`
- `0x2bbc0`
- `0x5b390`

## string_xrefs

- `0x5b3b0`: `deserialize`
- `0x5b3eb`: `Error deserializing extension options. Returning null.`

## pseudocode

```c

```

## disassembly

```asm
0x5b390  ldarg.1
0x5b391  brtrue.s loc_5B395
0x5b393  ldnull
0x5b394  ret
0x5b395  nop
0x5b396  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Serialization.ExtensionOptionsEnumerableSerializer::.ctor()
0x5b39b  ldarg.1
0x5b39c  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ExtensionOptions>>::Deserialize(!!T0)
0x5b3a1  stloc.0
0x5b3a2  leave.s  loc_5B3FE
0x5b3a4  stloc.1
0x5b3a5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5b3aa  dup
0x5b3ab  ldsfld   string Extensions::SerializationErrorOperationTypeProperty
0x5b3b0  ldstr    aDeserialize// "deserialize"
0x5b3b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5b3ba  stloc.2
0x5b3bb  ldarg.0
0x5b3bc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b3c1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Telemetry()
0x5b3c6  dup
0x5b3c7  brtrue.s loc_5B3CC
0x5b3c9  pop
0x5b3ca  br.s     loc_5B3D9
0x5b3cc  ldsfld   string Extensions::SerializationErrorEvent
0x5b3d1  ldloc.2
0x5b3d2  ldnull
0x5b3d3  ldc.i4.0
0x5b3d4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x5b3d9  ldarg.0
0x5b3da  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.InstallerUpdateContinueHandler::serviceOptions
0x5b3df  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x5b3e4  dup
0x5b3e5  brtrue.s loc_5B3EA
0x5b3e7  pop
0x5b3e8  br.s     loc_5B3FA
0x5b3ea  ldloc.1
0x5b3eb  ldstr    aErrorDeseriali// "Error deserializing extension options. "...
0x5b3f0  call     T0x2B000010
0x5b3f5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5b3fa  ldnull
0x5b3fb  stloc.0
0x5b3fc  leave.s  loc_5B3FE
0x5b3fe  ldloc.0
0x5b3ff  ret
```
