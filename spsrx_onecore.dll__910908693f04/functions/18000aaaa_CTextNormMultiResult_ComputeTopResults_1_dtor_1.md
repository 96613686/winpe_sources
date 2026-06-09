# _CTextNormMultiResult::ComputeTopResults_::_1_::dtor$1

- ea: `0x18000aaaa`
- end: `0x18000aab6`
- name: `_CTextNormMultiResult::ComputeTopResults_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004cfc`

## pseudocode

```c
void __fastcall CTextNormMultiResult::ComputeTopResults_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(a2 + 144);
}

```

## disassembly

```asm
0x18000aaaa  lea     rcx, [rdx+90h]
0x18000aab1  jmp     ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
```
