# CAssocQuery::GetClassDefsOnlyClass(IWbemClassObject *,IWbemClassObject * *)

- ea: `0x180095368`
- end: `0x1800956cb`
- name: `?GetClassDefsOnlyClass@CAssocQuery@@AEAAJPEAUIWbemClassObject@@PEAPEAU2@@Z`
- size: `867`
- prototype: `__int64 __fastcall(CAssocQuery *__hidden this, struct IWbemClassObject *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180025df0`

## callees

- `0x18000b140`
- `0x18000e950`
- `0x18000ebd0`
- `0x18003cfe0`
- `0x180094cbc`
- `0x180095078`
- `0x180095368`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180095476`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180095476`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180095467`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180095467`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18009557d`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18009557d`
- `wbemcomn!GetMemLogObject` at `0x1800953ba`
- `wbemcomn!GetMemLogObject` at `0x1800954b9`
- `wbemcomn!GetMemLogObject` at `0x18009551f`
- `wbemcomn!GetMemLogObject` at `0x180095587`
- `wbemcomn!GetMemLogObject` at `0x1800955f8`
- `wbemcomn!GetMemLogObject` at `0x18009565e`
- `wbemcomn!GetMemLogObject` at `0x1800953ba`
- `wbemcomn!GetMemLogObject` at `0x1800954b9`
- `wbemcomn!GetMemLogObject` at `0x18009551f`
- `wbemcomn!GetMemLogObject` at `0x180095587`
- `wbemcomn!GetMemLogObject` at `0x1800955f8`
- `wbemcomn!GetMemLogObject` at `0x18009565e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800953c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800954c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009552a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180095597`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180095608`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009566e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800953c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800954c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009552a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180095597`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180095608`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009566e`
- `OLEAUT32!__imp_VariantInit` at `0x180095411`
- `OLEAUT32!__imp_VariantInit` at `0x180095411`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAssocQuery::GetClassDefsOnlyClass(
        CAssocQuery *this,
        struct IWbemClassObject *a2,
        struct IWbemClassObject **a3)
{
  unsigned int ParentmostClass; // ebx
  CMemoryLog *v7; // rax
  CClientCnt *v8; // r10
  __int64 v9; // rdx
  __int64 v10; // r9
  struct IWbemClassObject *v11; // r12
  unsigned int i; // ebx
  const unsigned __int16 *v13; // rax
  CMemoryLog *v14; // rax
  CClientCnt *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r9
  struct IWbemClassObject *v18; // r12
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r9
  CMemoryLog *v23; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *MemLogObject; // rax
  struct IWbemClassObject *v27; // [rsp+40h] [rbp-30h] BYREF
  struct IWbemClassObject *v28; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  struct IWbemClassObject *v30; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a2 || !a3 )
  {
    MemLogObject = GetMemLogObject();
    ParentmostClass = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return ParentmostClass;
    }
    v9 = 165;
    v10 = 2147749896LL;
