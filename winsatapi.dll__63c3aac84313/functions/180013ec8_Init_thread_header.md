# _Init_thread_header

- ea: `0x180013ec8`
- end: `0x180013f43`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
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

## callees

- `0x180013ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013f3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ed8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ed8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180013f00`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180013f00`

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
0x180013ec8  push    rbx
0x180013eca  sub     rsp, 20h
0x180013ece  mov     rbx, rcx
0x180013ed1  lea     rcx, SRWLock; SRWLock
0x180013ed8  call    cs:__imp_AcquireSRWLockExclusive
0x180013ede  cmp     dword ptr [rbx], 0
0x180013ee1  jnz     short loc_180013F08
0x180013ee3  mov     dword ptr [rbx], 0FFFFFFFFh
0x180013ee9  jmp     short loc_180013F30
0x180013eeb  xor     r9d, r9d; Flags
0x180013eee  lea     rdx, SRWLock; SRWLock
0x180013ef5  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180013ef9  lea     rcx, ConditionVariable; ConditionVariable
0x180013f00  call    cs:__imp_SleepConditionVariableSRW
0x180013f06  jmp     short loc_180013EDE
0x180013f08  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180013f0b  jz      short loc_180013EEB
0x180013f0d  mov     rax, gs:58h
0x180013f16  mov     ecx, cs:_tls_index
0x180013f1c  mov     r8d, 4
0x180013f22  mov     rdx, [rax+rcx*8]
0x180013f26  mov     eax, cs:_Init_global_epoch
0x180013f2c  mov     [r8+rdx], eax
0x180013f30  lea     rcx, SRWLock
0x180013f37  add     rsp, 20h
0x180013f3b  pop     rbx
0x180013f3c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
