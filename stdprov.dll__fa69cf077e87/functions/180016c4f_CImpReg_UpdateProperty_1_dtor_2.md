# _CImpReg::UpdateProperty_::_1_::dtor$2

- ea: `0x180016c4f`
- end: `0x180016c5b`
- name: `_CImpReg::UpdateProperty_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800091e0`

## pseudocode

```c
void __fastcall CImpReg::UpdateProperty_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CVariant::~CVariant((CVariant *)(a2 + 120));
}

```

## disassembly

```asm
0x180016c4f  lea     rcx, [rdx+78h]; this
0x180016c56  jmp     ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
```
