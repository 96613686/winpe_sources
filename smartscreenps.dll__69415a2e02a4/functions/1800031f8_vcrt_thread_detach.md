# __vcrt_thread_detach

- ea: `0x1800031f8`
- end: `0x180003208`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001640`
- `0x180001670`

## callees

- `0x180003388`

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
0x1800031f8  sub     rsp, 28h
0x1800031fc  call    __vcrt_freeptd_for_this_thread
0x180003201  mov     al, 1
0x180003203  add     rsp, 28h
0x180003207  retn
```
