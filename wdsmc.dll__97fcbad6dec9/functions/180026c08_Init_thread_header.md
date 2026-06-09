# _Init_thread_header

- ea: `0x180026c08`
- end: `0x180026c80`
- name: `_Init_thread_header`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002334c`
- `0x180023404`

## callees

- `0x180026c08`

## import_xrefs

- `KERNEL32!SleepConditionVariableSRW` at `0x180026c3d`
- `KERNEL32!SleepConditionVariableSRW` at `0x180026c3d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026c18`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026c18`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026c79`

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
0x180026c08  push    rbx
0x180026c0a  sub     rsp, 20h
0x180026c0e  mov     rbx, rcx
0x180026c11  lea     rcx, SRWLock; SRWLock
0x180026c18  call    cs:__imp_AcquireSRWLockExclusive
0x180026c1e  cmp     dword ptr [rbx], 0
0x180026c21  jnz     short loc_180026C45
0x180026c23  or      dword ptr [rbx], 0FFFFFFFFh
0x180026c26  jmp     short loc_180026C6D
0x180026c28  xor     r9d, r9d; Flags
0x180026c2b  lea     rdx, SRWLock; SRWLock
0x180026c32  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180026c36  lea     rcx, ConditionVariable; ConditionVariable
0x180026c3d  call    cs:__imp_SleepConditionVariableSRW
0x180026c43  jmp     short loc_180026C1E
0x180026c45  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180026c48  jz      short loc_180026C28
0x180026c4a  mov     rax, gs:58h
0x180026c53  mov     ecx, cs:_tls_index
0x180026c59  mov     r8d, 4
0x180026c5f  mov     rdx, [rax+rcx*8]
0x180026c63  mov     eax, cs:_Init_global_epoch
0x180026c69  mov     [r8+rdx], eax
0x180026c6d  lea     rcx, SRWLock
0x180026c74  add     rsp, 20h
0x180026c78  pop     rbx
0x180026c79  jmp     cs:__imp_ReleaseSRWLockExclusive
```
