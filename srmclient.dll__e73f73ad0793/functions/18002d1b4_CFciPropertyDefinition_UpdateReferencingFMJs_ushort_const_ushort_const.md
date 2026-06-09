# CFciPropertyDefinition::UpdateReferencingFMJs(ushort const *,ushort const *)

- ea: `0x18002d1b4`
- end: `0x18002d9d7`
- name: `?UpdateReferencingFMJs@CFciPropertyDefinition@@AEAAXPEBG0@Z`
- size: `2083`
- prototype: `void(CFciPropertyDefinition *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180027ac8`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18002d1b4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002d47e`
- `msvcrt!_wcsicmp` at `0x18002d47e`
- `ole32!CoCreateInstance` at `0x18002d2a0`
- `ole32!CoCreateInstance` at `0x18002d2a0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d4b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d4b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d48d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d507`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d48d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d507`
- `OLEAUT32!__imp_VariantInit` at `0x18002d312`
- `OLEAUT32!__imp_VariantInit` at `0x18002d3d4`
- `OLEAUT32!__imp_VariantInit` at `0x18002d312`
- `OLEAUT32!__imp_VariantInit` at `0x18002d3d4`
- `OLEAUT32!__imp_VariantClear` at `0x18002d52a`
- `OLEAUT32!__imp_VariantClear` at `0x18002d5aa`
- `OLEAUT32!__imp_VariantClear` at `0x18002d52a`
- `OLEAUT32!__imp_VariantClear` at `0x18002d5aa`

## string_xrefs

