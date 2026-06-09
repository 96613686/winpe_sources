# _Init_thread_footer

- ea: `0x180013e58`
- end: `0x180013ec1`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003230`
- `0x180005394`
- `0x180006580`
- `0x18000b194`
- `0x18000e6ac`
- `0x18001cb70`
- `0x18001d490`
- `0x18001d520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e68`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180013eba`

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
0x180013e58  push    rbx
0x180013e5a  sub     rsp, 20h
0x180013e5e  mov     rbx, rcx
0x180013e61  lea     rcx, SRWLock; SRWLock
0x180013e68  call    cs:__imp_AcquireSRWLockExclusive
0x180013e6e  mov     eax, cs:_Init_global_epoch
0x180013e74  lea     rcx, SRWLock; SRWLock
0x180013e7b  mov     edx, cs:_tls_index
0x180013e81  inc     eax
0x180013e83  mov     cs:_Init_global_epoch, eax
0x180013e89  mov     [rbx], eax
0x180013e8b  mov     rax, gs:58h
0x180013e94  mov     r9d, 4
0x180013e9a  mov     r8, [rax+rdx*8]
0x180013e9e  mov     eax, cs:_Init_global_epoch
0x180013ea4  mov     [r9+r8], eax
0x180013ea8  call    cs:__imp_ReleaseSRWLockExclusive
0x180013eae  lea     rcx, ConditionVariable
0x180013eb5  add     rsp, 20h
0x180013eb9  pop     rbx
0x180013eba  jmp     cs:__imp_WakeAllConditionVariable
```
