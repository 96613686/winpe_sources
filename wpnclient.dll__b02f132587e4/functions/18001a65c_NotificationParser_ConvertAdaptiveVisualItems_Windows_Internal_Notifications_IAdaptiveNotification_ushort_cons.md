# NotificationParser::ConvertAdaptiveVisualItems(Windows::Internal::Notifications::IAdaptiveNotification *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x18001a65c`
- end: `0x18001acf4`
- name: `?ConvertAdaptiveVisualItems@NotificationParser@@AEAAXPEAUIAdaptiveNotification@Notifications@Internal@Windows@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@@Z`
- size: `1688`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001a1a8`

## callees

- `0x180005670`
- `0x180008910`
- `0x18000dc30`
- `0x18001a40c`
- `0x18001a65c`
- `0x18001acfc`
- `0x18001afb0`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a6e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001abc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ac97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001acb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001acc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a6e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001abc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ac97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001acb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001acc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HRESULT __fastcall NotificationParser::ConvertAdaptiveVisualItems(
        NotificationParser *this,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        __int64 a7)
{
  NotificationParser *v9; // rdi
  int v10; // eax
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  unsigned int v13; // esi
  HSTRING v14; // rcx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  __int64 (__fastcall *v18)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v19; // rbx
  int v20; // eax
  int v21; // eax
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  __int64 (__fastcall *v27)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v28; // rbx
  int v29; // eax
  int v30; // eax
  __int64 (__fastcall *v31)(__int64, __int64 *); // rbx
  int v32; // eax
  __int64 (__fastcall *v33)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v34; // rbx
  int v35; // eax
  int v36; // eax
  __int64 (__fastcall *v37)(__int64, __int64 *); // rbx
  int v38; // eax
  NotificationParser *v39; // r12
  __int64 (__fastcall *v40)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v41; // rbx
  int v42; // eax
  int v43; // eax
  void (__fastcall *v44)(__int64, HSTRING *); // rbx
  HSTRING v45; // rcx
  __int64 (__fastcall *v46)(__int64, _QWORD, NotificationParser *, _BYTE *); // rdi
  NotificationParser *v47; // rbx
  int v48; // eax
  int v49; // eax
  const char *v51; // [rsp+20h] [rbp-A1h]
  _BYTE v52[8]; // [rsp+40h] [rbp-81h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v53; // [rsp+48h] [rbp-79h] BYREF
  HSTRING string; // [rsp+50h] [rbp-71h] BYREF
  HSTRING v55; // [rsp+58h] [rbp-69h] BYREF
  __int64 v56; // [rsp+60h] [rbp-61h] BYREF
  NotificationParser *v57; // [rsp+68h] [rbp-59h] BYREF
  HSTRING v58; // [rsp+70h] [rbp-51h] BYREF
  const unsigned __int16 *v59; // [rsp+78h] [rbp-49h]
  __int64 v60; // [rsp+80h] [rbp-41h] BYREF
  _QWORD v61[4]; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int16 v62[12]; // [rsp+A8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v59 = a4;
  v9 = this;
  v57 = this;
  v52[0] = 0;
  v10 = StringCchPrintfW(v62, 0xAu, L"%ld", 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v10,
      (int)v51);
  v55 = 0;
  string = 0;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(0);
  v55 = 0;
  v12 = v11(a2, &v55);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v12,
      (int)v51);
  v13 = 1;
  v14 = v55;
  if ( v55 )
  {
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v15(a2, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v16,
        (int)v51);
    v53 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    NotificationParser::ConvertAdaptiveTextItem(v9, v17, a4, v55, string, &v53);
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)a7 + 80LL);
    v19 = v53;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, v62);
    v20 = v18(a7, v61[0], v19, v52);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v20,
        (int)v51);
    v21 = StringCchPrintfW(v62, 0xAu, L"%ld");
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v21,
        (int)v51);
    v13 = 2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    v14 = v55;
    v9 = v57;
  }
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(v14);
  v55 = 0;
  v23 = v22(a2, &v55);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v23,
      (int)v51);
  if ( v55 )
  {
    v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 88LL);
    WindowsDeleteString(string);
    string = 0;
    v25 = v24(a2, &string);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v25,
        (int)v51);
    v53 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    NotificationParser::ConvertAdaptiveTextItem(v9, v26, a4, v55, string, &v53);
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)a7 + 80LL);
    v28 = v53;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, v62);
    v29 = v27(a7, v61[0], v28, v52);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v29,
        (int)v51);
    v30 = StringCchPrintfW(v62, 0xAu, L"%ld", v13);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v30,
        (int)v51);
    ++v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  }
  v56 = 0;
  v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  v32 = v31(a2, &v56);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v32,
      (int)v51);
  if ( v56 )
  {
    v53 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    v51 = L"appLogoOverride";
    NotificationParser::ConvertAdaptiveImage(v57, v56, v59);
    v33 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)a7 + 80LL);
    v34 = v53;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, v62);
    v35 = v33(a7, v61[0], v34, v52);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v35,
        (int)L"appLogoOverride");
    v36 = StringCchPrintfW(v62, 0xAu, L"%ld", v13);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v36,
        (int)L"appLogoOverride");
    ++v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  }
  v60 = 0;
  v37 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  v38 = v37(a2, &v56);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v38,
      (int)v51);
  if ( v56 )
  {
    v53 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    v51 = L"hero";
    v39 = v57;
    NotificationParser::ConvertAdaptiveImage(v57, v56, v59);
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)a7 + 80LL);
    v41 = v53;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, v62);
    v42 = v40(a7, v61[0], v41, v52);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v42,
        (int)L"hero");
    v43 = StringCchPrintfW(v62, 0xAu, L"%ld", v13);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v43,
        (int)L"hero");
    ++v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  }
  else
  {
    v39 = v57;
  }
  v58 = 0;
  v44 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v58 = 0;
  v44(a2, &v58);
  v45 = v58;
  if ( v58 )
  {
    v57 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    NotificationParser::ConvertAdaptiveCardPayload(v39, v58, &v57);
    v46 = *(__int64 (__fastcall **)(__int64, _QWORD, NotificationParser *, _BYTE *))(*(_QWORD *)a7 + 80LL);
    v47 = v57;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, v62);
    v48 = v46(a7, v61[0], v47, v52);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v48,
        (int)v51);
    v49 = StringCchPrintfW(v62, 0xAu, L"%ld", v13);
    if ( v49 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v49,
        (int)v51);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    v45 = v58;
  }
  WindowsDeleteString(v45);
  v58 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  WindowsDeleteString(string);
  string = 0;
  return WindowsDeleteString(v55);
}

```

