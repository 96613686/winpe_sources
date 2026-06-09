# UmpoWnfProvEngineTurnCallback

- ea: `0x18000e750`
- end: `0x18000e83e`
- name: `UmpoWnfProvEngineTurnCallback`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002bc0`
- `0x18000a990`
- `0x18000e750`
- `0x18000f3dc`
- `0x18000f5f4`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000e808`
- `ntdll!EtwEventWrite` at `0x18000e808`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e823`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e823`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7bd`

## pseudocode

```c
__int64 __fastcall UmpoWnfProvEngineTurnCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        unsigned int a6)
{
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v9[2]; // [rsp+28h] [rbp-20h] BYREF

  if ( a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a6 >= 0xC )
  {
    if ( !a5 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (a5[1] & 1) != 0 && ((*a5 - 1) & 0xFFFFFFFA) == 0 )
    {
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      EnterCriticalSection(&UmpoSchemeLock);
      UmpoNotifyKernelAllPowerPolicyChanged(0, v6);
      UmpoCheckAndUpdateOverlayNotification(0);
      UmpoRefreshProfileSettings();
      v8 = *a5;
      v9[1] = 4;
      v9[0] = &v8;
      EtwEventWrite(UmpoProviderHandle, UMPO_EVT_PROV_ENGINE_TURN_APPLY, 1, v9);
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      LeaveCriticalSection(&UmpoSchemeLock);
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return 0;
}

```

## disassembly

```asm
0x18000e750  push    rbx
0x18000e752  sub     rsp, 40h
0x18000e756  mov     rax, cs:__security_cookie
0x18000e75d  xor     rax, rsp
0x18000e760  mov     [rsp+48h+var_10], rax
0x18000e765  test    r9, r9
0x18000e768  jz      short loc_18000E76F
0x18000e76a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e76f  cmp     [rsp+48h+arg_28], 0Ch
0x18000e774  jnb     short loc_18000E780
0x18000e776  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e77b  jmp     loc_18000E829
0x18000e780  mov     rbx, [rsp+48h+arg_20]
0x18000e785  test    rbx, rbx
0x18000e788  jnz     short loc_18000E78F
0x18000e78a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e78f  test    byte ptr [rbx+4], 1
0x18000e793  jz      loc_18000E829
0x18000e799  mov     eax, [rbx]
0x18000e79b  dec     eax
0x18000e79d  test    eax, 0FFFFFFFAh
0x18000e7a2  jnz     loc_18000E829
0x18000e7a8  cmp     cs:byte_180024FA8, 1
0x18000e7af  jz      short loc_18000E7B6
0x18000e7b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e7b6  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000e7bd  call    cs:__imp_EnterCriticalSection
0x18000e7c3  xor     ecx, ecx
0x18000e7c5  call    UmpoNotifyKernelAllPowerPolicyChanged
0x18000e7ca  xor     ecx, ecx
0x18000e7cc  call    UmpoCheckAndUpdateOverlayNotification
0x18000e7d1  call    UmpoRefreshProfileSettings
0x18000e7d6  mov     eax, [rbx]
0x18000e7d8  lea     r9, [rsp+48h+var_20]
0x18000e7dd  mov     rcx, cs:UmpoProviderHandle
0x18000e7e4  lea     rdx, UMPO_EVT_PROV_ENGINE_TURN_APPLY
0x18000e7eb  mov     [rsp+48h+var_28], eax
0x18000e7ef  mov     r8d, 1
0x18000e7f5  lea     rax, [rsp+48h+var_28]
0x18000e7fa  mov     [rsp+48h+var_18], 4
0x18000e803  mov     [rsp+48h+var_20], rax
0x18000e808  call    cs:__imp_EtwEventWrite
0x18000e80e  cmp     cs:byte_180024FA8, 1
0x18000e815  jz      short loc_18000E81C
0x18000e817  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e81c  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000e823  call    cs:__imp_LeaveCriticalSection
0x18000e829  xor     eax, eax
0x18000e82b  mov     rcx, [rsp+48h+var_10]
0x18000e830  xor     rcx, rsp; StackCookie
0x18000e833  call    __security_check_cookie
0x18000e838  add     rsp, 40h
0x18000e83c  pop     rbx
0x18000e83d  retn
```
