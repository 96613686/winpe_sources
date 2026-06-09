# CWbemNamespace::CloneClientCtx(IWbemContext *)

- ea: `0x1800604f8`
- end: `0x180060a00`
- name: `?CloneClientCtx@CWbemNamespace@@QEAAJPEAUIWbemContext@@@Z`
- size: `1288`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct IWbemContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002e7f8`

## callees

- `0x18000b140`
- `0x18000e950`
- `0x18000e99c`
- `0x1800604f8`
- `0x180060a08`
- `0x180061fd8`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180060662`
- `wbemcomn!GetMemLogObject` at `0x1800606bd`
- `wbemcomn!GetMemLogObject` at `0x180060711`
- `wbemcomn!GetMemLogObject` at `0x18006079a`
- `wbemcomn!GetMemLogObject` at `0x1800607df`
- `wbemcomn!GetMemLogObject` at `0x180060952`
- `wbemcomn!GetMemLogObject` at `0x1800609cd`
- `wbemcomn!GetMemLogObject` at `0x180060662`
- `wbemcomn!GetMemLogObject` at `0x1800606bd`
- `wbemcomn!GetMemLogObject` at `0x180060711`
- `wbemcomn!GetMemLogObject` at `0x18006079a`
- `wbemcomn!GetMemLogObject` at `0x1800607df`
- `wbemcomn!GetMemLogObject` at `0x180060952`
- `wbemcomn!GetMemLogObject` at `0x1800609cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060670`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800606c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006071f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800607a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800607ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006095d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800609d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060670`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800606c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006071f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800607a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800607ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006095d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800609d8`
- `OLEAUT32!__imp_VariantInit` at `0x18006051e`
- `OLEAUT32!__imp_VariantInit` at `0x180060578`
- `OLEAUT32!__imp_VariantInit` at `0x18006051e`
- `OLEAUT32!__imp_VariantInit` at `0x180060578`
- `OLEAUT32!__imp_VariantClear` at `0x18006063e`
- `OLEAUT32!__imp_VariantClear` at `0x18006064c`
- `OLEAUT32!__imp_VariantClear` at `0x180060691`
- `OLEAUT32!__imp_VariantClear` at `0x1800606e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800606fb`
- `OLEAUT32!__imp_VariantClear` at `0x180060740`
- `OLEAUT32!__imp_VariantClear` at `0x18006074e`
- `OLEAUT32!__imp_VariantClear` at `0x18006077c`
- `OLEAUT32!__imp_VariantClear` at `0x1800607c9`
- `OLEAUT32!__imp_VariantClear` at `0x18006080b`
- `OLEAUT32!__imp_VariantClear` at `0x180060819`
- `OLEAUT32!__imp_VariantClear` at `0x18006063e`
- `OLEAUT32!__imp_VariantClear` at `0x18006064c`
- `OLEAUT32!__imp_VariantClear` at `0x180060691`
- `OLEAUT32!__imp_VariantClear` at `0x1800606e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800606fb`
- `OLEAUT32!__imp_VariantClear` at `0x180060740`
- `OLEAUT32!__imp_VariantClear` at `0x18006074e`
- `OLEAUT32!__imp_VariantClear` at `0x18006077c`
- `OLEAUT32!__imp_VariantClear` at `0x1800607c9`
- `OLEAUT32!__imp_VariantClear` at `0x18006080b`
- `OLEAUT32!__imp_VariantClear` at `0x180060819`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::CloneClientCtx(CWbemNamespace *this, struct IWbemContext *a2)
{
  int v5; // ebx
  int v6; // eax
  int v7; // ebx
  HRESULT v8; // eax
  struct IErrorInfo *v9; // rdx
  HRESULT v10; // eax
  struct IErrorInfo *v11; // rdx
  CMemoryLog *v12; // rax
  HRESULT v13; // eax
  struct IErrorInfo *v14; // rdx
  CMemoryLog *v15; // rax
  HRESULT v16; // eax
  struct IErrorInfo *v17; // rdx
  HRESULT v18; // eax
  struct IErrorInfo *v19; // rdx
  CMemoryLog *v20; // rax
  HRESULT v21; // eax
  struct IErrorInfo *v22; // rdx
  HRESULT v23; // eax
  struct IErrorInfo *v24; // rdx
  HRESULT v25; // eax
  struct IErrorInfo *v26; // rdx
  CMemoryLog *v27; // rax
  HRESULT v28; // eax
  struct IErrorInfo *v29; // rdx
  CMemoryLog *v30; // rax
  HRESULT v31; // eax
  struct IErrorInfo *v32; // rdx
  HRESULT v33; // eax
  struct IErrorInfo *v34; // rdx
  CMemoryLog *v35; // rax
  CMemoryLog *MemLogObject; // rax
  VARIANTARG pvarSrc; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF

  if ( !a2 )
    return 0;
  VariantInit(&pvarg);
  v5 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
         a2,
         L"__ProviderArchitecture",
         0,
         &pvarg);
  if ( v5 < 0 )
  {
    if ( v5 == -2147217406 )
    {
      v25 = VariantClear(&pvarg);
      if ( v25 < 0 )
        _com_issue_error(v25, v26);
      return 0;
    }
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v5);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        489,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v5);
    }
    goto LABEL_64;
  }
  if ( pvarg.vt != 3 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 487, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    v13 = VariantClear(&pvarg);
    if ( v13 < 0 )
      _com_issue_error(v13, v14);
    return 2147749896LL;
  }
  v6 = _variant_t::operator long(&pvarg);
  *((_DWORD *)this + 98) = v6;
  if ( ((v6 - 32) & 0xFFFFFFDF) != 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 488, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    v28 = VariantClear(&pvarg);
    if ( v28 < 0 )
      _com_issue_error(v28, v29);
    return 2147749896LL;
  }
  VariantInit(&pvarSrc);
  v5 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
         a2,
         L"__RequiredArchitecture",
         0,
         &pvarSrc);
  if ( v5 < 0 )
  {
    if ( v5 != -2147217406 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, v5);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          491,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v5);
      }
      v16 = VariantClear(&pvarSrc);
      if ( v16 < 0 )
        _com_issue_error(v16, v17);
      v18 = VariantClear(&pvarg);
      if ( v18 < 0 )
        _com_issue_error(v18, v19);
      return (unsigned int)v5;
    }
    goto LABEL_9;
  }
  if ( pvarSrc.vt != 11 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 490, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    v21 = VariantClear(&pvarSrc);
    if ( v21 < 0 )
      _com_issue_error(v21, v22);
    v23 = VariantClear(&pvarg);
    if ( v23 < 0 )
      _com_issue_error(v23, v24);
    return 2147749896LL;
  }
  *((_DWORD *)this + 99) = _variant_t::operator long(&pvarSrc);