## disassembly

```asm
0x18001a65c  mov     [rsp-8+arg_10], rbx
0x18001a661  push    rbp
0x18001a662  push    rsi
0x18001a663  push    rdi
0x18001a664  push    r12
0x18001a666  push    r13
0x18001a668  push    r14
0x18001a66a  push    r15
0x18001a66c  lea     rbp, [rsp-0Fh]
0x18001a671  sub     rsp, 0D0h
0x18001a678  mov     rax, cs:__security_cookie
0x18001a67f  xor     rax, rsp
0x18001a682  mov     [rbp+3Fh+var_40], rax
0x18001a686  mov     r12, r9
0x18001a689  mov     [rbp+3Fh+var_88], r9
0x18001a68d  mov     r14, rdx
0x18001a690  mov     rdi, rcx
0x18001a693  mov     [rbp+3Fh+var_98], rcx
0x18001a697  mov     r15, [rbp+3Fh+arg_30]
0x18001a69b  xor     r13d, r13d
0x18001a69e  mov     [rsp+100h+var_C0], r13b
0x18001a6a3  xor     r9d, r9d
0x18001a6a6  lea     r8, aLd; "%ld"
0x18001a6ad  lea     edx, [r13+0Ah]; unsigned __int64
0x18001a6b1  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001a6b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a6ba  mov     rcx, [rbp+47h]; this
0x18001a6be  test    eax, eax
0x18001a6c0  jns     short loc_18001A6D7
0x18001a6c2  mov     r9d, eax; char *
0x18001a6c5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a6cc  mov     edx, 0E5h; void *
0x18001a6d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a6d7  mov     [rbp+3Fh+var_A8], r13
0x18001a6db  mov     [rbp+3Fh+string], r13
0x18001a6df  mov     rax, [r14]
0x18001a6e2  mov     rbx, [rax+40h]
0x18001a6e6  xor     ecx, ecx; string
0x18001a6e8  call    cs:__imp_WindowsDeleteString
0x18001a6ee  mov     [rbp+3Fh+var_A8], r13
0x18001a6f2  lea     rdx, [rbp+3Fh+var_A8]
0x18001a6f6  mov     rcx, r14
0x18001a6f9  mov     rax, rbx
0x18001a6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a701  mov     rcx, [rbp+47h]; this
0x18001a705  test    eax, eax
0x18001a707  jns     short loc_18001A71E
0x18001a709  mov     r9d, eax; char *
0x18001a70c  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a713  mov     edx, 0E9h; void *
0x18001a718  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a71e  mov     esi, 1
0x18001a723  mov     rcx, [rbp+3Fh+var_A8]
0x18001a727  test    rcx, rcx
0x18001a72a  jz      loc_18001A838
0x18001a730  mov     rax, [r14]
0x18001a733  mov     rbx, [rax+48h]
0x18001a737  mov     rcx, [rbp+3Fh+string]; string
0x18001a73b  call    cs:__imp_WindowsDeleteString
0x18001a741  mov     [rbp+3Fh+string], r13
0x18001a745  lea     rdx, [rbp+3Fh+string]
0x18001a749  mov     rcx, r14
0x18001a74c  mov     rax, rbx
0x18001a74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a754  mov     rcx, [rbp+47h]; this
0x18001a758  test    eax, eax
0x18001a75a  jns     short loc_18001A771
0x18001a75c  mov     r9d, eax; char *
0x18001a75f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a766  mov     edx, 0EDh; void *
0x18001a76b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a771  mov     [rbp+3Fh+var_B8], r13
0x18001a775  lea     rcx, [rbp+3Fh+var_B8]
0x18001a779  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a77e  lea     rax, [rbp+3Fh+var_B8]
0x18001a782  mov     [rsp+100h+var_D8], rax; struct Windows::Foundation::Collections::IPropertySet **
0x18001a787  mov     rax, [rbp+3Fh+string]
0x18001a78b  mov     [rsp+100h+var_E0], rax; int
0x18001a790  mov     r9, [rbp+3Fh+var_A8]; HSTRING
0x18001a794  mov     r8, r12; unsigned __int16 *
0x18001a797  mov     rcx, rdi; this
0x18001a79a  call    ?ConvertAdaptiveTextItem@NotificationParser@@AEAAXPEBG0PEAUHSTRING__@@1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ConvertAdaptiveTextItem(ushort const *,ushort const *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet * *)
0x18001a79f  mov     rax, [r15]
0x18001a7a2  mov     rdi, [rax+50h]
0x18001a7a6  mov     rbx, [rbp+3Fh+var_B8]
0x18001a7aa  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001a7ae  lea     rcx, [rbp+3Fh+var_78]; this
0x18001a7b2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001a7b7  lea     r9, [rsp+100h+var_C0]
0x18001a7bc  mov     r8, rbx
0x18001a7bf  mov     rdx, [rbp+3Fh+var_78]
0x18001a7c3  mov     rcx, r15
0x18001a7c6  mov     rax, rdi
0x18001a7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ce  mov     rcx, [rbp+47h]; this
0x18001a7d2  test    eax, eax
0x18001a7d4  jns     short loc_18001A7EB
0x18001a7d6  mov     r9d, eax; char *
0x18001a7d9  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a7e0  mov     edx, 0F1h; void *
0x18001a7e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a7eb  mov     r9d, 1
0x18001a7f1  lea     r8, aLd; "%ld"
0x18001a7f8  lea     edx, [r9+9]; unsigned __int64
0x18001a7fc  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001a800  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a805  mov     rcx, [rbp+47h]; this
0x18001a809  test    eax, eax
0x18001a80b  jns     short loc_18001A822
0x18001a80d  mov     r9d, eax; char *
0x18001a810  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a817  mov     edx, 0F2h; void *
0x18001a81c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a822  mov     esi, 2
0x18001a827  lea     rcx, [rbp+3Fh+var_B8]
0x18001a82b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a830  mov     rcx, [rbp+3Fh+var_A8]; string
0x18001a834  mov     rdi, [rbp+3Fh+var_98]
0x18001a838  mov     rax, [r14]
0x18001a83b  mov     rbx, [rax+50h]
0x18001a83f  call    cs:__imp_WindowsDeleteString
0x18001a845  mov     [rbp+3Fh+var_A8], r13
0x18001a849  lea     rdx, [rbp+3Fh+var_A8]
0x18001a84d  mov     rcx, r14
0x18001a850  mov     rax, rbx
0x18001a853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a858  mov     rcx, [rbp+47h]; this
0x18001a85c  test    eax, eax
0x18001a85e  jns     short loc_18001A875
0x18001a860  mov     r9d, eax; char *
0x18001a863  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a86a  mov     edx, 0F6h; void *
0x18001a86f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a875  cmp     [rbp+3Fh+var_A8], r13
0x18001a879  jz      loc_18001A97A
0x18001a87f  mov     rax, [r14]
0x18001a882  mov     rbx, [rax+58h]
0x18001a886  mov     rcx, [rbp+3Fh+string]; string
0x18001a88a  call    cs:__imp_WindowsDeleteString
0x18001a890  mov     [rbp+3Fh+string], r13
0x18001a894  lea     rdx, [rbp+3Fh+string]
0x18001a898  mov     rcx, r14
0x18001a89b  mov     rax, rbx
0x18001a89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8a3  mov     rcx, [rbp+47h]; this
0x18001a8a7  test    eax, eax
0x18001a8a9  jns     short loc_18001A8C0
0x18001a8ab  mov     r9d, eax; char *
0x18001a8ae  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a8b5  mov     edx, 0F9h; void *
0x18001a8ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a8c0  mov     [rbp+3Fh+var_B8], r13
0x18001a8c4  lea     rcx, [rbp+3Fh+var_B8]
0x18001a8c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a8cd  lea     rax, [rbp+3Fh+var_B8]
0x18001a8d1  mov     [rsp+100h+var_D8], rax; struct Windows::Foundation::Collections::IPropertySet **
0x18001a8d6  mov     rax, [rbp+3Fh+string]
0x18001a8da  mov     [rsp+100h+var_E0], rax; int
0x18001a8df  mov     r9, [rbp+3Fh+var_A8]; HSTRING
0x18001a8e3  mov     r8, r12; unsigned __int16 *
0x18001a8e6  mov     rcx, rdi; this
0x18001a8e9  call    ?ConvertAdaptiveTextItem@NotificationParser@@AEAAXPEBG0PEAUHSTRING__@@1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ConvertAdaptiveTextItem(ushort const *,ushort const *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet * *)
0x18001a8ee  mov     rax, [r15]
0x18001a8f1  mov     rdi, [rax+50h]
0x18001a8f5  mov     rbx, [rbp+3Fh+var_B8]
0x18001a8f9  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001a8fd  lea     rcx, [rbp+3Fh+var_78]; this
0x18001a901  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001a906  lea     r9, [rsp+100h+var_C0]
0x18001a90b  mov     r8, rbx
0x18001a90e  mov     rdx, [rbp+3Fh+var_78]
0x18001a912  mov     rcx, r15
0x18001a915  mov     rax, rdi
0x18001a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a91d  mov     rcx, [rbp+47h]; this
0x18001a921  test    eax, eax
0x18001a923  jns     short loc_18001A93A
0x18001a925  mov     r9d, eax; char *
0x18001a928  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a92f  mov     edx, 0FDh; void *
0x18001a934  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a93a  mov     r9d, esi
0x18001a93d  lea     r8, aLd; "%ld"
0x18001a944  mov     edx, 0Ah; unsigned __int64
0x18001a949  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001a94d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a952  mov     rcx, [rbp+47h]; this
0x18001a956  test    eax, eax
0x18001a958  jns     short loc_18001A96F
0x18001a95a  mov     r9d, eax; char *
0x18001a95d  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a964  mov     edx, 0FEh; void *
0x18001a969  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a96f  inc     esi
0x18001a971  lea     rcx, [rbp+3Fh+var_B8]
0x18001a975  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a97a  mov     [rbp+3Fh+var_A0], r13
0x18001a97e  mov     rax, [r14]
0x18001a981  mov     rbx, [rax+60h]
0x18001a985  lea     rcx, [rbp+3Fh+var_A0]
0x18001a989  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a98e  lea     rdx, [rbp+3Fh+var_A0]
0x18001a992  mov     rcx, r14
0x18001a995  mov     rax, rbx
0x18001a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99d  mov     rcx, [rbp+47h]; this
0x18001a9a1  test    eax, eax
0x18001a9a3  jns     short loc_18001A9BA
0x18001a9a5  mov     r9d, eax; char *
0x18001a9a8  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a9af  mov     edx, 102h; void *
0x18001a9b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a9ba  mov     r12d, [rbp+3Fh+arg_28]
0x18001a9be  mov     r13d, [rbp+3Fh+arg_20]
0x18001a9c2  xor     edi, edi
0x18001a9c4  cmp     [rbp+3Fh+var_A0], rdi
0x18001a9c8  jz      loc_18001AA99
0x18001a9ce  mov     [rbp+3Fh+var_B8], rdi
0x18001a9d2  lea     rcx, [rbp+3Fh+var_B8]
0x18001a9d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a9db  lea     rax, [rbp+3Fh+var_B8]
0x18001a9df  mov     [rsp+100h+var_C8], rax
0x18001a9e4  mov     [rsp+100h+var_D0], r12d
0x18001a9e9  mov     dword ptr [rsp+100h+var_D8], r13d
0x18001a9ee  lea     rax, aApplogooverrid; "appLogoOverride"
0x18001a9f5  mov     [rsp+100h+var_E0], rax; int
0x18001a9fa  mov     r8, [rbp+3Fh+var_88]
0x18001a9fe  mov     rdx, [rbp+3Fh+var_A0]
0x18001aa02  mov     rcx, [rbp+3Fh+var_98]
0x18001aa06  call    ?ConvertAdaptiveImage@NotificationParser@@AEAAXPEAUIAdaptiveImage@Notifications@Internal@Windows@@PEBG11W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z; NotificationParser::ConvertAdaptiveImage(Windows::Internal::Notifications::IAdaptiveImage *,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18001aa0b  mov     rax, [r15]
0x18001aa0e  mov     rdi, [rax+50h]
0x18001aa12  mov     rbx, [rbp+3Fh+var_B8]
0x18001aa16  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001aa1a  lea     rcx, [rbp+3Fh+var_78]; this
0x18001aa1e  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001aa23  lea     r9, [rsp+100h+var_C0]
0x18001aa28  mov     r8, rbx
0x18001aa2b  mov     rdx, [rbp+3Fh+var_78]
0x18001aa2f  mov     rcx, r15
0x18001aa32  mov     rax, rdi
0x18001aa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa3a  mov     rcx, [rbp+47h]; this
0x18001aa3e  xor     edi, edi
0x18001aa40  test    eax, eax
0x18001aa42  jns     short loc_18001AA59
0x18001aa44  mov     r9d, eax; char *
0x18001aa47  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001aa4e  mov     edx, 108h; void *
0x18001aa53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aa59  mov     r9d, esi
0x18001aa5c  lea     r8, aLd; "%ld"
0x18001aa63  mov     edx, 0Ah; unsigned __int64
0x18001aa68  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18001aa6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001aa71  mov     rcx, [rbp+47h]; this
0x18001aa75  test    eax, eax
0x18001aa77  jns     short loc_18001AA8E
0x18001aa79  mov     r9d, eax; char *
0x18001aa7c  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001aa83  mov     edx, 109h; void *
0x18001aa88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aa8e  inc     esi
0x18001aa90  lea     rcx, [rbp+3Fh+var_B8]
0x18001aa94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001aa99  mov     [rbp+3Fh+var_80], rdi
0x18001aa9d  mov     rax, [r14]
0x18001aaa0  mov     rbx, [rax+68h]
0x18001aaa4  lea     rcx, [rbp+3Fh+var_A0]
0x18001aaa8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001aaad  lea     rdx, [rbp+3Fh+var_A0]
0x18001aab1  mov     rcx, r14
0x18001aab4  mov     rax, rbx
0x18001aab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aabc  mov     rcx, [rbp+47h]; this
0x18001aac0  test    eax, eax
0x18001aac2  jns     short loc_18001AAD9
0x18001aac4  mov     r9d, eax; char *
0x18001aac7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001aace  mov     edx, 10Dh; void *
0x18001aad3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aad9  cmp     [rbp+3Fh+var_A0], rdi
0x18001aadd  jz      loc_18001ABB3
0x18001aae3  mov     [rbp+3Fh+var_B8], rdi
0x18001aae7  lea     rcx, [rbp+3Fh+var_B8]
0x18001aaeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001aaf0  lea     rax, [rbp+3Fh+var_B8]
0x18001aaf4  mov     [rsp+100h+var_C8], rax
0x18001aaf9  mov     [rsp+100h+var_D0], r12d
0x18001aafe  mov     dword ptr [rsp+100h+var_D8], r13d
0x18001ab03  lea     rax, aHero; "hero"
0x18001ab0a  mov     [rsp+100h+var_E0], rax; int
0x18001ab0f  mov     r8, [rbp+3Fh+var_88]
0x18001ab13  mov     rdx, [rbp+3Fh+var_A0]
0x18001ab17  mov     r12, [rbp+3Fh+var_98]
0x18001ab1b  mov     rcx, r12
0x18001ab1e  call    ?ConvertAdaptiveImage@NotificationParser@@AEAAXPEAUIAdaptiveImage@Notifications@Internal@Windows@@PEBG11W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z; NotificationParser::ConvertAdaptiveImage(Windows::Internal::Notifications::IAdaptiveImage *,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18001ab23  mov     rax, [r15]
0x18001ab26  mov     rdi, [rax+50h]
0x18001ab2a  mov     rbx, [rbp+3Fh+var_B8]
  ... truncated ...
```
