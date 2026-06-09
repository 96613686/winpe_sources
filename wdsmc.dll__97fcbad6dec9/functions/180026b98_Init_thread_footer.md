# _Init_thread_footer

- ea: `0x180026b98`
- end: `0x180026c01`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002334c`
- `0x180023404`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180026bfa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026ba8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026ba8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026be8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026be8`

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
0x180026b98  push    rbx
0x180026b9a  sub     rsp, 20h
0x180026b9e  mov     rbx, rcx
0x180026ba1  lea     rcx, SRWLock; SRWLock
0x180026ba8  call    cs:__imp_AcquireSRWLockExclusive
0x180026bae  mov     eax, cs:_Init_global_epoch
0x180026bb4  lea     rcx, SRWLock; SRWLock
0x180026bbb  mov     edx, cs:_tls_index
0x180026bc1  inc     eax
0x180026bc3  mov     cs:_Init_global_epoch, eax
0x180026bc9  mov     [rbx], eax
0x180026bcb  mov     rax, gs:58h
0x180026bd4  mov     r9d, 4
0x180026bda  mov     r8, [rax+rdx*8]
0x180026bde  mov     eax, cs:_Init_global_epoch
0x180026be4  mov     [r9+r8], eax
0x180026be8  call    cs:__imp_ReleaseSRWLockExclusive
0x180026bee  lea     rcx, ConditionVariable
0x180026bf5  add     rsp, 20h
0x180026bf9  pop     rbx
0x180026bfa  jmp     cs:__imp_WakeAllConditionVariable
```
