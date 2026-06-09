# CAdReader::PopulateCollectionFromList(ATL::CComObject<CFsrmCollection> *,bool)

- ea: `0x18001671c`
- end: `0x180016d20`
- name: `?PopulateCollectionFromList@CAdReader@@AEAAXPEAV?$CComObject@VCFsrmCollection@@@ATL@@_N@Z`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014c40`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x1800125c0`
- `0x180014ed4`
- `0x18001671c`
- `0x18001791c`
- `0x18006febc`
- `0x1800700b8`
- `0x180072598`
- `0x180073a80`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001687b`
- `ole32!CoTaskMemFree` at `0x180016a28`
- `ole32!CoTaskMemFree` at `0x180016aec`
- `ole32!CoTaskMemFree` at `0x18001687b`
- `ole32!CoTaskMemFree` at `0x180016a28`
- `ole32!CoTaskMemFree` at `0x180016aec`
- `ole32!CoCreateInstance` at `0x18001699a`
- `ole32!CoCreateInstance` at `0x18001699a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800168ed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800168ed`
- `OLEAUT32!__imp_SysFreeString` at `0x180016921`
- `OLEAUT32!__imp_SysFreeString` at `0x180016921`
- `OLEAUT32!__imp_VariantInit` at `0x1800167c2`
- `OLEAUT32!__imp_VariantInit` at `0x1800169b9`
- `OLEAUT32!__imp_VariantInit` at `0x1800167c2`
- `OLEAUT32!__imp_VariantInit` at `0x1800169b9`
- `OLEAUT32!__imp_VariantClear` at `0x1800168c3`
- `OLEAUT32!__imp_VariantClear` at `0x180016a05`
- `OLEAUT32!__imp_VariantClear` at `0x180016a70`
- `OLEAUT32!__imp_VariantClear` at `0x180016ad9`
- `OLEAUT32!__imp_VariantClear` at `0x180016b34`
- `OLEAUT32!__imp_VariantClear` at `0x1800168c3`
- `OLEAUT32!__imp_VariantClear` at `0x180016a05`
- `OLEAUT32!__imp_VariantClear` at `0x180016a70`
- `OLEAUT32!__imp_VariantClear` at `0x180016ad9`
- `OLEAUT32!__imp_VariantClear` at `0x180016b34`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180016968`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180016968`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180016947`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180016947`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800169d7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800169d7`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18001685d`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18001685d`

## string_xrefs

