# UmpoUpdatePowerSettingOverrides

- ea: `0x18000e360`
- end: `0x18000e3dc`
- name: `UmpoUpdatePowerSettingOverrides`
- size: `124`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002bc0`
- `0x180008e68`
- `0x18000d700`
- `0x18000e360`
- `0x18000f3dc`
- `0x18000f5f4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000e3a0`
- `ntdll!EtwEventWrite` at `0x18000e3a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e37b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e37b`

## pseudocode

```c
__int64 UmpoUpdatePowerSettingOverrides()
{
  unsigned int UpdatedOverrides; // ebx
  __int64 v1; // rdx

  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  UpdatedOverrides = UmpoGetUpdatedOverrides();
  if ( !UpdatedOverrides )
  {
    EtwEventWrite(UmpoProviderHandle, UMPO_EVT_OVERRIDE_DLL_SETTINGS_UPDATE, 0, 0);
    UmpoRundownOverrideSettings(0);
    UmpoNotifyKernelAllPowerPolicyChanged(0, v1);
    UmpoRefreshProfileSettings();
  }
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
  return UpdatedOverrides;
}

```

## disassembly

```asm
0x18000e360  push    rbx
0x18000e362  sub     rsp, 20h
0x18000e366  cmp     cs:byte_180024FA8, 1
0x18000e36d  jz      short loc_18000E374
0x18000e36f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e374  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000e37b  call    cs:__imp_EnterCriticalSection
0x18000e381  call    UmpoGetUpdatedOverrides
0x18000e386  mov     ebx, eax
0x18000e388  test    eax, eax
0x18000e38a  jnz     short loc_18000E3B9
0x18000e38c  mov     rcx, cs:UmpoProviderHandle
0x18000e393  lea     rdx, UMPO_EVT_OVERRIDE_DLL_SETTINGS_UPDATE
0x18000e39a  xor     r9d, r9d
0x18000e39d  xor     r8d, r8d
0x18000e3a0  call    cs:__imp_EtwEventWrite
0x18000e3a6  xor     ecx, ecx
0x18000e3a8  call    UmpoRundownOverrideSettings
0x18000e3ad  xor     ecx, ecx
0x18000e3af  call    UmpoNotifyKernelAllPowerPolicyChanged
0x18000e3b4  call    UmpoRefreshProfileSettings
0x18000e3b9  cmp     cs:byte_180024FA8, 1
0x18000e3c0  jz      short loc_18000E3C7
0x18000e3c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e3c7  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000e3ce  call    cs:__imp_LeaveCriticalSection
0x18000e3d4  mov     eax, ebx
0x18000e3d6  add     rsp, 20h
0x18000e3da  pop     rbx
0x18000e3db  retn
```
