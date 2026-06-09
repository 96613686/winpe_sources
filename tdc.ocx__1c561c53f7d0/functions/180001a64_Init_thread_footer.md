# _Init_thread_footer

- ea: `0x180001a64`
- end: `0x180001acd`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180004fd0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001ab4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001ab4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001a74`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001a74`
- `KERNEL32!WakeAllConditionVariable` at `0x180001ac6`

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
0x180001a64  push    rbx
0x180001a66  sub     rsp, 20h
0x180001a6a  mov     rbx, rcx
0x180001a6d  lea     rcx, SRWLock; SRWLock
0x180001a74  call    cs:__imp_AcquireSRWLockExclusive
0x180001a7a  mov     eax, cs:_Init_global_epoch
0x180001a80  lea     rcx, SRWLock; SRWLock
0x180001a87  mov     edx, cs:_tls_index
0x180001a8d  inc     eax
0x180001a8f  mov     cs:_Init_global_epoch, eax
0x180001a95  mov     [rbx], eax
0x180001a97  mov     rax, gs:58h
0x180001aa0  mov     r9d, 4
0x180001aa6  mov     r8, [rax+rdx*8]
0x180001aaa  mov     eax, cs:_Init_global_epoch
0x180001ab0  mov     [r9+r8], eax
0x180001ab4  call    cs:__imp_ReleaseSRWLockExclusive
0x180001aba  lea     rcx, ConditionVariable
0x180001ac1  add     rsp, 20h
0x180001ac5  pop     rbx
0x180001ac6  jmp     cs:__imp_WakeAllConditionVariable
```
