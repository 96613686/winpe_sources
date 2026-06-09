# _Init_thread_header

- ea: `0x180001d44`
- end: `0x180001dbf`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002177c`

## callees

- `0x180001d44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001db8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001d54`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001d7c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001d7c`

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
0x180001d44  push    rbx
0x180001d46  sub     rsp, 20h
0x180001d4a  mov     rbx, rcx
0x180001d4d  lea     rcx, SRWLock; SRWLock
0x180001d54  call    cs:__imp_AcquireSRWLockExclusive
0x180001d5a  cmp     dword ptr [rbx], 0
0x180001d5d  jnz     short loc_180001D84
0x180001d5f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001d65  jmp     short loc_180001DAC
0x180001d67  xor     r9d, r9d; Flags
0x180001d6a  lea     rdx, SRWLock; SRWLock
0x180001d71  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001d75  lea     rcx, ConditionVariable; ConditionVariable
0x180001d7c  call    cs:__imp_SleepConditionVariableSRW
0x180001d82  jmp     short loc_180001D5A
0x180001d84  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001d87  jz      short loc_180001D67
0x180001d89  mov     rax, gs:58h
0x180001d92  mov     ecx, cs:_tls_index
0x180001d98  mov     r8d, 4
0x180001d9e  mov     rdx, [rax+rcx*8]
0x180001da2  mov     eax, cs:_Init_global_epoch
0x180001da8  mov     [r8+rdx], eax
0x180001dac  lea     rcx, SRWLock
0x180001db3  add     rsp, 20h
0x180001db7  pop     rbx
0x180001db8  jmp     cs:__imp_ReleaseSRWLockExclusive
```
