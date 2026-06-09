# NotificationParser::TransformAdaptiveToast(Windows::Internal::Notifications::IAdaptiveNotification *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180019d04`
- end: `0x18001a1a2`
- name: `?TransformAdaptiveToast@NotificationParser@@QEAAXPEAUIAdaptiveNotification@Notifications@Internal@Windows@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z`
- size: `1182`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180002b70`

## callees

- `0x180005670`
- `0x180008390`
- `0x180013bc0`
- `0x180014160`
- `0x180014550`
- `0x1800151b8`
- `0x180019d04`
- `0x18001a1a8`
- `0x18001a610`
- `0x18001b494`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019db6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019db6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a150`

## string_xrefs

- `0x180019e55`: `protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NotificationParser::TransformAdaptiveToast(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v10; // rcx
  _QWORD *v11; // rax
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v19; // rax
  int v20; // eax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v23; // rbx
  _QWORD *v24; // rax
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v31; // rbx
  _QWORD *v32; // rax
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v36; // rax
  int v37; // eax
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v40; // rbx
  _QWORD *v41; // rax
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, HSTRING, __int64 *); // rbx
  int v45; // eax
  __int64 v46; // rsi
  __int64 (__fastcall *v47)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v48; // rbx
  _QWORD *v49; // rax
  int v50; // eax
  __int64 v51; // r8
  __int64 v52; // rsi
  __int64 (__fastcall *v53)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v54; // rbx
  _QWORD *v55; // rax
  int v56; // eax
  __int64 v57; // rax
  int v59; // [rsp+20h] [rbp-61h]
  _BYTE v60[8]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v61; // [rsp+48h] [rbp-39h] BYREF
  HSTRING string; // [rsp+50h] [rbp-31h] BYREF
  __int64 v63; // [rsp+58h] [rbp-29h] BYREF
  __int64 v64; // [rsp+60h] [rbp-21h] BYREF
  HSTRING v65[4]; // [rsp+68h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v64 = 0;
  v63 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  NotificationParser::CreateValueSet(v10, &v64, &v63);
  v61 = 0;
  v60[0] = 0;
  if ( !*a1 )
  {
    v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"Windows.Foundation.PropertyValue");
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
            *v11,
            a1);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v12,
        v59);
  }
  string = 0;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 112LL);
  WindowsDeleteString(0);
  string = 0;
  v14 = v13(a2, &string);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v14,
      v59);
  if ( string )
  {
    v34 = *a1;
    v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v36 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"foreground");
    v37 = v35(v34, *v36, &v61);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v37,
        v59);
    v38 = v63;
    v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v63 + 80LL);
    v40 = v61;
    v41 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"activationType");
    v42 = v39(v38, *v41, v40, v60);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v42,
        v59);
    v43 = *a1;
    v44 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a1 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    v45 = v44(v43, string, &v61);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v45,
        v59);
    v46 = v63;
    v47 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v63 + 80LL);
    v48 = v61;
    v49 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"launch");
    v50 = v47(v46, *v49, v48, v60);
    if ( v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v50,
        v59);
  }
  else
  {
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 120LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = v15(a2, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v16,
        v59);
    if ( string )
    {
      v17 = *a1;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 144LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"protocol");
      v20 = v18(v17, *v19, &v61);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA7,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v20,
          v59);
      v21 = v63;
      v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v63 + 80LL);
      v23 = v61;
      v24 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"activationType");
      v25 = v22(v21, *v24, v23, v60);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v25,
          v59);
      v26 = *a1;
      v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a1 + 144LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      v28 = v27(v26, string, &v61);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v28,
          v59);
      v29 = v63;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v63 + 80LL);
      v31 = v61;
      v32 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"launch");
      v33 = v30(v29, *v32, v31, v60);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v33,
          v59);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  NotificationParser::ConvertAdaptiveVisual(a1, a2, v51, a4);
  v52 = v63;
  v53 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v63 + 80LL);
  v54 = v61;
  v55 = (_QWORD *)Windows::Internal::StringReference::StringReference(v65, L"visual");
  v56 = v53(v52, *v55, v54, v60);
  if ( v56 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v56,
      a5);
  v57 = v64;
  v64 = 0;
  *a7 = v57;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
}

```

## disassembly

