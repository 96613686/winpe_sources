# CProperty::get_Sources(tagSAFEARRAY * *)

- ea: `0x180058270`
- end: `0x180058630`
- name: `?get_Sources@CProperty@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(CProperty *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012210`
- `0x180012238`
- `0x180016540`
- `0x1800556bc`
- `0x180058270`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800584e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800584e4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180058578`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180058578`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180058510`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180058510`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800584a0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800584a0`

## string_xrefs

- `0x1800582bc`: `base\fs\fsrm\service\pipeline\property.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CProperty::get_Sources(CProperty *this, struct tagSAFEARRAY **a2)
{
  CProperty *v3; // rdi
  int v4; // esi
  _QWORD *v5; // r15
  unsigned __int64 v6; // r14
  SAFEARRAY *Vector; // r12
  SAFEARRAY *v8; // rdi
  LONG v9; // eax
  __int64 v10; // rsi
  BSTR v11; // rax
  char Hr; // al
  LONG rgIndices; // [rsp+40h] [rbp-1E8h] BYREF
  CProperty *v15; // [rsp+48h] [rbp-1E0h]
  void **v16; // [rsp+50h] [rbp-1D8h]
  SAFEARRAY *v17; // [rsp+58h] [rbp-1D0h]
  VARIANTARG pv; // [rsp+60h] [rbp-1C8h] BYREF
  int v19; // [rsp+78h] [rbp-1B0h] BYREF
  struct tagSAFEARRAY **v20; // [rsp+80h] [rbp-1A8h]
  CProperty *v21; // [rsp+88h] [rbp-1A0h] BYREF
  char v22; // [rsp+90h] [rbp-198h]
  _com_error *v23; // [rsp+98h] [rbp-190h] BYREF
  const exception *v24; // [rsp+A0h] [rbp-188h] BYREF
  _QWORD v25[3]; // [rsp+A8h] [rbp-180h] BYREF
  int v26; // [rsp+C0h] [rbp-168h]
  int v27; // [rsp+C4h] [rbp-164h]
  int v28; // [rsp+C8h] [rbp-160h]
  _DWORD v29[28]; // [rsp+D0h] [rbp-158h] BYREF
  void **v30; // [rsp+140h] [rbp-E8h] BYREF
  HRESULT v31; // [rsp+148h] [rbp-E0h]
  unsigned int v32; // [rsp+16Ch] [rbp-BCh]

  v3 = this;
  v15 = this;
  v20 = a2;
  *(_QWORD *)&pv.vt = v25;
  v25[0] = L"base\\fs\\fsrm\\service\\pipeline\\property.cpp";
  v25[1] = L"CProperty::get_Sources";
  v25[2] = L"PROPRTYC";
  v26 = 247;
  v27 = 22;
  v28 = 255;
  v29[24] = 0x1000000;
  memset_0(v29, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v30, (const struct CSrmDebugInfo *)v25, 0);
  v21 = (CProperty *)((char *)v3 + 496);
  CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)v3 + 496));
  v22 = 1;
  try
  {
    if ( !a2 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, -2147024809);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0xFEu, Hr, 0);
    }
    v31 = 0;
    *a2 = 0;
    CProperty::AggregateIfNecessary(v3, (struct CSrmFunctionTracer *)&v30);
  }
  catch ( long v19 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v30,
      v19,
      L"base\\fs\\fsrm\\service\\pipeline\\property.cpp",
      L"PROPRTYC",
      L"CProperty::get_Sources",
      0x106u,
      v32);
    v3 = v15;
  }
  catch ( _com_error *v23 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v30,
      v23,
      L"base\\fs\\fsrm\\service\\pipeline\\property.cpp",
      L"PROPRTYC",
      L"CProperty::get_Sources",
      0x106u,
      v32);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v30,
      L"base\\fs\\fsrm\\service\\pipeline\\property.cpp",
      L"PROPRTYC",
      L"CProperty::get_Sources",
      0x106u,
      v32);
    v3 = v15;
  }
  catch ( const exception *v24 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v30,
      v24,
      L"base\\fs\\fsrm\\service\\pipeline\\property.cpp",
      L"PROPRTYC",
      L"CProperty::get_Sources",
      0x106u,
      v32);
  }
  v4 = v31;
  if ( v31 == -2147200183 )
  {
    *(_QWORD *)&pv.vt = (char *)v3 + 448;
    pv.bVal = 0;
    CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)v3 + 448));
    pv.bVal = 1;
    v5 = (_QWORD *)((char *)v3 + 360);
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v30,
      0x8Cu,
      0x110u,
      L"Property '%s' was marked for deletion",
      *((_QWORD *)v3 + 15));
    v31 = 0;
    CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&pv);
    v4 = v31;
  }
  else
  {
    v5 = (_QWORD *)((char *)v3 + 288);
    if ( v31 == -2147200201 )
    {
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v30,
        0x8Cu,
        0x119u,
        L"Could not aggregate property '%s'",
        *((_QWORD *)v3 + 15));
      v4 = 0;
      v31 = 0;
    }
  }
  if ( v4 >= 0 )
  {
    v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v5[1] - *v5) >> 3);
    v16 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
    Vector = SafeArrayCreateVector(0xCu, 0, v6);
    v8 = Vector;
    v17 = Vector;
    rgIndices = 0;
    if ( (int)v6 > 0 )
    {
      v9 = 0;
      while ( 1 )
      {
        v10 = *v5 + 40LL * v9;
        if ( *(_QWORD *)(v10 + 24) >= 8u )
          v10 = *(_QWORD *)v10;
        v11 = SysAllocString((const OLECHAR *)v10);
        if ( !v11 && v10 )
          _com_issue_error(-2147024882);
        pv.vt = 8;
        pv.llVal = (LONGLONG)v11;
        v31 = SafeArrayPutElement(Vector, &rgIndices, &pv);
        if ( v31 < 0 )
          break;
        _variant_t::~_variant_t(&pv);
        v9 = rgIndices + 1;
        rgIndices = v9;
        if ( v9 >= (int)v6 )
          goto LABEL_19;
      }
      _variant_t::~_variant_t(&pv);
    }
