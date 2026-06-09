# _Init_thread_footer

- ea: `0x180001cd4`
- end: `0x180001d3d`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002177c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001d24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001d24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001ce4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001ce4`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180001d36`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x180001cd4  push    rbx
0x180001cd6  sub     rsp, 20h
0x180001cda  mov     rbx, rcx
0x180001cdd  lea     rcx, SRWLock; SRWLock
0x180001ce4  call    cs:__imp_AcquireSRWLockExclusive
0x180001cea  mov     eax, cs:_Init_global_epoch
0x180001cf0  lea     rcx, SRWLock; SRWLock
0x180001cf7  mov     edx, cs:_tls_index
0x180001cfd  inc     eax
0x180001cff  mov     cs:_Init_global_epoch, eax
0x180001d05  mov     [rbx], eax
0x180001d07  mov     rax, gs:58h
0x180001d10  mov     r9d, 4
0x180001d16  mov     r8, [rax+rdx*8]
0x180001d1a  mov     eax, cs:_Init_global_epoch
0x180001d20  mov     [r9+r8], eax
0x180001d24  call    cs:__imp_ReleaseSRWLockExclusive
0x180001d2a  lea     rcx, ConditionVariable
0x180001d31  add     rsp, 20h
0x180001d35  pop     rbx
0x180001d36  jmp     cs:__imp_WakeAllConditionVariable
```
