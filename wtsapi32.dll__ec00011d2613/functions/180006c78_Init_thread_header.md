# _Init_thread_header

- ea: `0x180006c78`
- end: `0x180006cf3`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c91c`

## callees

- `0x180006c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006cec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c88`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180006cb0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180006cb0`

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
0x180006c78  push    rbx
0x180006c7a  sub     rsp, 20h
0x180006c7e  mov     rbx, rcx
0x180006c81  lea     rcx, SRWLock; SRWLock
0x180006c88  call    cs:__imp_AcquireSRWLockExclusive
0x180006c8e  cmp     dword ptr [rbx], 0
0x180006c91  jnz     short loc_180006CB8
0x180006c93  mov     dword ptr [rbx], 0FFFFFFFFh
0x180006c99  jmp     short loc_180006CE0
0x180006c9b  xor     r9d, r9d; Flags
0x180006c9e  lea     rdx, SRWLock; SRWLock
0x180006ca5  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180006ca9  lea     rcx, ConditionVariable; ConditionVariable
0x180006cb0  call    cs:__imp_SleepConditionVariableSRW
0x180006cb6  jmp     short loc_180006C8E
0x180006cb8  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180006cbb  jz      short loc_180006C9B
0x180006cbd  mov     rax, gs:58h
0x180006cc6  mov     ecx, cs:_tls_index
0x180006ccc  mov     r8d, 4
0x180006cd2  mov     rdx, [rax+rcx*8]
0x180006cd6  mov     eax, cs:_Init_global_epoch
0x180006cdc  mov     [r8+rdx], eax
0x180006ce0  lea     rcx, SRWLock
0x180006ce7  add     rsp, 20h
0x180006ceb  pop     rbx
0x180006cec  jmp     cs:__imp_ReleaseSRWLockExclusive
```
