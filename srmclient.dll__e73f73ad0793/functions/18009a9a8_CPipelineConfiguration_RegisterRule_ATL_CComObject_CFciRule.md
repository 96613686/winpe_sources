# CPipelineConfiguration::RegisterRule(ATL::CComObject<CFciRule> &)

- ea: `0x18009a9a8`
- end: `0x18009ba0a`
- name: `?RegisterRule@CPipelineConfiguration@@AEAAXAEAV?$CComObject@VCFciRule@@@ATL@@@Z`
- size: `4194`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009a5d0`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000eef4`
- `0x180012238`
- `0x18001a184`
- `0x180022b84`
- `0x180022e80`
- `0x18003dcec`
- `0x18005162c`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073a80`
- `0x180073f54`
- `0x18008d668`
- `0x18008e0a8`
- `0x180099420`
- `0x180099588`
- `0x1800996f0`
- `0x18009a9a8`
- `0x1800a290c`
- `0x1800a2a98`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18009ac58`
- `msvcrt!_wcsicmp` at `0x18009aca2`
- `msvcrt!_wcsicmp` at `0x18009b213`
- `msvcrt!_wcsicmp` at `0x18009b260`
- `msvcrt!_wcsicmp` at `0x18009b2ef`
- `msvcrt!_wcsicmp` at `0x18009b339`
- `msvcrt!_wcsicmp` at `0x18009ac58`
- `msvcrt!_wcsicmp` at `0x18009aca2`
- `msvcrt!_wcsicmp` at `0x18009b213`
- `msvcrt!_wcsicmp` at `0x18009b260`
- `msvcrt!_wcsicmp` at `0x18009b2ef`
- `msvcrt!_wcsicmp` at `0x18009b339`
- `OLEAUT32!__imp_SysFreeString` at `0x18009aafe`
- `OLEAUT32!__imp_SysFreeString` at `0x18009adb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18009adc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b00f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b01a`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b046`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b052`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b5f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b604`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b630`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b63c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009aafe`
- `OLEAUT32!__imp_SysFreeString` at `0x18009adb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18009adc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b00f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b01a`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b046`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b052`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b5f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b604`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b630`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b63c`
- `OLEAUT32!__imp_VariantInit` at `0x18009ab8b`
- `OLEAUT32!__imp_VariantInit` at `0x18009abd4`
- `OLEAUT32!__imp_VariantInit` at `0x18009ab8b`
- `OLEAUT32!__imp_VariantInit` at `0x18009abd4`
- `OLEAUT32!__imp_VariantChangeType` at `0x18009abec`
- `OLEAUT32!__imp_VariantChangeType` at `0x18009abec`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009b5d4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009b5d4`

## string_xrefs

- `0x18009a9e7`: `base\fs\fsrm\service\pipeline\plconfig.cpp`
- `0x18009acfe`: `base\fs\fsrm\service\pipeline\plconfig.cpp`
- `0x18009af64`: `base\fs\fsrm\service\pipeline\plconfig.cpp`
- `0x18009a9f2`: `CPipelineConfiguration::RegisterRule`
- `0x18009ad09`: `CPipelineConfiguration::RegisterRule`
- `0x18009af6f`: `CPipelineConfiguration::RegisterRule`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
void __fastcall CPipelineConfiguration::RegisterRule(_QWORD *a1, CFciRule *a2)
{
  __int64 v4; // r13
  int v5; // eax
  _QWORD *v6; // rdi
  int v7; // eax
  unsigned int v8; // r12d
  int v9; // eax
  int v10; // eax
  int v11; // eax
  LONGLONG llVal; // rbx
  HRESULT v13; // eax
  __int64 *v14; // r14
  __int64 *v15; // rbx
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rdx
  __int64 *v18; // rbx
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  __int64 *v21; // r14
  struct CSrmDebugInfo *v22; // rax
  CSrmDebugInfo *v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  struct CSrmDebugInfo *v29; // rax
  CSrmDebugInfo *v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // r14
  __int64 v35; // rcx
  SAFEARRAY *v36; // r12
  __int64 *v37; // rdi
  __int64 *v38; // rbx
  const wchar_t *v39; // rcx
  const wchar_t *v40; // rdx
  __int64 *v41; // r15
  const wchar_t *v42; // rdx
  const wchar_t *v43; // rcx
  _QWORD *v44; // rdi
  __int64 *v45; // rbx
  const wchar_t *v46; // rcx
  const wchar_t *v47; // rdx
  const wchar_t *v48; // rdx
  const wchar_t *v49; // rcx
  int v50; // eax
  CScanRuleCollection *v51; // rbx
  int v52; // eax
  CScanPropDefCollection *v53; // rdi
  CScanRuleCollection **v54; // rax
  CScanRuleCollection **v55; // r15
  CScanPropDefCollection **v56; // rax
  CScanPropDefCollection **v57; // rsi
  CScanPropDefCollection *v58; // rbx
  int v59; // eax
  char v60; // al
  int Hr; // eax
  char v62; // al
  int v63; // eax
  char v64; // al
  int v65; // eax
  char v66; // al
  int v67; // eax
  char v68; // al
  int v69; // eax
  char v70; // al
  int v71; // eax
  char v72; // al
  int v73; // eax
  char v74; // al
  int v75; // eax
  char v76; // al
  int v77; // eax
  char v78; // al
  int v79; // eax
  char v80; // al
  int v81; // eax
  char v82; // al
  int v83; // eax
  char v84; // al
  int v85; // eax
  char v86; // al
  unsigned int v87; // [rsp+50h] [rbp-B0h]
  BSTR v88; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v89[2]; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  struct IFsrmRule *v91; // [rsp+78h] [rbp-88h] BYREF
  BSTR v92; // [rsp+80h] [rbp-80h] BYREF
  __int64 v93; // [rsp+88h] [rbp-78h] BYREF
  enum _FsrmExecutionOption v94; // [rsp+90h] [rbp-70h] BYREF
  void **v95; // [rsp+98h] [rbp-68h] BYREF
  SAFEARRAY *psa; // [rsp+A0h] [rbp-60h]
  LONGLONG v97; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v98; // [rsp+B0h] [rbp-50h] BYREF
  int v99; // [rsp+B8h] [rbp-48h] BYREF
  SAFEARRAY *v100; // [rsp+C0h] [rbp-40h] BYREF
  CScanRuleCollection *v101; // [rsp+C8h] [rbp-38h] BYREF
  CScanPropDefCollection *v102; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v104; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v105; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v106; // [rsp+100h] [rbp+0h]
  int v107; // [rsp+108h] [rbp+8h]
  int v108; // [rsp+10Ch] [rbp+Ch]
  int v109; // [rsp+110h] [rbp+10h]
  _BYTE v110[96]; // [rsp+118h] [rbp+18h] BYREF
  int v111; // [rsp+178h] [rbp+78h]
  void *Block[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v113; // [rsp+190h] [rbp+90h]
  __int64 v114; // [rsp+1A0h] [rbp+A0h]
  _BYTE v115[144]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v116[144]; // [rsp+238h] [rbp+138h] BYREF
  VARIANTARG pvargDest; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned __int64 v118; // [rsp+2E0h] [rbp+1E0h]
  void **v119; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v120; // [rsp+2F8h] [rbp+1F8h]
  wchar_t *String2[3]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int64 v122; // [rsp+3B8h] [rbp+2B8h]
  wchar_t *String1[3]; // [rsp+3C8h] [rbp+2C8h] BYREF
  unsigned __int64 v124; // [rsp+3E0h] [rbp+2E0h]
  wchar_t *v125[3]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int64 v126; // [rsp+408h] [rbp+308h]
  struct _GUID v127; // [rsp+418h] [rbp+318h] BYREF
  struct _GUID v128; // [rsp+428h] [rbp+328h] BYREF

  *(_QWORD *)v89 = &v104;
  v104 = L"base\\fs\\fsrm\\service\\pipeline\\plconfig.cpp";
  v105 = L"CPipelineConfiguration::RegisterRule";
  v106 = L"PLCONFGC";
  v107 = 346;
  v108 = 22;
  v109 = 255;
  v4 = 0;
  v111 = 0x1000000;
  memset_0(v110, 0, sizeof(v110));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v119, (const struct CSrmDebugInfo *)&v104, 0);
  v91 = 0;
  v5 = (**(__int64 (__fastcall ***)(CFciRule *, GUID *, struct IFsrmRule **))a2)(
         a2,
         &GUID_cb0df960_16f5_4495_9079_3f9360d831df,
         &v91);
  v120 = v5;
  if ( v5 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, Hr);
    v62 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x15Du, v62, 0);
  }
  v120 = v5;
  bstrString = 0;
  v6 = (_QWORD *)((char *)a2 + 8);
  v7 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*((_QWORD *)a2 + 1) + 96LL))((_QWORD *)a2 + 1, &bstrString);
  v120 = v7;
  if ( v7 < 0 )
  {
    v63 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v63);
    v64 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x163u, v64, 0);
  }
  v120 = v7;
  v89[0] = 0;
  CFciRule::GetRuleFlagsInternal(a2, (int *)v89, 1);
  v8 = v89[0];
  if ( (v89[0] & 0x100) != 0 )
  {
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v119,
      0x8Cu,
      0x16Du,
      L"Rule '%s' is disabled and won't be registered",
      bstrString);
    SysFreeString(bstrString);
    if ( v91 )
      ((void (__fastcall *)(struct IFsrmRule *))v91->lpVtbl->Release)(v91);
    v119 = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v88 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v6 + 120LL))((_QWORD *)a2 + 1, &v88);
    v120 = v9;
    if ( v9 < 0 )
    {
      v65 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v65);
      v66 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x172u, v66, 0);
    }
    v120 = v9;
    v99 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v6 + 112LL))((_QWORD *)a2 + 1, &v99);
    v120 = v10;
    if ( v10 < 0 )
    {
      v67 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v67);
      v68 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x175u, v68, 0);
    }
    v120 = v10;
    VariantInit(&pvarg);
    v11 = (*(__int64 (__fastcall **)(_QWORD *, VARIANTARG *))(*v6 + 184LL))((_QWORD *)a2 + 1, &pvarg);
    v120 = v11;
    if ( v11 < 0 )
    {
      v69 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v69);
      v70 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x17Bu, v70, 0);
    }
    v120 = v11;
    if ( pvarg.vt == 21 )
    {
      llVal = pvarg.llVal;
    }
    else
    {
      VariantInit(&pvargDest);
      v13 = VariantChangeType(&pvargDest, &pvarg, 0, 0x15u);
      if ( v13 < 0 )
        _com_issue_error(v13);
      llVal = pvargDest.llVal;
      _variant_t::~_variant_t(&pvargDest);
    }
    v97 = llVal;
    std::wstring::wstring(String2, v88);
    v14 = (__int64 *)a1[13];
    v15 = (__int64 *)v14[1];
    while ( !*((_BYTE *)v15 + 73) )
    {
      v16 = (const wchar_t *)(v15 + 3);
      v17 = (const wchar_t *)String2;
      if ( v122 >= 8 )
        v17 = String2[0];
      if ( (unsigned __int64)v15[6] >= 8 )
        v16 = *(const wchar_t **)v16;
      if ( _wcsicmp(v16, v17) >= 0 )
      {
        v14 = v15;
        v15 = (__int64 *)*v15;
      }
      else
      {
        v15 = (__int64 *)v15[2];
      }
    }
    v18 = (__int64 *)a1[13];
    if ( v14 != v18 )
    {
      v19 = (const wchar_t *)(v14 + 3);
      if ( (unsigned __int64)v14[6] >= 8 )
        v19 = *(const wchar_t **)v19;
      v20 = (const wchar_t *)String2;
      if ( v122 >= 8 )
        v20 = String2[0];
      if ( _wcsicmp(v20, v19) >= 0 )
        v18 = v14;
      else
        v18 = (__int64 *)a1[13];
    }
    v21 = (__int64 *)a1[13];
    if ( v122 >= 8 )
      operator delete(String2[0]);
    v122 = 7;
    String2[2] = 0;
    LOWORD(String2[0]) = 0;
    if ( v18 == v21 )
    {
      *(_QWORD *)v89 = v115;
      v104 = L"base\\fs\\fsrm\\service\\pipeline\\plconfig.cpp";
      v105 = L"CPipelineConfiguration::RegisterRule";
      v106 = L"PLCONFGC";
      v107 = 391;
      v108 = 22;
      v109 = 255;
      v111 = 0x1000000;
      memset_0(v110, 0, sizeof(v110));
      v22 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)&v104, (CSrmDebugInfo *)v116, bstrString);
      v23 = CSrmDebugInfo::operator<<(v22, (CSrmDebugInfo *)v115, v88);
      CSrmFunctionTracer::LogError((__int64)&v119, 0x80043030, (__int64)v23, 2u);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v116);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v104);
      _variant_t::~_variant_t(&pvarg);
      SysFreeString(v88);
      SysFreeString(bstrString);
      if ( v91 )
        ((void (__fastcall *)(struct IFsrmRule *))v91->lpVtbl->Release)(v91);
      v119 = &CSrmFunctionTracer::`vftable';
    }
    else
    {
      v128 = 0;
      v93 = 0;
      v92 = 0;
      v98 = 0;
      v94 = FsrmExecutionOption_Unknown;
      v24 = (*(__int64 (__fastcall **)(_QWORD *, struct _GUID *))(*v6 + 56LL))((_QWORD *)a2 + 1, &v128);
      v120 = v24;
      if ( v24 < 0 )
      {
        v71 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v71);
        v72 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x19Bu, v72, 0);
      }
      v120 = v24;
      v25 = (**(__int64 (__fastcall ***)(CFciRule *, GUID *, __int64 *))a2)(
              a2,
              &GUID_afc052c2_5315_45ab_841b_c6db0e120148,
              &v93);
      v120 = v25;
      if ( v25 < 0 )
      {
        v73 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v73);
        v74 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x19Cu, v74, 0);
      }
      v120 = v25;
      v26 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v93 + 208LL))(v93, &v92);
      v120 = v26;
      if ( v26 < 0 )
      {
        v75 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v75);
        v76 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x19Du, v76, 0);
      }
      v120 = v26;
      v27 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v93 + 224LL))(v93, &v98);
      v120 = v27;
      if ( v27 < 0 )
      {
        v77 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v77);
        v78 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x19Eu, v78, 0);
      }
      v120 = v27;
      v28 = (*(__int64 (__fastcall **)(__int64, enum _FsrmExecutionOption *))(*(_QWORD *)v93 + 192LL))(v93, &v94);
      v120 = v28;
      if ( v28 < 0 )
      {
        v79 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v79);
        v80 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x19Fu, v80, 0);
      }
      v120 = v28;
      std::wstring::wstring(&pvargDest, v92);
      std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
        a1 + 2,
        v89,
        &pvargDest);
      if ( v118 >= 8 )
        operator delete(*(void **)&pvargDest.vt);
      v118 = 7;
      pvargDest.pRecInfo = 0;
      pvargDest.vt = 0;
      if ( *(_QWORD *)v89 != a1[3] )
        v4 = *(_QWORD *)(*(_QWORD *)v89 + 64LL);
      if ( v4 )
      {
        v127 = 0;
        v31 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**(_QWORD **)(v4 + 16) + 56LL))(
                *(_QWORD *)(v4 + 16),
                &v127);
        v120 = v31;
        if ( v31 < 0 )
        {
          v81 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v81);
          v82 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x1ABu, v82, 0);
        }
        v120 = v31;
        v100 = 0;
        psa = 0;
        v95 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
        *(_OWORD *)Block = 0;
        v113 = 0;
        v32 = (*(__int64 (__fastcall **)(_QWORD *, SAFEARRAY **))(*v6 + 136LL))(v6, &v100);
        v120 = v32;
        if ( v32 < 0 )
        {
          v83 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v83);
          v84 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x1B4u, v84, 0);
        }
        v120 = v32;
        psa = v100;
        v33 = CSrmSingleton<CFciMgmtProperties>::Instance();
        v34 = v33;
        v114 = v33;
        if ( v33 )
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
        CFciMgmtProperties::ExpandNamespaceRoots(v33, &v95, Block);
        v97 = (LONGLONG)*CPipelineConfiguration::DetermineEffectiveModifedTime(
                           v35,
                           (FILETIME *)v89,
                           (__int64)&v95,
                           Block,
                           (FILETIME *)&v97);
        v87 = v8;
        v36 = psa;
        CScanInformation::RegisterNamespaceRoots(
          (CScanInformation *)(a1 + 27),
          psa,
          bstrString,
          v88,
          v92,
          v98,
          &v128,
          &v127,
          v94,
          (FILETIME *)&v97,
          v87,
          0);
        std::wstring::wstring(String1, v88);
        v37 = (__int64 *)a1[20];
        v38 = (__int64 *)v37[1];
        while ( !*((_BYTE *)v38 + 73) )
        {
          v39 = (const wchar_t *)(v38 + 3);
          v40 = (const wchar_t *)String1;
          if ( v124 >= 8 )
            v40 = String1[0];
          if ( (unsigned __int64)v38[6] >= 8 )
            v39 = *(const wchar_t **)v39;
          if ( _wcsicmp(v39, v40) >= 0 )
          {
            v37 = v38;
            v38 = (__int64 *)*v38;
          }
          else
          {
            v38 = (__int64 *)v38[2];
          }
        }
        v41 = (__int64 *)a1[20];
        if ( v37 != v41 )
        {
          v42 = (const wchar_t *)(v37 + 3);
          if ( (unsigned __int64)v37[6] >= 8 )
            v42 = *(const wchar_t **)v42;
          v43 = (const wchar_t *)String1;
          if ( v124 >= 8 )
            v43 = String1[0];
          if ( _wcsicmp(v43, v42) >= 0 )
            v41 = v37;
          else
            v41 = (__int64 *)a1[20];
        }
        if ( v124 >= 8 )
          operator delete(String1[0]);
        v124 = 7;
        String1[2] = 0;
        LOWORD(String1[0]) = 0;
        std::wstring::wstring(v125, v88);
        v44 = (_QWORD *)a1[24];
        v45 = (__int64 *)v44[1];
        while ( !*((_BYTE *)v45 + 73) )
        {
          v46 = (const wchar_t *)(v45 + 3);
          v47 = (const wchar_t *)v125;
          if ( v126 >= 8 )
            v47 = v125[0];
          if ( (unsigned __int64)v45[6] >= 8 )
            v46 = *(const wchar_t **)v46;
          if ( _wcsicmp(v46, v47) >= 0 )
          {
            v44 = v45;
            v45 = (__int64 *)*v45;
          }
          else
          {
            v45 = (__int64 *)v45[2];
          }
        }
        if ( v44 == (_QWORD *)a1[24] )
          goto LABEL_90;
        v48 = (const wchar_t *)(v44 + 3);
        if ( v44[6] >= 8u )
          v48 = *(const wchar_t **)v48;
        v49 = (const wchar_t *)v125;
        if ( v126 >= 8 )
          v49 = v125[0];
        if ( _wcsicmp(v49, v48) < 0 )
