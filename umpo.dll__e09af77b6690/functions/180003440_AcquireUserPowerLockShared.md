# AcquireUserPowerLockShared

- ea: `0x180003440`
- end: `0x1800034b0`
- name: `AcquireUserPowerLockShared`
- size: `112`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d4`
- `0x180002d8c`
- `0x180003370`
- `0x1800034c0`

## callees

- `0x180003440`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003477`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003477`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003494`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000344f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000344f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003463`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003463`

## pseudocode

```c
BOOL __fastcall AcquireUserPowerLockShared(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int Value; // ebx

  if ( UmpoUserPowerTlsSlot == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( UmpoUserPowerLockThread == GetCurrentThreadId() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  Value = (unsigned int)TlsGetValue(UmpoUserPowerTlsSlot);
  if ( !Value )
    AcquireSRWLockShared(&UmpoUserPowerLock);
  if ( UmpoUserPowerLockThread )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  return TlsSetValue(UmpoUserPowerTlsSlot, (LPVOID)(Value + 1));
}

```

## disassembly

```asm
0x180003440  push    rbx
0x180003442  sub     rsp, 20h
0x180003446  cmp     cs:UmpoUserPowerTlsSlot, 0FFFFFFFFh
0x18000344d  jz      short loc_18000349B
0x18000344f  call    cs:__imp_GetCurrentThreadId
0x180003455  cmp     cs:UmpoUserPowerLockThread, eax
0x18000345b  jz      short loc_1800034A2
0x18000345d  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180003463  call    cs:__imp_TlsGetValue
0x180003469  mov     rbx, rax
0x18000346c  test    eax, eax
0x18000346e  jnz     short loc_18000347D
0x180003470  lea     rcx, UmpoUserPowerLock; SRWLock
0x180003477  call    cs:__imp_AcquireSRWLockShared
0x18000347d  cmp     cs:UmpoUserPowerLockThread, 0
0x180003484  jnz     short loc_1800034A9
0x180003486  mov     ecx, cs:UmpoUserPowerTlsSlot
0x18000348c  lea     edx, [rbx+1]
0x18000348f  add     rsp, 20h
0x180003493  pop     rbx
0x180003494  jmp     cs:__imp_TlsSetValue
0x18000349b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800034a0  jmp     short loc_18000344F
0x1800034a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800034a7  jmp     short loc_18000345D
0x1800034a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800034ae  jmp     short loc_180003486
```
