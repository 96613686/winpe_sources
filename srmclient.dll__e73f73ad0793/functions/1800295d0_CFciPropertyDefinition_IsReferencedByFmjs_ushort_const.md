# CFciPropertyDefinition::IsReferencedByFmjs(ushort const *)

- ea: `0x1800295d0`
- end: `0x180029d30`
- name: `?IsReferencedByFmjs@CFciPropertyDefinition@@AEAAHPEBG@Z`
- size: `1888`
- prototype: `int(CFciPropertyDefinition *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029d38`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x1800295d0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800298a8`
- `msvcrt!_wcsicmp` at `0x1800298c3`
- `msvcrt!_wcsicmp` at `0x1800298a8`
- `msvcrt!_wcsicmp` at `0x1800298c3`
- `ole32!CoCreateInstance` at `0x180029689`
- `ole32!CoCreateInstance` at `0x180029689`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299d7`
- `OLEAUT32!__imp_VariantInit` at `0x180029705`
- `OLEAUT32!__imp_VariantInit` at `0x1800297ca`
- `OLEAUT32!__imp_VariantInit` at `0x180029705`
- `OLEAUT32!__imp_VariantInit` at `0x1800297ca`
- `OLEAUT32!__imp_VariantClear` at `0x180029905`
- `OLEAUT32!__imp_VariantClear` at `0x18002991b`
- `OLEAUT32!__imp_VariantClear` at `0x1800299fa`
- `OLEAUT32!__imp_VariantClear` at `0x180029a05`
- `OLEAUT32!__imp_VariantClear` at `0x180029905`
- `OLEAUT32!__imp_VariantClear` at `0x18002991b`
- `OLEAUT32!__imp_VariantClear` at `0x1800299fa`
- `OLEAUT32!__imp_VariantClear` at `0x180029a05`

## string_xrefs

