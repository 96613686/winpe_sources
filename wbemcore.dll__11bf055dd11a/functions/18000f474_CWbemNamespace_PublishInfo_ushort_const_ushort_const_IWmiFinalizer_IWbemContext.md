# CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)

- ea: `0x18000f474`
- end: `0x18000fa6d`
- name: `?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z`
- size: `1529`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _IWmiFinalizer *, struct IWbemContext *)`
- caller_count: `10`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020f20`
- `0x180022a90`
- `0x180046a20`
- `0x1800477b0`
- `0x180048360`
- `0x180064630`
- `0x180066e10`
- `0x1800842f0`
- `0x1800a0a40`
- `0x1800a1270`

## callees

- `0x18000b140`
- `0x18000e950`
- `0x18000e99c`
- `0x18000f474`
- `0x18000fa74`
- `0x18003d010`
- `0x180061078`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!BuildOperationInfo` at `0x18000f575`
- `wbemcomn!BuildOperationInfo` at `0x18000f575`
- `wbemcomn!?Publish@CPublishWMIOperationEvent@@SAJPEAGKK0000K_K0H@Z` at `0x18000f630`
- `wbemcomn!?Publish@CPublishWMIOperationEvent@@SAJPEAGKK0000K_K0H@Z` at `0x18000f630`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f58a`
- `wbemcomn!GetMemLogObject` at `0x18000f78d`
- `wbemcomn!GetMemLogObject` at `0x18000f7e1`
- `wbemcomn!GetMemLogObject` at `0x18000f836`
- `wbemcomn!GetMemLogObject` at `0x18000f882`
- `wbemcomn!GetMemLogObject` at `0x18000f927`
- `wbemcomn!GetMemLogObject` at `0x18000f9ca`
- `wbemcomn!GetMemLogObject` at `0x18000fa0b`
- `wbemcomn!GetMemLogObject` at `0x18000f78d`
- `wbemcomn!GetMemLogObject` at `0x18000f7e1`
- `wbemcomn!GetMemLogObject` at `0x18000f836`
- `wbemcomn!GetMemLogObject` at `0x18000f882`
- `wbemcomn!GetMemLogObject` at `0x18000f927`
- `wbemcomn!GetMemLogObject` at `0x18000f9ca`
- `wbemcomn!GetMemLogObject` at `0x18000fa0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f798`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f7ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f841`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f88d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f937`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f9d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000fa16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f798`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f7ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f841`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f88d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f937`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f9d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000fa16`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f6c1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f6c1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f6dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f6dc`
- `OLEAUT32!__imp_VariantInit` at `0x18000f4bb`
- `OLEAUT32!__imp_VariantInit` at `0x18000f51a`
- `OLEAUT32!__imp_VariantInit` at `0x18000f4bb`
- `OLEAUT32!__imp_VariantInit` at `0x18000f51a`
- `OLEAUT32!__imp_VariantClear` at `0x18000f650`
- `OLEAUT32!__imp_VariantClear` at `0x18000f65e`
- `OLEAUT32!__imp_VariantClear` at `0x18000f752`
- `OLEAUT32!__imp_VariantClear` at `0x18000f7ba`
- `OLEAUT32!__imp_VariantClear` at `0x18000f7c8`
- `OLEAUT32!__imp_VariantClear` at `0x18000f80d`
- `OLEAUT32!__imp_VariantClear` at `0x18000f650`
- `OLEAUT32!__imp_VariantClear` at `0x18000f65e`
- `OLEAUT32!__imp_VariantClear` at `0x18000f752`
- `OLEAUT32!__imp_VariantClear` at `0x18000f7ba`
- `OLEAUT32!__imp_VariantClear` at `0x18000f7c8`
- `OLEAUT32!__imp_VariantClear` at `0x18000f80d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemNamespace::PublishInfo(
        CWbemNamespace *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _IWmiFinalizer *a4,
        struct IWbemContext *a5)
{
  int v9; // edi
  int v10; // ebx
  int v11; // edi
  LONG lVal; // edi
  signed __int32 v13; // esi
  int IsLocalMachine; // ebx
  HRESULT v15; // eax
  struct IErrorInfo *v16; // rdx
  HRESULT v17; // eax
  struct IErrorInfo *v18; // rdx
  HRESULT v20; // eax
  struct IErrorInfo *v21; // rdx
  CMemoryLog *v22; // rax
  HRESULT v23; // eax
  struct IErrorInfo *v24; // rdx
  HRESULT v25; // eax
  struct IErrorInfo *v26; // rdx
  CMemoryLog *v27; // rax
  HRESULT v28; // eax
  struct IErrorInfo *v29; // rdx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  unsigned __int16 *v38; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v39; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[8]; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v42)(__int64); // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+B0h] [rbp-50h]
  GUID rguid; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR sz[64]; // [rsp+D0h] [rbp-30h] BYREF

