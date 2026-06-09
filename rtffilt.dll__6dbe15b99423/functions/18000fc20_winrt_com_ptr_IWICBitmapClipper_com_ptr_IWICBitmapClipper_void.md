# winrt::com_ptr<IWICBitmapClipper>::~com_ptr<IWICBitmapClipper>(void)

- ea: `0x18000fc20`
- end: `0x18000fc34`
- name: `??1?$com_ptr@UIWICBitmapClipper@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a649`
- `0x18001a6c7`
- `0x18001a6d9`
- `0x18001a745`
- `0x18001a78f`
- `0x18001a7a1`
- `0x18001a7b7`
- `0x18001a7cd`

## callees

- `0x18000fc20`
- `0x180018f38`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IWICBitmapClipper>::~com_ptr<IWICBitmapClipper>(__int64 *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000fc20  sub     rsp, 28h
0x18000fc24  cmp     qword ptr [rcx], 0
0x18000fc28  jz      short loc_18000FC2F
0x18000fc2a  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000fc2f  add     rsp, 28h
0x18000fc33  retn
```