LABEL_9:
  v7 = *((_DWORD *)this + 99);
  if ( pvarSrc.vt != 11 )
  {
    _variant_t::Clear((_variant_t *)&pvarSrc);
    pvarSrc.vt = 11;
  }
  pvarSrc.iVal = -(v7 != 0);
  v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 48) + 64LL))(
         *((_QWORD *)this + 48),
         L"__ProviderArchitecture",
         0,
         &pvarg);
  if ( v5 < 0 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, v5);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        492,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v5);
    }
    v31 = VariantClear(&pvarSrc);
    if ( v31 < 0 )
      _com_issue_error(v31, v32);
    v33 = VariantClear(&pvarg);
    if ( v33 < 0 )
      _com_issue_error(v33, v34);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 48) + 64LL))(
         *((_QWORD *)this + 48),
         L"__RequiredArchitecture",
         0,
         &pvarSrc);
  if ( v5 >= 0 )
  {
    *((_BYTE *)this + 400) = 1;
    v8 = VariantClear(&pvarSrc);
    if ( v8 < 0 )
      _com_issue_error(v8, v9);
    v10 = VariantClear(&pvarg);
    if ( v10 < 0 )
      _com_issue_error(v10, v11);
    return 0;
  }
  v35 = GetMemLogObject();
  CMemoryLog::Write(v35, v5);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      493,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)v5);
  }
  _variant_t::~_variant_t(&pvarSrc);