  v38 = 0;
  VariantInit(&pvarg);
  v9 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->GetValue)(
         a5,
         L"__CorrelationId",
         0,
         &pvarg);
  v10 = -2147217406;
  if ( v9 >= 0 )
    goto LABEL_2;
  if ( v9 == -2147217406 )
  {
    *(_QWORD *)&rguid.Data1 = 0;
    *(_QWORD *)rguid.Data4 = 0;
    EnsureGetActivityId(&rguid);
    if ( !StringFromGUID2(&rguid, sz, 64) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217406);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_69;
      }
      v32 = 937;
      v33 = 2147749890LL;
      goto LABEL_55;
    }
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(sz);
    v11 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->SetValue)(
            a5,
            L"__CorrelationId",
            0,
            &pvarg);
    if ( v11 < 0 )
    {
      v34 = GetMemLogObject();
      CMemoryLog::Write(v34, v11);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          938,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v11);
      }
LABEL_47:
      v10 = v11;
LABEL_69:
      _variant_t::~_variant_t(&pvarg);
      return (unsigned int)v10;
    }
LABEL_2:
    if ( pvarg.vt == 8 )
    {
      (*(void (__fastcall **)(struct _IWmiFinalizer *, LONGLONG))(*(_QWORD *)a4 + 128LL))(a4, pvarg.llVal);
      VariantInit(&v39);
      v11 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->GetValue)(
              a5,
              L"__GroupOperationId",
              0,
              &v39);
      if ( v11 >= 0 )
      {
        lVal = v39.lVal;
LABEL_5:
        v13 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_WMIOperation_Id, 1u);
        v10 = BuildOperationInfo(L"Start ", a2, *((const unsigned __int16 **)this + 12), a3, &v38);
        if ( v10 >= 0 )
        {
          MakeGuard<int (*)(void *),unsigned short *>(v41, CWin32DefaultArena::WbemMemFree, v38);
          IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
          (*(void (__fastcall **)(struct _IWmiFinalizer *, unsigned __int16 *))(*(_QWORD *)a4 + 136LL))(a4, v38);
          if ( *((_DWORD *)this + 76) != -1 )
          {
            (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)a4 + 120LL))(
              a4,
              (unsigned int)(v13 + 1));
            CPublishWMIOperationEvent::Publish(
              pvarg.bstrVal,
              lVal,
              v13 + 1,
              v38,
              *((unsigned __int16 **)this + 35),
              *((unsigned __int16 **)this + 36),
              *((unsigned __int16 **)this + 14),
              *((_DWORD *)this + 76),
              *((_QWORD *)this + 37),
              *((unsigned __int16 **)this + 11),
              IsLocalMachine);
          }
          if ( !v41[0] )
            v42(v43);
          v15 = VariantClear(&v39);
          if ( v15 < 0 )
            _com_issue_error(v15, v16);
          v17 = VariantClear(&pvarg);
          if ( v17 < 0 )
            _com_issue_error(v17, v18);
          return 0;
        }
        v37 = GetMemLogObject();
        CMemoryLog::Write(v37, v10);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            945,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v10);
        }
        _variant_t::~_variant_t(&v39);
        goto LABEL_69;
      }
      if ( v11 == -2147217406 )
      {
        lVal = _InterlockedIncrement((volatile signed __int32 *)&g_WMIOperation_Id);
        if ( v39.vt != 3 && v39.vt != 10 )
        {
          if ( v39.vt == 11 )
          {
            v39.iVal = -(lVal != 0);
LABEL_26:
            v10 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a5->lpVtbl->SetValue)(
                    a5,
                    L"__GroupOperationId",
                    0,
                    &v39);
            if ( v10 < 0 )
            {
              v22 = GetMemLogObject();
              CMemoryLog::Write(v22, v10);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  941,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  (unsigned int)v10);
              }
              v23 = VariantClear(&v39);
              if ( v23 < 0 )
                _com_issue_error(v23, v24);
              v25 = VariantClear(&pvarg);
              if ( v25 < 0 )
                _com_issue_error(v25, v26);
              return (unsigned int)v10;
            }
            goto LABEL_5;
          }
          v20 = VariantClear(&v39);
          if ( v20 < 0 )
            _com_issue_error(v20, v21);
          v39.vt = 3;
        }
        v39.lVal = lVal;
        goto LABEL_26;
      }
      v36 = GetMemLogObject();
      CMemoryLog::Write(v36, v11);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          942,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v11);
      }
      _variant_t::~_variant_t(&v39);
      goto LABEL_47;
    }
    v35 = GetMemLogObject();
    v10 = -2147217400;
    CMemoryLog::Write(v35, -2147217400);
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v32 = 940;
    v33 = 2147749896LL;
