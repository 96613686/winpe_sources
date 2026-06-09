# TimeZoneSyncTask.DynamicDstTransform::IsManagedByOneSettings

- ea: `0xd6c0`
- end: `0xd6fe`
- name: `TimeZoneSyncTask.DynamicDstTransform::IsManagedByOneSettings`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd2c0`

## callees

- `0x1200`
- `0xd6c0`

## pseudocode

```c

```

## disassembly

```asm
0xd6c0  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xd6c5  call     void [System]System.Diagnostics.Trace::Assert(bool)
0xd6ca  ldc.i4.0
0xd6cb  stloc.0
0xd6cc  ldarg.0
0xd6cd  ldarg.1
0xd6ce  ldc.i4.0
0xd6cf  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xd6d4  stloc.1
0xd6d5  ldloc.1
0xd6d6  ldstr    aOnesettingstzv// "OneSettingsTzVersion"
0xd6db  ldnull
0xd6dc  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0xd6e1  stloc.2
0xd6e2  ldloc.2
0xd6e3  brfalse.s loc_D6F0
0xd6e5  ldloc.2
0xd6e6  call     unsigned int32 [mscorlib]System.Convert::ToUInt32(object)
0xd6eb  ldarg.2
0xd6ec  ble.un.s loc_D6F0
0xd6ee  ldc.i4.1
0xd6ef  stloc.0
0xd6f0  leave.s  loc_D6FC
0xd6f2  ldloc.1
0xd6f3  brfalse.s loc_D6FB
0xd6f5  ldloc.1
0xd6f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd6fb  endfinally
0xd6fc  ldloc.0
0xd6fd  ret
```
