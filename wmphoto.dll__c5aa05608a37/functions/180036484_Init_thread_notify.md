# _Init_thread_notify

- ea: `0x180036484`
- end: `0x1800364c3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800363b0`

## callees

- `0x180036484`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800364ab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800364ab`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800364bc`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180050358 )
    return qword_180050358(&unk_180050318);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180036484  sub     rsp, 28h
0x180036488  mov     rax, cs:qword_180050358
0x18003648f  test    rax, rax
0x180036492  jz      short loc_1800364A4
0x180036494  lea     rcx, unk_180050318
0x18003649b  add     rsp, 28h
0x18003649f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800364a4  mov     rcx, cs:hHandle; hEvent
0x1800364ab  call    cs:__imp_SetEvent
0x1800364b1  mov     rcx, cs:hHandle
0x1800364b8  add     rsp, 28h
0x1800364bc  jmp     cs:__imp_ResetEvent
```
