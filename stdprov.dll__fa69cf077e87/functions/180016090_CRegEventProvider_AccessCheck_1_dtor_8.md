# _CRegEventProvider::AccessCheck_::_1_::dtor$8

- ea: `0x180016090`
- end: `0x18001609c`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$8`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180009da0`

## pseudocode

```c
int __fastcall CRegEventProvider::AccessCheck_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>((void **)(a2 + 176));
}

```

## disassembly

```asm
0x180016090  lea     rcx, [rdx+0B0h]
0x180016097  jmp     ??1?$CVectorDeleteMe@E@@QEAA@XZ; CVectorDeleteMe<uchar>::~CVectorDeleteMe<uchar>(void)
```
