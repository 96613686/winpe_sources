# _Init_thread_notify

- ea: `0x1800023b4`
- end: `0x1800023f3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022e0`

## callees

- `0x1800023b4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800023ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800023db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800023db`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800133B8 )
    return qword_1800133B8(&qword_180013378);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800023b4  sub     rsp, 28h
0x1800023b8  mov     rax, cs:qword_1800133B8
0x1800023bf  test    rax, rax
0x1800023c2  jz      short loc_1800023D4
0x1800023c4  lea     rcx, qword_180013378
0x1800023cb  add     rsp, 28h
0x1800023cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d4  mov     rcx, cs:hHandle; hEvent
0x1800023db  call    cs:__imp_SetEvent
0x1800023e1  mov     rcx, cs:hHandle
0x1800023e8  add     rsp, 28h
0x1800023ec  jmp     cs:__imp_ResetEvent
```