LABEL_64:
  _variant_t::~_variant_t(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800604f8  push    rbp
0x1800604fa  push    rbx
0x1800604fb  push    rsi
0x1800604fc  push    rdi
0x1800604fd  mov     rbp, rsp
0x180060500  sub     rsp, 68h
0x180060504  mov     rsi, rdx
0x180060507  mov     rdi, rcx
0x18006050a  test    rdx, rdx
0x18006050d  jnz     short loc_18006051A
0x18006050f  xor     eax, eax
0x180060511  add     rsp, 68h
0x180060515  pop     rdi
0x180060516  pop     rsi
0x180060517  pop     rbx
0x180060518  pop     rbp
0x180060519  retn
0x18006051a  lea     rcx, [rbp+pvarg]; pvarg
0x18006051e  call    cs:__imp_VariantInit
0x180060524  nop
0x180060525  mov     rax, [rsi]
0x180060528  lea     r9, [rbp+pvarg]
0x18006052c  xor     r8d, r8d
0x18006052f  lea     rdx, aProviderarchit; "__ProviderArchitecture"
0x180060536  mov     rcx, rsi
0x180060539  mov     rax, [rax+48h]
0x18006053d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060542  mov     ebx, eax
0x180060544  test    eax, eax
0x180060546  js      loc_18006076C
0x18006054c  cmp     word ptr [rbp+pvarg], 3
0x180060551  jnz     loc_180060662
0x180060557  lea     rcx, [rbp+pvarg]; pvarSrc
0x18006055b  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x180060560  mov     [rdi+188h], eax
0x180060566  add     eax, 0FFFFFFE0h
0x180060569  test    eax, 0FFFFFFDFh
0x18006056e  jnz     loc_18006079A
0x180060574  lea     rcx, [rbp+pvarSrc]; pvarg
0x180060578  call    cs:__imp_VariantInit
0x18006057e  nop
0x18006057f  mov     rax, [rsi]
0x180060582  lea     r9, [rbp+pvarSrc]
0x180060586  xor     r8d, r8d
0x180060589  lea     rdx, aRequiredarchit; "__RequiredArchitecture"
0x180060590  mov     rcx, rsi
0x180060593  mov     rax, [rax+48h]
0x180060597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006059c  mov     ebx, eax
0x18006059e  mov     esi, 0Bh
0x1800605a3  test    eax, eax
0x1800605a5  js      loc_1800606B1
0x1800605ab  cmp     word ptr [rbp+pvarSrc], si
0x1800605af  jnz     loc_180060711
0x1800605b5  lea     rcx, [rbp+pvarSrc]; pvarSrc
0x1800605b9  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x1800605be  mov     [rdi+18Ch], eax
0x1800605c4  mov     ebx, [rdi+18Ch]
0x1800605ca  cmp     word ptr [rbp+pvarSrc], si
0x1800605ce  jnz     loc_18006090F
0x1800605d4  neg     ebx
0x1800605d6  sbb     ax, ax
0x1800605d9  mov     word ptr [rbp+pvarSrc+8], ax
0x1800605dd  mov     rcx, [rdi+180h]
0x1800605e4  mov     rax, [rcx]
0x1800605e7  lea     r9, [rbp+pvarg]
0x1800605eb  xor     r8d, r8d
0x1800605ee  lea     rdx, aProviderarchit; "__ProviderArchitecture"
0x1800605f5  mov     rax, [rax+40h]
0x1800605f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605fe  mov     ebx, eax
0x180060600  test    eax, eax
0x180060602  js      loc_1800607DF
0x180060608  mov     rcx, [rdi+180h]
0x18006060f  mov     rax, [rcx]
0x180060612  lea     r9, [rbp+pvarSrc]
0x180060616  xor     r8d, r8d
0x180060619  lea     rdx, aRequiredarchit; "__RequiredArchitecture"
0x180060620  mov     rax, [rax+40h]
0x180060624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060629  mov     ebx, eax
0x18006062b  test    eax, eax
0x18006062d  js      loc_180060952
0x180060633  mov     byte ptr [rdi+190h], 1
0x18006063a  lea     rcx, [rbp+pvarSrc]; pvarg
0x18006063e  call    cs:__imp_VariantClear
0x180060644  test    eax, eax
0x180060646  js      short loc_1800606A9
0x180060648  lea     rcx, [rbp+pvarg]; pvarg
0x18006064c  call    cs:__imp_VariantClear
0x180060652  test    eax, eax
0x180060654  jns     loc_18006050F
0x18006065a  mov     ecx, eax; int
0x18006065c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060662  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060668  mov     edx, 80041008h
0x18006066d  mov     rcx, rax
0x180060670  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060676  lea     rax, WPP_GLOBAL_Control
0x18006067d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060684  cmp     rcx, rax
0x180060687  jnz     loc_180060842
0x18006068d  lea     rcx, [rbp+pvarg]; pvarg
0x180060691  call    cs:__imp_VariantClear
0x180060697  test    eax, eax
0x180060699  js      loc_180060764
0x18006069f  mov     eax, 80041008h
0x1800606a4  jmp     loc_180060511
0x1800606a9  mov     ecx, eax; int
0x1800606ab  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800606b1  cmp     ebx, 80041002h
0x1800606b7  jz      loc_1800605C4
0x1800606bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800606c3  mov     edx, ebx
0x1800606c5  mov     rcx, rax
0x1800606c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800606ce  lea     rax, WPP_GLOBAL_Control
0x1800606d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606dc  cmp     rcx, rax
0x1800606df  jnz     loc_1800608DE
0x1800606e5  lea     rcx, [rbp+pvarSrc]; pvarg
0x1800606e9  call    cs:__imp_VariantClear
0x1800606ef  test    eax, eax
0x1800606f1  js      loc_18006083A
0x1800606f7  lea     rcx, [rbp+pvarg]; pvarg
0x1800606fb  call    cs:__imp_VariantClear
0x180060701  test    eax, eax
0x180060703  jns     loc_180060823
0x180060709  mov     ecx, eax; int
0x18006070b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060711  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060717  mov     edx, 80041008h
0x18006071c  mov     rcx, rax
0x18006071f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060725  lea     rax, WPP_GLOBAL_Control
0x18006072c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060733  cmp     rcx, rax
0x180060736  jnz     loc_1800608AA
0x18006073c  lea     rcx, [rbp+pvarSrc]; pvarg
0x180060740  call    cs:__imp_VariantClear
0x180060746  test    eax, eax
0x180060748  js      short loc_180060792
0x18006074a  lea     rcx, [rbp+pvarg]; pvarg
0x18006074e  call    cs:__imp_VariantClear
0x180060754  test    eax, eax
0x180060756  jns     loc_18006069F
0x18006075c  mov     ecx, eax; int
0x18006075e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060764  mov     ecx, eax; int
0x180060766  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18006076c  cmp     ebx, 80041002h
0x180060772  jnz     loc_1800609CD
0x180060778  lea     rcx, [rbp+pvarg]; pvarg
0x18006077c  call    cs:__imp_VariantClear
0x180060782  test    eax, eax
0x180060784  jns     loc_18006050F
0x18006078a  mov     ecx, eax; int
0x18006078c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060792  mov     ecx, eax; int
0x180060794  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18006079a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800607a0  mov     edx, 80041008h
0x1800607a5  mov     rcx, rax
0x1800607a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800607ae  lea     rax, WPP_GLOBAL_Control
0x1800607b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607bc  cmp     rcx, rax
0x1800607bf  jnz     loc_180060876
0x1800607c5  lea     rcx, [rbp+pvarg]; pvarg
0x1800607c9  call    cs:__imp_VariantClear
0x1800607cf  test    eax, eax
0x1800607d1  jns     loc_18006069F
0x1800607d7  mov     ecx, eax; int
0x1800607d9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800607df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800607e5  mov     edx, ebx
0x1800607e7  mov     rcx, rax
0x1800607ea  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800607f0  lea     rax, WPP_GLOBAL_Control
0x1800607f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607fe  cmp     rcx, rax
0x180060801  jnz     loc_180060921
0x180060807  lea     rcx, [rbp+pvarSrc]; pvarg
0x18006080b  call    cs:__imp_VariantClear
0x180060811  test    eax, eax
0x180060813  js      short loc_18006082A
0x180060815  lea     rcx, [rbp+pvarg]; pvarg
0x180060819  call    cs:__imp_VariantClear
0x18006081f  test    eax, eax
0x180060821  js      short loc_180060832
0x180060823  mov     eax, ebx
0x180060825  jmp     loc_180060511
0x18006082a  mov     ecx, eax; int
0x18006082c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060832  mov     ecx, eax; int
0x180060834  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18006083a  mov     ecx, eax; int
0x18006083c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180060842  test    byte ptr [rcx+1Ch], 1
0x180060846  jz      loc_18006068D
0x18006084c  cmp     byte ptr [rcx+19h], 2
0x180060850  jb      loc_18006068D
0x180060856  mov     edx, 1E7h
0x18006085b  mov     r9d, 80041008h
0x180060861  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180060868  mov     rcx, [rcx+10h]
0x18006086c  call    WPP_SF_d
0x180060871  jmp     loc_18006068D
0x180060876  test    byte ptr [rcx+1Ch], 1
0x18006087a  jz      loc_1800607C5
0x180060880  cmp     byte ptr [rcx+19h], 2
0x180060884  jb      loc_1800607C5
0x18006088a  mov     edx, 1E8h
0x18006088f  mov     r9d, 80041008h
0x180060895  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18006089c  mov     rcx, [rcx+10h]
0x1800608a0  call    WPP_SF_d
0x1800608a5  jmp     loc_1800607C5
0x1800608aa  test    byte ptr [rcx+1Ch], 1
0x1800608ae  jz      loc_18006073C
0x1800608b4  cmp     byte ptr [rcx+19h], 2
0x1800608b8  jb      loc_18006073C
0x1800608be  mov     edx, 1EAh
0x1800608c3  mov     r9d, 80041008h
0x1800608c9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800608d0  mov     rcx, [rcx+10h]
0x1800608d4  call    WPP_SF_d
0x1800608d9  jmp     loc_18006073C
0x1800608de  test    byte ptr [rcx+1Ch], 1
0x1800608e2  jz      loc_1800606E5
0x1800608e8  cmp     byte ptr [rcx+19h], 2
0x1800608ec  jb      loc_1800606E5
0x1800608f2  mov     edx, 1EBh
0x1800608f7  mov     r9d, ebx
0x1800608fa  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180060901  mov     rcx, [rcx+10h]
0x180060905  call    WPP_SF_d
0x18006090a  jmp     loc_1800606E5
0x18006090f  lea     rcx, [rbp+pvarSrc]; this
0x180060913  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x180060918  mov     word ptr [rbp+pvarSrc], si
0x18006091c  jmp     loc_1800605D4
0x180060921  test    byte ptr [rcx+1Ch], 1
0x180060925  jz      loc_180060807
0x18006092b  cmp     byte ptr [rcx+19h], 2
0x18006092f  jb      loc_180060807
0x180060935  mov     edx, 1ECh
0x18006093a  mov     r9d, ebx
0x18006093d  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180060944  mov     rcx, [rcx+10h]
0x180060948  call    WPP_SF_d
0x18006094d  jmp     loc_180060807
0x180060952  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060958  mov     edx, ebx
0x18006095a  mov     rcx, rax
0x18006095d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060963  lea     rax, WPP_GLOBAL_Control
0x18006096a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060971  cmp     rcx, rax
0x180060974  jz      short loc_18006099B
0x180060976  test    byte ptr [rcx+1Ch], 1
0x18006097a  jz      short loc_18006099B
0x18006097c  cmp     byte ptr [rcx+19h], 2
0x180060980  jb      short loc_18006099B
0x180060982  mov     edx, 1EDh
0x180060987  mov     r9d, ebx
0x18006098a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180060991  mov     rcx, [rcx+10h]
0x180060995  call    WPP_SF_d
0x18006099a  nop
0x18006099b  lea     rcx, [rbp+pvarSrc]; this
0x18006099f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800609a4  jmp     short loc_1800609BF
0x1800609a6  mov     edx, 1E9h
0x1800609ab  mov     r9d, ebx
0x1800609ae  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800609b5  mov     rcx, [rcx+10h]
0x1800609b9  call    WPP_SF_d
0x1800609be  nop
0x1800609bf  lea     rcx, [rbp+pvarg]; this
0x1800609c3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800609c8  jmp     loc_180060823
0x1800609cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800609d3  mov     edx, ebx
0x1800609d5  mov     rcx, rax
0x1800609d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800609de  lea     rax, WPP_GLOBAL_Control
0x1800609e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800609ec  cmp     rcx, rax
0x1800609ef  jz      short loc_1800609BF
0x1800609f1  test    byte ptr [rcx+1Ch], 1
0x1800609f5  jz      short loc_1800609BF
0x1800609f7  cmp     byte ptr [rcx+19h], 2
0x1800609fb  jb      short loc_1800609BF
0x1800609fd  jmp     short loc_1800609A6
```
