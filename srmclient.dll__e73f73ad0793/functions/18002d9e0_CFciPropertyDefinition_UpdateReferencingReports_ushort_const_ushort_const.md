# CFciPropertyDefinition::UpdateReferencingReports(ushort const *,ushort const *)

- ea: `0x18002d9e0`
- end: `0x18002e2bc`
- name: `?UpdateReferencingReports@CFciPropertyDefinition@@AEAAXPEBG0@Z`
- size: `2268`
- prototype: `void(CFciPropertyDefinition *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180027ac8`

## callees

- `0x1800020ba`
- `0x180004ec8`
- `0x180006a1c`
- `0x1800095f4`
- `0x18002d9e0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002dd1e`
- `msvcrt!_wcsicmp` at `0x18002dd1e`
- `ole32!CoCreateInstance` at `0x18002daaa`
- `ole32!CoCreateInstance` at `0x18002daaa`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dd3f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dd78`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dd3f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dd78`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dd9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dd9e`
- `OLEAUT32!__imp_VariantInit` at `0x18002db39`
- `OLEAUT32!__imp_VariantInit` at `0x18002dc3d`
- `OLEAUT32!__imp_VariantInit` at `0x18002dce5`
- `OLEAUT32!__imp_VariantInit` at `0x18002db39`
- `OLEAUT32!__imp_VariantInit` at `0x18002dc3d`
- `OLEAUT32!__imp_VariantInit` at `0x18002dce5`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd65`
- `OLEAUT32!__imp_VariantClear` at `0x18002de11`
- `OLEAUT32!__imp_VariantClear` at `0x18002de1e`
- `OLEAUT32!__imp_VariantClear` at `0x18002de30`
- `OLEAUT32!__imp_VariantClear` at `0x18002de93`
- `OLEAUT32!__imp_VariantClear` at `0x18002dd65`
- `OLEAUT32!__imp_VariantClear` at `0x18002de11`
- `OLEAUT32!__imp_VariantClear` at `0x18002de1e`
- `OLEAUT32!__imp_VariantClear` at `0x18002de30`
- `OLEAUT32!__imp_VariantClear` at `0x18002de93`

## string_xrefs

