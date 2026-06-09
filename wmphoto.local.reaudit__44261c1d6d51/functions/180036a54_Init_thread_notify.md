# _Init_thread_notify

- ea: `0x180036a54`
- end: `0x180036a93`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036980`

## callees

- `0x180036a54`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036a7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036a7b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036a8c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180051358 )
    return qword_180051358(&qword_180051318);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180036a54  sub     rsp, 28h
0x180036a58  mov     rax, cs:qword_180051358
0x180036a5f  test    rax, rax
0x180036a62  jz      short loc_180036A74
0x180036a64  lea     rcx, qword_180051318
0x180036a6b  add     rsp, 28h
0x180036a6f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180036a74  mov     rcx, cs:hHandle; hEvent
0x180036a7b  call    cs:__imp_SetEvent
0x180036a81  mov     rcx, cs:hHandle
0x180036a88  add     rsp, 28h
0x180036a8c  jmp     cs:__imp_ResetEvent
```
