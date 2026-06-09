# winrt::Windows::Internal::Shell::implementation::TabProxyWindow::GetIconFromGlyphForSize(tagSIZE)

- ea: `0x180065ccc`
- end: `0x180065fd2`
- name: `?GetIconFromGlyphForSize@TabProxyWindow@implementation@Shell@Internal@Windows@winrt@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@UtagSIZE@@@Z`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1805a1180`

## callees

- `0x180065ccc`
- `0x180066030`
- `0x18006609c`
- `0x180066428`
- `0x180066488`
- `0x1800664e8`
- `0x1800665d0`
- `0x1801e92f0`
- `0x1802dd850`
- `0x180356360`
- `0x180356edc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065ed4`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180065e10`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180065e10`
- `GDI32!DeleteObject` at `0x180065f4b`
- `GDI32!DeleteObject` at `0x180065f5f`
- `GDI32!DeleteObject` at `0x180065f4b`
- `GDI32!DeleteObject` at `0x180065f5f`
- `GDI32!CreateDIBSection` at `0x180065e84`
- `GDI32!CreateDIBSection` at `0x180065e84`
- `GDI32!CreateCompatibleDC` at `0x180065e29`
- `GDI32!CreateCompatibleDC` at `0x180065e29`
- `GDI32!SelectObject` at `0x180065eec`
- `GDI32!SelectObject` at `0x180065fc6`
- `GDI32!SelectObject` at `0x180065eec`
- `GDI32!SelectObject` at `0x180065fc6`
- `GDI32!DeleteDC` at `0x180065f55`
- `GDI32!DeleteDC` at `0x180065f55`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
WCHAR *__fastcall winrt::Windows::Internal::Shell::implementation::TabProxyWindow::GetIconFromGlyphForSize(
        __int64 a1,
        WCHAR *a2,
        unsigned __int64 a3)
{
  LONG v3; // r14d
  unsigned __int64 v5; // rdi
  __int64 v6; // rbx
  winrt::impl **v7; // rax
  struct winrt::impl::hstring_header *v8; // rdx
  HSTRING v9; // r15
  winrt::impl **v10; // rax
  struct winrt::impl::hstring_header *v11; // rdx
  HSTRING v12; // r12
  LONG v13; // esi
  __int64 v14; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  WCHAR *lfFaceName; // rdx
  WCHAR v18; // cx
  WCHAR *v19; // rcx
  HFONT v20; // rdi
  HDC CompatibleDC; // rbx
  HBITMAP v22; // rsi
  unsigned __int16 v23; // r9
  winrt::Windows::Internal::Shell::implementation::TabProxyWindow *v24; // rcx
  const struct Geometry::CRect *offset; // [rsp+28h] [rbp-D8h]
  HDC v27; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 v28; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 length; // [rsp+3Ch] [rbp-C4h] BYREF
  HSTRING v30; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-B8h] BYREF
  HFONT v32; // [rsp+50h] [rbp-B0h] BYREF
  HBITMAP v33; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR v34; // [rsp+60h] [rbp-A0h]
  unsigned int v35[2]; // [rsp+68h] [rbp-98h] BYREF
  LONG v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+74h] [rbp-8Ch]
  void *ppvBits; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v39; // [rsp+88h] [rbp-78h]
  HGDIOBJ h; // [rsp+90h] [rbp-70h]
  HDC v41; // [rsp+98h] [rbp-68h]
  BITMAPINFO pbmi; // [rsp+A0h] [rbp-60h] BYREF
  LOGFONTW lf; // [rsp+D0h] [rbp-30h] BYREF

  v3 = a3;
  v34 = a2;
  v5 = HIDWORD(a3);
  v39 = HIDWORD(a3);
  v30 = 0;
  v31 = 0;
  v6 = a1 + 48;
  v7 = (winrt::impl **)winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FamilyName(
                         a1 + 48,
                         &v27);
  v9 = (HSTRING)winrt::impl::duplicate_hstring(*v7, v8);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
  v30 = v9;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
  v10 = (winrt::impl **)winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Query(
                          v6,
                          &v27);
  v12 = (HSTRING)winrt::impl::duplicate_hstring(*v10, v11);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
  v31 = v12;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
  memset_0(&lf, 0, sizeof(lf));
  v13 = -(int)v5;
  lf.lfHeight = -(int)v5;
  lf.lfWeight = 400;
  lf.lfCharSet = 0;
  lf.lfQuality = 5;
  length = 0;
  v14 = 2147483646;
  StringRawBuffer = WindowsGetStringRawBuffer(v12, &length);
  v16 = 32;
  lfFaceName = lf.lfFaceName;
  do
  {
    if ( !v14 )
      break;
    v18 = *StringRawBuffer;
    if ( !*StringRawBuffer )
      break;
    ++StringRawBuffer;
    *lfFaceName++ = v18;
    --v14;
    --v16;
  }
  while ( v16 );
  v19 = lfFaceName - 1;
  if ( v16 )
    v19 = lfFaceName;
  *v19 = 0;
  v20 = CreateFontIndirectW(&lf);
  v32 = v20;
  if ( !v20 )
  {
    *(_QWORD *)a2 = 0;
    goto LABEL_11;
  }
  CompatibleDC = CreateCompatibleDC(0);
  v27 = CompatibleDC;
  if ( CompatibleDC )
  {
    pbmi.bmiHeader.biSize = 44;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biWidth = v3;
    pbmi.bmiHeader.biHeight = v13;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    ppvBits = 0;
    v22 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
    v33 = v22;
    if ( v22 )
    {
      v28 = 0;
      v34 = WindowsGetStringRawBuffer(v9, &v28);
      if ( v28 == 1 )
      {
        h = SelectObject(CompatibleDC, v22);
        v41 = CompatibleDC;
        *(_QWORD *)v35 = 0;
        v36 = v3;
        v37 = v39;
        GDIHelpers::RenderTransparentCenteredGlyph(CompatibleDC, (HDC)v20, (HFONT)*v34, v23, (unsigned int)v35, offset);
        if ( h )
          SelectObject(CompatibleDC, h);
        *(_QWORD *)a2 = winrt::Windows::Internal::Shell::implementation::TabProxyWindow::GetIconFromBitmap(v24, v22);
        DeleteObject(v22);
        DeleteDC(CompatibleDC);
        goto LABEL_16;
      }
    }
    *(_QWORD *)a2 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(&v33);
    wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(&v27);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(&v32);
    goto LABEL_17;
  }
  *(_QWORD *)a2 = 0;
LABEL_16:
  DeleteObject(v20);
LABEL_17:
  if ( v12 )
    WindowsDeleteString(v12);
  if ( v9 )
    WindowsDeleteString(v9);
  return a2;
}

```

