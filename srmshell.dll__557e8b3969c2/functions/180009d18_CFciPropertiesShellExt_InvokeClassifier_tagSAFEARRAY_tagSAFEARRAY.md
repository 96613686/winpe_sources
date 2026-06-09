# CFciPropertiesShellExt::InvokeClassifier(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x180009d18`
- end: `0x18000a458`
- name: `?InvokeClassifier@CFciPropertiesShellExt@@AEAAXPEAUtagSAFEARRAY@@0@Z`
- size: `1856`
- prototype: `void __fastcall(HANDLE *this, SAFEARRAY *psa, struct tagSAFEARRAY *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800061d0`
- `0x180009ba0`

## callees

- `0x180001e44`
- `0x180006688`
- `0x1800083e0`
- `0x180008408`
- `0x180009d18`
- `0x18000d368`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a076`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a076`
- `OLEAUT32!__imp_VariantInit` at `0x180009ebb`
- `OLEAUT32!__imp_VariantInit` at `0x18000a031`
- `OLEAUT32!__imp_VariantInit` at `0x180009ebb`
- `OLEAUT32!__imp_VariantInit` at `0x18000a031`
- `OLEAUT32!__imp_VariantClear` at `0x18000a0db`
- `OLEAUT32!__imp_VariantClear` at `0x18000a191`
- `OLEAUT32!__imp_VariantClear` at `0x18000a0db`
- `OLEAUT32!__imp_VariantClear` at `0x18000a191`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ed8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009ed8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180009f55`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180009f55`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180009f2e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180009f2e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000a09f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000a09f`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180009ff6`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180009ff6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009e38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009e38`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::InvokeClassifier(HANDLE *this, SAFEARRAY *psa, struct tagSAFEARRAY *a3)
{
  struct IFsrmClassificationManager2 *v5; // rbx
  unsigned __int64 v6; // r14
  LONG v7; // ecx
  LONG v8; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  int v11; // r15d
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r14
  __int64 v15; // rax
  HRESULT v16; // eax
  unsigned __int64 v17; // r13
  unsigned __int64 j; // rax
  __int64 v19; // rcx
  BSTR v20; // rax
  HRESULT v21; // eax
  int v22; // eax
  unsigned __int64 v23; // rdx
  char *k; // rax
  __int64 v25; // rcx
  _WORD *v26; // r8
  int v27; // eax
  char v28; // al
  int v29; // eax
  char v30; // al
  int v31; // eax
  char v32; // al
  int v33; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  char Hr; // al
  int v38; // eax
  char v39; // al
  LONG plLbound; // [rsp+40h] [rbp-248h] BYREF
  LONG plUbound; // [rsp+44h] [rbp-244h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-240h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-238h]
  CFciPropertiesShellExt *v44; // [rsp+58h] [rbp-230h]
  int pExceptionObject; // [rsp+60h] [rbp-228h] BYREF
  LONG rgIndices; // [rsp+64h] [rbp-224h] BYREF
  unsigned __int64 v47; // [rsp+68h] [rbp-220h]
  int v48; // [rsp+70h] [rbp-218h]
  __int64 i; // [rsp+78h] [rbp-210h]
  struct IFsrmClassificationManager2 *v50; // [rsp+80h] [rbp-208h] BYREF
  _QWORD *v51; // [rsp+88h] [rbp-200h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-1F8h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-1D8h]
  unsigned __int64 v54; // [rsp+B8h] [rbp-1D0h]
  struct tagSAFEARRAY *v55; // [rsp+C0h] [rbp-1C8h]
  SAFEARRAY *v56; // [rsp+C8h] [rbp-1C0h]
  VARIANTARG pv; // [rsp+D0h] [rbp-1B8h] BYREF
  _QWORD v58[3]; // [rsp+F8h] [rbp-190h] BYREF
  int v59; // [rsp+110h] [rbp-178h]
  int v60; // [rsp+114h] [rbp-174h]
  int v61; // [rsp+118h] [rbp-170h]
  _DWORD v62[28]; // [rsp+120h] [rbp-168h] BYREF
  void **v63; // [rsp+190h] [rbp-F8h] BYREF
  int v64; // [rsp+198h] [rbp-F0h]

  v55 = a3;
  v56 = psa;
  v44 = (CFciPropertiesShellExt *)this;
  v51 = v58;
  v58[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  v58[1] = L"CFciPropertiesShellExt::InvokeClassifier";
  v58[2] = L"FCIPROPC";
  v59 = 4941;
  v60 = 17;
  v61 = 255;
  v62[24] = 0x1000000;
  memset_0(v62, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v63, v58, 0);
  this[29] = 0;
  *((_DWORD *)this + 60) = 0;
  v50 = 0;
  CFciPropertiesShellExt::CreateClassificationManager((CFciPropertiesShellExt *)this, &v50);
  v5 = v50;
  CFciPropertiesShellExt::GetPropertyDefinitions(v50, *((unsigned int *)this + 61), this + 12);
  if ( WaitForSingleObject(this[19], 0) == 258 )
  {
    v6 = 0xCCCCCCCCCCCCCCCDuLL * (((_BYTE *)this[4] - (_BYTE *)this[3]) >> 3);
    v47 = v6;
    if ( v6 > 0x3E8 )
      v6 = 1000;
    v54 = v6;
    v47 = v6;
    VariantInit(&pvarg);
    rgsabound.cElements = v6;
    rgsabound.lLbound = 0;
    pvarg.llVal = (LONGLONG)SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( !pvarg.llVal )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x1372u, Hr, 0);
    }
    v64 = 0;
    pvarg.vt = 8204;
    v7 = 0;
    plLbound = 0;
    v8 = -1;
    plUbound = -1;
    if ( psa )
    {
      LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
      v64 = LBound;
      if ( LBound < 0 )
      {
        v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v27);
        v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x137Cu, v28, 0);
      }
      v64 = LBound;
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      v64 = UBound;
      if ( UBound < 0 )
      {
        v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v29);
        v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x137Du, v30, 0);
      }
      v64 = UBound;
      v7 = plLbound;
      v8 = plUbound;
    }
    LODWORD(v47) = v8 - v7 == -1;
    v11 = 0;
    v48 = 0;
    v12 = 0;
    for ( i = 0; ; i += v14 )
    {
      v13 = 0xCCCCCCCCCCCCCCCDuLL * (((_BYTE *)this[4] - (_BYTE *)this[3]) >> 3);
      if ( v12 >= v13 )
        break;
      v14 = v13 - v12;
      v53 = v14;
      v15 = 1000;
      if ( v14 <= 0x3E8 )
      {
        v15 = v14;
      }
      else
      {
        v14 = 1000;
        v53 = 1000;
      }
      if ( v15 != v54 )
      {
        rgsabound.cElements = v14;
        v16 = SafeArrayRedim(pvarg.parray, &rgsabound);
        v64 = v16;
        if ( v16 < 0 )
        {
          v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v31);
          v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x1399u, v32, 0);
        }
        v64 = v16;
      }
      v17 = 0;
      v51 = 0;
      for ( j = 0; j < v14; j = v17 )
      {
        VariantInit(&pv);
        v19 = (__int64)this[3] + 40 * v17 + 40 * i;
        if ( *(_QWORD *)(v19 + 24) >= 8u )
          v19 = *(_QWORD *)v19;
        if ( v19 )
        {
          bstrString = SysAllocString((const OLECHAR *)v19);
          if ( !bstrString )
          {
            pExceptionObject = -2147024882;
            throw (long *)&pExceptionObject;
          }
        }
        else
        {
          bstrString = 0;
        }
        v20 = bstrString;
        bstrString = 0;
        pv.llVal = (LONGLONG)v20;
        SysFreeString(0);
        pv.vt = 8;
        rgIndices = v17;
        v21 = SafeArrayPutElement(pvarg.parray, &rgIndices, &pv);
        v64 = v21;
        if ( v21 < 0 )
        {
          v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v33);
          v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x13A3u, v34, 0);
        }
        v64 = v21;
        VariantClear(&pv);
        v51 = (_QWORD *)++v17;
      }
      v22 = ((__int64 (__fastcall *)(struct IFsrmClassificationManager2 *, LONGLONG, SAFEARRAY *, struct tagSAFEARRAY *, _DWORD))v5->lpVtbl->ClassifyFiles)(
              v5,
              pvarg.llVal,
              v56,
              v55,
              v47);
      v64 = v22;
      if ( v22 == -2147200141 )
      {
        v64 = 0;
        break;
      }
      if ( v22 < 0 )
      {
        if ( v11 >= 0 )
          v11 = v22;
        v48 = v11;
        v64 = 0;
      }
      v12 = v14 + i;
    }
    v64 = v11;
    if ( v11 < 0 )
    {
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v35);
      v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x13C2u, v36, 0);
    }
    v64 = v11;
    VariantClear(&pvarg);
    if ( v5 )
      ((void (__fastcall *)(struct IFsrmClassificationManager2 *))v5->lpVtbl->Release)(v5);
    v23 = 0xCCCCCCCCCCCCCCCDuLL * (((_BYTE *)this[4] - (_BYTE *)this[3]) >> 3);
    for ( k = (char *)this[12]; k != this[13]; k += 224 )
    {
      v25 = *((unsigned int *)k + 53);
      if ( (_DWORD)v25 && v25 != v23 )
      {
        *((_DWORD *)k + 52) = 2;
        if ( *((_QWORD *)k + 24) < 8u )
          v26 = k + 168;
        else
          v26 = (_WORD *)*((_QWORD *)k + 21);
        *((_QWORD *)k + 23) = 0;
        *v26 = 0;
      }
    }
    if ( v64 < 0 )
    {
      v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v63, v38);
      v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v63);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v63, 0x13C8u, v39, 0);
    }
    v63 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v63);
  }
  else
  {
    if ( v5 )
      ((void (__fastcall *)(struct IFsrmClassificationManager2 *))v5->lpVtbl->Release)(v5);
    v63 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v63);
  }
}

```

