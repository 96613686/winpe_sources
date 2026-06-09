# _Init_thread_header

- ea: `0x180001f7c`
- end: `0x180001ff7`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001aa14`
- `0x18001b048`

## callees

- `0x180001f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001fb4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001fb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001ff0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f8c`

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
0x180001f7c  push    rbx
0x180001f7e  sub     rsp, 20h
0x180001f82  mov     rbx, rcx
0x180001f85  lea     rcx, SRWLock; SRWLock
0x180001f8c  call    cs:__imp_AcquireSRWLockExclusive
0x180001f92  cmp     dword ptr [rbx], 0
0x180001f95  jnz     short loc_180001FBC
0x180001f97  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001f9d  jmp     short loc_180001FE4
0x180001f9f  xor     r9d, r9d; Flags
0x180001fa2  lea     rdx, SRWLock; SRWLock
0x180001fa9  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001fad  lea     rcx, ConditionVariable; ConditionVariable
0x180001fb4  call    cs:__imp_SleepConditionVariableSRW
0x180001fba  jmp     short loc_180001F92
0x180001fbc  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001fbf  jz      short loc_180001F9F
0x180001fc1  mov     rax, gs:58h
0x180001fca  mov     ecx, cs:_tls_index
0x180001fd0  mov     r8d, 4
0x180001fd6  mov     rdx, [rax+rcx*8]
0x180001fda  mov     eax, cs:_Init_global_epoch
0x180001fe0  mov     [r8+rdx], eax
0x180001fe4  lea     rcx, SRWLock
0x180001feb  add     rsp, 20h
0x180001fef  pop     rbx
0x180001ff0  jmp     cs:__imp_ReleaseSRWLockExclusive
```
