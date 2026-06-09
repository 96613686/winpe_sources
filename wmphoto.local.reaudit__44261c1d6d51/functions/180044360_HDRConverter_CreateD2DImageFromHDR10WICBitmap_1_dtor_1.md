# _HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor$1

- ea: `0x180044360`
- end: `0x18004436c`
- name: `_HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003bfa0`

## pseudocode

```c
_QWORD *__fastcall HDRConverter::CreateD2DImageFromHDR10WICBitmap_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<ID2D1ImageSource>::~ComPtr<ID2D1ImageSource>((_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x180044360  lea     rcx, [rdx+50h]
0x180044367  jmp     ??1?$ComPtr@UID2D1ImageSource@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ID2D1ImageSource>::~ComPtr<ID2D1ImageSource>(void)
```