## disassembly

```asm
0x180009d18  mov     r11, rsp
0x180009d1b  push    rbx
0x180009d1c  push    rsi
0x180009d1d  push    rdi
0x180009d1e  push    r12
0x180009d20  push    r13
0x180009d22  push    r14
0x180009d24  push    r15
0x180009d26  sub     rsp, 250h
0x180009d2d  mov     rax, cs:__security_cookie
0x180009d34  xor     rax, rsp
0x180009d37  mov     [rsp+288h+var_48], rax
0x180009d3f  mov     [rsp+288h+var_1C8], r8
0x180009d47  mov     r15, rdx
0x180009d4a  mov     [rsp+288h+var_1C0], rdx
0x180009d52  mov     rsi, rcx
0x180009d55  mov     [rsp+288h+var_230], rcx
0x180009d5a  lea     rax, [r11-190h]
0x180009d61  mov     [r11-200h], rax
0x180009d68  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180009d6f  mov     [r11-190h], rax
0x180009d76  lea     rax, aCfciproperties_4; "CFciPropertiesShellExt::InvokeClassifie"...
0x180009d7d  mov     [r11-188h], rax
0x180009d84  lea     rax, aFcipropc; "FCIPROPC"
0x180009d8b  mov     [r11-180h], rax
0x180009d92  mov     [rsp+288h+var_178], 134Dh
0x180009d9d  mov     [rsp+288h+var_174], 11h
0x180009da8  mov     [rsp+288h+var_170], 0FFh
0x180009db3  xor     edi, edi
0x180009db5  mov     [rsp+288h+var_108], 1000000h
0x180009dc0  xor     edx, edx; Val
0x180009dc2  lea     r12d, [rdi+1]
0x180009dc6  lea     r8d, [rdi+60h]; Size
0x180009dca  lea     rcx, [r11-168h]; void *
0x180009dd1  call    memset_0
0x180009dd6  nop
0x180009dd7  xor     r8d, r8d
0x180009dda  lea     rdx, [rsp+288h+var_190]
0x180009de2  lea     rcx, [rsp+288h+var_F8]
0x180009dea  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180009def  nop
0x180009df0  mov     [rsi+0E8h], rdi
0x180009df7  mov     [rsi+0F0h], edi
0x180009dfd  mov     [rsp+288h+var_208], rdi
0x180009e05  lea     rdx, [rsp+288h+var_208]; struct IFsrmClassificationManager2 **
0x180009e0d  mov     rcx, rsi; this
0x180009e10  call    ?CreateClassificationManager@CFciPropertiesShellExt@@AEAAXPEAPEAUIFsrmClassificationManager2@@@Z; CFciPropertiesShellExt::CreateClassificationManager(IFsrmClassificationManager2 * *)
0x180009e15  lea     r8, [rsi+60h]
0x180009e19  mov     edx, [rsi+0F4h]
0x180009e1f  mov     rbx, [rsp+288h+var_208]
0x180009e27  mov     rcx, rbx
0x180009e2a  call    ?GetPropertyDefinitions@CFciPropertiesShellExt@@CAXPEAUIFsrmClassificationManager2@@JAEAV?$vector@UPropertyInfo@CFciPropertiesShellExt@@V?$allocator@UPropertyInfo@CFciPropertiesShellExt@@@std@@@std@@@Z; CFciPropertiesShellExt::GetPropertyDefinitions(IFsrmClassificationManager2 *,long,std::vector<CFciPropertiesShellExt::PropertyInfo> &)
0x180009e2f  xor     edx, edx; dwMilliseconds
0x180009e31  mov     rcx, [rsi+98h]; hHandle
0x180009e38  call    cs:__imp_WaitForSingleObject
0x180009e3e  cmp     eax, 102h
0x180009e43  jz      short loc_180009E7B
0x180009e45  test    rbx, rbx
0x180009e48  jz      short loc_180009E5A
0x180009e4a  mov     rax, [rbx]
0x180009e4d  mov     rcx, rbx
0x180009e50  mov     rax, [rax+10h]
0x180009e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e59  nop
0x180009e5a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180009e61  mov     [rsp+288h+var_F8], rax
0x180009e69  lea     rcx, [rsp+288h+var_F8]; this
0x180009e71  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180009e76  jmp     loc_18000A25B
0x180009e7b  mov     r14, [rsi+20h]
0x180009e7f  sub     r14, [rsi+18h]
0x180009e83  sar     r14, 3
0x180009e87  mov     r13, 0CCCCCCCCCCCCCCCDh
0x180009e91  imul    r14, r13
0x180009e95  mov     [rsp+288h+var_220], r14
0x180009e9a  mov     eax, 3E8h
0x180009e9f  cmp     r14, rax
0x180009ea2  cmova   r14, rax
0x180009ea6  mov     [rsp+288h+var_1D0], r14
0x180009eae  mov     [rsp+288h+var_220], r14
0x180009eb3  lea     rcx, [rsp+288h+pvarg]; pvarg
0x180009ebb  call    cs:__imp_VariantInit
0x180009ec1  nop
0x180009ec2  mov     [rsp+288h+rgsabound.cElements], r14d
0x180009ec7  mov     [rsp+288h+rgsabound.lLbound], edi
0x180009ecb  mov     ecx, 0Ch; vt
0x180009ed0  lea     r8, [rsp+288h+rgsabound]; rgsabound
0x180009ed5  mov     edx, r12d; cDims
0x180009ed8  call    cs:__imp_SafeArrayCreate
0x180009ede  mov     qword ptr [rsp+288h+pvarg+8], rax
0x180009ee6  mov     ecx, [rsp+288h+var_F0]
0x180009eed  mov     [rsp+288h+var_F0], ecx
0x180009ef4  test    rax, rax
0x180009ef7  jz      loc_18000A3DE
0x180009efd  mov     [rsp+288h+var_F0], edi
0x180009f04  mov     eax, 200Ch
0x180009f09  mov     word ptr [rsp+288h+pvarg], ax
0x180009f11  mov     ecx, edi
0x180009f13  mov     [rsp+288h+plLbound], ecx
0x180009f17  or      eax, 0FFFFFFFFh
0x180009f1a  mov     [rsp+288h+plUbound], eax
0x180009f1e  test    r15, r15
0x180009f21  jz      short loc_180009F79
0x180009f23  lea     r8, [rsp+288h+plLbound]; plLbound
0x180009f28  mov     edx, r12d; nDim
0x180009f2b  mov     rcx, r15; psa
0x180009f2e  call    cs:__imp_SafeArrayGetLBound
0x180009f34  mov     [rsp+288h+var_F0], eax
0x180009f3b  test    eax, eax
0x180009f3d  js      loc_18000A27E
0x180009f43  mov     [rsp+288h+var_F0], eax
0x180009f4a  lea     r8, [rsp+288h+plUbound]; plUbound
0x180009f4f  mov     edx, r12d; nDim
0x180009f52  mov     rcx, r15; psa
0x180009f55  call    cs:__imp_SafeArrayGetUBound
0x180009f5b  mov     [rsp+288h+var_F0], eax
0x180009f62  test    eax, eax
0x180009f64  js      loc_18000A2BF
0x180009f6a  mov     [rsp+288h+var_F0], eax
0x180009f71  mov     ecx, [rsp+288h+plLbound]
0x180009f75  mov     eax, [rsp+288h+plUbound]
0x180009f79  sub     eax, ecx
0x180009f7b  add     eax, r12d
0x180009f7e  mov     ecx, edi
0x180009f80  setz    cl
0x180009f83  mov     dword ptr [rsp+288h+var_220], ecx
0x180009f87  mov     r15d, edi
0x180009f8a  mov     [rsp+288h+var_218], edi
0x180009f8e  mov     rax, rdi
0x180009f91  mov     [rsp+288h+var_210], rax
0x180009f96  mov     r12d, 8
0x180009f9c  mov     r14, [rsi+20h]
0x180009fa0  sub     r14, [rsi+18h]
0x180009fa4  sar     r14, 3
0x180009fa8  imul    r14, r13
0x180009fac  cmp     rax, r14
0x180009faf  jnb     loc_18000A13B
0x180009fb5  sub     r14, rax
0x180009fb8  mov     [rsp+288h+var_1D8], r14
0x180009fc0  mov     eax, 3E8h
0x180009fc5  cmp     r14, rax
0x180009fc8  jbe     short loc_180009FD7
0x180009fca  mov     r14d, eax
0x180009fcd  mov     [rsp+288h+var_1D8], rax
0x180009fd5  jmp     short loc_180009FDA
0x180009fd7  mov     rax, r14
0x180009fda  cmp     rax, [rsp+288h+var_1D0]
0x180009fe2  jz      short loc_18000A012
0x180009fe4  mov     [rsp+288h+rgsabound.cElements], r14d
0x180009fe9  lea     rdx, [rsp+288h+rgsabound]; psaboundNew
0x180009fee  mov     rcx, qword ptr [rsp+288h+pvarg+8]; psa
0x180009ff6  call    cs:__imp_SafeArrayRedim
0x180009ffc  mov     [rsp+288h+var_F0], eax
0x18000a003  test    eax, eax
0x18000a005  js      loc_18000A300
0x18000a00b  mov     [rsp+288h+var_F0], eax
0x18000a012  mov     r13, rdi
0x18000a015  mov     [rsp+288h+var_200], rdi
0x18000a01d  mov     rax, rdi
0x18000a020  cmp     rax, r14
0x18000a023  jnb     loc_18000A0F4
0x18000a029  lea     rcx, [rsp+288h+pv]; pvarg
0x18000a031  call    cs:__imp_VariantInit
0x18000a037  nop
0x18000a038  mov     rax, [rsp+288h+var_210]
0x18000a03d  add     rax, r13
0x18000a040  lea     rcx, [rax+rax*4]
0x18000a044  mov     rax, [rsi+18h]
0x18000a048  lea     rcx, [rax+rcx*8]
0x18000a04c  cmp     [rcx+18h], r12
0x18000a050  jb      short loc_18000A055
0x18000a052  mov     rcx, [rcx]; psz
0x18000a055  test    rcx, rcx
0x18000a058  jnz     short loc_18000A0B6
0x18000a05a  mov     [rsp+288h+bstrString], rdi
0x18000a05f  mov     rax, [rsp+288h+bstrString]
0x18000a064  mov     [rsp+288h+bstrString], rdi
0x18000a069  mov     qword ptr [rsp+288h+pv+8], rax
0x18000a071  mov     rcx, [rsp+288h+bstrString]; bstrString
0x18000a076  call    cs:__imp_SysFreeString
0x18000a07c  mov     word ptr [rsp+288h+pv], r12w
0x18000a085  mov     [rsp+288h+rgIndices], r13d
0x18000a08a  lea     r8, [rsp+288h+pv]; pv
0x18000a092  lea     rdx, [rsp+288h+rgIndices]; rgIndices
0x18000a097  mov     rcx, qword ptr [rsp+288h+pvarg+8]; psa
0x18000a09f  call    cs:__imp_SafeArrayPutElement
0x18000a0a5  mov     [rsp+288h+var_F0], eax
0x18000a0ac  test    eax, eax
0x18000a0ae  js      loc_18000A342
0x18000a0b4  jmp     short loc_18000A0CC
0x18000a0b6  call    cs:__imp_SysAllocString
0x18000a0bc  mov     [rsp+288h+bstrString], rax
0x18000a0c1  test    rax, rax
0x18000a0c4  jz      loc_18000A383
0x18000a0ca  jmp     short loc_18000A05F
0x18000a0cc  mov     [rsp+288h+var_F0], eax
0x18000a0d3  lea     rcx, [rsp+288h+pv]; pvarg
0x18000a0db  call    cs:__imp_VariantClear
0x18000a0e1  inc     r13
0x18000a0e4  mov     [rsp+288h+var_200], r13
0x18000a0ec  mov     rax, r13
0x18000a0ef  jmp     loc_18000A020
0x18000a0f4  mov     rax, [rbx]
0x18000a0f7  mov     ecx, dword ptr [rsp+288h+var_220]
0x18000a0fb  mov     [rsp+288h+var_268], ecx
0x18000a0ff  mov     r9, [rsp+288h+var_1C8]
0x18000a107  mov     r8, [rsp+288h+var_1C0]
0x18000a10f  mov     rdx, qword ptr [rsp+288h+pvarg+8]
0x18000a117  mov     rcx, rbx
0x18000a11a  mov     rax, [rax+110h]
0x18000a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a126  mov     [rsp+288h+var_F0], eax
0x18000a12d  cmp     eax, 80045373h
0x18000a132  jnz     short loc_18000A14E
0x18000a134  mov     [rsp+288h+var_F0], edi
0x18000a13b  mov     [rsp+288h+var_F0], r15d
0x18000a143  test    r15d, r15d
0x18000a146  js      loc_18000A39D
0x18000a14c  jmp     short loc_18000A181
0x18000a14e  test    eax, eax
0x18000a150  jns     short loc_18000A165
0x18000a152  test    r15d, r15d
0x18000a155  cmovns  r15d, eax
0x18000a159  mov     [rsp+288h+var_218], r15d
0x18000a15e  mov     [rsp+288h+var_F0], edi
0x18000a165  mov     rax, [rsp+288h+var_210]
0x18000a16a  add     rax, r14
0x18000a16d  mov     [rsp+288h+var_210], rax
0x18000a172  mov     r13, 0CCCCCCCCCCCCCCCDh
0x18000a17c  jmp     loc_180009F9C
0x18000a181  mov     [rsp+288h+var_F0], r15d
0x18000a189  lea     rcx, [rsp+288h+pvarg]; pvarg
0x18000a191  call    cs:__imp_VariantClear
0x18000a197  nop
0x18000a198  test    rbx, rbx
0x18000a19b  jz      short loc_18000A1AD
0x18000a19d  mov     rax, [rbx]
0x18000a1a0  mov     rcx, rbx
0x18000a1a3  mov     rax, [rax+10h]
0x18000a1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ac  nop
0x18000a1ad  jmp     short loc_18000A1BC
0x18000a1af  mov     rsi, [rsp+288h+var_230]
0x18000a1b4  mov     r12d, 8
0x18000a1ba  xor     edi, edi
0x18000a1bc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a1c6  mov     rdx, [rsi+20h]
0x18000a1ca  sub     rdx, [rsi+18h]
0x18000a1ce  sar     rdx, 3
0x18000a1d2  imul    rdx, rax
0x18000a1d6  mov     rax, [rsi+60h]
0x18000a1da  cmp     rax, [rsi+68h]
0x18000a1de  jz      short loc_18000A222
0x18000a1e0  mov     ecx, [rax+0D4h]
0x18000a1e6  test    ecx, ecx
0x18000a1e8  jz      short loc_18000A21A
0x18000a1ea  cmp     rcx, rdx
0x18000a1ed  jz      short loc_18000A21A
0x18000a1ef  mov     dword ptr [rax+0D0h], 2
0x18000a1f9  lea     rcx, [rax+0A8h]
0x18000a200  cmp     [rcx+18h], r12
0x18000a204  jb      short loc_18000A20F
0x18000a206  mov     r8, [rcx]
0x18000a209  jmp     short loc_18000A212
0x18000a20b  jmp     short loc_18000A1AF
0x18000a20d  jmp     short loc_18000A1AF
0x18000a20f  mov     r8, rcx
0x18000a212  mov     [rcx+10h], rdi
0x18000a216  mov     [r8], di
0x18000a21a  add     rax, 0E0h
0x18000a220  jmp     short loc_18000A1DA
0x18000a222  mov     eax, [rsp+288h+var_F0]
0x18000a229  mov     [rsp+288h+var_F0], eax
0x18000a230  test    eax, eax
0x18000a232  js      loc_18000A416
0x18000a238  mov     [rsp+288h+var_F0], eax
0x18000a23f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000a246  mov     [rsp+288h+var_F8], rax
0x18000a24e  lea     rcx, [rsp+288h+var_F8]; this
0x18000a256  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000a25b  mov     rcx, [rsp+288h+var_48]
0x18000a263  xor     rcx, rsp; StackCookie
0x18000a266  call    __security_check_cookie
0x18000a26b  add     rsp, 250h
0x18000a272  pop     r15
0x18000a274  pop     r14
0x18000a276  pop     r13
0x18000a278  pop     r12
0x18000a27a  pop     rdi
0x18000a27b  pop     rsi
0x18000a27c  pop     rbx
0x18000a27d  retn
0x18000a27e  lea     rcx, [rsp+288h+var_F8]; this
0x18000a286  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000a28b  mov     edx, eax; int
0x18000a28d  lea     rcx, [rsp+288h+var_F8]; this
0x18000a295  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000a29a  lea     rcx, [rsp+288h+var_F8]; this
0x18000a2a2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000a2a7  mov     r8d, eax; char
  ... truncated ...
```
