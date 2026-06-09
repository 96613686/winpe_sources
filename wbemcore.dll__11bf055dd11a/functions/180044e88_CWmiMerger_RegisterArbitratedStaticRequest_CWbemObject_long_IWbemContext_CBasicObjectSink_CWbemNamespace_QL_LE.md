# CWmiMerger::RegisterArbitratedStaticRequest(CWbemObject *,long,IWbemContext *,CBasicObjectSink *,CWbemNamespace *,QL_LEVEL_1_RPN_EXPRESSION *)

- ea: `0x180044e88`
- end: `0x1800452c4`
- name: `?RegisterArbitratedStaticRequest@CWmiMerger@@QEAAJPEAVCWbemObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@PEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z`
- size: `1084`
- prototype: `__int64 __usercall@<rax>(CWmiMerger *__hidden this@<rcx>, struct CWbemObject *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct CBasicObjectSink *, struct CWbemNamespace *, struct QL_LEVEL_1_RPN_EXPRESSION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180044758`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x180042908`
- `0x180044e88`
- `0x1800452cc`
- `0x1800453a4`
- `0x180045428`
- `0x18008a550`
- `0x18008d608`
- `0x1800bfa44`
- `0x1800bff8c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180044f94`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180044f94`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044ec9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044f64`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044ec9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044f64`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180044f3e`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180044f3e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180044ffb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004503d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004507e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800450b9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004522e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180044ffb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004503d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004507e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800450b9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004522e`
- `wbemcomn!GetMemLogObject` at `0x180045053`
- `wbemcomn!GetMemLogObject` at `0x180045093`
- `wbemcomn!GetMemLogObject` at `0x1800450f5`
- `wbemcomn!GetMemLogObject` at `0x180045150`
- `wbemcomn!GetMemLogObject` at `0x1800451df`
- `wbemcomn!GetMemLogObject` at `0x180045287`
- `wbemcomn!GetMemLogObject` at `0x180045053`
- `wbemcomn!GetMemLogObject` at `0x180045093`
- `wbemcomn!GetMemLogObject` at `0x1800450f5`
- `wbemcomn!GetMemLogObject` at `0x180045150`
- `wbemcomn!GetMemLogObject` at `0x1800451df`
- `wbemcomn!GetMemLogObject` at `0x180045287`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045063`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004509e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045105`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045160`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800451ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045292`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045063`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004509e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045105`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045160`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800451ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045292`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CWmiMerger::RegisterArbitratedStaticRequest(
        CWmiMerger *this,
        struct CWbemObject *a2,
        __int64 a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5,
        struct CWbemNamespace *a6,
        struct QL_LEVEL_1_RPN_EXPRESSION *a7)
{
  CMergerDynReq_Static_GetInstances *Instances; // rax
  int v11; // r9d
  struct CMergerDynReq *v12; // r14
  int v13; // r15d
  CWmiMergerRequestMgr *v14; // rax
  unsigned __int16 *LPWSTR; // rax
  __int64 v16; // r15
  unsigned int v17; // edi
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  struct CMergerDynReq *v24; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v25[8]; // [rsp+50h] [rbp-38h] BYREF
  CMergerDynReq_Static_GetInstances *v26; // [rsp+58h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids);
  }
  std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(&v24);
  Instances = (CMergerDynReq_Static_GetInstances *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
  v26 = Instances;
  if ( Instances )
    Instances = CMergerDynReq_Static_GetInstances::CMergerDynReq_Static_GetInstances(Instances, a6, a2, v11, a4, a5, a7);
  std::unique_ptr<CMergerDynReq_Static_GetInstances>::reset(&v24, Instances);
  v12 = v24;
  if ( !v24 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids, 2147749894LL);
    }
    goto LABEL_28;
  }
  if ( !*((_QWORD *)v24 + 5) )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids, 2147749894LL);
    }
