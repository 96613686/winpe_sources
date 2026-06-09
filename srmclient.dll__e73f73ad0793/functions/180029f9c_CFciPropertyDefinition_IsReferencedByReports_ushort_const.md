# CFciPropertyDefinition::IsReferencedByReports(ushort const *)

- ea: `0x180029f9c`
- end: `0x18002a7d7`
- name: `?IsReferencedByReports@CFciPropertyDefinition@@AEAAHPEBG@Z`
- size: `2107`
- prototype: `int(CFciPropertyDefinition *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029d38`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x180029f9c`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a303`
- `msvcrt!_wcsicmp` at `0x18002a31c`
- `msvcrt!_wcsicmp` at `0x18002a303`
- `msvcrt!_wcsicmp` at `0x18002a31c`
- `ole32!CoCreateInstance` at `0x18002a062`
- `ole32!CoCreateInstance` at `0x18002a062`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a2d7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a2d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a258`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a32d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a428`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a258`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a32d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a428`
- `OLEAUT32!__imp_VariantInit` at `0x18002a0e3`
- `OLEAUT32!__imp_VariantInit` at `0x18002a1a5`
- `OLEAUT32!__imp_VariantInit` at `0x18002a1bb`
- `OLEAUT32!__imp_VariantInit` at `0x18002a0e3`
- `OLEAUT32!__imp_VariantInit` at `0x18002a1a5`
- `OLEAUT32!__imp_VariantInit` at `0x18002a1bb`
- `OLEAUT32!__imp_VariantClear` at `0x18002a264`
- `OLEAUT32!__imp_VariantClear` at `0x18002a339`
- `OLEAUT32!__imp_VariantClear` at `0x18002a35f`
- `OLEAUT32!__imp_VariantClear` at `0x18002a375`
- `OLEAUT32!__imp_VariantClear` at `0x18002a434`
- `OLEAUT32!__imp_VariantClear` at `0x18002a456`
- `OLEAUT32!__imp_VariantClear` at `0x18002a461`
- `OLEAUT32!__imp_VariantClear` at `0x18002a264`
- `OLEAUT32!__imp_VariantClear` at `0x18002a339`
- `OLEAUT32!__imp_VariantClear` at `0x18002a35f`
- `OLEAUT32!__imp_VariantClear` at `0x18002a375`
- `OLEAUT32!__imp_VariantClear` at `0x18002a434`
- `OLEAUT32!__imp_VariantClear` at `0x18002a456`
- `OLEAUT32!__imp_VariantClear` at `0x18002a461`

## string_xrefs

