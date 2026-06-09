# ATL::CRegKey::~CRegKey(void)

- ea: `0x1800058ec`
- end: `0x1800058f1`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073c8`
- `0x1800078ec`
- `0x180007e9f`
- `0x180007eab`

## callees

- `0x180006ad4`

## pseudocode

```c
// attributes: thunk
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
{
  ATL::CRegKey::Close(this);
}

```

## disassembly

```asm
0x1800058ec  jmp     ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
```
