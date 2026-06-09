# SrmStringRangeToSafeArray<std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>(std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,unsigned __int64,tagSAFEARRAY * *)

- ea: `0x180002658`
- end: `0x180002958`
- name: `??$SrmStringRangeToSafeArray@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@@YAXV?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@0_KPEAPEAUtagSAFEARRAY@@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, __int64, __int64, SAFEARRAY **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e224`

## callees

- `0x180002658`
- `0x1800083e0`
- `0x18000d368`
- `0x180015ef4`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002799`
- `OLEAUT32!__imp_SysAllocString` at `0x180002799`
- `OLEAUT32!__imp_VariantClear` at `0x1800027e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800027e6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800027c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800027c9`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000274d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000274d`

## pseudocode

```c
void __fastcall SrmStringRangeToSafeArray<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        SAFEARRAY **a4)
{
  SAFEARRAY *Vector; // r14
  HRESULT v9; // ecx
  LONG v10; // edx
  const OLECHAR *v11; // rsi
  BSTR v12; // rax
  HRESULT v13; // eax
  HRESULT v14; // eax
  char v15; // al
  char Hr; // al
  int v17; // eax
  char v18; // al
  char v19; // al
  LONG rgIndices; // [rsp+20h] [rbp-E0h] BYREF
  void **v21; // [rsp+28h] [rbp-D8h]
  SAFEARRAY *v22; // [rsp+30h] [rbp-D0h]
  VARIANTARG pv; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v24; // [rsp+50h] [rbp-B0h]
  _QWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+74h] [rbp-8Ch]
  int v28; // [rsp+78h] [rbp-88h]
  char v29[96]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+E0h] [rbp-20h]
  void **v31; // [rsp+F0h] [rbp-10h] BYREF
  HRESULT v32; // [rsp+F8h] [rbp-8h]

  v24 = v25;
  v25[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmtypes.h";
  v25[1] = L"SrmStringRangeToSafeArray";
  v25[2] = L"INCTYPEH";
  v26 = 2748;
  v27 = 17;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CSrmFunctionTracer::CSrmFunctionTracer(&v31, v25, 0);
  if ( !a4 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0xAC0u, Hr, 0);
  }
  *a4 = 0;
  v32 = 0;
  v21 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  Vector = SafeArrayCreateVector(0xCu, 0, a3);
  v22 = Vector;
  if ( !Vector )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, -2147024882);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0xAC5u, v15, 0);
  }
  v9 = 0;
  v32 = 0;
  v10 = 0;
  rgIndices = 0;
  while ( a1 != a2 )
  {
    if ( *(_QWORD *)(a1 + 24) < 8u )
      v11 = (const OLECHAR *)a1;
    else
      v11 = *(const OLECHAR **)a1;
    v12 = SysAllocString(v11);
    if ( !v12 && v11 )
      _com_issue_error(-2147024882);
    pv.vt = 8;
    pv.llVal = (LONGLONG)v12;
    v13 = SafeArrayPutElement(Vector, &rgIndices, &pv);
    v32 = v13;
    if ( v13 < 0 )
    {
      v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, v17);
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0xACDu, v18, 0);
    }
    v32 = v13;
    ++rgIndices;
    v14 = VariantClear(&pv);
    if ( v14 < 0 )
      _com_issue_error(v14);
    a1 += 40;
    v9 = v32;
    v10 = rgIndices;
  }
  v32 = v9;
  if ( v10 != a3 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, -2147200234);
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0xAD3u, v19, 0);
  }
  v32 = 0;
  *a4 = Vector;
  v21 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v22 = 0;
  v31 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v31);
}

```

## disassembly