- `0x18002d1ea`: `base\fs\fsrm\service\globalstore\fcipropertydefinition.cpp`
- `0x18002d1f5`: `CFciPropertyDefinition::UpdateReferencingFMJs`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CFciPropertyDefinition::UpdateReferencingFMJs(
        CFciPropertyDefinition *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  int i; // esi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // edi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 *v18; // r14
  __int64 v19; // r15
  BSTR v20; // rax
  OLECHAR *v21; // rbx
  int v22; // eax
  int v23; // eax
  char v24; // al
  char Hr; // al
  int v26; // eax
  char v27; // al
  int v28; // eax
  char v29; // al
  int v30; // eax
  char v31; // al
  int v32; // eax
  char v33; // al
  int v34; // eax
  char v35; // al
  int v36; // eax
  char v37; // al
  char v38; // al
  int v39; // eax
  char v40; // al
  int v41; // eax
  char v42; // al
  char v43; // al
  int v44; // eax
  char v45; // al
  int v46; // eax
  char v47; // al
  int v48; // eax
  char v49; // al
  int v50; // eax
  char v51; // al
  char v52; // al
  int v53; // eax
  char v54; // al
  int v55; // [rsp+30h] [rbp-D0h] BYREF
  int v56; // [rsp+34h] [rbp-CCh] BYREF
  BSTR pExceptionObject; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v58; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v64; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v66[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v67; // [rsp+C0h] [rbp-40h]
  _BYTE v68[96]; // [rsp+C8h] [rbp-38h] BYREF
  int v69; // [rsp+128h] [rbp+28h]
  void **v70; // [rsp+130h] [rbp+30h] BYREF
  int v71; // [rsp+138h] [rbp+38h]

  v66[0] = L"base\\fs\\fsrm\\service\\globalstore\\fcipropertydefinition.cpp";
  v66[1] = L"CFciPropertyDefinition::UpdateReferencingFMJs";
  v66[2] = L"CFCIPRPD";
  v66[3] = 1669;
  v67 = 255;
  v69 = 0x1000000;
  memset_0(v68, 0, sizeof(v68));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v70, (const struct CSrmDebugInfo *)v66, 0);
  if ( !a3 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x68Bu, Hr, 0);
  }
  v71 = 0;
  if ( !*a3 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147024809);
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x68Cu, v24, 0);
  }
  v71 = 0;
  ppv = 0;
  v62 = 0;
  v61 = 0;
  v60 = 0;
  v56 = 0;
  v55 = 0;
  v5 = CoCreateInstance(&CLSID_FsrmFileManagementJobManager, 0, 0x15u, &IID_IFsrmFileManagementJobManager, &ppv);
  v71 = v5;
  if ( v5 < 0 )
  {
    v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v26);
    v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x699u, v27, 0);
  }
  v71 = v5;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, 4, &v62);
  v71 = v6;
  if ( v6 < 0 )
  {
    v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v28);
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x69Bu, v29, 0);
  }
  v71 = v6;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 72LL))(v62, &v56);
  v71 = v7;
  if ( v7 < 0 )
  {
    v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v30);
    v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x69Du, v31, 0);
  }
  v71 = v7;
  for ( i = 1; i <= v56; ++i )
  {
    VariantInit(&pvarg);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v62 + 64LL))(
           v62,
           (unsigned int)i,
           &pvarg);
    v71 = v9;
    if ( v9 < 0 )
    {
      v53 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v53);
      v54 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6A4u, v54, 0);
    }
    v71 = v9;
    if ( pvarg.vt != 9 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147418113);
      v52 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6A6u, v52, 0);
    }
    v71 = 0;
    v10 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
            pvarg.llVal,
            &GUID_9326aba8_cc60_476b_b3be_8d26ffde9e0e,
            &v61);
    v71 = v10;
    if ( v10 < 0 )
    {
      v50 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v50);
      v51 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6A8u, v51, 0);
    }
    v71 = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 72LL))(v61, &v60);
    v71 = v11;
    if ( v11 < 0 )
    {
      v48 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v48);
      v49 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6AAu, v49, 0);
    }
    v71 = v11;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 72LL))(v60, &v55);
    v71 = v12;
    if ( v12 < 0 )
    {
      v46 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v46);
      v47 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6ACu, v47, 0);
    }
    v13 = 0;
    v71 = v12;
    v14 = 1;
    if ( v55 >= 1 )
    {
      do
      {
        VariantInit(&v64);
        v58 = 0;
        String1 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v60 + 64LL))(
                v60,
                (unsigned int)v14,
                &v64);
        v71 = v15;
        if ( v15 < 0 )
        {
          v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v44);
          v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6B4u, v45, 0);
        }
        v71 = v15;
        if ( v64.vt != 9 )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147418113);
          v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6B6u, v43, 0);
        }
        v71 = 0;
        v16 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 **))v64.llVal)(
                v64.llVal,
                &GUID_8ddadb3b_f51d_4e16_aa67_4161a85e2deb,
                &v58);
        v71 = v16;
        if ( v16 < 0 )
        {
          v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v41);
          v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6B8u, v42, 0);
        }
        v71 = v16;
        v17 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(*v58 + 24))(v58, &String1);
        v71 = v17;
        if ( v17 < 0 )
        {
          v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v39);
          v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6BAu, v40, 0);
        }
        v71 = v17;
        if ( !String1 )
        {
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, -2147200234);
          v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6BCu, v38, 0);
        }
        v71 = 0;
        if ( _wcsicmp(String1, a2) )
        {
          SysFreeString(String1);
          if ( v58 )
            (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
        }
        else
        {
          v18 = v58;
          v19 = *v58;
          v20 = SysAllocString(a3);
          v21 = v20;
          pExceptionObject = v20;
          if ( !v20 )
          {
            LODWORD(pExceptionObject) = -2147024882;
            throw (long *)&pExceptionObject;
          }
          v71 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v19 + 32))(v18, v20);
          SysFreeString(v21);
          if ( v71 < 0 )
          {
            v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v36);
            v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
            CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6C1u, v37, 0);
          }
          v13 = 1;
          SysFreeString(String1);
          if ( v58 )
            (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
        }
        VariantClear(&v64);
        ++v14;
      }
      while ( v14 <= v55 );
      if ( v13 )
      {
        pExceptionObject = 0;
        v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, BSTR *))v61)(
                v61,
                &GUID_0770687e_9f36_4d6f_8778_599d188461c9,
                &pExceptionObject);
        v71 = v22;
        if ( v22 < 0 )
        {
          v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v34);
          v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6CAu, v35, 0);
        }
        v71 = v22;
        v23 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)pExceptionObject + 88LL))(pExceptionObject);
        v71 = v23;
        if ( v23 < 0 )
        {
          v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v70, v32);
          v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v70);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v70, 0x6CCu, v33, 0);
        }
        v71 = v23;
        if ( pExceptionObject )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)pExceptionObject + 16LL))(pExceptionObject);
      }
    }
    VariantClear(&pvarg);
  }
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v70 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v70);
}

