# ParseStringToSafearray(ushort *,tagSAFEARRAY * *,long *)

- ea: `0x18001bd9c`
- end: `0x18001c007`
- name: `?ParseStringToSafearray@@YAJPEAGPEAPEAUtagSAFEARRAY@@PEAJ@Z`
- size: `619`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct tagSAFEARRAY **, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c1f0`
- `0x18001cb84`

## callees

- `0x180006a1c`
- `0x18001bd9c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074a04`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!wcschr` at `0x18001bf1d`
- `msvcrt!wcschr` at `0x18001bf1d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bf32`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bf32`
- `OLEAUT32!__imp_VariantClear` at `0x18001bf82`
- `OLEAUT32!__imp_VariantClear` at `0x18001bf82`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001be6a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001befc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001be6a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001befc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001bf62`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001bf62`

## string_xrefs

- `0x18001bdd5`: `base\fs\fsrm\service\globalstore\inboxmodules.cpp`
- `0x18001bfcc`: `base\fs\fsrm\service\globalstore\inboxmodules.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ParseStringToSafearray(OLECHAR *psz, struct tagSAFEARRAY **a2, int *a3)
{
  unsigned __int64 v6; // rcx
  LONG v7; // ebx
  SAFEARRAY *v8; // rsi
  unsigned int v9; // ebx
  unsigned __int64 i; // rdx
  ULONG v12; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  BSTR v15; // rax
  OLECHAR *v16; // rax
  HRESULT v17; // eax
  unsigned int Hr; // eax
  __int64 v19; // rdx
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pv; // [rsp+50h] [rbp-B0h] BYREF
  void **v23; // [rsp+70h] [rbp-90h]
  SAFEARRAY *v24; // [rsp+78h] [rbp-88h]
  _QWORD v25[4]; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+A0h] [rbp-60h]
  _BYTE v27[96]; // [rsp+A8h] [rbp-58h] BYREF
  int v28; // [rsp+108h] [rbp+8h]
  void **v29; // [rsp+110h] [rbp+10h] BYREF
  HRESULT v30; // [rsp+118h] [rbp+18h]

  v25[0] = L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp";
  v25[1] = L"ParseStringToSafearray";
  v25[2] = L"CINBOXMD";
  v25[3] = 325;
  v26 = 255;
  v28 = 0x1000000;
  memset_0(v27, 0, sizeof(v27));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v29, (const struct CSrmDebugInfo *)v25, 0);
  *a2 = 0;
  v23 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  v6 = -1;
  do
    ++v6;
  while ( psz[v6] );
  if ( v6 )
  {
    v7 = 1;
    for ( i = 0; i < v6; ++i )
    {
      v12 = v7 + 1;
      if ( psz[i] != 124 )
        v12 = v7;
      v7 = v12;
    }
    rgsabound.cElements = v12;
    rgsabound.lLbound = 0;
    v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v24 = v8;
    for ( rgIndices = 0; rgIndices < v7; ++rgIndices )
    {
      v13 = wcschr(psz, 0x7Cu);
      v14 = v13;
      if ( v13 )
        *v13 = 0;
      v15 = SysAllocString(psz);
      if ( !v15 && psz )
        _com_issue_error(-2147024882);
      pv.vt = 8;
      pv.llVal = (LONGLONG)v15;
      v30 = SafeArrayPutElement(v8, &rgIndices, &pv);
      if ( v30 < 0 )
      {
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)v25,
          (__int64)L"base\\fs\\fsrm\\service\\globalstore\\inboxmodules.cpp",
          (__int64)L"CINBOXMD",
          (__int64)L"ParseStringToSafearray",
          371,
          0);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v29);
        CSrmFunctionTracer::TranslateGenericError(&v29, v19, Hr, L"SafeArrayPutElement");
      }
      v16 = v14 + 1;
      if ( !v14 )
        v16 = psz;
      psz = v16;
      v17 = VariantClear(&pv);
      if ( v17 < 0 )
        _com_issue_error(v17);
    }
  }
  else
  {
    v7 = 0;
    rgsabound = 0;
    v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  }
  *a2 = v8;
  if ( a3 )
    *a3 = v7;
  v9 = v30;
  v29 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
  return v9;
}

