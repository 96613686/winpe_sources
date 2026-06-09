# Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::RemoveChannel

- ea: `0x25e80`
- end: `0x25f0e`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::RemoveChannel`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x25e70`
- `0x26070`

## callees

- `0x22890`
- `0x25e80`
- `0x26010`

## string_xrefs

- `0x25ecc`: `Failed to remove the channel: `
- `0x25ef8`: `The remote channel with uri {0} was not removed because it was not found.`

## pseudocode

```c

```

## disassembly

```asm
0x25e80  ldarg.0
0x25e81  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelValidator Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::channelValidator
0x25e86  ldarg.1
0x25e87  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelValidator::ValidateChannelUri(class [System]System.Uri)
0x25e8c  ldarg.0
0x25e8d  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManagerBase::Initialize()
0x25e92  ldarg.0
0x25e93  ldarg.1
0x25e94  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::GetChannel(class [System]System.Uri channelUri)
0x25e99  stloc.0
0x25e9a  ldloc.0
0x25e9b  brfalse.s loc_25EED
0x25e9d  ldarg.0
0x25e9e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::channelRepository
0x25ea3  ldloc.0
0x25ea4  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IChannelRepository::RemoveChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair)
0x25ea9  ldarg.2
0x25eaa  brfalse.s loc_25EBD
0x25eac  ldarg.0
0x25ead  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.IRemoteChannelManagerSettingsRepository Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::remoteChannelManagerSettingsRepository
0x25eb2  ldarg.1
0x25eb3  callvirt instance string [mscorlib]System.Object::ToString()
0x25eb8  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IRemoteChannelManagerSettingsRepository::SetIsRemoved(string channelUri)
0x25ebd  leave.s  loc_25F0D
0x25ebf  stloc.1
0x25ec0  ldarg.0
0x25ec1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::logger
0x25ec6  dup
0x25ec7  brtrue.s loc_25ECC
0x25ec9  pop
0x25eca  br.s     loc_25EEB
0x25ecc  ldstr    aFailedToRemove// "Failed to remove the channel: "
0x25ed1  ldloc.1
0x25ed2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25ed7  ldstr    asc_9EBEA// "."
0x25edc  call     string [mscorlib]System.String::Concat(string, string, string)
0x25ee1  call     T0x2B000010
0x25ee6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25eeb  leave.s  loc_25F0D
0x25eed  ldarg.0
0x25eee  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Services.RemoteChannelManager::logger
0x25ef3  dup
0x25ef4  brtrue.s loc_25EF8
0x25ef6  pop
0x25ef7  ret
0x25ef8  ldstr    aTheRemoteChann// "The remote channel with uri {0} was not"...
0x25efd  ldarg.1
0x25efe  call     string [mscorlib]System.String::Format(string, object)
0x25f03  call     T0x2B000010
0x25f08  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25f0d  ret
```
