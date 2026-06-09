# _CTextNormMultiResult::ComputeTopResults_::_1_::dtor$0

- ea: `0x18000aa9e`
- end: `0x18000aaaa`
- name: `_CTextNormMultiResult::ComputeTopResults_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004cfc`

## pseudocode

```c
void __fastcall CTextNormMultiResult::ComputeTopResults_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(a2 + 88);
}

```

## disassembly

```asm
0x18000aa9e  lea     rcx, [rdx+58h]
0x18000aaa5  jmp     ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
```