LABEL_90:
          v44 = (_QWORD *)a1[24];
        if ( v126 >= 8 )
          operator delete(v125[0]);
        v126 = 7;
        v125[2] = 0;
        LOWORD(v125[0]) = 0;
        if ( v41 == (__int64 *)a1[20] )
        {
          v101 = 0;
          v50 = ATL::CComObject<CScanRuleCollection>::CreateInstance(&v101);
          v120 = v50;
          if ( v50 < 0 )
          {
            v85 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v85);
            v86 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x1ECu, v86, 0);
          }
          v120 = v50;
          v51 = v101;
          (*(void (__fastcall **)(CScanRuleCollection *))(*(_QWORD *)v101 + 8LL))(v101);
          v102 = 0;
          v52 = ATL::CComObject<CScanPropDefCollection>::CreateInstance(&v102);
          v120 = v52;
          if ( v52 < 0 )
          {
            v59 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v119, v59);
            v60 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v119);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v119, 0x1F1u, v60, 0);
          }
          v120 = v52;
          v53 = v102;
          (*(void (__fastcall **)(CScanPropDefCollection *))(*(_QWORD *)v102 + 8LL))(v102);
          CScanRuleCollection::AddItem(v51, v91);
          CScanPropDefCollection::AddItem(v53, *(struct IFsrmPropertyDefinition **)(v4 + 16));
          std::wstring::wstring(&pvargDest, v88);
          v54 = (CScanRuleCollection **)std::map<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CProperty>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CProperty>>>>>>::operator[](
                                          a1 + 19,
                                          &pvargDest);
          v55 = v54;
          if ( *v54 != v51 && v54 )
          {
            if ( v51 )
              (*(void (__fastcall **)(CScanRuleCollection *))(*(_QWORD *)v51 + 8LL))(v51);
            if ( *v55 )
              (*(void (__fastcall **)(CScanRuleCollection *))(*(_QWORD *)*v55 + 16LL))(*v55);
            *v55 = v51;
          }
          if ( v118 >= 8 )
            operator delete(*(void **)&pvargDest.vt);
          v118 = 7;
          pvargDest.pRecInfo = 0;
          pvargDest.vt = 0;
          std::wstring::wstring(&pvargDest, v88);
          v56 = (CScanPropDefCollection **)std::map<std::wstring,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CProperty>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<ATL::CComObject<CProperty>>>>>>::operator[](
                                             a1 + 23,
                                             &pvargDest);
          v57 = v56;
          if ( *v56 != v53 && v56 )
          {
            if ( v53 )
              (*(void (__fastcall **)(CScanPropDefCollection *))(*(_QWORD *)v53 + 8LL))(v53);
            if ( *v57 )
              (*(void (__fastcall **)(CScanPropDefCollection *))(*(_QWORD *)*v57 + 16LL))(*v57);
            *v57 = v53;
          }
          if ( v118 >= 8 )
            operator delete(*(void **)&pvargDest.vt);
          v118 = 7;
          pvargDest.pRecInfo = 0;
          pvargDest.vt = 0;
          (*(void (__fastcall **)(CScanPropDefCollection *))(*(_QWORD *)v53 + 16LL))(v53);
          (*(void (__fastcall **)(CScanRuleCollection *))(*(_QWORD *)v51 + 16LL))(v51);
        }
        else
        {
          v58 = (CScanPropDefCollection *)v44[8];
          CScanRuleCollection::AddItem((CScanRuleCollection *)v41[8], v91);
          CScanPropDefCollection::AddItem(v58, *(struct IFsrmPropertyDefinition **)(v4 + 16));
        }
        if ( v34 && _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v34)(v34, 1);
        if ( Block[0] )
          operator delete(Block[0]);
        *(_OWORD *)Block = 0;
        v113 = 0;
        v95 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
        if ( v36 )
          SafeArrayDestroy(v36);
        v95 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
        psa = 0;
        SysFreeString(v98);
        SysFreeString(v92);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        _variant_t::~_variant_t(&pvarg);
        SysFreeString(v88);
        SysFreeString(bstrString);
        if ( v91 )
          ((void (__fastcall *)(struct IFsrmRule *))v91->lpVtbl->Release)(v91);
        v119 = &CSrmFunctionTracer::`vftable';
      }
      else
      {
        *(_QWORD *)v89 = v116;
        v104 = L"base\\fs\\fsrm\\service\\pipeline\\plconfig.cpp";
        v105 = L"CPipelineConfiguration::RegisterRule";
        v106 = L"PLCONFGC";
        v107 = 421;
        v108 = 22;
        v109 = 255;
        v111 = 0x1000000;
        memset_0(v110, 0, sizeof(v110));
        v29 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)&v104, (CSrmDebugInfo *)v115, bstrString);
        v30 = CSrmDebugInfo::operator<<(v29, (CSrmDebugInfo *)v116, v92);
        CSrmFunctionTracer::LogError((__int64)&v119, 0x80043031, (__int64)v30, 2u);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v115);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v104);
        SysFreeString(v98);
        SysFreeString(v92);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        _variant_t::~_variant_t(&pvarg);
        SysFreeString(v88);
        SysFreeString(bstrString);
        if ( v91 )
          ((void (__fastcall *)(struct IFsrmRule *))v91->lpVtbl->Release)(v91);
        v119 = &CSrmFunctionTracer::`vftable';
      }
    }
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v119);
}