- `0x18001676d`: `ADREADRC`
- `0x180016757`: `base\fs\fsrm\service\globalstore\adreader.cpp`
- `0x180016762`: `CAdReader::PopulateCollectionFromList`
- `0x18001683a`: `LDAP://%s/CN=%s,CN=Resource Property Lists,CN=Claims Configuration,CN=Services,%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CAdReader::PopulateCollectionFromList(__int64 a1, __int64 a2, char a3)
{
  _QWORD *v6; // rdi
  void **v7; // rax
  const wchar_t *v8; // rbx
  const wchar_t *v9; // r9
  HRESULT Object; // eax
  unsigned int v11; // r9d
  HRESULT v12; // eax
  void *v13; // rdi
  __int64 v14; // r14
  BSTR v15; // rax
  OLECHAR *v16; // rbx
  SAFEARRAY *parray; // rbx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v20; // eax
  LONG i; // eax
  HRESULT Element; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  int Hr; // eax
  char v28; // al
  int v29; // eax
  char v30; // al
  int v31; // eax
  char v32; // al
  int v33; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  int v37; // eax
  char v38; // al
  LPCWSTR lpszPathName; // [rsp+30h] [rbp-D0h] BYREF
  LONG plUbound; // [rsp+38h] [rbp-C8h] BYREF
  LONG rgIndices[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppObject; // [rsp+48h] [rbp-B8h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pv; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v47; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v48; // [rsp+98h] [rbp-68h]
  LPCWSTR v49; // [rsp+A0h] [rbp-60h]
  __int128 v50; // [rsp+A8h] [rbp-58h]
  _OWORD v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-28h]
  int v53; // [rsp+118h] [rbp+18h]
  __int16 v54; // [rsp+120h] [rbp+20h]
  __int64 v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  void *Block[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v58; // [rsp+158h] [rbp+58h]
  unsigned __int64 v59; // [rsp+160h] [rbp+60h]
  void **v60; // [rsp+170h] [rbp+70h] BYREF
  int v61; // [rsp+178h] [rbp+78h]

  v47 = L"base\\fs\\fsrm\\service\\globalstore\\adreader.cpp";
  v48 = L"CAdReader::PopulateCollectionFromList";
  v49 = L"ADREADRC";
  *(_QWORD *)&v50 = 0x1E000000F0LL;
  DWORD2(v50) = 255;
  v53 = 0x1000000;
  memset_0(v51, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v60, (const struct CSrmDebugInfo *)&v47, 0);
  ppObject = 0;
  VariantInit(&pvarg);
  plLbound = 0;
  plUbound = 0;
  v56 = 7;
  v55 = 0;
  v54 = 0;
  v59 = 7;
  v58 = 0;
  LOWORD(Block[0]) = 0;
  ppv = 0;
  v6 = (_QWORD *)(a1 + 16);
  CAdReader::GetConfigurationNamingContext(Block, (void *)(a1 + 16));
  v7 = Block;
  if ( v59 >= 8 )
    v7 = (void **)Block[0];
  v8 = (const wchar_t *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 80) < 8u )
    v9 = (const wchar_t *)(a1 + 56);
  else
    v9 = *(const wchar_t **)v8;
  if ( *(_QWORD *)(a1 + 40) >= 8u )
    v6 = (_QWORD *)*v6;
  SrmFormatString(
    &lpszPathName,
    L"LDAP://%s/CN=%s,CN=Resource Property Lists,CN=Claims Configuration,CN=Services,%s",
    v6,
    v9,
    v7);
  Object = ADsGetObject(lpszPathName, &IID_IADs, &ppObject);
  v61 = Object;
  if ( Object == -2147016656 )
  {
    if ( a3 )
    {
      CoTaskMemFree((LPVOID)lpszPathName);
      lpszPathName = 0;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v59 >= 8 )
        operator delete(Block[0]);
      v59 = 7;
      v58 = 0;
      LOWORD(Block[0]) = 0;
      v12 = VariantClear(&pvarg);
      if ( v12 < 0 )
        _com_issue_error(v12);
LABEL_33:
      if ( ppObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
      goto LABEL_35;
    }
LABEL_47:
    *(_BYTE *)(a1 + 1) = 1;
    if ( *(_QWORD *)(a1 + 80) >= 8u )
      v8 = *(const wchar_t **)v8;
    LODWORD(v47) = -2147209165;
    v48 = v8;
    v49 = lpszPathName;
    v50 = 0;
    memset(v51, 0, sizeof(v51));
    v52 = 0;
    CSrmFunctionTracer::LogEvent(
      (CSrmFunctionTracer *)&v60,
      0x119u,
      1u,
      v11,
      (const struct EventLogMessageContent *)&v47);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, Hr);
    v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x11Bu, v28, 0);
  }
  if ( Object < 0 )
    goto LABEL_47;
  v13 = ppObject;
  v14 = *(_QWORD *)ppObject;
  v15 = SysAllocString(L"msDS-MembersOfResourcePropertyList");
  v16 = v15;
  *(_QWORD *)rgIndices = v15;
  if ( !v15 )
  {
    rgIndices[0] = -2147024882;
    throw (long *)rgIndices;
  }
  v61 = (*(__int64 (__fastcall **)(void *, BSTR, VARIANTARG *))(v14 + 136))(v13, v15, &pvarg);
  SysFreeString(v16);
  if ( v61 < 0 )
  {
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v29);
    v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x11Fu, v30, 0);
  }
  parray = pvarg.parray;
  LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
  v61 = LBound;
  if ( LBound < 0 )
  {
    v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v31);
    v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x123u, v32, 0);
  }
  v61 = LBound;
  UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
  v61 = UBound;
  if ( UBound < 0 )
  {
    v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v33);
    v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x125u, v34, 0);
  }
  v61 = UBound;
  v20 = CoCreateInstance(&CLSID_Pathname, 0, 1u, &IID_IADsPathname, &ppv);
  v61 = v20;
  if ( v20 < 0 )
  {
    v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v35);
    v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x12Bu, v36, 0);
  }
  v61 = v20;
  for ( i = plLbound; ; i = rgIndices[0] + 1 )
  {
    rgIndices[0] = i;
    if ( i > plUbound )
    {
      CoTaskMemFree((LPVOID)lpszPathName);
      lpszPathName = 0;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v59 >= 8 )
        operator delete(Block[0]);
      v59 = 7;
      v58 = 0;
      LOWORD(Block[0]) = 0;
      v24 = VariantClear(&pvarg);
      if ( v24 < 0 )
        _com_issue_error(v24);
      goto LABEL_33;
    }
    VariantInit(&pv);
    if ( *(_BYTE *)a1 )
      break;
    Element = SafeArrayGetElement(parray, rgIndices, &pv);
    v61 = Element;
    if ( Element < 0 )
    {
      v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v60, v37);
      v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v60);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v60, 0x133u, v38, 0);
    }
    v61 = Element;
    CAdReader::CreateAndAddPropertyFromAD(a1, pv.llVal, a2, ppv);
    v23 = VariantClear(&pv);
    if ( v23 < 0 )
      _com_issue_error(v23);
  }
  v25 = VariantClear(&pv);
  if ( v25 < 0 )
    _com_issue_error(v25);
  CoTaskMemFree((LPVOID)lpszPathName);
  lpszPathName = 0;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v59 >= 8 )
    operator delete(Block[0]);
  v59 = 7;
  v58 = 0;
  LOWORD(Block[0]) = 0;
  v26 = VariantClear(&pvarg);
  if ( v26 < 0 )
    _com_issue_error(v26);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
LABEL_35:
  v60 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v60);
}

```

