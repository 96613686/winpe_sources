# UmpoInternalInitializeSubscribeOnProvisioningComplete

- ea: `0x180013598`
- end: `0x18001362a`
- name: `UmpoInternalInitializeSubscribeOnProvisioningComplete`
- size: `146`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a030`

## callees

- `0x18000f3dc`
- `0x180013598`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001361f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001361f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800135d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800135d8`

## pseudocode

```c
__int64 UmpoInternalInitializeSubscribeOnProvisioningComplete()
{
  if ( UmpoIsPolicyManagerSupported )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  UmpoIsPolicyManagerSupported = 1;
  qword_180024CA8 = (__int64)&UmpoAdvancedSettingList;
  UmpoAdvancedSettingList = &UmpoAdvancedSettingList;
  ProvisioningCompleteSubscription = 0;
  InitializeCriticalSection(&UmpoAdvancedSettingListLock);
  byte_180024D68 = 1;
  return RtlSubscribeWnfStateChangeNotification(
           &ProvisioningCompleteSubscription,
           WNF_DEVM_PROVISIONING_COMPLETE,
           0,
           UmpoInternalInitializeCallbackForProvisioning,
           0,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x180013598  sub     rsp, 48h
0x18001359c  cmp     cs:UmpoIsPolicyManagerSupported, 0
0x1800135a3  jz      short loc_1800135AA
0x1800135a5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800135aa  lea     rax, UmpoAdvancedSettingList
0x1800135b1  mov     cs:UmpoIsPolicyManagerSupported, 1
0x1800135b8  lea     rcx, UmpoAdvancedSettingListLock; lpCriticalSection
0x1800135bf  mov     cs:qword_180024CA8, rax
0x1800135c6  mov     cs:UmpoAdvancedSettingList, rax
0x1800135cd  mov     cs:ProvisioningCompleteSubscription, 0
0x1800135d8  call    cs:__imp_InitializeCriticalSection
0x1800135de  mov     rdx, cs:WNF_DEVM_PROVISIONING_COMPLETE
0x1800135e5  lea     r9, UmpoInternalInitializeCallbackForProvisioning
0x1800135ec  mov     [rsp+48h+var_10], 0
0x1800135f4  lea     rcx, ProvisioningCompleteSubscription
0x1800135fb  mov     [rsp+48h+var_18], 0
0x180013603  xor     r8d, r8d
0x180013606  mov     [rsp+48h+var_20], 0
0x18001360f  mov     [rsp+48h+var_28], 0
0x180013618  mov     cs:byte_180024D68, 1
0x18001361f  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180013625  add     rsp, 48h
0x180013629  retn
```
