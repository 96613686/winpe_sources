# std::unique_ptr<ImagingHandler,std::default_delete<ImagingHandler>>::~unique_ptr<ImagingHandler,std::default_delete<ImagingHandler>>(void)

- ea: `0x18000ff64`
- end: `0x18000ffc9`
- name: `??1?$unique_ptr@VImagingHandler@@U?$default_delete@VImagingHandler@@@std@@@std@@QEAA@XZ`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001026c`
- `0x180014030`

## callees

- `0x1800022a4`
- `0x1800041b8`
- `0x18000ff64`
- `0x180018f38`

## pseudocode

```c
void __fastcall std::unique_ptr<ImagingHandler>::~unique_ptr<ImagingHandler>(__int64 **a1)
{
  __int64 *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::wstring::~wstring(v1 + 6);
    if ( v1[3] )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v1 + 3);
    if ( v1[2] )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v1 + 2);
    if ( v1[1] )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v1 + 1);
    if ( *v1 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000ff64  push    rbx
0x18000ff66  sub     rsp, 20h
0x18000ff6a  mov     rbx, [rcx]
0x18000ff6d  test    rbx, rbx
0x18000ff70  jz      short loc_18000FFC3
0x18000ff72  lea     rcx, [rbx+30h]
0x18000ff76  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff7b  lea     rcx, [rbx+18h]
0x18000ff7f  cmp     qword ptr [rcx], 0
0x18000ff83  jz      short loc_18000FF8A
0x18000ff85  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000ff8a  lea     rcx, [rbx+10h]
0x18000ff8e  cmp     qword ptr [rcx], 0
0x18000ff92  jz      short loc_18000FF99
0x18000ff94  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000ff99  lea     rcx, [rbx+8]
0x18000ff9d  cmp     qword ptr [rcx], 0
0x18000ffa1  jz      short loc_18000FFA8
0x18000ffa3  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000ffa8  cmp     qword ptr [rbx], 0
0x18000ffac  jz      short loc_18000FFB6
0x18000ffae  mov     rcx, rbx
0x18000ffb1  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000ffb6  mov     edx, 50h ; 'P'
0x18000ffbb  mov     rcx, rbx; Block
0x18000ffbe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ffc3  add     rsp, 20h
0x18000ffc7  pop     rbx
0x18000ffc8  retn
```
