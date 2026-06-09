# _Init_thread_footer

- ea: `0x180001f0c`
- end: `0x180001f75`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001aa14`
- `0x18001b048`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180001f6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f1c`

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
0x180001f0c  push    rbx
0x180001f0e  sub     rsp, 20h
0x180001f12  mov     rbx, rcx
0x180001f15  lea     rcx, SRWLock; SRWLock
0x180001f1c  call    cs:__imp_AcquireSRWLockExclusive
0x180001f22  mov     eax, cs:_Init_global_epoch
0x180001f28  lea     rcx, SRWLock; SRWLock
0x180001f2f  mov     edx, cs:_tls_index
0x180001f35  inc     eax
0x180001f37  mov     cs:_Init_global_epoch, eax
0x180001f3d  mov     [rbx], eax
0x180001f3f  mov     rax, gs:58h
0x180001f48  mov     r9d, 4
0x180001f4e  mov     r8, [rax+rdx*8]
0x180001f52  mov     eax, cs:_Init_global_epoch
0x180001f58  mov     [r9+r8], eax
0x180001f5c  call    cs:__imp_ReleaseSRWLockExclusive
0x180001f62  lea     rcx, ConditionVariable
0x180001f69  add     rsp, 20h
0x180001f6d  pop     rbx
0x180001f6e  jmp     cs:__imp_WakeAllConditionVariable
```
