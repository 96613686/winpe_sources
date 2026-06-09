# wmainCRTStartup

- ea: `0x1400012f0`
- end: `0x140001302`
- name: `wmainCRTStartup`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001140`
- `0x140001714`

## pseudocode

```c
__int64 wmainCRTStartup()
{
  _security_init_cookie();
  return _wmainCRTStartup();
}

```

## disassembly

```asm
0x1400012f0  sub     rsp, 28h
0x1400012f4  call    __security_init_cookie
0x1400012f9  add     rsp, 28h
0x1400012fd  jmp     __wmainCRTStartup
```
