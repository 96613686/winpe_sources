# NotificationParser::ParseActions(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18001780c`
- end: `0x180017d19`
- name: `?ParseActions@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x180008fe0`
- `0x18000dc30`
- `0x180013f00`
- `0x180014550`
- `0x180016334`
- `0x18001780c`
- `0x18001b848`
- `0x18001ff00`
- `0x18002d280`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180017ae4`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall NotificationParser::ParseActions(
        NotificationParser *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v13; // rbx
  HSTRING *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v19; // rbx
  HSTRING *v20; // rax
  int v21; // eax
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r15d
  unsigned int v26; // r12d
  unsigned int i; // r14d
  __int64 v28; // rdi
  void (__fastcall *v29)(__int64, _QWORD, struct IXMLDOMNode **); // rbx
  int v30; // eax
  wchar_t *v31; // rbx
  int v32; // eax
  const unsigned __int16 *v33; // r9
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v36; // rbx
  int v37; // eax
  __int64 *v38; // rcx
  OLECHAR *v39; // rcx
  __int64 v40; // rax
  int v42; // eax
  __int64 v43; // r9
  __int64 v44; // rbx
  __int64 v45; // rsi
  __int64 (__fastcall *v46)(__int64, HSTRING, __int64, _BYTE *); // rdi
  int v47; // eax
  int v48; // [rsp+20h] [rbp-D1h]
  _BYTE v49[4]; // [rsp+40h] [rbp-B1h] BYREF
  int v50; // [rsp+44h] [rbp-ADh] BYREF
  struct IXMLDOMNode *v51; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v52; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v53; // [rsp+58h] [rbp-99h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-91h] BYREF
  __int64 v55; // [rsp+68h] [rbp-89h] BYREF
  __int64 v56; // [rsp+70h] [rbp-81h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v57; // [rsp+78h] [rbp-79h] BYREF
  __int64 v58; // [rsp+80h] [rbp-71h] BYREF
  __int64 v59; // [rsp+88h] [rbp-69h] BYREF
  __int64 v60; // [rsp+90h] [rbp-61h] BYREF
  __int64 v61; // [rsp+98h] [rbp-59h] BYREF
  unsigned __int16 *v62; // [rsp+A0h] [rbp-51h]
  NotificationParser *v63; // [rsp+A8h] [rbp-49h]
  __int64 *v64; // [rsp+B0h] [rbp-41h]
  HSTRING string[4]; // [rsp+B8h] [rbp-39h] BYREF
  unsigned __int16 v66[12]; // [rsp+D8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  v62 = a3;
  v63 = a1;
  v64 = a7;
  v56 = 0;
  v52 = 0;
  v61 = 0;
  v60 = 0;
  v59 = 0;
  v58 = 0;
  v55 = 0;
  v49[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  NotificationParser::CreateValueSet(v9, &v56, &v52);
  NotificationParser::GetAttributes((__int64 *)a1, a2, v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  NotificationParser::CreateValueSet(v10, &v61, &v60);
  v11 = v52;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v52 + 80LL);
  v13 = v61;
  v14 = Windows::Internal::StringReference::StringReference(string, L"inputs");
  v15 = v12(v11, *v14, v13, v49);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x594,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  NotificationParser::CreateValueSet(v16, &v59, &v58);
  v17 = v52;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v52 + 80LL);
  v19 = v59;
  v20 = Windows::Internal::StringReference::StringReference(string, L"actions");
  v21 = v18(v17, *v20, v19, v49);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x599,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v21,
      v48);
  v50 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v23 = v22(a2, &v55);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v23,
      v48);
  v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 64LL))(v55, &v50);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v24,
      v48);
  v25 = 0;
  v26 = 0;
  for ( i = 0; (int)i < v50; ++i )
  {
    v51 = 0;
    v28 = v55;
    v29 = *(void (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v55 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v51);
    v29(v28, i, &v51);
    String1 = 0;
    v30 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v51->lpVtbl->get_nodeName)(v51, &String1);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v30,
        v48);
    v31 = String1;
    if ( !wcscmp_0(String1, L"input") )
    {
      v32 = StringCchPrintfW(v66, 0xAu, L"%ld", v25);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B1,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v32,
          v48);
      v57 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v57);
      NotificationParser::ParseInput(v63, v51, v62, v33, &v57);
      v34 = v60;
      v35 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)v60 + 80LL);
      v36 = v57;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v66);
      v37 = v35(v34, string[0], v36, v49);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v37,
          v48);
      ++v25;
      v38 = (__int64 *)&v57;
    }
    else
    {
      if ( wcscmp_0(v31, L"action") )
        goto LABEL_12;
      v42 = StringCchPrintfW(v66, 0xAu, L"%ld", v26);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5BB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v42,
          v48);
      v53 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      NotificationParser::ParseAction((__int64 *)v63, (__int64)v51, v62, v43, a5, a6, &v53);
      v44 = v53;
      if ( !v53 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        v39 = String1;
        goto LABEL_13;
      }
      v45 = v58;
      v46 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v58 + 80LL);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v66);
      v47 = v46(v45, string[0], v44, v49);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5C9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v47,
          v48);
      ++v26;
      v38 = &v53;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38);
    v31 = String1;
LABEL_12:
    v39 = v31;
LABEL_13:
    SysFreeString(v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v51);
  }
  v40 = v56;
  v56 = 0;
  *v64 = v40;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
}

```