```

## disassembly

```asm
0x18002d1b4  mov     [rsp-8+arg_0], rbx
0x18002d1b9  push    rbp
0x18002d1ba  push    rsi
0x18002d1bb  push    rdi
0x18002d1bc  push    r12
0x18002d1be  push    r13
0x18002d1c0  push    r14
0x18002d1c2  push    r15
0x18002d1c4  lea     rbp, [rsp-0F0h]
0x18002d1cc  sub     rsp, 1F0h
0x18002d1d3  mov     rax, cs:__security_cookie
0x18002d1da  xor     rax, rsp
0x18002d1dd  mov     [rbp+120h+var_40], rax
0x18002d1e4  mov     r12, r8
0x18002d1e7  mov     r13, rdx
0x18002d1ea  lea     rax, aBaseFsFsrmServ_4; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x18002d1f1  mov     [rbp+120h+var_180], rax
0x18002d1f5  lea     rax, aCfcipropertyde_48; "CFciPropertyDefinition::UpdateReferenci"...
0x18002d1fc  mov     [rbp+120h+var_178], rax
0x18002d200  lea     rax, aCfciprpd; "CFCIPRPD"
0x18002d207  mov     [rbp+120h+var_170], rax
0x18002d20b  mov     [rbp+120h+var_168], 685h
0x18002d213  xor     r14d, r14d
0x18002d216  mov     [rbp+120h+var_160], 0FFh
0x18002d21d  mov     [rbp+120h+var_F8], 1000000h
0x18002d224  xor     edx, edx; Val
0x18002d226  lea     r15d, [r14+1]
0x18002d22a  lea     r8d, [r14+60h]; Size
0x18002d22e  lea     rcx, [rbp+120h+var_158]; void *
0x18002d232  call    memset_0
0x18002d237  xor     r8d, r8d
0x18002d23a  lea     rdx, [rbp+120h+var_180]
0x18002d23e  lea     rcx, [rbp+120h+var_F0]
0x18002d242  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18002d247  nop
0x18002d248  test    r12, r12
0x18002d24b  jz      loc_18002D683
0x18002d251  mov     [rbp+120h+var_E8], r14d
0x18002d255  cmp     [r12], r14w
0x18002d25a  jz      loc_18002D657
0x18002d260  mov     [rbp+120h+var_E8], r14d
0x18002d264  mov     [rsp+220h+var_1B8], r14
0x18002d269  mov     [rsp+220h+var_1C0], r14
0x18002d26e  mov     [rsp+220h+var_1C8], r14
0x18002d273  mov     [rsp+220h+var_1D0], r14
0x18002d278  mov     [rsp+220h+var_1EC], r14d
0x18002d27d  mov     [rsp+220h+var_1F0], r14d
0x18002d282  lea     rax, [rsp+220h+var_1B8]
0x18002d287  mov     [rsp+220h+ppv], rax; ppv
0x18002d28c  lea     r9, IID_IFsrmFileManagementJobManager; riid
0x18002d293  xor     edx, edx; pUnkOuter
0x18002d295  lea     r8d, [r14+15h]; dwClsContext
0x18002d299  lea     rcx, CLSID_FsrmFileManagementJobManager; rclsid
0x18002d2a0  call    cs:__imp_CoCreateInstance
0x18002d2a6  mov     [rbp+120h+var_E8], eax
0x18002d2a9  test    eax, eax
0x18002d2ab  js      loc_18002D6AF
0x18002d2b1  mov     [rbp+120h+var_E8], eax
0x18002d2b4  mov     rcx, [rsp+220h+var_1B8]
0x18002d2b9  mov     rax, [rcx]
0x18002d2bc  lea     r8, [rsp+220h+var_1C0]
0x18002d2c1  lea     edx, [r14+4]
0x18002d2c5  mov     rax, [rax+48h]
0x18002d2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ce  mov     [rbp+120h+var_E8], eax
0x18002d2d1  test    eax, eax
0x18002d2d3  js      loc_18002D6E1
0x18002d2d9  mov     [rbp+120h+var_E8], eax
0x18002d2dc  mov     rcx, [rsp+220h+var_1C0]
0x18002d2e1  mov     rax, [rcx]
0x18002d2e4  lea     rdx, [rsp+220h+var_1EC]
0x18002d2e9  mov     rax, [rax+48h]
0x18002d2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2f2  mov     [rbp+120h+var_E8], eax
0x18002d2f5  test    eax, eax
0x18002d2f7  js      loc_18002D713
0x18002d2fd  mov     [rbp+120h+var_E8], eax
0x18002d300  mov     esi, r15d
0x18002d303  cmp     [rsp+220h+var_1EC], r15d
0x18002d308  jl      loc_18002D5BD
0x18002d30e  lea     rcx, [rbp+120h+pvarg]; pvarg
0x18002d312  call    cs:__imp_VariantInit
0x18002d318  nop
0x18002d319  mov     rcx, [rsp+220h+var_1C0]
0x18002d31e  mov     rax, [rcx]
0x18002d321  lea     r8, [rbp+120h+pvarg]
0x18002d325  mov     edx, esi
0x18002d327  mov     rax, [rax+40h]
0x18002d32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d330  mov     [rbp+120h+var_E8], eax
0x18002d333  test    eax, eax
0x18002d335  js      loc_18002D9A5
0x18002d33b  mov     [rbp+120h+var_E8], eax
0x18002d33e  cmp     word ptr [rbp+120h+pvarg], 9
0x18002d343  jnz     loc_18002D979
0x18002d349  mov     [rbp+120h+var_E8], r14d
0x18002d34d  mov     rcx, qword ptr [rbp+120h+pvarg+8]
0x18002d351  mov     rax, [rcx]
0x18002d354  lea     r8, [rsp+220h+var_1C8]
0x18002d359  lea     rdx, _GUID_9326aba8_cc60_476b_b3be_8d26ffde9e0e
0x18002d360  mov     rax, [rax]
0x18002d363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d368  mov     [rbp+120h+var_E8], eax
0x18002d36b  test    eax, eax
0x18002d36d  js      loc_18002D947
0x18002d373  mov     [rbp+120h+var_E8], eax
0x18002d376  mov     rcx, [rsp+220h+var_1C8]
0x18002d37b  mov     rax, [rcx]
0x18002d37e  lea     rdx, [rsp+220h+var_1D0]
0x18002d383  mov     rax, [rax+48h]
0x18002d387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d38c  mov     [rbp+120h+var_E8], eax
0x18002d38f  test    eax, eax
0x18002d391  js      loc_18002D915
0x18002d397  mov     [rbp+120h+var_E8], eax
0x18002d39a  mov     rcx, [rsp+220h+var_1D0]
0x18002d39f  mov     rax, [rcx]
0x18002d3a2  lea     rdx, [rsp+220h+var_1F0]
0x18002d3a7  mov     rax, [rax+48h]
0x18002d3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3b0  mov     [rbp+120h+var_E8], eax
0x18002d3b3  test    eax, eax
0x18002d3b5  js      loc_18002D8E3
0x18002d3bb  mov     ebx, r14d
0x18002d3be  mov     [rbp+120h+var_E8], eax
0x18002d3c1  mov     edi, r15d
0x18002d3c4  cmp     [rsp+220h+var_1F0], r15d
0x18002d3c9  jl      loc_18002D5A6
0x18002d3cf  lea     rcx, [rsp+220h+var_1B0]; pvarg
0x18002d3d4  call    cs:__imp_VariantInit
0x18002d3da  nop
0x18002d3db  mov     [rsp+220h+var_1E0], r14
0x18002d3e0  mov     [rsp+220h+String1], r14
0x18002d3e5  mov     rcx, [rsp+220h+var_1D0]
0x18002d3ea  mov     rax, [rcx]
0x18002d3ed  lea     r8, [rsp+220h+var_1B0]
0x18002d3f2  mov     edx, edi
0x18002d3f4  mov     rax, [rax+40h]
0x18002d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3fd  mov     [rbp+120h+var_E8], eax
0x18002d400  test    eax, eax
0x18002d402  js      loc_18002D8B1
0x18002d408  mov     [rbp+120h+var_E8], eax
0x18002d40b  cmp     word ptr [rsp+220h+var_1B0], 9
0x18002d411  jnz     loc_18002D885
0x18002d417  mov     [rbp+120h+var_E8], r14d
0x18002d41b  mov     rcx, qword ptr [rsp+220h+var_1B0+8]
0x18002d420  mov     rax, [rcx]
0x18002d423  lea     r8, [rsp+220h+var_1E0]
0x18002d428  lea     rdx, _GUID_8ddadb3b_f51d_4e16_aa67_4161a85e2deb
0x18002d42f  mov     rax, [rax]
0x18002d432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d437  mov     [rbp+120h+var_E8], eax
0x18002d43a  test    eax, eax
0x18002d43c  js      loc_18002D853
0x18002d442  mov     [rbp+120h+var_E8], eax
0x18002d445  mov     rcx, [rsp+220h+var_1E0]
0x18002d44a  mov     rax, [rcx]
0x18002d44d  lea     rdx, [rsp+220h+String1]
0x18002d452  mov     rax, [rax+18h]
0x18002d456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d45b  mov     [rbp+120h+var_E8], eax
0x18002d45e  test    eax, eax
0x18002d460  js      loc_18002D821
0x18002d466  mov     [rbp+120h+var_E8], eax
0x18002d469  mov     rcx, [rsp+220h+String1]; String1
0x18002d46e  test    rcx, rcx
0x18002d471  jz      loc_18002D7F5
0x18002d477  mov     [rbp+120h+var_E8], r14d
0x18002d47b  mov     rdx, r13; String2
0x18002d47e  call    cs:__imp__wcsicmp
0x18002d484  test    eax, eax
0x18002d486  jz      short loc_18002D4AD
0x18002d488  mov     rcx, [rsp+220h+String1]; bstrString
0x18002d48d  call    cs:__imp_SysFreeString
0x18002d493  nop
0x18002d494  mov     rcx, [rsp+220h+var_1E0]
0x18002d499  test    rcx, rcx
0x18002d49c  jz      short loc_18002D4AB
0x18002d49e  mov     rax, [rcx]
0x18002d4a1  mov     rax, [rax+10h]
0x18002d4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4aa  nop
0x18002d4ab  jmp     short loc_18002D525
0x18002d4ad  mov     r14, [rsp+220h+var_1E0]
0x18002d4b2  mov     r15, [r14]
0x18002d4b5  mov     rcx, r12; psz
0x18002d4b8  call    cs:__imp_SysAllocString
0x18002d4be  mov     rbx, rax
0x18002d4c1  mov     [rsp+220h+pExceptionObject], rax
0x18002d4c6  test    rax, rax
0x18002d4c9  jz      loc_18002D7DB
0x18002d4cf  mov     rdx, rax
0x18002d4d2  mov     rcx, r14
0x18002d4d5  mov     rax, [r15+20h]
0x18002d4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4de  mov     [rbp+120h+var_E8], eax
0x18002d4e1  mov     rcx, rbx; bstrString
0x18002d4e4  call    cs:__imp_SysFreeString
0x18002d4ea  mov     eax, [rbp+120h+var_E8]
0x18002d4ed  xor     r14d, r14d
0x18002d4f0  test    eax, eax
0x18002d4f2  js      loc_18002D7A9
0x18002d4f8  mov     [rbp+120h+var_E8], eax
0x18002d4fb  lea     r15d, [r14+1]
0x18002d4ff  mov     ebx, r15d
0x18002d502  mov     rcx, [rsp+220h+String1]; bstrString
0x18002d507  call    cs:__imp_SysFreeString
0x18002d50d  nop
0x18002d50e  mov     rcx, [rsp+220h+var_1E0]
0x18002d513  test    rcx, rcx
0x18002d516  jz      short loc_18002D525
0x18002d518  mov     rax, [rcx]
0x18002d51b  mov     rax, [rax+10h]
0x18002d51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d524  nop
0x18002d525  lea     rcx, [rsp+220h+var_1B0]; pvarg
0x18002d52a  call    cs:__imp_VariantClear
0x18002d530  add     edi, r15d
0x18002d533  cmp     edi, [rsp+220h+var_1F0]
0x18002d537  jle     loc_18002D3CF
0x18002d53d  test    ebx, ebx
0x18002d53f  jz      short loc_18002D5A6
0x18002d541  mov     [rsp+220h+pExceptionObject], r14
0x18002d546  mov     rcx, [rsp+220h+var_1C8]
0x18002d54b  mov     rax, [rcx]
0x18002d54e  lea     r8, [rsp+220h+pExceptionObject]
0x18002d553  lea     rdx, _GUID_0770687e_9f36_4d6f_8778_599d188461c9
0x18002d55a  mov     rax, [rax]
0x18002d55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d562  mov     [rbp+120h+var_E8], eax
0x18002d565  test    eax, eax
0x18002d567  js      loc_18002D777
0x18002d56d  mov     [rbp+120h+var_E8], eax
0x18002d570  mov     rcx, [rsp+220h+pExceptionObject]
0x18002d575  mov     rax, [rcx]
0x18002d578  mov     rax, [rax+58h]
0x18002d57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d581  mov     [rbp+120h+var_E8], eax
0x18002d584  test    eax, eax
0x18002d586  js      loc_18002D745
0x18002d58c  mov     [rbp+120h+var_E8], eax
0x18002d58f  mov     rcx, [rsp+220h+pExceptionObject]
0x18002d594  test    rcx, rcx
0x18002d597  jz      short loc_18002D5A6
0x18002d599  mov     rax, [rcx]
0x18002d59c  mov     rax, [rax+10h]
0x18002d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5a5  nop
0x18002d5a6  lea     rcx, [rbp+120h+pvarg]; pvarg
0x18002d5aa  call    cs:__imp_VariantClear
0x18002d5b0  add     esi, r15d
0x18002d5b3  cmp     esi, [rsp+220h+var_1EC]
0x18002d5b7  jle     loc_18002D30E
0x18002d5bd  mov     rcx, [rsp+220h+var_1D0]
0x18002d5c2  test    rcx, rcx
0x18002d5c5  jz      short loc_18002D5D4
0x18002d5c7  mov     rax, [rcx]
0x18002d5ca  mov     rax, [rax+10h]
0x18002d5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5d3  nop
0x18002d5d4  mov     rcx, [rsp+220h+var_1C8]
0x18002d5d9  test    rcx, rcx
0x18002d5dc  jz      short loc_18002D5EB
0x18002d5de  mov     rax, [rcx]
0x18002d5e1  mov     rax, [rax+10h]
0x18002d5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5ea  nop
0x18002d5eb  mov     rcx, [rsp+220h+var_1C0]
0x18002d5f0  test    rcx, rcx
0x18002d5f3  jz      short loc_18002D602
0x18002d5f5  mov     rax, [rcx]
0x18002d5f8  mov     rax, [rax+10h]
0x18002d5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d601  nop
0x18002d602  mov     rcx, [rsp+220h+var_1B8]
0x18002d607  test    rcx, rcx
0x18002d60a  jz      short loc_18002D619
0x18002d60c  mov     rax, [rcx]
0x18002d60f  mov     rax, [rax+10h]
0x18002d613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d618  nop
0x18002d619  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18002d620  mov     [rbp+120h+var_F0], rax
0x18002d624  lea     rcx, [rbp+120h+var_F0]; this
0x18002d628  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18002d62d  mov     rcx, [rbp+120h+var_40]
0x18002d634  xor     rcx, rsp; StackCookie
0x18002d637  call    __security_check_cookie
0x18002d63c  mov     rbx, [rsp+220h+arg_0]
0x18002d644  add     rsp, 1F0h
0x18002d64b  pop     r15
0x18002d64d  pop     r14
0x18002d64f  pop     r13
0x18002d651  pop     r12
0x18002d653  pop     rdi
0x18002d654  pop     rsi
0x18002d655  pop     rbp
0x18002d656  retn
0x18002d657  mov     edx, 80070057h; int
  ... truncated ...
```
