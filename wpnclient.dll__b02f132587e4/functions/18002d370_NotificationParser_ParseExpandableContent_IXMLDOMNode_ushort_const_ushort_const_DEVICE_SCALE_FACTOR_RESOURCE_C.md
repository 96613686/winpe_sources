# NotificationParser::ParseExpandableContent(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18002d370`
- end: `0x18002d736`
- name: `?ParseExpandableContent@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x180008fe0`
- `0x18000dc30`
- `0x18001b848`
- `0x18001ff00`
- `0x18002d370`
- `0x18002d73c`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d451`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d438`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d61c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d61c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NotificationParser::ParseExpandableContent(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, _BYTE *); // r14
  __int64 v13; // rsi
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r14d
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  OLECHAR *v24; // rbx
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rax
  int v32; // [rsp+20h] [rbp-B1h]
  _BYTE v33[4]; // [rsp+40h] [rbp-91h] BYREF
  int v34; // [rsp+44h] [rbp-8Dh] BYREF
  __int64 v35; // [rsp+48h] [rbp-89h] BYREF
  __int64 v36; // [rsp+50h] [rbp-81h] BYREF
  __int64 v37; // [rsp+58h] [rbp-79h] BYREF
  __int64 v38; // [rsp+60h] [rbp-71h] BYREF
  __int64 v39; // [rsp+68h] [rbp-69h] BYREF
  __int64 v40; // [rsp+70h] [rbp-61h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-59h] BYREF
  __int64 v42; // [rsp+80h] [rbp-51h] BYREF
  __int64 v43; // [rsp+88h] [rbp-49h]
  __int64 *v44; // [rsp+90h] [rbp-41h]
  HSTRING string; // [rsp+98h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-31h] BYREF
  unsigned __int16 v47[12]; // [rsp+B8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v43 = a3;
  v44 = a1;
  v39 = 0;
  v38 = 0;
  v42 = 0;
  v37 = 0;
  v36 = 0;
  v33[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  NotificationParser::CreateValueSet(v9, &v39, &v38);
  NotificationParser::GetAttributes(a1, a2, v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  NotificationParser::CreateValueSet(v10, &v42, &v37);
  v11 = v38;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v38 + 80LL);
  v13 = v37;
  if ( WindowsCreateStringReference(L"expandableItems", 0xFu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v14 = v12(v11, string, v13, v33);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x507,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v14,
      v32);
  v34 = 0;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  v16 = v15(a2, &v36);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v16,
      v32);
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 64LL))(v36, &v34);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      v32);
  v18 = v34;
  if ( v34 >= 3 )
  {
    v18 = 3;
    v34 = 3;
  }
  v19 = 0;
  if ( v18 > 0 )
  {
    do
    {
      v35 = 0;
      v20 = v36;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      v22 = v21(v20, v19, &v35);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x514,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v22,
          v32);
      String1 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v35 + 56LL))(v35, &String1);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x517,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v23,
          v32);
      v24 = String1;
      if ( !wcscmp_0(String1, L"expandableItem") )
      {
        v25 = StringCchPrintfW(v47, 0xAu, L"%ld", v19);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x51B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v25,
            v32);
        v40 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        v32 = a5;
        NotificationParser::ParseExpandableItem(v44, v35, v43);
        v26 = v37;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v37 + 80LL);
        v28 = v40;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&string, v47);
        v29 = v27(v26, string, v28, v33);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x51F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v29,
            a5);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        v24 = String1;
      }
      SysFreeString(v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      ++v19;
    }
    while ( (int)v19 < v34 );
  }
  v30 = v39;
  v39 = 0;
  *a7 = v30;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
}