- `0x180029602`: `base\fs\fsrm\service\globalstore\fcipropertydefinition.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CFciPropertyDefinition::IsReferencedByFmjs(CFciPropertyDefinition *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const wchar_t *v17; // rcx
  char v19; // al
  int v20; // eax
  char v21; // al
  int Hr; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  int v26; // eax
  char v27; // al
  char v28; // al
  int v29; // eax
  char v30; // al
  int v31; // eax
  char v32; // al
  int v33; // eax
  char v34; // al
  char v35; // al
  int v36; // eax
  char v37; // al
  int v38; // eax
  char v39; // al
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // [rsp+30h] [rbp-D0h] BYREF
  int v45; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v53; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v55[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v56; // [rsp+C0h] [rbp-40h]
  _BYTE v57[96]; // [rsp+C8h] [rbp-38h] BYREF
  int v58; // [rsp+128h] [rbp+28h]
  void **v59; // [rsp+130h] [rbp+30h] BYREF
  HRESULT v60; // [rsp+138h] [rbp+38h]

  v55[0] = L"base\\fs\\fsrm\\service\\globalstore\\fcipropertydefinition.cpp";
  v55[1] = L"CFciPropertyDefinition::IsReferencedByFmjs";
  v55[2] = L"CFCIPRPD";
  v55[3] = 1970;
  v56 = 255;
  v58 = 0x1000000;
  memset_0(v57, 0, sizeof(v57));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v59, (const struct CSrmDebugInfo *)v55, 0);
  ppv = 0;
  v48 = 0;
  v45 = 0;
  v4 = CoCreateInstance(&CLSID_FsrmFileManagementJobManager, 0, 0x15u, &IID_IFsrmFileManagementJobManager, &ppv);
  v60 = v4;
  if ( v4 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, Hr);
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7BFu, v23, 0);
  }
  v60 = v4;
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, 4, &v48);
  v60 = v5;
  if ( v5 < 0 )
  {
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v24);
    v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7C1u, v25, 0);
  }
  v60 = v5;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 72LL))(v48, &v45);
  v60 = v6;
  if ( v6 < 0 )
  {
    v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v26);
    v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7C3u, v27, 0);
  }
  v60 = v6;
  v7 = 1;
  if ( v45 < 1 )
  {
LABEL_30:
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v59 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v59);
    return 0;
  }
  else
  {
    while ( 1 )
    {
      v52 = 0;
      v47 = 0;
      VariantInit(&pvarg);
      v44 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v48 + 64LL))(v48, v7, &pvarg);
      v60 = v8;
      if ( v8 < 0 )
      {
        v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v20);
        v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7CFu, v21, 0);
      }
      v60 = v8;
      if ( pvarg.vt != 9 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, -2147418113);
        v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7D1u, v19, 0);
      }
      v60 = 0;
      v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
             pvarg.llVal,
             &IID_IFsrmFileManagementJobInternal,
             &v52);
      v60 = v9;
      if ( v9 < 0 )
      {
        v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v42);
        v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7D3u, v43, 0);
      }
      v60 = v9;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 72LL))(v52, &v47);
      v60 = v10;
      if ( v10 < 0 )
      {
        v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v40);
        v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7D5u, v41, 0);
      }
      v60 = v10;
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 72LL))(v47, &v44);
      v60 = v11;
      if ( v11 < 0 )
      {
        v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v38);
        v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7D7u, v39, 0);
      }
      v60 = v11;
      v12 = 1;
      if ( v44 >= 1 )
        break;
LABEL_25:
      VariantClear(&pvarg);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( (int)++v7 > v45 )
        goto LABEL_30;
    }
    while ( 1 )
    {
      VariantInit(&v53);
      v46 = 0;
      String2 = 0;
      bstrString = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v47 + 64LL))(v47, v12, &v53);
      v60 = v13;
      if ( v13 < 0 )
      {
        v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v36);
        v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7E1u, v37, 0);
      }
      v60 = v13;
      if ( v53.vt != 9 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, -2147418113);
        v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7E3u, v35, 0);
      }
      v60 = 0;
      v14 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v53.llVal)(
              v53.llVal,
              &IID_IFsrmFMJConditionInternal,
              &v46);
      v60 = v14;
      if ( v14 < 0 )
      {
        v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v33);
        v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7E5u, v34, 0);
      }
      v60 = v14;
      v15 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v46 + 24LL))(v46, &String2);
      v60 = v15;
      if ( v15 < 0 )
      {
        v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v31);
        v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7E7u, v32, 0);
      }
      v60 = v15;
      v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v46 + 56LL))(v46, &bstrString);
      v60 = v16;
      if ( v16 < 0 )
      {
        v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, v29);
        v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7E9u, v30, 0);
      }
      v60 = v16;
      if ( !String2 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v59, -2147200234);
        v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v59);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v59, 0x7EBu, v28, 0);
      }
      v60 = 0;
      v17 = (const wchar_t *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) >= 8u )
        v17 = *(const wchar_t **)v17;
      if ( !_wcsicmp(v17, String2) && (!a2 || !_wcsicmp(a2, bstrString)) )
        break;
      SysFreeString(bstrString);
      SysFreeString(String2);
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      VariantClear(&v53);
      if ( (int)++v12 > v44 )
        goto LABEL_25;
    }
    SysFreeString(bstrString);
    SysFreeString(String2);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    VariantClear(&v53);
    VariantClear(&pvarg);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v59 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v59);
    return 1;
  }
}

```

## disassembly

