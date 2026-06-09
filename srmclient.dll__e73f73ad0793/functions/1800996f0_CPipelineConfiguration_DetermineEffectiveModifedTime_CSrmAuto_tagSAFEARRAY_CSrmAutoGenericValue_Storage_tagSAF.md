# CPipelineConfiguration::DetermineEffectiveModifedTime(CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>> const &,std::vector<_FILETIME,std::allocator<_FILETIME>> const &,CSrmFileTime const &)

- ea: `0x1800996f0`
- end: `0x1800999b1`
- name: `?DetermineEffectiveModifedTime@CPipelineConfiguration@@AEAA?AVCSrmFileTime@@AEBV?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@AEBV?$vector@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@AEBV2@@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009a9a8`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012238`
- `0x1800353dc`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18007c45c`
- `0x18008d668`
- `0x1800996f0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800997a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800997a4`
- `OLEAUT32!__imp_VariantClear` at `0x18009980a`
- `OLEAUT32!__imp_VariantClear` at `0x18009980a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800997e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800997e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800997c6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800997c6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180099826`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180099826`
- `KERNEL32!CompareFileTime` at `0x18009987d`
- `KERNEL32!CompareFileTime` at `0x18009987d`

## string_xrefs

- `0x18009972b`: `base\fs\fsrm\service\pipeline\plconfig.cpp`
- `0x180099737`: `CPipelineConfiguration::DetermineEffectiveModifedTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
FILETIME *__fastcall CPipelineConfiguration::DetermineEffectiveModifedTime(
        __int64 a1,
        FILETIME *a2,
        __int64 a3,
        _QWORD *a4,
        FILETIME *a5)
{
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  int i; // eax
  HRESULT v11; // eax
  HRESULT Element; // eax
  unsigned __int64 v13; // rcx
  int v15; // eax
  char v16; // al
  int Hr; // eax
  char v18; // al
  int v19; // eax
  char v20; // al
  LONG rgIndices; // [rsp+30h] [rbp-D0h] BYREF
  LONG plLbound; // [rsp+34h] [rbp-CCh] BYREF
  LONG plUbound; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v26[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  int v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[96]; // [rsp+88h] [rbp-78h] BYREF
  int v31; // [rsp+E8h] [rbp-18h]
  void **v32; // [rsp+F0h] [rbp-10h] BYREF
  HRESULT v33; // [rsp+F8h] [rbp-8h]

  FileTime1 = (FILETIME)v26;
  v26[0] = L"base\\fs\\fsrm\\service\\pipeline\\plconfig.cpp";
  v26[1] = L"CPipelineConfiguration::DetermineEffectiveModifedTime";
  v26[2] = L"PLCONFGC";
  v27 = 615;
  v28 = 22;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v32, (const struct CSrmDebugInfo *)v26, 0);
  plLbound = 0;
  plUbound = 0;
  VariantInit(&pvarg);
  *a2 = *a5;
  LBound = SafeArrayGetLBound(*(SAFEARRAY **)(a3 + 8), 1u, &plLbound);
  v33 = LBound;
  if ( LBound < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, Hr);
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x271u, v18, 0);
  }
  v33 = LBound;
  UBound = SafeArrayGetUBound(*(SAFEARRAY **)(a3 + 8), 1u, &plUbound);
  v33 = UBound;
  if ( UBound < 0 )
  {
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v19);
    v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x272u, v20, 0);
  }
  v33 = UBound;
  for ( i = plLbound; ; i = rgIndices + 1 )
  {
    rgIndices = i;
    if ( i > plUbound )
      break;
    v11 = VariantClear(&pvarg);
    if ( v11 < 0 )
      _com_issue_error(v11);
    Element = SafeArrayGetElement(*(SAFEARRAY **)(a3 + 8), &rgIndices, &pvarg);
    v33 = Element;
    if ( Element < 0 )
    {
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v15);
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x27Au, v16, 0);
    }
    v33 = Element;
    if ( SrmDoesPathExist(pvarg.bstrVal, 0) )
    {
      v13 = rgIndices - plLbound;
      if ( (__int64)(a4[1] - *a4) >> 3 <= v13 )
        std::vector<std::pair<std::wstring,std::wstring>>::_Xran();
      FileTime1 = *(FILETIME *)(*a4 + 8 * v13);
      if ( CompareFileTime(&FileTime1, a2) == 1 )
      {
        *a2 = FileTime1;
        CSrmFunctionTracer::Trace(
          (CSrmFunctionTracer *)&v32,
          0x8Cu,
          0x286u,
          L"Found a namespace that was modified after the rule: %s",
          pvarg.llVal);
      }
    }
  }
  _variant_t::~_variant_t(&pvarg);
  v32 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v32);
  return a2;
}

