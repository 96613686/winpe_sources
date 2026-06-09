# _HDRConverter::CreateD2DBitmaps_::_1_::dtor$2

- ea: `0x180043b10`
- end: `0x180043b1c`
- name: `_HDRConverter::CreateD2DBitmaps_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800386a8`

## pseudocode

```c
__int64 __fastcall HDRConverter::CreateD2DBitmaps_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(a2 + 248);
}

```

## disassembly

```asm
0x180043b10  lea     rcx, [rdx+0F8h]
0x180043b17  jmp     ??1?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::~ComPtr<IWICBitmapSource>(void)
```