```asm
0x180002658  mov     [rsp-8+arg_0], rbx
0x18000265d  mov     [rsp-8+arg_8], rsi
0x180002662  push    rbp
0x180002663  push    rdi
0x180002664  push    r12
0x180002666  push    r14
0x180002668  push    r15
0x18000266a  lea     rbp, [rsp-0B0h]
0x180002672  sub     rsp, 1B0h
0x180002679  mov     rax, cs:__security_cookie
0x180002680  xor     rax, rsp
0x180002683  mov     [rbp+0D0h+var_30], rax
0x18000268a  mov     r15, r9
0x18000268d  mov     r12, r8
0x180002690  mov     rdi, rdx
0x180002693  mov     rbx, rcx
0x180002696  lea     rax, [rsp+1D0h+var_178]
0x18000269b  mov     [rsp+1D0h+var_180], rax
0x1800026a0  lea     rax, aBaseFsFsrmUtil; "base\\fs\\fsrm\\utilities\\inc\\srmtype"...
0x1800026a7  mov     [rsp+1D0h+var_178], rax
0x1800026ac  lea     rax, aSrmstringrange; "SrmStringRangeToSafeArray"
0x1800026b3  mov     [rsp+1D0h+var_170], rax
0x1800026b8  lea     rax, aInctypeh; "INCTYPEH"
0x1800026bf  mov     [rsp+1D0h+var_168], rax
0x1800026c4  mov     [rsp+1D0h+var_160], 0ABCh
0x1800026cc  mov     [rsp+1D0h+var_15C], 11h
0x1800026d4  mov     [rsp+1D0h+var_158], 0FFh
0x1800026dc  mov     [rbp+0D0h+var_F0], 1000000h
0x1800026e3  xor     edx, edx; Val
0x1800026e5  lea     r8d, [rdx+60h]; Size
0x1800026e9  lea     rcx, [rbp+0D0h+var_150]; void *
0x1800026ed  call    memset_0
0x1800026f2  nop
0x1800026f3  xor     r8d, r8d
0x1800026f6  lea     rdx, [rsp+1D0h+var_178]
0x1800026fb  lea     rcx, [rbp+0D0h+var_E0]
0x1800026ff  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180002704  nop
0x180002705  mov     eax, [rbp+0D0h+var_D8]
0x180002708  mov     [rbp+0D0h+var_D8], eax
0x18000270b  test    r15, r15
0x18000270e  jz      loc_1800028BB
0x180002714  mov     qword ptr [r15], 0
0x18000271b  mov     [rbp+0D0h+var_D8], 0
0x180002722  lea     rsi, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x180002729  mov     [rsp+1D0h+var_1A8], rsi
0x18000272e  mov     [rsp+1D0h+var_1A0], 0
0x180002737  lea     rsi, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18000273e  mov     [rsp+1D0h+var_1A8], rsi
0x180002743  mov     r8d, r12d; cElements
0x180002746  mov     ecx, 0Ch; vt
0x18000274b  xor     edx, edx; lLbound
0x18000274d  call    cs:__imp_SafeArrayCreateVector
0x180002753  mov     r14, rax
0x180002756  mov     [rsp+1D0h+var_1A0], 0
0x18000275f  mov     [rsp+1D0h+var_1A0], rax
0x180002764  mov     ecx, [rbp+0D0h+var_D8]
0x180002767  mov     [rbp+0D0h+var_D8], ecx
0x18000276a  test    rax, rax
0x18000276d  jz      loc_18000288F
0x180002773  xor     ecx, ecx
0x180002775  mov     [rbp+0D0h+var_D8], ecx
0x180002778  xor     edx, edx
0x18000277a  mov     [rsp+1D0h+rgIndices], edx
0x18000277e  mov     eax, 8
0x180002783  cmp     rbx, rdi
0x180002786  jz      short loc_180002804
0x180002788  cmp     [rbx+18h], rax
0x18000278c  jb      short loc_180002793
0x18000278e  mov     rsi, [rbx]
0x180002791  jmp     short loc_180002796
0x180002793  mov     rsi, rbx
0x180002796  mov     rcx, rsi; psz
0x180002799  call    cs:__imp_SysAllocString
0x18000279f  test    rax, rax
0x1800027a2  jnz     short loc_1800027AD
0x1800027a4  test    rsi, rsi
0x1800027a7  jnz     loc_1800028E7
0x1800027ad  mov     ecx, 8
0x1800027b2  mov     [rsp+1D0h+pv], cx
0x1800027b7  mov     [rsp+1D0h+var_190], rax
0x1800027bc  lea     r8, [rsp+1D0h+pv]; pv
0x1800027c1  lea     rdx, [rsp+1D0h+rgIndices]; rgIndices
0x1800027c6  mov     rcx, r14; psa
0x1800027c9  call    cs:__imp_SafeArrayPutElement
0x1800027cf  mov     [rbp+0D0h+var_D8], eax
0x1800027d2  test    eax, eax
0x1800027d4  js      loc_1800028FA
0x1800027da  mov     [rbp+0D0h+var_D8], eax
0x1800027dd  inc     [rsp+1D0h+rgIndices]
0x1800027e1  lea     rcx, [rsp+1D0h+pv]; pvarg
0x1800027e6  call    cs:__imp_VariantClear
0x1800027ec  test    eax, eax
0x1800027ee  js      loc_1800028F2
0x1800027f4  add     rbx, 28h ; '('
0x1800027f8  mov     ecx, [rbp+0D0h+var_D8]
0x1800027fb  mov     edx, [rsp+1D0h+rgIndices]
0x1800027ff  jmp     loc_18000277E
0x180002804  mov     [rbp+0D0h+var_D8], ecx
0x180002807  movsxd  rax, edx
0x18000280a  cmp     rax, r12
0x18000280d  jnz     loc_18000292C
0x180002813  mov     [rbp+0D0h+var_D8], 0
0x18000281a  mov     [rsp+1D0h+var_1A0], 0
0x180002823  mov     [r15], r14
0x180002826  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18000282d  mov     [rsp+1D0h+var_1A8], rax
0x180002832  mov     [rsp+1D0h+var_1A0], 0
0x18000283b  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x180002842  mov     [rsp+1D0h+var_1A8], rax
0x180002847  mov     [rsp+1D0h+var_1A0], 0
0x180002850  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180002857  mov     [rbp+0D0h+var_E0], rax
0x18000285b  lea     rcx, [rbp+0D0h+var_E0]; this
0x18000285f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180002864  mov     rcx, [rbp+0D0h+var_30]
0x18000286b  xor     rcx, rsp; StackCookie
0x18000286e  call    __security_check_cookie
0x180002873  lea     r11, [rsp+1D0h+var_20]
0x18000287b  mov     rbx, [r11+30h]
0x18000287f  mov     rsi, [r11+38h]
0x180002883  mov     rsp, r11
0x180002886  pop     r15
0x180002888  pop     r14
0x18000288a  pop     r12
0x18000288c  pop     rdi
0x18000288d  pop     rbp
0x18000288e  retn
0x18000288f  mov     edx, 8007000Eh; int
0x180002894  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002898  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000289d  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028a1  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800028a6  mov     r8d, eax; char
0x1800028a9  xor     r9d, r9d; unsigned __int16 *
0x1800028ac  mov     edx, 0AC5h; unsigned int
0x1800028b1  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028b5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800028bb  mov     edx, 80070057h; int
0x1800028c0  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028c4  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800028c9  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028cd  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800028d2  mov     r8d, eax; char
0x1800028d5  xor     r9d, r9d; unsigned __int16 *
0x1800028d8  mov     edx, 0AC0h; unsigned int
0x1800028dd  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028e1  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800028e7  mov     ecx, 8007000Eh; int
0x1800028ec  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800028f2  mov     ecx, eax; int
0x1800028f4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800028fa  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800028fe  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002903  mov     edx, eax; int
0x180002905  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002909  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000290e  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002912  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002917  mov     r8d, eax; char
0x18000291a  xor     r9d, r9d; unsigned __int16 *
0x18000291d  mov     edx, 0ACDh; unsigned int
0x180002922  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002926  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000292c  mov     edx, 80045316h; int
0x180002931  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002935  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000293a  lea     rcx, [rbp+0D0h+var_E0]; this
0x18000293e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002943  mov     r8d, eax; char
0x180002946  xor     r9d, r9d; unsigned __int16 *
0x180002949  mov     edx, 0AD3h; unsigned int
0x18000294e  lea     rcx, [rbp+0D0h+var_E0]; this
0x180002952  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
