# CWbemNamespace::DynAux_GetInstances(CWbemObject *,long,IWbemContext *,CBasicObjectSink *,int)

- ea: `0x180040b74`
- end: `0x180041189`
- name: `?DynAux_GetInstances@CWbemNamespace@@QEAAJPEAVCWbemObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@H@Z`
- size: `1557`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct CWbemObject *, int, struct IWbemContext *, struct IWbemObjectSinkEx *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800406a0`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x18003cfe0`
- `0x180040b74`
- `0x180041640`
- `0x1800416a8`
- `0x1800421ac`
- `0x18007e310`
- `0x18007eb10`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040bc4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180040bc4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180040eb0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180040eb0`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180040c0d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180040cbd`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180040c0d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180040cbd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180040c73`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180040d10`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180040c73`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180040d10`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040c19`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040c5b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040cce`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040e36`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040c19`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040c5b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040cce`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180040e36`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180040c28`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180040cdf`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180040c28`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180040cdf`
- `wbemcomn!GetMemLogObject` at `0x180040e49`
- `wbemcomn!GetMemLogObject` at `0x180040f9d`
- `wbemcomn!GetMemLogObject` at `0x180040fef`
- `wbemcomn!GetMemLogObject` at `0x180041043`
- `wbemcomn!GetMemLogObject` at `0x1800410c4`
- `wbemcomn!GetMemLogObject` at `0x18004114a`
- `wbemcomn!GetMemLogObject` at `0x180040e49`
- `wbemcomn!GetMemLogObject` at `0x180040f9d`
- `wbemcomn!GetMemLogObject` at `0x180040fef`
- `wbemcomn!GetMemLogObject` at `0x180041043`
- `wbemcomn!GetMemLogObject` at `0x1800410c4`
- `wbemcomn!GetMemLogObject` at `0x18004114a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040e54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040fad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040ffa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004104e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041156`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040e54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040fad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040ffa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004104e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041156`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemNamespace::DynAux_GetInstances(
        CWbemNamespace *this,
        struct CWbemObject *a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSinkEx *a5)
{
  _QWORD *Value; // rax
  __int64 v6; // r14
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // r12
  signed int i; // esi
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // ebx
  unsigned int v14; // edi
  CWmiMerger *v15; // r15
  int v16; // edi
  unsigned int v17; // r13d
  __int64 v18; // r15
  __int64 (__fastcall ***v19)(_QWORD, GUID *, CWmiMerger **); // rcx
  CMemoryLog *MemLogObject; // rax
  CWmiMerger *v22; // rax
  CAsyncReq_DynAux_GetInstances *Instances; // rdi
  int v24; // r14d
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  int v30; // [rsp+30h] [rbp-51h]
  __int64 v31; // [rsp+48h] [rbp-39h] BYREF
  CWmiMerger *v32; // [rsp+50h] [rbp-31h] BYREF
  __int64 v33; // [rsp+58h] [rbp-29h] BYREF
  __int64 v34; // [rsp+60h] [rbp-21h] BYREF
  char v35[8]; // [rsp+68h] [rbp-19h] BYREF
  char v36[8]; // [rsp+70h] [rbp-11h] BYREF
  CWmiMerger *v37; // [rsp+78h] [rbp-9h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  Value = TlsGetValue(g_QueueTlsIndex);
  if ( !Value || (v6 = Value[1]) == 0 )
  {
    v7 = 0;
    v8 = 0;
    v31 = 0;
    v9 = 272;
    v33 = 184;
    goto LABEL_38;
  }
  v7 = *(_QWORD *)(v6 + 32);
  v8 = 0;
  v31 = 0;
  v9 = v7 + 272;
  v10 = v7 + 184;
  if ( !v7 )
  {
    v33 = 184;
LABEL_38:
    v10 = 184;
    goto LABEL_13;
  }
  CInCritSec::CInCritSec((CInCritSec *)v35, (struct _RTL_CRITICAL_SECTION *)(v7 + 272));
  for ( i = 0; i < CFlexArray::Size((CFlexArray *)(v7 + 184)); ++i )
  {
    v12 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))CFlexArray::operator[](v7 + 184, (unsigned int)i);
    if ( v12 && (**v12)(v12, &IID__IWmiFinalizer, &v31) >= 0 )
      break;
  }
  v13 = CFlexArray::Size((CFlexArray *)(v7 + 184));
  v14 = 0;
  if ( i >= v13 )
    v14 = -2147217406;
  CInCritSec::~CInCritSec((CInCritSec *)v35);
  if ( i >= v13 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v14);
    }
    return v14;
  }
  v33 = v7 + 184;
  v8 = v31;
LABEL_13:
  v34 = v8;
  v15 = 0;
  v37 = 0;
  if ( (unsigned int)ConfigMgr::GetEnableQueryArbitration() && v7 )
  {
    v32 = 0;
    v16 = -2147467262;
    CInCritSec::CInCritSec((CInCritSec *)v36, (struct _RTL_CRITICAL_SECTION *)v9);
    v17 = 0;
    v18 = v33;
    do
    {
      if ( (signed int)v17 >= CFlexArray::Size((CFlexArray *)v10) )
        break;
      v19 = *(__int64 (__fastcall ****)(_QWORD, GUID *, CWmiMerger **))CFlexArray::operator[](v18, v17);
      if ( v19 )
        v16 = (**v19)(v19, &IID__IWmiArbitratedQuery, &v32);
      ++v17;
    }
    while ( v16 < 0 );
    CInCritSec::~CInCritSec((CInCritSec *)v36);
    v15 = v37;
    if ( v16 < 0 )
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, v16);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids,
        (unsigned int)v16);
    }
    if ( v16 >= 0 )
    {
      if ( (*(int (__fastcall **)(CWmiMerger *))(*(_QWORD *)v32 + 24LL))(v32) < 0 )
      {
        (*(void (__fastcall **)(CWmiMerger *))(*(_QWORD *)v32 + 16LL))(v32);
      }
      else
      {
        v15 = v32;
        if ( v32 )
          v15 = (CWmiMerger *)((char *)v32 - 8);
      }
    }
  }
  v33 = (__int64)v15;
  if ( v15 )
  {
    v14 = CWmiMerger::RegisterArbitratedInstRequest(v15, a2, a3, a4, a5, v30, this);
    if ( (v14 & 0x80000000) != 0 )
    {
      if ( v31 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 112LL))(v31, 0);
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, v14);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 358, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v14);
    }
    (*(void (__fastcall **)(CWmiMerger *))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_33:
    v33 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_35:
    v34 = 0;
    return v14;
  }
  v22 = (CWmiMerger *)CWin32DefaultArena::WbemMemAlloc(0x80u);
  v37 = v22;
  if ( v22 )
    Instances = CAsyncReq_DynAux_GetInstances::CAsyncReq_DynAux_GetInstances(v22, this, a2, a3, a4, a5);
  else
    Instances = 0;
  if ( !Instances )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 112LL))(v31, 0);
    v25 = GetMemLogObject();
    v14 = -2147217402;
    CMemoryLog::Write(v25, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 359, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    goto LABEL_33;
  }
  if ( *((_QWORD *)Instances + 5) )
  {
    *((_QWORD *)Instances + 4) = v7;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v24 = ConfigMgr::EnqueueRequest(Instances);
    if ( v24 < 0 )
    {
      if ( v31 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 112LL))(v31, 0);
      CAsyncReq_DynAux_GetInstances::`vector deleting destructor'(Instances, 1u);
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v24);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        361,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v24);
    }
    v33 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v14 = v24;
    goto LABEL_35;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 112LL))(v31, 0);
  CAsyncReq_DynAux_GetInstances::`vector deleting destructor'(Instances, 1u);
  v28 = GetMemLogObject();
  v14 = -2147217402;
  CMemoryLog::Write(v28, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 360, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
  }
  CReleaseMe::release((CReleaseMe *)&v33);
  CReleaseMe::release((CReleaseMe *)&v34);
  return v14;
}

```

