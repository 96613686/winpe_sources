# CPropertyBagFieldsBase::GetProperties(_FSRM_PROPERTYBAG_PROPERTIES *)

- ea: `0x1800851ec`
- end: `0x1800859fa`
- name: `?GetProperties@CPropertyBagFieldsBase@@QEBAXPEAU_FSRM_PROPERTYBAG_PROPERTIES@@@Z`
- size: `2062`
- prototype: `void __fastcall(CPropertyBagFieldsBase *__hidden this, struct _FSRM_PROPERTYBAG_PROPERTIES *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180045ee0`
- `0x18008ee10`

## callees

- `0x180006a1c`
- `0x180012238`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800851ec`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800853b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800853ea`
- `OLEAUT32!__imp_SysAllocString` at `0x1800853b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800853ea`
- `OLEAUT32!__imp_VariantInit` at `0x180085514`
- `OLEAUT32!__imp_VariantInit` at `0x180085514`
- `OLEAUT32!__imp_VariantClear` at `0x18008554c`
- `OLEAUT32!__imp_VariantClear` at `0x18008554c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085436`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085456`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085476`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18008553c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085436`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085456`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180085476`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18008553c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800854bc`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800854bc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800854ef`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800854ef`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800852f0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008531a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180085342`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008536c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800852f0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008531a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180085342`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18008536c`

## string_xrefs

- `0x180085980`: `SafeArrayCopy`
- `0x180085760`: `SafeArrayCreateVector`
- `0x1800857a9`: `SafeArrayCreateVector`
- `0x1800857f6`: `SafeArrayCreateVector`
- `0x180085847`: `SafeArrayCreateVector`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CPropertyBagFieldsBase::GetProperties(
        CPropertyBagFieldsBase *this,
        struct _FSRM_PROPERTYBAG_PROPERTIES *a2)
{
  SAFEARRAY *Vector; // r12
  SAFEARRAY *v5; // r13
  SAFEARRAY *v6; // r15
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r14
  BSTR v11; // rax
  BSTR v12; // rax
  LONG v13; // eax
  SAFEARRAY *v14; // rbx
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned int Hr; // ebx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // ebx
  __int64 v24; // rax
  unsigned int v25; // ebx
  __int64 v26; // rax
  unsigned int v27; // ebx
  __int64 v28; // rax
  unsigned int v29; // ebx
  __int64 v30; // rax
  const OLECHAR *v31; // [rsp+40h] [rbp-C0h]
  const OLECHAR *v32; // [rsp+40h] [rbp-C0h]
  LONG rgIndices; // [rsp+48h] [rbp-B8h] BYREF
  VARTYPE pvt; // [rsp+4Ch] [rbp-B4h] BYREF
  void **v35; // [rsp+50h] [rbp-B0h]
  SAFEARRAY *v36; // [rsp+58h] [rbp-A8h]
  void **v37; // [rsp+60h] [rbp-A0h]
  SAFEARRAY *v38; // [rsp+68h] [rbp-98h]
  void **v39; // [rsp+70h] [rbp-90h]
  SAFEARRAY *v40; // [rsp+78h] [rbp-88h]
  void **v41; // [rsp+80h] [rbp-80h]
  SAFEARRAY *v42; // [rsp+88h] [rbp-78h]
  void **v43; // [rsp+90h] [rbp-70h]
  SAFEARRAY *v44; // [rsp+98h] [rbp-68h]
  SAFEARRAY *ppsaOut; // [rsp+A0h] [rbp-60h] BYREF
  SAFEARRAY *psa; // [rsp+A8h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v48[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v49; // [rsp+E0h] [rbp-20h]
  int v50; // [rsp+E4h] [rbp-1Ch]
  int v51; // [rsp+E8h] [rbp-18h]
  _BYTE v52[96]; // [rsp+F0h] [rbp-10h] BYREF
  int v53; // [rsp+150h] [rbp+50h]
  VARIANTARG v54; // [rsp+158h] [rbp+58h] BYREF
  VARIANTARG v55; // [rsp+170h] [rbp+70h] BYREF
  VARIANTARG pv; // [rsp+188h] [rbp+88h] BYREF
  void **v57; // [rsp+1A0h] [rbp+A0h] BYREF
  HRESULT Vartype; // [rsp+1A8h] [rbp+A8h]

  v48[0] = L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp";
  v48[1] = L"CPropertyBagFieldsBase::GetProperties";
  v48[2] = L"SRMPROPC";
  v49 = 307;
  v50 = 17;
  v51 = 255;
  v53 = 0x1000000;
  memset_0(v52, 0, sizeof(v52));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v57, (const struct CSrmDebugInfo *)v48, 0);
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  v44 = 0;
  v43 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  v42 = 0;
  v41 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  v40 = 0;
  v39 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  v38 = 0;
  v37 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  psa = SafeArrayCreateVector(0xCu, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 16LL));
  v44 = psa;
  if ( !psa )
  {
    v19 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v48,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
            (__int64)L"SRMPROPC",
            (__int64)L"CPropertyBagFieldsBase::GetProperties",
            321,
            17);
    CSrmFunctionTracer::Throw(&v57, v19, 2147942414LL, L"SafeArrayCreateVector");
  }
  Vector = SafeArrayCreateVector(0xCu, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 16LL));
  v42 = Vector;
  if ( !Vector )
  {
    v20 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v48,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
            (__int64)L"SRMPROPC",
            (__int64)L"CPropertyBagFieldsBase::GetProperties",
            329,
            17);
    CSrmFunctionTracer::Throw(&v57, v20, 2147942414LL, L"SafeArrayCreateVector");
  }
  v5 = SafeArrayCreateVector(0xCu, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 16LL));
  v40 = v5;
  if ( !v5 )
  {
    v21 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v48,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
            (__int64)L"SRMPROPC",
            (__int64)L"CPropertyBagFieldsBase::GetProperties",
            337,
            17);
    CSrmFunctionTracer::Throw(&v57, v21, 2147942414LL, L"SafeArrayCreateVector");
  }
  v6 = SafeArrayCreateVector(0xCu, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 16LL));
  v38 = v6;
  if ( !v6 )
  {
    v22 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v48,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
            (__int64)L"SRMPROPC",
            (__int64)L"CPropertyBagFieldsBase::GetProperties",
            345,
            17);
    CSrmFunctionTracer::Throw(&v57, v22, 2147942414LL, L"SafeArrayCreateVector");
  }
  rgIndices = 0;
  v7 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v7 + 16) )
  {
    v8 = 0;
    do
    {
      v9 = 32LL * v8;
      v10 = *(_QWORD *)(v7 + 24);
      v31 = *(const OLECHAR **)(v9 + v10);
      v11 = SysAllocString(v31);
      if ( !v11 && v31 )
        _com_issue_error(-2147024882);
      pv.vt = 8;
      pv.llVal = (LONGLONG)v11;
      v32 = *(const OLECHAR **)(v9 + v10 + 8);
      v12 = SysAllocString(v32);
      if ( !v12 && v32 )
        _com_issue_error(-2147024882);
      v55.vt = 8;
      v55.llVal = (LONGLONG)v12;
      v13 = *(_DWORD *)(v9 + v10 + 24);
      v54.vt = 3;
      v54.lVal = v13;
      Vartype = SafeArrayPutElement(psa, &rgIndices, &pv);
      if ( Vartype < 0 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v18 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                359,
                17);
        CSrmFunctionTracer::Throw(&v57, v18, Hr, L"SafeArrayPutElement");
      }
      Vartype = SafeArrayPutElement(Vector, &rgIndices, &v55);
      if ( Vartype < 0 )
      {
        v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v16 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                365,
                17);
        CSrmFunctionTracer::Throw(&v57, v16, v15, L"SafeArrayPutElement");
      }
      Vartype = SafeArrayPutElement(v6, &rgIndices, &v54);
      if ( Vartype < 0 )
      {
        v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v30 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                371,
                17);
        CSrmFunctionTracer::Throw(&v57, v30, v29, L"SafeArrayPutElement");
      }
      ppsaOut = 0;
      v36 = 0;
      v35 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
      Vartype = SafeArrayCopy(*(SAFEARRAY **)(v9 + v10 + 16), &ppsaOut);
      if ( Vartype < 0 )
      {
        v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v28 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                383,
                17);
        CSrmFunctionTracer::Throw(&v57, v28, v27, L"SafeArrayCopy");
      }
      v14 = ppsaOut;
      v36 = ppsaOut;
      pvt = 0;
      Vartype = SafeArrayGetVartype(ppsaOut, &pvt);
      if ( Vartype < 0 )
      {
        v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v26 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                391,
                17);
        CSrmFunctionTracer::Throw(&v57, v26, v25, L"SafeArrayGetVarType");
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = pvt | 0x2000;
      v36 = 0;
      pvarg.llVal = (LONGLONG)v14;
      Vartype = SafeArrayPutElement(v5, &rgIndices, &pvarg);
      VariantClear(&pvarg);
      if ( Vartype < 0 )
      {
        v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v57);
        v24 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v48,
                (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmprop.cpp",
                (__int64)L"SRMPROPC",
                (__int64)L"CPropertyBagFieldsBase::GetProperties",
                404,
                17);
        CSrmFunctionTracer::Throw(&v57, v24, v23, L"SafeArrayPutElement");
      }
      v35 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
      v36 = 0;
      _variant_t::~_variant_t(&v54);
      _variant_t::~_variant_t(&v55);
      _variant_t::~_variant_t(&pv);
      v8 = rgIndices + 1;
      rgIndices = v8;
      v7 = *((_QWORD *)this + 2);
    }
    while ( v8 < *(_DWORD *)(v7 + 16) );
  }
  *(_QWORD *)a2 = psa;
  *((_QWORD *)a2 + 1) = Vector;
  *((_QWORD *)a2 + 2) = v5;
  *((_QWORD *)a2 + 3) = v6;
  v37 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v38 = 0;
  v39 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v40 = 0;
  v41 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v42 = 0;
  v43 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v44 = 0;
  v57 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v57);
}

```

