# _Init_thread_footer

- ea: `0x180006c08`
- end: `0x180006c71`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c91c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c18`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180006c6a`

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
0x180006c08  push    rbx
0x180006c0a  sub     rsp, 20h
0x180006c0e  mov     rbx, rcx
0x180006c11  lea     rcx, SRWLock; SRWLock
0x180006c18  call    cs:__imp_AcquireSRWLockExclusive
0x180006c1e  mov     eax, cs:_Init_global_epoch
0x180006c24  lea     rcx, SRWLock; SRWLock
0x180006c2b  mov     edx, cs:_tls_index
0x180006c31  inc     eax
0x180006c33  mov     cs:_Init_global_epoch, eax
0x180006c39  mov     [rbx], eax
0x180006c3b  mov     rax, gs:58h
0x180006c44  mov     r9d, 4
0x180006c4a  mov     r8, [rax+rdx*8]
0x180006c4e  mov     eax, cs:_Init_global_epoch
0x180006c54  mov     [r9+r8], eax
0x180006c58  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c5e  lea     rcx, ConditionVariable
0x180006c65  add     rsp, 20h
0x180006c69  pop     rbx
0x180006c6a  jmp     cs:__imp_WakeAllConditionVariable
```
