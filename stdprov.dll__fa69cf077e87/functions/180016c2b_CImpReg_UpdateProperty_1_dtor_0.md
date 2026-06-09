# _CImpReg::UpdateProperty_::_1_::dtor$0

- ea: `0x180016c2b`
- end: `0x180016c37`
- name: `_CImpReg::UpdateProperty_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800092b0`

## pseudocode

```c
void __fastcall CImpReg::UpdateProperty_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TString::~TString((TString *)(a2 + 96));
}

```

## disassembly

```asm
0x180016c2b  lea     rcx, [rdx+60h]; this
0x180016c32  jmp     ??1TString@@QEAA@XZ; TString::~TString(void)
```
