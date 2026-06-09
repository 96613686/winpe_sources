# __vcrt_thread_detach

- ea: `0x180011bf4`
- end: `0x180011c04`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd4c`
- `0x18000fd7c`

## callees

- `0x180011f48`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_detach()
{
  _vcrt_freeptd_for_this_thread();
  return 1;
}

```

## disassembly

```asm
0x180011bf4  sub     rsp, 28h
0x180011bf8  call    __vcrt_freeptd_for_this_thread
0x180011bfd  mov     al, 1
0x180011bff  add     rsp, 28h
0x180011c03  retn
```