## disassembly

```asm
0x18001671c  mov     [rsp-8+arg_10], rbx
0x180016721  mov     [rsp-8+arg_18], rsi
0x180016726  push    rbp
0x180016727  push    rdi
0x180016728  push    r12
0x18001672a  push    r14
0x18001672c  push    r15
0x18001672e  lea     rbp, [rsp-130h]
0x180016736  sub     rsp, 230h
0x18001673d  mov     rax, cs:__security_cookie
0x180016744  xor     rax, rsp
0x180016747  mov     [rbp+150h+var_30], rax
0x18001674e  mov     r14b, r8b
0x180016751  mov     r15, rdx
0x180016754  mov     rsi, rcx
0x180016757  lea     rax, aBaseFsFsrmServ_14; "base\\fs\\fsrm\\service\\globalstore\\a"...
0x18001675e  mov     [rbp+150h+var_1C0], rax
0x180016762  lea     rax, aCadreaderPopul; "CAdReader::PopulateCollectionFromList"
0x180016769  mov     [rbp+150h+var_1B8], rax
0x18001676d  lea     rax, aAdreadrc; "ADREADRC"
0x180016774  mov     [rbp+150h+var_1B0], rax
0x180016778  mov     dword ptr [rbp+150h+var_1A8], 0F0h
0x18001677f  mov     dword ptr [rbp+150h+var_1A8+4], 1Eh
0x180016786  mov     dword ptr [rbp+150h+var_1A8+8], 0FFh
0x18001678d  xor     r12d, r12d
0x180016790  mov     [rbp+150h+var_138], 1000000h
0x180016797  xor     edx, edx; Val
0x180016799  lea     r8d, [r12+60h]; Size
0x18001679e  lea     rcx, [rbp+150h+var_198]; void *
0x1800167a2  call    memset_0
0x1800167a7  xor     r8d, r8d
0x1800167aa  lea     rdx, [rbp+150h+var_1C0]
0x1800167ae  lea     rcx, [rbp+150h+var_E0]
0x1800167b2  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800167b7  nop
0x1800167b8  mov     [rsp+250h+ppObject], r12
0x1800167bd  lea     rcx, [rsp+250h+pvarg]; pvarg
0x1800167c2  call    cs:__imp_VariantInit
0x1800167c8  nop
0x1800167c9  mov     [rsp+250h+plLbound], r12d
0x1800167ce  mov     [rsp+250h+plUbound], r12d
0x1800167d3  lea     ecx, [r12+7]
0x1800167d8  mov     [rbp+150h+var_118], rcx
0x1800167dc  mov     [rbp+150h+var_120], r12
0x1800167e0  mov     [rbp+150h+var_130], r12w
0x1800167e5  mov     [rbp+150h+var_F0], rcx
0x1800167e9  mov     [rbp+150h+var_F8], r12
0x1800167ed  mov     word ptr [rbp+150h+Block], r12w
0x1800167f2  mov     [rsp+250h+var_1F8], r12
0x1800167f7  lea     rdi, [rsi+10h]
0x1800167fb  mov     rdx, rdi; void *
0x1800167fe  lea     rcx, [rbp+150h+Block]; void *
0x180016802  call    ?GetConfigurationNamingContext@CAdReader@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CAdReader::GetConfigurationNamingContext(std::wstring &,std::wstring &)
0x180016807  lea     rax, [rbp+150h+Block]
0x18001680b  cmp     [rbp+150h+var_F0], 8
0x180016810  cmovnb  rax, [rbp+150h+Block]
0x180016815  lea     rbx, [rsi+38h]
0x180016819  cmp     qword ptr [rbx+18h], 8
0x18001681e  jb      short loc_180016825
0x180016820  mov     r9, [rbx]
0x180016823  jmp     short loc_180016828
0x180016825  mov     r9, rbx
0x180016828  cmp     qword ptr [rdi+18h], 8
0x18001682d  jb      short loc_180016832
0x18001682f  mov     rdi, [rdi]
0x180016832  mov     [rsp+250h+ppv], rax
0x180016837  mov     r8, rdi
0x18001683a  lea     rdx, aLdapSCnSCnReso; "LDAP://%s/CN=%s,CN=Resource Property Li"...
0x180016841  lea     rcx, [rsp+250h+lpszPathName]
0x180016846  call    ?SrmFormatString@@YA?AVCSrmAutoPWSZ@@PEBGZZ; SrmFormatString(ushort const *,...)
0x18001684b  nop
0x18001684c  lea     r8, [rsp+250h+ppObject]; ppObject
0x180016851  lea     rdx, IID_IADs; riid
0x180016858  mov     rcx, [rsp+250h+lpszPathName]; lpszPathName
0x18001685d  call    cs:__imp_ADsGetObject
0x180016863  mov     [rbp+150h+var_D8], eax
0x180016866  cmp     eax, 80072030h
0x18001686b  jnz     short loc_1800168D6
0x18001686d  test    r14b, r14b
0x180016870  jz      loc_180016B6A
0x180016876  mov     rcx, [rsp+250h+lpszPathName]; pv
0x18001687b  call    cs:__imp_CoTaskMemFree
0x180016881  mov     [rsp+250h+lpszPathName], r12
0x180016886  mov     rcx, [rsp+250h+var_1F8]
0x18001688b  test    rcx, rcx
0x18001688e  jz      short loc_18001689D
0x180016890  mov     rax, [rcx]
0x180016893  mov     rax, [rax+10h]
0x180016897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001689c  nop
0x18001689d  cmp     [rbp+150h+var_F0], 8
0x1800168a2  jb      short loc_1800168AD
0x1800168a4  mov     rcx, [rbp+150h+Block]; Block
0x1800168a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800168ad  mov     [rbp+150h+var_F0], 7
0x1800168b5  mov     [rbp+150h+var_F8], r12
0x1800168b9  mov     word ptr [rbp+150h+Block], r12w
0x1800168be  lea     rcx, [rsp+250h+pvarg]; pvarg
0x1800168c3  call    cs:__imp_VariantClear
0x1800168c9  test    eax, eax
0x1800168cb  js      loc_180016B62
0x1800168d1  jmp     loc_180016A7E
0x1800168d6  test    eax, eax
0x1800168d8  js      loc_180016B6A
0x1800168de  mov     rdi, [rsp+250h+ppObject]
0x1800168e3  mov     r14, [rdi]
0x1800168e6  lea     rcx, aMsdsMembersofr; "msDS-MembersOfResourcePropertyList"
0x1800168ed  call    cs:__imp_SysAllocString
0x1800168f3  mov     rbx, rax
0x1800168f6  mov     qword ptr [rsp+250h+rgIndices], rax
0x1800168fb  test    rax, rax
0x1800168fe  jz      loc_180016BF4
0x180016904  lea     r8, [rsp+250h+pvarg]
0x180016909  mov     rdx, rax
0x18001690c  mov     rcx, rdi
0x18001690f  mov     rax, [r14+88h]
0x180016916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691b  mov     [rbp+150h+var_D8], eax
0x18001691e  mov     rcx, rbx; bstrString
0x180016921  call    cs:__imp_SysFreeString
0x180016927  mov     eax, [rbp+150h+var_D8]
0x18001692a  test    eax, eax
0x18001692c  js      loc_180016C0E
0x180016932  mov     [rbp+150h+var_D8], eax
0x180016935  mov     rbx, qword ptr [rsp+250h+pvarg+8]
0x18001693a  lea     r8, [rsp+250h+plLbound]; plLbound
0x18001693f  mov     edx, 1; nDim
0x180016944  mov     rcx, rbx; psa
0x180016947  call    cs:__imp_SafeArrayGetLBound
0x18001694d  mov     [rbp+150h+var_D8], eax
0x180016950  test    eax, eax
0x180016952  js      loc_180016C40
0x180016958  mov     [rbp+150h+var_D8], eax
0x18001695b  lea     r8, [rsp+250h+plUbound]; plUbound
0x180016960  mov     edx, 1; nDim
0x180016965  mov     rcx, rbx; psa
0x180016968  call    cs:__imp_SafeArrayGetUBound
0x18001696e  mov     [rbp+150h+var_D8], eax
0x180016971  test    eax, eax
0x180016973  js      loc_180016C72
0x180016979  mov     [rbp+150h+var_D8], eax
0x18001697c  lea     rax, [rsp+250h+var_1F8]
0x180016981  mov     [rsp+250h+ppv], rax; ppv
0x180016986  lea     r9, IID_IADsPathname; riid
0x18001698d  xor     edx, edx; pUnkOuter
0x18001698f  lea     r8d, [rdx+1]; dwClsContext
0x180016993  lea     rcx, CLSID_Pathname; rclsid
0x18001699a  call    cs:__imp_CoCreateInstance
0x1800169a0  mov     [rbp+150h+var_D8], eax
0x1800169a3  test    eax, eax
0x1800169a5  js      loc_180016CA4
0x1800169ab  mov     [rbp+150h+var_D8], eax
0x1800169ae  mov     eax, [rsp+250h+plLbound]
0x1800169b2  jmp     short loc_180016A19
0x1800169b4  lea     rcx, [rsp+250h+pv]; pvarg
0x1800169b9  call    cs:__imp_VariantInit
0x1800169bf  nop
0x1800169c0  mov     al, [rsi]
0x1800169c2  test    al, al
0x1800169c4  jnz     loc_180016AD4
0x1800169ca  lea     r8, [rsp+250h+pv]; pv
0x1800169cf  lea     rdx, [rsp+250h+rgIndices]; rgIndices
0x1800169d4  mov     rcx, rbx; psa
0x1800169d7  call    cs:__imp_SafeArrayGetElement
0x1800169dd  mov     [rbp+150h+var_D8], eax
0x1800169e0  test    eax, eax
0x1800169e2  js      loc_180016CE6
0x1800169e8  mov     [rbp+150h+var_D8], eax
0x1800169eb  mov     r9, [rsp+250h+var_1F8]
0x1800169f0  mov     r8, r15
0x1800169f3  mov     rdx, qword ptr [rbp+150h+pv+8]
0x1800169f7  mov     rcx, rsi
0x1800169fa  call    ?CreateAndAddPropertyFromAD@CAdReader@@AEAAXPEBGPEAV?$CComObject@VCFsrmCollection@@@ATL@@PEAUIADsPathname@@@Z; CAdReader::CreateAndAddPropertyFromAD(ushort const *,ATL::CComObject<CFsrmCollection> *,IADsPathname *)
0x1800169ff  nop
0x180016a00  lea     rcx, [rsp+250h+pv]; pvarg
0x180016a05  call    cs:__imp_VariantClear
0x180016a0b  test    eax, eax
0x180016a0d  js      loc_180016CDE
0x180016a13  mov     eax, [rsp+250h+rgIndices]
0x180016a17  inc     eax
0x180016a19  cmp     eax, [rsp+250h+plUbound]
0x180016a1d  mov     [rsp+250h+rgIndices], eax
0x180016a21  jle     short loc_1800169B4
0x180016a23  mov     rcx, [rsp+250h+lpszPathName]; pv
0x180016a28  call    cs:__imp_CoTaskMemFree
0x180016a2e  mov     [rsp+250h+lpszPathName], r12
0x180016a33  mov     rcx, [rsp+250h+var_1F8]
0x180016a38  test    rcx, rcx
0x180016a3b  jz      short loc_180016A4A
0x180016a3d  mov     rax, [rcx]
0x180016a40  mov     rax, [rax+10h]
0x180016a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a49  nop
0x180016a4a  cmp     [rbp+150h+var_F0], 8
0x180016a4f  jb      short loc_180016A5A
0x180016a51  mov     rcx, [rbp+150h+Block]; Block
0x180016a55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a5a  mov     [rbp+150h+var_F0], 7
0x180016a62  mov     [rbp+150h+var_F8], r12
0x180016a66  mov     word ptr [rbp+150h+Block], r12w
0x180016a6b  lea     rcx, [rsp+250h+pvarg]; pvarg
0x180016a70  call    cs:__imp_VariantClear
0x180016a76  test    eax, eax
0x180016a78  js      loc_180016CD6
0x180016a7e  mov     rcx, [rsp+250h+ppObject]
0x180016a83  test    rcx, rcx
0x180016a86  jz      short loc_180016A95
0x180016a88  mov     rax, [rcx]
0x180016a8b  mov     rax, [rax+10h]
0x180016a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a94  nop
0x180016a95  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180016a9c  mov     [rbp+150h+var_E0], rax
0x180016aa0  lea     rcx, [rbp+150h+var_E0]; this
0x180016aa4  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180016aa9  mov     rcx, [rbp+150h+var_30]
0x180016ab0  xor     rcx, rsp; StackCookie
0x180016ab3  call    __security_check_cookie
0x180016ab8  lea     r11, [rsp+250h+var_20]
0x180016ac0  mov     rbx, [r11+40h]
0x180016ac4  mov     rsi, [r11+48h]
0x180016ac8  mov     rsp, r11
0x180016acb  pop     r15
0x180016acd  pop     r14
0x180016acf  pop     r12
0x180016ad1  pop     rdi
0x180016ad2  pop     rbp
0x180016ad3  retn
0x180016ad4  lea     rcx, [rsp+250h+pv]; pvarg
0x180016ad9  call    cs:__imp_VariantClear
0x180016adf  test    eax, eax
0x180016ae1  js      loc_180016D18
0x180016ae7  mov     rcx, [rsp+250h+lpszPathName]; pv
0x180016aec  call    cs:__imp_CoTaskMemFree
0x180016af2  mov     [rsp+250h+lpszPathName], r12
0x180016af7  mov     rcx, [rsp+250h+var_1F8]
0x180016afc  test    rcx, rcx
0x180016aff  jz      short loc_180016B0E
0x180016b01  mov     rax, [rcx]
0x180016b04  mov     rax, [rax+10h]
0x180016b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b0d  nop
0x180016b0e  cmp     [rbp+150h+var_F0], 8
0x180016b13  jb      short loc_180016B1E
0x180016b15  mov     rcx, [rbp+150h+Block]; Block
0x180016b19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016b1e  mov     [rbp+150h+var_F0], 7
0x180016b26  mov     [rbp+150h+var_F8], r12
0x180016b2a  mov     word ptr [rbp+150h+Block], r12w
0x180016b2f  lea     rcx, [rsp+250h+pvarg]; pvarg
0x180016b34  call    cs:__imp_VariantClear
0x180016b3a  test    eax, eax
0x180016b3c  js      short loc_180016B5A
0x180016b3e  mov     rcx, [rsp+250h+ppObject]
0x180016b43  test    rcx, rcx
0x180016b46  jz      short loc_180016B55
0x180016b48  mov     rax, [rcx]
0x180016b4b  mov     rax, [rax+10h]
0x180016b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b54  nop
0x180016b55  jmp     loc_180016A95
0x180016b5a  mov     ecx, eax; int
0x180016b5c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180016b62  mov     ecx, eax; int
0x180016b64  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180016b6a  mov     byte ptr [rsi+1], 1
0x180016b6e  mov     rax, [rsp+250h+lpszPathName]
0x180016b73  cmp     qword ptr [rbx+18h], 8
0x180016b78  jb      short loc_180016B7D
0x180016b7a  mov     rbx, [rbx]
0x180016b7d  mov     dword ptr [rbp+150h+var_1C0], 80043033h
0x180016b84  mov     [rbp+150h+var_1B8], rbx
0x180016b88  mov     [rbp+150h+var_1B0], rax
0x180016b8c  xorps   xmm0, xmm0
0x180016b8f  movdqu  [rbp+150h+var_1A8], xmm0
0x180016b94  xorps   xmm1, xmm1
0x180016b97  movdqu  [rbp+150h+var_198], xmm1
0x180016b9c  movdqu  [rbp+150h+var_188], xmm0
0x180016ba1  mov     [rbp+150h+var_178], r12
0x180016ba5  mov     r8d, 1; unsigned __int16
0x180016bab  lea     rax, [rbp+150h+var_1C0]
0x180016baf  mov     [rsp+250h+ppv], rax; struct EventLogMessageContent *
0x180016bb4  mov     edx, 119h; unsigned int
0x180016bb9  lea     rcx, [rbp+150h+var_E0]; this
0x180016bbd  call    ?LogEvent@CSrmFunctionTracer@@QEAAXKGKAEBUEventLogMessageContent@@@Z; CSrmFunctionTracer::LogEvent(ulong,ushort,ulong,EventLogMessageContent const &)
0x180016bc2  lea     rcx, [rbp+150h+var_E0]; this
0x180016bc6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180016bcb  mov     edx, eax; int
0x180016bcd  lea     rcx, [rbp+150h+var_E0]; this
0x180016bd1  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180016bd6  lea     rcx, [rbp+150h+var_E0]; this
0x180016bda  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180016bdf  mov     r8d, eax; char
0x180016be2  xor     r9d, r9d; unsigned __int16 *
0x180016be5  mov     edx, 11Bh; unsigned int
0x180016bea  lea     rcx, [rbp+150h+var_E0]; this
0x180016bee  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180016bf4  mov     [rsp+250h+rgIndices], 8007000Eh
0x180016bfc  lea     rdx, _TI1J; pThrowInfo
0x180016c03  lea     rcx, [rsp+250h+rgIndices]; pExceptionObject
  ... truncated ...
```
