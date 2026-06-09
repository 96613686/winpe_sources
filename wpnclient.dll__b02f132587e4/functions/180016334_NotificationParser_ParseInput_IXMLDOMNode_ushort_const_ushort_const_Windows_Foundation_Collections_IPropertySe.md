# NotificationParser::ParseInput(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180016334`
- end: `0x18001669e`
- name: `?ParseInput@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `874`
- prototype: `void __fastcall(NotificationParser *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001780c`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008fe0`
- `0x18000b440`
- `0x180016334`
- `0x180017d74`
- `0x18001b494`
- `0x18001b848`
- `0x18001d9d4`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800163fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800163fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800163e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800164e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800163e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800164e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001660d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001660d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180016514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180016514`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663c`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall NotificationParser::ParseInput(
        NotificationParser *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Foundation::Collections::IPropertySet **a5)
{
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING, struct IInspectable **); // rdi
  int v11; // edi
  struct Windows::Foundation::Collections::IPropertySet *v12; // rbx
  bool v13; // r8
  bool v14; // r9
  int v15; // edx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdi
  int v19; // ebx
  int v20; // eax
  HRESULT v21; // eax
  const unsigned __int16 *v22; // r9
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v25; // rbx
  _QWORD *v26; // rax
  int v27; // eax
  struct Windows::Foundation::Collections::IPropertySet *v28; // rax
  __int64 v29; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v30; // rcx
  int v31; // [rsp+20h] [rbp-81h]
  int v32; // [rsp+20h] [rbp-81h]
  char v33[8]; // [rsp+30h] [rbp-71h] BYREF
  __int64 v34; // [rsp+38h] [rbp-69h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v35; // [rsp+40h] [rbp-61h] BYREF
  INT32 result; // [rsp+48h] [rbp-59h] BYREF
  HSTRING string1; // [rsp+50h] [rbp-51h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v38; // [rsp+58h] [rbp-49h] BYREF
  struct IInspectable *v39; // [rsp+60h] [rbp-41h] BYREF
  __int64 v40; // [rsp+68h] [rbp-39h] BYREF
  char *v41; // [rsp+70h] [rbp-31h]
  __int64 v42; // [rsp+78h] [rbp-29h] BYREF
  int v43; // [rsp+80h] [rbp-21h]
  __int64 v44; // [rsp+88h] [rbp-19h]
  __int64 v45; // [rsp+90h] [rbp-11h]
  HSTRING string; // [rsp+98h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v35 = 0;
  v34 = 0;
  v44 = 0;
  v45 = 0;
  v40 = 0;
  LODWORD(v41) = 0;
  v33[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  NotificationParser::CreateValueSet(v8, &v35, &v34);
  NotificationParser::GetAttributes(this, a2);
  v9 = v34;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, struct IInspectable **))(*(_QWORD *)v34 + 48LL);
  v38 = (struct Windows::Foundation::Collections::IPropertySet *)&v40;
  v39 = 0;
  if ( WindowsCreateStringReference(L"type", 4u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v11 = v10(v9, string, &v39);
  v12 = v38;
  RoVariant::RoVariant((RoVariant *)&v42, v39, v13, v14);
  v15 = v43;
  v16 = *(_QWORD *)v12;
  *(_QWORD *)v12 = v42;
  v17 = *((_DWORD *)v12 + 2);
  *((_DWORD *)v12 + 2) = v15;
  if ( v16 && ((v17 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v11,
      v31);
  string1 = 0;
  v18 = v40;
  v19 = (int)v41;
  WindowsDeleteString(0);
  string1 = 0;
  if ( v19 == 7 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 152LL))(v18, &string1);
  }
  else
  {
    v20 = -2147316576;
    if ( v19 < 0 )
      v20 = v19;
  }
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v20,
      v31);
  result = 0;
  if ( WindowsCreateStringReference(L"selection", 9u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v21 = WindowsCompareStringOrdinal(string1, string, &result);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5EC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v21,
      v31);
  if ( !result )
  {
    v38 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    NotificationParser::ParseSelectionItems(this, a2, a3, v22, &v38);
    v23 = v34;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)v34 + 80LL);
    v25 = v38;
    v26 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"selections");
    v27 = v24(v23, *v26, v25, v33);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v27,
        v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  }
  NotificationParser::ResolveTextElement(this, v34, L"title", (__int64)a3);
  NotificationParser::ResolveTextElement(this, v34, L"placeHolderContent", (__int64)a3);
  NotificationParser::ResolveTextElement(this, v34, L"defaultInput", (__int64)a3);
  v28 = v35;
  v35 = 0;
  *a5 = v28;
  WindowsDeleteString(string1);
  string1 = 0;
  if ( v40 && (((_DWORD)v41 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v40 + 16LL))();
  SysFreeString(0);
  v29 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v30 + 16LL))(v30);
  }
}

