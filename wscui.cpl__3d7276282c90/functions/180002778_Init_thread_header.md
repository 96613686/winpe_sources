# _Init_thread_header

- ea: `0x180002778`
- end: `0x1800027f3`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ad0`

## callees

- `0x180002778`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800027ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002788`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002788`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800027b0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800027b0`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &SRWLock, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180002778  push    rbx
0x18000277a  sub     rsp, 20h
0x18000277e  mov     rbx, rcx
0x180002781  lea     rcx, SRWLock; SRWLock
0x180002788  call    cs:__imp_AcquireSRWLockExclusive
0x18000278e  cmp     dword ptr [rbx], 0
0x180002791  jnz     short loc_1800027B8
0x180002793  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002799  jmp     short loc_1800027E0
0x18000279b  xor     r9d, r9d; Flags
0x18000279e  lea     rdx, SRWLock; SRWLock
0x1800027a5  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800027a9  lea     rcx, ConditionVariable; ConditionVariable
0x1800027b0  call    cs:__imp_SleepConditionVariableSRW
0x1800027b6  jmp     short loc_18000278E
0x1800027b8  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800027bb  jz      short loc_18000279B
0x1800027bd  mov     rax, gs:58h
0x1800027c6  mov     ecx, cs:_tls_index
0x1800027cc  mov     r8d, 4
0x1800027d2  mov     rdx, [rax+rcx*8]
0x1800027d6  mov     eax, cs:_Init_global_epoch
0x1800027dc  mov     [r8+rdx], eax
0x1800027e0  lea     rcx, SRWLock
0x1800027e7  add     rsp, 20h
0x1800027eb  pop     rbx
0x1800027ec  jmp     cs:__imp_ReleaseSRWLockExclusive
```
