# UmpoGetUpdatedOverrides

- ea: `0x18000d700`
- end: `0x18000d7b4`
- name: `UmpoGetUpdatedOverrides`
- size: `180`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a574`
- `0x18000e360`

## callees

- `0x18000d700`
- `0x18000f3dc`
- `0x180019010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000d7a1`
- `ntdll!RtlFreeHeap` at `0x18000d7a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d789`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d751`

## pseudocode

```c
__int64 UmpoGetUpdatedOverrides()
{
  unsigned int v0; // ebx
  PVOID v1; // rdi
  int v3; // [rsp+30h] [rbp+8h] BYREF
  void *v4; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v4 = 0;
  v0 = ((__int64 (__fastcall *)(__int64 *, int *, void **))UmpoOverrideFn)(UmpoOverrideConfiguration, &v3, &v4);
  if ( !v0 )
  {
    if ( byte_1800248C8 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    EnterCriticalSection(&UmpoPowerSettingOverrideLock);
    v1 = UmpoPowerSettingOverride;
    UmpoPowerSettingOverride = v4;
    UmpoPowerSettingOverrideCount = v3;
    if ( byte_1800248C8 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LeaveCriticalSection(&UmpoPowerSettingOverrideLock);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  }
  return v0;
}

```

## disassembly

```asm
0x18000d700  mov     rax, rsp
0x18000d703  mov     [rax+18h], rbx
0x18000d707  push    rdi
0x18000d708  sub     rsp, 20h
0x18000d70c  mov     dword ptr [rax+8], 0
0x18000d713  lea     r8, [rax+10h]
0x18000d717  mov     qword ptr [rax+10h], 0
0x18000d71f  lea     rdx, [rax+8]
0x18000d723  mov     rax, cs:UmpoOverrideFn
0x18000d72a  lea     rcx, UmpoOverrideConfiguration
0x18000d731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d736  mov     ebx, eax
0x18000d738  test    eax, eax
0x18000d73a  jnz     short loc_18000D7A7
0x18000d73c  cmp     cs:byte_1800248C8, 1
0x18000d743  jz      short loc_18000D74A
0x18000d745  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d74a  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x18000d751  call    cs:__imp_EnterCriticalSection
0x18000d757  cmp     cs:byte_1800248C8, 1
0x18000d75e  mov     rax, [rsp+28h+arg_8]
0x18000d763  mov     rdi, cs:UmpoPowerSettingOverride
0x18000d76a  mov     cs:UmpoPowerSettingOverride, rax
0x18000d771  mov     eax, [rsp+28h+arg_0]
0x18000d775  mov     cs:UmpoPowerSettingOverrideCount, eax
0x18000d77b  jz      short loc_18000D782
0x18000d77d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d782  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x18000d789  call    cs:__imp_LeaveCriticalSection
0x18000d78f  mov     rcx, gs:60h
0x18000d798  mov     r8, rdi; P
0x18000d79b  xor     edx, edx; Flags
0x18000d79d  mov     rcx, [rcx+30h]; HeapHandle
0x18000d7a1  call    cs:__imp_RtlFreeHeap
0x18000d7a7  mov     eax, ebx
0x18000d7a9  mov     rbx, [rsp+28h+arg_10]
0x18000d7ae  add     rsp, 20h
0x18000d7b2  pop     rdi
0x18000d7b3  retn
```
