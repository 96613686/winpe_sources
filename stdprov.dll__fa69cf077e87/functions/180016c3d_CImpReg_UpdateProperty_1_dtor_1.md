# _CImpReg::UpdateProperty_::_1_::dtor$1

- ea: `0x180016c3d`
- end: `0x180016c49`
- name: `_CImpReg::UpdateProperty_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002e90`

## pseudocode

```c
void __fastcall CImpReg::UpdateProperty_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CProvObj::~CProvObj((CProvObj *)(a2 + 160));
}

```

## disassembly

```asm
0x180016c3d  lea     rcx, [rdx+0A0h]; this
0x180016c44  jmp     ??1CProvObj@@UEAA@XZ; CProvObj::~CProvObj(void)
```
