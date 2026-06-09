# _Init_thread_wait_v2

- ea: `0x1800027b8`
- end: `0x180002816`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002704`

## callees

- `0x1800027b8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000280f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800027fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800027fe`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800C72D8 )
  {
    qword_1800C72D8(&qword_1800C72A0, &CriticalSection, 0xFFFFFFFFLL);
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
0x1800027b8  sub     rsp, 28h
0x1800027bc  mov     rax, cs:qword_1800C72D8
0x1800027c3  test    rax, rax
0x1800027c6  jz      short loc_1800027E3
0x1800027c8  or      r8d, 0FFFFFFFFh
0x1800027cc  lea     rdx, CriticalSection
0x1800027d3  lea     rcx, qword_1800C72A0
0x1800027da  add     rsp, 28h
0x1800027de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800027e3  lea     rcx, CriticalSection; lpCriticalSection
0x1800027ea  call    cs:__imp_LeaveCriticalSection
0x1800027f0  mov     rcx, cs:hHandle; hHandle
0x1800027f7  xor     r8d, r8d; bAlertable
0x1800027fa  lea     edx, [r8+64h]; dwMilliseconds
0x1800027fe  call    cs:__imp_WaitForSingleObjectEx
0x180002804  lea     rcx, CriticalSection
0x18000280b  add     rsp, 28h
0x18000280f  jmp     cs:__imp_EnterCriticalSection
```