## disassembly

```asm
0x1800851ec  mov     [rsp-8+arg_10], rbx
0x1800851f1  push    rbp
0x1800851f2  push    rsi
0x1800851f3  push    rdi
0x1800851f4  push    r12
0x1800851f6  push    r13
0x1800851f8  push    r14
0x1800851fa  push    r15
0x1800851fc  lea     rbp, [rsp-160h]
0x180085204  sub     rsp, 260h
0x18008520b  mov     rax, cs:__security_cookie
0x180085212  xor     rax, rsp
0x180085215  mov     [rbp+190h+var_40], rax
0x18008521c  mov     rdi, rdx
0x18008521f  mov     rsi, rcx
0x180085222  lea     rax, [rbp+190h+var_1C8]
0x180085226  mov     [rsp+290h+var_250], rax
0x18008522b  lea     rbx, aBaseFsFsrmUtil_17; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180085232  mov     [rbp+190h+var_1C8], rbx
0x180085236  lea     r15, aCpropertybagfi_0; "CPropertyBagFieldsBase::GetProperties"
0x18008523d  mov     [rbp+190h+var_1C0], r15
0x180085241  lea     r13, aSrmpropc; "SRMPROPC"
0x180085248  mov     [rbp+190h+var_1B8], r13
0x18008524c  mov     [rbp+190h+var_1B0], 133h
0x180085253  mov     r12d, 11h
0x180085259  mov     [rbp+190h+var_1AC], r12d
0x18008525d  mov     [rbp+190h+var_1A8], 0FFh
0x180085264  xor     r14d, r14d
0x180085267  mov     [rbp+190h+var_140], 1000000h
0x18008526e  xor     edx, edx; Val
0x180085270  lea     r8d, [r12+4Fh]; Size
0x180085275  lea     rcx, [rbp+190h+var_1A0]; void *
0x180085279  call    memset_0
0x18008527e  nop
0x18008527f  xor     r8d, r8d
0x180085282  lea     rdx, [rbp+190h+var_1C8]
0x180085286  lea     rcx, [rbp+190h+var_F0]
0x18008528d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180085292  nop
0x180085293  xorps   xmm0, xmm0
0x180085296  movups  xmmword ptr [rdi], xmm0
0x180085299  movups  xmmword ptr [rdi+10h], xmm0
0x18008529d  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x1800852a4  mov     [rbp+190h+var_200], rax
0x1800852a8  mov     [rbp+190h+var_1F8], r14
0x1800852ac  lea     rcx, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x1800852b3  mov     [rbp+190h+var_200], rcx
0x1800852b7  mov     [rbp+190h+var_210], rax
0x1800852bb  mov     [rbp+190h+var_208], r14
0x1800852bf  mov     [rbp+190h+var_210], rcx
0x1800852c3  mov     [rsp+290h+var_220], rax
0x1800852c8  mov     [rsp+290h+var_218], r14
0x1800852cd  mov     [rsp+290h+var_220], rcx
0x1800852d2  mov     [rsp+290h+var_230], rax
0x1800852d7  mov     [rsp+290h+var_228], r14
0x1800852dc  mov     [rsp+290h+var_230], rcx
0x1800852e1  mov     r8, [rsi+10h]
0x1800852e5  lea     ecx, [r12-5]; vt
0x1800852ea  mov     r8d, [r8+10h]; cElements
0x1800852ee  xor     edx, edx; lLbound
0x1800852f0  call    cs:__imp_SafeArrayCreateVector
0x1800852f6  mov     [rbp+190h+psa], rax
0x1800852fa  mov     [rbp+190h+var_1F8], r14
0x1800852fe  mov     [rbp+190h+var_1F8], rax
0x180085302  test    rax, rax
0x180085305  jz      loc_180085737
0x18008530b  mov     r8, [rsi+10h]
0x18008530f  lea     ecx, [r12-5]; vt
0x180085314  mov     r8d, [r8+10h]; cElements
0x180085318  xor     edx, edx; lLbound
0x18008531a  call    cs:__imp_SafeArrayCreateVector
0x180085320  mov     r12, rax
0x180085323  mov     [rbp+190h+var_208], r14
0x180085327  mov     [rbp+190h+var_208], rax
0x18008532b  test    rax, rax
0x18008532e  jz      loc_18008577D
0x180085334  mov     r8, [rsi+10h]
0x180085338  lea     ecx, [r14+0Ch]; vt
0x18008533c  mov     r8d, [r8+10h]; cElements
0x180085340  xor     edx, edx; lLbound
0x180085342  call    cs:__imp_SafeArrayCreateVector
0x180085348  mov     r13, rax
0x18008534b  mov     [rsp+290h+var_218], r14
0x180085350  mov     [rsp+290h+var_218], rax
0x180085355  test    rax, rax
0x180085358  jz      loc_1800857C6
0x18008535e  mov     r8, [rsi+10h]
0x180085362  lea     ecx, [r14+0Ch]; vt
0x180085366  mov     r8d, [r8+10h]; cElements
0x18008536a  xor     edx, edx; lLbound
0x18008536c  call    cs:__imp_SafeArrayCreateVector
0x180085372  mov     r15, rax
0x180085375  mov     [rsp+290h+var_228], r14
0x18008537a  mov     [rsp+290h+var_228], rax
0x18008537f  test    rax, rax
0x180085382  jz      loc_180085813
0x180085388  mov     [rsp+290h+rgIndices], r14d
0x18008538d  mov     rcx, [rsi+10h]
0x180085391  cmp     [rcx+10h], r14d
0x180085395  jbe     loc_1800855B8
0x18008539b  mov     eax, r14d
0x18008539e  mov     ebx, eax
0x1800853a0  shl     rbx, 5
0x1800853a4  mov     r14, [rcx+18h]
0x1800853a8  mov     rax, [rbx+r14]
0x1800853ac  mov     [rsp+290h+var_250], rax
0x1800853b1  mov     rcx, rax; psz
0x1800853b4  call    cs:__imp_SysAllocString
0x1800853ba  test    rax, rax
0x1800853bd  jnz     short loc_1800853CA
0x1800853bf  cmp     [rsp+290h+var_250], rax
0x1800853c4  jnz     loc_180085864
0x1800853ca  mov     ecx, 8
0x1800853cf  mov     [rbp+190h+pv], cx
0x1800853d6  mov     [rbp+190h+var_100], rax
0x1800853dd  mov     rax, [rbx+r14+8]
0x1800853e2  mov     [rsp+290h+var_250], rax
0x1800853e7  mov     rcx, rax; psz
0x1800853ea  call    cs:__imp_SysAllocString
0x1800853f0  test    rax, rax
0x1800853f3  jnz     short loc_180085400
0x1800853f5  cmp     [rsp+290h+var_250], rax
0x1800853fa  jnz     loc_18008586F
0x180085400  mov     ecx, 8
0x180085405  mov     [rbp+190h+var_120], cx
0x180085409  mov     [rbp+190h+var_118], rax
0x18008540d  mov     eax, [rbx+r14+18h]
0x180085412  mov     ecx, 3
0x180085417  mov     [rbp+190h+var_138], cx
0x18008541b  mov     [rbp+190h+var_130], ax
0x18008541f  sar     eax, 10h
0x180085422  mov     [rbp+190h+var_12E], ax
0x180085426  lea     r8, [rbp+190h+pv]; pv
0x18008542d  lea     rdx, [rsp+290h+rgIndices]; rgIndices
0x180085432  mov     rcx, [rbp+190h+psa]; psa
0x180085436  call    cs:__imp_SafeArrayPutElement
0x18008543c  mov     [rbp+190h+var_E8], eax
0x180085442  test    eax, eax
0x180085444  js      loc_1800856D7
0x18008544a  lea     r8, [rbp+190h+var_120]; pv
0x18008544e  lea     rdx, [rsp+290h+rgIndices]; rgIndices
0x180085453  mov     rcx, r12; psa
0x180085456  call    cs:__imp_SafeArrayPutElement
0x18008545c  mov     [rbp+190h+var_E8], eax
0x180085462  test    eax, eax
0x180085464  js      loc_180085677
0x18008546a  lea     r8, [rbp+190h+var_138]; pv
0x18008546e  lea     rdx, [rsp+290h+rgIndices]; rgIndices
0x180085473  mov     rcx, r15; psa
0x180085476  call    cs:__imp_SafeArrayPutElement
0x18008547c  mov     [rbp+190h+var_E8], eax
0x180085482  test    eax, eax
0x180085484  js      loc_18008599A
0x18008548a  mov     [rbp+190h+ppsaOut], 0
0x180085492  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x180085499  mov     [rsp+290h+var_240], rax
0x18008549e  mov     [rsp+290h+var_238], 0
0x1800854a7  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x1800854ae  mov     [rsp+290h+var_240], rax
0x1800854b3  lea     rdx, [rbp+190h+ppsaOut]; ppsaOut
0x1800854b7  mov     rcx, [rbx+r14+10h]; psa
0x1800854bc  call    cs:__imp_SafeArrayCopy
0x1800854c2  mov     [rbp+190h+var_E8], eax
0x1800854c8  xor     r14d, r14d
0x1800854cb  test    eax, eax
0x1800854cd  js      loc_18008593A
0x1800854d3  mov     rbx, [rbp+190h+ppsaOut]
0x1800854d7  mov     [rsp+290h+var_238], r14
0x1800854dc  mov     [rsp+290h+var_238], rbx
0x1800854e1  mov     [rsp+290h+pvt], r14w
0x1800854e7  lea     rdx, [rsp+290h+pvt]; pvt
0x1800854ec  mov     rcx, rbx; psa
0x1800854ef  call    cs:__imp_SafeArrayGetVartype
0x1800854f5  mov     [rbp+190h+var_E8], eax
0x1800854fb  test    eax, eax
0x1800854fd  js      loc_1800858DA
0x180085503  xorps   xmm0, xmm0
0x180085506  xor     eax, eax
0x180085508  movups  xmmword ptr [rbp+190h+pvarg], xmm0
0x18008550c  mov     qword ptr [rbp+190h+pvarg+10h], rax
0x180085510  lea     rcx, [rbp+190h+pvarg]; pvarg
0x180085514  call    cs:__imp_VariantInit
0x18008551a  movzx   eax, [rsp+290h+pvt]
0x18008551f  or      ax, 2000h
0x180085523  mov     word ptr [rbp+190h+pvarg], ax
0x180085527  mov     [rsp+290h+var_238], r14
0x18008552c  mov     qword ptr [rbp+190h+pvarg+8], rbx
0x180085530  lea     r8, [rbp+190h+pvarg]; pv
0x180085534  lea     rdx, [rsp+290h+rgIndices]; rgIndices
0x180085539  mov     rcx, r13; psa
0x18008553c  call    cs:__imp_SafeArrayPutElement
0x180085542  mov     [rbp+190h+var_E8], eax
0x180085548  lea     rcx, [rbp+190h+pvarg]; pvarg
0x18008554c  call    cs:__imp_VariantClear
0x180085552  cmp     [rbp+190h+var_E8], r14d
0x180085559  jl      loc_18008587A
0x18008555f  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x180085566  mov     [rsp+290h+var_240], rax
0x18008556b  mov     [rsp+290h+var_238], r14
0x180085570  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x180085577  mov     [rsp+290h+var_240], rax
0x18008557c  mov     [rsp+290h+var_238], r14
0x180085581  lea     rcx, [rbp+190h+var_138]; this
0x180085585  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008558a  nop
0x18008558b  lea     rcx, [rbp+190h+var_120]; this
0x18008558f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180085594  nop
0x180085595  lea     rcx, [rbp+190h+pv]; this
0x18008559c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800855a1  mov     eax, [rsp+290h+rgIndices]
0x1800855a5  inc     eax
0x1800855a7  mov     [rsp+290h+rgIndices], eax
0x1800855ab  mov     rcx, [rsi+10h]
0x1800855af  cmp     eax, [rcx+10h]
0x1800855b2  jb      loc_18008539E
0x1800855b8  mov     [rbp+190h+var_1F8], r14
0x1800855bc  mov     rax, [rbp+190h+psa]
0x1800855c0  mov     [rdi], rax
0x1800855c3  mov     [rbp+190h+var_208], r14
0x1800855c7  mov     [rdi+8], r12
0x1800855cb  mov     [rsp+290h+var_218], r14
0x1800855d0  mov     [rdi+10h], r13
0x1800855d4  mov     [rsp+290h+var_228], r14
0x1800855d9  mov     [rdi+18h], r15
0x1800855dd  lea     rcx, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x1800855e4  mov     [rsp+290h+var_230], rcx
0x1800855e9  mov     [rsp+290h+var_228], r14
0x1800855ee  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x1800855f5  mov     [rsp+290h+var_230], rax
0x1800855fa  mov     [rsp+290h+var_228], r14
0x1800855ff  mov     [rsp+290h+var_220], rcx
0x180085604  mov     [rsp+290h+var_218], r14
0x180085609  mov     [rsp+290h+var_220], rax
0x18008560e  mov     [rsp+290h+var_218], r14
0x180085613  mov     [rbp+190h+var_210], rcx
0x180085617  mov     [rbp+190h+var_208], r14
0x18008561b  mov     [rbp+190h+var_210], rax
0x18008561f  mov     [rbp+190h+var_208], r14
0x180085623  mov     [rbp+190h+var_200], rcx
0x180085627  mov     [rbp+190h+var_1F8], r14
0x18008562b  mov     [rbp+190h+var_200], rax
0x18008562f  mov     [rbp+190h+var_1F8], r14
0x180085633  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008563a  mov     [rbp+190h+var_F0], rax
0x180085641  lea     rcx, [rbp+190h+var_F0]; this
0x180085648  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008564d  mov     rcx, [rbp+190h+var_40]
0x180085654  xor     rcx, rsp; StackCookie
0x180085657  call    __security_check_cookie
0x18008565c  mov     rbx, [rsp+290h+arg_10]
0x180085664  add     rsp, 260h
0x18008566b  pop     r15
0x18008566d  pop     r14
0x18008566f  pop     r13
0x180085671  pop     r12
0x180085673  pop     rdi
0x180085674  pop     rsi
0x180085675  pop     rbp
0x180085676  retn
0x180085677  lea     rcx, [rbp+190h+var_F0]; this
0x18008567e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180085683  mov     ebx, eax
0x180085685  lea     rax, [rbp+190h+var_1C8]
0x180085689  mov     [rsp+290h+var_250], rax
0x18008568e  mov     [rsp+290h+var_268], 11h
0x180085696  mov     [rsp+290h+var_270], 16Dh
0x18008569e  lea     r9, aCpropertybagfi_0; "CPropertyBagFieldsBase::GetProperties"
0x1800856a5  lea     r8, aSrmpropc; "SRMPROPC"
0x1800856ac  lea     rdx, aBaseFsFsrmUtil_17; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x1800856b3  lea     rcx, [rbp+190h+var_1C8]
0x1800856b7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800856bc  nop
0x1800856bd  lea     r9, aSafearrayputel; "SafeArrayPutElement"
0x1800856c4  mov     r8d, ebx
0x1800856c7  mov     rdx, rax
0x1800856ca  lea     rcx, [rbp+190h+var_F0]
0x1800856d1  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800856d7  lea     rcx, [rbp+190h+var_F0]; this
0x1800856de  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800856e3  mov     ebx, eax
0x1800856e5  lea     rax, [rbp+190h+var_1C8]
0x1800856e9  mov     [rsp+290h+var_250], rax
0x1800856ee  mov     [rsp+290h+var_268], 11h
0x1800856f6  mov     [rsp+290h+var_270], 167h
0x1800856fe  lea     r9, aCpropertybagfi_0; "CPropertyBagFieldsBase::GetProperties"
0x180085705  lea     r8, aSrmpropc; "SRMPROPC"
0x18008570c  lea     rdx, aBaseFsFsrmUtil_17; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180085713  lea     rcx, [rbp+190h+var_1C8]
0x180085717  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18008571c  nop
0x18008571d  lea     r9, aSafearrayputel; "SafeArrayPutElement"
0x180085724  mov     r8d, ebx
0x180085727  mov     rdx, rax
0x18008572a  lea     rcx, [rbp+190h+var_F0]
0x180085731  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180085737  lea     rax, [rbp+190h+var_1C8]
0x18008573b  mov     [rsp+290h+var_250], rax
0x180085740  mov     [rsp+290h+var_268], r12d
0x180085745  mov     [rsp+290h+var_270], 141h
  ... truncated ...
```
