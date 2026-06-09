# NotificationParser::ParseSubGroup(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180009380`
- end: `0x180009889`
- name: `?ParseSubGroup@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1289`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cb68`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x180008fe0`
- `0x180009380`
- `0x180009890`
- `0x18000a460`
- `0x18000dc30`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009633`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000944d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000944d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009647`
- `OLEAUT32!__imp_SysFreeString` at `0x180009735`
- `OLEAUT32!__imp_SysFreeString` at `0x180009735`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NotificationParser::ParseSubGroup(
        __int64 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 *v8; // r15
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, char *); // r14
  __int64 v13; // rsi
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r14d
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, struct IXMLDOMNode **); // rbx
  int v22; // eax
  int v23; // eax
  wchar_t *v24; // rbx
  const unsigned __int16 *v25; // r9
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, char *); // r15
  struct Windows::Foundation::Collections::IPropertySet *v28; // rsi
  unsigned __int64 v29; // rbx
  int v30; // eax
  struct Windows::Foundation::Collections::IPropertySet *v31; // rcx
  __int64 v32; // r9
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, char *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v35; // rbx
  int v36; // eax
  struct IXMLDOMNode *v37; // rcx
  __int64 result; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  int v44; // [rsp+20h] [rbp-C1h]
  char v45[8]; // [rsp+40h] [rbp-A1h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v46; // [rsp+48h] [rbp-99h] BYREF
  int v47; // [rsp+50h] [rbp-91h] BYREF
  struct IXMLDOMNode *v48; // [rsp+58h] [rbp-89h] BYREF
  __int64 v49; // [rsp+60h] [rbp-81h] BYREF
  __int64 v50; // [rsp+68h] [rbp-79h] BYREF
  __int64 v51; // [rsp+70h] [rbp-71h] BYREF
  __int64 v52; // [rsp+78h] [rbp-69h] BYREF
  __int64 v53; // [rsp+80h] [rbp-61h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-59h] BYREF
  unsigned __int16 *v55; // [rsp+90h] [rbp-51h]
  __int64 *v56; // [rsp+98h] [rbp-49h]
  __int64 *v57; // [rsp+A0h] [rbp-41h]
  HSTRING string; // [rsp+A8h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-31h] BYREF
  HSTRING v60; // [rsp+C8h] [rbp-19h] BYREF
  HSTRING_HEADER v61; // [rsp+D0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v55 = a3;
  v8 = a1;
  v56 = a1;
  v57 = a7;
  v52 = 0;
  v51 = 0;
  v53 = 0;
  v50 = 0;
  v49 = 0;
  v45[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  NotificationParser::CreateValueSet(v9, &v52, &v51);
  NotificationParser::GetAttributes(v8, a2, v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  NotificationParser::CreateValueSet(v10, &v53, &v50);
  v11 = v51;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v51 + 80LL);
  v13 = v53;
  if ( WindowsCreateStringReference(L"items", 5u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v14 = v12(v11, string, v13, v45);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v14,
      v44);
  v47 = 0;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v16 = v15(a2, &v49);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4CD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v16,
      v44);
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v47);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4CF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      v44);
  v18 = 0;
  if ( v47 > 0 )
  {
    while ( 1 )
    {
      v19 = StringCchPrintfW((unsigned __int16 *)&string, 0xAu, L"%ld", v18);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D5,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v19,
          v44);
      v48 = 0;
      v20 = v49;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v49 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      v22 = v21(v20, v18, &v48);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v22,
          v44);
      String1 = 0;
      v23 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v48->lpVtbl->get_nodeName)(v48, &String1);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4DD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v23,
          v44);
      v24 = String1;
      if ( !wcscmp_0(String1, L"text") )
        break;
      if ( !wcscmp_0(v24, L"image") )
      {
        v46 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        NotificationParser::ParseImage(v8, (__int64)v48, v55, v32, a5, a6, (__int64 *)&v46);
        v33 = v50;
        v34 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)v50 + 80LL);
        v35 = v46;
        Windows::Internal::StringReference::_ConstructorHelper(
          (Windows::Internal::StringReference *)&v60,
          (const unsigned __int16 *)&string);
        v36 = v34(v33, v60, v35, v45);
        if ( v36 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4EB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v36,
            v44);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        goto LABEL_25;
      }
