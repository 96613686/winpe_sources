# CPropertyBag::get_FilePropertyNames(tagSAFEARRAY * *)

- ea: `0x1800915b0`
- end: `0x1800918c4`
- name: `?get_FilePropertyNames@CPropertyBag@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(CPropertyBag *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012210`
- `0x180012238`
- `0x180016540`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18008d668`
- `0x1800915b0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18009178c`
- `OLEAUT32!__imp_SysAllocString` at `0x18009178c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800917c5`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800917c5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800916cb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800916cb`

## string_xrefs

- `0x1800915ef`: `base\fs\fsrm\service\pipeline\propertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPropertyBag::get_FilePropertyNames(CPropertyBag *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *Vector; // r14
  unsigned int v5; // ebx
  const OLECHAR *v7; // rdi
  BSTR v8; // rax
  HRESULT v9; // eax
  __int64 *v10; // rax
  __int64 *v11; // rbx
  __int64 *v12; // rax
  __int64 *v13; // rax
  int Hr; // eax
  char v15; // al
  LONG rgIndices; // [rsp+40h] [rbp-1E8h] BYREF
  void **v17; // [rsp+48h] [rbp-1E0h]
  SAFEARRAY *v18; // [rsp+50h] [rbp-1D8h]
  __int64 *v19; // [rsp+58h] [rbp-1D0h]
  __int64 *v20; // [rsp+60h] [rbp-1C8h]
  int v21; // [rsp+68h] [rbp-1C0h] BYREF
  __int64 *i; // [rsp+70h] [rbp-1B8h]
  CPropertyBag *v23; // [rsp+78h] [rbp-1B0h] BYREF
  char v24; // [rsp+80h] [rbp-1A8h]
  VARIANTARG pv; // [rsp+88h] [rbp-1A0h] BYREF
  _com_error *v26; // [rsp+A0h] [rbp-188h] BYREF
  const exception *v27; // [rsp+A8h] [rbp-180h] BYREF
  _QWORD v28[3]; // [rsp+B0h] [rbp-178h] BYREF
  int v29; // [rsp+C8h] [rbp-160h]
  int v30; // [rsp+CCh] [rbp-15Ch]
  int v31; // [rsp+D0h] [rbp-158h]
  _DWORD v32[26]; // [rsp+D8h] [rbp-150h] BYREF
  void **v33; // [rsp+140h] [rbp-E8h] BYREF
  HRESULT v34; // [rsp+148h] [rbp-E0h]
  unsigned int v35; // [rsp+16Ch] [rbp-BCh]

  v20 = v28;
  v28[0] = L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp";
  v28[1] = L"CPropertyBag::get_FilePropertyNames";
  v28[2] = L"PROPBAGC";
  v29 = 417;
  v30 = 22;
  v31 = 255;
  v32[24] = 0x1000000;
  memset_0(v32, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v33, (const struct CSrmDebugInfo *)v28, 0);
  try
  {
    v23 = (CPropertyBag *)((char *)this + 1232);
    CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)this + 1232));
    v24 = 1;
    v20 = (__int64 *)*((_QWORD *)this + 63);
    rgIndices = 0;
    v17 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
    Vector = SafeArrayCreateVector(0xCu, 0, (ULONG)v20);
    v18 = Vector;
    v11 = (__int64 *)**((_QWORD **)this + 62);
    v19 = v11;
    while ( 1 )
    {
      v20 = (__int64 *)*((_QWORD *)this + 62);
      if ( v11 == v20 )
        break;
      v7 = (const OLECHAR *)(v11 + 3);
      if ( (unsigned __int64)v11[6] >= 8 )
        v7 = *(const OLECHAR **)v7;
      v8 = SysAllocString(v7);
      if ( !v8 && v7 )
        _com_issue_error(-2147024882);
      pv.vt = 8;
      pv.llVal = (LONGLONG)v8;
      v9 = SafeArrayPutElement(Vector, &rgIndices, &pv);
      v34 = v9;
      if ( v9 < 0 )
      {
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, Hr);
        v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x1B5u, v15, 0);
      }
      v34 = v9;
      ++rgIndices;
      _variant_t::~_variant_t(&pv);
      v20 = v11;
      if ( !*((_BYTE *)v11 + 73) )
      {
        v10 = (__int64 *)v11[2];
        if ( *((_BYTE *)v10 + 73) )
        {
          while ( 1 )
          {
            v13 = (__int64 *)v11[1];
            if ( *((_BYTE *)v13 + 73) || v11 != (__int64 *)v13[2] )
              break;
            v11 = (__int64 *)v11[1];
            v19 = v13;
          }
          v11 = (__int64 *)v11[1];
          v19 = v13;
        }
        else
        {
          v11 = (__int64 *)v11[2];
          for ( i = v10; ; i = v12 )
          {
            v12 = (__int64 *)*v11;
            if ( *(_BYTE *)(*v11 + 73) )
              break;
            v11 = (__int64 *)*v11;
          }
          v19 = v11;
        }
      }
    }
    *a2 = Vector;
    v17 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
    v18 = 0;
    CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v23);
  }
  catch ( long v21 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v33,
      v21,
      L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp",
      L"PROPBAGC",
      L"CPropertyBag::get_FilePropertyNames",
      0x1BCu,
      v35);
  }
  catch ( _com_error *v26 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v33,
      v26,
      L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp",
      L"PROPBAGC",
      L"CPropertyBag::get_FilePropertyNames",
      0x1BCu,
      v35);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v33,
      L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp",
      L"PROPBAGC",
      L"CPropertyBag::get_FilePropertyNames",
      0x1BCu,
      v35);
  }
  catch ( const exception *v27 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v33,
      v27,
      L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp",
      L"PROPBAGC",
      L"CPropertyBag::get_FilePropertyNames",
      0x1BCu,
      v35);
  }
  v5 = v34;
  v33 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v33);
  return v5;
}

```

