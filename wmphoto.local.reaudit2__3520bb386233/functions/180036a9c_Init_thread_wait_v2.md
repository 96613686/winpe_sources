# _Init_thread_wait_v2

- ea: `0x180036a9c`
- end: `0x180036afa`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800369e8`

## callees

- `0x180036a9c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ae2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ace`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036ace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036af3`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180051350 )
  {
    qword_180051350(&qword_180051318, &CriticalSection, 0xFFFFFFFFLL);
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
0x180036a9c  sub     rsp, 28h
0x180036aa0  mov     rax, cs:qword_180051350
0x180036aa7  test    rax, rax
0x180036aaa  jz      short loc_180036AC7
0x180036aac  or      r8d, 0FFFFFFFFh
0x180036ab0  lea     rdx, CriticalSection
0x180036ab7  lea     rcx, qword_180051318
0x180036abe  add     rsp, 28h
0x180036ac2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac7  lea     rcx, CriticalSection; lpCriticalSection
0x180036ace  call    cs:__imp_LeaveCriticalSection
0x180036ad4  mov     rcx, cs:hHandle; hHandle
0x180036adb  xor     r8d, r8d; bAlertable
0x180036ade  lea     edx, [r8+64h]; dwMilliseconds
0x180036ae2  call    cs:__imp_WaitForSingleObjectEx
0x180036ae8  lea     rcx, CriticalSection
0x180036aef  add     rsp, 28h
0x180036af3  jmp     cs:__imp_EnterCriticalSection
```