LABEL_19:
    if ( v31 >= 0 )
    {
      v8 = 0;
      v17 = 0;
      *v20 = Vector;
    }
    v16 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
    if ( v8 )
      SafeArrayDestroy(v8);
    v16 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
    v17 = 0;
    v4 = v31;
  }
  CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v21);
  v30 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180058270  mov     r11, rsp
0x180058273  mov     [r11+18h], rbx
0x180058277  mov     [r11+20h], rsi
0x18005827b  push    rdi
0x18005827c  push    r12
0x18005827e  push    r13
0x180058280  push    r14
0x180058282  push    r15
0x180058284  sub     rsp, 200h
0x18005828b  mov     rax, cs:__security_cookie
0x180058292  xor     rax, rsp
0x180058295  mov     [rsp+228h+var_38], rax
0x18005829d  mov     rsi, rdx
0x1800582a0  mov     rdi, rcx
0x1800582a3  mov     [rsp+228h+var_1E0], rcx
0x1800582a8  mov     [rsp+228h+var_1A8], rdx
0x1800582b0  lea     rax, [r11-180h]
0x1800582b7  mov     [rsp+228h+pv], rax
0x1800582bc  lea     rax, aBaseFsFsrmServ_31; "base\\fs\\fsrm\\service\\pipeline\\prop"...
0x1800582c3  mov     [r11-180h], rax
0x1800582ca  lea     rax, aCpropertyGetSo; "CProperty::get_Sources"
0x1800582d1  mov     [r11-178h], rax
0x1800582d8  lea     rax, aProprtyc; "PROPRTYC"
0x1800582df  mov     [r11-170h], rax
0x1800582e6  mov     [rsp+228h+var_168], 0F7h
0x1800582f1  mov     [rsp+228h+var_164], 16h
0x1800582fc  mov     [rsp+228h+var_160], 0FFh
0x180058307  xor     ebx, ebx
0x180058309  mov     [rsp+228h+var_F8], 1000000h
0x180058314  xor     edx, edx; Val
0x180058316  lea     r8d, [rbx+60h]; Size
0x18005831a  lea     rcx, [r11-158h]; void *
0x180058321  call    memset_0
0x180058326  nop
0x180058327  xor     r8d, r8d
0x18005832a  lea     rdx, [rsp+228h+var_180]
0x180058332  lea     rcx, [rsp+228h+var_E8]
0x18005833a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005833f  nop
0x180058340  lea     rcx, [rdi+1F0h]; lpCriticalSection
0x180058347  mov     [rsp+228h+var_1A0], rcx
0x18005834f  mov     [rsp+228h+var_198], bl
0x180058356  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x18005835b  mov     [rsp+228h+var_198], 1
0x180058363  mov     eax, [rsp+228h+var_E0]
0x18005836a  mov     [rsp+228h+var_E0], eax
0x180058371  test    rsi, rsi
0x180058374  jz      loc_1800585ED
0x18005837a  mov     [rsp+228h+var_E0], ebx
0x180058381  mov     [rsi], rbx
0x180058384  lea     rdx, [rsp+228h+var_E8]; struct CSrmFunctionTracer *
0x18005838c  mov     rcx, rdi; this
0x18005838f  call    ?AggregateIfNecessary@CProperty@@AEAAXAEAVCSrmFunctionTracer@@@Z; CProperty::AggregateIfNecessary(CSrmFunctionTracer &)
0x180058394  nop
0x180058395  jmp     short loc_18005839E
0x180058397  mov     rdi, [rsp+228h+var_1E0]
0x18005839c  xor     ebx, ebx
0x18005839e  mov     esi, [rsp+228h+var_E0]
0x1800583a5  cmp     esi, 80045349h
0x1800583ab  jnz     short loc_180058414
0x1800583ad  lea     rcx, [rdi+1C0h]; lpCriticalSection
0x1800583b4  mov     [rsp+228h+pv], rcx
0x1800583b9  mov     byte ptr [rsp+228h+var_1C0], bl
0x1800583bd  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x1800583c2  mov     byte ptr [rsp+228h+var_1C0], 1
0x1800583c7  lea     r15, [rdi+168h]
0x1800583ce  mov     rax, [rdi+78h]
0x1800583d2  mov     [rsp+228h+var_208], rax
0x1800583d7  lea     r9, aPropertySWasMa; "Property '%s' was marked for deletion"
0x1800583de  mov     edx, 8Ch; unsigned int
0x1800583e3  mov     r8d, 110h; unsigned int
0x1800583e9  lea     rcx, [rsp+228h+var_E8]; this
0x1800583f1  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800583f6  mov     [rsp+228h+var_E0], ebx
0x1800583fd  lea     rcx, [rsp+228h+pv]; this
0x180058402  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x180058407  mov     esi, [rsp+228h+var_E0]
0x18005840e  jmp     short loc_180058454
0x180058410  jmp     short loc_180058397
0x180058412  jmp     short loc_180058397
0x180058414  lea     r15, [rdi+120h]
0x18005841b  cmp     esi, 80045337h
0x180058421  jnz     short loc_180058454
0x180058423  mov     rax, [rdi+78h]
0x180058427  mov     [rsp+228h+var_208], rax
0x18005842c  lea     r9, aCouldNotAggreg; "Could not aggregate property '%s'"
0x180058433  mov     edx, 8Ch; unsigned int
0x180058438  mov     r8d, 119h; unsigned int
0x18005843e  lea     rcx, [rsp+228h+var_E8]; this
0x180058446  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005844b  mov     esi, ebx
0x18005844d  mov     [rsp+228h+var_E0], ebx
0x180058454  test    esi, esi
0x180058456  js      loc_180058594
0x18005845c  mov     r14, [r15+8]
0x180058460  sub     r14, [r15]
0x180058463  sar     r14, 3
0x180058467  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180058471  imul    r14, rax
0x180058475  mov     [rsp+228h+rgIndices], ebx
0x180058479  lea     rsi, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x180058480  mov     [rsp+228h+var_1D8], rsi
0x180058485  mov     [rsp+228h+var_1D0], rbx
0x18005848a  lea     r13, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x180058491  mov     [rsp+228h+var_1D8], r13
0x180058496  mov     ecx, 0Ch; vt
0x18005849b  mov     r8d, r14d; cElements
0x18005849e  xor     edx, edx; lLbound
0x1800584a0  call    cs:__imp_SafeArrayCreateVector
0x1800584a6  mov     r12, rax
0x1800584a9  mov     [rsp+228h+var_1D0], rbx
0x1800584ae  mov     rdi, rax
0x1800584b1  mov     [rsp+228h+var_1D0], rax
0x1800584b6  mov     [rsp+228h+rgIndices], ebx
0x1800584ba  test    r14d, r14d
0x1800584bd  jle     loc_18005854F
0x1800584c3  mov     eax, ebx
0x1800584c5  mov     r13d, 8
0x1800584cb  cdqe
0x1800584cd  lea     rcx, [rax+rax*4]
0x1800584d1  mov     rax, [r15]
0x1800584d4  lea     rsi, [rax+rcx*8]
0x1800584d8  cmp     [rsi+18h], r13
0x1800584dc  jb      short loc_1800584E1
0x1800584de  mov     rsi, [rsi]
0x1800584e1  mov     rcx, rsi; psz
0x1800584e4  call    cs:__imp_SysAllocString
0x1800584ea  test    rax, rax
0x1800584ed  jnz     short loc_1800584F8
0x1800584ef  test    rsi, rsi
0x1800584f2  jnz     loc_180058625
0x1800584f8  mov     word ptr [rsp+228h+pv], r13w
0x1800584fe  mov     [rsp+228h+var_1C0], rax
0x180058503  lea     r8, [rsp+228h+pv]; pv
0x180058508  lea     rdx, [rsp+228h+rgIndices]; rgIndices
0x18005850d  mov     rcx, r12; psa
0x180058510  call    cs:__imp_SafeArrayPutElement
0x180058516  mov     [rsp+228h+var_E0], eax
0x18005851d  lea     rcx, [rsp+228h+pv]; this
0x180058522  test    eax, eax
0x180058524  js      short loc_18005853C
0x180058526  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005852b  mov     eax, [rsp+228h+rgIndices]
0x18005852f  inc     eax
0x180058531  mov     [rsp+228h+rgIndices], eax
0x180058535  cmp     eax, r14d
0x180058538  jl      short loc_1800584CB
0x18005853a  jmp     short loc_180058541
0x18005853c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180058541  lea     r13, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x180058548  lea     rsi, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18005854f  cmp     [rsp+228h+var_E0], ebx
0x180058556  jl      short loc_18005856B
0x180058558  mov     rdi, rbx
0x18005855b  mov     [rsp+228h+var_1D0], rbx
0x180058560  mov     rax, [rsp+228h+var_1A8]
0x180058568  mov     [rax], r12
0x18005856b  mov     [rsp+228h+var_1D8], r13
0x180058570  test    rdi, rdi
0x180058573  jz      short loc_18005857E
0x180058575  mov     rcx, rdi; psa
0x180058578  call    cs:__imp_SafeArrayDestroy
0x18005857e  mov     [rsp+228h+var_1D0], rbx
0x180058583  mov     [rsp+228h+var_1D8], rsi
0x180058588  mov     [rsp+228h+var_1D0], rbx
0x18005858d  mov     esi, [rsp+228h+var_E0]
0x180058594  lea     rcx, [rsp+228h+var_1A0]; this
0x18005859c  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x1800585a1  nop
0x1800585a2  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800585a9  mov     [rsp+228h+var_E8], rax
0x1800585b1  lea     rcx, [rsp+228h+var_E8]; this
0x1800585b9  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800585be  mov     eax, esi
0x1800585c0  mov     rcx, [rsp+228h+var_38]
0x1800585c8  xor     rcx, rsp; StackCookie
0x1800585cb  call    __security_check_cookie
0x1800585d0  lea     r11, [rsp+228h+var_28]
0x1800585d8  mov     rbx, [r11+40h]
0x1800585dc  mov     rsi, [r11+48h]
0x1800585e0  mov     rsp, r11
0x1800585e3  pop     r15
0x1800585e5  pop     r14
0x1800585e7  pop     r13
0x1800585e9  pop     r12
0x1800585eb  pop     rdi
0x1800585ec  retn
0x1800585ed  mov     edx, 80070057h; int
0x1800585f2  lea     rcx, [rsp+228h+var_E8]; this
0x1800585fa  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800585ff  lea     rcx, [rsp+228h+var_E8]; this
0x180058607  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005860c  mov     r8d, eax; char
0x18005860f  xor     r9d, r9d; unsigned __int16 *
0x180058612  mov     edx, 0FEh; unsigned int
0x180058617  lea     rcx, [rsp+228h+var_E8]; this
0x18005861f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180058625  mov     ecx, 8007000Eh; int
0x18005862a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
