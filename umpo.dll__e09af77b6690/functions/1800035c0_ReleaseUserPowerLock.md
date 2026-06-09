# ReleaseUserPowerLock

- ea: `0x1800035c0`
- end: `0x180003638`
- name: `ReleaseUserPowerLock`
- size: `120`
- prototype: `void()`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d4`
- `0x180002d8c`
- `0x180003370`
- `0x1800034c0`
- `0x180003560`
- `0x180007790`
- `0x180014e50`

## callees

- `0x1800035c0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000360e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000360e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800035f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800035f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800035d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800035d0`

## pseudocode

```c
void ReleaseUserPowerLock()
{
  unsigned int Value; // ebx
  BOOL v1; // edi
  unsigned int v2; // ebx

  Value = (unsigned int)TlsGetValue(UmpoUserPowerTlsSlot);
  if ( !Value )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v1 = UmpoUserPowerLockThread == GetCurrentThreadId();
  v2 = Value - 1;
  TlsSetValue(UmpoUserPowerTlsSlot, (LPVOID)v2);
  if ( !v2 )
  {
    if ( v1 )
    {
      UmpoUserPowerLockThread = 0;
      ReleaseSRWLockExclusive(&UmpoUserPowerLock);
    }
    else
    {
      ReleaseSRWLockShared(&UmpoUserPowerLock);
    }
  }
}

```

## disassembly

```asm
0x1800035c0  mov     [rsp+arg_0], rbx
0x1800035c5  push    rdi
0x1800035c6  sub     rsp, 20h
0x1800035ca  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x1800035d0  call    cs:__imp_TlsGetValue
0x1800035d6  mov     rbx, rax
0x1800035d9  test    eax, eax
0x1800035db  jz      short loc_18000361F
0x1800035dd  call    cs:__imp_GetCurrentThreadId
0x1800035e3  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x1800035e9  xor     edi, edi
0x1800035eb  cmp     cs:UmpoUserPowerLockThread, eax
0x1800035f1  setz    dil
0x1800035f5  dec     ebx
0x1800035f7  mov     edx, ebx; lpTlsValue
0x1800035f9  call    cs:__imp_TlsSetValue
0x1800035ff  test    ebx, ebx
0x180003601  jnz     short loc_180003614
0x180003603  lea     rcx, UmpoUserPowerLock; SRWLock
0x18000360a  test    edi, edi
0x18000360c  jnz     short loc_180003626
0x18000360e  call    cs:__imp_ReleaseSRWLockShared
0x180003614  mov     rbx, [rsp+28h+arg_0]
0x180003619  add     rsp, 20h
0x18000361d  pop     rdi
0x18000361e  retn
0x18000361f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003624  jmp     short loc_1800035DD
0x180003626  mov     cs:UmpoUserPowerLockThread, 0
0x180003630  call    cs:__imp_ReleaseSRWLockExclusive
0x180003636  jmp     short loc_180003614
```
