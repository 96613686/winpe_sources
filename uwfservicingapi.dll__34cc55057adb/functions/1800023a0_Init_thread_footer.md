# _Init_thread_footer

- ea: `0x1800023a0`
- end: `0x180002409`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a20`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180002402`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800023f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800023f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800023b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800023b0`

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
0x1800023a0  push    rbx
0x1800023a2  sub     rsp, 20h
0x1800023a6  mov     rbx, rcx
0x1800023a9  lea     rcx, SRWLock; SRWLock
0x1800023b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800023b6  mov     eax, cs:_Init_global_epoch
0x1800023bc  lea     rcx, SRWLock; SRWLock
0x1800023c3  mov     edx, cs:_tls_index
0x1800023c9  inc     eax
0x1800023cb  mov     cs:_Init_global_epoch, eax
0x1800023d1  mov     [rbx], eax
0x1800023d3  mov     rax, gs:58h
0x1800023dc  mov     r9d, 4
0x1800023e2  mov     r8, [rax+rdx*8]
0x1800023e6  mov     eax, cs:_Init_global_epoch
0x1800023ec  mov     [r9+r8], eax
0x1800023f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800023f6  lea     rcx, ConditionVariable
0x1800023fd  add     rsp, 20h
0x180002401  pop     rbx
0x180002402  jmp     cs:__imp_WakeAllConditionVariable
```
