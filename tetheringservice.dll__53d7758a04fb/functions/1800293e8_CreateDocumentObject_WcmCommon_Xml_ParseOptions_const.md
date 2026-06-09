# CreateDocumentObject(WcmCommon::Xml::ParseOptions const &)

- ea: `0x1800293e8`
- end: `0x1800295f9`
- name: `?CreateDocumentObject@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBUParseOptions@Xml@WcmCommon@@@Z`
- size: `529`
- prototype: `LPVOID *__fastcall(LPVOID *ppv, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`

## callees

- `0x180028c8c`
- `0x1800293e8`
- `0x180029a5c`
- `0x18003127c`
- `0x180031290`
- `0x180031448`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800294d6`
- `OLEAUT32!__imp_VariantClear` at `0x18002951c`
- `OLEAUT32!__imp_VariantClear` at `0x180029582`
- `OLEAUT32!__imp_VariantClear` at `0x1800294d6`
- `OLEAUT32!__imp_VariantClear` at `0x18002951c`
- `OLEAUT32!__imp_VariantClear` at `0x180029582`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029434`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029434`

## pseudocode

```c
LPVOID *__fastcall CreateDocumentObject(LPVOID *ppv, _BYTE *a2)
{
  HRESULT Instance; // eax
  struct IUnknown *v5; // rdi
  int v6; // eax
  struct IUnknown *v7; // rdi
  int v8; // eax
  LPVOID v9; // rdi
  _bstr_t *v10; // rax
  LPVOID v11; // rdi
  _bstr_t *v12; // rax
  LPVOID v13; // rdi
  _bstr_t *v14; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  char v17; // [rsp+90h] [rbp+40h] BYREF

  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               0x17u,
               &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
               ppv);
  if ( Instance < 0 )
    _com_raise_error(Instance, 0);
  v5 = (struct IUnknown *)*ppv;
  if ( !*ppv )
    goto LABEL_18;
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v5->lpVtbl[21].QueryInterface)(*ppv, 0);
  if ( v6 < 0 )
    _com_issue_errorex(v6, v5, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v7 = (struct IUnknown *)*ppv;
  if ( !*ppv )
    goto LABEL_18;
  v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v7->lpVtbl[22].Release)(*ppv, 0);
  if ( v8 < 0 )
    _com_issue_errorex(v8, v7, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v9 = *ppv;
  if ( !*ppv )
    _com_issue_error(-2147467261);
  pvarg.vt = 2;
  pvarg.iVal = -1;
  v10 = _bstr_t::_bstr_t((_bstr_t *)&v17, L"NewParser");
  MSXML2::IXMLDOMDocument2::setProperty(v9, v10, &pvarg);
  VariantClear(&pvarg);
  if ( !*a2 )
  {
    v11 = *ppv;
    if ( !*ppv )
      _com_issue_error(-2147467261);
    pvarg.vt = 2;
    pvarg.iVal = 0;
    v12 = _bstr_t::_bstr_t((_bstr_t *)&v17, L"ProhibitDTD");
    MSXML2::IXMLDOMDocument2::setProperty(v11, v12, &pvarg);
    VariantClear(&pvarg);
  }
  if ( a2[1] )
  {
    if ( *ppv )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppv + 576LL))(*ppv, 0xFFFFFFFFLL);
      goto LABEL_13;
    }
LABEL_18:
    _com_issue_error(-2147467261);
  }
LABEL_13:
  if ( a2[2] )
  {
    v13 = *ppv;
    if ( !*ppv )
      _com_issue_error(-2147467261);
    pvarg.vt = 2;
    pvarg.iVal = -1;
    v14 = _bstr_t::_bstr_t((_bstr_t *)&v17, L"PopulateElementDefaultValues");
    MSXML2::IXMLDOMDocument2::setProperty(v13, v14, &pvarg);
    VariantClear(&pvarg);
  }
  return ppv;
}