## disassembly

```asm
0x180065ccc  mov     [rsp-8+arg_18], rbx
0x180065cd1  push    rbp
0x180065cd2  push    rsi
0x180065cd3  push    rdi
0x180065cd4  push    r12
0x180065cd6  push    r13
0x180065cd8  push    r14
0x180065cda  push    r15
0x180065cdc  lea     rbp, [rsp-40h]
0x180065ce1  sub     rsp, 140h
0x180065ce8  mov     rax, cs:__security_cookie
0x180065cef  xor     rax, rsp
0x180065cf2  mov     [rbp+70h+var_40], rax
0x180065cf6  mov     r14, r8
0x180065cf9  mov     r13, rdx
0x180065cfc  mov     [rsp+170h+var_110], rdx
0x180065d01  mov     rdi, r8
0x180065d04  shr     rdi, 20h
0x180065d08  mov     [rbp+70h+var_E8], rdi
0x180065d0c  xor     eax, eax
0x180065d0e  mov     [rsp+170h+var_130], rax
0x180065d13  mov     [rsp+170h+var_128], rax
0x180065d18  lea     rbx, [rcx+30h]
0x180065d1c  lea     rdx, [rsp+170h+var_140]
0x180065d21  mov     rcx, rbx
0x180065d24  call    ?FamilyName@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FamilyName(void)
0x180065d29  nop
0x180065d2a  mov     rcx, [rax]; this
0x180065d2d  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180065d32  mov     r15, rax
0x180065d35  lea     rcx, [rsp+170h+var_130]
0x180065d3a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d3f  lea     rcx, [rsp+170h+var_130]
0x180065d44  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d49  mov     [rsp+170h+var_130], r15
0x180065d4e  lea     rcx, [rsp+170h+var_140]
0x180065d53  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d58  lea     rdx, [rsp+170h+var_140]
0x180065d5d  mov     rcx, rbx
0x180065d60  call    ?Query@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Query(void)
0x180065d65  nop
0x180065d66  mov     rcx, [rax]; this
0x180065d69  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180065d6e  mov     r12, rax
0x180065d71  lea     rcx, [rsp+170h+var_128]
0x180065d76  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d7b  lea     rcx, [rsp+170h+var_128]
0x180065d80  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d85  mov     [rsp+170h+var_128], r12
0x180065d8a  lea     rcx, [rsp+170h+var_140]
0x180065d8f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180065d94  xor     edx, edx; Val
0x180065d96  lea     r8d, [rdx+5Ch]; Size
0x180065d9a  lea     rcx, [rbp+70h+lf]; void *
0x180065d9e  call    memset_0
0x180065da3  mov     esi, edi
0x180065da5  neg     esi
0x180065da7  mov     [rbp+70h+lf.lfHeight], esi
0x180065daa  mov     [rbp+70h+lf.lfWeight], 190h
0x180065db1  xor     edi, edi
0x180065db3  mov     [rbp+70h+lf.lfCharSet], dil
0x180065db7  mov     [rbp+70h+lf.lfQuality], 5
0x180065dbb  mov     [rsp+170h+length], edi
0x180065dbf  mov     ebx, 7FFFFFFEh
0x180065dc4  lea     rdx, [rsp+170h+length]; length
0x180065dc9  mov     rcx, r12; string
0x180065dcc  call    cs:__imp_WindowsGetStringRawBuffer
0x180065dd2  lea     r8d, [rdi+20h]
0x180065dd6  lea     rdx, [rbp+70h+lf.lfFaceName]
0x180065dda  lea     r9d, [rdi+1]
0x180065dde  test    rbx, rbx
0x180065de1  jz      short loc_180065DFE
0x180065de3  movzx   ecx, word ptr [rax]
0x180065de6  test    cx, cx
0x180065de9  jz      short loc_180065DFE
0x180065deb  add     rax, 2
0x180065def  mov     [rdx], cx
0x180065df2  add     rdx, 2
0x180065df6  sub     rbx, r9
0x180065df9  sub     r8, r9
0x180065dfc  jnz     short loc_180065DDE
0x180065dfe  lea     rcx, [rdx-2]
0x180065e02  test    r8, r8
0x180065e05  cmovnz  rcx, rdx
0x180065e09  mov     [rcx], di
0x180065e0c  lea     rcx, [rbp+70h+lf]; lplf
0x180065e10  call    cs:__imp_CreateFontIndirectW
0x180065e16  mov     rdi, rax
0x180065e19  mov     [rsp+170h+var_120], rax
0x180065e1e  test    rax, rax
0x180065e21  jz      loc_180065FB6
0x180065e27  xor     ecx, ecx; hdc
0x180065e29  call    cs:__imp_CreateCompatibleDC
0x180065e2f  mov     rbx, rax
0x180065e32  mov     [rsp+170h+var_140], rax
0x180065e37  xor     ecx, ecx
0x180065e39  test    rax, rax
0x180065e3c  jz      loc_180065F9A
0x180065e42  mov     [rbp+70h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x180065e49  xorps   xmm0, xmm0
0x180065e4c  xor     eax, eax
0x180065e4e  movups  xmmword ptr [rbp+70h+pbmi.bmiHeader.biWidth], xmm0
0x180065e52  movups  xmmword ptr [rbp+70h+pbmi.bmiHeader.biSizeImage], xmm0
0x180065e56  mov     qword ptr [rbp+70h+pbmi.bmiHeader.biClrImportant], rax
0x180065e5a  mov     [rbp+70h+pbmi.bmiHeader.biWidth], r14d
0x180065e5e  mov     [rbp+70h+pbmi.bmiHeader.biHeight], esi
0x180065e61  mov     qword ptr [rbp+70h+pbmi.bmiHeader.biPlanes], 200001h
0x180065e69  mov     [rbp+70h+ppvBits], rcx
0x180065e6d  mov     dword ptr [rsp+170h+offset], ecx; struct Geometry::CRect *
0x180065e71  mov     [rsp+170h+hSection], rcx; hSection
0x180065e76  lea     r9, [rbp+70h+ppvBits]; ppvBits
0x180065e7a  xor     r8d, r8d; usage
0x180065e7d  lea     rdx, [rbp+70h+pbmi]; pbmi
0x180065e81  mov     rcx, rbx; hdc
0x180065e84  call    cs:__imp_CreateDIBSection
0x180065e8a  mov     rsi, rax
0x180065e8d  mov     [rsp+170h+var_118], rax
0x180065e92  test    rax, rax
0x180065e95  jnz     short loc_180065EC4
0x180065e97  mov     qword ptr [r13+0], 0
0x180065e9f  lea     rcx, [rsp+170h+var_118]
0x180065ea4  call    ??1?$unique_storage@U?$resource_policy@PEAUHFONT__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(void)
0x180065ea9  nop
0x180065eaa  lea     rcx, [rsp+170h+var_140]
0x180065eaf  call    ??1?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(void)
0x180065eb4  nop
0x180065eb5  lea     rcx, [rsp+170h+var_120]
0x180065eba  call    ??1?$unique_storage@U?$resource_policy@PEAUHFONT__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(void)
0x180065ebf  jmp     loc_180065F66
0x180065ec4  mov     [rsp+170h+var_138], 0
0x180065ecc  lea     rdx, [rsp+170h+var_138]; length
0x180065ed1  mov     rcx, r15; string
0x180065ed4  call    cs:__imp_WindowsGetStringRawBuffer
0x180065eda  mov     [rsp+170h+var_110], rax
0x180065edf  cmp     [rsp+170h+var_138], 1
0x180065ee4  jnz     short loc_180065E97
0x180065ee6  mov     rdx, rsi; h
0x180065ee9  mov     rcx, rbx; hdc
0x180065eec  call    cs:__imp_SelectObject
0x180065ef2  mov     [rbp+70h+h], rax
0x180065ef6  mov     [rbp+70h+var_D8], rbx
0x180065efa  mov     qword ptr [rsp+170h+var_108], 0
0x180065f03  mov     [rsp+170h+var_100], r14d
0x180065f08  mov     rax, [rbp+70h+var_E8]
0x180065f0c  mov     [rsp+170h+var_FC], eax
0x180065f10  lea     rax, [rsp+170h+var_108]
0x180065f15  mov     [rsp+170h+hSection], rax; unsigned int
0x180065f1a  mov     r8, [rsp+170h+var_110]
0x180065f1f  movzx   r8d, word ptr [r8]; HFONT
0x180065f23  mov     rdx, rdi; HDC
0x180065f26  mov     rcx, rbx; hdc
0x180065f29  call    ?RenderTransparentCenteredGlyph@GDIHelpers@@YAXPEAUHDC__@@PEAUHFONT__@@GKAEBUCRect@Geometry@@@Z; GDIHelpers::RenderTransparentCenteredGlyph(HDC__ *,HFONT__ *,ushort,ulong,Geometry::CRect const &)
0x180065f2e  nop
0x180065f2f  mov     rdx, [rbp+70h+h]; h
0x180065f33  test    rdx, rdx
0x180065f36  jnz     loc_180065FC3
0x180065f3c  mov     rdx, rsi; HBITMAP
0x180065f3f  call    ?GetIconFromBitmap@TabProxyWindow@implementation@Shell@Internal@Windows@winrt@@AEAAPEAUHICON__@@PEAUHBITMAP__@@@Z; winrt::Windows::Internal::Shell::implementation::TabProxyWindow::GetIconFromBitmap(HBITMAP__ *)
0x180065f44  mov     [r13+0], rax
0x180065f48  mov     rcx, rsi; ho
0x180065f4b  call    cs:__imp_DeleteObject
0x180065f51  nop
0x180065f52  mov     rcx, rbx; hdc
0x180065f55  call    cs:__imp_DeleteDC
0x180065f5b  nop
0x180065f5c  mov     rcx, rdi; ho
0x180065f5f  call    cs:__imp_DeleteObject
0x180065f65  nop
0x180065f66  test    r12, r12
0x180065f69  jnz     short loc_180065FA0
0x180065f6b  test    r15, r15
0x180065f6e  jnz     short loc_180065FAB
0x180065f70  mov     rax, r13
0x180065f73  mov     rcx, [rbp+70h+var_40]
0x180065f77  xor     rcx, rsp; StackCookie
0x180065f7a  call    __security_check_cookie
0x180065f7f  mov     rbx, [rsp+170h+arg_18]
0x180065f87  add     rsp, 140h
0x180065f8e  pop     r15
0x180065f90  pop     r14
0x180065f92  pop     r13
0x180065f94  pop     r12
0x180065f96  pop     rdi
0x180065f97  pop     rsi
0x180065f98  pop     rbp
0x180065f99  retn
0x180065f9a  mov     [r13+0], rcx
0x180065f9e  jmp     short loc_180065F5C
0x180065fa0  mov     rcx, r12; string
0x180065fa3  call    cs:__imp_WindowsDeleteString
0x180065fa9  jmp     short loc_180065F6B
0x180065fab  mov     rcx, r15; string
0x180065fae  call    cs:__imp_WindowsDeleteString
0x180065fb4  jmp     short loc_180065F70
0x180065fb6  mov     qword ptr [r13+0], 0
0x180065fbe  jmp     loc_180065EB5
0x180065fc3  mov     rcx, rbx; hdc
0x180065fc6  call    cs:__imp_SelectObject
0x180065fcc  jmp     loc_180065F3C
```