LABEL_28:
    std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
    return 2147749894LL;
  }
  CInCritSec::CInCritSec((CInCritSec *)v25, (struct _RTL_CRITICAL_SECTION *)((char *)this + 288));
  v13 = *((_DWORD *)this + 69);
  if ( v13 < 0 )
  {
    CInCritSec::~CInCritSec((CInCritSec *)v25);
    std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
    return (unsigned int)v13;
  }
  else
  {
    if ( *((_QWORD *)this + 42) )
      goto LABEL_12;
    v14 = (CWmiMergerRequestMgr *)CWin32DefaultArena::WbemMemAlloc(0x78u);
    v26 = v14;
    if ( v14 )
      v14 = CWmiMergerRequestMgr::CWmiMergerRequestMgr(v14, this);
    *((_QWORD *)this + 42) = v14;
    if ( v14 )
    {
LABEL_12:
      LPWSTR = CVar::GetLPWSTR((struct CMergerDynReq *)((char *)v12 + 96));
      v16 = CSortedUniquePointerArray<CWmiMergerRecord>::Find((char *)this + 80, LPWSTR);
      if ( v16 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
        *((_QWORD *)v12 + 4) = *((_QWORD *)this + 5);
        v17 = CWmiMergerRequestMgr::AddRequest(*((CWmiMergerRequestMgr **)this + 42), v12, *(_DWORD *)(v16 + 8));
        if ( (v17 & 0x80000000) != 0 )
        {
          v20 = GetMemLogObject();
          CMemoryLog::Write(v20, v17);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids, v17);
          }
          CInCritSec::~CInCritSec((CInCritSec *)v25);
          std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
          return v17;
        }
        else
        {
          std::unique_ptr<CMergerChildReq>::release(&v24);
          CInCritSec::~CInCritSec((CInCritSec *)v25);
          std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids, v17);
          }
          return v17;
        }
      }
      else
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids,
            2147749889LL);
        }
        CInCritSec::~CInCritSec((CInCritSec *)v25);
        std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
        return 2147749889LL;
      }
    }
    else
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids, 2147749894LL);
      }
      CInCritSec::~CInCritSec((CInCritSec *)v25);
      std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>();
      return 2147749894LL;
    }
  }
}