```

## disassembly

```asm
0x180016334  mov     [rsp-8+arg_18], rbx
0x180016339  push    rbp
0x18001633a  push    rsi
0x18001633b  push    rdi
0x18001633c  push    r12
0x18001633e  push    r13
0x180016340  push    r14
0x180016342  push    r15
0x180016344  lea     rbp, [rsp-1Fh]
0x180016349  sub     rsp, 0C0h
0x180016350  mov     rax, cs:__security_cookie
0x180016357  xor     rax, rsp
0x18001635a  mov     [rbp+4Fh+var_38], rax
0x18001635e  mov     r15, r8
0x180016361  mov     rsi, rdx
0x180016364  mov     r14, rcx
0x180016367  mov     r12, [rbp+4Fh+arg_20]
0x18001636b  xor     r13d, r13d
0x18001636e  mov     [rbp+4Fh+var_B0], r13
0x180016372  mov     [rbp+4Fh+var_B8], r13
0x180016376  mov     [rbp+4Fh+var_68], r13
0x18001637a  mov     [rbp+4Fh+var_60], r13
0x18001637e  mov     [rbp+4Fh+var_88], r13
0x180016382  mov     dword ptr [rbp+4Fh+var_80], r13d
0x180016386  mov     [rbp+4Fh+var_C0], r13b
0x18001638a  lea     rcx, [rbp+4Fh+var_B8]
0x18001638e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016393  lea     rcx, [rbp+4Fh+var_B0]
0x180016397  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001639c  lea     r8, [rbp+4Fh+var_B8]
0x1800163a0  lea     rdx, [rbp+4Fh+var_B0]
0x1800163a4  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x1800163a9  mov     r8, [rbp+4Fh+var_B8]
0x1800163ad  mov     rdx, rsi
0x1800163b0  mov     rcx, r14
0x1800163b3  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x1800163b8  mov     rbx, [rbp+4Fh+var_B8]
0x1800163bc  mov     rax, [rbx]
0x1800163bf  mov     rdi, [rax+30h]
0x1800163c3  lea     rax, [rbp+4Fh+var_88]
0x1800163c7  mov     [rbp+4Fh+var_98], rax
0x1800163cb  mov     [rbp+4Fh+var_90], r13
0x1800163cf  lea     r9, [rbp+4Fh+string]; string
0x1800163d3  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800163d7  lea     edx, [r13+4]; length
0x1800163db  lea     rcx, aType; "type"
0x1800163e2  call    cs:__imp_WindowsCreateStringReference
0x1800163e8  test    eax, eax
0x1800163ea  jns     short loc_180016401
0x1800163ec  xor     r9d, r9d; lpArguments
0x1800163ef  xor     r8d, r8d; nNumberOfArguments
0x1800163f2  lea     edx, [r13+1]; dwExceptionFlags
0x1800163f6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800163fb  call    cs:__imp_RaiseException
0x180016401  lea     r8, [rbp+4Fh+var_90]
0x180016405  mov     rdx, [rbp+4Fh+string]
0x180016409  mov     rcx, rbx
0x18001640c  mov     rax, rdi
0x18001640f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016414  mov     edi, eax
0x180016416  mov     rbx, [rbp+4Fh+var_98]
0x18001641a  mov     rdx, [rbp+4Fh+var_90]; struct IInspectable *
0x18001641e  lea     rcx, [rbp+4Fh+var_78]; this
0x180016422  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180016427  mov     rcx, [rbp+4Fh+var_78]
0x18001642b  mov     edx, [rbp+4Fh+var_70]
0x18001642e  mov     r8, [rbx]
0x180016431  mov     [rbx], rcx
0x180016434  mov     eax, [rbx+8]
0x180016437  mov     [rbx+8], edx
0x18001643a  test    r8, r8
0x18001643d  jz      short loc_180016459
0x18001643f  add     eax, 0FFFFFFFDh
0x180016442  test    eax, 0FFFFFFFBh
0x180016447  jnz     short loc_180016459
0x180016449  mov     rax, [r8]
0x18001644c  mov     rcx, r8
0x18001644f  mov     rax, [rax+10h]
0x180016453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016458  nop
0x180016459  mov     rcx, [rbp+57h]; this
0x18001645d  test    edi, edi
0x18001645f  jns     short loc_180016476
0x180016461  mov     r9d, edi; char *
0x180016464  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001646b  mov     edx, 5E4h; void *
0x180016470  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016476  mov     [rbp+4Fh+string1], r13
0x18001647a  mov     rdi, [rbp+4Fh+var_88]
0x18001647e  mov     ebx, dword ptr [rbp+4Fh+var_80]
0x180016481  xor     ecx, ecx; string
0x180016483  call    cs:__imp_WindowsDeleteString
0x180016489  mov     [rbp+4Fh+string1], r13
0x18001648d  cmp     ebx, 7
0x180016490  jz      short loc_18001649E
0x180016492  mov     eax, 80028CA0h
0x180016497  test    ebx, ebx
0x180016499  cmovs   eax, ebx
0x18001649c  jmp     short loc_1800164B4
0x18001649e  mov     rax, [rdi]
0x1800164a1  lea     rdx, [rbp+4Fh+string1]
0x1800164a5  mov     rcx, rdi
0x1800164a8  mov     rax, [rax+98h]
0x1800164af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164b4  mov     rcx, [rbp+57h]; this
0x1800164b8  test    eax, eax
0x1800164ba  jns     short loc_1800164D1
0x1800164bc  mov     r9d, eax; char *
0x1800164bf  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800164c6  mov     edx, 5E8h; void *
0x1800164cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800164d1  mov     [rbp+4Fh+result], r13d
0x1800164d5  lea     r9, [rbp+4Fh+string]; string
0x1800164d9  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800164dd  mov     edx, 9; length
0x1800164e2  lea     rcx, aSelection; "selection"
0x1800164e9  call    cs:__imp_WindowsCreateStringReference
0x1800164ef  test    eax, eax
0x1800164f1  jns     short loc_180016508
0x1800164f3  xor     r9d, r9d; lpArguments
0x1800164f6  xor     r8d, r8d; nNumberOfArguments
0x1800164f9  lea     edx, [r9+1]; dwExceptionFlags
0x1800164fd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016502  call    cs:__imp_RaiseException
0x180016508  lea     r8, [rbp+4Fh+result]; result
0x18001650c  mov     rdx, [rbp+4Fh+string]; string2
0x180016510  mov     rcx, [rbp+4Fh+string1]; string1
0x180016514  call    cs:__imp_WindowsCompareStringOrdinal
0x18001651a  mov     rcx, [rbp+57h]; this
0x18001651e  test    eax, eax
0x180016520  jns     short loc_180016537
0x180016522  mov     r9d, eax; char *
0x180016525  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001652c  mov     edx, 5ECh; void *
0x180016531  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016537  cmp     [rbp+4Fh+result], r13d
0x18001653b  jnz     short loc_1800165BB
0x18001653d  mov     [rbp+4Fh+var_98], r13
0x180016541  lea     rcx, [rbp+4Fh+var_98]
0x180016545  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001654a  lea     rax, [rbp+4Fh+var_98]
0x18001654e  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180016553  mov     r8, r15; unsigned __int16 *
0x180016556  mov     rdx, rsi; struct IXMLDOMNode *
0x180016559  mov     rcx, r14; this
0x18001655c  call    ?ParseSelectionItems@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseSelectionItems(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x180016561  mov     rsi, [rbp+4Fh+var_B8]
0x180016565  mov     rax, [rsi]
0x180016568  mov     rdi, [rax+50h]
0x18001656c  mov     rbx, [rbp+4Fh+var_98]
0x180016570  lea     rdx, aSelections; "selections"
0x180016577  lea     rcx, [rbp+4Fh+string]; string
0x18001657b  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x180016580  lea     r9, [rbp+4Fh+var_C0]
0x180016584  mov     r8, rbx
0x180016587  mov     rdx, [rax]
0x18001658a  mov     rcx, rsi
0x18001658d  mov     rax, rdi
0x180016590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016595  mov     rcx, [rbp+57h]; this
0x180016599  test    eax, eax
0x18001659b  jns     short loc_1800165B2
0x18001659d  mov     r9d, eax; char *
0x1800165a0  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800165a7  mov     edx, 5F3h; void *
0x1800165ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800165b2  lea     rcx, [rbp+4Fh+var_98]
0x1800165b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800165bb  mov     r9, r15
0x1800165be  lea     r8, aTitle; "title"
0x1800165c5  mov     rdx, [rbp+4Fh+var_B8]
0x1800165c9  mov     rcx, r14
0x1800165cc  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x1800165d1  mov     r9, r15
0x1800165d4  lea     r8, aPlaceholdercon; "placeHolderContent"
0x1800165db  mov     rdx, [rbp+4Fh+var_B8]
0x1800165df  mov     rcx, r14
0x1800165e2  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x1800165e7  mov     r9, r15
0x1800165ea  lea     r8, aDefaultinput; "defaultInput"
0x1800165f1  mov     rdx, [rbp+4Fh+var_B8]
0x1800165f5  mov     rcx, r14
0x1800165f8  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x1800165fd  mov     rax, [rbp+4Fh+var_B0]
0x180016601  mov     [rbp+4Fh+var_B0], r13
0x180016605  mov     [r12], rax
0x180016609  mov     rcx, [rbp+4Fh+string1]; string
0x18001660d  call    cs:__imp_WindowsDeleteString
0x180016613  mov     [rbp+4Fh+string1], r13
0x180016617  mov     rcx, [rbp+4Fh+var_88]
0x18001661b  test    rcx, rcx
0x18001661e  jz      short loc_18001663A
0x180016620  mov     eax, dword ptr [rbp+4Fh+var_80]
0x180016623  add     eax, 0FFFFFFFDh
0x180016626  test    eax, 0FFFFFFFBh
0x18001662b  jnz     short loc_18001663A
0x18001662d  mov     rax, [rcx]
0x180016630  mov     rax, [rax+10h]
0x180016634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016639  nop
0x18001663a  xor     ecx, ecx; bstrString
0x18001663c  call    cs:__imp_SysFreeString
0x180016642  nop
0x180016643  mov     rcx, [rbp+4Fh+var_B8]
0x180016647  test    rcx, rcx
0x18001664a  jz      short loc_18001665D
0x18001664c  mov     [rbp+4Fh+var_B8], r13
0x180016650  mov     rax, [rcx]
0x180016653  mov     rax, [rax+10h]
0x180016657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665c  nop
0x18001665d  mov     rcx, [rbp+4Fh+var_B0]
0x180016661  test    rcx, rcx
0x180016664  jz      short loc_180016677
0x180016666  mov     [rbp+4Fh+var_B0], r13
0x18001666a  mov     rax, [rcx]
0x18001666d  mov     rax, [rax+10h]
0x180016671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016676  nop
0x180016677  mov     rcx, [rbp+4Fh+var_38]
0x18001667b  xor     rcx, rsp; StackCookie
0x18001667e  call    __security_check_cookie
0x180016683  mov     rbx, [rsp+0F0h+arg_18]
0x18001668b  add     rsp, 0C0h
0x180016692  pop     r15
0x180016694  pop     r14
0x180016696  pop     r13
0x180016698  pop     r12
0x18001669a  pop     rdi
0x18001669b  pop     rsi
0x18001669c  pop     rbp
0x18001669d  retn
```