- `0x180029fd4`: `base\fs\fsrm\service\globalstore\fcipropertydefinition.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CFciPropertyDefinition::IsReferencedByReports(
        CFciPropertyDefinition *this,
        const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const OLECHAR *bstrVal; // rbx
  const wchar_t *v18; // rax
  wchar_t *v19; // rbx
  const wchar_t *v20; // rcx
  char v22; // al
  int v23; // eax
  char v24; // al
  int Hr; // eax
  char v26; // al
  int v27; // eax
  char v28; // al
  int v29; // eax
  char v30; // al
  char v31; // al
  char v32; // al
  int v33; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  int v37; // eax
  char v38; // al
  char v39; // al
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  int v44; // eax
  char v45; // al
  int v46; // eax
  char v47; // al
  int v48; // [rsp+30h] [rbp-D0h] BYREF
  int v49; // [rsp+34h] [rbp-CCh] BYREF
  int v50; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v57; // [rsp+70h] [rbp-90h]
  VARIANTARG v58; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v59; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v61[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v62; // [rsp+E0h] [rbp-20h]
  _BYTE v63[96]; // [rsp+E8h] [rbp-18h] BYREF
  int v64; // [rsp+148h] [rbp+48h]
  void **v65; // [rsp+150h] [rbp+50h] BYREF
  HRESULT v66; // [rsp+158h] [rbp+58h]

  v61[0] = L"base\\fs\\fsrm\\service\\globalstore\\fcipropertydefinition.cpp";
  v61[1] = L"CFciPropertyDefinition::IsReferencedByReports";
  v61[2] = L"CFCIPRPD";
  v61[3] = 2045;
  v62 = 255;
  v64 = 0x1000000;
  memset_0(v63, 0, sizeof(v63));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v65, (const struct CSrmDebugInfo *)v61, 0);
  ppv = 0;
  v53 = 0;
  v50 = 0;
  v49 = 0;
  v4 = CoCreateInstance(&CLSID_FsrmReportManager, 0, 0x15u, &IID_IFsrmReportManager, &ppv);
  v66 = v4;
  if ( v4 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, Hr);
    v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x80Bu, v26, 0);
  }
  v66 = v4;
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 4, &v53);
  v66 = v5;
  if ( v5 < 0 )
  {
    v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v27);
    v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x80Du, v28, 0);
  }
  v66 = v5;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 72LL))(v53, &v50);
  v66 = v6;
  if ( v6 < 0 )
  {
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v29);
    v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x80Fu, v30, 0);
  }
  v66 = v6;
  v7 = 1;
  if ( v50 < 1 )
  {
LABEL_36:
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v65 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v65);
    return 0;
  }
  while ( 1 )
  {
    v54 = 0;
    v52 = 0;
    VariantInit(&pvarg);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v53 + 64LL))(v53, v7, &pvarg);
    v66 = v8;
    if ( v8 < 0 )
    {
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v23);
      v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x81Au, v24, 0);
    }
    v66 = v8;
    if ( pvarg.vt != 9 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, -2147418113);
      v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x81Cu, v22, 0);
    }
    v66 = 0;
    v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_IFsrmReportJob, &v54);
    v66 = v9;
    if ( v9 < 0 )
    {
      v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v46);
      v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x81Eu, v47, 0);
    }
    v66 = v9;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 192LL))(v54, &v52);
    v66 = v10;
    if ( v10 < 0 )
    {
      v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v44);
      v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x820u, v45, 0);
    }
    v66 = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 72LL))(v52, &v49);
    v66 = v11;
    if ( v11 < 0 )
    {
      v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v42);
      v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x822u, v43, 0);
    }
    v66 = v11;
    v12 = 1;
    if ( v49 >= 1 )
      break;
LABEL_31:
    VariantClear(&pvarg);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    if ( (int)++v7 > v50 )
      goto LABEL_36;
  }
  while ( 1 )
  {
    VariantInit(&v59);
    v51 = 0;
    v48 = 0;
    VariantInit(&v58);
    v57 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v52 + 64LL))(v52, v12, &v59);
    v66 = v13;
    if ( v13 < 0 )
    {
      v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v40);
      v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x82Du, v41, 0);
    }
    v66 = v13;
    if ( v59.vt != 9 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, -2147418113);
      v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x82Fu, v39, 0);
    }
    v66 = 0;
    v14 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v59.llVal)(v59.llVal, &IID_IFsrmReport, &v51);
    v66 = v14;
    if ( v14 < 0 )
    {
      v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v37);
      v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x831u, v38, 0);
    }
    v66 = v14;
    v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 56LL))(v51, &v48);
    v66 = v15;
    if ( v15 < 0 )
    {
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v35);
      v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x833u, v36, 0);
    }
    v66 = v15;
    if ( v48 != 10 && v48 != 13 )
    {
      SysFreeString(0);
      VariantClear(&v58);
      if ( v51 )
        goto LABEL_29;
      goto LABEL_30;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v51 + 104LL))(v51, 8, &v58);
    v66 = v16;
    if ( v16 < 0 )
    {
      v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, v33);
      v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x83Au, v34, 0);
    }
    v66 = v16;
    if ( v58.vt != 8 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, -2147418113);
      v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x83Cu, v32, 0);
    }
    v66 = 0;
    bstrVal = v58.bstrVal;
    SysFreeString(0);
    if ( !bstrVal )
    {
      v57 = 0;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v65, -2147200234);
      v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v65);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v65, 0x840u, v31, 0);
    }
    v18 = SysAllocString(bstrVal);
    v19 = (wchar_t *)v18;
    v57 = v18;
    if ( !v18 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v66 = 0;
    v20 = (const wchar_t *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) >= 8u )
      v20 = *(const wchar_t **)v20;
    if ( !_wcsicmp(v20, v18) && (!a2 || !_wcsicmp(a2, v19)) )
      break;
    SysFreeString(v19);
    VariantClear(&v58);
    if ( v51 )
LABEL_29:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
LABEL_30:
    VariantClear(&v59);
    if ( (int)++v12 > v49 )
      goto LABEL_31;
  }
  SysFreeString(v19);
  VariantClear(&v58);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  VariantClear(&v59);
  VariantClear(&pvarg);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v65 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v65);
  return 1;
}

```

