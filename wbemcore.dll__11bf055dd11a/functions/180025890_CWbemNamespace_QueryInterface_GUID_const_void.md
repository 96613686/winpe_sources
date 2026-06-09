# CWbemNamespace::QueryInterface(_GUID const &,void * *)

- ea: `0x180025890`
- end: `0x180025d8f`
- name: `?QueryInterface@CWbemNamespace@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1279`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnkOuter, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009fc50`
- `0x18009fc60`
- `0x1800be2d0`

## callees

- `0x18000b140`
- `0x180025890`
- `0x180027920`
- `0x18003cfe0`
- `0x180086c70`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002598a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002598a`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025ac5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025b4b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025b98`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025c07`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025c3f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025d81`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025ac5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025b4b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025b98`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025c07`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025c3f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180025d81`
- `wbemcomn!GetMemLogObject` at `0x180025af3`
- `wbemcomn!GetMemLogObject` at `0x180025b5b`
- `wbemcomn!GetMemLogObject` at `0x180025ba5`
- `wbemcomn!GetMemLogObject` at `0x180025c17`
- `wbemcomn!GetMemLogObject` at `0x180025d0b`
- `wbemcomn!GetMemLogObject` at `0x180025af3`
- `wbemcomn!GetMemLogObject` at `0x180025b5b`
- `wbemcomn!GetMemLogObject` at `0x180025ba5`
- `wbemcomn!GetMemLogObject` at `0x180025c17`
- `wbemcomn!GetMemLogObject` at `0x180025d0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025b01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025b66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025bb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025c22`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025d17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025b01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025b66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025bb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025c22`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025d17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800259c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800259c3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025a17`
- `OLEAUT32!__imp_SysAllocString` at `0x180025a31`
- `OLEAUT32!__imp_SysAllocString` at `0x180025a17`
- `OLEAUT32!__imp_SysAllocString` at `0x180025a31`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a84`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d58`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d62`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a84`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d58`
- `OLEAUT32!__imp_SysFreeString` at `0x180025d62`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemNamespace::QueryInterface(LPUNKNOWN pUnkOuter, const struct _GUID *a2, LPUNKNOWN *a3)
{
  __int64 v5; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  LPUNKNOWN v11; // rcx
  HRESULT v12; // ebx
  LPVOID v13; // r12
  int v14; // ebx
  __int64 v15; // rbx
  const OLECHAR *MachineName; // rax
  BSTR v17; // rax
  OLECHAR *v18; // r14
  BSTR v19; // rax
  OLECHAR *v20; // r15
  int v21; // r12d
  unsigned int v22; // ebx
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v27; // rax
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v29[3]; // [rsp+38h] [rbp-28h] BYREF
  LPVOID v30; // [rsp+50h] [rbp-10h] BYREF
  char v31; // [rsp+58h] [rbp-8h]
  char v32; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 0;
  v5 = *(_QWORD *)&IID_IUnknown.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 )
    v5 = *(_QWORD *)IID_IUnknown.Data4 - *(_QWORD *)a2->Data4;
  if ( !v5 )
    goto LABEL_4;
  v7 = *(_QWORD *)&IID_IWbemServices.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IWbemServices.Data1 == *(_QWORD *)&a2->Data1 )
    v7 = *(_QWORD *)IID_IWbemServices.Data4 - *(_QWORD *)a2->Data4;
  if ( !v7 )
  {
LABEL_4:
    *a3 = pUnkOuter;
    _InterlockedIncrement((volatile signed __int32 *)&pUnkOuter[3]);
    return 0;
  }
  v8 = *(_QWORD *)&IID_IWbemRefreshingServices.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IWbemRefreshingServices.Data1 == *(_QWORD *)&a2->Data1 )
    v8 = *(_QWORD *)IID_IWbemRefreshingServices.Data4 - *(_QWORD *)a2->Data4;
  if ( !v8 )
  {
    CInCritSec::CInCritSec((CInCritSec *)&v32, (struct _RTL_CRITICAL_SECTION *)&pUnkOuter[17]);
    if ( pUnkOuter[34].lpVtbl )
      goto LABEL_30;
    ppv = 0;
    v12 = CoCreateInstance(&CLSID__WbemConfigureRefreshingSvcs, pUnkOuter, 1u, &IID_IUnknown, &ppv);
    if ( v12 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v12);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v12);
      }
      CInCritSec::~CInCritSec((CInCritSec *)&v32);
      return (unsigned int)v12;
    }
    v13 = ppv;
    v30 = ppv;
    v31 = 0;
    v29[0] = 0;
    v14 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &IID__IWbemConfigureRefreshingSvcs, v29);
    if ( v14 < 0 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, v14);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v14);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      CInCritSec::~CInCritSec((CInCritSec *)&v32);
      return (unsigned int)v14;
    }
    v15 = v29[0];
    v28 = v29[0];
    MachineName = ConfigMgr::GetMachineName();
    v17 = SysAllocString(MachineName);
    v18 = v17;
    if ( v17 )
    {
      v29[1] = v17;
      v19 = SysAllocString((const OLECHAR *)pUnkOuter[12].lpVtbl);
      v20 = v19;
      if ( v19 )
      {
        v29[2] = v19;
        v21 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, BSTR))(*(_QWORD *)v29[0] + 24LL))(v29[0], v18, v19);
        if ( v21 < 0 )
        {
          v27 = GetMemLogObject();
          CMemoryLog::Write(v27, v21);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)v21);
          }
          SysFreeString(v20);
          SysFreeString(v18);
          CReleaseMe::release((CReleaseMe *)&v28);
          OnDeleteIf<IUnknown *,void (*)(IUnknown *),&void RM(IUnknown *)>::~OnDeleteIf<IUnknown *,void (*)(IUnknown *),&void RM(IUnknown *)>(&v30);
          CInCritSec::~CInCritSec((CInCritSec *)&v32);
          return (unsigned int)v21;
        }
        pUnkOuter[34].lpVtbl = (struct IUnknownVtbl *)ppv;
        v31 = 1;
        SysFreeString(v20);
        SysFreeString(v18);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v28 = 0;
LABEL_30:
        v22 = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, LPUNKNOWN *))pUnkOuter[34].lpVtbl->QueryInterface)(
                pUnkOuter[34].lpVtbl,
                &IID_IWbemRefreshingServices,
                a3);
        CInCritSec::~CInCritSec((CInCritSec *)&v32);
        return v22;
      }
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      }
      SysFreeString(v18);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    else
    {
      v23 = GetMemLogObject();
      CMemoryLog::Write(v23, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v28 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    CInCritSec::~CInCritSec((CInCritSec *)&v32);
    return 2147749894LL;
  }
  v9 = *(_QWORD *)&IID_IWbemInternalServices.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IWbemInternalServices.Data1 == *(_QWORD *)&a2->Data1 )
    v9 = *(_QWORD *)IID_IWbemInternalServices.Data4 - *(_QWORD *)a2->Data4;
  if ( !v9 )
  {
    v11 = pUnkOuter + 1;
    if ( !pUnkOuter )
      v11 = 0;
    goto LABEL_20;
  }
  v10 = *(_QWORD *)&IID_IClientOperations.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IClientOperations.Data1 == *(_QWORD *)&a2->Data1 )
    v10 = *(_QWORD *)IID_IClientOperations.Data4 - *(_QWORD *)a2->Data4;
  if ( !v10 )
  {
    v11 = pUnkOuter + 2;
    if ( !pUnkOuter )
      v11 = 0;
LABEL_20:
    *a3 = v11;
    _InterlockedIncrement((volatile signed __int32 *)&pUnkOuter[3]);
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180025890  mov     [rsp-38h+arg_0], rbx
0x180025895  push    rbp
0x180025896  push    rsi
0x180025897  push    rdi
0x180025898  push    r12
0x18002589a  push    r13
0x18002589c  push    r14
0x18002589e  push    r15
0x1800258a0  mov     rbp, rsp
0x1800258a3  sub     rsp, 60h
0x1800258a7  mov     rsi, r8
0x1800258aa  mov     rdi, rcx
0x1800258ad  xor     r13d, r13d
0x1800258b0  mov     [r8], r13
0x1800258b3  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x1800258ba  sub     rax, [rdx]
0x1800258bd  jnz     short loc_1800258CA
0x1800258bf  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x1800258c6  sub     rax, [rdx+8]
0x1800258ca  test    rax, rax
0x1800258cd  jnz     short loc_1800258F0
0x1800258cf  mov     [r8], rdi
0x1800258d2  lock inc dword ptr [rcx+18h]
0x1800258d6  xor     eax, eax
0x1800258d8  mov     rbx, [rsp+60h+arg_0]
0x1800258e0  add     rsp, 60h
0x1800258e4  pop     r15
0x1800258e6  pop     r14
0x1800258e8  pop     r13
0x1800258ea  pop     r12
0x1800258ec  pop     rdi
0x1800258ed  pop     rsi
0x1800258ee  pop     rbp
0x1800258ef  retn
0x1800258f0  mov     rax, qword ptr cs:IID_IWbemServices.Data1
0x1800258f7  sub     rax, [rdx]
0x1800258fa  jnz     short loc_180025907
0x1800258fc  mov     rax, qword ptr cs:IID_IWbemServices.Data4
0x180025903  sub     rax, [rdx+8]
0x180025907  test    rax, rax
0x18002590a  jz      short loc_1800258CF
0x18002590c  mov     rax, qword ptr cs:IID_IWbemRefreshingServices.Data1
0x180025913  sub     rax, [rdx]
0x180025916  jnz     short loc_180025923
0x180025918  mov     rax, qword ptr cs:IID_IWbemRefreshingServices.Data4
0x18002591f  sub     rax, [rdx+8]
0x180025923  test    rax, rax
0x180025926  jz      short loc_18002597F
0x180025928  mov     rax, qword ptr cs:IID_IWbemInternalServices.Data1
0x18002592f  sub     rax, [rdx]
0x180025932  jnz     short loc_18002593F
0x180025934  mov     rax, qword ptr cs:IID_IWbemInternalServices.Data4
0x18002593b  sub     rax, [rdx+8]
0x18002593f  test    rax, rax
0x180025942  jz      loc_180025AD2
0x180025948  mov     rax, qword ptr cs:IID_IClientOperations.Data1
0x18002594f  sub     rax, [rdx]
0x180025952  jnz     short loc_18002595F
0x180025954  mov     rax, qword ptr cs:IID_IClientOperations.Data4
0x18002595b  sub     rax, [rdx+8]
0x18002595f  test    rax, rax
0x180025962  jnz     loc_180025AE9
0x180025968  add     rcx, 10h
0x18002596c  test    rdi, rdi
0x18002596f  cmovz   rcx, r13
0x180025973  mov     [r8], rcx
0x180025976  lock inc dword ptr [rdi+18h]
0x18002597a  jmp     loc_1800258D6
0x18002597f  lea     rdx, [rcx+88h]
0x180025986  lea     rcx, [rbp+arg_10]
0x18002598a  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180025990  nop
0x180025991  cmp     qword ptr [rdi+110h], 0
0x180025999  jnz     loc_180025AA3
0x18002599f  mov     [rbp+arg_18], r13
0x1800259a3  lea     rax, [rbp+arg_18]
0x1800259a7  mov     [rsp+60h+ppv], rax; ppv
0x1800259ac  lea     r9, IID_IUnknown; riid
0x1800259b3  mov     r8d, 1; dwClsContext
0x1800259b9  mov     rdx, rdi; pUnkOuter
0x1800259bc  lea     rcx, CLSID__WbemConfigureRefreshingSvcs; rclsid
0x1800259c3  call    cs:__imp_CoCreateInstance
0x1800259c9  mov     ebx, eax
0x1800259cb  test    eax, eax
0x1800259cd  js      loc_180025C17
0x1800259d3  mov     r12, [rbp+arg_18]
0x1800259d7  mov     [rbp+var_10], r12
0x1800259db  mov     [rbp+var_8], 0
0x1800259df  mov     [rbp+var_28], r13
0x1800259e3  mov     rcx, [rbp+arg_18]
0x1800259e7  mov     rax, [rcx]
0x1800259ea  lea     r8, [rbp+var_28]
0x1800259ee  lea     rdx, IID__IWbemConfigureRefreshingSvcs
0x1800259f5  mov     rax, [rax]
0x1800259f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259fd  mov     ebx, eax
0x1800259ff  test    eax, eax
0x180025a01  js      loc_180025B5B
0x180025a07  mov     rbx, [rbp+var_28]
0x180025a0b  mov     [rbp+var_30], rbx
0x180025a0f  call    ?GetMachineName@ConfigMgr@@SAPEAGXZ; ConfigMgr::GetMachineName(void)
0x180025a14  mov     rcx, rax; psz
0x180025a17  call    cs:__imp_SysAllocString
0x180025a1d  mov     r14, rax
0x180025a20  test    rax, rax
0x180025a23  jz      loc_180025AF3
0x180025a29  mov     [rbp+var_20], rax
0x180025a2d  mov     rcx, [rdi+60h]; psz
0x180025a31  call    cs:__imp_SysAllocString
0x180025a37  mov     r15, rax
0x180025a3a  test    rax, rax
0x180025a3d  jz      loc_180025BA5
0x180025a43  mov     [rbp+var_18], rax
0x180025a47  mov     rcx, [rbp+var_28]
0x180025a4b  mov     rax, [rcx]
0x180025a4e  mov     r8, r15
0x180025a51  mov     rdx, r14
0x180025a54  mov     rax, [rax+18h]
0x180025a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a5d  mov     r12d, eax
0x180025a60  test    eax, eax
0x180025a62  js      loc_180025D0B
0x180025a68  mov     rax, [rbp+arg_18]
0x180025a6c  mov     [rdi+110h], rax
0x180025a73  mov     [rbp+var_8], 1
0x180025a77  mov     rcx, r15; bstrString
0x180025a7a  call    cs:__imp_SysFreeString
0x180025a80  nop
0x180025a81  mov     rcx, r14; bstrString
0x180025a84  call    cs:__imp_SysFreeString
0x180025a8a  nop
0x180025a8b  test    rbx, rbx
0x180025a8e  jz      short loc_180025A9F
0x180025a90  mov     rax, [rbx]
0x180025a93  mov     rcx, rbx
0x180025a96  mov     rax, [rax+10h]
0x180025a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a9f  mov     [rbp+var_30], r13
0x180025aa3  mov     rcx, [rdi+110h]
0x180025aaa  mov     rax, [rcx]
0x180025aad  mov     r8, rsi
0x180025ab0  lea     rdx, IID_IWbemRefreshingServices
0x180025ab7  mov     rax, [rax]
0x180025aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025abf  mov     ebx, eax
0x180025ac1  lea     rcx, [rbp+arg_10]
0x180025ac5  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180025acb  mov     eax, ebx
0x180025acd  jmp     loc_1800258D8
0x180025ad2  add     rcx, 8
0x180025ad6  test    rdi, rdi
0x180025ad9  cmovz   rcx, r13
0x180025add  mov     [r8], rcx
0x180025ae0  lock inc dword ptr [rdi+18h]
0x180025ae4  jmp     loc_1800258D6
0x180025ae9  mov     eax, 80004002h
0x180025aee  jmp     loc_1800258D8
0x180025af3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025af9  mov     edx, 80041006h
0x180025afe  mov     rcx, rax
0x180025b01  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025b07  lea     rax, WPP_GLOBAL_Control
0x180025b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b15  cmp     rcx, rax
0x180025b18  jnz     loc_180025CA3
0x180025b1e  test    rbx, rbx
0x180025b21  jz      short loc_180025B32
0x180025b23  mov     rax, [rbx]
0x180025b26  mov     rcx, rbx
0x180025b29  mov     rax, [rax+10h]
0x180025b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b32  mov     [rbp+var_30], r13
0x180025b36  mov     rcx, [r12]
0x180025b3a  mov     rax, [rcx+10h]
0x180025b3e  mov     rcx, r12
0x180025b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b46  nop
0x180025b47  lea     rcx, [rbp+arg_10]
0x180025b4b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180025b51  mov     eax, 80041006h
0x180025b56  jmp     loc_1800258D8
0x180025b5b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025b61  mov     edx, ebx
0x180025b63  mov     rcx, rax
0x180025b66  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025b6c  lea     rax, WPP_GLOBAL_Control
0x180025b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b7a  cmp     rcx, rax
0x180025b7d  jnz     loc_180025C72
0x180025b83  mov     rax, [r12]
0x180025b87  mov     rcx, r12
0x180025b8a  mov     rax, [rax+10h]
0x180025b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b93  nop
0x180025b94  lea     rcx, [rbp+arg_10]
0x180025b98  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180025b9e  mov     eax, ebx
0x180025ba0  jmp     loc_1800258D8
0x180025ba5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025bab  mov     edx, 80041006h
0x180025bb0  mov     rcx, rax
0x180025bb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025bb9  lea     rax, WPP_GLOBAL_Control
0x180025bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bc7  cmp     rcx, rax
0x180025bca  jnz     loc_180025CD7
0x180025bd0  mov     rcx, r14; bstrString
0x180025bd3  call    cs:__imp_SysFreeString
0x180025bd9  nop
0x180025bda  test    rbx, rbx
0x180025bdd  jz      short loc_180025BEE
0x180025bdf  mov     rax, [rbx]
0x180025be2  mov     rcx, rbx
0x180025be5  mov     rax, [rax+10h]
0x180025be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bee  mov     [rbp+var_30], r13
0x180025bf2  mov     rax, [r12]
0x180025bf6  mov     rcx, r12
0x180025bf9  mov     rax, [rax+10h]
0x180025bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c02  nop
0x180025c03  lea     rcx, [rbp+arg_10]
0x180025c07  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180025c0d  mov     eax, 80041006h
0x180025c12  jmp     loc_1800258D8
0x180025c17  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025c1d  mov     edx, ebx
0x180025c1f  mov     rcx, rax
0x180025c22  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025c28  lea     rax, WPP_GLOBAL_Control
0x180025c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c36  cmp     rcx, rax
0x180025c39  jnz     short loc_180025C4C
0x180025c3b  lea     rcx, [rbp+arg_10]
0x180025c3f  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180025c45  mov     eax, ebx
0x180025c47  jmp     loc_1800258D8
0x180025c4c  test    byte ptr [rcx+1Ch], 1
0x180025c50  jz      short loc_180025C3B
0x180025c52  cmp     byte ptr [rcx+19h], 2
0x180025c56  jb      short loc_180025C3B
0x180025c58  mov     edx, 2Ch ; ','
0x180025c5d  mov     r9d, ebx
0x180025c60  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180025c67  mov     rcx, [rcx+10h]
0x180025c6b  call    WPP_SF_d
0x180025c70  jmp     short loc_180025C3B
0x180025c72  test    byte ptr [rcx+1Ch], 1
0x180025c76  jz      loc_180025B83
0x180025c7c  cmp     byte ptr [rcx+19h], 2
0x180025c80  jb      loc_180025B83
0x180025c86  mov     edx, 2Dh ; '-'
0x180025c8b  mov     r9d, ebx
0x180025c8e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180025c95  mov     rcx, [rcx+10h]
0x180025c99  call    WPP_SF_d
0x180025c9e  jmp     loc_180025B83
0x180025ca3  test    byte ptr [rcx+1Ch], 1
0x180025ca7  jz      loc_180025B1E
0x180025cad  cmp     byte ptr [rcx+19h], 2
0x180025cb1  jb      loc_180025B1E
0x180025cb7  mov     edx, 2Eh ; '.'
0x180025cbc  mov     r9d, 80041006h
0x180025cc2  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180025cc9  mov     rcx, [rcx+10h]
0x180025ccd  call    WPP_SF_d
0x180025cd2  jmp     loc_180025B1E
0x180025cd7  test    byte ptr [rcx+1Ch], 1
0x180025cdb  jz      loc_180025BD0
0x180025ce1  cmp     byte ptr [rcx+19h], 2
0x180025ce5  jb      loc_180025BD0
0x180025ceb  mov     edx, 2Fh ; '/'
0x180025cf0  mov     r9d, 80041006h
0x180025cf6  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180025cfd  mov     rcx, [rcx+10h]
0x180025d01  call    WPP_SF_d
0x180025d06  jmp     loc_180025BD0
0x180025d0b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025d11  mov     edx, r12d
0x180025d14  mov     rcx, rax
0x180025d17  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025d1d  lea     rax, WPP_GLOBAL_Control
0x180025d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d2b  cmp     rcx, rax
0x180025d2e  jz      short loc_180025D55
0x180025d30  test    byte ptr [rcx+1Ch], 1
0x180025d34  jz      short loc_180025D55
0x180025d36  cmp     byte ptr [rcx+19h], 2
0x180025d3a  jb      short loc_180025D55
0x180025d3c  mov     edx, 30h ; '0'
0x180025d41  mov     r9d, r12d
0x180025d44  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180025d4b  mov     rcx, [rcx+10h]
0x180025d4f  call    WPP_SF_d
0x180025d54  nop
0x180025d55  mov     rcx, r15; bstrString
0x180025d58  call    cs:__imp_SysFreeString
0x180025d5e  nop
0x180025d5f  mov     rcx, r14; bstrString
0x180025d62  call    cs:__imp_SysFreeString
  ... truncated ...
```