## disassembly

```asm
0x1800915b0  mov     r11, rsp
0x1800915b3  mov     [r11+18h], rbx
0x1800915b7  mov     [r11+20h], rsi
0x1800915bb  push    rdi
0x1800915bc  push    r12
0x1800915be  push    r13
0x1800915c0  push    r14
0x1800915c2  push    r15
0x1800915c4  sub     rsp, 200h
0x1800915cb  mov     rax, cs:__security_cookie
0x1800915d2  xor     rax, rsp
0x1800915d5  mov     [rsp+228h+var_38], rax
0x1800915dd  mov     r15, rdx
0x1800915e0  mov     rsi, rcx
0x1800915e3  lea     rax, [r11-178h]
0x1800915ea  mov     [rsp+228h+var_1C8], rax
0x1800915ef  lea     rax, aBaseFsFsrmServ_26; "base\\fs\\fsrm\\service\\pipeline\\prop"...
0x1800915f6  mov     [r11-178h], rax
0x1800915fd  lea     rax, aCpropertybagGe_2; "CPropertyBag::get_FilePropertyNames"
0x180091604  mov     [r11-170h], rax
0x18009160b  lea     rax, aPropbagc; "PROPBAGC"
0x180091612  mov     [r11-168h], rax
0x180091619  mov     [rsp+228h+var_160], 1A1h
0x180091624  mov     [rsp+228h+var_15C], 16h
0x18009162f  mov     [rsp+228h+var_158], 0FFh
0x18009163a  xor     r12d, r12d
0x18009163d  mov     [rsp+228h+var_F0], 1000000h
0x180091648  xor     edx, edx; Val
0x18009164a  lea     r8d, [r12+60h]; Size
0x18009164f  lea     rcx, [r11-150h]; void *
0x180091656  call    memset_0
0x18009165b  nop
0x18009165c  xor     r8d, r8d
0x18009165f  lea     rdx, [rsp+228h+var_178]
0x180091667  lea     rcx, [rsp+228h+var_E8]
0x18009166f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180091674  nop
0x180091675  lea     rcx, [rsi+4D0h]; lpCriticalSection
0x18009167c  mov     [rsp+228h+var_1B0], rcx
0x180091681  mov     [rsp+228h+var_1A8], r12b
0x180091689  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x18009168e  mov     [rsp+228h+var_1A8], 1
0x180091696  mov     r8, [rsi+1F8h]; cElements
0x18009169d  mov     [rsp+228h+var_1C8], r8
0x1800916a2  mov     [rsp+228h+rgIndices], r12d
0x1800916a7  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x1800916ae  mov     [rsp+228h+var_1E0], r13
0x1800916b3  mov     [rsp+228h+var_1D8], r12
0x1800916b8  lea     rdi, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x1800916bf  mov     [rsp+228h+var_1E0], rdi
0x1800916c4  lea     ecx, [r12+0Ch]; vt
0x1800916c9  xor     edx, edx; lLbound
0x1800916cb  call    cs:__imp_SafeArrayCreateVector
0x1800916d1  mov     r14, rax
0x1800916d4  mov     [rsp+228h+var_1D8], r12
0x1800916d9  mov     [rsp+228h+var_1D8], rax
0x1800916de  mov     rbx, [rsi+1F0h]
0x1800916e5  mov     rbx, [rbx]
0x1800916e8  mov     [rsp+228h+var_1D0], rbx
0x1800916ed  mov     eax, 8
0x1800916f2  mov     rcx, [rsi+1F0h]
0x1800916f9  mov     [rsp+228h+var_1C8], rcx
0x1800916fe  cmp     rbx, rcx
0x180091701  jnz     short loc_18009177C
0x180091703  mov     [rsp+228h+var_1D8], r12
0x180091708  mov     [r15], r14
0x18009170b  mov     [rsp+228h+var_1E0], rdi
0x180091710  mov     [rsp+228h+var_1D8], r12
0x180091715  mov     [rsp+228h+var_1E0], r13
0x18009171a  mov     [rsp+228h+var_1D8], r12
0x18009171f  lea     rcx, [rsp+228h+var_1B0]; this
0x180091724  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x180091729  nop
0x18009172a  mov     ebx, [rsp+228h+var_E0]
0x180091731  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180091738  mov     [rsp+228h+var_E8], rax
0x180091740  lea     rcx, [rsp+228h+var_E8]; this
0x180091748  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18009174d  mov     eax, ebx
0x18009174f  mov     rcx, [rsp+228h+var_38]
0x180091757  xor     rcx, rsp; StackCookie
0x18009175a  call    __security_check_cookie
0x18009175f  lea     r11, [rsp+228h+var_28]
0x180091767  mov     rbx, [r11+40h]
0x18009176b  mov     rsi, [r11+48h]
0x18009176f  mov     rsp, r11
0x180091772  pop     r15
0x180091774  pop     r14
0x180091776  pop     r13
0x180091778  pop     r12
0x18009177a  pop     rdi
0x18009177b  retn
0x18009177c  lea     rdi, [rbx+18h]
0x180091780  cmp     [rdi+18h], rax
0x180091784  jb      short loc_180091789
0x180091786  mov     rdi, [rdi]
0x180091789  mov     rcx, rdi; psz
0x18009178c  call    cs:__imp_SysAllocString
0x180091792  test    rax, rax
0x180091795  jnz     short loc_1800917A0
0x180091797  test    rdi, rdi
0x18009179a  jnz     loc_180091876
0x1800917a0  mov     ecx, 8
0x1800917a5  mov     [rsp+228h+pv], cx
0x1800917ad  mov     [rsp+228h+var_198], rax
0x1800917b5  lea     r8, [rsp+228h+pv]; pv
0x1800917bd  lea     rdx, [rsp+228h+rgIndices]; rgIndices
0x1800917c2  mov     rcx, r14; psa
0x1800917c5  call    cs:__imp_SafeArrayPutElement
0x1800917cb  mov     [rsp+228h+var_E0], eax
0x1800917d2  test    eax, eax
0x1800917d4  js      loc_180091881
0x1800917da  mov     [rsp+228h+var_E0], eax
0x1800917e1  inc     [rsp+228h+rgIndices]
0x1800917e5  lea     rcx, [rsp+228h+pv]; this
0x1800917ed  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800917f2  mov     [rsp+228h+var_1C8], rbx
0x1800917f7  cmp     [rbx+49h], r12b
0x1800917fb  lea     rdi, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x180091802  mov     eax, 8
0x180091807  jnz     loc_1800916F2
0x18009180d  mov     rax, [rbx+10h]
0x180091811  cmp     [rax+49h], r12b
0x180091815  jnz     short loc_180091843
0x180091817  mov     rbx, rax
0x18009181a  mov     [rsp+228h+var_1B8], rax
0x18009181f  mov     rax, [rbx]
0x180091822  cmp     [rax+49h], r12b
0x180091826  jnz     short loc_180091832
0x180091828  mov     rbx, rax
0x18009182b  mov     [rsp+228h+var_1B8], rax
0x180091830  jmp     short loc_18009181F
0x180091832  mov     [rsp+228h+var_1D0], rbx
0x180091837  lea     rdi, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18009183e  jmp     loc_1800916ED
0x180091843  mov     rax, [rbx+8]
0x180091847  cmp     [rax+49h], r12b
0x18009184b  jnz     short loc_18009185D
0x18009184d  cmp     rbx, [rax+10h]
0x180091851  jnz     short loc_18009185D
0x180091853  mov     rbx, rax
0x180091856  mov     [rsp+228h+var_1D0], rax
0x18009185b  jmp     short loc_180091843
0x18009185d  mov     rbx, rax
0x180091860  mov     [rsp+228h+var_1D0], rax
0x180091865  jmp     short loc_180091837
0x180091867  jmp     loc_18009172A
0x18009186c  jmp     loc_18009172A
0x180091871  jmp     loc_18009172A
0x180091876  mov     ecx, 8007000Eh; int
0x18009187b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180091881  lea     rcx, [rsp+228h+var_E8]; this
0x180091889  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18009188e  mov     edx, eax; int
0x180091890  lea     rcx, [rsp+228h+var_E8]; this
0x180091898  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18009189d  lea     rcx, [rsp+228h+var_E8]; this
0x1800918a5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800918aa  mov     r8d, eax; char
0x1800918ad  xor     r9d, r9d; unsigned __int16 *
0x1800918b0  mov     edx, 1B5h; unsigned int
0x1800918b5  lea     rcx, [rsp+228h+var_E8]; this
0x1800918bd  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