- `0x18002da18`: `base\fs\fsrm\service\globalstore\fcipropertydefinition.cpp`
- `0x18002da23`: `CFciPropertyDefinition::UpdateReferencingReports`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CFciPropertyDefinition::UpdateReferencingReports(
        CFciPropertyDefinition *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  int i; // r14d
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int j; // esi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  OLECHAR *v18; // rbx
  const OLECHAR *v19; // rdi
  BSTR v20; // rax
  int v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  char v25; // al
  int v26; // eax
  char v27; // al
  int Hr; // eax
  char v29; // al
  int v30; // eax
  char v31; // al
  int v32; // eax
  char v33; // al
  int v34; // eax
  char v35; // al
  int v36; // eax
  char v37; // al
  int v38; // eax
  char v39; // al
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // eax
  char v45; // al
  int v46; // eax
  char v47; // al
  int v48; // eax
  char v49; // al
  int v50; // eax
  char v51; // al
  int v52; // [rsp+30h] [rbp-D0h] BYREF
  int v53; // [rsp+34h] [rbp-CCh] BYREF
  int v54; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  BSTR pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v61; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v63; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v64; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v65; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v66[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v67; // [rsp+110h] [rbp+10h]
  _BYTE v68[96]; // [rsp+118h] [rbp+18h] BYREF
  int v69; // [rsp+178h] [rbp+78h]
  void **v70; // [rsp+180h] [rbp+80h] BYREF
  HRESULT v71; // [rsp+188h] [rbp+88h]

  v66[0] = L"base\\fs\\fsrm\\service\\globalstore\\fcipropertydefinition.cpp";
  v66[1] = L"CFciPropertyDefinition::UpdateReferencingReports";
  v66[2] = L"CFCIPRPD";
  v66[3] = 1751;
  v67 = 255;
  v69 = 0x1000000;
  memset_0(v68, 0, sizeof(v68));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v70, (const struct CSrmDebugInfo *)v66, 0);
  ppv = 0;
  v58 = 0;
  v54 = 0;
  v5 = CoCreateInstance(&CLSID_FsrmReportManager, 0, 0x15u, &IID_IFsrmReportManager, &ppv);
  v71 = v5;
  if ( v5 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, Hr);
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6E5u, v29, 0);
  }
  v71 = v5;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 4, &v58);
  v71 = v6;
  if ( v6 < 0 )
  {
    v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v30);
    v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6E7u, v31, 0);
  }
  v71 = v6;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 72LL))(v58, &v54);
  v71 = v7;
  if ( v7 < 0 )
  {
    v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v32);
    v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6E9u, v33, 0);
  }
  v71 = v7;
  for ( i = 1; i <= v54; ++i )
  {
    VariantInit(&pvarg);
    v57 = 0;
    v56 = 0;
    v53 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v58 + 64LL))(
           v58,
           (unsigned int)i,
           &pvarg);
    v71 = v9;
    if ( v9 < 0 )
    {
      v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v26);
      v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6F2u, v27, 0);
    }
    v71 = v9;
    if ( pvarg.vt != 9 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147418113);
      v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6F4u, v25, 0);
    }
    v71 = 0;
    v10 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_IFsrmReportJob, &v57);
    v71 = v10;
    if ( v10 < 0 )
    {
      v50 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v50);
      v51 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6F6u, v51, 0);
    }
    v71 = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 192LL))(v57, &v56);
    v71 = v11;
    if ( v11 < 0 )
    {
      v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v48);
      v49 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6F8u, v49, 0);
    }
    v71 = v11;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 72LL))(v56, &v53);
    v71 = v12;
    if ( v12 < 0 )
    {
      v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v46);
      v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6FAu, v47, 0);
    }
    v71 = v12;
    for ( j = 1; j <= v53; ++j )
    {
      v55 = 0;
      VariantInit(&v64);
      v52 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v56 + 64LL))(
              v56,
              (unsigned int)j,
              &v64);
      v71 = v14;
      if ( v14 < 0 )
      {
        v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v44);
        v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x702u, v45, 0);
      }
      v71 = v14;
      v15 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v64.llVal)(
              v64.llVal,
              &GUID_d8cc81d9_46b8_4fa4_bfa5_4aa9dec9b638,
              &v55);
      v71 = v15;
      if ( v15 < 0 )
      {
        v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v42);
        v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x704u, v43, 0);
      }
      v71 = v15;
      v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v52);
      v71 = v16;
      if ( v16 < 0 )
      {
        v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v40);
        v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x706u, v41, 0);
      }
      v71 = v16;
      if ( v52 == 10 || v52 == 13 )
      {
        VariantInit(&v63);
        v17 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v55 + 104LL))(v55, 8, &v63);
        v71 = v17;
        if ( v17 < 0 )
        {
          v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v38);
          v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x70Cu, v39, 0);
        }
        v71 = v17;
        if ( !_wcsicmp(v63.bstrVal, a2) )
        {
          if ( a3 )
          {
            v20 = SysAllocString(a3);
            v18 = v20;
            pExceptionObject = v20;
            if ( !v20 )
            {
              LODWORD(pExceptionObject) = -2147024882;
              throw (long *)&pExceptionObject;
            }
            v19 = v20;
          }
          else
          {
            v18 = 0;
            pExceptionObject = 0;
            v19 = 0;
          }
          v61.vt = 0;
          VariantClear(&v61);
          v61.vt = 8;
          v61.llVal = (LONGLONG)SysAllocString(v19);
          if ( !v61.llVal && v19 )
          {
            v61.vt = 10;
            v61.lVal = -2147024882;
            ATL::AtlThrowImpl(-2147024882);
          }
          SysFreeString(v18);
          v65 = v61;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v55 + 112LL))(v55, 8, &v65);
          v71 = v21;
          if ( v21 < 0 )
          {
            v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v36);
            v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x712u, v37, 0);
          }
          v71 = v21;
          v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 88LL))(v57);
          v71 = v22;
          if ( v22 < 0 )
          {
            v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v34);
            v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x714u, v35, 0);
          }
          v71 = v22;
          VariantClear(&v61);
        }
        v23 = VariantClear(&v63);
        if ( v23 < 0 )
          _com_issue_error(v23);
      }
      v24 = VariantClear(&v64);
      if ( v24 < 0 )
        _com_issue_error(v24);
      if ( v55 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    VariantClear(&pvarg);
  }
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v70 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v70);
}

