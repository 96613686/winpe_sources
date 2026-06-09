# _Init_thread_wait_v2

- ea: `0x1800364cc`
- end: `0x18003652a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036418`

## callees

- `0x1800364cc`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036512`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800364fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800364fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036523`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180050350 )
  {
    qword_180050350(&unk_180050318, &CriticalSection, 0xFFFFFFFFLL);
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
0x1800364cc  sub     rsp, 28h
0x1800364d0  mov     rax, cs:qword_180050350
0x1800364d7  test    rax, rax
0x1800364da  jz      short loc_1800364F7
0x1800364dc  or      r8d, 0FFFFFFFFh
0x1800364e0  lea     rdx, CriticalSection
0x1800364e7  lea     rcx, unk_180050318
0x1800364ee  add     rsp, 28h
0x1800364f2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800364f7  lea     rcx, CriticalSection; lpCriticalSection
0x1800364fe  call    cs:__imp_LeaveCriticalSection
0x180036504  mov     rcx, cs:hHandle; hHandle
0x18003650b  xor     r8d, r8d; bAlertable
0x18003650e  lea     edx, [r8+64h]; dwMilliseconds
0x180036512  call    cs:__imp_WaitForSingleObjectEx
0x180036518  lea     rcx, CriticalSection
0x18003651f  add     rsp, 28h
0x180036523  jmp     cs:__imp_EnterCriticalSection
```