```

## disassembly

```asm
0x1800293e8  mov     [rsp-28h+arg_8], rbx
0x1800293ed  mov     [rsp-28h+arg_0], rcx
0x1800293f2  push    rbp
0x1800293f3  push    rsi
0x1800293f4  push    rdi
0x1800293f5  push    r12
0x1800293f7  push    r15
0x1800293f9  mov     rbp, rsp
0x1800293fc  sub     rsp, 50h
0x180029400  mov     rsi, rdx
0x180029403  mov     rbx, rcx
0x180029406  mov     [rbp+var_20], 0
0x18002940d  mov     [rbp+var_20], 1
0x180029414  mov     qword ptr [rcx], 0
0x18002941b  mov     [rsp+50h+ppv], rcx; ppv
0x180029420  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180029427  xor     edx, edx; pUnkOuter
0x180029429  lea     r8d, [rdx+17h]; dwClsContext
0x18002942d  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180029434  call    cs:__imp_CoCreateInstance
0x18002943a  test    eax, eax
0x18002943c  js      loc_1800295B5
0x180029442  mov     rdi, [rbx]
0x180029445  test    rdi, rdi
0x180029448  jz      loc_1800295AA
0x18002944e  mov     rax, [rdi]
0x180029451  xor     edx, edx
0x180029453  mov     rcx, rdi
0x180029456  mov     rax, [rax+1F8h]
0x18002945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029462  test    eax, eax
0x180029464  js      loc_1800295BF
0x18002946a  mov     rdi, [rbx]
0x18002946d  test    rdi, rdi
0x180029470  jz      loc_1800295AA
0x180029476  mov     rax, [rdi]
0x180029479  xor     edx, edx
0x18002947b  mov     rcx, rdi
0x18002947e  mov     rax, [rax+220h]
0x180029485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002948a  test    eax, eax
0x18002948c  js      loc_1800295D1
0x180029492  mov     rdi, [rbx]
0x180029495  test    rdi, rdi
0x180029498  jz      loc_18002959F
0x18002949e  mov     r12d, 2
0x1800294a4  mov     word ptr [rbp+pvarg], r12w
0x1800294a9  or      r15d, 0FFFFFFFFh
0x1800294ad  mov     word ptr [rbp+pvarg+8], r15w
0x1800294b2  lea     rdx, aNewparser; "NewParser"
0x1800294b9  lea     rcx, [rbp+arg_10]; this
0x1800294bd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800294c2  lea     r8, [rbp+pvarg]
0x1800294c6  mov     rdx, rax
0x1800294c9  mov     rcx, rdi
0x1800294cc  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x1800294d1  nop
0x1800294d2  lea     rcx, [rbp+pvarg]; pvarg
0x1800294d6  call    cs:__imp_VariantClear
0x1800294dc  cmp     byte ptr [rsi], 0
0x1800294df  jnz     short loc_180029522
0x1800294e1  mov     rdi, [rbx]
0x1800294e4  test    rdi, rdi
0x1800294e7  jz      loc_1800295E3
0x1800294ed  mov     word ptr [rbp+pvarg], r12w
0x1800294f2  xor     eax, eax
0x1800294f4  mov     word ptr [rbp+pvarg+8], ax
0x1800294f8  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1800294ff  lea     rcx, [rbp+arg_10]; this
0x180029503  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029508  lea     r8, [rbp+pvarg]
0x18002950c  mov     rdx, rax
0x18002950f  mov     rcx, rdi
0x180029512  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x180029517  nop
0x180029518  lea     rcx, [rbp+pvarg]; pvarg
0x18002951c  call    cs:__imp_VariantClear
0x180029522  cmp     byte ptr [rsi+1], 0
0x180029526  jz      short loc_180029542
0x180029528  mov     rcx, [rbx]
0x18002952b  test    rcx, rcx
0x18002952e  jz      short loc_1800295AA
0x180029530  mov     rax, [rcx]
0x180029533  mov     edx, r15d
0x180029536  mov     rax, [rax+240h]
0x18002953d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029542  cmp     byte ptr [rsi+2], 0
0x180029546  jz      short loc_180029588
0x180029548  mov     rdi, [rbx]
0x18002954b  test    rdi, rdi
0x18002954e  jz      loc_1800295EE
0x180029554  mov     word ptr [rbp+pvarg], r12w
0x180029559  mov     word ptr [rbp+pvarg+8], r15w
0x18002955e  lea     rdx, aPopulateelemen; "PopulateElementDefaultValues"
0x180029565  lea     rcx, [rbp+arg_10]; this
0x180029569  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002956e  lea     r8, [rbp+pvarg]
0x180029572  mov     rdx, rax
0x180029575  mov     rcx, rdi
0x180029578  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x18002957d  nop
0x18002957e  lea     rcx, [rbp+pvarg]; pvarg
0x180029582  call    cs:__imp_VariantClear
0x180029588  mov     rax, rbx
0x18002958b  mov     rbx, [rsp+50h+arg_8]
0x180029593  add     rsp, 50h
0x180029597  pop     r15
0x180029599  pop     r12
0x18002959b  pop     rdi
0x18002959c  pop     rsi
0x18002959d  pop     rbp
0x18002959e  retn
0x18002959f  mov     ecx, 80004003h; int
0x1800295a4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800295aa  mov     ecx, 80004003h; int
0x1800295af  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800295b5  xor     edx, edx; struct IErrorInfo *
0x1800295b7  mov     ecx, eax; int
0x1800295b9  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800295bf  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1800295c6  mov     rdx, rdi; struct IUnknown *
0x1800295c9  mov     ecx, eax; int
0x1800295cb  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x1800295d1  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1800295d8  mov     rdx, rdi; struct IUnknown *
0x1800295db  mov     ecx, eax; int
0x1800295dd  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x1800295e3  mov     ecx, 80004003h; int
0x1800295e8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800295ee  mov     ecx, 80004003h; int
0x1800295f3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
