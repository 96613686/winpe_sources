# _Init_thread_notify

- ea: `0x180002770`
- end: `0x1800027af`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002660`
- `0x18000269c`

## callees

- `0x180002770`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002797`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002797`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800027a8`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800C72E0 )
    return qword_1800C72E0(&qword_1800C72A0);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002770  sub     rsp, 28h
0x180002774  mov     rax, cs:qword_1800C72E0
0x18000277b  test    rax, rax
0x18000277e  jz      short loc_180002790
0x180002780  lea     rcx, qword_1800C72A0
0x180002787  add     rsp, 28h
0x18000278b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002790  mov     rcx, cs:hHandle; hEvent
0x180002797  call    cs:__imp_SetEvent
0x18000279d  mov     rcx, cs:hHandle
0x1800027a4  add     rsp, 28h
0x1800027a8  jmp     cs:__imp_ResetEvent
```
