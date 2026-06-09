# ATL::CComPtr<IPicture>::~CComPtr<IPicture>(void)

- ea: `0x18000344c`
- end: `0x180003451`
- name: `??1?$CComPtr@UIPicture@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002dd8a`
- `0x18002dd9c`
- `0x18002ddae`
- `0x18002e1e1`
- `0x18002e33d`
- `0x18002e577`
- `0x18002e5dd`
- `0x18002e63b`
- `0x18002e87d`
- `0x18002f178`
- `0x18002f19c`

## callees

- `0x180003458`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IPicture>::~CComPtr<IPicture>(__int64 *a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x18000344c  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
