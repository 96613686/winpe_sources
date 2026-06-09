# CModernTarget::Launch(CallerInformation const &,Windows::System::Internal::Launch::InternalLauncherOptions,Windows::System::ILauncherUIOptions *,HSTRING__ *)

- ea: `0x180073dc0`
- end: `0x180074167`
- name: `?Launch@CModernTarget@@UEAAJAEBVCallerInformation@@W4InternalLauncherOptions@0Internal@System@Windows@@PEAUILauncherUIOptions@56@PEAUHSTRING__@@@Z`
- size: `935`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800243a4`
- `0x1800247c4`
- `0x18002cec0`
- `0x180041eb4`
- `0x180073dc0`
- `0x180074170`
- `0x18008a030`
- `0x18008a9d8`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180073ea2`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180073ea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180073e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180073e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800740c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007404a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007411e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007404a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007411e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074135`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CModernTarget::Launch(
        __int64 a1,
        const struct CallerInformation *a2,
        __int16 a3,
        __int64 a4,
        HSTRING a5)
{
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  HSTRING v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LauncherMiscHelpers **); // rbx
  int v15; // eax
  struct Windows::Foundation::Collections::IPropertySet **v16; // r8
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD); // rbx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  void (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // esi
  PCWSTR v26; // rbx
  __int64 v27; // rdi
  unsigned __int16 *v28; // rax
  int v30; // [rsp+20h] [rbp-318h]
  HSTRING v31; // [rsp+60h] [rbp-2D8h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-2D0h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-2C8h] BYREF
  LauncherMiscHelpers *v34; // [rsp+78h] [rbp-2C0h] BYREF
  HSTRING string; // [rsp+80h] [rbp-2B8h] BYREF
  __int64 v36; // [rsp+88h] [rbp-2B0h] BYREF
  __int64 v37; // [rsp+90h] [rbp-2A8h] BYREF
  HSTRING v38; // [rsp+98h] [rbp-2A0h]
  _DWORD v39[2]; // [rsp+A0h] [rbp-298h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-290h]
  __int64 v41; // [rsp+B0h] [rbp-288h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-280h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-268h]
  WCHAR pszOutBuf[264]; // [rsp+E0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v38 = a5;
  v39[1] = 0;
  v39[0] = *(_DWORD *)(a1 + 36);
  v40 = *(_QWORD *)(a1 + 40);
  v41 = *(_QWORD *)(a1 + 48);
  string = 0;
  memset_0(pszOutBuf, 0, 0x208u);
  v9 = *(_QWORD *)(a1 + 80);
  if ( v9 )
  {
    v10 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 72LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v10(v9, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x104u, 0);
    }
  }
  v12 = 0;
  v31 = 0;
  v13 = *(_QWORD *)(a1 + 80);
  if ( v13 )
  {
    v34 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, LauncherMiscHelpers **))(*(_QWORD *)v13 + 168LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v15 = v14(v13, &v34);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\TargetAppResolver.h",
        (const char *)(unsigned int)v15,
        v30);
    v33 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v17 = LauncherMiscHelpers::DeserializePropertySet(v34, (struct Windows::Storage::Streams::IBuffer *)&v33, v16);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\TargetAppResolver.h",
        (const char *)(unsigned int)v17,
        v30);
    v37 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v33,
            (__int64)&v37);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\TargetAppResolver.h",
        (const char *)(unsigned int)v18,
        v30);
    v32 = 0;
    v19 = v37;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v37 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v43 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PackageId", 0xAu, 9u);
    v21 = v20(v19, v43, &v32);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\TargetAppResolver.h",
        (const char *)(unsigned int)v21,
        v30);
    v36 = 0;
    v22 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<HSTRING__ *>>(&v32, (__int64)&v36);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\inc\\TargetAppResolver.h",
        (const char *)(unsigned int)v22,
        v30);
    v23 = v36;
    v24 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 48LL);
    WindowsDeleteString(v31);
    v31 = 0;
    v24(v23, &v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v12 = v31;
  }
  v25 = *(_DWORD *)(a1 + 96);
  v26 = WindowsGetStringRawBuffer(v12, 0);
  v27 = *(_QWORD *)(a1 + 64);
  v28 = (unsigned __int16 *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 72), 0);
  LaunchModernTargetApp(
    a2,
    *(const unsigned __int16 **)(a1 + 56),
    v28,
    pszOutBuf,
    a3,
    (int)v39,
    a4,
    v27,
    v38,
    (__int64)v26,
    v25,
    a1 + 88);
  WindowsDeleteString(v31);
  v31 = 0;
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180073dc0  mov     r11, rsp
0x180073dc3  push    rbx
0x180073dc4  push    rsi
0x180073dc5  push    rdi
0x180073dc6  push    r12
0x180073dc8  push    r13
0x180073dca  push    r14
0x180073dcc  push    r15
0x180073dce  sub     rsp, 300h
0x180073dd5  mov     rax, cs:__security_cookie
0x180073ddc  xor     rax, rsp
0x180073ddf  mov     [rsp+338h+var_48], rax
0x180073de7  mov     r13, r9
0x180073dea  mov     r15d, r8d
0x180073ded  mov     r12, rdx
0x180073df0  mov     r14, rcx
0x180073df3  mov     rax, [rsp+338h+arg_20]
0x180073dfb  mov     [rsp+338h+var_2A0], rax
0x180073e03  xor     esi, esi
0x180073e05  mov     [rsp+338h+var_294], esi
0x180073e0c  mov     eax, [rcx+24h]
0x180073e0f  mov     [rsp+338h+var_298], eax
0x180073e16  mov     rax, [rcx+28h]
0x180073e1a  mov     [r11-290h], rax
0x180073e21  mov     rax, [rcx+30h]
0x180073e25  mov     [r11-288h], rax
0x180073e2c  mov     [r11-2B8h], rsi
0x180073e33  xor     edx, edx; Val
0x180073e35  mov     r8d, 208h; Size
0x180073e3b  lea     rcx, [r11-258h]; void *
0x180073e42  call    memset_0
0x180073e47  mov     rdi, [r14+50h]
0x180073e4b  test    rdi, rdi
0x180073e4e  jz      short loc_180073EA8
0x180073e50  mov     rax, [rdi]
0x180073e53  mov     rbx, [rax+48h]
0x180073e57  xor     ecx, ecx; string
0x180073e59  call    cs:__imp_WindowsDeleteString
0x180073e5f  mov     [rsp+338h+string], rsi
0x180073e67  lea     rdx, [rsp+338h+string]
0x180073e6f  mov     rcx, rdi
0x180073e72  mov     rax, rbx
0x180073e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e7a  test    eax, eax
0x180073e7c  js      short loc_180073EA8
0x180073e7e  xor     edx, edx; length
0x180073e80  mov     rcx, [rsp+338h+string]; string
0x180073e88  call    cs:__imp_WindowsGetStringRawBuffer
0x180073e8e  xor     r9d, r9d; ppvReserved
0x180073e91  mov     r8d, 104h; cchOutBuf
0x180073e97  lea     rdx, [rsp+338h+pszOutBuf]; pszOutBuf
0x180073e9f  mov     rcx, rax; pszSource
0x180073ea2  call    cs:__imp_SHLoadIndirectString
0x180073ea8  mov     rcx, rsi
0x180073eab  mov     [rsp+338h+var_2D8], rcx
0x180073eb0  mov     rdi, [r14+50h]
0x180073eb4  test    rdi, rdi
0x180073eb7  jz      loc_1800740A7
0x180073ebd  mov     [rsp+338h+var_2C0], rsi
0x180073ec2  mov     rax, [rdi]
0x180073ec5  mov     rbx, [rax+0A8h]
0x180073ecc  lea     rcx, [rsp+338h+var_2C0]
0x180073ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073ed6  lea     rdx, [rsp+338h+var_2C0]
0x180073edb  mov     rcx, rdi
0x180073ede  mov     rax, rbx
0x180073ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ee6  mov     rcx, [rsp+338h]; this
0x180073eee  test    eax, eax
0x180073ef0  jns     short loc_180073F06
0x180073ef2  mov     r9d, eax; char *
0x180073ef5  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\windows.system.launc"...
0x180073efc  mov     edx, 8Dh; void *
0x180073f01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073f06  mov     [rsp+338h+var_2C8], rsi
0x180073f0b  lea     rcx, [rsp+338h+var_2C8]
0x180073f10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073f15  lea     rdx, [rsp+338h+var_2C8]; struct Windows::Storage::Streams::IBuffer *
0x180073f1a  mov     rcx, [rsp+338h+var_2C0]; this
0x180073f1f  call    ?DeserializePropertySet@LauncherMiscHelpers@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z; LauncherMiscHelpers::DeserializePropertySet(Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::IPropertySet * *)
0x180073f24  mov     rcx, [rsp+338h]; this
0x180073f2c  test    eax, eax
0x180073f2e  jns     short loc_180073F44
0x180073f30  mov     r9d, eax; char *
0x180073f33  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\windows.system.launc"...
0x180073f3a  mov     edx, 90h; void *
0x180073f3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073f44  mov     [rsp+338h+var_2A8], rsi
0x180073f4c  lea     rdx, [rsp+338h+var_2A8]
0x180073f54  lea     rcx, [rsp+338h+var_2C8]
0x180073f59  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180073f5e  mov     rcx, [rsp+338h]; this
0x180073f66  test    eax, eax
0x180073f68  jns     short loc_180073F7E
0x180073f6a  mov     r9d, eax; char *
0x180073f6d  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\windows.system.launc"...
0x180073f74  mov     edx, 93h; void *
0x180073f79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073f7e  mov     [rsp+338h+var_2D0], rsi
0x180073f83  mov     rdi, [rsp+338h+var_2A8]
0x180073f8b  mov     rax, [rdi]
0x180073f8e  mov     rbx, [rax+30h]
0x180073f92  lea     rcx, [rsp+338h+var_2D0]
0x180073f97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073f9c  mov     [rsp+338h+var_268], rsi
0x180073fa4  mov     r9d, 9; unsigned int
0x180073faa  lea     r8d, [r9+1]; unsigned int
0x180073fae  lea     rdx, aPackageid; "PackageId"
0x180073fb5  lea     rcx, [rsp+338h+hstringHeader]; hstringHeader
0x180073fbd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180073fc2  nop
0x180073fc3  lea     r8, [rsp+338h+var_2D0]
0x180073fc8  mov     rdx, [rsp+338h+var_268]
0x180073fd0  mov     rcx, rdi
0x180073fd3  mov     rax, rbx
0x180073fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fdb  mov     rcx, [rsp+338h]; this
0x180073fe3  test    eax, eax
0x180073fe5  jns     short loc_180073FFC
0x180073fe7  mov     r9d, eax; char *
0x180073fea  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\windows.system.launc"...
0x180073ff1  mov     edx, 96h; void *
0x180073ff6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073ffc  mov     [rsp+338h+var_2B0], rsi
0x180074004  lea     rdx, [rsp+338h+var_2B0]
0x18007400c  lea     rcx, [rsp+338h+var_2D0]
0x180074011  call    ??$As@U?$IReference@PEAUHSTRING__@@@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IReference@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IReference<HSTRING__ *>>>)
0x180074016  mov     rcx, [rsp+338h]; this
0x18007401e  test    eax, eax
0x180074020  jns     short loc_180074036
0x180074022  mov     r9d, eax; char *
0x180074025  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\windows.system.launc"...
0x18007402c  mov     edx, 99h; void *
0x180074031  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074036  mov     rdi, [rsp+338h+var_2B0]
0x18007403e  mov     rax, [rdi]
0x180074041  mov     rbx, [rax+30h]
0x180074045  mov     rcx, [rsp+338h+var_2D8]; string
0x18007404a  call    cs:__imp_WindowsDeleteString
0x180074050  mov     [rsp+338h+var_2D8], rsi
0x180074055  lea     rdx, [rsp+338h+var_2D8]
0x18007405a  mov     rcx, rdi
0x18007405d  mov     rax, rbx
0x180074060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074065  nop
0x180074066  lea     rcx, [rsp+338h+var_2B0]
0x18007406e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074073  nop
0x180074074  lea     rcx, [rsp+338h+var_2D0]
0x180074079  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007407e  nop
0x18007407f  lea     rcx, [rsp+338h+var_2A8]
0x180074087  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007408c  nop
0x18007408d  lea     rcx, [rsp+338h+var_2C8]
0x180074092  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074097  nop
0x180074098  lea     rcx, [rsp+338h+var_2C0]
0x18007409d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800740a2  mov     rcx, [rsp+338h+var_2D8]; string
0x1800740a7  mov     esi, [r14+60h]
0x1800740ab  xor     edx, edx; length
0x1800740ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1800740b3  mov     rbx, rax
0x1800740b6  mov     rdi, [r14+40h]
0x1800740ba  xor     edx, edx; length
0x1800740bc  mov     rcx, [r14+48h]; string
0x1800740c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800740c6  lea     rdx, [r14+58h]
0x1800740ca  mov     [rsp+338h+var_2E0], rdx
0x1800740cf  mov     [rsp+338h+var_2E8], esi
0x1800740d3  mov     [rsp+338h+var_2F0], rbx
0x1800740d8  mov     rcx, [rsp+338h+var_2A0]
0x1800740e0  mov     [rsp+338h+var_2F8], rcx
0x1800740e5  mov     [rsp+338h+var_300], rdi
0x1800740ea  mov     [rsp+338h+var_308], r13
0x1800740ef  lea     rcx, [rsp+338h+var_298]
0x1800740f7  mov     [rsp+338h+var_310], rcx
0x1800740fc  mov     [rsp+338h+var_318], r15d
0x180074101  lea     r9, [rsp+338h+pszOutBuf]
0x180074109  mov     r8, rax
0x18007410c  mov     rdx, [r14+38h]
0x180074110  mov     rcx, r12
0x180074113  call    ?LaunchModernTargetApp@@YAXAEBVCallerInformation@@PEAUIUnknown@@PEBG2W4InternalLauncherOptions@Launch@Internal@System@Windows@@PEBULAUNCH_PARAMETERS@@PEAUILauncherUIOptions@67@PEAUIStorageFileQueryResult@Search@Storage@7@PEAUHSTRING__@@2W4PendingLaunchType@Private@67@PEAPEAUIInspectable@@@Z; LaunchModernTargetApp(CallerInformation const &,IUnknown *,ushort const *,ushort const *,Windows::System::Internal::Launch::InternalLauncherOptions,LAUNCH_PARAMETERS const *,Windows::System::ILauncherUIOptions *,Windows::Storage::Search::IStorageFileQueryResult *,HSTRING__ *,ushort const *,Windows::System::Private::PendingLaunchType,IInspectable * *)
0x180074118  nop
0x180074119  mov     rcx, [rsp+338h+var_2D8]; string
0x18007411e  call    cs:__imp_WindowsDeleteString
0x180074124  mov     [rsp+338h+var_2D8], 0
0x18007412d  mov     rcx, [rsp+338h+string]; string
0x180074135  call    cs:__imp_WindowsDeleteString
0x18007413b  xor     eax, eax
0x18007413d  jmp     short loc_180074143
0x18007413f  mov     eax, dword ptr [rsp+338h+var_2D8]
0x180074143  mov     rcx, [rsp+338h+var_48]
0x18007414b  xor     rcx, rsp; StackCookie
0x18007414e  call    __security_check_cookie
0x180074153  add     rsp, 300h
0x18007415a  pop     r15
0x18007415c  pop     r14
0x18007415e  pop     r13
0x180074160  pop     r12
0x180074162  pop     rdi
0x180074163  pop     rsi
0x180074164  pop     rbx
0x180074165  retn
```
