# ATL::CComPtr<IFunctionDiscoveryNotification>::~CComPtr<IFunctionDiscoveryNotification>(void)

- ea: `0x1800054bc`
- end: `0x1800054c1`
- name: `??1?$CComPtr@UIFunctionDiscoveryNotification@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010806`
- `0x180010ae3`
- `0x180010af5`
- `0x180010d91`
- `0x180010da7`
- `0x180010dbd`
- `0x180010ea5`

## callees

- `0x180003728`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IFunctionDiscoveryNotification>::~CComPtr<IFunctionDiscoveryNotification>(__int64 a1)
{
  return ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(a1);
}

```

## disassembly

```asm
0x1800054bc  jmp     ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
```
