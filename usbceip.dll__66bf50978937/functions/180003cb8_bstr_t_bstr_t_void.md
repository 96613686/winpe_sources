# _bstr_t::~_bstr_t(void)

- ea: `0x180003cb8`
- end: `0x180003cbd`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x180010208`
- `0x18001021e`
- `0x18001028a`
- `0x1800102ae`
- `0x180010354`
- `0x1800103c0`
- `0x1800103e8`
- `0x1800103fe`
- `0x18001047c`
- `0x1800104c3`
- `0x1800104d5`
- `0x1800104e7`
- `0x1800104f9`
- `0x18001050b`
- `0x18001051d`
- `0x18001052f`
- `0x180010541`
- `0x180010588`
- `0x18001059e`
- `0x18001069b`
- `0x180010739`
- `0x1800107fe`
- `0x18001084a`
- `0x18001089e`
- `0x180010915`

## callees

- `0x180003fec`

## pseudocode

```c
// attributes: thunk
void __fastcall _bstr_t::~_bstr_t(_bstr_t *this)
{
  _bstr_t::_Free(this);
}

```

## disassembly

```asm
0x180003cb8  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
