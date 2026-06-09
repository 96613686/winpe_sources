# UmpoUninitializeEffectivePowerModeCallbacks

- ea: `0x18000f864`
- end: `0x18000f91f`
- name: `UmpoUninitializeEffectivePowerModeCallbacks`
- size: `187`
- prototype: `DWORD()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dc64`
- `0x1800165a8`

## callees

- `0x18000f864`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f883`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f883`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f86f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f86f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f895`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8b2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8cf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8ec`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f895`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8b2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8cf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f8ec`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000f909`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000f909`

## pseudocode

```c
DWORD UmpoUninitializeEffectivePowerModeCallbacks()
{
  DWORD result; // eax

  RtlAcquireSRWLockExclusive(UmpoEpmLock);
  UmpoPublishEffectivePowerMode = 0;
  result = RtlReleaseSRWLockExclusive(UmpoEpmLock);
  if ( UmpoRegistrationEnergySaver )
  {
    result = RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoRegistrationEnergySaver);
    UmpoRegistrationEnergySaver = 0;
  }
  if ( UmpoRegistrationGameMode )
  {
    result = RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoRegistrationGameMode);
    UmpoRegistrationGameMode = 0;
  }
  if ( UmpoRegistrationMixedReality )
  {
    result = RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoRegistrationMixedReality);
    UmpoRegistrationMixedReality = 0;
  }
  if ( UmpoRegistrationUserConfiguredPowerMode )
  {
    result = RtlUnsubscribeWnfNotificationWaitForCompletion(UmpoRegistrationUserConfiguredPowerMode);
    UmpoRegistrationUserConfiguredPowerMode = 0;
  }
  if ( UmpoRegistrationSchemePersonality )
  {
    result = PowerSettingUnregisterNotification(UmpoRegistrationSchemePersonality);
    UmpoRegistrationSchemePersonality = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f864  sub     rsp, 28h
0x18000f868  lea     rcx, UmpoEpmLock
0x18000f86f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f875  lea     rcx, UmpoEpmLock
0x18000f87c  mov     cs:UmpoPublishEffectivePowerMode, 0
0x18000f883  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000f889  mov     rcx, cs:UmpoRegistrationEnergySaver
0x18000f890  test    rcx, rcx
0x18000f893  jz      short loc_18000F8A6
0x18000f895  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f89b  mov     cs:UmpoRegistrationEnergySaver, 0
0x18000f8a6  mov     rcx, cs:UmpoRegistrationGameMode
0x18000f8ad  test    rcx, rcx
0x18000f8b0  jz      short loc_18000F8C3
0x18000f8b2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f8b8  mov     cs:UmpoRegistrationGameMode, 0
0x18000f8c3  mov     rcx, cs:UmpoRegistrationMixedReality
0x18000f8ca  test    rcx, rcx
0x18000f8cd  jz      short loc_18000F8E0
0x18000f8cf  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f8d5  mov     cs:UmpoRegistrationMixedReality, 0
0x18000f8e0  mov     rcx, cs:UmpoRegistrationUserConfiguredPowerMode
0x18000f8e7  test    rcx, rcx
0x18000f8ea  jz      short loc_18000F8FD
0x18000f8ec  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f8f2  mov     cs:UmpoRegistrationUserConfiguredPowerMode, 0
0x18000f8fd  mov     rcx, cs:UmpoRegistrationSchemePersonality; RegistrationHandle
0x18000f904  test    rcx, rcx
0x18000f907  jz      short loc_18000F91A
0x18000f909  call    cs:__imp_PowerSettingUnregisterNotification
0x18000f90f  mov     cs:UmpoRegistrationSchemePersonality, 0
0x18000f91a  add     rsp, 28h
0x18000f91e  retn
```