```asm
0x1800295d0  mov     [rsp-8+arg_10], rbx
0x1800295d5  push    rbp
0x1800295d6  push    rsi
0x1800295d7  push    rdi
0x1800295d8  push    r14
0x1800295da  push    r15
0x1800295dc  lea     rbp, [rsp-0F0h]
0x1800295e4  sub     rsp, 1F0h
0x1800295eb  mov     rax, cs:__security_cookie
0x1800295f2  xor     rax, rsp
0x1800295f5  mov     [rbp+110h+var_30], rax
0x1800295fc  mov     rsi, rdx
0x1800295ff  mov     r14, rcx
0x180029602  lea     rax, aBaseFsFsrmServ_4; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x180029609  mov     [rbp+110h+var_170], rax
0x18002960d  lea     rax, aCfcipropertyde_39; "CFciPropertyDefinition::IsReferencedByF"...
0x180029614  mov     [rbp+110h+var_168], rax
0x180029618  lea     rax, aCfciprpd; "CFCIPRPD"
0x18002961f  mov     [rbp+110h+var_160], rax
0x180029623  mov     [rbp+110h+var_158], 7B2h
0x18002962b  xor     r15d, r15d
0x18002962e  mov     [rbp+110h+var_150], 0FFh
0x180029635  mov     [rbp+110h+var_E8], 1000000h
0x18002963c  xor     edx, edx; Val
0x18002963e  lea     r8d, [r15+60h]; Size
0x180029642  lea     rcx, [rbp+110h+var_148]; void *
0x180029646  call    memset_0
0x18002964b  xor     r8d, r8d
0x18002964e  lea     rdx, [rbp+110h+var_170]
0x180029652  lea     rcx, [rbp+110h+var_E0]
0x180029656  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18002965b  nop
0x18002965c  mov     [rsp+210h+var_1C0], r15
0x180029661  mov     [rsp+210h+var_1C8], r15
0x180029666  mov     [rsp+210h+var_1DC], r15d
0x18002966b  lea     rax, [rsp+210h+var_1C0]
0x180029670  mov     [rsp+210h+ppv], rax; ppv
0x180029675  lea     r9, IID_IFsrmFileManagementJobManager; riid
0x18002967c  xor     edx, edx; pUnkOuter
0x18002967e  lea     r8d, [r15+15h]; dwClsContext
0x180029682  lea     rcx, CLSID_FsrmFileManagementJobManager; rclsid
0x180029689  call    cs:__imp_CoCreateInstance
0x18002968f  mov     [rbp+110h+var_D8], eax
0x180029692  test    eax, eax
0x180029694  js      loc_180029AE4
0x18002969a  mov     [rbp+110h+var_D8], eax
0x18002969d  mov     rcx, [rsp+210h+var_1C0]
0x1800296a2  mov     rax, [rcx]
0x1800296a5  lea     r8, [rsp+210h+var_1C8]
0x1800296aa  lea     edx, [r15+4]
0x1800296ae  mov     rax, [rax+48h]
0x1800296b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b7  mov     [rbp+110h+var_D8], eax
0x1800296ba  test    eax, eax
0x1800296bc  js      loc_180029B16
0x1800296c2  mov     [rbp+110h+var_D8], eax
0x1800296c5  mov     rcx, [rsp+210h+var_1C8]
0x1800296ca  mov     rax, [rcx]
0x1800296cd  lea     rdx, [rsp+210h+var_1DC]
0x1800296d2  mov     rax, [rax+48h]
0x1800296d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296db  mov     [rbp+110h+var_D8], eax
0x1800296de  test    eax, eax
0x1800296e0  js      loc_180029B48
0x1800296e6  mov     [rbp+110h+var_D8], eax
0x1800296e9  lea     edi, [r15+1]
0x1800296ed  cmp     [rsp+210h+var_1DC], edi
0x1800296f1  jl      loc_18002995C
0x1800296f7  mov     [rsp+210h+var_1A8], r15
0x1800296fc  mov     [rsp+210h+var_1D0], r15
0x180029701  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180029705  call    cs:__imp_VariantInit
0x18002970b  nop
0x18002970c  mov     [rsp+210h+var_1E0], r15d
0x180029711  mov     rcx, [rsp+210h+var_1C8]
0x180029716  mov     rax, [rcx]
0x180029719  lea     r8, [rbp+110h+pvarg]
0x18002971d  mov     edx, edi
0x18002971f  mov     rax, [rax+40h]
0x180029723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029728  mov     [rbp+110h+var_D8], eax
0x18002972b  test    eax, eax
0x18002972d  js      loc_180029AB2
0x180029733  mov     [rbp+110h+var_D8], eax
0x180029736  cmp     word ptr [rbp+110h+pvarg], 9
0x18002973b  jnz     loc_180029A86
0x180029741  mov     [rbp+110h+var_D8], r15d
0x180029745  mov     rcx, qword ptr [rbp+110h+pvarg+8]
0x180029749  mov     rax, [rcx]
0x18002974c  lea     r8, [rsp+210h+var_1A8]
0x180029751  lea     rdx, IID_IFsrmFileManagementJobInternal
0x180029758  mov     rax, [rax]
0x18002975b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029760  mov     [rbp+110h+var_D8], eax
0x180029763  test    eax, eax
0x180029765  js      loc_180029CFE
0x18002976b  mov     [rbp+110h+var_D8], eax
0x18002976e  mov     rcx, [rsp+210h+var_1A8]
0x180029773  mov     rax, [rcx]
0x180029776  lea     rdx, [rsp+210h+var_1D0]
0x18002977b  mov     rax, [rax+48h]
0x18002977f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029784  mov     [rbp+110h+var_D8], eax
0x180029787  test    eax, eax
0x180029789  js      loc_180029CCC
0x18002978f  mov     [rbp+110h+var_D8], eax
0x180029792  mov     rcx, [rsp+210h+var_1D0]
0x180029797  mov     rax, [rcx]
0x18002979a  lea     rdx, [rsp+210h+var_1E0]
0x18002979f  mov     rax, [rax+48h]
0x1800297a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297a8  mov     [rbp+110h+var_D8], eax
0x1800297ab  test    eax, eax
0x1800297ad  js      loc_180029C9A
0x1800297b3  mov     [rbp+110h+var_D8], eax
0x1800297b6  mov     ebx, 1
0x1800297bb  cmp     [rsp+210h+var_1E0], ebx
0x1800297bf  jl      loc_180029917
0x1800297c5  lea     rcx, [rsp+210h+var_1A0]; pvarg
0x1800297ca  call    cs:__imp_VariantInit
0x1800297d0  nop
0x1800297d1  mov     [rsp+210h+var_1D8], r15
0x1800297d6  mov     [rsp+210h+String2], r15
0x1800297db  mov     [rsp+210h+bstrString], r15
0x1800297e0  mov     rcx, [rsp+210h+var_1D0]
0x1800297e5  mov     rax, [rcx]
0x1800297e8  lea     r8, [rsp+210h+var_1A0]
0x1800297ed  mov     edx, ebx
0x1800297ef  mov     rax, [rax+40h]
0x1800297f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f8  mov     [rbp+110h+var_D8], eax
0x1800297fb  test    eax, eax
0x1800297fd  js      loc_180029C68
0x180029803  mov     [rbp+110h+var_D8], eax
0x180029806  cmp     word ptr [rsp+210h+var_1A0], 9
0x18002980c  jnz     loc_180029C3C
0x180029812  mov     [rbp+110h+var_D8], r15d
0x180029816  mov     rcx, qword ptr [rsp+210h+var_1A0+8]
0x18002981b  mov     rax, [rcx]
0x18002981e  lea     r8, [rsp+210h+var_1D8]
0x180029823  lea     rdx, IID_IFsrmFMJConditionInternal
0x18002982a  mov     rax, [rax]
0x18002982d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029832  mov     [rbp+110h+var_D8], eax
0x180029835  test    eax, eax
0x180029837  js      loc_180029C0A
0x18002983d  mov     [rbp+110h+var_D8], eax
0x180029840  mov     rcx, [rsp+210h+var_1D8]
0x180029845  mov     rax, [rcx]
0x180029848  lea     rdx, [rsp+210h+String2]
0x18002984d  mov     rax, [rax+18h]
0x180029851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029856  mov     [rbp+110h+var_D8], eax
0x180029859  test    eax, eax
0x18002985b  js      loc_180029BD8
0x180029861  mov     [rbp+110h+var_D8], eax
0x180029864  mov     rcx, [rsp+210h+var_1D8]
0x180029869  mov     rax, [rcx]
0x18002986c  lea     rdx, [rsp+210h+bstrString]
0x180029871  mov     rax, [rax+38h]
0x180029875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987a  mov     [rbp+110h+var_D8], eax
0x18002987d  test    eax, eax
0x18002987f  js      loc_180029BA6
0x180029885  mov     [rbp+110h+var_D8], eax
0x180029888  mov     rdx, [rsp+210h+String2]; String2
0x18002988d  test    rdx, rdx
0x180029890  jz      loc_180029B7A
0x180029896  mov     [rbp+110h+var_D8], r15d
0x18002989a  lea     rcx, [r14+28h]
0x18002989e  cmp     qword ptr [rcx+18h], 8
0x1800298a3  jb      short loc_1800298A8
0x1800298a5  mov     rcx, [rcx]; String1
0x1800298a8  call    cs:__imp__wcsicmp
0x1800298ae  test    eax, eax
0x1800298b0  jnz     short loc_1800298D1
0x1800298b2  test    rsi, rsi
0x1800298b5  jz      loc_1800299C6
0x1800298bb  mov     rdx, [rsp+210h+bstrString]; String2
0x1800298c0  mov     rcx, rsi; String1
0x1800298c3  call    cs:__imp__wcsicmp
0x1800298c9  test    eax, eax
0x1800298cb  jz      loc_1800299C6
0x1800298d1  mov     rcx, [rsp+210h+bstrString]; bstrString
0x1800298d6  call    cs:__imp_SysFreeString
0x1800298dc  nop
0x1800298dd  mov     rcx, [rsp+210h+String2]; bstrString
0x1800298e2  call    cs:__imp_SysFreeString
0x1800298e8  nop
0x1800298e9  mov     rcx, [rsp+210h+var_1D8]
0x1800298ee  test    rcx, rcx
0x1800298f1  jz      short loc_180029900
0x1800298f3  mov     rax, [rcx]
0x1800298f6  mov     rax, [rax+10h]
0x1800298fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ff  nop
0x180029900  lea     rcx, [rsp+210h+var_1A0]; pvarg
0x180029905  call    cs:__imp_VariantClear
0x18002990b  inc     ebx
0x18002990d  cmp     ebx, [rsp+210h+var_1E0]
0x180029911  jle     loc_1800297C5
0x180029917  lea     rcx, [rbp+110h+pvarg]; pvarg
0x18002991b  call    cs:__imp_VariantClear
0x180029921  nop
0x180029922  mov     rcx, [rsp+210h+var_1D0]
0x180029927  test    rcx, rcx
0x18002992a  jz      short loc_180029939
0x18002992c  mov     rax, [rcx]
0x18002992f  mov     rax, [rax+10h]
0x180029933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029938  nop
0x180029939  mov     rcx, [rsp+210h+var_1A8]
0x18002993e  test    rcx, rcx
0x180029941  jz      short loc_180029950
0x180029943  mov     rax, [rcx]
0x180029946  mov     rax, [rax+10h]
0x18002994a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002994f  nop
0x180029950  inc     edi
0x180029952  cmp     edi, [rsp+210h+var_1DC]
0x180029956  jle     loc_1800296F7
0x18002995c  mov     rcx, [rsp+210h+var_1C8]
0x180029961  test    rcx, rcx
0x180029964  jz      short loc_180029973
0x180029966  mov     rax, [rcx]
0x180029969  mov     rax, [rax+10h]
0x18002996d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029972  nop
0x180029973  mov     rcx, [rsp+210h+var_1C0]
0x180029978  test    rcx, rcx
0x18002997b  jz      short loc_18002998A
0x18002997d  mov     rax, [rcx]
0x180029980  mov     rax, [rax+10h]
0x180029984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029989  nop
0x18002998a  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180029991  mov     [rbp+110h+var_E0], rcx
0x180029995  lea     rcx, [rbp+110h+var_E0]; this
0x180029999  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18002999e  xor     eax, eax
0x1800299a0  mov     rcx, [rbp+110h+var_30]
0x1800299a7  xor     rcx, rsp; StackCookie
0x1800299aa  call    __security_check_cookie
0x1800299af  mov     rbx, [rsp+210h+arg_10]
0x1800299b7  add     rsp, 1F0h
0x1800299be  pop     r15
0x1800299c0  pop     r14
0x1800299c2  pop     rdi
0x1800299c3  pop     rsi
0x1800299c4  pop     rbp
0x1800299c5  retn
0x1800299c6  mov     rcx, [rsp+210h+bstrString]; bstrString
0x1800299cb  call    cs:__imp_SysFreeString
0x1800299d1  nop
0x1800299d2  mov     rcx, [rsp+210h+String2]; bstrString
0x1800299d7  call    cs:__imp_SysFreeString
0x1800299dd  nop
0x1800299de  mov     rcx, [rsp+210h+var_1D8]
0x1800299e3  test    rcx, rcx
0x1800299e6  jz      short loc_1800299F5
0x1800299e8  mov     rax, [rcx]
0x1800299eb  mov     rax, [rax+10h]
0x1800299ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299f4  nop
0x1800299f5  lea     rcx, [rsp+210h+var_1A0]; pvarg
0x1800299fa  call    cs:__imp_VariantClear
0x180029a00  nop
0x180029a01  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180029a05  call    cs:__imp_VariantClear
0x180029a0b  nop
0x180029a0c  mov     rcx, [rsp+210h+var_1D0]
0x180029a11  test    rcx, rcx
0x180029a14  jz      short loc_180029A23
0x180029a16  mov     rax, [rcx]
0x180029a19  mov     rax, [rax+10h]
0x180029a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a22  nop
0x180029a23  mov     rcx, [rsp+210h+var_1A8]
0x180029a28  test    rcx, rcx
0x180029a2b  jz      short loc_180029A3A
0x180029a2d  mov     rax, [rcx]
0x180029a30  mov     rax, [rax+10h]
0x180029a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a39  nop
0x180029a3a  mov     rcx, [rsp+210h+var_1C8]
0x180029a3f  test    rcx, rcx
0x180029a42  jz      short loc_180029A51
0x180029a44  mov     rax, [rcx]
0x180029a47  mov     rax, [rax+10h]
0x180029a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a50  nop
0x180029a51  mov     rcx, [rsp+210h+var_1C0]
0x180029a56  test    rcx, rcx
0x180029a59  jz      short loc_180029A68
0x180029a5b  mov     rdx, [rcx]
0x180029a5e  mov     rax, [rdx+10h]
0x180029a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a67  nop
0x180029a68  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180029a6f  mov     [rbp+110h+var_E0], rcx
  ... truncated ...
```
