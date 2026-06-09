# _Init_thread_notify

- ea: `0x1800027a0`
- end: `0x1800027df`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002690`
- `0x1800026cc`

## callees

- `0x1800027a0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800027c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800027c7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800027d8`

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
0x1800027a0  sub     rsp, 28h
0x1800027a4  mov     rax, cs:qword_1800C72E0
0x1800027ab  test    rax, rax
0x1800027ae  jz      short loc_1800027C0
0x1800027b0  lea     rcx, qword_1800C72A0
0x1800027b7  add     rsp, 28h
0x1800027bb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c0  mov     rcx, cs:hHandle; hEvent
0x1800027c7  call    cs:__imp_SetEvent
0x1800027cd  mov     rcx, cs:hHandle
0x1800027d4  add     rsp, 28h
0x1800027d8  jmp     cs:__imp_ResetEvent
```