LABEL_55:
    WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v33);
    goto LABEL_69;
  }
  v27 = GetMemLogObject();
  CMemoryLog::Write(v27, v9);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      939,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)v9);
  }
  v28 = VariantClear(&pvarg);
  if ( v28 < 0 )
    _com_issue_error(v28, v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f474  push    rbp
0x18000f476  push    rbx
0x18000f477  push    rsi
0x18000f478  push    rdi
0x18000f479  push    r12
0x18000f47b  push    r13
0x18000f47d  push    r14
0x18000f47f  push    r15
0x18000f481  lea     rbp, [rsp-68h]
0x18000f486  sub     rsp, 168h
0x18000f48d  mov     rax, cs:__security_cookie
0x18000f494  xor     rax, rsp
0x18000f497  mov     [rbp+0A0h+var_50], rax
0x18000f49b  mov     r15, r9
0x18000f49e  mov     r13, r8
0x18000f4a1  mov     r12, rdx
0x18000f4a4  mov     r14, rcx
0x18000f4a7  mov     rsi, [rbp+0A0h+arg_20]
0x18000f4ae  mov     [rsp+1A0h+var_140], 0
0x18000f4b7  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18000f4bb  call    cs:__imp_VariantInit
0x18000f4c1  nop
0x18000f4c2  mov     rax, [rsi]
0x18000f4c5  lea     r9, [rbp+0A0h+pvarg]
0x18000f4c9  xor     r8d, r8d
0x18000f4cc  lea     rdx, aCorrelationid; "__CorrelationId"
0x18000f4d3  mov     rcx, rsi
0x18000f4d6  mov     rax, [rax+48h]
0x18000f4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4df  mov     edi, eax
0x18000f4e1  mov     ebx, 80041002h
0x18000f4e6  mov     eax, 8
0x18000f4eb  xor     ecx, ecx
0x18000f4ed  test    edi, edi
0x18000f4ef  js      loc_18000F69A
0x18000f4f5  cmp     word ptr [rbp+0A0h+pvarg], ax
0x18000f4f9  jnz     loc_18000F927
0x18000f4ff  mov     rax, [r15]
0x18000f502  mov     rdx, qword ptr [rbp+0A0h+pvarg+8]
0x18000f506  mov     rcx, r15
0x18000f509  mov     rax, [rax+80h]
0x18000f510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f515  lea     rcx, [rsp+1A0h+var_138]; pvarg
0x18000f51a  call    cs:__imp_VariantInit
0x18000f520  nop
0x18000f521  mov     rax, [rsi]
0x18000f524  lea     r9, [rsp+1A0h+var_138]
0x18000f529  xor     r8d, r8d
0x18000f52c  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18000f533  mov     rcx, rsi
0x18000f536  mov     rax, [rax+48h]
0x18000f53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f53f  mov     edi, eax
0x18000f541  test    eax, eax
0x18000f543  js      loc_18000F717
0x18000f549  mov     edi, dword ptr [rsp+1A0h+var_138+8]
0x18000f54d  mov     esi, 1
0x18000f552  lock xadd cs:?g_WMIOperation_Id@@3KA, esi; ulong g_WMIOperation_Id
0x18000f55a  lea     rax, [rsp+1A0h+var_140]
0x18000f55f  mov     [rsp+1A0h+var_180], rax
0x18000f564  mov     r9, r13
0x18000f567  mov     r8, [r14+60h]
0x18000f56b  mov     rdx, r12
0x18000f56e  lea     rcx, aStart; "Start "
0x18000f575  call    cs:__imp_?BuildOperationInfo@@YAJPEBG000PEAPEAG@Z; BuildOperationInfo(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18000f57b  mov     ebx, eax
0x18000f57d  test    eax, eax
0x18000f57f  js      loc_18000FA0B
0x18000f585  mov     r8, [rsp+1A0h+var_140]
0x18000f58a  mov     rdx, cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f591  lea     rcx, [rbp+0A0h+var_100]
0x18000f595  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x18000f59a  nop
0x18000f59b  mov     rcx, [r14+118h]; String2
0x18000f5a2  call    ?IsLocalMachine@CWbemNamespace@@KAHPEBG@Z; CWbemNamespace::IsLocalMachine(ushort const *)
0x18000f5a7  mov     ebx, eax
0x18000f5a9  mov     rcx, [r15]
0x18000f5ac  mov     rax, [rcx+88h]
0x18000f5b3  mov     rdx, [rsp+1A0h+var_140]
0x18000f5b8  mov     rcx, r15
0x18000f5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c0  cmp     dword ptr [r14+130h], 0FFFFFFFFh
0x18000f5c8  jz      short loc_18000F637
0x18000f5ca  mov     rdx, [r15]
0x18000f5cd  mov     rax, [rdx+78h]
0x18000f5d1  lea     edx, [rsi+1]
0x18000f5d4  mov     rcx, r15
0x18000f5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5dc  mov     [rsp+1A0h+var_150], ebx
0x18000f5e0  mov     rax, [r14+58h]
0x18000f5e4  mov     [rsp+1A0h+var_158], rax
0x18000f5e9  mov     rax, [r14+128h]
0x18000f5f0  mov     [rsp+1A0h+var_160], rax
0x18000f5f5  mov     eax, [r14+130h]
0x18000f5fc  mov     [rsp+1A0h+var_168], eax
0x18000f600  mov     rax, [r14+70h]
0x18000f604  mov     [rsp+1A0h+var_170], rax
0x18000f609  mov     rax, [r14+120h]
0x18000f610  mov     [rsp+1A0h+var_178], rax
0x18000f615  mov     rax, [r14+118h]
0x18000f61c  mov     [rsp+1A0h+var_180], rax
0x18000f621  mov     r9, [rsp+1A0h+var_140]
0x18000f626  lea     r8d, [rsi+1]
0x18000f62a  mov     edx, edi
0x18000f62c  mov     rcx, qword ptr [rbp+0A0h+pvarg+8]
0x18000f630  call    cs:__imp_?Publish@CPublishWMIOperationEvent@@SAJPEAGKK0000K_K0H@Z; CPublishWMIOperationEvent::Publish(ushort *,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ulong,unsigned __int64,ushort *,int)
0x18000f636  nop
0x18000f637  cmp     [rbp+0A0h+var_100], 0
0x18000f63b  jnz     short loc_18000F64B
0x18000f63d  mov     rcx, [rbp+0A0h+var_F0]
0x18000f641  mov     rax, [rbp+0A0h+var_F8]
0x18000f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64a  nop
0x18000f64b  lea     rcx, [rsp+1A0h+var_138]; pvarg
0x18000f650  call    cs:__imp_VariantClear
0x18000f656  test    eax, eax
0x18000f658  js      short loc_18000F68A
0x18000f65a  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18000f65e  call    cs:__imp_VariantClear
0x18000f664  test    eax, eax
0x18000f666  js      short loc_18000F692
0x18000f668  xor     eax, eax
0x18000f66a  mov     rcx, [rbp+0A0h+var_50]
0x18000f66e  xor     rcx, rsp; StackCookie
0x18000f671  call    __security_check_cookie
0x18000f676  add     rsp, 168h
0x18000f67d  pop     r15
0x18000f67f  pop     r14
0x18000f681  pop     r13
0x18000f683  pop     r12
0x18000f685  pop     rdi
0x18000f686  pop     rsi
0x18000f687  pop     rbx
0x18000f688  pop     rbp
0x18000f689  retn
0x18000f68a  mov     ecx, eax; int
0x18000f68c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f692  mov     ecx, eax; int
0x18000f694  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f69a  cmp     edi, ebx
0x18000f69c  jnz     loc_18000F7E1
0x18000f6a2  mov     qword ptr [rbp+0A0h+rguid.Data1], rcx
0x18000f6a6  mov     qword ptr [rbp+0A0h+rguid.Data4], rcx
0x18000f6aa  lea     rcx, [rbp+0A0h+rguid]; ActivityId
0x18000f6ae  call    ?EnsureGetActivityId@@YAXPEAU_GUID@@@Z; EnsureGetActivityId(_GUID *)
0x18000f6b3  mov     r8d, 40h ; '@'; cchMax
0x18000f6b9  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18000f6bd  lea     rcx, [rbp+0A0h+rguid]; rguid
0x18000f6c1  call    cs:__imp_StringFromGUID2
0x18000f6c7  test    eax, eax
0x18000f6c9  jz      loc_18000F836
0x18000f6cf  mov     eax, 8
0x18000f6d4  mov     word ptr [rbp+0A0h+pvarg], ax
0x18000f6d8  lea     rcx, [rbp+0A0h+sz]; psz
0x18000f6dc  call    cs:__imp_SysAllocString
0x18000f6e2  mov     qword ptr [rbp+0A0h+pvarg+8], rax
0x18000f6e6  mov     rax, [rsi]
0x18000f6e9  lea     r9, [rbp+0A0h+pvarg]
0x18000f6ed  xor     r8d, r8d
0x18000f6f0  lea     rdx, aCorrelationid; "__CorrelationId"
0x18000f6f7  mov     rcx, rsi
0x18000f6fa  mov     rax, [rax+40h]
0x18000f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f703  mov     edi, eax
0x18000f705  test    eax, eax
0x18000f707  js      loc_18000F882
0x18000f70d  mov     eax, 8
0x18000f712  jmp     loc_18000F4F5
0x18000f717  cmp     edi, ebx
0x18000f719  jnz     loc_18000F9CA
0x18000f71f  mov     edi, 1
0x18000f724  lock xadd cs:?g_WMIOperation_Id@@3KA, edi; ulong g_WMIOperation_Id
0x18000f72c  inc     edi
0x18000f72e  movzx   eax, word ptr [rsp+1A0h+var_138]
0x18000f733  mov     ebx, 3
0x18000f738  cmp     ax, bx
0x18000f73b  jz      short loc_18000F761
0x18000f73d  cmp     ax, 0Ah
0x18000f741  jz      short loc_18000F761
0x18000f743  cmp     ax, 0Bh
0x18000f747  jz      loc_18000F988
0x18000f74d  lea     rcx, [rsp+1A0h+var_138]; pvarg
0x18000f752  call    cs:__imp_VariantClear
0x18000f758  test    eax, eax
0x18000f75a  js      short loc_18000F7D9
0x18000f75c  mov     word ptr [rsp+1A0h+var_138], bx
0x18000f761  mov     dword ptr [rsp+1A0h+var_138+8], edi
0x18000f765  mov     rax, [rsi]
0x18000f768  lea     r9, [rsp+1A0h+var_138]
0x18000f76d  xor     r8d, r8d
0x18000f770  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18000f777  mov     rcx, rsi
0x18000f77a  mov     rax, [rax+40h]
0x18000f77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f783  mov     ebx, eax
0x18000f785  test    eax, eax
0x18000f787  jns     loc_18000F54D
0x18000f78d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f793  mov     edx, ebx
0x18000f795  mov     rcx, rax
0x18000f798  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f79e  lea     rax, WPP_GLOBAL_Control
0x18000f7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7ac  cmp     rcx, rax
0x18000f7af  jnz     loc_18000F999
0x18000f7b5  lea     rcx, [rsp+1A0h+var_138]; pvarg
0x18000f7ba  call    cs:__imp_VariantClear
0x18000f7c0  test    eax, eax
0x18000f7c2  js      short loc_18000F826
0x18000f7c4  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18000f7c8  call    cs:__imp_VariantClear
0x18000f7ce  test    eax, eax
0x18000f7d0  js      short loc_18000F82E
0x18000f7d2  mov     eax, ebx
0x18000f7d4  jmp     loc_18000F66A
0x18000f7d9  mov     ecx, eax; int
0x18000f7db  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f7e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f7e7  mov     edx, edi
0x18000f7e9  mov     rcx, rax
0x18000f7ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f7f2  lea     rax, WPP_GLOBAL_Control
0x18000f7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f800  cmp     rcx, rax
0x18000f803  jnz     loc_18000F8F6
0x18000f809  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18000f80d  call    cs:__imp_VariantClear
0x18000f813  test    eax, eax
0x18000f815  js      short loc_18000F81E
0x18000f817  mov     eax, edi
0x18000f819  jmp     loc_18000F66A
0x18000f81e  mov     ecx, eax; int
0x18000f820  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f826  mov     ecx, eax; int
0x18000f828  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f82e  mov     ecx, eax; int
0x18000f830  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f836  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f83c  mov     edx, ebx
0x18000f83e  mov     rcx, rax
0x18000f841  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f847  lea     rax, WPP_GLOBAL_Control
0x18000f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f855  cmp     rcx, rax
0x18000f858  jz      loc_18000FA5F
0x18000f85e  test    byte ptr [rcx+1Ch], 1
0x18000f862  jz      loc_18000FA5F
0x18000f868  cmp     byte ptr [rcx+19h], 2
0x18000f86c  jb      loc_18000FA5F
0x18000f872  mov     edx, 3A9h
0x18000f877  mov     r9d, 80041002h
0x18000f87d  jmp     loc_18000F973
0x18000f882  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f888  mov     edx, edi
0x18000f88a  mov     rcx, rax
0x18000f88d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f893  lea     rax, WPP_GLOBAL_Control
0x18000f89a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8a1  cmp     rcx, rax
0x18000f8a4  jz      short loc_18000F8EF
0x18000f8a6  test    byte ptr [rcx+1Ch], 1
0x18000f8aa  jz      short loc_18000F8EF
0x18000f8ac  cmp     byte ptr [rcx+19h], 2
0x18000f8b0  jb      short loc_18000F8EF
0x18000f8b2  mov     edx, 3AAh
0x18000f8b7  mov     r9d, edi
0x18000f8ba  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18000f8c1  mov     rcx, [rcx+10h]
0x18000f8c5  call    WPP_SF_d
0x18000f8ca  jmp     short loc_18000F8EF
0x18000f8cc  mov     edx, 3AEh
0x18000f8d1  mov     r9d, edi
0x18000f8d4  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18000f8db  mov     rcx, [rcx+10h]
0x18000f8df  call    WPP_SF_d
0x18000f8e4  nop
0x18000f8e5  lea     rcx, [rsp+1A0h+var_138]; this
0x18000f8ea  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f8ef  mov     ebx, edi
0x18000f8f1  jmp     loc_18000FA5F
0x18000f8f6  test    byte ptr [rcx+1Ch], 1
0x18000f8fa  jz      loc_18000F809
0x18000f900  cmp     byte ptr [rcx+19h], 2
0x18000f904  jb      loc_18000F809
0x18000f90a  mov     edx, 3ABh
0x18000f90f  mov     r9d, edi
0x18000f912  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18000f919  mov     rcx, [rcx+10h]
0x18000f91d  call    WPP_SF_d
0x18000f922  jmp     loc_18000F809
0x18000f927  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f92d  mov     ebx, 80041008h
0x18000f932  mov     edx, ebx
0x18000f934  mov     rcx, rax
0x18000f937  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f93d  lea     rax, WPP_GLOBAL_Control
0x18000f944  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f94b  cmp     rcx, rax
0x18000f94e  jz      loc_18000FA5F
0x18000f954  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
