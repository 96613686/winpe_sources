# _Init_thread_footer

- ea: `0x180002708`
- end: `0x180002771`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002758`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002758`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002718`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002718`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000276a`

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
0x180002708  push    rbx
0x18000270a  sub     rsp, 20h
0x18000270e  mov     rbx, rcx
0x180002711  lea     rcx, SRWLock; SRWLock
0x180002718  call    cs:__imp_AcquireSRWLockExclusive
0x18000271e  mov     eax, cs:_Init_global_epoch
0x180002724  lea     rcx, SRWLock; SRWLock
0x18000272b  mov     edx, cs:_tls_index
0x180002731  inc     eax
0x180002733  mov     cs:_Init_global_epoch, eax
0x180002739  mov     [rbx], eax
0x18000273b  mov     rax, gs:58h
0x180002744  mov     r9d, 4
0x18000274a  mov     r8, [rax+rdx*8]
0x18000274e  mov     eax, cs:_Init_global_epoch
0x180002754  mov     [r9+r8], eax
0x180002758  call    cs:__imp_ReleaseSRWLockExclusive
0x18000275e  lea     rcx, ConditionVariable
0x180002765  add     rsp, 20h
0x180002769  pop     rbx
0x18000276a  jmp     cs:__imp_WakeAllConditionVariable
```
