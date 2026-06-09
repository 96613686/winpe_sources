# _ATL::CRegKey::RecurseDeleteKey_::_1_::dtor$0

- ea: `0x1800050ff`
- end: `0x18000510b`
- name: `_ATL::CRegKey::RecurseDeleteKey_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001f0c`

## pseudocode

```c
void __fastcall ATL::CRegKey::RecurseDeleteKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((HKEY *)(a2 + 72));
}

```

## disassembly

```asm
0x1800050ff  lea     rcx, [rdx+48h]; this
0x180005106  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
