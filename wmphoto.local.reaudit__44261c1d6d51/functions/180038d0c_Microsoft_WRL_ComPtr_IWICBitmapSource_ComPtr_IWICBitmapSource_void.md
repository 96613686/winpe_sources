# Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(void)

- ea: `0x180038d0c`
- end: `0x180038d11`
- name: `??1?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180044280`
- `0x1800442a0`
- `0x1800442c0`
- `0x1800442e0`
- `0x180044320`
- `0x180044340`
- `0x1800443c0`
- `0x1800443e0`

## callees

- `0x180035a50`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180038d0c  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
