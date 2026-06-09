# _CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor$2

- ea: `0x18001a745`
- end: `0x18001a751`
- name: `_CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000fc20`

## pseudocode

```c
__int64 __fastcall CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return winrt::com_ptr<IWICBitmapClipper>::~com_ptr<IWICBitmapClipper>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18001a745  lea     rcx, [rdx+80h]
0x18001a74c  jmp     ??1?$com_ptr@UIWICBitmapClipper@@@winrt@@QEAA@XZ; winrt::com_ptr<IWICBitmapClipper>::~com_ptr<IWICBitmapClipper>(void)
```