## disassembly

```asm
0x180029f9c  mov     [rsp-8+arg_10], rbx
0x180029fa1  mov     [rsp-8+arg_18], rsi
0x180029fa6  push    rbp
0x180029fa7  push    rdi
0x180029fa8  push    r12
0x180029faa  push    r14
0x180029fac  push    r15
0x180029fae  lea     rbp, [rsp-110h]
0x180029fb6  sub     rsp, 210h
0x180029fbd  mov     rax, cs:__security_cookie
0x180029fc4  xor     rax, rsp
0x180029fc7  mov     [rbp+130h+var_30], rax
0x180029fce  mov     r14, rdx
0x180029fd1  mov     r15, rcx
0x180029fd4  lea     rax, aBaseFsFsrmServ_4; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x180029fdb  mov     [rbp+130h+var_170], rax
0x180029fdf  lea     rax, aCfcipropertyde_44; "CFciPropertyDefinition::IsReferencedByR"...
0x180029fe6  mov     [rbp+130h+var_168], rax
0x180029fea  lea     rax, aCfciprpd; "CFCIPRPD"
0x180029ff1  mov     [rbp+130h+var_160], rax
0x180029ff5  mov     [rbp+130h+var_158], 7FDh
0x180029ffd  xor     r12d, r12d
0x18002a000  mov     [rbp+130h+var_150], 0FFh
0x18002a007  mov     [rbp+130h+var_E8], 1000000h
0x18002a00e  xor     edx, edx; Val
0x18002a010  lea     r8d, [r12+60h]; Size
0x18002a015  lea     rcx, [rbp+130h+var_148]; void *
0x18002a019  call    memset_0
0x18002a01e  xor     r8d, r8d
0x18002a021  lea     rdx, [rbp+130h+var_170]
0x18002a025  lea     rcx, [rbp+130h+var_E0]
0x18002a029  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18002a02e  nop
0x18002a02f  mov     [rsp+230h+var_1D0], r12
0x18002a034  mov     [rsp+230h+var_1E0], r12
0x18002a039  mov     [rsp+230h+var_1F8], r12d
0x18002a03e  mov     [rsp+230h+var_1FC], r12d
0x18002a043  lea     rax, [rsp+230h+var_1D0]
0x18002a048  mov     [rsp+230h+ppv], rax; ppv
0x18002a04d  lea     r9, IID_IFsrmReportManager; riid
0x18002a054  xor     edx, edx; pUnkOuter
0x18002a056  lea     r8d, [r12+15h]; dwClsContext
0x18002a05b  lea     rcx, CLSID_FsrmReportManager; rclsid
0x18002a062  call    cs:__imp_CoCreateInstance
0x18002a068  mov     [rbp+130h+var_D8], eax
0x18002a06b  test    eax, eax
0x18002a06d  js      loc_18002A540
0x18002a073  mov     [rbp+130h+var_D8], eax
0x18002a076  mov     rcx, [rsp+230h+var_1D0]
0x18002a07b  mov     rax, [rcx]
0x18002a07e  lea     r8, [rsp+230h+var_1E0]
0x18002a083  lea     edx, [r12+4]
0x18002a088  mov     rax, [rax+38h]
0x18002a08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a091  mov     [rbp+130h+var_D8], eax
0x18002a094  test    eax, eax
0x18002a096  js      loc_18002A572
0x18002a09c  mov     [rbp+130h+var_D8], eax
0x18002a09f  mov     rcx, [rsp+230h+var_1E0]
0x18002a0a4  mov     rax, [rcx]
0x18002a0a7  lea     rdx, [rsp+230h+var_1F8]
0x18002a0ac  mov     rax, [rax+48h]
0x18002a0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0b5  mov     [rbp+130h+var_D8], eax
0x18002a0b8  test    eax, eax
0x18002a0ba  js      loc_18002A5A4
0x18002a0c0  mov     [rbp+130h+var_D8], eax
0x18002a0c3  lea     esi, [r12+1]
0x18002a0c8  cmp     [rsp+230h+var_1F8], esi
0x18002a0cc  jl      loc_18002A3B6
0x18002a0d2  lea     ebx, [rsi+7]
0x18002a0d5  mov     [rsp+230h+var_1D8], r12
0x18002a0da  mov     [rsp+230h+var_1E8], r12
0x18002a0df  lea     rcx, [rbp+130h+pvarg]; pvarg
0x18002a0e3  call    cs:__imp_VariantInit
0x18002a0e9  nop
0x18002a0ea  mov     rcx, [rsp+230h+var_1E0]
0x18002a0ef  mov     rax, [rcx]
0x18002a0f2  lea     r8, [rbp+130h+pvarg]
0x18002a0f6  mov     edx, esi
0x18002a0f8  mov     rax, [rax+40h]
0x18002a0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a101  mov     [rbp+130h+var_D8], eax
0x18002a104  test    eax, eax
0x18002a106  js      loc_18002A50E
0x18002a10c  mov     [rbp+130h+var_D8], eax
0x18002a10f  cmp     word ptr [rbp+130h+pvarg], 9
0x18002a114  jnz     loc_18002A4E2
0x18002a11a  mov     [rbp+130h+var_D8], r12d
0x18002a11e  mov     rcx, qword ptr [rbp+130h+pvarg+8]
0x18002a122  mov     rax, [rcx]
0x18002a125  lea     r8, [rsp+230h+var_1D8]
0x18002a12a  lea     rdx, IID_IFsrmReportJob
0x18002a131  mov     rax, [rax]
0x18002a134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a139  mov     [rbp+130h+var_D8], eax
0x18002a13c  test    eax, eax
0x18002a13e  js      loc_18002A7A5
0x18002a144  mov     [rbp+130h+var_D8], eax
0x18002a147  mov     rcx, [rsp+230h+var_1D8]
0x18002a14c  mov     rax, [rcx]
0x18002a14f  lea     rdx, [rsp+230h+var_1E8]
0x18002a154  mov     rax, [rax+0C0h]
0x18002a15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a160  mov     [rbp+130h+var_D8], eax
0x18002a163  test    eax, eax
0x18002a165  js      loc_18002A773
0x18002a16b  mov     [rbp+130h+var_D8], eax
0x18002a16e  mov     rcx, [rsp+230h+var_1E8]
0x18002a173  mov     rax, [rcx]
0x18002a176  lea     rdx, [rsp+230h+var_1FC]
0x18002a17b  mov     rax, [rax+48h]
0x18002a17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a184  mov     [rbp+130h+var_D8], eax
0x18002a187  test    eax, eax
0x18002a189  js      loc_18002A741
0x18002a18f  mov     [rbp+130h+var_D8], eax
0x18002a192  mov     edi, 1
0x18002a197  cmp     [rsp+230h+var_1FC], edi
0x18002a19b  jl      loc_18002A371
0x18002a1a1  lea     rcx, [rbp+130h+var_1A0]; pvarg
0x18002a1a5  call    cs:__imp_VariantInit
0x18002a1ab  nop
0x18002a1ac  mov     [rsp+230h+var_1F0], r12
0x18002a1b1  mov     [rsp+230h+var_200], r12d
0x18002a1b6  lea     rcx, [rsp+230h+var_1B8]; pvarg
0x18002a1bb  call    cs:__imp_VariantInit
0x18002a1c1  nop
0x18002a1c2  mov     [rsp+230h+var_1C0], r12
0x18002a1c7  mov     rcx, [rsp+230h+var_1E8]
0x18002a1cc  mov     rax, [rcx]
0x18002a1cf  lea     r8, [rbp+130h+var_1A0]
0x18002a1d3  mov     edx, edi
0x18002a1d5  mov     rax, [rax+40h]
0x18002a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1de  mov     [rbp+130h+var_D8], eax
0x18002a1e1  test    eax, eax
0x18002a1e3  js      loc_18002A70F
0x18002a1e9  mov     [rbp+130h+var_D8], eax
0x18002a1ec  cmp     word ptr [rbp+130h+var_1A0], 9
0x18002a1f1  jnz     loc_18002A6E3
0x18002a1f7  mov     [rbp+130h+var_D8], r12d
0x18002a1fb  mov     rcx, qword ptr [rbp+130h+var_1A0+8]
0x18002a1ff  mov     rax, [rcx]
0x18002a202  lea     r8, [rsp+230h+var_1F0]
0x18002a207  lea     rdx, IID_IFsrmReport
0x18002a20e  mov     rax, [rax]
0x18002a211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a216  mov     [rbp+130h+var_D8], eax
0x18002a219  test    eax, eax
0x18002a21b  js      loc_18002A6B1
0x18002a221  mov     [rbp+130h+var_D8], eax
0x18002a224  mov     rcx, [rsp+230h+var_1F0]
0x18002a229  mov     rax, [rcx]
0x18002a22c  lea     rdx, [rsp+230h+var_200]
0x18002a231  mov     rax, [rax+38h]
0x18002a235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a23a  mov     [rbp+130h+var_D8], eax
0x18002a23d  test    eax, eax
0x18002a23f  js      loc_18002A67F
0x18002a245  mov     [rbp+130h+var_D8], eax
0x18002a248  cmp     [rsp+230h+var_200], 0Ah
0x18002a24d  jz      short loc_18002A28A
0x18002a24f  cmp     [rsp+230h+var_200], 0Dh
0x18002a254  jz      short loc_18002A28A
0x18002a256  xor     ecx, ecx; bstrString
0x18002a258  call    cs:__imp_SysFreeString
0x18002a25e  nop
0x18002a25f  lea     rcx, [rsp+230h+var_1B8]; pvarg
0x18002a264  call    cs:__imp_VariantClear
0x18002a26a  nop
0x18002a26b  mov     rcx, [rsp+230h+var_1F0]
0x18002a270  test    rcx, rcx
0x18002a273  jz      loc_18002A35B
0x18002a279  mov     rax, [rcx]
0x18002a27c  mov     rax, [rax+10h]
0x18002a280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a285  jmp     loc_18002A35B
0x18002a28a  mov     rcx, [rsp+230h+var_1F0]
0x18002a28f  mov     rax, [rcx]
0x18002a292  lea     r8, [rsp+230h+var_1B8]
0x18002a297  mov     edx, ebx
0x18002a299  mov     rax, [rax+68h]
0x18002a29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2a2  mov     [rbp+130h+var_D8], eax
0x18002a2a5  test    eax, eax
0x18002a2a7  js      loc_18002A64D
0x18002a2ad  mov     [rbp+130h+var_D8], eax
0x18002a2b0  cmp     word ptr [rsp+230h+var_1B8], bx
0x18002a2b5  jnz     loc_18002A621
0x18002a2bb  mov     [rbp+130h+var_D8], r12d
0x18002a2bf  mov     rbx, qword ptr [rbp+130h+var_1B8+8]
0x18002a2c3  xor     ecx, ecx; bstrString
0x18002a2c5  call    cs:__imp_SysFreeString
0x18002a2cb  test    rbx, rbx
0x18002a2ce  jz      loc_18002A5F0
0x18002a2d4  mov     rcx, rbx; psz
0x18002a2d7  call    cs:__imp_SysAllocString
0x18002a2dd  mov     rbx, rax
0x18002a2e0  mov     [rsp+230h+var_1C0], rax
0x18002a2e5  test    rax, rax
0x18002a2e8  jz      loc_18002A5D6
0x18002a2ee  mov     [rbp+130h+var_D8], r12d
0x18002a2f2  lea     rcx, [r15+28h]
0x18002a2f6  cmp     qword ptr [rcx+18h], 8
0x18002a2fb  jb      short loc_18002A300
0x18002a2fd  mov     rcx, [rcx]; String1
0x18002a300  mov     rdx, rbx; String2
0x18002a303  call    cs:__imp__wcsicmp
0x18002a309  test    eax, eax
0x18002a30b  jnz     short loc_18002A32A
0x18002a30d  test    r14, r14
0x18002a310  jz      loc_18002A425
0x18002a316  mov     rdx, rbx; String2
0x18002a319  mov     rcx, r14; String1
0x18002a31c  call    cs:__imp__wcsicmp
0x18002a322  test    eax, eax
0x18002a324  jz      loc_18002A425
0x18002a32a  mov     rcx, rbx; bstrString
0x18002a32d  call    cs:__imp_SysFreeString
0x18002a333  nop
0x18002a334  lea     rcx, [rsp+230h+var_1B8]; pvarg
0x18002a339  call    cs:__imp_VariantClear
0x18002a33f  nop
0x18002a340  mov     rcx, [rsp+230h+var_1F0]
0x18002a345  test    rcx, rcx
0x18002a348  jz      short loc_18002A356
0x18002a34a  mov     rax, [rcx]
0x18002a34d  mov     rax, [rax+10h]
0x18002a351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a356  mov     ebx, 8
0x18002a35b  lea     rcx, [rbp+130h+var_1A0]; pvarg
0x18002a35f  call    cs:__imp_VariantClear
0x18002a365  inc     edi
0x18002a367  cmp     edi, [rsp+230h+var_1FC]
0x18002a36b  jle     loc_18002A1A1
0x18002a371  lea     rcx, [rbp+130h+pvarg]; pvarg
0x18002a375  call    cs:__imp_VariantClear
0x18002a37b  nop
0x18002a37c  mov     rcx, [rsp+230h+var_1E8]
0x18002a381  test    rcx, rcx
0x18002a384  jz      short loc_18002A393
0x18002a386  mov     rax, [rcx]
0x18002a389  mov     rax, [rax+10h]
0x18002a38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a392  nop
0x18002a393  mov     rcx, [rsp+230h+var_1D8]
0x18002a398  test    rcx, rcx
0x18002a39b  jz      short loc_18002A3AA
0x18002a39d  mov     rax, [rcx]
0x18002a3a0  mov     rax, [rax+10h]
0x18002a3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3a9  nop
0x18002a3aa  inc     esi
0x18002a3ac  cmp     esi, [rsp+230h+var_1F8]
0x18002a3b0  jle     loc_18002A0D5
0x18002a3b6  mov     rcx, [rsp+230h+var_1E0]
0x18002a3bb  test    rcx, rcx
0x18002a3be  jz      short loc_18002A3CD
0x18002a3c0  mov     rax, [rcx]
0x18002a3c3  mov     rax, [rax+10h]
0x18002a3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3cc  nop
0x18002a3cd  mov     rcx, [rsp+230h+var_1D0]
0x18002a3d2  test    rcx, rcx
0x18002a3d5  jz      short loc_18002A3E4
0x18002a3d7  mov     rax, [rcx]
0x18002a3da  mov     rax, [rax+10h]
0x18002a3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3e3  nop
0x18002a3e4  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18002a3eb  mov     [rbp+130h+var_E0], rcx
0x18002a3ef  lea     rcx, [rbp+130h+var_E0]; this
0x18002a3f3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18002a3f8  xor     eax, eax
0x18002a3fa  mov     rcx, [rbp+130h+var_30]
0x18002a401  xor     rcx, rsp; StackCookie
0x18002a404  call    __security_check_cookie
0x18002a409  lea     r11, [rsp+230h+var_20]
0x18002a411  mov     rbx, [r11+40h]
0x18002a415  mov     rsi, [r11+48h]
0x18002a419  mov     rsp, r11
0x18002a41c  pop     r15
0x18002a41e  pop     r14
0x18002a420  pop     r12
0x18002a422  pop     rdi
0x18002a423  pop     rbp
0x18002a424  retn
0x18002a425  mov     rcx, rbx; bstrString
0x18002a428  call    cs:__imp_SysFreeString
0x18002a42e  nop
0x18002a42f  lea     rcx, [rsp+230h+var_1B8]; pvarg
0x18002a434  call    cs:__imp_VariantClear
0x18002a43a  nop
0x18002a43b  mov     rcx, [rsp+230h+var_1F0]
0x18002a440  test    rcx, rcx
0x18002a443  jz      short loc_18002A452
0x18002a445  mov     rax, [rcx]
0x18002a448  mov     rax, [rax+10h]
0x18002a44c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