```

## disassembly

```asm
0x1800996f0  mov     [rsp-8+arg_0], rbx
0x1800996f5  push    rbp
0x1800996f6  push    rsi
0x1800996f7  push    rdi
0x1800996f8  lea     rbp, [rsp-0B0h]
0x180099700  sub     rsp, 1B0h
0x180099707  mov     rax, cs:__security_cookie
0x18009970e  xor     rax, rsp
0x180099711  mov     [rbp+0C0h+var_20], rax
0x180099718  mov     rsi, r9
0x18009971b  mov     rdi, r8
0x18009971e  mov     rbx, rdx
0x180099721  lea     rax, [rsp+1C0h+var_160]
0x180099726  mov     qword ptr [rsp+1C0h+FileTime1.dwLowDateTime], rax
0x18009972b  lea     rax, aBaseFsFsrmServ_23; "base\\fs\\fsrm\\service\\pipeline\\plco"...
0x180099732  mov     [rsp+1C0h+var_160], rax
0x180099737  lea     rax, aCpipelineconfi_7; "CPipelineConfiguration::DetermineEffect"...
0x18009973e  mov     [rsp+1C0h+var_158], rax
0x180099743  lea     rax, aPlconfgc; "PLCONFGC"
0x18009974a  mov     [rsp+1C0h+var_150], rax
0x18009974f  mov     [rsp+1C0h+var_148], 267h
0x180099757  mov     [rsp+1C0h+var_144], 16h
0x18009975f  mov     [rbp+0C0h+var_140], 0FFh
0x180099766  mov     [rbp+0C0h+var_D8], 1000000h
0x18009976d  xor     edx, edx; Val
0x18009976f  lea     r8d, [rdx+60h]; Size
0x180099773  lea     rcx, [rbp+0C0h+var_138]; void *
0x180099777  call    memset_0
0x18009977c  nop
0x18009977d  xor     r8d, r8d
0x180099780  lea     rdx, [rsp+1C0h+var_160]
0x180099785  lea     rcx, [rbp+0C0h+var_D0]
0x180099789  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18009978e  nop
0x18009978f  mov     [rsp+1C0h+plLbound], 0
0x180099797  mov     [rsp+1C0h+plUbound], 0
0x18009979f  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x1800997a4  call    cs:__imp_VariantInit
0x1800997aa  nop
0x1800997ab  mov     rax, [rbp+0C0h+arg_20]
0x1800997b2  mov     rcx, [rax]
0x1800997b5  mov     [rbx], rcx
0x1800997b8  lea     r8, [rsp+1C0h+plLbound]; plLbound
0x1800997bd  mov     edx, 1; nDim
0x1800997c2  mov     rcx, [rdi+8]; psa
0x1800997c6  call    cs:__imp_SafeArrayGetLBound
0x1800997cc  mov     [rbp+0C0h+var_C8], eax
0x1800997cf  test    eax, eax
0x1800997d1  js      loc_180099947
0x1800997d7  mov     [rbp+0C0h+var_C8], eax
0x1800997da  lea     r8, [rsp+1C0h+plUbound]; plUbound
0x1800997df  mov     edx, 1; nDim
0x1800997e4  mov     rcx, [rdi+8]; psa
0x1800997e8  call    cs:__imp_SafeArrayGetUBound
0x1800997ee  mov     [rbp+0C0h+var_C8], eax
0x1800997f1  test    eax, eax
0x1800997f3  js      loc_180099979
0x1800997f9  mov     [rbp+0C0h+var_C8], eax
0x1800997fc  mov     eax, [rsp+1C0h+plLbound]
0x180099800  jmp     loc_1800998BB
0x180099805  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x18009980a  call    cs:__imp_VariantClear
0x180099810  test    eax, eax
0x180099812  js      loc_18009993F
0x180099818  lea     r8, [rsp+1C0h+pvarg]; pv
0x18009981d  lea     rdx, [rsp+1C0h+rgIndices]; rgIndices
0x180099822  mov     rcx, [rdi+8]; psa
0x180099826  call    cs:__imp_SafeArrayGetElement
0x18009982c  mov     [rbp+0C0h+var_C8], eax
0x18009982f  test    eax, eax
0x180099831  js      loc_18009990D
0x180099837  mov     [rbp+0C0h+var_C8], eax
0x18009983a  xor     edx, edx; unsigned int *
0x18009983c  mov     rcx, qword ptr [rsp+1C0h+pvarg+8]; unsigned __int16 *
0x180099841  call    ?SrmDoesPathExist@@YA_NPEBGPEAK@Z; SrmDoesPathExist(ushort const *,ulong *)
0x180099846  test    al, al
0x180099848  jz      short loc_1800998B5
0x18009984a  mov     eax, [rsp+1C0h+rgIndices]
0x18009984e  sub     eax, [rsp+1C0h+plLbound]
0x180099852  movsxd  rcx, eax
0x180099855  mov     rdx, [rsi]
0x180099858  mov     rax, [rsi+8]
0x18009985c  sub     rax, rdx
0x18009985f  sar     rax, 3
0x180099863  cmp     rax, rcx
0x180099866  jbe     loc_1800999AB
0x18009986c  mov     rax, [rdx+rcx*8]
0x180099870  mov     qword ptr [rsp+1C0h+FileTime1.dwLowDateTime], rax
0x180099875  mov     rdx, rbx; lpFileTime2
0x180099878  lea     rcx, [rsp+1C0h+FileTime1]; lpFileTime1
0x18009987d  call    cs:__imp_CompareFileTime
0x180099883  cmp     eax, 1
0x180099886  jnz     short loc_1800998B5
0x180099888  mov     rax, qword ptr [rsp+1C0h+FileTime1.dwLowDateTime]
0x18009988d  mov     [rbx], rax
0x180099890  mov     rax, qword ptr [rsp+1C0h+pvarg+8]
0x180099895  mov     [rsp+1C0h+var_1A0], rax
0x18009989a  lea     r9, aFoundANamespac; "Found a namespace that was modified aft"...
0x1800998a1  mov     edx, 8Ch; unsigned int
0x1800998a6  mov     r8d, 286h; unsigned int
0x1800998ac  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800998b0  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800998b5  mov     eax, [rsp+1C0h+rgIndices]
0x1800998b9  inc     eax
0x1800998bb  cmp     eax, [rsp+1C0h+plUbound]
0x1800998bf  mov     [rsp+1C0h+rgIndices], eax
0x1800998c3  jle     loc_180099805
0x1800998c9  lea     rcx, [rsp+1C0h+pvarg]; this
0x1800998ce  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800998d3  nop
0x1800998d4  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800998db  mov     [rbp+0C0h+var_D0], rax
0x1800998df  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800998e3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800998e8  mov     rax, rbx
0x1800998eb  mov     rcx, [rbp+0C0h+var_20]
0x1800998f2  xor     rcx, rsp; StackCookie
0x1800998f5  call    __security_check_cookie
0x1800998fa  mov     rbx, [rsp+1C0h+arg_0]
0x180099902  add     rsp, 1B0h
0x180099909  pop     rdi
0x18009990a  pop     rsi
0x18009990b  pop     rbp
0x18009990c  retn
0x18009990d  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099911  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180099916  mov     edx, eax; int
0x180099918  lea     rcx, [rbp+0C0h+var_D0]; this
0x18009991c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180099921  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099925  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18009992a  mov     r8d, eax; char
0x18009992d  xor     r9d, r9d; unsigned __int16 *
0x180099930  mov     edx, 27Ah; unsigned int
0x180099935  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099939  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18009993f  mov     ecx, eax; int
0x180099941  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180099947  lea     rcx, [rbp+0C0h+var_D0]; this
0x18009994b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180099950  mov     edx, eax; int
0x180099952  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099956  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18009995b  lea     rcx, [rbp+0C0h+var_D0]; this
0x18009995f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180099964  mov     r8d, eax; char
0x180099967  xor     r9d, r9d; unsigned __int16 *
0x18009996a  mov     edx, 271h; unsigned int
0x18009996f  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099973  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180099979  lea     rcx, [rbp+0C0h+var_D0]; this
0x18009997d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180099982  mov     edx, eax; int
0x180099984  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099988  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18009998d  lea     rcx, [rbp+0C0h+var_D0]; this
0x180099991  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180099996  mov     r8d, eax; char
0x180099999  xor     r9d, r9d; unsigned __int16 *
0x18009999c  mov     edx, 272h; unsigned int
0x1800999a1  lea     rcx, [rbp+0C0h+var_D0]; this
0x1800999a5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800999ab  call    ?_Xran@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEBAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Xran(void)
```
