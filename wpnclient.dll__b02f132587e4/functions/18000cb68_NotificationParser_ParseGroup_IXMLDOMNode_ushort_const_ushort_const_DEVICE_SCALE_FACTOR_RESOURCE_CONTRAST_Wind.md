# NotificationParser::ParseGroup(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18000cb68`
- end: `0x18000d0c9`
- name: `?ParseGroup@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800192d4`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x180008fe0`
- `0x180009380`
- `0x18000cb68`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc33`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cca6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cd4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cf13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cc33`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cca6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cd4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cf13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cc1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cc8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cd33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cf27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cc1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cc8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cd33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cf27`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall NotificationParser::ParseGroup(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 v7; // r12
  __int64 *v9; // r15
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64 *); // rsi
  int v13; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64, _BYTE *); // r14
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64, _BYTE *); // r14
  __int64 v21; // rsi
  int v22; // eax
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  int v25; // eax
  unsigned int v26; // r14d
  unsigned int i; // esi
  __int64 v28; // rdi
  void (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  int v30; // eax
  OLECHAR *v31; // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING, __int64, _BYTE *); // r12
  __int64 v35; // r15
  unsigned __int64 v36; // rbx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 result; // rax
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // [rsp+20h] [rbp-C1h]
  _BYTE v48[4]; // [rsp+40h] [rbp-A1h] BYREF
  int v49; // [rsp+44h] [rbp-9Dh] BYREF
  __int64 v50; // [rsp+48h] [rbp-99h] BYREF
  __int64 v51; // [rsp+50h] [rbp-91h] BYREF
  __int64 v52; // [rsp+58h] [rbp-89h] BYREF
  __int64 v53; // [rsp+60h] [rbp-81h] BYREF
  __int64 v54; // [rsp+68h] [rbp-79h] BYREF
  __int64 v55; // [rsp+70h] [rbp-71h] BYREF
  __int64 v56; // [rsp+78h] [rbp-69h] BYREF
  __int64 v57; // [rsp+80h] [rbp-61h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-59h] BYREF
  __int64 *v59; // [rsp+90h] [rbp-51h]
  __int64 v60; // [rsp+98h] [rbp-49h]
  __int64 *v61; // [rsp+A0h] [rbp-41h]
  HSTRING string; // [rsp+A8h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-31h] BYREF
  WCHAR sourceString[12]; // [rsp+C8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = a3;
  v60 = a3;
  v9 = a1;
  v59 = a1;
  v61 = a7;
  v53 = 0;
  v50 = 0;
  v57 = 0;
  v56 = 0;
  v55 = 0;
  v52 = 0;
  v48[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  NotificationParser::CreateValueSet(v10, &v53, &v50);
  v11 = *v9;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*v9 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  if ( WindowsCreateStringReference(L"group", 5u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v13 = v12(v11, string, &v55);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x482,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v13,
      v47);
  v14 = v50;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v50 + 80LL);
  v16 = v55;
  if ( WindowsCreateStringReference(L"item-type", 9u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v17 = v15(v14, string, v16, v48);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x485,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      v47);
  NotificationParser::GetAttributes(v9, a2, v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  NotificationParser::CreateValueSet(v18, &v57, &v56);
  v19 = v50;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v50 + 80LL);
  v21 = v57;
  if ( WindowsCreateStringReference(L"subgroups", 9u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v22 = v20(v19, string, v21, v48);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v22,
      v47);
  v49 = 0;
  v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  v24 = v23(a2, &v52);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x492,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v24,
      v47);
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 64LL))(v52, &v49);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v25,
      v47);
  v26 = 0;
  for ( i = 0; (int)i < v49; ++i )
  {
    v51 = 0;
    v28 = v52;
    v29 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v29(v28, i, &v51);
    String1 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v51 + 56LL))(v51, &String1);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x49F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v30,
        v47);
    v31 = String1;
    if ( !wcscmp_0(String1, L"subgroup") )
    {
      v32 = StringCchPrintfW(sourceString, 0xAu, L"%ld", v26);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v32,
          v47);
      v54 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
      v47 = a5;
      NotificationParser::ParseSubGroup(v9, v51, v7);
      v33 = v56;
      v34 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v56 + 80LL);
      v35 = v54;
      v36 = -1;
      do
        ++v36;
      while ( sourceString[v36] );
      if ( v36 > 0xFFFFFFFF )
      {
        LODWORD(v36) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(sourceString, v36, &hstringHeader, &string);
      v37 = v34(v33, string, v35, v48);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v37,
          a5);
      ++v26;
      v38 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v31 = String1;
      v9 = v59;
      v7 = v60;
    }
    SysFreeString(v31);
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
  }
  result = v53;
  v53 = 0;
  *v61 = result;
  v41 = v52;
  if ( v52 )
  {
    v52 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v55;
  if ( v55 )
  {
    v55 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v56;
  if ( v56 )
  {
    v56 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v57;
  if ( v57 )
  {
    v57 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v50;
  if ( v50 )
  {
    v50 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v53;
  if ( v53 )
  {
    v53 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return result;
}

```

## disassembly

```asm
0x18000cb68  mov     [rsp-8+arg_18], rbx
0x18000cb6d  push    rbp
0x18000cb6e  push    rsi
0x18000cb6f  push    rdi
0x18000cb70  push    r12
0x18000cb72  push    r13
0x18000cb74  push    r14
0x18000cb76  push    r15
0x18000cb78  lea     rbp, [rsp-0Fh]
0x18000cb7d  sub     rsp, 0F0h
0x18000cb84  mov     rax, cs:__security_cookie
0x18000cb8b  xor     rax, rsp
0x18000cb8e  mov     [rbp+3Fh+var_40], rax
0x18000cb92  mov     r12, r8
0x18000cb95  mov     [rbp+3Fh+var_88], r8
0x18000cb99  mov     rdi, rdx
0x18000cb9c  mov     r15, rcx
0x18000cb9f  mov     [rbp+3Fh+var_90], rcx
0x18000cba3  mov     rax, [rbp+3Fh+arg_30]
0x18000cba7  mov     [rbp+3Fh+var_80], rax
0x18000cbab  xor     r13d, r13d
0x18000cbae  mov     [rsp+120h+var_C0], r13
0x18000cbb3  mov     [rsp+120h+var_D8], r13
0x18000cbb8  mov     [rbp+3Fh+var_A0], r13
0x18000cbbc  mov     [rbp+3Fh+var_A8], r13
0x18000cbc0  mov     [rbp+3Fh+var_B0], r13
0x18000cbc4  mov     [rsp+120h+var_C8], r13
0x18000cbc9  mov     [rsp+120h+var_E0], r13b
0x18000cbce  lea     rcx, [rsp+120h+var_D8]
0x18000cbd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cbd8  lea     rcx, [rsp+120h+var_C0]
0x18000cbdd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cbe2  lea     r8, [rsp+120h+var_D8]
0x18000cbe7  lea     rdx, [rsp+120h+var_C0]
0x18000cbec  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18000cbf1  mov     rbx, [r15]
0x18000cbf4  mov     rax, [rbx]
0x18000cbf7  mov     rsi, [rax+90h]
0x18000cbfe  lea     rcx, [rbp+3Fh+var_B0]
0x18000cc02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc07  lea     r9, [rbp+3Fh+string]; string
0x18000cc0b  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18000cc0f  lea     edx, [r13+5]; length
0x18000cc13  lea     rcx, aGroup; "group"
0x18000cc1a  call    cs:__imp_WindowsCreateStringReference
0x18000cc20  test    eax, eax
0x18000cc22  jns     short loc_18000CC39
0x18000cc24  xor     r9d, r9d; lpArguments
0x18000cc27  xor     r8d, r8d; nNumberOfArguments
0x18000cc2a  lea     edx, [r13+1]; dwExceptionFlags
0x18000cc2e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cc33  call    cs:__imp_RaiseException
0x18000cc39  lea     r8, [rbp+3Fh+var_B0]
0x18000cc3d  mov     rdx, [rbp+3Fh+string]
0x18000cc41  mov     rcx, rbx
0x18000cc44  mov     rax, rsi
0x18000cc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4c  mov     rcx, [rbp+47h]; this
0x18000cc50  test    eax, eax
0x18000cc52  jns     short loc_18000CC69
0x18000cc54  mov     r9d, eax; char *
0x18000cc57  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cc5e  mov     edx, 482h; void *
0x18000cc63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cc69  mov     rbx, [rsp+120h+var_D8]
0x18000cc6e  mov     rax, [rbx]
0x18000cc71  mov     r14, [rax+50h]
0x18000cc75  mov     rsi, [rbp+3Fh+var_B0]
0x18000cc79  lea     r9, [rbp+3Fh+string]; string
0x18000cc7d  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18000cc81  mov     edx, 9; length
0x18000cc86  lea     rcx, aItemType; "item-type"
0x18000cc8d  call    cs:__imp_WindowsCreateStringReference
0x18000cc93  test    eax, eax
0x18000cc95  jns     short loc_18000CCAC
0x18000cc97  xor     r9d, r9d; lpArguments
0x18000cc9a  xor     r8d, r8d; nNumberOfArguments
0x18000cc9d  lea     edx, [r9+1]; dwExceptionFlags
0x18000cca1  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cca6  call    cs:__imp_RaiseException
0x18000ccac  lea     r9, [rsp+120h+var_E0]
0x18000ccb1  mov     r8, rsi
0x18000ccb4  mov     rdx, [rbp+3Fh+string]
0x18000ccb8  mov     rcx, rbx
0x18000ccbb  mov     rax, r14
0x18000ccbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc3  mov     rcx, [rbp+47h]; this
0x18000ccc7  test    eax, eax
0x18000ccc9  jns     short loc_18000CCE0
0x18000cccb  mov     r9d, eax; char *
0x18000ccce  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ccd5  mov     edx, 485h; void *
0x18000ccda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cce0  mov     r8, [rsp+120h+var_D8]
0x18000cce5  mov     rdx, rdi
0x18000cce8  mov     rcx, r15
0x18000cceb  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18000ccf0  lea     rcx, [rbp+3Fh+var_A8]
0x18000ccf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ccf9  lea     rcx, [rbp+3Fh+var_A0]
0x18000ccfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd02  lea     r8, [rbp+3Fh+var_A8]
0x18000cd06  lea     rdx, [rbp+3Fh+var_A0]
0x18000cd0a  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18000cd0f  mov     rbx, [rsp+120h+var_D8]
0x18000cd14  mov     rax, [rbx]
0x18000cd17  mov     r14, [rax+50h]
0x18000cd1b  mov     rsi, [rbp+3Fh+var_A0]
0x18000cd1f  lea     r9, [rbp+3Fh+string]; string
0x18000cd23  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18000cd27  mov     edx, 9; length
0x18000cd2c  lea     rcx, aSubgroups; "subgroups"
0x18000cd33  call    cs:__imp_WindowsCreateStringReference
0x18000cd39  test    eax, eax
0x18000cd3b  jns     short loc_18000CD52
0x18000cd3d  xor     r9d, r9d; lpArguments
0x18000cd40  xor     r8d, r8d; nNumberOfArguments
0x18000cd43  lea     edx, [r9+1]; dwExceptionFlags
0x18000cd47  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cd4c  call    cs:__imp_RaiseException
0x18000cd52  lea     r9, [rsp+120h+var_E0]
0x18000cd57  mov     r8, rsi
0x18000cd5a  mov     rdx, [rbp+3Fh+string]
0x18000cd5e  mov     rcx, rbx
0x18000cd61  mov     rax, r14
0x18000cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd69  mov     rcx, [rbp+47h]; this
0x18000cd6d  test    eax, eax
0x18000cd6f  jns     short loc_18000CD86
0x18000cd71  mov     r9d, eax; char *
0x18000cd74  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cd7b  mov     edx, 48Dh; void *
0x18000cd80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cd86  mov     [rsp+120h+var_DC], r13d
0x18000cd8b  mov     rax, [rdi]
0x18000cd8e  mov     rbx, [rax+60h]
0x18000cd92  lea     rcx, [rsp+120h+var_C8]
0x18000cd97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd9c  lea     rdx, [rsp+120h+var_C8]
0x18000cda1  mov     rcx, rdi
0x18000cda4  mov     rax, rbx
0x18000cda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdac  mov     rcx, [rbp+47h]; this
0x18000cdb0  test    eax, eax
0x18000cdb2  jns     short loc_18000CDC9
0x18000cdb4  mov     r9d, eax; char *
0x18000cdb7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cdbe  mov     edx, 492h; void *
0x18000cdc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cdc9  mov     rcx, [rsp+120h+var_C8]
0x18000cdce  mov     rax, [rcx]
0x18000cdd1  lea     rdx, [rsp+120h+var_DC]
0x18000cdd6  mov     rax, [rax+40h]
0x18000cdda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cddf  mov     rcx, [rbp+47h]; this
0x18000cde3  test    eax, eax
0x18000cde5  jns     short loc_18000CDFC
0x18000cde7  mov     r9d, eax; char *
0x18000cdea  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cdf1  mov     edx, 494h; void *
0x18000cdf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cdfc  mov     r14d, r13d
0x18000cdff  mov     esi, r13d
0x18000ce02  cmp     [rsp+120h+var_DC], r13d
0x18000ce07  jle     loc_18000CFB0
0x18000ce0d  mov     r13d, [rbp+3Fh+arg_28]
0x18000ce11  xor     edi, edi
0x18000ce13  mov     [rsp+120h+var_D0], rdi
0x18000ce18  mov     rdi, [rsp+120h+var_C8]
0x18000ce1d  mov     rax, [rdi]
0x18000ce20  mov     rbx, [rax+38h]
0x18000ce24  lea     rcx, [rsp+120h+var_D0]
0x18000ce29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ce2e  lea     r8, [rsp+120h+var_D0]
0x18000ce33  mov     edx, esi
0x18000ce35  mov     rcx, rdi
0x18000ce38  mov     rax, rbx
0x18000ce3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce40  xor     edi, edi
0x18000ce42  mov     [rbp+3Fh+String1], rdi
0x18000ce46  mov     rcx, [rsp+120h+var_D0]
0x18000ce4b  mov     rax, [rcx]
0x18000ce4e  lea     rdx, [rbp+3Fh+String1]
0x18000ce52  mov     rax, [rax+38h]
0x18000ce56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce5b  mov     rcx, [rbp+47h]; this
0x18000ce5f  test    eax, eax
0x18000ce61  js      loc_18000D0B4
0x18000ce67  lea     rdx, aSubgroup; "subgroup"
0x18000ce6e  mov     rbx, [rbp+3Fh+String1]
0x18000ce72  mov     rcx, rbx; String1
0x18000ce75  call    wcscmp_0
0x18000ce7a  test    eax, eax
0x18000ce7c  jnz     loc_18000CF7B
0x18000ce82  mov     r9d, r14d
0x18000ce85  lea     r8, aLd; "%ld"
0x18000ce8c  lea     edx, [rdi+0Ah]; unsigned __int64
0x18000ce8f  lea     rcx, [rbp+3Fh+sourceString]; unsigned __int16 *
0x18000ce93  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ce98  mov     rcx, [rbp+47h]; this
0x18000ce9c  test    eax, eax
0x18000ce9e  js      loc_18000D09F
0x18000cea4  mov     [rbp+3Fh+var_B8], rdi
0x18000cea8  lea     rcx, [rbp+3Fh+var_B8]
0x18000ceac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ceb1  lea     rax, [rbp+3Fh+var_B8]
0x18000ceb5  mov     [rsp+120h+var_F0], rax
0x18000ceba  mov     [rsp+120h+var_F8], r13d
0x18000cebf  mov     eax, [rbp+3Fh+arg_20]
0x18000cec2  mov     [rsp+120h+var_100], eax; int
0x18000cec6  mov     r8, r12
0x18000cec9  mov     rdx, [rsp+120h+var_D0]
0x18000cece  mov     rcx, r15
0x18000ced1  call    ?ParseSubGroup@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseSubGroup(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18000ced6  mov     rdi, [rbp+3Fh+var_A8]
0x18000ceda  mov     rax, [rdi]
0x18000cedd  mov     r12, [rax+50h]
0x18000cee1  mov     r15, [rbp+3Fh+var_B8]
0x18000cee5  lea     rcx, [rbp+3Fh+sourceString]
0x18000cee9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ceed  xor     eax, eax
0x18000ceef  inc     rbx
0x18000cef2  cmp     [rcx+rbx*2], ax
0x18000cef6  jnz     short loc_18000CEEF
0x18000cef8  mov     eax, 0FFFFFFFFh
0x18000cefd  cmp     rbx, rax
0x18000cf00  jbe     short loc_18000CF19
0x18000cf02  mov     ebx, eax
0x18000cf04  xor     r9d, r9d; lpArguments
0x18000cf07  xor     r8d, r8d; nNumberOfArguments
0x18000cf0a  lea     edx, [r9+1]; dwExceptionFlags
0x18000cf0e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cf13  call    cs:__imp_RaiseException
0x18000cf19  lea     r9, [rbp+3Fh+string]; string
0x18000cf1d  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18000cf21  mov     edx, ebx; length
0x18000cf23  lea     rcx, [rbp+3Fh+sourceString]; sourceString
0x18000cf27  call    cs:__imp_WindowsCreateStringReference
0x18000cf2d  lea     r9, [rsp+120h+var_E0]
0x18000cf32  mov     r8, r15
0x18000cf35  mov     rdx, [rbp+3Fh+string]
0x18000cf39  mov     rcx, rdi
0x18000cf3c  mov     rax, r12
0x18000cf3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf44  mov     rcx, [rbp+47h]; this
0x18000cf48  xor     edi, edi
0x18000cf4a  test    eax, eax
0x18000cf4c  js      loc_18000D08A
0x18000cf52  inc     r14d
0x18000cf55  mov     rcx, [rbp+3Fh+var_B8]
0x18000cf59  test    rcx, rcx
0x18000cf5c  jz      short loc_18000CF6F
0x18000cf5e  mov     [rbp+3Fh+var_B8], rdi
0x18000cf62  mov     rax, [rcx]
0x18000cf65  mov     rax, [rax+10h]
0x18000cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf6e  nop
0x18000cf6f  mov     rbx, [rbp+3Fh+String1]
0x18000cf73  mov     r15, [rbp+3Fh+var_90]
0x18000cf77  mov     r12, [rbp+3Fh+var_88]
0x18000cf7b  mov     rcx, rbx; bstrString
0x18000cf7e  call    cs:__imp_SysFreeString
0x18000cf84  nop
0x18000cf85  mov     rcx, [rsp+120h+var_D0]
0x18000cf8a  test    rcx, rcx
0x18000cf8d  jz      short loc_18000CFA1
0x18000cf8f  mov     [rsp+120h+var_D0], rdi
0x18000cf94  mov     rax, [rcx]
0x18000cf97  mov     rax, [rax+10h]
0x18000cf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa0  nop
0x18000cfa1  inc     esi
0x18000cfa3  cmp     esi, [rsp+120h+var_DC]
0x18000cfa7  jl      loc_18000CE13
0x18000cfad  xor     r13d, r13d
0x18000cfb0  mov     rax, [rsp+120h+var_C0]
0x18000cfb5  mov     [rsp+120h+var_C0], r13
0x18000cfba  mov     rcx, [rbp+3Fh+var_80]
0x18000cfbe  mov     [rcx], rax
0x18000cfc1  mov     rcx, [rsp+120h+var_C8]
0x18000cfc6  test    rcx, rcx
0x18000cfc9  jz      short loc_18000CFDD
0x18000cfcb  mov     [rsp+120h+var_C8], r13
0x18000cfd0  mov     rax, [rcx]
0x18000cfd3  mov     rax, [rax+10h]
0x18000cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfdc  nop
0x18000cfdd  mov     rcx, [rbp+3Fh+var_B0]
0x18000cfe1  test    rcx, rcx
0x18000cfe4  jz      short loc_18000CFF7
0x18000cfe6  mov     [rbp+3Fh+var_B0], r13
0x18000cfea  mov     rax, [rcx]
0x18000cfed  mov     rax, [rax+10h]
0x18000cff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cff6  nop
0x18000cff7  mov     rcx, [rbp+3Fh+var_A8]
0x18000cffb  test    rcx, rcx
0x18000cffe  jz      short loc_18000D011
0x18000d000  mov     [rbp+3Fh+var_A8], r13
0x18000d004  mov     rax, [rcx]
  ... truncated ...
```