LABEL_43:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, v10);
    return ParentmostClass;
  }
  *a3 = 0;
  v30 = 0;
  ParentmostClass = CAssocQuery::FindParentmostClass(this, a2, &v30);
  if ( (ParentmostClass & 0x80000000) != 0 )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, ParentmostClass);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return ParentmostClass;
    }
    v9 = 166;
    v10 = ParentmostClass;
    goto LABEL_43;
  }
  v11 = v30;
  v28 = v30;
  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v11->lpVtbl->Get)(
         v11,
         L"__CLASS",
         0,
         &pvarg,
         0,
         0) < 0
    || pvarg.vt != 8 )
  {
    v25 = GetMemLogObject();
    ParentmostClass = -2147217407;
    CMemoryLog::Write(v25, -2147217407);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v16 = 167;
    v17 = 2147749889LL;
LABEL_37:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, v17);
    goto LABEL_38;
  }
  for ( i = 0; (signed int)i < CWStringArray::Size((CAssocQuery *)((char *)this + 616)); ++i )
  {
    v13 = (const unsigned __int16 *)CWStringArray::operator[]((char *)this + 616, i);
    if ( !(unsigned int)wbem_wcsicmp(v13, pvarg.bstrVal) )
    {
      ParentmostClass = 0;
      goto LABEL_38;
    }
  }
  v27 = 0;
  ParentmostClass = ((__int64 (__fastcall *)(struct IWbemClassObject *, struct IWbemClassObject **))v11->lpVtbl->Clone)(
                      v11,
                      &v27);
  if ( (ParentmostClass & 0x80000000) != 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, ParentmostClass);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v16 = 168;
    v17 = ParentmostClass;
    goto LABEL_37;
  }
  v18 = v27;
  v30 = v27;
  ParentmostClass = CAssocQuery::ComputeInOutTags(this, a2, v27);
  if ( (ParentmostClass & 0x80000000) == 0 )
  {
    if ( !CWStringArray::Add((CAssocQuery *)((char *)this + 616), pvarg.bstrVal) )
    {
      v30 = 0;
      *a3 = v18;
      CReleaseMe::release((CReleaseMe *)&v30);
      _variant_t::~_variant_t(&pvarg);
      CReleaseMe::release((CReleaseMe *)&v28);
      return 0;
    }
    v23 = GetMemLogObject();
    ParentmostClass = -2147217402;
    CMemoryLog::Write(v23, -2147217402);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v21 = 170;
    v22 = 2147749894LL;
  }
  else
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, ParentmostClass);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v21 = 169;
    v22 = ParentmostClass;
  }
  WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, v22);
LABEL_26:
  CReleaseMe::release((CReleaseMe *)&v30);
LABEL_38:
  _variant_t::~_variant_t(&pvarg);
  CReleaseMe::release((CReleaseMe *)&v28);
  return ParentmostClass;
}

