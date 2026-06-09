# _HARDWARE_ID_INFO::~_HARDWARE_ID_INFO(void)

- ea: `0x180003c88`
- end: `0x180003cb0`
- name: `??1_HARDWARE_ID_INFO@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(_HARDWARE_ID_INFO *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dc4`
- `0x1800045d0`
- `0x1800053e4`
- `0x1800090d4`
- `0x1800100b2`
- `0x18001011e`
- `0x180010130`
- `0x1800101ae`
- `0x180010689`

## callees

- `0x180003fec`

## pseudocode

```c
void __fastcall _HARDWARE_ID_INFO::~_HARDWARE_ID_INFO(_HARDWARE_ID_INFO *this)
{
  _bstr_t::_Free((_HARDWARE_ID_INFO *)((char *)this + 16));
  _bstr_t::_Free((_HARDWARE_ID_INFO *)((char *)this + 8));
  _bstr_t::_Free(this);
}

```

## disassembly

```asm
0x180003c88  push    rbx
0x180003c8a  sub     rsp, 20h
0x180003c8e  mov     rbx, rcx
0x180003c91  add     rcx, 10h; this
0x180003c95  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180003c9a  lea     rcx, [rbx+8]; this
0x180003c9e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180003ca3  mov     rcx, rbx; this
0x180003ca6  add     rsp, 20h
0x180003caa  pop     rbx
0x180003cab  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