LABEL_26:
      SysFreeString(v24);
      v37 = v48;
      if ( v48 )
      {
        v48 = 0;
        ((void (__fastcall *)(struct IXMLDOMNode *))v37->lpVtbl->Release)(v37);
      }
      if ( (int)++v18 >= v47 )
        goto LABEL_29;
    }
    v46 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    NotificationParser::ParseText((NotificationParser *)v8, v48, v55, v25, &v46);
    v26 = v50;
    v27 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)v50 + 80LL);
    v28 = v46;
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)&string + v29) );
    if ( v29 > 0xFFFFFFFF )
    {
      LODWORD(v29) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference((PCWSTR)&string, v29, &v61, &v60);
    v30 = v27(v26, v60, v28, v45);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v30,
        v44);
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v8 = v56;
LABEL_25:
    v24 = String1;
    goto LABEL_26;
  }
LABEL_29:
  result = v52;
  v52 = 0;
  *v57 = result;
  v39 = v49;
  if ( v49 )
  {
    v49 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v50;
  if ( v50 )
  {
    v50 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v53;
  if ( v53 )
  {
    v53 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v51;
  if ( v51 )
  {
    v51 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v52;
  if ( v52 )
  {
    v52 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  return result;
}

```

## disassembly

```asm
0x180009380  mov     [rsp-8+arg_18], rbx
0x180009385  push    rbp
0x180009386  push    rsi
0x180009387  push    rdi
0x180009388  push    r12
0x18000938a  push    r13
0x18000938c  push    r14
0x18000938e  push    r15
0x180009390  lea     rbp, [rsp-0Fh]
0x180009395  sub     rsp, 0F0h
0x18000939c  mov     rax, cs:__security_cookie
0x1800093a3  xor     rax, rsp
0x1800093a6  mov     [rbp+3Fh+var_38], rax
0x1800093aa  mov     [rbp+3Fh+var_90], r8
0x1800093ae  mov     rdi, rdx
0x1800093b1  mov     r15, rcx
0x1800093b4  mov     [rbp+3Fh+var_88], rcx
0x1800093b8  mov     rax, [rbp+3Fh+arg_30]
0x1800093bc  mov     [rbp+3Fh+var_80], rax
0x1800093c0  xor     r12d, r12d
0x1800093c3  mov     [rbp+3Fh+var_A8], r12
0x1800093c7  mov     [rbp+3Fh+var_B0], r12
0x1800093cb  mov     [rbp+3Fh+var_A0], r12
0x1800093cf  mov     [rbp+3Fh+var_B8], r12
0x1800093d3  mov     [rsp+120h+var_C0], r12
0x1800093d8  mov     [rsp+120h+var_E0], r12b
0x1800093dd  lea     rcx, [rbp+3Fh+var_B0]
0x1800093e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800093e6  lea     rcx, [rbp+3Fh+var_A8]
0x1800093ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800093ef  lea     r8, [rbp+3Fh+var_B0]
0x1800093f3  lea     rdx, [rbp+3Fh+var_A8]
0x1800093f7  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x1800093fc  mov     r8, [rbp+3Fh+var_B0]
0x180009400  mov     rdx, rdi
0x180009403  mov     rcx, r15
0x180009406  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18000940b  lea     rcx, [rbp+3Fh+var_B8]
0x18000940f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009414  lea     rcx, [rbp+3Fh+var_A0]
0x180009418  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000941d  lea     r8, [rbp+3Fh+var_B8]
0x180009421  lea     rdx, [rbp+3Fh+var_A0]
0x180009425  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18000942a  mov     rbx, [rbp+3Fh+var_B0]
0x18000942e  mov     rax, [rbx]
0x180009431  mov     r14, [rax+50h]
0x180009435  mov     rsi, [rbp+3Fh+var_A0]
0x180009439  lea     r9, [rbp+3Fh+string]; string
0x18000943d  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x180009441  lea     edx, [r12+5]; length
0x180009446  lea     rcx, aItems; "items"
0x18000944d  call    cs:__imp_WindowsCreateStringReference
0x180009453  test    eax, eax
0x180009455  jns     short loc_18000946D
0x180009457  xor     r9d, r9d; lpArguments
0x18000945a  xor     r8d, r8d; nNumberOfArguments
0x18000945d  lea     edx, [r12+1]; dwExceptionFlags
0x180009462  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009467  call    cs:__imp_RaiseException
0x18000946d  lea     r9, [rsp+120h+var_E0]
0x180009472  mov     r8, rsi
0x180009475  mov     rdx, [rbp+3Fh+string]
0x180009479  mov     rcx, rbx
0x18000947c  mov     rax, r14
0x18000947f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009484  mov     rcx, [rbp+47h]; this
0x180009488  xor     esi, esi
0x18000948a  test    eax, eax
0x18000948c  jns     short loc_1800094A3
0x18000948e  mov     r9d, eax; char *
0x180009491  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009498  mov     edx, 4C8h; void *
0x18000949d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800094a3  mov     [rsp+120h+var_D0], esi
0x1800094a7  mov     rax, [rdi]
0x1800094aa  mov     rbx, [rax+60h]
0x1800094ae  lea     rcx, [rsp+120h+var_C0]
0x1800094b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800094b8  lea     rdx, [rsp+120h+var_C0]
0x1800094bd  mov     rcx, rdi
0x1800094c0  mov     rax, rbx
0x1800094c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c8  mov     rcx, [rbp+47h]; this
0x1800094cc  test    eax, eax
0x1800094ce  jns     short loc_1800094E5
0x1800094d0  mov     r9d, eax; char *
0x1800094d3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800094da  mov     edx, 4CDh; void *
0x1800094df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800094e5  mov     rcx, [rsp+120h+var_C0]
0x1800094ea  mov     rax, [rcx]
0x1800094ed  lea     rdx, [rsp+120h+var_D0]
0x1800094f2  mov     rax, [rax+40h]
0x1800094f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fb  mov     rcx, [rbp+47h]; this
0x1800094ff  test    eax, eax
0x180009501  jns     short loc_180009518
0x180009503  mov     r9d, eax; char *
0x180009506  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000950d  mov     edx, 4CFh; void *
0x180009512  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009518  mov     r14d, esi
0x18000951b  cmp     [rsp+120h+var_D0], esi
0x18000951f  jle     loc_180009766
0x180009525  mov     r12d, [rbp+3Fh+arg_28]
0x180009529  mov     r13d, [rbp+3Fh+arg_20]
0x18000952d  mov     r9d, r14d
0x180009530  lea     r8, aLd; "%ld"
0x180009537  mov     edx, 0Ah; unsigned __int64
0x18000953c  lea     rcx, [rbp+3Fh+string]; unsigned __int16 *
0x180009540  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009545  mov     rcx, [rbp+47h]; this
0x180009549  test    eax, eax
0x18000954b  js      loc_180009874
0x180009551  mov     [rsp+120h+var_C8], rsi
0x180009556  mov     rdi, [rsp+120h+var_C0]
0x18000955b  mov     rax, [rdi]
0x18000955e  mov     rbx, [rax+38h]
0x180009562  lea     rcx, [rsp+120h+var_C8]
0x180009567  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000956c  lea     r8, [rsp+120h+var_C8]
0x180009571  mov     edx, r14d
0x180009574  mov     rcx, rdi
0x180009577  mov     rax, rbx
0x18000957a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957f  mov     rcx, [rbp+47h]; this
0x180009583  test    eax, eax
0x180009585  js      loc_18000985F
0x18000958b  mov     [rbp+3Fh+String1], rsi
0x18000958f  mov     rcx, [rsp+120h+var_C8]
0x180009594  mov     rax, [rcx]
0x180009597  lea     rdx, [rbp+3Fh+String1]
0x18000959b  mov     rax, [rax+38h]
0x18000959f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a4  mov     rcx, [rbp+47h]; this
0x1800095a8  test    eax, eax
0x1800095aa  js      loc_18000984A
0x1800095b0  lea     rdx, aText; "text"
0x1800095b7  mov     rbx, [rbp+3Fh+String1]
0x1800095bb  mov     rcx, rbx; String1
0x1800095be  call    wcscmp_0
0x1800095c3  test    eax, eax
0x1800095c5  jnz     loc_180009697
0x1800095cb  mov     [rsp+120h+var_D8], rsi
0x1800095d0  lea     rcx, [rsp+120h+var_D8]
0x1800095d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800095da  lea     rax, [rsp+120h+var_D8]
0x1800095df  mov     [rsp+120h+var_100], rax; int
0x1800095e4  mov     r8, [rbp+3Fh+var_90]; unsigned __int16 *
0x1800095e8  mov     rdx, [rsp+120h+var_C8]; struct IXMLDOMNode *
0x1800095ed  mov     rcx, r15; this
0x1800095f0  call    ?ParseText@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseText(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x1800095f5  mov     rdi, [rbp+3Fh+var_B8]
0x1800095f9  mov     rax, [rdi]
0x1800095fc  mov     r15, [rax+50h]
0x180009600  mov     rsi, [rsp+120h+var_D8]
0x180009605  lea     rcx, [rbp+3Fh+string]
0x180009609  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000960d  xor     eax, eax
0x18000960f  inc     rbx
0x180009612  cmp     [rcx+rbx*2], ax
0x180009616  jnz     short loc_18000960F
0x180009618  mov     eax, 0FFFFFFFFh
0x18000961d  cmp     rbx, rax
0x180009620  jbe     short loc_180009639
0x180009622  mov     ebx, eax
0x180009624  xor     r9d, r9d; lpArguments
0x180009627  xor     r8d, r8d; nNumberOfArguments
0x18000962a  lea     edx, [r9+1]; dwExceptionFlags
0x18000962e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009633  call    cs:__imp_RaiseException
0x180009639  lea     r9, [rbp+3Fh+var_58]; string
0x18000963d  lea     r8, [rbp+3Fh+var_50]; hstringHeader
0x180009641  mov     edx, ebx; length
0x180009643  lea     rcx, [rbp+3Fh+string]; sourceString
0x180009647  call    cs:__imp_WindowsCreateStringReference
0x18000964d  lea     r9, [rsp+120h+var_E0]
0x180009652  mov     r8, rsi
0x180009655  mov     rdx, [rbp+3Fh+var_58]
0x180009659  mov     rcx, rdi
0x18000965c  mov     rax, r15
0x18000965f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009664  mov     rcx, [rbp+47h]; this
0x180009668  xor     esi, esi
0x18000966a  test    eax, eax
0x18000966c  js      loc_180009820
0x180009672  mov     rcx, [rsp+120h+var_D8]
0x180009677  test    rcx, rcx
0x18000967a  jz      short loc_18000968E
0x18000967c  mov     [rsp+120h+var_D8], rsi
0x180009681  mov     rax, [rcx]
0x180009684  mov     rax, [rax+10h]
0x180009688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968d  nop
0x18000968e  mov     r15, [rbp+3Fh+var_88]
0x180009692  jmp     loc_18000972E
0x180009697  lea     rdx, aImage; "image"
0x18000969e  mov     rcx, rbx; String1
0x1800096a1  call    wcscmp_0
0x1800096a6  test    eax, eax
0x1800096a8  jnz     loc_180009732
0x1800096ae  mov     [rsp+120h+var_D8], rsi
0x1800096b3  lea     rcx, [rsp+120h+var_D8]
0x1800096b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800096bd  lea     rax, [rsp+120h+var_D8]
0x1800096c2  mov     [rsp+120h+var_F0], rax
0x1800096c7  mov     [rsp+120h+var_F8], r12d
0x1800096cc  mov     dword ptr [rsp+120h+var_100], r13d; int
0x1800096d1  mov     r8, [rbp+3Fh+var_90]
0x1800096d5  mov     rdx, [rsp+120h+var_C8]
0x1800096da  mov     rcx, r15
0x1800096dd  call    ?ParseImage@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseImage(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x1800096e2  mov     rsi, [rbp+3Fh+var_B8]
0x1800096e6  mov     rax, [rsi]
0x1800096e9  mov     rdi, [rax+50h]
0x1800096ed  mov     rbx, [rsp+120h+var_D8]
0x1800096f2  lea     rdx, [rbp+3Fh+string]; unsigned __int16 *
0x1800096f6  lea     rcx, [rbp+3Fh+var_58]; this
0x1800096fa  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800096ff  lea     r9, [rsp+120h+var_E0]
0x180009704  mov     r8, rbx
0x180009707  mov     rdx, [rbp+3Fh+var_58]
0x18000970b  mov     rcx, rsi
0x18000970e  mov     rax, rdi
0x180009711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009716  mov     rcx, [rbp+47h]; this
0x18000971a  xor     esi, esi
0x18000971c  test    eax, eax
0x18000971e  js      loc_180009835
0x180009724  lea     rcx, [rsp+120h+var_D8]
0x180009729  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000972e  mov     rbx, [rbp+3Fh+String1]
0x180009732  mov     rcx, rbx; bstrString
0x180009735  call    cs:__imp_SysFreeString
0x18000973b  nop
0x18000973c  mov     rcx, [rsp+120h+var_C8]
0x180009741  test    rcx, rcx
0x180009744  jz      short loc_180009758
0x180009746  mov     [rsp+120h+var_C8], rsi
0x18000974b  mov     rax, [rcx]
0x18000974e  mov     rax, [rax+10h]
0x180009752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009757  nop
0x180009758  inc     r14d
0x18000975b  cmp     r14d, [rsp+120h+var_D0]
0x180009760  jl      loc_18000952D
0x180009766  mov     rax, [rbp+3Fh+var_A8]
0x18000976a  mov     [rbp+3Fh+var_A8], rsi
0x18000976e  mov     rcx, [rbp+3Fh+var_80]
0x180009772  mov     [rcx], rax
0x180009775  mov     rcx, [rsp+120h+var_C0]
0x18000977a  test    rcx, rcx
0x18000977d  jz      short loc_180009791
0x18000977f  mov     [rsp+120h+var_C0], rsi
0x180009784  mov     rax, [rcx]
0x180009787  mov     rax, [rax+10h]
0x18000978b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009790  nop
0x180009791  mov     rcx, [rbp+3Fh+var_B8]
0x180009795  test    rcx, rcx
0x180009798  jz      short loc_1800097AB
0x18000979a  mov     [rbp+3Fh+var_B8], rsi
0x18000979e  mov     rax, [rcx]
0x1800097a1  mov     rax, [rax+10h]
0x1800097a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097aa  nop
0x1800097ab  mov     rcx, [rbp+3Fh+var_A0]
0x1800097af  test    rcx, rcx
0x1800097b2  jz      short loc_1800097C5
0x1800097b4  mov     [rbp+3Fh+var_A0], rsi
0x1800097b8  mov     rax, [rcx]
0x1800097bb  mov     rax, [rax+10h]
0x1800097bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097c4  nop
0x1800097c5  mov     rcx, [rbp+3Fh+var_B0]
0x1800097c9  test    rcx, rcx
0x1800097cc  jz      short loc_1800097DF
0x1800097ce  mov     [rbp+3Fh+var_B0], rsi
0x1800097d2  mov     rax, [rcx]
0x1800097d5  mov     rax, [rax+10h]
0x1800097d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097de  nop
0x1800097df  mov     rcx, [rbp+3Fh+var_A8]
0x1800097e3  test    rcx, rcx
0x1800097e6  jz      short loc_1800097F9
0x1800097e8  mov     [rbp+3Fh+var_A8], rsi
0x1800097ec  mov     rax, [rcx]
0x1800097ef  mov     rax, [rax+10h]
0x1800097f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f8  nop
0x1800097f9  mov     rcx, [rbp+3Fh+var_38]
0x1800097fd  xor     rcx, rsp; StackCookie
0x180009800  call    __security_check_cookie
0x180009805  mov     rbx, [rsp+120h+arg_18]
0x18000980d  add     rsp, 0F0h
0x180009814  pop     r15
0x180009816  pop     r14
0x180009818  pop     r13
0x18000981a  pop     r12
  ... truncated ...
```
