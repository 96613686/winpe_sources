# _Init_thread_wait_v2

- ea: `0x1800027e8`
- end: `0x180002846`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002734`

## callees

- `0x1800027e8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000283f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000281a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000281a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000282e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000282e`

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
0x1800027e8  sub     rsp, 28h
0x1800027ec  mov     rax, cs:qword_1800C72D8
0x1800027f3  test    rax, rax
0x1800027f6  jz      short loc_180002813
0x1800027f8  or      r8d, 0FFFFFFFFh
0x1800027fc  lea     rdx, CriticalSection
0x180002803  lea     rcx, qword_1800C72A0
0x18000280a  add     rsp, 28h
0x18000280e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002813  lea     rcx, CriticalSection; lpCriticalSection
0x18000281a  call    cs:__imp_LeaveCriticalSection
0x180002820  mov     rcx, cs:hHandle; hHandle
0x180002827  xor     r8d, r8d; bAlertable
0x18000282a  lea     edx, [r8+64h]; dwMilliseconds
0x18000282e  call    cs:__imp_WaitForSingleObjectEx
0x180002834  lea     rcx, CriticalSection
0x18000283b  add     rsp, 28h
0x18000283f  jmp     cs:__imp_EnterCriticalSection
```