```

## disassembly

```asm
0x18002d9e0  mov     [rsp-8+arg_0], rbx
0x18002d9e5  mov     [rsp-8+arg_18], rsi
0x18002d9ea  push    rbp
0x18002d9eb  push    rdi
0x18002d9ec  push    r12
0x18002d9ee  push    r14
0x18002d9f0  push    r15
0x18002d9f2  lea     rbp, [rsp-140h]
0x18002d9fa  sub     rsp, 240h
0x18002da01  mov     rax, cs:__security_cookie
0x18002da08  xor     rax, rsp
0x18002da0b  mov     [rbp+160h+var_30], rax
0x18002da12  mov     r15, r8
0x18002da15  mov     r12, rdx
0x18002da18  lea     rax, aBaseFsFsrmServ_4; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x18002da1f  mov     [rbp+160h+var_170], rax
0x18002da23  lea     rax, aCfcipropertyde_47; "CFciPropertyDefinition::UpdateReferenci"...
0x18002da2a  mov     [rbp+160h+var_168], rax
0x18002da2e  lea     rax, aCfciprpd; "CFCIPRPD"
0x18002da35  mov     [rbp+160h+var_160], rax
0x18002da39  mov     [rbp+160h+var_158], 6D7h
0x18002da41  mov     [rbp+160h+var_150], 0FFh
0x18002da48  mov     [rbp+160h+var_E8], 1000000h
0x18002da4f  xor     edx, edx; Val
0x18002da51  lea     r8d, [rdx+60h]; Size
0x18002da55  lea     rcx, [rbp+160h+var_148]; void *
0x18002da59  call    memset_0
0x18002da5e  xor     r8d, r8d
0x18002da61  lea     rdx, [rbp+160h+var_170]
0x18002da65  lea     rcx, [rbp+160h+var_E0]
0x18002da6c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18002da71  nop
0x18002da72  mov     [rsp+260h+var_200], 0
0x18002da7b  mov     [rsp+260h+var_208], 0
0x18002da84  mov     [rsp+260h+var_228], 0
0x18002da8c  lea     rax, [rsp+260h+var_200]
0x18002da91  mov     [rsp+260h+ppv], rax; ppv
0x18002da96  lea     r9, IID_IFsrmReportManager; riid
0x18002da9d  xor     edx, edx; pUnkOuter
0x18002da9f  lea     r8d, [rdx+15h]; dwClsContext
0x18002daa3  lea     rcx, CLSID_FsrmReportManager; rclsid
0x18002daaa  call    cs:__imp_CoCreateInstance
0x18002dab0  mov     [rbp+160h+var_D8], eax
0x18002dab6  test    eax, eax
0x18002dab8  js      loc_18002DF8D
0x18002dabe  mov     [rbp+160h+var_D8], eax
0x18002dac4  mov     rcx, [rsp+260h+var_200]
0x18002dac9  mov     rax, [rcx]
0x18002dacc  lea     r8, [rsp+260h+var_208]
0x18002dad1  mov     edx, 4
0x18002dad6  mov     rax, [rax+38h]
0x18002dada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dadf  mov     [rbp+160h+var_D8], eax
0x18002dae5  test    eax, eax
0x18002dae7  js      loc_18002DFCB
0x18002daed  mov     [rbp+160h+var_D8], eax
0x18002daf3  mov     rcx, [rsp+260h+var_208]
0x18002daf8  mov     rax, [rcx]
0x18002dafb  lea     rdx, [rsp+260h+var_228]
0x18002db00  mov     rax, [rax+48h]
0x18002db04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db09  mov     [rbp+160h+var_D8], eax
0x18002db0f  test    eax, eax
0x18002db11  js      loc_18002E009
0x18002db17  mov     [rbp+160h+var_D8], eax
0x18002db1d  mov     r14d, 1
0x18002db23  cmp     [rsp+260h+var_228], r14d
0x18002db28  jl      loc_18002DEA7
0x18002db2e  lea     ebx, [r14+9]
0x18002db32  lea     edi, [rbx-2]
0x18002db35  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18002db39  call    cs:__imp_VariantInit
0x18002db3f  nop
0x18002db40  mov     [rsp+260h+var_210], 0
0x18002db49  mov     [rsp+260h+var_218], 0
0x18002db52  mov     [rsp+260h+var_22C], 0
0x18002db5a  mov     rcx, [rsp+260h+var_208]
0x18002db5f  mov     rax, [rcx]
0x18002db62  lea     r8, [rbp+160h+pvarg]
0x18002db66  mov     edx, r14d
0x18002db69  mov     rax, [rax+40h]
0x18002db6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db72  mov     [rbp+160h+var_D8], eax
0x18002db78  test    eax, eax
0x18002db7a  js      loc_18002DF4F
0x18002db80  mov     [rbp+160h+var_D8], eax
0x18002db86  cmp     word ptr [rbp+160h+pvarg], 9
0x18002db8b  jnz     loc_18002DF1A
0x18002db91  mov     [rbp+160h+var_D8], 0
0x18002db9b  mov     rcx, qword ptr [rbp+160h+pvarg+8]
0x18002db9f  mov     rax, [rcx]
0x18002dba2  lea     r8, [rsp+260h+var_210]
0x18002dba7  lea     rdx, IID_IFsrmReportJob
0x18002dbae  mov     rax, [rax]
0x18002dbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbb6  mov     [rbp+160h+var_D8], eax
0x18002dbbc  test    eax, eax
0x18002dbbe  js      loc_18002E27E
0x18002dbc4  mov     [rbp+160h+var_D8], eax
0x18002dbca  mov     rcx, [rsp+260h+var_210]
0x18002dbcf  mov     rax, [rcx]
0x18002dbd2  lea     rdx, [rsp+260h+var_218]
0x18002dbd7  mov     rax, [rax+0C0h]
0x18002dbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbe3  mov     [rbp+160h+var_D8], eax
0x18002dbe9  test    eax, eax
0x18002dbeb  js      loc_18002E240
0x18002dbf1  mov     [rbp+160h+var_D8], eax
0x18002dbf7  mov     rcx, [rsp+260h+var_218]
0x18002dbfc  mov     rax, [rcx]
0x18002dbff  lea     rdx, [rsp+260h+var_22C]
0x18002dc04  mov     rax, [rax+48h]
0x18002dc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc0d  mov     [rbp+160h+var_D8], eax
0x18002dc13  test    eax, eax
0x18002dc15  js      loc_18002E202
0x18002dc1b  mov     [rbp+160h+var_D8], eax
0x18002dc21  mov     esi, 1
0x18002dc26  cmp     [rsp+260h+var_22C], esi
0x18002dc2a  jl      loc_18002DE61
0x18002dc30  mov     [rsp+260h+var_220], 0
0x18002dc39  lea     rcx, [rbp+160h+var_1A8]; pvarg
0x18002dc3d  call    cs:__imp_VariantInit
0x18002dc43  nop
0x18002dc44  mov     [rsp+260h+var_230], 0
0x18002dc4c  mov     rcx, [rsp+260h+var_218]
0x18002dc51  mov     rax, [rcx]
0x18002dc54  lea     r8, [rbp+160h+var_1A8]
0x18002dc58  mov     edx, esi
0x18002dc5a  mov     rax, [rax+40h]
0x18002dc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc63  mov     [rbp+160h+var_D8], eax
0x18002dc69  test    eax, eax
0x18002dc6b  js      loc_18002E1C4
0x18002dc71  mov     [rbp+160h+var_D8], eax
0x18002dc77  mov     rcx, qword ptr [rbp+160h+var_1A8+8]
0x18002dc7b  mov     rax, [rcx]
0x18002dc7e  lea     r8, [rsp+260h+var_220]
0x18002dc83  lea     rdx, _GUID_d8cc81d9_46b8_4fa4_bfa5_4aa9dec9b638
0x18002dc8a  mov     rax, [rax]
0x18002dc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc92  mov     [rbp+160h+var_D8], eax
0x18002dc98  test    eax, eax
0x18002dc9a  js      loc_18002E186
0x18002dca0  mov     [rbp+160h+var_D8], eax
0x18002dca6  mov     rcx, [rsp+260h+var_220]
0x18002dcab  mov     rax, [rcx]
0x18002dcae  lea     rdx, [rsp+260h+var_230]
0x18002dcb3  mov     rax, [rax+38h]
0x18002dcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcbc  mov     [rbp+160h+var_D8], eax
0x18002dcc2  test    eax, eax
0x18002dcc4  js      loc_18002E148
0x18002dcca  mov     [rbp+160h+var_D8], eax
0x18002dcd0  cmp     [rsp+260h+var_230], ebx
0x18002dcd4  jz      short loc_18002DCE1
0x18002dcd6  cmp     [rsp+260h+var_230], 0Dh
0x18002dcdb  jnz     loc_18002DE2C
0x18002dce1  lea     rcx, [rbp+160h+var_1C0]; pvarg
0x18002dce5  call    cs:__imp_VariantInit
0x18002dceb  nop
0x18002dcec  mov     rcx, [rsp+260h+var_220]
0x18002dcf1  mov     rax, [rcx]
0x18002dcf4  lea     r8, [rbp+160h+var_1C0]
0x18002dcf8  mov     edx, edi
0x18002dcfa  mov     rax, [rax+68h]
0x18002dcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd03  mov     [rbp+160h+var_D8], eax
0x18002dd09  test    eax, eax
0x18002dd0b  js      loc_18002E10A
0x18002dd11  mov     [rbp+160h+var_D8], eax
0x18002dd17  mov     rdx, r12; String2
0x18002dd1a  mov     rcx, qword ptr [rbp+160h+var_1C0+8]; String1
0x18002dd1e  call    cs:__imp__wcsicmp
0x18002dd24  test    eax, eax
0x18002dd26  jnz     loc_18002DE1A
0x18002dd2c  test    r15, r15
0x18002dd2f  jnz     short loc_18002DD3C
0x18002dd31  xor     ebx, ebx
0x18002dd33  mov     [rsp+260h+pExceptionObject], rbx
0x18002dd38  xor     edi, edi
0x18002dd3a  jmp     short loc_18002DD59
0x18002dd3c  mov     rcx, r15; psz
0x18002dd3f  call    cs:__imp_SysAllocString
0x18002dd45  mov     rbx, rax
0x18002dd48  mov     [rsp+260h+pExceptionObject], rax
0x18002dd4d  test    rax, rax
0x18002dd50  jz      loc_18002E0E0
0x18002dd56  mov     rdi, rax
0x18002dd59  xor     eax, eax
0x18002dd5b  mov     word ptr [rsp+260h+var_1F0], ax
0x18002dd60  lea     rcx, [rsp+260h+var_1F0]; pvarg
0x18002dd65  call    cs:__imp_VariantClear
0x18002dd6b  mov     eax, 8
0x18002dd70  mov     word ptr [rsp+260h+var_1F0], ax
0x18002dd75  mov     rcx, rdi; psz
0x18002dd78  call    cs:__imp_SysAllocString
0x18002dd7e  mov     dword ptr [rsp+260h+var_1F0+8], eax
0x18002dd82  mov     rcx, rax
0x18002dd85  sar     rcx, 20h
0x18002dd89  mov     dword ptr [rsp+260h+var_1F0+0Ch], ecx
0x18002dd8d  test    rax, rax
0x18002dd90  jnz     short loc_18002DD9B
0x18002dd92  test    rdi, rdi
0x18002dd95  jnz     loc_18002E047
0x18002dd9b  mov     rcx, rbx; bstrString
0x18002dd9e  call    cs:__imp_SysFreeString
0x18002dda4  mov     rcx, [rsp+260h+var_220]
0x18002dda9  movups  xmm0, xmmword ptr [rsp+260h+var_1F0]
0x18002ddae  movaps  [rbp+160h+var_190], xmm0
0x18002ddb2  movsd   xmm1, qword ptr [rbp+160h+var_1F0+10h]
0x18002ddb7  movsd   [rbp+160h+var_180], xmm1
0x18002ddbc  mov     rax, [rcx]
0x18002ddbf  lea     r8, [rbp+160h+var_190]
0x18002ddc3  mov     edi, 8
0x18002ddc8  mov     edx, edi
0x18002ddca  mov     rax, [rax+70h]
0x18002ddce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddd3  mov     [rbp+160h+var_D8], eax
0x18002ddd9  test    eax, eax
0x18002dddb  js      loc_18002E0A2
0x18002dde1  mov     [rbp+160h+var_D8], eax
0x18002dde7  mov     rcx, [rsp+260h+var_210]
0x18002ddec  mov     rax, [rcx]
0x18002ddef  mov     rax, [rax+58h]
0x18002ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddf8  mov     [rbp+160h+var_D8], eax
0x18002ddfe  test    eax, eax
0x18002de00  js      loc_18002E064
0x18002de06  mov     [rbp+160h+var_D8], eax
0x18002de0c  lea     rcx, [rsp+260h+var_1F0]; pvarg
0x18002de11  call    cs:__imp_VariantClear
0x18002de17  lea     ebx, [rdi+2]
0x18002de1a  lea     rcx, [rbp+160h+var_1C0]; pvarg
0x18002de1e  call    cs:__imp_VariantClear
0x18002de24  test    eax, eax
0x18002de26  js      loc_18002E102
0x18002de2c  lea     rcx, [rbp+160h+var_1A8]; pvarg
0x18002de30  call    cs:__imp_VariantClear
0x18002de36  test    eax, eax
0x18002de38  js      loc_18002E0FA
0x18002de3e  mov     rcx, [rsp+260h+var_220]
0x18002de43  test    rcx, rcx
0x18002de46  jz      short loc_18002DE55
0x18002de48  mov     rax, [rcx]
0x18002de4b  mov     rax, [rax+10h]
0x18002de4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de54  nop
0x18002de55  inc     esi
0x18002de57  cmp     esi, [rsp+260h+var_22C]
0x18002de5b  jle     loc_18002DC30
0x18002de61  mov     rcx, [rsp+260h+var_218]
0x18002de66  test    rcx, rcx
0x18002de69  jz      short loc_18002DE78
0x18002de6b  mov     rax, [rcx]
0x18002de6e  mov     rax, [rax+10h]
0x18002de72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de77  nop
0x18002de78  mov     rcx, [rsp+260h+var_210]
0x18002de7d  test    rcx, rcx
0x18002de80  jz      short loc_18002DE8F
0x18002de82  mov     rax, [rcx]
0x18002de85  mov     rax, [rax+10h]
0x18002de89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de8e  nop
0x18002de8f  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18002de93  call    cs:__imp_VariantClear
0x18002de99  inc     r14d
0x18002de9c  cmp     r14d, [rsp+260h+var_228]
0x18002dea1  jle     loc_18002DB35
0x18002dea7  mov     rcx, [rsp+260h+var_208]
0x18002deac  test    rcx, rcx
0x18002deaf  jz      short loc_18002DEBE
0x18002deb1  mov     rax, [rcx]
0x18002deb4  mov     rax, [rax+10h]
0x18002deb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002debd  nop
0x18002debe  mov     rcx, [rsp+260h+var_200]
0x18002dec3  test    rcx, rcx
0x18002dec6  jz      short loc_18002DED5
0x18002dec8  mov     rax, [rcx]
0x18002decb  mov     rax, [rax+10h]
0x18002decf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ded4  nop
0x18002ded5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18002dedc  mov     [rbp+160h+var_E0], rax
0x18002dee3  lea     rcx, [rbp+160h+var_E0]; this
0x18002deea  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18002deef  mov     rcx, [rbp+160h+var_30]
0x18002def6  xor     rcx, rsp; StackCookie
0x18002def9  call    __security_check_cookie
0x18002defe  lea     r11, [rsp+260h+var_20]
0x18002df06  mov     rbx, [r11+30h]
0x18002df0a  mov     rsi, [r11+48h]
0x18002df0e  mov     rsp, r11
0x18002df11  pop     r15
0x18002df13  pop     r14
0x18002df15  pop     r12
0x18002df17  pop     rdi
0x18002df18  pop     rbp
  ... truncated ...
```
