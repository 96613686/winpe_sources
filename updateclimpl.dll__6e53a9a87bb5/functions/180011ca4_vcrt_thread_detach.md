# __vcrt_thread_detach

- ea: `0x180011ca4`
- end: `0x180011cb4`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800103d8`
- `0x180010408`

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
0x180011ca4  sub     rsp, 28h
0x180011ca8  call    __vcrt_freeptd_for_this_thread
0x180011cad  mov     al, 1
0x180011caf  add     rsp, 28h
0x180011cb3  retn
```