## disassembly

```asm
0x180040b74  mov     rax, rsp
0x180040b77  mov     [rax+20h], r9
0x180040b7b  mov     [rax+18h], r8d
0x180040b7f  mov     [rax+10h], rdx
0x180040b83  mov     [rax+8], rcx
0x180040b87  push    rbp
0x180040b88  push    rbx
0x180040b89  push    rsi
0x180040b8a  push    rdi
0x180040b8b  push    r12
0x180040b8d  push    r13
0x180040b8f  push    r14
0x180040b91  push    r15
0x180040b93  lea     rbp, [rax-4Fh]
0x180040b97  sub     rsp, 88h
0x180040b9e  mov     rax, rdx
0x180040ba1  lea     r15, WPP_GLOBAL_Control
0x180040ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180040baf  cmp     rcx, r15
0x180040bb2  jz      short loc_180040BBE
0x180040bb4  test    byte ptr [rcx+1Ch], 1
0x180040bb8  jnz     loc_180040FC8
0x180040bbe  mov     ecx, cs:?g_QueueTlsIndex@@3VCTLS@@A; dwTlsIndex
0x180040bc4  call    cs:__imp_TlsGetValue
0x180040bca  mov     ecx, 0B8h
0x180040bcf  test    rax, rax
0x180040bd2  jz      loc_180040E10
0x180040bd8  mov     r14, [rax+8]
0x180040bdc  test    r14, r14
0x180040bdf  jz      loc_180040E10
0x180040be5  mov     r14, [r14+20h]
0x180040be9  xor     ebx, ebx
0x180040beb  mov     [rbp+47h+var_80], rbx
0x180040bef  lea     r13, [r14+110h]
0x180040bf6  lea     r12, [r14+0B8h]
0x180040bfd  test    r14, r14
0x180040c00  jz      loc_180040E04
0x180040c06  mov     rdx, r13
0x180040c09  lea     rcx, [rbp+47h+var_60]
0x180040c0d  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180040c13  nop
0x180040c14  xor     esi, esi
0x180040c16  mov     rcx, r12
0x180040c19  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180040c1f  test    eax, eax
0x180040c21  jle     short loc_180040C58
0x180040c23  mov     edx, esi
0x180040c25  mov     rcx, r12
0x180040c28  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180040c2e  mov     rcx, [rax]
0x180040c31  test    rcx, rcx
0x180040c34  jz      loc_180040E31
0x180040c3a  mov     rax, [rcx]
0x180040c3d  lea     r8, [rbp+47h+var_80]
0x180040c41  lea     rdx, IID__IWmiFinalizer
0x180040c48  mov     rax, [rax]
0x180040c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c50  test    eax, eax
0x180040c52  js      loc_180040E31
0x180040c58  mov     rcx, r12
0x180040c5b  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180040c61  mov     ebx, eax
0x180040c63  xor     edi, edi
0x180040c65  mov     eax, 80041002h
0x180040c6a  cmp     esi, ebx
0x180040c6c  cmovge  edi, eax
0x180040c6f  lea     rcx, [rbp+47h+var_60]
0x180040c73  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180040c79  cmp     esi, ebx
0x180040c7b  jge     loc_180040E49
0x180040c81  mov     [rbp+47h+var_70], r12
0x180040c85  mov     rbx, [rbp+47h+var_80]
0x180040c89  mov     [rbp+47h+var_68], rbx
0x180040c8d  xor     r15d, r15d
0x180040c90  mov     [rbp+47h+var_50], r15
0x180040c94  call    ?GetEnableQueryArbitration@ConfigMgr@@SAHXZ; ConfigMgr::GetEnableQueryArbitration(void)
0x180040c99  mov     sil, 2
0x180040c9c  test    eax, eax
0x180040c9e  jz      loc_180040E25
0x180040ca4  test    r14, r14
0x180040ca7  jz      loc_180040E25
0x180040cad  mov     [rbp+47h+var_78], r15
0x180040cb1  mov     edi, 80004002h
0x180040cb6  mov     rdx, r13
0x180040cb9  lea     rcx, [rbp+47h+var_58]
0x180040cbd  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180040cc3  nop
0x180040cc4  xor     r13d, r13d
0x180040cc7  mov     r15, [rbp+47h+var_70]
0x180040ccb  mov     rcx, r12
0x180040cce  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180040cd4  cmp     r13d, eax
0x180040cd7  jge     short loc_180040D0C
0x180040cd9  mov     edx, r13d
0x180040cdc  mov     rcx, r15
0x180040cdf  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180040ce5  mov     rcx, [rax]
0x180040ce8  test    rcx, rcx
0x180040ceb  jz      short loc_180040D05
0x180040ced  mov     rax, [rcx]
0x180040cf0  lea     r8, [rbp+47h+var_78]
0x180040cf4  lea     rdx, IID__IWmiArbitratedQuery
0x180040cfb  mov     rax, [rax]
0x180040cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d03  mov     edi, eax
0x180040d05  inc     r13d
0x180040d08  test    edi, edi
0x180040d0a  js      short loc_180040CCB
0x180040d0c  lea     rcx, [rbp+47h+var_58]
0x180040d10  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180040d16  test    edi, edi
0x180040d18  mov     r15, [rbp+47h+var_50]
0x180040d1c  js      loc_180040FEF
0x180040d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d29  lea     r12, WPP_GLOBAL_Control
0x180040d30  cmp     rcx, r12
0x180040d33  jz      short loc_180040D3F
0x180040d35  test    byte ptr [rcx+1Ch], 1
0x180040d39  jnz     loc_180041005
0x180040d3f  test    edi, edi
0x180040d41  js      short loc_180040D68
0x180040d43  mov     rcx, [rbp+47h+var_78]
0x180040d47  mov     rax, [rcx]
0x180040d4a  mov     rax, [rax+18h]
0x180040d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d53  test    eax, eax
0x180040d55  js      loc_180040E96
0x180040d5b  mov     r15, [rbp+47h+var_78]
0x180040d5f  test    r15, r15
0x180040d62  jz      short loc_180040D68
0x180040d64  add     r15, 0FFFFFFFFFFFFFFF8h
0x180040d68  mov     [rbp+47h+var_70], r15
0x180040d6c  test    r15, r15
0x180040d6f  jz      loc_180040EAB
0x180040d75  mov     rdx, [rbp+47h+arg_0]
0x180040d79  mov     qword ptr [rsp+0C0h+var_98+8], rdx; struct CWbemNamespace *
0x180040d7e  mov     rax, [rbp+47h+arg_20]
0x180040d82  mov     [rsp+0C0h+var_A0], rax; struct CBasicObjectSink *
0x180040d87  mov     r9, [rbp+47h+arg_18]; struct IWbemContext *
0x180040d8b  mov     r8d, [rbp+47h+arg_10]; int
0x180040d8f  mov     rdx, [rbp+47h+arg_8]; struct CWbemObject *
0x180040d93  mov     rcx, r15; this
0x180040d96  call    ?RegisterArbitratedInstRequest@CWmiMerger@@QEAAJPEAVCWbemObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@HPEAVCWbemNamespace@@@Z; CWmiMerger::RegisterArbitratedInstRequest(CWbemObject *,long,IWbemContext *,CBasicObjectSink *,int,CWbemNamespace *)
0x180040d9b  mov     edi, eax
0x180040d9d  test    eax, eax
0x180040d9f  js      loc_18004102C
0x180040da5  mov     rcx, cs:WPP_GLOBAL_Control
0x180040dac  cmp     rcx, r12
0x180040daf  jz      short loc_180040DBB
0x180040db1  test    byte ptr [rcx+1Ch], 1
0x180040db5  jnz     loc_180040F69
0x180040dbb  mov     rax, [r15]
0x180040dbe  mov     rcx, r15
0x180040dc1  mov     rax, [rax+10h]
0x180040dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dca  mov     [rbp+47h+var_70], 0
0x180040dd2  test    rbx, rbx
0x180040dd5  jz      short loc_180040DE6
0x180040dd7  mov     rax, [rbx]
0x180040dda  mov     rcx, rbx
0x180040ddd  mov     rax, [rax+10h]
0x180040de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040de6  mov     [rbp+47h+var_68], 0
0x180040dee  mov     eax, edi
0x180040df0  add     rsp, 88h
0x180040df7  pop     r15
0x180040df9  pop     r14
0x180040dfb  pop     r13
0x180040dfd  pop     r12
0x180040dff  pop     rdi
0x180040e00  pop     rsi
0x180040e01  pop     rbx
0x180040e02  pop     rbp
0x180040e03  retn
0x180040e04  mov     [rbp+47h+var_70], r12
0x180040e08  mov     r12, rcx
0x180040e0b  jmp     loc_180040C89
0x180040e10  xor     r14d, r14d
0x180040e13  xor     ebx, ebx
0x180040e15  mov     [rbp+47h+var_80], rbx
0x180040e19  mov     r13d, 110h
0x180040e1f  mov     [rbp+47h+var_70], rcx
0x180040e23  jmp     short loc_180040E08
0x180040e25  lea     r12, WPP_GLOBAL_Control
0x180040e2c  jmp     loc_180040D68
0x180040e31  inc     esi
0x180040e33  mov     rcx, r12
0x180040e36  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180040e3c  cmp     esi, eax
0x180040e3e  jge     loc_180040C58
0x180040e44  jmp     loc_180040C23
0x180040e49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040e4f  mov     edx, edi
0x180040e51  mov     rcx, rax
0x180040e54  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e61  cmp     rcx, r15
0x180040e64  jz      short loc_180040DEE
0x180040e66  test    byte ptr [rcx+1Ch], 1
0x180040e6a  jz      short loc_180040DEE
0x180040e6c  mov     sil, 2
0x180040e6f  cmp     [rcx+19h], sil
0x180040e73  jb      loc_180040DEE
0x180040e79  mov     edx, 165h
0x180040e7e  mov     r9d, edi
0x180040e81  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180040e88  mov     rcx, [rcx+10h]
0x180040e8c  call    WPP_SF_d
0x180040e91  jmp     loc_180040DEE
0x180040e96  mov     rcx, [rbp+47h+var_78]
0x180040e9a  mov     rax, [rcx]
0x180040e9d  mov     rax, [rax+10h]
0x180040ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ea6  jmp     loc_180040D68
0x180040eab  mov     ecx, 80h
0x180040eb0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180040eb6  mov     [rbp+47h+var_50], rax
0x180040eba  test    rax, rax
0x180040ebd  jz      loc_180040F65
0x180040ec3  mov     rcx, [rbp+47h+arg_20]
0x180040ec7  mov     qword ptr [rsp+0C0h+var_98], rcx; struct IWbemObjectSinkEx *
0x180040ecc  mov     rcx, [rbp+47h+arg_18]
0x180040ed0  mov     [rsp+0C0h+var_A0], rcx; struct IWbemContext *
0x180040ed5  mov     r9d, [rbp+47h+arg_10]; int
0x180040ed9  mov     r8, [rbp+47h+arg_8]; struct CWbemObject *
0x180040edd  mov     rdx, [rbp+47h+arg_0]; struct CWbemNamespace *
0x180040ee1  mov     rcx, rax; this
0x180040ee4  call    ??0CAsyncReq_DynAux_GetInstances@@QEAA@PEAVCWbemNamespace@@PEAVCWbemObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CAsyncReq_DynAux_GetInstances::CAsyncReq_DynAux_GetInstances(CWbemNamespace *,CWbemObject *,long,IWbemContext *,CBasicObjectSink *)
0x180040ee9  mov     rdi, rax
0x180040eec  test    rdi, rdi
0x180040eef  jz      loc_180040F90
0x180040ef5  cmp     qword ptr [rdi+28h], 0
0x180040efa  jz      loc_1800410A0
0x180040f00  mov     [rdi+20h], r14
0x180040f04  test    r14, r14
0x180040f07  jz      short loc_180040F18
0x180040f09  mov     rax, [r14]
0x180040f0c  mov     rcx, r14
0x180040f0f  mov     rax, [rax+8]
0x180040f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f18  mov     rcx, rdi; struct CAsyncReq *
0x180040f1b  call    ?EnqueueRequest@ConfigMgr@@SAJPEAVCAsyncReq@@@Z; ConfigMgr::EnqueueRequest(CAsyncReq *)
0x180040f20  mov     r14d, eax
0x180040f23  test    eax, eax
0x180040f25  js      loc_180041126
0x180040f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f32  cmp     rcx, r12
0x180040f35  jz      short loc_180040F41
0x180040f37  test    byte ptr [rcx+1Ch], 1
0x180040f3b  jnz     loc_180041161
0x180040f41  mov     [rbp+47h+var_70], 0
0x180040f49  test    rbx, rbx
0x180040f4c  jz      short loc_180040F5D
0x180040f4e  mov     rax, [rbx]
0x180040f51  mov     rcx, rbx
0x180040f54  mov     rax, [rax+10h]
0x180040f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f5d  mov     edi, r14d
0x180040f60  jmp     loc_180040DE6
0x180040f65  xor     edi, edi
0x180040f67  jmp     short loc_180040EEC
0x180040f69  cmp     [rcx+19h], sil
0x180040f6d  jb      loc_180040DBB
0x180040f73  mov     edx, 166h
0x180040f78  mov     r9d, edi
0x180040f7b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180040f82  mov     rcx, [rcx+10h]
0x180040f86  call    WPP_SF_d
0x180040f8b  jmp     loc_180040DBB
0x180040f90  mov     rcx, [rbp+47h+var_80]
0x180040f94  test    rcx, rcx
0x180040f97  jnz     loc_180041059
0x180040f9d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040fa3  mov     edi, 80041006h
0x180040fa8  mov     edx, edi
0x180040faa  mov     rcx, rax
0x180040fad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fba  cmp     rcx, r12
0x180040fbd  jnz     loc_18004106C
0x180040fc3  jmp     loc_180040DCA
0x180040fc8  cmp     byte ptr [rcx+19h], 5
0x180040fcc  jb      loc_180040BBE
0x180040fd2  mov     edx, 164h
0x180040fd7  mov     r9, rax
0x180040fda  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180040fe1  mov     rcx, [rcx+10h]
0x180040fe5  call    WPP_SF_q
0x180040fea  jmp     loc_180040BBE
0x180040fef  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040ff5  mov     edx, edi
0x180040ff7  mov     rcx, rax
0x180040ffa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041000  jmp     loc_180040D22
0x180041005  cmp     [rcx+19h], sil
0x180041009  jb      loc_180040D3F
0x18004100f  mov     edx, 1Bh
0x180041014  mov     r9d, edi
0x180041017  lea     r8, WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids
0x18004101e  mov     rcx, [rcx+10h]
  ... truncated ...
```
