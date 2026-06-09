# __acrt_thread_detach

- ea: `0x10041b07c`
- end: `0x10041b08c`
- name: `__acrt_thread_detach`
- size: `16`
- prototype: `__crt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100416dec`

## callees

- `0x10041b774`

## pseudocode

```c
__crt_bool __cdecl _acrt_thread_detach()
{
  _acrt_freeptd();
  return 1;
}

```

## disassembly

```asm
0x10041b07c  sub     rsp, 28h
0x10041b080  call    __acrt_freeptd
0x10041b085  mov     al, 1
0x10041b087  add     rsp, 28h
0x10041b08b  retn
```