```asm
0x180019d04  mov     [rsp-8+arg_10], rbx
0x180019d09  push    rbp
0x180019d0a  push    rsi
0x180019d0b  push    rdi
0x180019d0c  push    r12
0x180019d0e  push    r13
0x180019d10  push    r14
0x180019d12  push    r15
0x180019d14  lea     rbp, [rsp-0Fh]
0x180019d19  sub     rsp, 90h
0x180019d20  mov     rax, cs:__security_cookie
0x180019d27  xor     rax, rsp
0x180019d2a  mov     [rbp+3Fh+var_38], rax
0x180019d2e  mov     r13, r9
0x180019d31  mov     r15, rdx
0x180019d34  mov     r14, rcx
0x180019d37  mov     r12, [rbp+3Fh+arg_30]
0x180019d3b  xor     esi, esi
0x180019d3d  mov     [rbp+3Fh+var_60], rsi
0x180019d41  mov     [rbp+3Fh+var_68], rsi
0x180019d45  lea     rcx, [rbp+3Fh+var_68]
0x180019d49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d4e  lea     rcx, [rbp+3Fh+var_60]
0x180019d52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d57  lea     r8, [rbp+3Fh+var_68]
0x180019d5b  lea     rdx, [rbp+3Fh+var_60]
0x180019d5f  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180019d64  mov     [rbp+3Fh+var_78], rsi
0x180019d68  mov     [rbp+3Fh+var_80], sil
0x180019d6c  cmp     [r14], rsi
0x180019d6f  jnz     short loc_180019DA9
0x180019d71  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180019d78  lea     rcx, [rbp+3Fh+var_58]; string
0x180019d7c  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x180019d81  mov     rdx, r14
0x180019d84  mov     rcx, [rax]
0x180019d87  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180019d8c  mov     rcx, [rbp+47h]; this
0x180019d90  test    eax, eax
0x180019d92  jns     short loc_180019DA9
0x180019d94  mov     r9d, eax; char *
0x180019d97  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019d9e  mov     edx, 94h; void *
0x180019da3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019da9  mov     [rbp+3Fh+string], rsi
0x180019dad  mov     rax, [r15]
0x180019db0  mov     rbx, [rax+70h]
0x180019db4  xor     ecx, ecx; string
0x180019db6  call    cs:__imp_WindowsDeleteString
0x180019dbc  mov     [rbp+3Fh+string], rsi
0x180019dc0  lea     rdx, [rbp+3Fh+string]
0x180019dc4  mov     rcx, r15
0x180019dc7  mov     rax, rbx
0x180019dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dcf  mov     rcx, [rbp+47h]; this
0x180019dd3  test    eax, eax
0x180019dd5  jns     short loc_180019DEC
0x180019dd7  mov     r9d, eax; char *
0x180019dda  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019de1  mov     edx, 98h; void *
0x180019de6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019dec  cmp     [rbp+3Fh+string], rsi
0x180019df0  jnz     loc_180019F80
0x180019df6  mov     rax, [r15]
0x180019df9  mov     rbx, [rax+78h]
0x180019dfd  xor     ecx, ecx; string
0x180019dff  call    cs:__imp_WindowsDeleteString
0x180019e05  mov     [rbp+3Fh+string], rsi
0x180019e09  lea     rdx, [rbp+3Fh+string]
0x180019e0d  mov     rcx, r15
0x180019e10  mov     rax, rbx
0x180019e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e18  mov     rcx, [rbp+47h]; this
0x180019e1c  test    eax, eax
0x180019e1e  jns     short loc_180019E35
0x180019e20  mov     r9d, eax; char *
0x180019e23  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019e2a  mov     edx, 0A4h; void *
0x180019e2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019e35  cmp     [rbp+3Fh+string], rsi
0x180019e39  jz      loc_18001A0BD
0x180019e3f  mov     rdi, [r14]
0x180019e42  mov     rax, [rdi]
0x180019e45  mov     rbx, [rax+90h]
0x180019e4c  lea     rcx, [rbp+3Fh+var_78]
0x180019e50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019e55  lea     rdx, aProtocol; "protocol"
0x180019e5c  lea     rcx, [rbp+3Fh+var_58]; string
0x180019e60  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x180019e65  lea     r8, [rbp+3Fh+var_78]
0x180019e69  mov     rdx, [rax]
0x180019e6c  mov     rcx, rdi
0x180019e6f  mov     rax, rbx
0x180019e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e77  mov     rcx, [rbp+47h]; this
0x180019e7b  test    eax, eax
0x180019e7d  jns     short loc_180019E94
0x180019e7f  mov     r9d, eax; char *
0x180019e82  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019e89  mov     edx, 0A7h; void *
0x180019e8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019e94  mov     rsi, [rbp+3Fh+var_68]
0x180019e98  mov     rax, [rsi]
0x180019e9b  mov     rdi, [rax+50h]
0x180019e9f  mov     rbx, [rbp+3Fh+var_78]
0x180019ea3  lea     rdx, aActivationtype; "activationType"
0x180019eaa  lea     rcx, [rbp+3Fh+var_58]; string
0x180019eae  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x180019eb3  lea     r9, [rbp+3Fh+var_80]
0x180019eb7  mov     r8, rbx
0x180019eba  mov     rdx, [rax]
0x180019ebd  mov     rcx, rsi
0x180019ec0  mov     rax, rdi
0x180019ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ec8  mov     rcx, [rbp+47h]; this
0x180019ecc  test    eax, eax
0x180019ece  jns     short loc_180019EE5
0x180019ed0  mov     r9d, eax; char *
0x180019ed3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019eda  mov     edx, 0A8h; void *
0x180019edf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019ee5  mov     rdi, [r14]
0x180019ee8  mov     rax, [rdi]
0x180019eeb  mov     rbx, [rax+90h]
0x180019ef2  lea     rcx, [rbp+3Fh+var_78]
0x180019ef6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019efb  lea     r8, [rbp+3Fh+var_78]
0x180019eff  mov     rdx, [rbp+3Fh+string]
0x180019f03  mov     rcx, rdi
0x180019f06  mov     rax, rbx
0x180019f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f0e  mov     rcx, [rbp+47h]; this
0x180019f12  test    eax, eax
0x180019f14  jns     short loc_180019F2B
0x180019f16  mov     r9d, eax; char *
0x180019f19  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019f20  mov     edx, 0A9h; void *
0x180019f25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019f2b  mov     rsi, [rbp+3Fh+var_68]
0x180019f2f  mov     rax, [rsi]
0x180019f32  mov     rdi, [rax+50h]
0x180019f36  mov     rbx, [rbp+3Fh+var_78]
0x180019f3a  lea     rdx, aLaunch; "launch"
0x180019f41  lea     rcx, [rbp+3Fh+var_58]; string
0x180019f45  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x180019f4a  lea     r9, [rbp+3Fh+var_80]
0x180019f4e  mov     r8, rbx
0x180019f51  mov     rdx, [rax]
0x180019f54  mov     rcx, rsi
0x180019f57  mov     rax, rdi
0x180019f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f5f  mov     rcx, [rbp+47h]; this
0x180019f63  test    eax, eax
0x180019f65  jns     loc_18001A0BD
0x180019f6b  mov     r9d, eax; char *
0x180019f6e  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019f75  mov     edx, 0AAh; void *
0x180019f7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019f80  mov     rdi, [r14]
0x180019f83  mov     rax, [rdi]
0x180019f86  mov     rbx, [rax+90h]
0x180019f8d  lea     rcx, [rbp+3Fh+var_78]
0x180019f91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019f96  lea     rdx, aForeground; "foreground"
0x180019f9d  lea     rcx, [rbp+3Fh+var_58]; string
0x180019fa1  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x180019fa6  lea     r8, [rbp+3Fh+var_78]
0x180019faa  mov     rdx, [rax]
0x180019fad  mov     rcx, rdi
0x180019fb0  mov     rax, rbx
0x180019fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb8  mov     rcx, [rbp+47h]; this
0x180019fbc  test    eax, eax
0x180019fbe  jns     short loc_180019FD5
0x180019fc0  mov     r9d, eax; char *
0x180019fc3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019fca  mov     edx, 9Dh; void *
0x180019fcf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019fd5  mov     rsi, [rbp+3Fh+var_68]
0x180019fd9  mov     rax, [rsi]
0x180019fdc  mov     rdi, [rax+50h]
0x180019fe0  mov     rbx, [rbp+3Fh+var_78]
0x180019fe4  lea     rdx, aActivationtype; "activationType"
0x180019feb  lea     rcx, [rbp+3Fh+var_58]; string
0x180019fef  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x180019ff4  lea     r9, [rbp+3Fh+var_80]
0x180019ff8  mov     r8, rbx
0x180019ffb  mov     rdx, [rax]
0x180019ffe  mov     rcx, rsi
0x18001a001  mov     rax, rdi
0x18001a004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a009  mov     rcx, [rbp+47h]; this
0x18001a00d  test    eax, eax
0x18001a00f  jns     short loc_18001A026
0x18001a011  mov     r9d, eax; char *
0x18001a014  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a01b  mov     edx, 9Eh; void *
0x18001a020  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a026  mov     rdi, [r14]
0x18001a029  mov     rax, [rdi]
0x18001a02c  mov     rbx, [rax+90h]
0x18001a033  lea     rcx, [rbp+3Fh+var_78]
0x18001a037  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a03c  lea     r8, [rbp+3Fh+var_78]
0x18001a040  mov     rdx, [rbp+3Fh+string]
0x18001a044  mov     rcx, rdi
0x18001a047  mov     rax, rbx
0x18001a04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a04f  mov     rcx, [rbp+47h]; this
0x18001a053  test    eax, eax
0x18001a055  jns     short loc_18001A06C
0x18001a057  mov     r9d, eax; char *
0x18001a05a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a061  mov     edx, 9Fh; void *
0x18001a066  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a06c  mov     rsi, [rbp+3Fh+var_68]
0x18001a070  mov     rax, [rsi]
0x18001a073  mov     rdi, [rax+50h]
0x18001a077  mov     rbx, [rbp+3Fh+var_78]
0x18001a07b  lea     rdx, aLaunch; "launch"
0x18001a082  lea     rcx, [rbp+3Fh+var_58]; string
0x18001a086  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x18001a08b  lea     r9, [rbp+3Fh+var_80]
0x18001a08f  mov     r8, rbx
0x18001a092  mov     rdx, [rax]
0x18001a095  mov     rcx, rsi
0x18001a098  mov     rax, rdi
0x18001a09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0a0  mov     rcx, [rbp+47h]; this
0x18001a0a4  test    eax, eax
0x18001a0a6  jns     short loc_18001A0BD
0x18001a0a8  mov     r9d, eax; char *
0x18001a0ab  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a0b2  mov     edx, 0A0h; void *
0x18001a0b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a0bd  lea     rcx, [rbp+3Fh+var_78]
0x18001a0c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a0c6  lea     rax, [rbp+3Fh+var_78]
0x18001a0ca  mov     [rsp+0C0h+var_90], rax
0x18001a0cf  mov     eax, [rbp+3Fh+arg_28]
0x18001a0d2  mov     [rsp+0C0h+var_98], eax
0x18001a0d6  mov     eax, [rbp+3Fh+arg_20]
0x18001a0d9  mov     [rsp+0C0h+var_A0], eax; int
0x18001a0dd  mov     r9, r13
0x18001a0e0  mov     rdx, r15
0x18001a0e3  mov     rcx, r14
0x18001a0e6  call    ?ConvertAdaptiveVisual@NotificationParser@@AEAAXPEAUIAdaptiveNotification@Notifications@Internal@Windows@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z; NotificationParser::ConvertAdaptiveVisual(Windows::Internal::Notifications::IAdaptiveNotification *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18001a0eb  mov     rsi, [rbp+3Fh+var_68]
0x18001a0ef  mov     rax, [rsi]
0x18001a0f2  mov     rdi, [rax+50h]
0x18001a0f6  mov     rbx, [rbp+3Fh+var_78]
0x18001a0fa  lea     rdx, sourceString; "visual"
0x18001a101  lea     rcx, [rbp+3Fh+var_58]; string
0x18001a105  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x18001a10a  lea     r9, [rbp+3Fh+var_80]
0x18001a10e  mov     r8, rbx
0x18001a111  mov     rdx, [rax]
0x18001a114  mov     rcx, rsi
0x18001a117  mov     rax, rdi
0x18001a11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a11f  mov     rcx, [rbp+47h]; this
0x18001a123  test    eax, eax
0x18001a125  jns     short loc_18001A13C
0x18001a127  mov     r9d, eax; char *
0x18001a12a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a131  mov     edx, 0B1h; void *
0x18001a136  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a13c  mov     rax, [rbp+3Fh+var_60]
0x18001a140  mov     [rbp+3Fh+var_60], 0
0x18001a148  mov     [r12], rax
0x18001a14c  mov     rcx, [rbp+3Fh+string]; string
0x18001a150  call    cs:__imp_WindowsDeleteString
0x18001a156  mov     [rbp+3Fh+string], 0
0x18001a15e  lea     rcx, [rbp+3Fh+var_78]
0x18001a162  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a167  nop
0x18001a168  lea     rcx, [rbp+3Fh+var_68]
0x18001a16c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a171  nop
0x18001a172  lea     rcx, [rbp+3Fh+var_60]
0x18001a176  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a17b  mov     rcx, [rbp+3Fh+var_38]
0x18001a17f  xor     rcx, rsp; StackCookie
0x18001a182  call    __security_check_cookie
0x18001a187  mov     rbx, [rsp+0C0h+arg_10]
0x18001a18f  add     rsp, 90h
0x18001a196  pop     r15
0x18001a198  pop     r14
0x18001a19a  pop     r13
0x18001a19c  pop     r12
0x18001a19e  pop     rdi
0x18001a19f  pop     rsi
0x18001a1a0  pop     rbp
0x18001a1a1  retn
```
