# _HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor$0

- ea: `0x180044340`
- end: `0x18004434c`
- name: `_HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180038d0c`

## pseudocode

```c
__int64 __fastcall HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(a2 + 96);
}

```

## disassembly

```asm
0x180044340  lea     rcx, [rdx+60h]
0x180044347  jmp     ??1?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(void)
```
