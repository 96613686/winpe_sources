# __vcrt_thread_detach

- ea: `0x180010cb4`
- end: `0x180010cc4`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee78`
- `0x18000eea8`

## callees

- `0x180011008`

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
0x180010cb4  sub     rsp, 28h
0x180010cb8  call    __vcrt_freeptd_for_this_thread
0x180010cbd  mov     al, 1
0x180010cbf  add     rsp, 28h
0x180010cc3  retn
```
