# ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(void)

- ea: `0x180003768`
- end: `0x18000376d`
- name: `??1?$CComPtr@UICatRegister@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004099`
- `0x180005270`
- `0x180005618`
- `0x180006598`

## callees

- `0x180003774`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<ICatRegister>::~CComPtr<ICatRegister>(__int64 *a1)
{
  return ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(a1);
}

```

## disassembly

```asm
0x180003768  jmp     ??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)
```