## disassembly

```asm
0x18001780c  mov     [rsp-8+arg_18], rbx
0x180017811  push    rbp
0x180017812  push    rsi
0x180017813  push    rdi
0x180017814  push    r12
0x180017816  push    r13
0x180017818  push    r14
0x18001781a  push    r15
0x18001781c  lea     rbp, [rsp-0Fh]
0x180017821  sub     rsp, 100h
0x180017828  mov     rax, cs:__security_cookie
0x18001782f  xor     rax, rsp
0x180017832  mov     [rbp+3Fh+var_40], rax
0x180017836  mov     [rbp+3Fh+var_90], r8
0x18001783a  mov     r14, rdx
0x18001783d  mov     rbx, rcx
0x180017840  mov     [rbp+3Fh+var_88], rcx
0x180017844  mov     rax, [rbp+3Fh+arg_30]
0x180017848  mov     [rbp+3Fh+var_80], rax
0x18001784c  xor     r15d, r15d
0x18001784f  mov     [rsp+130h+var_C0], r15
0x180017854  mov     [rsp+130h+var_E0], r15
0x180017859  mov     [rbp+3Fh+var_98], r15
0x18001785d  mov     [rbp+3Fh+var_A0], r15
0x180017861  mov     [rbp+3Fh+var_A8], r15
0x180017865  mov     [rbp+3Fh+var_B0], r15
0x180017869  mov     [rsp+130h+var_C8], r15
0x18001786e  mov     [rsp+130h+var_F0], r15b
0x180017873  lea     rcx, [rsp+130h+var_E0]
0x180017878  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001787d  lea     rcx, [rsp+130h+var_C0]
0x180017882  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017887  lea     r8, [rsp+130h+var_E0]
0x18001788c  lea     rdx, [rsp+130h+var_C0]
0x180017891  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180017896  mov     r8, [rsp+130h+var_E0]
0x18001789b  mov     rdx, r14
0x18001789e  mov     rcx, rbx
0x1800178a1  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x1800178a6  lea     rcx, [rbp+3Fh+var_A0]
0x1800178aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800178af  lea     rcx, [rbp+3Fh+var_98]
0x1800178b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800178b8  lea     r8, [rbp+3Fh+var_A0]
0x1800178bc  lea     rdx, [rbp+3Fh+var_98]
0x1800178c0  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x1800178c5  mov     rsi, [rsp+130h+var_E0]
0x1800178ca  mov     rax, [rsi]
0x1800178cd  mov     rdi, [rax+50h]
0x1800178d1  mov     rbx, [rbp+3Fh+var_98]
0x1800178d5  lea     rdx, aInputs; "inputs"
0x1800178dc  lea     rcx, [rbp+3Fh+string]; string
0x1800178e0  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x1800178e5  lea     r9, [rsp+130h+var_F0]
0x1800178ea  mov     r8, rbx
0x1800178ed  mov     rdx, [rax]
0x1800178f0  mov     rcx, rsi
0x1800178f3  mov     rax, rdi
0x1800178f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178fb  mov     rcx, [rbp+47h]; this
0x1800178ff  test    eax, eax
0x180017901  js      loc_180017C86
0x180017907  lea     rcx, [rbp+3Fh+var_B0]
0x18001790b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017910  lea     rcx, [rbp+3Fh+var_A8]
0x180017914  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017919  lea     r8, [rbp+3Fh+var_B0]
0x18001791d  lea     rdx, [rbp+3Fh+var_A8]
0x180017921  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180017926  mov     rsi, [rsp+130h+var_E0]
0x18001792b  mov     rax, [rsi]
0x18001792e  mov     rdi, [rax+50h]
0x180017932  mov     rbx, [rbp+3Fh+var_A8]
0x180017936  lea     rdx, aActions; "actions"
0x18001793d  lea     rcx, [rbp+3Fh+string]; string
0x180017941  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x180017946  lea     r9, [rsp+130h+var_F0]
0x18001794b  mov     r8, rbx
0x18001794e  mov     rdx, [rax]
0x180017951  mov     rcx, rsi
0x180017954  mov     rax, rdi
0x180017957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001795c  mov     rcx, [rbp+47h]; this
0x180017960  xor     esi, esi
0x180017962  test    eax, eax
0x180017964  js      loc_180017C9B
0x18001796a  mov     [rsp+130h+var_EC], esi
0x18001796e  mov     rax, [r14]
0x180017971  mov     rbx, [rax+60h]
0x180017975  lea     rcx, [rsp+130h+var_C8]
0x18001797a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001797f  lea     rdx, [rsp+130h+var_C8]
0x180017984  mov     rcx, r14
0x180017987  mov     rax, rbx
0x18001798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798f  mov     rcx, [rbp+47h]; this
0x180017993  test    eax, eax
0x180017995  js      loc_180017CB0
0x18001799b  mov     rcx, [rsp+130h+var_C8]
0x1800179a0  mov     rax, [rcx]
0x1800179a3  lea     rdx, [rsp+130h+var_EC]
0x1800179a8  mov     rax, [rax+40h]
0x1800179ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179b1  mov     rcx, [rbp+47h]; this
0x1800179b5  test    eax, eax
0x1800179b7  js      loc_180017CC5
0x1800179bd  mov     r15d, esi
0x1800179c0  mov     r12d, esi
0x1800179c3  mov     r14d, esi
0x1800179c6  cmp     [rsp+130h+var_EC], esi
0x1800179ca  jle     loc_180017B03
0x1800179d0  mov     r13d, [rbp+3Fh+arg_28]
0x1800179d4  mov     [rsp+130h+var_E8], rsi
0x1800179d9  mov     rdi, [rsp+130h+var_C8]
0x1800179de  mov     rax, [rdi]
0x1800179e1  mov     rbx, [rax+38h]
0x1800179e5  lea     rcx, [rsp+130h+var_E8]
0x1800179ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800179ef  lea     r8, [rsp+130h+var_E8]
0x1800179f4  mov     edx, r14d
0x1800179f7  mov     rcx, rdi
0x1800179fa  mov     rax, rbx
0x1800179fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a02  mov     [rsp+130h+String1], rsi
0x180017a07  mov     rcx, [rsp+130h+var_E8]
0x180017a0c  mov     rax, [rcx]
0x180017a0f  lea     rdx, [rsp+130h+String1]
0x180017a14  mov     rax, [rax+38h]
0x180017a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a1d  mov     rcx, [rbp+47h]; this
0x180017a21  test    eax, eax
0x180017a23  js      loc_180017C71
0x180017a29  lea     rdx, aInput; "input"
0x180017a30  mov     rbx, [rsp+130h+String1]
0x180017a35  mov     rcx, rbx; String1
0x180017a38  call    wcscmp_0
0x180017a3d  test    eax, eax
0x180017a3f  jnz     loc_180017B83
0x180017a45  mov     r9d, r15d
0x180017a48  lea     r8, aLd; "%ld"
0x180017a4f  lea     edx, [rax+0Ah]; unsigned __int64
0x180017a52  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x180017a56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017a5b  mov     rcx, [rbp+47h]; this
0x180017a5f  test    eax, eax
0x180017a61  js      loc_180017CEF
0x180017a67  mov     [rbp+3Fh+var_B8], rsi
0x180017a6b  lea     rcx, [rbp+3Fh+var_B8]
0x180017a6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017a74  lea     rax, [rbp+3Fh+var_B8]
0x180017a78  mov     [rsp+130h+var_110], rax; int
0x180017a7d  mov     r8, [rbp+3Fh+var_90]; unsigned __int16 *
0x180017a81  mov     rdx, [rsp+130h+var_E8]; struct IXMLDOMNode *
0x180017a86  mov     rcx, [rbp+3Fh+var_88]; this
0x180017a8a  call    ?ParseInput@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseInput(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x180017a8f  mov     rsi, [rbp+3Fh+var_A0]
0x180017a93  mov     rax, [rsi]
0x180017a96  mov     rdi, [rax+50h]
0x180017a9a  mov     rbx, [rbp+3Fh+var_B8]
0x180017a9e  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x180017aa2  lea     rcx, [rbp+3Fh+string]; this
0x180017aa6  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180017aab  lea     r9, [rsp+130h+var_F0]
0x180017ab0  mov     r8, rbx
0x180017ab3  mov     rdx, [rbp+3Fh+string]
0x180017ab7  mov     rcx, rsi
0x180017aba  mov     rax, rdi
0x180017abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ac2  mov     rcx, [rbp+47h]; this
0x180017ac6  xor     esi, esi
0x180017ac8  test    eax, eax
0x180017aca  js      loc_180017CDA
0x180017ad0  inc     r15d
0x180017ad3  lea     rcx, [rbp+3Fh+var_B8]
0x180017ad7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017adc  mov     rbx, [rsp+130h+String1]
0x180017ae1  mov     rcx, rbx; bstrString
0x180017ae4  call    cs:__imp_SysFreeString
0x180017aea  nop
0x180017aeb  lea     rcx, [rsp+130h+var_E8]
0x180017af0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017af5  inc     r14d
0x180017af8  cmp     r14d, [rsp+130h+var_EC]
0x180017afd  jl      loc_1800179D4
0x180017b03  mov     rax, [rsp+130h+var_C0]
0x180017b08  mov     [rsp+130h+var_C0], rsi
0x180017b0d  mov     rcx, [rbp+3Fh+var_80]
0x180017b11  mov     [rcx], rax
0x180017b14  lea     rcx, [rsp+130h+var_C8]
0x180017b19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b1e  nop
0x180017b1f  lea     rcx, [rbp+3Fh+var_B0]
0x180017b23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b28  nop
0x180017b29  lea     rcx, [rbp+3Fh+var_A8]
0x180017b2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b32  nop
0x180017b33  lea     rcx, [rbp+3Fh+var_A0]
0x180017b37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b3c  nop
0x180017b3d  lea     rcx, [rbp+3Fh+var_98]
0x180017b41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b46  nop
0x180017b47  lea     rcx, [rsp+130h+var_E0]
0x180017b4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b51  nop
0x180017b52  lea     rcx, [rsp+130h+var_C0]
0x180017b57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b5c  mov     rcx, [rbp+3Fh+var_40]
0x180017b60  xor     rcx, rsp; StackCookie
0x180017b63  call    __security_check_cookie
0x180017b68  mov     rbx, [rsp+130h+arg_18]
0x180017b70  add     rsp, 100h
0x180017b77  pop     r15
0x180017b79  pop     r14
0x180017b7b  pop     r13
0x180017b7d  pop     r12
0x180017b7f  pop     rdi
0x180017b80  pop     rsi
0x180017b81  pop     rbp
0x180017b82  retn
0x180017b83  lea     rdx, aAction; "action"
0x180017b8a  mov     rcx, rbx; String1
0x180017b8d  call    wcscmp_0
0x180017b92  test    eax, eax
0x180017b94  jnz     loc_180017AE1
0x180017b9a  mov     r9d, r12d
0x180017b9d  lea     r8, aLd; "%ld"
0x180017ba4  lea     edx, [rax+0Ah]; unsigned __int64
0x180017ba7  lea     rcx, [rbp+3Fh+var_58]; unsigned __int16 *
0x180017bab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017bb0  mov     rcx, [rbp+47h]; this
0x180017bb4  test    eax, eax
0x180017bb6  js      loc_180017C5C
0x180017bbc  mov     [rsp+130h+var_D8], rsi
0x180017bc1  lea     rcx, [rsp+130h+var_D8]
0x180017bc6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bcb  lea     rax, [rsp+130h+var_D8]
0x180017bd0  mov     [rsp+130h+var_100], rax
0x180017bd5  mov     [rsp+130h+var_108], r13d
0x180017bda  mov     eax, [rbp+3Fh+arg_20]
0x180017bdd  mov     dword ptr [rsp+130h+var_110], eax; int
0x180017be1  mov     r8, [rbp+3Fh+var_90]
0x180017be5  mov     rdx, [rsp+130h+var_E8]
0x180017bea  mov     rcx, [rbp+3Fh+var_88]
0x180017bee  call    ?ParseAction@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseAction(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x180017bf3  mov     rbx, [rsp+130h+var_D8]
0x180017bf8  test    rbx, rbx
0x180017bfb  jz      short loc_180017C47
0x180017bfd  mov     rsi, [rbp+3Fh+var_B0]
0x180017c01  mov     rax, [rsi]
0x180017c04  mov     rdi, [rax+50h]
0x180017c08  lea     rdx, [rbp+3Fh+var_58]; unsigned __int16 *
0x180017c0c  lea     rcx, [rbp+3Fh+string]; this
0x180017c10  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180017c15  lea     r9, [rsp+130h+var_F0]
0x180017c1a  mov     r8, rbx
0x180017c1d  mov     rdx, [rbp+3Fh+string]
0x180017c21  mov     rcx, rsi
0x180017c24  mov     rax, rdi
0x180017c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c2c  mov     rcx, [rbp+47h]; this
0x180017c30  xor     esi, esi
0x180017c32  test    eax, eax
0x180017c34  js      loc_180017D04
0x180017c3a  inc     r12d
0x180017c3d  lea     rcx, [rsp+130h+var_D8]
0x180017c42  jmp     loc_180017AD7
0x180017c47  lea     rcx, [rsp+130h+var_D8]
0x180017c4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c51  nop
0x180017c52  mov     rcx, [rsp+130h+String1]
0x180017c57  jmp     loc_180017AE4
0x180017c5c  mov     r9d, eax; char *
0x180017c5f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017c66  mov     edx, 5BBh; void *
0x180017c6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c71  mov     r9d, eax; char *
0x180017c74  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017c7b  mov     edx, 5ACh; void *
0x180017c80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c86  mov     r9d, eax; char *
0x180017c89  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017c90  mov     edx, 594h; void *
0x180017c95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c9b  mov     r9d, eax; char *
0x180017c9e  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017ca5  mov     edx, 599h; void *
0x180017caa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017cb0  mov     r9d, eax; char *
0x180017cb3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017cba  mov     edx, 59Eh; void *
0x180017cbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017cc5  mov     r9d, eax; char *
0x180017cc8  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017ccf  mov     edx, 5A0h; void *
0x180017cd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017cda  mov     r9d, eax; char *
0x180017cdd  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180017ce4  mov     edx, 5B6h; void *
  ... truncated ...
```
