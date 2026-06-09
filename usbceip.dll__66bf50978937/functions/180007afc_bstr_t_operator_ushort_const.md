# _bstr_t::operator=(ushort const *)

- ea: `0x180007afc`
- end: `0x180007b3d`
- name: `??4_bstr_t@@QEAAAEAV0@PEBG@Z`
- size: `65`
- prototype: `_bstr_t *__fastcall(_bstr_t *, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b44`
- `0x180009c50`
- `0x180009d50`
- `0x18000ae48`
- `0x18000aeac`
- `0x18000af94`
- `0x18000b140`
- `0x18000be14`
- `0x18000bebc`

## callees

- `0x18000246c`
- `0x180003fec`
- `0x180007a54`

## pseudocode

```c
_bstr_t *__fastcall _bstr_t::operator=(_bstr_t *a1, const unsigned __int16 *a2)
{
  _bstr_t::Data_t *v5; // [rsp+30h] [rbp+8h]

  _bstr_t::_Free(a1);
  v5 = (_bstr_t::Data_t *)operator new(0x18u);
  *(_QWORD *)a1 = _bstr_t::Data_t::Data_t(v5, a2);
  return a1;
}

```

## disassembly

```asm
0x180007afc  mov     [rsp+arg_8], rbx
0x180007b01  push    rdi
0x180007b02  sub     rsp, 20h
0x180007b06  mov     rbx, rdx
0x180007b09  mov     rdi, rcx
0x180007b0c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180007b11  mov     ecx, 18h; Size
0x180007b16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b1b  mov     [rsp+28h+arg_0], rax
0x180007b20  mov     rdx, rbx; unsigned __int16 *
0x180007b23  mov     rcx, rax; this
0x180007b26  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x180007b2b  nop
0x180007b2c  mov     [rdi], rax
0x180007b2f  mov     rax, rdi
0x180007b32  mov     rbx, [rsp+28h+arg_8]
0x180007b37  add     rsp, 20h
0x180007b3b  pop     rdi
0x180007b3c  retn
```
