# __vcrt_thread_detach

- ea: `0x1004175ec`
- end: `0x1004175fe`
- name: `__vcrt_thread_detach`
- size: `18`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x100416dbc`
- `0x100416dec`

## callees

- `0x100417a28`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_detach()
{
  _vcrt_freeptd(0);
  return 1;
}

```

## disassembly

```asm
0x1004175ec  sub     rsp, 28h
0x1004175f0  xor     ecx, ecx; Block
0x1004175f2  call    __vcrt_freeptd
0x1004175f7  mov     al, 1
0x1004175f9  add     rsp, 28h
0x1004175fd  retn
```
