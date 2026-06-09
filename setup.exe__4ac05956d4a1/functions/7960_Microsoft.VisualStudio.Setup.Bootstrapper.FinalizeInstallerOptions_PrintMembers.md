# Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::PrintMembers

- ea: `0x7960`
- end: `0x7a6f`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::PrintMembers`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7920`

## callees

- `0x7810`
- `0x7830`
- `0x7850`
- `0x7860`
- `0x7880`
- `0x7890`
- `0x78a0`
- `0x78c0`
- `0x78e0`
- `0x7900`

## string_xrefs

- `0x79d8`: `, TargetPath = `
- `0x79f1`: `, ElevationServicePath = `
- `0x7a23`: `, ElevationServiceName = `
- `0x7a3c`: `, ElevationServiceDisplayName = `
- `0x7a55`: `, ElevationServiceDescription = `

## pseudocode

```c

```

## disassembly

```asm
0x7960  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x7965  ldarg.1
0x7966  ldstr    aApplicationsho// "ApplicationShortcutName = "
0x796b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7970  pop
0x7971  ldarg.1
0x7972  ldarg.0
0x7973  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ApplicationShortcutName()
0x7978  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x797d  pop
0x797e  ldarg.1
0x797f  ldstr    aApplicationdes// ", ApplicationDescription = "
0x7984  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7989  pop
0x798a  ldarg.1
0x798b  ldarg.0
0x798c  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ApplicationDescription()
0x7991  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7996  pop
0x7997  ldarg.1
0x7998  ldstr    aApplicationver_0// ", ApplicationVersion = "
0x799d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x79a2  pop
0x79a3  ldarg.1
0x79a4  ldarg.0
0x79a5  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ApplicationVersion()
0x79aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x79af  pop
0x79b0  ldarg.1
0x79b1  ldstr    aApplicationsiz// ", ApplicationSizeInBytes = "
0x79b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x79bb  pop
0x79bc  ldarg.1
0x79bd  ldarg.0
0x79be  call     instance int32 Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ApplicationSizeInBytes()
0x79c3  stloc.0
0x79c4  ldloca.s 0
0x79c6  constrained. [mscorlib]System.Int32
0x79cc  callvirt instance string [mscorlib]System.Object::ToString()
0x79d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x79d6  pop
0x79d7  ldarg.1
0x79d8  ldstr    aTargetpath_0// ", TargetPath = "
0x79dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x79e2  pop
0x79e3  ldarg.1
0x79e4  ldarg.0
0x79e5  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_TargetPath()
0x79ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x79ef  pop
0x79f0  ldarg.1
0x79f1  ldstr    aElevationservi_0// ", ElevationServicePath = "
0x79f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x79fb  pop
0x79fc  ldarg.1
0x79fd  ldarg.0
0x79fe  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServicePath()
0x7a03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7a08  pop
0x7a09  ldarg.1
0x7a0a  ldstr    aAppplicationus// ", AppplicationUserModelId = "
0x7a0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7a14  pop
0x7a15  ldarg.1
0x7a16  ldarg.0
0x7a17  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_AppplicationUserModelId()
0x7a1c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7a21  pop
0x7a22  ldarg.1
0x7a23  ldstr    aElevationservi_1// ", ElevationServiceName = "
0x7a28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7a2d  pop
0x7a2e  ldarg.1
0x7a2f  ldarg.0
0x7a30  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x7a35  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7a3a  pop
0x7a3b  ldarg.1
0x7a3c  ldstr    aElevationservi_2// ", ElevationServiceDisplayName = "
0x7a41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7a46  pop
0x7a47  ldarg.1
0x7a48  ldarg.0
0x7a49  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceDisplayName()
0x7a4e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7a53  pop
0x7a54  ldarg.1
0x7a55  ldstr    aElevationservi_3// ", ElevationServiceDescription = "
0x7a5a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7a5f  pop
0x7a60  ldarg.1
0x7a61  ldarg.0
0x7a62  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceDescription()
0x7a67  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x7a6c  pop
0x7a6d  ldc.i4.1
0x7a6e  ret
```