```

## disassembly

```asm
0x18002d370  mov     [rsp-8+arg_18], rbx
0x18002d375  push    rbp
0x18002d376  push    rsi
0x18002d377  push    rdi
0x18002d378  push    r12
0x18002d37a  push    r13
0x18002d37c  push    r14
0x18002d37e  push    r15
0x18002d380  lea     rbp, [rsp-0Fh]
0x18002d385  sub     rsp, 0E0h
0x18002d38c  mov     rax, cs:__security_cookie
0x18002d393  xor     rax, rsp
0x18002d396  mov     [rbp+3Fh+var_40], rax
0x18002d39a  mov     [rbp+3Fh+var_88], r8
0x18002d39e  mov     rdi, rdx
0x18002d3a1  mov     rbx, rcx
0x18002d3a4  mov     [rbp+3Fh+var_80], rcx
0x18002d3a8  mov     r13, [rbp+3Fh+arg_30]
0x18002d3ac  xor     r15d, r15d
0x18002d3af  mov     [rbp+3Fh+var_A8], r15
0x18002d3b3  mov     [rbp+3Fh+var_B0], r15
0x18002d3b7  mov     [rbp+3Fh+var_90], r15
0x18002d3bb  mov     [rbp+3Fh+var_B8], r15
0x18002d3bf  mov     [rsp+110h+var_C0], r15
0x18002d3c4  mov     [rsp+110h+var_D0], r15b
0x18002d3c9  lea     rcx, [rbp+3Fh+var_B0]
0x18002d3cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d3d2  lea     rcx, [rbp+3Fh+var_A8]
0x18002d3d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d3db  lea     r8, [rbp+3Fh+var_B0]
0x18002d3df  lea     rdx, [rbp+3Fh+var_A8]
0x18002d3e3  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002d3e8  mov     r8, [rbp+3Fh+var_B0]
0x18002d3ec  mov     rdx, rdi
0x18002d3ef  mov     rcx, rbx
0x18002d3f2  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18002d3f7  lea     rcx, [rbp+3Fh+var_B8]
0x18002d3fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d400  lea     rcx, [rbp+3Fh+var_90]
0x18002d404  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d409  lea     r8, [rbp+3Fh+var_B8]
0x18002d40d  lea     rdx, [rbp+3Fh+var_90]
0x18002d411  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002d416  mov     rbx, [rbp+3Fh+var_B0]
0x18002d41a  mov     rax, [rbx]
0x18002d41d  mov     r14, [rax+50h]
0x18002d421  mov     rsi, [rbp+3Fh+var_B8]
0x18002d425  lea     r9, [rbp+3Fh+string]; string
0x18002d429  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18002d42d  lea     edx, [r15+0Fh]; length
0x18002d431  lea     rcx, aExpandableitem; "expandableItems"
0x18002d438  call    cs:__imp_WindowsCreateStringReference
0x18002d43e  test    eax, eax
0x18002d440  jns     short loc_18002D457
0x18002d442  xor     r9d, r9d; lpArguments
0x18002d445  xor     r8d, r8d; nNumberOfArguments
0x18002d448  lea     edx, [r15+1]; dwExceptionFlags
0x18002d44c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002d451  call    cs:__imp_RaiseException
0x18002d457  lea     r9, [rsp+110h+var_D0]
0x18002d45c  mov     r8, rsi
0x18002d45f  mov     rdx, [rbp+3Fh+string]
0x18002d463  mov     rcx, rbx
0x18002d466  mov     rax, r14
0x18002d469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d46e  mov     rcx, [rbp+47h]; this
0x18002d472  test    eax, eax
0x18002d474  js      loc_18002D6CD
0x18002d47a  mov     [rsp+110h+var_CC], r15d
0x18002d47f  mov     rax, [rdi]
0x18002d482  mov     rbx, [rax+60h]
0x18002d486  lea     rcx, [rsp+110h+var_C0]
0x18002d48b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d490  lea     rdx, [rsp+110h+var_C0]
0x18002d495  mov     rcx, rdi
0x18002d498  mov     rax, rbx
0x18002d49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4a0  mov     rcx, [rbp+47h]; this
0x18002d4a4  test    eax, eax
0x18002d4a6  js      loc_18002D6E2
0x18002d4ac  mov     rcx, [rsp+110h+var_C0]
0x18002d4b1  mov     rax, [rcx]
0x18002d4b4  lea     rdx, [rsp+110h+var_CC]
0x18002d4b9  mov     rax, [rax+40h]
0x18002d4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4c2  mov     rcx, [rbp+47h]; this
0x18002d4c6  test    eax, eax
0x18002d4c8  js      loc_18002D6F7
0x18002d4ce  mov     eax, [rsp+110h+var_CC]
0x18002d4d2  cmp     eax, 3
0x18002d4d5  jl      short loc_18002D4E0
0x18002d4d7  mov     eax, 3
0x18002d4dc  mov     [rsp+110h+var_CC], eax
0x18002d4e0  mov     r14d, r15d
0x18002d4e3  test    eax, eax
0x18002d4e5  jle     loc_18002D63E
0x18002d4eb  mov     r15d, [rbp+3Fh+arg_28]
0x18002d4ef  mov     r12d, [rbp+3Fh+arg_20]
0x18002d4f3  mov     [rsp+110h+var_C8], 0
0x18002d4fc  mov     rdi, [rsp+110h+var_C0]
0x18002d501  mov     rax, [rdi]
0x18002d504  mov     rbx, [rax+38h]
0x18002d508  lea     rcx, [rsp+110h+var_C8]
0x18002d50d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d512  lea     r8, [rsp+110h+var_C8]
0x18002d517  mov     edx, r14d
0x18002d51a  mov     rcx, rdi
0x18002d51d  mov     rax, rbx
0x18002d520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d525  mov     rcx, [rbp+47h]; this
0x18002d529  test    eax, eax
0x18002d52b  js      loc_18002D6B8
0x18002d531  mov     [rbp+3Fh+String1], 0
0x18002d539  mov     rcx, [rsp+110h+var_C8]
0x18002d53e  mov     rax, [rcx]
0x18002d541  lea     rdx, [rbp+3Fh+String1]
0x18002d545  mov     rax, [rax+38h]
0x18002d549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d54e  mov     rcx, [rbp+47h]; this
0x18002d552  test    eax, eax
0x18002d554  js      loc_18002D6A3
0x18002d55a  lea     rdx, aExpandableitem_0; "expandableItem"
0x18002d561  mov     rbx, [rbp+3Fh+String1]
0x18002d565  mov     rcx, rbx; String1
0x18002d568  call    wcscmp_0
0x18002d56d  test    eax, eax
0x18002d56f  jnz     loc_18002D619
0x18002d575  mov     r9d, r14d
0x18002d578  lea     r8, aLd; "%ld"
0x18002d57f  lea     edx, [rax+0Ah]; unsigned __int64
0x18002d582  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18002d586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d58b  mov     rcx, [rbp+47h]; this
0x18002d58f  test    eax, eax
0x18002d591  js      loc_18002D721
0x18002d597  mov     [rbp+3Fh+var_A0], 0
0x18002d59f  lea     rcx, [rbp+3Fh+var_A0]
0x18002d5a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d5a8  lea     rax, [rbp+3Fh+var_A0]
0x18002d5ac  mov     [rsp+110h+var_E0], rax
0x18002d5b1  mov     [rsp+110h+var_E8], r15d
0x18002d5b6  mov     [rsp+110h+var_F0], r12d; int
0x18002d5bb  mov     r8, [rbp+3Fh+var_88]
0x18002d5bf  mov     rdx, [rsp+110h+var_C8]
0x18002d5c4  mov     rcx, [rbp+3Fh+var_80]
0x18002d5c8  call    ?ParseExpandableItem@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseExpandableItem(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18002d5cd  mov     rsi, [rbp+3Fh+var_B8]
0x18002d5d1  mov     rax, [rsi]
0x18002d5d4  mov     rdi, [rax+50h]
0x18002d5d8  mov     rbx, [rbp+3Fh+var_A0]
0x18002d5dc  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x18002d5e0  lea     rcx, [rbp+3Fh+string]; this
0x18002d5e4  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002d5e9  lea     r9, [rsp+110h+var_D0]
0x18002d5ee  mov     r8, rbx
0x18002d5f1  mov     rdx, [rbp+3Fh+string]
0x18002d5f5  mov     rcx, rsi
0x18002d5f8  mov     rax, rdi
0x18002d5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d600  mov     rcx, [rbp+47h]; this
0x18002d604  test    eax, eax
0x18002d606  js      loc_18002D70C
0x18002d60c  lea     rcx, [rbp+3Fh+var_A0]
0x18002d610  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d615  mov     rbx, [rbp+3Fh+String1]
0x18002d619  mov     rcx, rbx; bstrString
0x18002d61c  call    cs:__imp_SysFreeString
0x18002d622  nop
0x18002d623  lea     rcx, [rsp+110h+var_C8]
0x18002d628  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d62d  inc     r14d
0x18002d630  cmp     r14d, [rsp+110h+var_CC]
0x18002d635  jl      loc_18002D4F3
0x18002d63b  xor     r15d, r15d
0x18002d63e  mov     rax, [rbp+3Fh+var_A8]
0x18002d642  mov     [rbp+3Fh+var_A8], r15
0x18002d646  mov     [r13+0], rax
0x18002d64a  lea     rcx, [rsp+110h+var_C0]
0x18002d64f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d654  nop
0x18002d655  lea     rcx, [rbp+3Fh+var_B8]
0x18002d659  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d65e  nop
0x18002d65f  lea     rcx, [rbp+3Fh+var_90]
0x18002d663  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d668  nop
0x18002d669  lea     rcx, [rbp+3Fh+var_B0]
0x18002d66d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d672  nop
0x18002d673  lea     rcx, [rbp+3Fh+var_A8]
0x18002d677  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d67c  mov     rcx, [rbp+3Fh+var_40]
0x18002d680  xor     rcx, rsp; StackCookie
0x18002d683  call    __security_check_cookie
0x18002d688  mov     rbx, [rsp+110h+arg_18]
0x18002d690  add     rsp, 0E0h
0x18002d697  pop     r15
0x18002d699  pop     r14
0x18002d69b  pop     r13
0x18002d69d  pop     r12
0x18002d69f  pop     rdi
0x18002d6a0  pop     rsi
0x18002d6a1  pop     rbp
0x18002d6a2  retn
0x18002d6a3  mov     r9d, eax; char *
0x18002d6a6  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d6ad  mov     edx, 517h; void *
0x18002d6b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d6b8  mov     r9d, eax; char *
0x18002d6bb  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d6c2  mov     edx, 514h; void *
0x18002d6c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d6cd  mov     r9d, eax; char *
0x18002d6d0  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d6d7  mov     edx, 507h; void *
0x18002d6dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d6e2  mov     r9d, eax; char *
0x18002d6e5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d6ec  mov     edx, 50Bh; void *
0x18002d6f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d6f7  mov     r9d, eax; char *
0x18002d6fa  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d701  mov     edx, 50Ch; void *
0x18002d706  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d70c  mov     r9d, eax; char *
0x18002d70f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d716  mov     edx, 51Fh; void *
0x18002d71b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d721  mov     r9d, eax; char *
0x18002d724  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002d72b  mov     edx, 51Bh; void *
0x18002d730  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
