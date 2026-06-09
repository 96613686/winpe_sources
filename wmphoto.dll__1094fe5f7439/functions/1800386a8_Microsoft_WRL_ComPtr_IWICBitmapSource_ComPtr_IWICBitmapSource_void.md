# Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(void)

- ea: `0x1800386a8`
- end: `0x1800386ad`
- name: `??1?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180043a70`
- `0x180043a90`
- `0x180043ab0`
- `0x180043ad0`
- `0x180043b10`
- `0x180043b30`
- `0x180043bb0`
- `0x180043bd0`

## callees

- `0x180035480`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800386a8  jmp     ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
```