```

## disassembly

```asm
0x18001bd9c  mov     [rsp-8+arg_18], rbx
0x18001bda1  push    rbp
0x18001bda2  push    rsi
0x18001bda3  push    rdi
0x18001bda4  push    r12
0x18001bda6  push    r13
0x18001bda8  push    r14
0x18001bdaa  push    r15
0x18001bdac  lea     rbp, [rsp-0D0h]
0x18001bdb4  sub     rsp, 1D0h
0x18001bdbb  mov     rax, cs:__security_cookie
0x18001bdc2  xor     rax, rsp
0x18001bdc5  mov     [rbp+100h+var_40], rax
0x18001bdcc  mov     r15, r8
0x18001bdcf  mov     r12, rdx
0x18001bdd2  mov     rdi, rcx
0x18001bdd5  lea     rax, aBaseFsFsrmServ_2; "base\\fs\\fsrm\\service\\globalstore\\i"...
0x18001bddc  mov     [rbp+100h+var_180], rax
0x18001bde0  lea     rax, aParsestringtos; "ParseStringToSafearray"
0x18001bde7  mov     [rbp+100h+var_178], rax
0x18001bdeb  lea     rax, aCinboxmd; "CINBOXMD"
0x18001bdf2  mov     [rbp+100h+var_170], rax
0x18001bdf6  mov     [rbp+100h+var_168], 145h
0x18001bdfe  xor     r13d, r13d
0x18001be01  mov     [rbp+100h+var_160], 0FFh
0x18001be08  mov     [rbp+100h+var_F8], 1000000h
0x18001be0f  lea     esi, [r13+1]
0x18001be13  xor     edx, edx; Val
0x18001be15  lea     r8d, [r13+60h]; Size
0x18001be19  lea     rcx, [rbp+100h+var_158]; void *
0x18001be1d  call    memset_0
0x18001be22  xor     r8d, r8d
0x18001be25  lea     rdx, [rbp+100h+var_180]
0x18001be29  lea     rcx, [rbp+100h+var_F0]
0x18001be2d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001be32  nop
0x18001be33  mov     [r12], r13
0x18001be37  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18001be3e  mov     [rsp+200h+var_190], rax
0x18001be43  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001be47  inc     rcx
0x18001be4a  cmp     [rdi+rcx*2], r13w
0x18001be4f  jnz     short loc_18001BE47
0x18001be51  test    rcx, rcx
0x18001be54  jnz     short loc_18001BEC2
0x18001be56  mov     ebx, r13d
0x18001be59  mov     qword ptr [rsp+200h+rgsabound.cElements], r13
0x18001be5e  mov     ecx, 0Ch; vt
0x18001be63  lea     r8, [rsp+200h+rgsabound]; rgsabound
0x18001be68  mov     edx, esi; cDims
0x18001be6a  call    cs:__imp_SafeArrayCreate
0x18001be70  mov     rsi, rax
0x18001be73  mov     [r12], rsi
0x18001be77  test    r15, r15
0x18001be7a  jz      short loc_18001BE7F
0x18001be7c  mov     [r15], ebx
0x18001be7f  mov     ebx, [rbp+100h+var_E8]
0x18001be82  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001be89  mov     [rbp+100h+var_F0], rax
0x18001be8d  lea     rcx, [rbp+100h+var_F0]; this
0x18001be91  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001be96  mov     eax, ebx
0x18001be98  mov     rcx, [rbp+100h+var_40]
0x18001be9f  xor     rcx, rsp; StackCookie
0x18001bea2  call    __security_check_cookie
0x18001bea7  mov     rbx, [rsp+200h+arg_18]
0x18001beaf  add     rsp, 1D0h
0x18001beb6  pop     r15
0x18001beb8  pop     r14
0x18001beba  pop     r13
0x18001bebc  pop     r12
0x18001bebe  pop     rdi
0x18001bebf  pop     rsi
0x18001bec0  pop     rbp
0x18001bec1  retn
0x18001bec2  mov     ebx, esi
0x18001bec4  mov     rdx, r13
0x18001bec7  mov     r14d, 7Ch ; '|'
0x18001becd  test    rcx, rcx
0x18001bed0  jz      short loc_18001BEE7
0x18001bed2  lea     eax, [rbx+1]
0x18001bed5  cmp     [rdi+rdx*2], r14w
0x18001beda  cmovnz  eax, ebx
0x18001bedd  mov     ebx, eax
0x18001bedf  add     rdx, rsi
0x18001bee2  cmp     rdx, rcx
0x18001bee5  jb      short loc_18001BED2
0x18001bee7  mov     [rsp+200h+rgsabound.cElements], ebx
0x18001beeb  mov     [rsp+200h+rgsabound.lLbound], r13d
0x18001bef0  mov     ecx, 0Ch; vt
0x18001bef5  lea     r8, [rsp+200h+rgsabound]; rgsabound
0x18001befa  mov     edx, esi; cDims
0x18001befc  call    cs:__imp_SafeArrayCreate
0x18001bf02  mov     rsi, rax
0x18001bf05  mov     [rsp+200h+var_188], rax
0x18001bf0a  mov     [rsp+200h+rgIndices], r13d
0x18001bf0f  test    ebx, ebx
0x18001bf11  jle     loc_18001BE73
0x18001bf17  mov     edx, r14d; Ch
0x18001bf1a  mov     rcx, rdi; Str
0x18001bf1d  call    cs:__imp_wcschr
0x18001bf23  mov     r14, rax
0x18001bf26  test    rax, rax
0x18001bf29  jz      short loc_18001BF2F
0x18001bf2b  mov     [rax], r13w
0x18001bf2f  mov     rcx, rdi; psz
0x18001bf32  call    cs:__imp_SysAllocString
0x18001bf38  test    rax, rax
0x18001bf3b  jnz     short loc_18001BF46
0x18001bf3d  test    rdi, rdi
0x18001bf40  jnz     loc_18001BFFC
0x18001bf46  mov     ecx, 8
0x18001bf4b  mov     [rsp+200h+pv], cx
0x18001bf50  mov     [rsp+200h+var_1A8], rax
0x18001bf55  lea     r8, [rsp+200h+pv]; pv
0x18001bf5a  lea     rdx, [rsp+200h+rgIndices]; rgIndices
0x18001bf5f  mov     rcx, rsi; psa
0x18001bf62  call    cs:__imp_SafeArrayPutElement
0x18001bf68  mov     [rbp+100h+var_E8], eax
0x18001bf6b  test    eax, eax
0x18001bf6d  js      short loc_18001BFB1
0x18001bf6f  lea     rax, [r14+2]
0x18001bf73  test    r14, r14
0x18001bf76  cmovz   rax, rdi
0x18001bf7a  mov     rdi, rax
0x18001bf7d  lea     rcx, [rsp+200h+pv]; pvarg
0x18001bf82  call    cs:__imp_VariantClear
0x18001bf88  test    eax, eax
0x18001bf8a  js      short loc_18001BFA9
0x18001bf8c  mov     eax, [rsp+200h+rgIndices]
0x18001bf90  inc     eax
0x18001bf92  mov     [rsp+200h+rgIndices], eax
0x18001bf96  cmp     eax, ebx
0x18001bf98  jge     loc_18001BE73
0x18001bf9e  mov     r14d, 7Ch ; '|'
0x18001bfa4  jmp     loc_18001BF17
0x18001bfa9  mov     ecx, eax; int
0x18001bfab  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001bfb1  mov     [rsp+200h+var_1D8], r13d
0x18001bfb6  mov     [rsp+200h+var_1E0], 173h
0x18001bfbe  lea     r9, aParsestringtos; "ParseStringToSafearray"
0x18001bfc5  lea     r8, aCinboxmd; "CINBOXMD"
0x18001bfcc  lea     rdx, aBaseFsFsrmServ_2; "base\\fs\\fsrm\\service\\globalstore\\i"...
0x18001bfd3  lea     rcx, [rbp+100h+var_180]
0x18001bfd7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001bfdc  mov     rdx, rax
0x18001bfdf  lea     rcx, [rbp+100h+var_F0]; this
0x18001bfe3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001bfe8  mov     r8d, eax
0x18001bfeb  lea     r9, aSafearrayputel; "SafeArrayPutElement"
0x18001bff2  lea     rcx, [rbp+100h+var_F0]
0x18001bff6  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001bffc  mov     ecx, 8007000Eh; int
0x18001c001  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
