# UmpoAlpcSendPortMessage

- ea: `0x180001770`
- end: `0x180001811`
- name: `UmpoAlpcSendPortMessage`
- size: `161`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001720`
- `0x180001ae0`
- `0x180004380`
- `0x180017cbc`

## callees

- `0x180001770`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800017b7`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800017b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800017e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800017e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001784`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001784`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800017cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800017cf`
- `KERNELBASE!WTSIsServerContainer` at `0x1800017fb`
- `KERNELBASE!WTSIsServerContainer` at `0x1800017fb`

## pseudocode

```c
__int64 __fastcall UmpoAlpcSendPortMessage(__int64 a1)
{
  unsigned int v2; // edi

  AcquireSRWLockShared(&UmpoAlpcPoPortLock);
  if ( UmpoAlpcPoPort )
  {
    v2 = NtAlpcSendWaitReceivePort(UmpoAlpcPoPort, 0x10000, a1, 0, 0, 0, 0, 0);
  }
  else
  {
    v2 = 0;
    if ( !(unsigned __int8)WTSIsServerContainer() )
      v2 = 6;
  }
  if ( UmpoAlpcPoPortLockThread )
  {
    UmpoAlpcPoPortLockThread = 0;
    ReleaseSRWLockExclusive(&UmpoAlpcPoPortLock);
  }
  else
  {
    ReleaseSRWLockShared(&UmpoAlpcPoPortLock);
  }
  return v2;
}

```

## disassembly

```asm
0x180001770  mov     [rsp+arg_0], rbx
0x180001775  push    rdi
0x180001776  sub     rsp, 40h
0x18000177a  mov     rdi, rcx
0x18000177d  lea     rcx, UmpoAlpcPoPortLock; SRWLock
0x180001784  call    cs:__imp_AcquireSRWLockShared
0x18000178a  mov     rcx, cs:UmpoAlpcPoPort
0x180001791  test    rcx, rcx
0x180001794  jz      short loc_1800017FB
0x180001796  xor     ebx, ebx
0x180001798  xor     r9d, r9d
0x18000179b  mov     [rsp+48h+var_10], rbx
0x1800017a0  mov     r8, rdi
0x1800017a3  mov     [rsp+48h+var_18], rbx
0x1800017a8  mov     edx, 10000h
0x1800017ad  mov     [rsp+48h+var_20], rbx
0x1800017b2  mov     [rsp+48h+var_28], rbx
0x1800017b7  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800017bd  mov     edi, eax
0x1800017bf  cmp     cs:UmpoAlpcPoPortLockThread, 0
0x1800017c6  lea     rcx, UmpoAlpcPoPortLock; SRWLock
0x1800017cd  jnz     short loc_1800017E2
0x1800017cf  call    cs:__imp_ReleaseSRWLockShared
0x1800017d5  mov     eax, edi
0x1800017d7  mov     rbx, [rsp+48h+arg_0]
0x1800017dc  add     rsp, 40h
0x1800017e0  pop     rdi
0x1800017e1  retn
0x1800017e2  mov     cs:UmpoAlpcPoPortLockThread, ebx
0x1800017e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800017ee  mov     rbx, [rsp+48h+arg_0]
0x1800017f3  mov     eax, edi
0x1800017f5  add     rsp, 40h
0x1800017f9  pop     rdi
0x1800017fa  retn
0x1800017fb  call    cs:__imp_WTSIsServerContainer
0x180001801  xor     ebx, ebx
0x180001803  mov     ecx, 6
0x180001808  test    al, al
0x18000180a  mov     edi, ebx
0x18000180c  cmovz   edi, ecx
0x18000180f  jmp     short loc_1800017BF
```
