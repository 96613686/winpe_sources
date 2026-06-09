# _Init_thread_notify

- ea: `0x180002344`
- end: `0x180002383`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002270`

## callees

- `0x180002344`
- `0x18001e010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18000237c`
- `KERNEL32!SetEvent` at `0x18000236b`
- `KERNEL32!SetEvent` at `0x18000236b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18002A518 )
    return qword_18002A518(&qword_18002A4D8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002344  sub     rsp, 28h
0x180002348  mov     rax, cs:qword_18002A518
0x18000234f  test    rax, rax
0x180002352  jz      short loc_180002364
0x180002354  lea     rcx, qword_18002A4D8
0x18000235b  add     rsp, 28h
0x18000235f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002364  mov     rcx, cs:hHandle; hEvent
0x18000236b  call    cs:__imp_SetEvent
0x180002371  mov     rcx, cs:hHandle
0x180002378  add     rsp, 28h
0x18000237c  jmp     cs:__imp_ResetEvent
```
