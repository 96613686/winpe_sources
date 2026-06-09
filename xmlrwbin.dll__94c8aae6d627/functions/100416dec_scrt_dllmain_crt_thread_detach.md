# __scrt_dllmain_crt_thread_detach

- ea: `0x100416dec`
- end: `0x100416e01`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1004165c0`

## callees

- `0x1004175ec`
- `0x10041b07c`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _acrt_thread_detach();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x100416dec  sub     rsp, 28h
0x100416df0  call    __acrt_thread_detach
0x100416df5  call    __vcrt_thread_detach
0x100416dfa  mov     al, 1
0x100416dfc  add     rsp, 28h
0x100416e00  retn
```
