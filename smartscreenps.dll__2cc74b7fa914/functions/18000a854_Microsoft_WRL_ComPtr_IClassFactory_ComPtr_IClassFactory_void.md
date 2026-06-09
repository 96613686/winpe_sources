# Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)

- ea: `0x18000a854`
- end: `0x18000a859`
- name: `??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cef3`
- `0x18000cf17`
- `0x18000cf29`
- `0x18000cfbf`

## callees

- `0x18000871c`

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
0x18000a854  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