```

## disassembly

```asm
0x180044e88  push    rsi
0x180044e8a  push    rdi
0x180044e8b  push    r14
0x180044e8d  push    r15
0x180044e8f  sub     rsp, 68h
0x180044e93  mov     r14, r9
0x180044e96  mov     r15, rdx
0x180044e99  mov     rdi, rcx
0x180044e9c  lea     rsi, WPP_GLOBAL_Control
0x180044ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180044eaa  cmp     rcx, rsi
0x180044ead  jz      short loc_180044EB9
0x180044eaf  test    byte ptr [rcx+1Ch], 1
0x180044eb3  jnz     loc_1800450D1
0x180044eb9  lea     rcx, [rsp+88h+var_40]
0x180044ebe  call    ??0?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(void)
0x180044ec3  nop
0x180044ec4  mov     ecx, 0A8h
0x180044ec9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180044ecf  mov     [rsp+88h+var_30], rax
0x180044ed4  test    rax, rax
0x180044ed7  jz      short loc_180044F0C
0x180044ed9  mov     rcx, [rsp+88h+arg_30]
0x180044ee1  mov     [rsp+88h+var_58], rcx; struct QL_LEVEL_1_RPN_EXPRESSION *
0x180044ee6  mov     rcx, [rsp+88h+arg_20]
0x180044eee  mov     [rsp+88h+var_60], rcx; struct CBasicObjectSink *
0x180044ef3  mov     [rsp+88h+var_68], r14; struct IWbemContext *
0x180044ef8  mov     r8, r15; struct CWbemObject *
0x180044efb  mov     rdx, [rsp+88h+arg_28]; struct CWbemNamespace *
0x180044f03  mov     rcx, rax; this
0x180044f06  call    ??0CMergerDynReq_Static_GetInstances@@QEAA@PEAVCWbemNamespace@@PEAVCWbemObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@PEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z; CMergerDynReq_Static_GetInstances::CMergerDynReq_Static_GetInstances(CWbemNamespace *,CWbemObject *,long,IWbemContext *,CBasicObjectSink *,QL_LEVEL_1_RPN_EXPRESSION *)
0x180044f0b  nop
0x180044f0c  mov     rdx, rax
0x180044f0f  lea     rcx, [rsp+88h+var_40]
0x180044f14  call    ?reset@?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAAXPEAVCMergerDynReq_Static_GetInstances@@@Z; std::unique_ptr<CMergerDynReq_Static_GetInstances>::reset(CMergerDynReq_Static_GetInstances *)
0x180044f19  mov     r14, [rsp+88h+var_40]
0x180044f1e  test    r14, r14
0x180044f21  jz      loc_1800450F5
0x180044f27  cmp     qword ptr [r14+28h], 0
0x180044f2c  jz      loc_180045150
0x180044f32  lea     rdx, [rdi+120h]
0x180044f39  lea     rcx, [rsp+88h+var_38]
0x180044f3e  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180044f44  nop
0x180044f45  mov     r15d, [rdi+114h]
0x180044f4c  test    r15d, r15d
0x180044f4f  js      loc_180045038
0x180044f55  cmp     qword ptr [rdi+150h], 0
0x180044f5d  jnz     short loc_180044F90
0x180044f5f  mov     ecx, 78h ; 'x'
0x180044f64  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180044f6a  mov     [rsp+88h+var_30], rax
0x180044f6f  test    rax, rax
0x180044f72  jz      short loc_180044F80
0x180044f74  mov     rdx, rdi; struct CWmiMerger *
0x180044f77  mov     rcx, rax; this
0x180044f7a  call    ??0CWmiMergerRequestMgr@@QEAA@PEAVCWmiMerger@@@Z; CWmiMergerRequestMgr::CWmiMergerRequestMgr(CWmiMerger *)
0x180044f7f  nop
0x180044f80  mov     [rdi+150h], rax
0x180044f87  test    rax, rax
0x180044f8a  jz      loc_180045053
0x180044f90  lea     rcx, [r14+60h]
0x180044f94  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180044f9a  lea     rcx, [rdi+50h]
0x180044f9e  mov     rdx, rax
0x180044fa1  call    ?Find@?$CSortedUniquePointerArray@VCWmiMergerRecord@@@@QEAAPEAVCWmiMergerRecord@@PEBGPEAH@Z; CSortedUniquePointerArray<CWmiMergerRecord>::Find(ushort const *,int *)
0x180044fa6  mov     r15, rax
0x180044fa9  test    rax, rax
0x180044fac  jz      loc_1800451DF
0x180044fb2  mov     rcx, [rdi+28h]
0x180044fb6  mov     rax, [rcx]
0x180044fb9  mov     rax, [rax+8]
0x180044fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fc2  mov     rax, [rdi+28h]
0x180044fc6  mov     [r14+20h], rax
0x180044fca  mov     r8d, [r15+8]; unsigned int
0x180044fce  mov     rdx, r14; struct CMergerDynReq *
0x180044fd1  mov     rcx, [rdi+150h]; this
0x180044fd8  call    ?AddRequest@CWmiMergerRequestMgr@@QEAAJPEAVCMergerDynReq@@K@Z; CWmiMergerRequestMgr::AddRequest(CMergerDynReq *,ulong)
0x180044fdd  mov     edi, eax
0x180044fdf  mov     [rsp+88h+var_48], eax
0x180044fe3  test    eax, eax
0x180044fe5  js      loc_180045093
0x180044feb  lea     rcx, [rsp+88h+var_40]
0x180044ff0  call    ?release@?$unique_ptr@VCMergerChildReq@@U?$default_delete@VCMergerChildReq@@@std@@@std@@QEAAPEAVCMergerChildReq@@XZ; std::unique_ptr<CMergerChildReq>::release(void)
0x180044ff5  nop
0x180044ff6  lea     rcx, [rsp+88h+var_38]
0x180044ffb  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180045001  nop
0x180045002  lea     rcx, [rsp+88h+var_40]
0x180045007  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x18004500c  nop
0x18004500d  test    edi, edi
0x18004500f  js      loc_180045287
0x180045015  mov     rcx, cs:WPP_GLOBAL_Control
0x18004501c  cmp     rcx, rsi
0x18004501f  jz      short loc_18004502B
0x180045021  test    byte ptr [rcx+1Ch], 1
0x180045025  jnz     loc_18004529D
0x18004502b  mov     eax, edi
0x18004502d  add     rsp, 68h
0x180045031  pop     r15
0x180045033  pop     r14
0x180045035  pop     rdi
0x180045036  pop     rsi
0x180045037  retn
0x180045038  lea     rcx, [rsp+88h+var_38]
0x18004503d  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180045043  nop
0x180045044  lea     rcx, [rsp+88h+var_40]
0x180045049  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x18004504e  mov     eax, r15d
0x180045051  jmp     short loc_18004502D
0x180045053  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045059  mov     edi, 80041006h
0x18004505e  mov     edx, edi
0x180045060  mov     rcx, rax
0x180045063  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045069  mov     rcx, cs:WPP_GLOBAL_Control
0x180045070  cmp     rcx, rsi
0x180045073  jnz     loc_1800451AB
0x180045079  lea     rcx, [rsp+88h+var_38]
0x18004507e  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180045084  nop
0x180045085  lea     rcx, [rsp+88h+var_40]
0x18004508a  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x18004508f  mov     eax, edi
0x180045091  jmp     short loc_18004502D
0x180045093  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045099  mov     edx, edi
0x18004509b  mov     rcx, rax
0x18004509e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800450a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800450ab  cmp     rcx, rsi
0x1800450ae  jnz     loc_180045246
0x1800450b4  lea     rcx, [rsp+88h+var_38]
0x1800450b9  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800450bf  nop
0x1800450c0  lea     rcx, [rsp+88h+var_40]
0x1800450c5  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x1800450ca  mov     eax, edi
0x1800450cc  jmp     loc_18004502D
0x1800450d1  cmp     byte ptr [rcx+19h], 5
0x1800450d5  jb      loc_180044EB9
0x1800450db  mov     edx, 3Dh ; '='
0x1800450e0  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x1800450e7  mov     rcx, [rcx+10h]
0x1800450eb  call    WPP_SF_
0x1800450f0  jmp     loc_180044EB9
0x1800450f5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800450fb  mov     edi, 80041006h
0x180045100  mov     edx, edi
0x180045102  mov     rcx, rax
0x180045105  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004510b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045112  cmp     rcx, rsi
0x180045115  jz      short loc_18004513F
0x180045117  test    byte ptr [rcx+1Ch], 1
0x18004511b  jz      short loc_18004513F
0x18004511d  cmp     byte ptr [rcx+19h], 2
0x180045121  jb      short loc_18004513F
0x180045123  mov     edx, 3Eh ; '>'
0x180045128  mov     r9d, 80041006h
0x18004512e  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x180045135  mov     rcx, [rcx+10h]
0x180045139  call    WPP_SF_d
0x18004513e  nop
0x18004513f  lea     rcx, [rsp+88h+var_40]
0x180045144  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x180045149  mov     eax, edi
0x18004514b  jmp     loc_18004502D
0x180045150  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045156  mov     edi, 80041006h
0x18004515b  mov     edx, edi
0x18004515d  mov     rcx, rax
0x180045160  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045166  mov     rcx, cs:WPP_GLOBAL_Control
0x18004516d  cmp     rcx, rsi
0x180045170  jz      short loc_18004519A
0x180045172  test    byte ptr [rcx+1Ch], 1
0x180045176  jz      short loc_18004519A
0x180045178  cmp     byte ptr [rcx+19h], 2
0x18004517c  jb      short loc_18004519A
0x18004517e  mov     edx, 3Fh ; '?'
0x180045183  mov     r9d, 80041006h
0x180045189  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x180045190  mov     rcx, [rcx+10h]
0x180045194  call    WPP_SF_d
0x180045199  nop
0x18004519a  lea     rcx, [rsp+88h+var_40]
0x18004519f  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x1800451a4  mov     eax, edi
0x1800451a6  jmp     loc_18004502D
0x1800451ab  test    byte ptr [rcx+1Ch], 1
0x1800451af  jz      loc_180045079
0x1800451b5  cmp     byte ptr [rcx+19h], 2
0x1800451b9  jb      loc_180045079
0x1800451bf  mov     edx, 40h ; '@'
0x1800451c4  mov     r9d, 80041006h
0x1800451ca  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x1800451d1  mov     rcx, [rcx+10h]
0x1800451d5  call    WPP_SF_d
0x1800451da  jmp     loc_180045079
0x1800451df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800451e5  mov     edi, 80041001h
0x1800451ea  mov     edx, edi
0x1800451ec  mov     rcx, rax
0x1800451ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800451f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800451fc  cmp     rcx, rsi
0x1800451ff  jz      short loc_180045229
0x180045201  test    byte ptr [rcx+1Ch], 1
0x180045205  jz      short loc_180045229
0x180045207  cmp     byte ptr [rcx+19h], 2
0x18004520b  jb      short loc_180045229
0x18004520d  mov     edx, 41h ; 'A'
0x180045212  mov     r9d, 80041001h
0x180045218  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x18004521f  mov     rcx, [rcx+10h]
0x180045223  call    WPP_SF_d
0x180045228  nop
0x180045229  lea     rcx, [rsp+88h+var_38]
0x18004522e  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180045234  nop
0x180045235  lea     rcx, [rsp+88h+var_40]
0x18004523a  call    ??1?$unique_ptr@VCMergerDynReq_Static_GetInstances@@U?$default_delete@VCMergerDynReq_Static_GetInstances@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMergerDynReq_Static_GetInstances>::~unique_ptr<CMergerDynReq_Static_GetInstances>(void)
0x18004523f  mov     eax, edi
0x180045241  jmp     loc_18004502D
0x180045246  test    byte ptr [rcx+1Ch], 1
0x18004524a  jz      loc_1800450B4
0x180045250  cmp     byte ptr [rcx+19h], 2
0x180045254  jb      loc_1800450B4
0x18004525a  mov     edx, 42h ; 'B'
0x18004525f  mov     r9d, edi
0x180045262  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x180045269  mov     rcx, [rcx+10h]
0x18004526d  call    WPP_SF_d
0x180045272  jmp     loc_1800450B4
0x180045277  lea     rsi, WPP_GLOBAL_Control
0x18004527e  mov     edi, [rsp+88h+var_48]
0x180045282  jmp     loc_18004500D
0x180045287  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004528d  mov     edx, edi
0x18004528f  mov     rcx, rax
0x180045292  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045298  jmp     loc_180045015
0x18004529d  cmp     byte ptr [rcx+19h], 2
0x1800452a1  jb      loc_18004502B
0x1800452a7  mov     edx, 43h ; 'C'
0x1800452ac  mov     r9d, edi
0x1800452af  lea     r8, WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids
0x1800452b6  mov     rcx, [rcx+10h]
0x1800452ba  call    WPP_SF_d
0x1800452bf  jmp     loc_18004502B
```
