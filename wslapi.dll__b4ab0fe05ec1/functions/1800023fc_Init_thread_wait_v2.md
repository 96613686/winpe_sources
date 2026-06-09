# _Init_thread_wait_v2

- ea: `0x1800023fc`
- end: `0x18000245a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002348`

## callees

- `0x1800023fc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002442`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002442`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000242e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000242e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002453`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800133B0 )
  {
    qword_1800133B0(&qword_180013378, &CriticalSection, 0xFFFFFFFFLL);
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
0x1800023fc  sub     rsp, 28h
0x180002400  mov     rax, cs:qword_1800133B0
0x180002407  test    rax, rax
0x18000240a  jz      short loc_180002427
0x18000240c  or      r8d, 0FFFFFFFFh
0x180002410  lea     rdx, CriticalSection
0x180002417  lea     rcx, qword_180013378
0x18000241e  add     rsp, 28h
0x180002422  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002427  lea     rcx, CriticalSection; lpCriticalSection
0x18000242e  call    cs:__imp_LeaveCriticalSection
0x180002434  mov     rcx, cs:hHandle; hHandle
0x18000243b  xor     r8d, r8d; bAlertable
0x18000243e  lea     edx, [r8+64h]; dwMilliseconds
0x180002442  call    cs:__imp_WaitForSingleObjectEx
0x180002448  lea     rcx, CriticalSection
0x18000244f  add     rsp, 28h
0x180002453  jmp     cs:__imp_EnterCriticalSection
```
