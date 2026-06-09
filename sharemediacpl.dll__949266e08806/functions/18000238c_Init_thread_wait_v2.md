# _Init_thread_wait_v2

- ea: `0x18000238c`
- end: `0x1800023ea`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022d8`

## callees

- `0x18000238c`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800023be`
- `KERNEL32!LeaveCriticalSection` at `0x1800023be`
- `KERNEL32!EnterCriticalSection` at `0x1800023e3`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800023d2`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800023d2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18002A510 )
  {
    qword_18002A510(&qword_18002A4D8, &CriticalSection, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x18000238c  sub     rsp, 28h
0x180002390  mov     rax, cs:qword_18002A510
0x180002397  test    rax, rax
0x18000239a  jz      short loc_1800023B7
0x18000239c  or      r8d, 0FFFFFFFFh
0x1800023a0  lea     rdx, CriticalSection
0x1800023a7  lea     rcx, qword_18002A4D8
0x1800023ae  add     rsp, 28h
0x1800023b2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b7  lea     rcx, CriticalSection; lpCriticalSection
0x1800023be  call    cs:__imp_LeaveCriticalSection
0x1800023c4  mov     rcx, cs:hHandle; hHandle
0x1800023cb  xor     r8d, r8d; bAlertable
0x1800023ce  lea     edx, [r8+64h]; dwMilliseconds
0x1800023d2  call    cs:__imp_WaitForSingleObjectEx
0x1800023d8  lea     rcx, CriticalSection
0x1800023df  add     rsp, 28h
0x1800023e3  jmp     cs:__imp_EnterCriticalSection
```