```

## disassembly

```asm
0x180095368  mov     [rsp-28h+arg_0], rbx
0x18009536d  mov     [rsp-28h+arg_10], rsi
0x180095372  push    rbp
0x180095373  push    rdi
0x180095374  push    r12
0x180095376  push    r14
0x180095378  push    r15
0x18009537a  mov     rbp, rsp
0x18009537d  sub     rsp, 70h
0x180095381  mov     rdi, r8
0x180095384  mov     rsi, rdx
0x180095387  mov     r14, rcx
0x18009538a  test    rdx, rdx
0x18009538d  jz      loc_18009565E
0x180095393  test    r8, r8
0x180095396  jz      loc_18009565E
0x18009539c  mov     qword ptr [r8], 0
0x1800953a3  mov     [rbp+arg_8], 0
0x1800953ab  lea     r8, [rbp+arg_8]; struct IWbemClassObject **
0x1800953af  call    ?FindParentmostClass@CAssocQuery@@AEAAJPEAUIWbemClassObject@@PEAPEAU2@@Z; CAssocQuery::FindParentmostClass(IWbemClassObject *,IWbemClassObject * *)
0x1800953b4  mov     ebx, eax
0x1800953b6  test    eax, eax
0x1800953b8  jns     short loc_180095405
0x1800953ba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800953c0  mov     edx, ebx
0x1800953c2  mov     rcx, rax
0x1800953c5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800953cb  lea     rcx, WPP_GLOBAL_Control
0x1800953d2  mov     r10, cs:WPP_GLOBAL_Control
0x1800953d9  cmp     r10, rcx
0x1800953dc  jz      loc_1800956B0
0x1800953e2  test    byte ptr [r10+1Ch], 1
0x1800953e7  jz      loc_1800956B0
0x1800953ed  cmp     byte ptr [r10+19h], 2
0x1800953f2  jb      loc_1800956B0
0x1800953f8  mov     edx, 0A6h
0x1800953fd  mov     r9d, ebx
0x180095400  jmp     loc_1800956A0
0x180095405  mov     r12, [rbp+arg_8]
0x180095409  mov     [rbp+var_28], r12
0x18009540d  lea     rcx, [rbp+pvarg]; pvarg
0x180095411  call    cs:__imp_VariantInit
0x180095417  nop
0x180095418  mov     rax, [r12]
0x18009541c  mov     [rsp+70h+var_48], 0
0x180095425  mov     [rsp+70h+var_50], 0
0x18009542e  lea     r9, [rbp+pvarg]
0x180095432  xor     r8d, r8d
0x180095435  lea     rdx, aClass_0; "__CLASS"
0x18009543c  mov     rcx, r12
0x18009543f  mov     rax, [rax+20h]
0x180095443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095448  test    eax, eax
0x18009544a  js      loc_1800955F8
0x180095450  cmp     word ptr [rbp+pvarg], 8
0x180095455  jnz     loc_1800955F8
0x18009545b  xor     ebx, ebx
0x18009545d  lea     r15, [r14+268h]
0x180095464  mov     rcx, r15
0x180095467  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18009546d  cmp     ebx, eax
0x18009546f  jge     short loc_180095497
0x180095471  mov     edx, ebx
0x180095473  mov     rcx, r15
0x180095476  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x18009547c  mov     rcx, rax; unsigned __int16 *
0x18009547f  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180095483  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180095488  test    eax, eax
0x18009548a  jz      short loc_180095490
0x18009548c  inc     ebx
0x18009548e  jmp     short loc_180095464
0x180095490  xor     ebx, ebx
0x180095492  jmp     loc_180095649
0x180095497  mov     [rbp+var_30], 0
0x18009549f  mov     rax, [r12]
0x1800954a3  lea     rdx, [rbp+var_30]
0x1800954a7  mov     rcx, r12
0x1800954aa  mov     rax, [rax+60h]
0x1800954ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800954b3  mov     ebx, eax
0x1800954b5  test    eax, eax
0x1800954b7  jns     short loc_180095502
0x1800954b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800954bf  mov     edx, ebx
0x1800954c1  mov     rcx, rax
0x1800954c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800954ca  lea     rcx, WPP_GLOBAL_Control
0x1800954d1  mov     rax, cs:WPP_GLOBAL_Control
0x1800954d8  cmp     rax, rcx
0x1800954db  jz      loc_180095649
0x1800954e1  test    byte ptr [rax+1Ch], 1
0x1800954e5  jz      loc_180095649
0x1800954eb  cmp     byte ptr [rax+19h], 2
0x1800954ef  jb      loc_180095649
0x1800954f5  mov     edx, 0A8h
0x1800954fa  mov     r9d, ebx
0x1800954fd  jmp     loc_180095638
0x180095502  mov     r12, [rbp+var_30]
0x180095506  mov     [rbp+arg_8], r12
0x18009550a  mov     r8, [rbp+var_30]; struct IWbemClassObject *
0x18009550e  mov     rdx, rsi; struct IWbemClassObject *
0x180095511  mov     rcx, r14; this
0x180095514  call    ?ComputeInOutTags@CAssocQuery@@AEAAJPEAUIWbemClassObject@@0@Z; CAssocQuery::ComputeInOutTags(IWbemClassObject *,IWbemClassObject *)
0x180095519  mov     ebx, eax
0x18009551b  test    eax, eax
0x18009551d  jns     short loc_180095576
0x18009551f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180095525  mov     edx, ebx
0x180095527  mov     rcx, rax
0x18009552a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180095530  lea     rcx, WPP_GLOBAL_Control
0x180095537  mov     rax, cs:WPP_GLOBAL_Control
0x18009553e  cmp     rax, rcx
0x180095541  jz      short loc_180095568
0x180095543  test    byte ptr [rax+1Ch], 1
0x180095547  jz      short loc_180095568
0x180095549  cmp     byte ptr [rax+19h], 2
0x18009554d  jb      short loc_180095568
0x18009554f  mov     edx, 0A9h
0x180095554  mov     r9d, ebx
0x180095557  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x18009555e  mov     rcx, [rax+10h]
0x180095562  call    WPP_SF_d
0x180095567  nop
0x180095568  lea     rcx, [rbp+arg_8]; this
0x18009556c  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180095571  jmp     loc_180095649
0x180095576  mov     rdx, qword ptr [rbp+pvarg+8]
0x18009557a  mov     rcx, r15
0x18009557d  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180095583  test    eax, eax
0x180095585  jz      short loc_1800955C9
0x180095587  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009558d  mov     ebx, 80041006h
0x180095592  mov     edx, ebx
0x180095594  mov     rcx, rax
0x180095597  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009559d  lea     rcx, WPP_GLOBAL_Control
0x1800955a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800955ab  cmp     rax, rcx
0x1800955ae  jz      short loc_180095568
0x1800955b0  test    byte ptr [rax+1Ch], 1
0x1800955b4  jz      short loc_180095568
0x1800955b6  cmp     byte ptr [rax+19h], 2
0x1800955ba  jb      short loc_180095568
0x1800955bc  mov     edx, 0AAh
0x1800955c1  mov     r9d, 80041006h
0x1800955c7  jmp     short loc_180095557
0x1800955c9  mov     [rbp+arg_8], 0
0x1800955d1  mov     [rdi], r12
0x1800955d4  lea     rcx, [rbp+arg_8]; this
0x1800955d8  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800955dd  nop
0x1800955de  lea     rcx, [rbp+pvarg]; this
0x1800955e2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800955e7  nop
0x1800955e8  lea     rcx, [rbp+var_28]; this
0x1800955ec  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800955f1  xor     eax, eax
0x1800955f3  jmp     loc_1800956B2
0x1800955f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800955fe  mov     ebx, 80041001h
0x180095603  mov     edx, ebx
0x180095605  mov     rcx, rax
0x180095608  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009560e  lea     rcx, WPP_GLOBAL_Control
0x180095615  mov     rax, cs:WPP_GLOBAL_Control
0x18009561c  cmp     rax, rcx
0x18009561f  jz      short loc_180095649
0x180095621  test    byte ptr [rax+1Ch], 1
0x180095625  jz      short loc_180095649
0x180095627  cmp     byte ptr [rax+19h], 2
0x18009562b  jb      short loc_180095649
0x18009562d  mov     edx, 0A7h
0x180095632  mov     r9d, 80041001h
0x180095638  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x18009563f  mov     rcx, [rax+10h]
0x180095643  call    WPP_SF_d
0x180095648  nop
0x180095649  lea     rcx, [rbp+pvarg]; this
0x18009564d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180095652  nop
0x180095653  lea     rcx, [rbp+var_28]; this
0x180095657  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009565c  jmp     short loc_1800956B0
0x18009565e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180095664  mov     ebx, 80041008h
0x180095669  mov     edx, ebx
0x18009566b  mov     rcx, rax
0x18009566e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180095674  lea     rcx, WPP_GLOBAL_Control
0x18009567b  mov     r10, cs:WPP_GLOBAL_Control
0x180095682  cmp     r10, rcx
0x180095685  jz      short loc_1800956B0
0x180095687  test    byte ptr [r10+1Ch], 1
0x18009568c  jz      short loc_1800956B0
0x18009568e  cmp     byte ptr [r10+19h], 2
0x180095693  jb      short loc_1800956B0
0x180095695  mov     edx, 0A5h
0x18009569a  mov     r9d, 80041008h
0x1800956a0  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x1800956a7  mov     rcx, [r10+10h]
0x1800956ab  call    WPP_SF_d
0x1800956b0  mov     eax, ebx
0x1800956b2  lea     r11, [rsp+70h+var_s0]
0x1800956b7  mov     rbx, [r11+30h]
0x1800956bb  mov     rsi, [r11+40h]
0x1800956bf  mov     rsp, r11
0x1800956c2  pop     r15
0x1800956c4  pop     r14
0x1800956c6  pop     r12
0x1800956c8  pop     rdi
0x1800956c9  pop     rbp
0x1800956ca  retn
```
