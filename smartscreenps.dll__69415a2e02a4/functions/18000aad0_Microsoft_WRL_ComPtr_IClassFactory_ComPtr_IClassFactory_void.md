# Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)

- ea: `0x18000aad0`
- end: `0x18000aad5`
- name: `??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d1d5`
- `0x18000d1f9`
- `0x18000d20b`
- `0x18000d2a3`

## callees

- `0x180008828`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18000aad0  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
