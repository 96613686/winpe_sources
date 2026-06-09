# _Init_thread_header

- ea: `0x180002410`
- end: `0x18000248b`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a20`

## callees

- `0x180002410`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002448`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002448`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002484`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002420`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002420`

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
0x180002410  push    rbx
0x180002412  sub     rsp, 20h
0x180002416  mov     rbx, rcx
0x180002419  lea     rcx, SRWLock; SRWLock
0x180002420  call    cs:__imp_AcquireSRWLockExclusive
0x180002426  cmp     dword ptr [rbx], 0
0x180002429  jnz     short loc_180002450
0x18000242b  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002431  jmp     short loc_180002478
0x180002433  xor     r9d, r9d; Flags
0x180002436  lea     rdx, SRWLock; SRWLock
0x18000243d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180002441  lea     rcx, ConditionVariable; ConditionVariable
0x180002448  call    cs:__imp_SleepConditionVariableSRW
0x18000244e  jmp     short loc_180002426
0x180002450  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002453  jz      short loc_180002433
0x180002455  mov     rax, gs:58h
0x18000245e  mov     ecx, cs:_tls_index
0x180002464  mov     r8d, 4
0x18000246a  mov     rdx, [rax+rcx*8]
0x18000246e  mov     eax, cs:_Init_global_epoch
0x180002474  mov     [r8+rdx], eax
0x180002478  lea     rcx, SRWLock
0x18000247f  add     rsp, 20h
0x180002483  pop     rbx
0x180002484  jmp     cs:__imp_ReleaseSRWLockExclusive
```
