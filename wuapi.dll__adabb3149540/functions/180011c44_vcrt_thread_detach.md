# __vcrt_thread_detach

- ea: `0x180011c44`
- end: `0x180011c54`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd9c`
- `0x18000fdcc`

## callees

- `0x180011f98`

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
0x180011c44  sub     rsp, 28h
0x180011c48  call    __vcrt_freeptd_for_this_thread
0x180011c4d  mov     al, 1
0x180011c4f  add     rsp, 28h
0x180011c53  retn
```