```

## disassembly

```asm
0x18009a9a8  mov     [rsp-8+arg_10], rbx
0x18009a9ad  push    rbp
0x18009a9ae  push    rsi
0x18009a9af  push    rdi
0x18009a9b0  push    r12
0x18009a9b2  push    r13
0x18009a9b4  push    r14
0x18009a9b6  push    r15
0x18009a9b8  lea     rbp, [rsp-340h]
0x18009a9c0  sub     rsp, 440h
0x18009a9c7  mov     rax, cs:__security_cookie
0x18009a9ce  xor     rax, rsp
0x18009a9d1  mov     [rbp+370h+var_38], rax
0x18009a9d8  mov     r15, rdx
0x18009a9db  mov     rsi, rcx
0x18009a9de  lea     rax, [rbp+370h+var_380]
0x18009a9e2  mov     qword ptr [rsp+470h+var_408], rax
0x18009a9e7  lea     rax, aBaseFsFsrmServ_23; "base\\fs\\fsrm\\service\\pipeline\\plco"...
0x18009a9ee  mov     [rbp+370h+var_380], rax
0x18009a9f2  lea     rax, aCpipelineconfi; "CPipelineConfiguration::RegisterRule"
0x18009a9f9  mov     [rbp+370h+var_378], rax
0x18009a9fd  lea     rax, aPlconfgc; "PLCONFGC"
0x18009aa04  mov     [rbp+370h+var_370], rax
0x18009aa08  mov     [rbp+370h+var_368], 15Ah
0x18009aa0f  mov     [rbp+370h+var_364], 16h
0x18009aa16  mov     [rbp+370h+var_360], 0FFh
0x18009aa1d  xor     r13d, r13d
0x18009aa20  mov     [rbp+370h+var_2F8], 1000000h
0x18009aa27  xor     edx, edx; Val
0x18009aa29  lea     r8d, [r13+60h]; Size
0x18009aa2d  lea     rcx, [rbp+370h+var_358]; void *
0x18009aa31  call    memset_0
0x18009aa36  nop
0x18009aa37  xor     r8d, r8d
0x18009aa3a  lea     rdx, [rbp+370h+var_380]
0x18009aa3e  lea     rcx, [rbp+370h+var_180]
0x18009aa45  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18009aa4a  nop
0x18009aa4b  mov     [rsp+470h+var_3F8], r13
0x18009aa50  mov     rax, [r15]
0x18009aa53  lea     r8, [rsp+470h+var_3F8]
0x18009aa58  lea     rdx, _GUID_cb0df960_16f5_4495_9079_3f9360d831df
0x18009aa5f  mov     rcx, r15
0x18009aa62  mov     rax, [rax]
0x18009aa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa6a  mov     [rbp+370h+var_178], eax
0x18009aa70  test    eax, eax
0x18009aa72  js      loc_18009B6DC
0x18009aa78  mov     [rbp+370h+var_178], eax
0x18009aa7e  mov     [rsp+470h+bstrString], r13
0x18009aa83  lea     rdi, [r15+8]
0x18009aa87  mov     rax, [rdi]
0x18009aa8a  lea     rdx, [rsp+470h+bstrString]
0x18009aa8f  mov     rcx, rdi
0x18009aa92  mov     rax, [rax+60h]
0x18009aa96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa9b  mov     [rbp+370h+var_178], eax
0x18009aaa1  test    eax, eax
0x18009aaa3  js      loc_18009B71A
0x18009aaa9  mov     [rbp+370h+var_178], eax
0x18009aaaf  mov     [rsp+470h+var_408], r13d
0x18009aab4  mov     r8b, 1; bool
0x18009aab7  lea     rdx, [rsp+470h+var_408]; int *
0x18009aabc  mov     rcx, r15; this
0x18009aabf  call    ?GetRuleFlagsInternal@CFciRule@@QEAAXPEAJ_N@Z; CFciRule::GetRuleFlagsInternal(long *,bool)
0x18009aac4  mov     r12d, [rsp+470h+var_408]
0x18009aac9  bt      r12d, 8
0x18009aace  jnb     short loc_18009AB2F
0x18009aad0  mov     rax, [rsp+470h+bstrString]
0x18009aad5  mov     [rsp+470h+var_450], rax
0x18009aada  lea     r9, aRuleSIsDisable; "Rule '%s' is disabled and won't be regi"...
0x18009aae1  mov     edx, 8Ch; unsigned int
0x18009aae6  mov     r8d, 16Dh; unsigned int
0x18009aaec  lea     rcx, [rbp+370h+var_180]; this
0x18009aaf3  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18009aaf8  nop
0x18009aaf9  mov     rcx, [rsp+470h+bstrString]; bstrString
0x18009aafe  call    cs:__imp_SysFreeString
0x18009ab04  nop
0x18009ab05  mov     rcx, [rsp+470h+var_3F8]
0x18009ab0a  test    rcx, rcx
0x18009ab0d  jz      short loc_18009AB1C
0x18009ab0f  mov     rax, [rcx]
0x18009ab12  mov     rax, [rax+10h]
0x18009ab16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab1b  nop
0x18009ab1c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18009ab23  mov     [rbp+370h+var_180], rax
0x18009ab2a  jmp     loc_18009B668
0x18009ab2f  mov     [rsp+470h+var_410], r13
0x18009ab34  mov     rax, [rdi]
0x18009ab37  lea     rdx, [rsp+470h+var_410]
0x18009ab3c  mov     rcx, rdi
0x18009ab3f  mov     rax, [rax+78h]
0x18009ab43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab48  mov     [rbp+370h+var_178], eax
0x18009ab4e  test    eax, eax
0x18009ab50  js      loc_18009B758
0x18009ab56  mov     [rbp+370h+var_178], eax
0x18009ab5c  mov     [rbp+370h+var_3B8], r13d
0x18009ab60  mov     rax, [rdi]
0x18009ab63  lea     rdx, [rbp+370h+var_3B8]
0x18009ab67  mov     rcx, rdi
0x18009ab6a  mov     rax, [rax+70h]
0x18009ab6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab73  mov     [rbp+370h+var_178], eax
0x18009ab79  test    eax, eax
0x18009ab7b  js      loc_18009B796
0x18009ab81  mov     [rbp+370h+var_178], eax
0x18009ab87  lea     rcx, [rbp+370h+pvarg]; pvarg
0x18009ab8b  call    cs:__imp_VariantInit
0x18009ab91  nop
0x18009ab92  mov     rax, [rdi]
0x18009ab95  lea     rdx, [rbp+370h+pvarg]
0x18009ab99  mov     rcx, rdi
0x18009ab9c  mov     rax, [rax+0B8h]
0x18009aba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aba8  mov     [rbp+370h+var_178], eax
0x18009abae  test    eax, eax
0x18009abb0  js      loc_18009B7D4
0x18009abb6  mov     [rbp+370h+var_178], eax
0x18009abbc  mov     ebx, 15h
0x18009abc1  cmp     word ptr [rbp+370h+pvarg], bx
0x18009abc5  jnz     short loc_18009ABCD
0x18009abc7  mov     rbx, qword ptr [rbp+370h+pvarg+8]
0x18009abcb  jmp     short loc_18009AC0D
0x18009abcd  lea     rcx, [rbp+370h+pvargDest]; pvarg
0x18009abd4  call    cs:__imp_VariantInit
0x18009abda  nop
0x18009abdb  mov     r9d, ebx; vt
0x18009abde  xor     r8d, r8d; wFlags
0x18009abe1  lea     rdx, [rbp+370h+pvarg]; pvarSrc
0x18009abe5  lea     rcx, [rbp+370h+pvargDest]; pvargDest
0x18009abec  call    cs:__imp_VariantChangeType
0x18009abf2  test    eax, eax
0x18009abf4  js      loc_18009B812
0x18009abfa  mov     rbx, qword ptr [rbp+370h+pvargDest+8]
0x18009ac01  lea     rcx, [rbp+370h+pvargDest]; this
0x18009ac08  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009ac0d  mov     dword ptr [rbp+370h+var_3C8], ebx
0x18009ac10  shr     rbx, 20h
0x18009ac14  mov     dword ptr [rbp+370h+var_3C8+4], ebx
0x18009ac17  mov     rdx, [rsp+470h+var_410]
0x18009ac1c  lea     rcx, [rbp+370h+String2]; void *
0x18009ac23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18009ac28  nop
0x18009ac29  mov     r14, [rsi+68h]
0x18009ac2d  mov     rbx, [r14+8]
0x18009ac31  jmp     short loc_18009AC6E
0x18009ac33  lea     rcx, [rbx+18h]
0x18009ac37  lea     rdx, [rbp+370h+String2]
0x18009ac3e  cmp     [rbp+370h+var_B8], 8
0x18009ac46  cmovnb  rdx, [rbp+370h+String2]; String2
0x18009ac4e  cmp     qword ptr [rcx+18h], 8
0x18009ac53  jb      short loc_18009AC58
0x18009ac55  mov     rcx, [rcx]; String1
0x18009ac58  call    cs:__imp__wcsicmp
0x18009ac5e  test    eax, eax
0x18009ac60  jns     short loc_18009AC68
0x18009ac62  mov     rbx, [rbx+10h]
0x18009ac66  jmp     short loc_18009AC6E
0x18009ac68  mov     r14, rbx
0x18009ac6b  mov     rbx, [rbx]
0x18009ac6e  cmp     [rbx+49h], r13b
0x18009ac72  jz      short loc_18009AC33
0x18009ac74  mov     rbx, [rsi+68h]
0x18009ac78  cmp     r14, rbx
0x18009ac7b  jz      short loc_18009ACB5
0x18009ac7d  lea     rdx, [r14+18h]
0x18009ac81  cmp     qword ptr [rdx+18h], 8
0x18009ac86  jb      short loc_18009AC8B
0x18009ac88  mov     rdx, [rdx]; String2
0x18009ac8b  lea     rcx, [rbp+370h+String2]
0x18009ac92  cmp     [rbp+370h+var_B8], 8
0x18009ac9a  cmovnb  rcx, [rbp+370h+String2]; String1
0x18009aca2  call    cs:__imp__wcsicmp
0x18009aca8  test    eax, eax
0x18009acaa  jns     short loc_18009ACB2
0x18009acac  mov     rbx, [rsi+68h]
0x18009acb0  jmp     short loc_18009ACB5
0x18009acb2  mov     rbx, r14
0x18009acb5  mov     r14, [rsi+68h]
0x18009acb9  cmp     [rbp+370h+var_B8], 8
0x18009acc1  jb      short loc_18009ACCF
0x18009acc3  mov     rcx, [rbp+370h+String2]; Block
0x18009acca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009accf  mov     [rbp+370h+var_B8], 7
0x18009acda  mov     [rbp+370h+var_C0], r13
0x18009ace1  mov     word ptr [rbp+370h+String2], r13w
0x18009ace9  cmp     rbx, r14
0x18009acec  jnz     loc_18009ADF4
0x18009acf2  lea     rax, [rbp+370h+var_2C8]
0x18009acf9  mov     qword ptr [rsp+470h+var_408], rax
0x18009acfe  lea     rax, aBaseFsFsrmServ_23; "base\\fs\\fsrm\\service\\pipeline\\plco"...
0x18009ad05  mov     [rbp+370h+var_380], rax
0x18009ad09  lea     rax, aCpipelineconfi; "CPipelineConfiguration::RegisterRule"
0x18009ad10  mov     [rbp+370h+var_378], rax
0x18009ad14  lea     rax, aPlconfgc; "PLCONFGC"
0x18009ad1b  mov     [rbp+370h+var_370], rax
0x18009ad1f  mov     [rbp+370h+var_368], 187h
0x18009ad26  mov     [rbp+370h+var_364], 16h
0x18009ad2d  mov     [rbp+370h+var_360], 0FFh
0x18009ad34  mov     [rbp+370h+var_2F8], 1000000h
0x18009ad3b  xor     edx, edx; Val
0x18009ad3d  lea     r8d, [rdx+60h]; Size
0x18009ad41  lea     rcx, [rbp+370h+var_358]; void *
0x18009ad45  call    memset_0
0x18009ad4a  nop
0x18009ad4b  mov     r8, [rsp+470h+bstrString]; unsigned __int16 *
0x18009ad50  lea     rdx, [rbp+370h+var_238]; this
0x18009ad57  lea     rcx, [rbp+370h+var_380]; struct CSrmDebugInfo *
0x18009ad5b  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18009ad60  nop
0x18009ad61  mov     r8, [rsp+470h+var_410]; unsigned __int16 *
0x18009ad66  lea     rdx, [rbp+370h+var_2C8]; this
0x18009ad6d  mov     rcx, rax; struct CSrmDebugInfo *
0x18009ad70  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18009ad75  nop
0x18009ad76  mov     r9d, 2
0x18009ad7c  mov     r8, rax
0x18009ad7f  mov     edx, 80043030h
0x18009ad84  lea     rcx, [rbp+370h+var_180]
0x18009ad8b  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18009ad90  nop
0x18009ad91  lea     rcx, [rbp+370h+var_238]; this
0x18009ad98  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18009ad9d  nop
0x18009ad9e  lea     rcx, [rbp+370h+var_380]; this
0x18009ada2  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18009ada7  nop
0x18009ada8  lea     rcx, [rbp+370h+pvarg]; this
0x18009adac  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18009adb1  nop
0x18009adb2  mov     rcx, [rsp+470h+var_410]; bstrString
0x18009adb7  call    cs:__imp_SysFreeString
0x18009adbd  nop
0x18009adbe  mov     rcx, [rsp+470h+bstrString]; bstrString
0x18009adc3  call    cs:__imp_SysFreeString
0x18009adc9  nop
0x18009adca  mov     rcx, [rsp+470h+var_3F8]
0x18009adcf  test    rcx, rcx
0x18009add2  jz      short loc_18009ADE1
0x18009add4  mov     rax, [rcx]
0x18009add7  mov     rax, [rax+10h]
0x18009addb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ade0  nop
0x18009ade1  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18009ade8  mov     [rbp+370h+var_180], rax
0x18009adef  jmp     loc_18009B668
0x18009adf4  xorps   xmm0, xmm0
0x18009adf7  movups  xmmword ptr [rbp+370h+var_48.Data1], xmm0
0x18009adfe  mov     [rbp+370h+var_3E8], r13
0x18009ae02  mov     [rbp+370h+var_3F0], r13
0x18009ae06  mov     [rbp+370h+var_3C0], r13
0x18009ae0a  mov     [rbp+370h+var_3E0], r13d
0x18009ae0e  mov     rax, [rdi]
0x18009ae11  lea     rdx, [rbp+370h+var_48]
0x18009ae18  mov     rcx, rdi
0x18009ae1b  mov     rax, [rax+38h]
0x18009ae1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae24  mov     [rbp+370h+var_178], eax
0x18009ae2a  test    eax, eax
0x18009ae2c  js      loc_18009B81A
0x18009ae32  mov     [rbp+370h+var_178], eax
0x18009ae38  mov     rax, [r15]
0x18009ae3b  lea     r8, [rbp+370h+var_3E8]
0x18009ae3f  lea     rdx, _GUID_afc052c2_5315_45ab_841b_c6db0e120148
0x18009ae46  mov     rcx, r15
0x18009ae49  mov     rax, [rax]
0x18009ae4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae51  mov     [rbp+370h+var_178], eax
0x18009ae57  test    eax, eax
0x18009ae59  js      loc_18009B858
0x18009ae5f  mov     [rbp+370h+var_178], eax
0x18009ae65  mov     rcx, [rbp+370h+var_3E8]
0x18009ae69  mov     rax, [rcx]
0x18009ae6c  lea     rdx, [rbp+370h+var_3F0]
0x18009ae70  mov     rax, [rax+0D0h]
0x18009ae77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae7c  mov     [rbp+370h+var_178], eax
0x18009ae82  test    eax, eax
0x18009ae84  js      loc_18009B896
0x18009ae8a  mov     [rbp+370h+var_178], eax
0x18009ae90  mov     rcx, [rbp+370h+var_3E8]
0x18009ae94  mov     rax, [rcx]
0x18009ae97  lea     rdx, [rbp+370h+var_3C0]
0x18009ae9b  mov     rax, [rax+0E0h]
0x18009aea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aea7  mov     [rbp+370h+var_178], eax
0x18009aead  test    eax, eax
0x18009aeaf  js      loc_18009B8D4
0x18009aeb5  mov     [rbp+370h+var_178], eax
0x18009aebb  mov     rcx, [rbp+370h+var_3E8]
0x18009aebf  mov     rax, [rcx]
0x18009aec2  lea     rdx, [rbp+370h+var_3E0]
0x18009aec6  mov     rax, [rax+0C0h]
0x18009aecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aed2  mov     [rbp+370h+var_178], eax
0x18009aed8  test    eax, eax
0x18009aeda  js      loc_18009B912
  ... truncated ...
```
