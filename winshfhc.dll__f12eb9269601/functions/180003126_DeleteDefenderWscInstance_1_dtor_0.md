# _DeleteDefenderWscInstance_::_1_::dtor$0

- ea: `0x180003126`
- end: `0x180003132`
- name: `_DeleteDefenderWscInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001ae4`

## pseudocode

```c
__int64 __fastcall DeleteDefenderWscInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IWbemLocator>::~CComPtr<IWbemLocator>((__int64 *)(a2 + 208));
}

```

## disassembly

```asm
0x180003126  lea     rcx, [rdx+0D0h]
0x18000312d  jmp     ??1?$CComPtr@UIWbemLocator@@@ATL@@QEAA@XZ; ATL::CComPtr<IWbemLocator>::~CComPtr<IWbemLocator>(void)
```
