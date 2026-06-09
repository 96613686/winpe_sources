# _Init_thread_header

- ea: `0x180001ad4`
- end: `0x180001b4f`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180004fd0`

## callees

- `0x180001ad4`

## import_xrefs

- `KERNEL32!SleepConditionVariableSRW` at `0x180001b0c`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001b0c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001b48`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001ae4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001ae4`

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
0x180001ad4  push    rbx
0x180001ad6  sub     rsp, 20h
0x180001ada  mov     rbx, rcx
0x180001add  lea     rcx, SRWLock; SRWLock
0x180001ae4  call    cs:__imp_AcquireSRWLockExclusive
0x180001aea  cmp     dword ptr [rbx], 0
0x180001aed  jnz     short loc_180001B14
0x180001aef  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001af5  jmp     short loc_180001B3C
0x180001af7  xor     r9d, r9d; Flags
0x180001afa  lea     rdx, SRWLock; SRWLock
0x180001b01  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001b05  lea     rcx, ConditionVariable; ConditionVariable
0x180001b0c  call    cs:__imp_SleepConditionVariableSRW
0x180001b12  jmp     short loc_180001AEA
0x180001b14  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001b17  jz      short loc_180001AF7
0x180001b19  mov     rax, gs:58h
0x180001b22  mov     ecx, cs:_tls_index
0x180001b28  mov     r8d, 4
0x180001b2e  mov     rdx, [rax+rcx*8]
0x180001b32  mov     eax, cs:_Init_global_epoch
0x180001b38  mov     [r8+rdx], eax
0x180001b3c  lea     rcx, SRWLock
0x180001b43  add     rsp, 20h
0x180001b47  pop     rbx
0x180001b48  jmp     cs:__imp_ReleaseSRWLockExclusive
```
