# CWbemNamespace::DynAux_ExecQueryAsync(CWbemObject *,ushort const *,ushort const *,long,IWbemContext *,CBasicObjectSink *,int)

- ea: `0x180044030`
- end: `0x18004464f`
- name: `?DynAux_ExecQueryAsync@CWbemNamespace@@QEAAJPEAVCWbemObject@@PEBG1JPEAUIWbemContext@@PEAVCBasicObjectSink@@H@Z`
- size: `1567`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct CWbemObject *, const unsigned __int16 *, const unsigned __int16 *, int, struct IWbemContext *, struct CBasicObjectSink *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800406a0`

## callees

- `0x18000af58`
- `0x18000b140`
- `0x18003cfe0`
- `0x180041640`
- `0x1800421ac`
- `0x1800438e8`
- `0x180044030`
- `0x180044658`
- `0x18009a8a0`
- `0x1800b1430`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044415`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044415`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800440b3`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180044175`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800440b3`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180044175`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180044127`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800441d0`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180044127`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800441d0`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800440c7`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004410b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180044186`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004431a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800440c7`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004410b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180044186`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004431a`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x1800440d7`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18004419b`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x1800440d7`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18004419b`
- `wbemcomn!GetMemLogObject` at `0x18004432e`
- `wbemcomn!GetMemLogObject` at `0x18004439c`
- `wbemcomn!GetMemLogObject` at `0x1800444ae`
- `wbemcomn!GetMemLogObject` at `0x180044514`
- `wbemcomn!GetMemLogObject` at `0x1800445dd`
- `wbemcomn!GetMemLogObject` at `0x18004432e`
- `wbemcomn!GetMemLogObject` at `0x18004439c`
- `wbemcomn!GetMemLogObject` at `0x1800444ae`
- `wbemcomn!GetMemLogObject` at `0x180044514`
- `wbemcomn!GetMemLogObject` at `0x1800445dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004433e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800443a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800444bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044522`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800445e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004433e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800443a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800444bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044522`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800445e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemNamespace::DynAux_ExecQueryAsync(
        CWbemNamespace *this,
        struct CWbemObject *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        struct IWbemContext *a6,
        struct CBasicObjectSink *a7)
{
  struct CWbemRequest *CurrentRequest; // rax
  const unsigned __int16 *v8; // r13
  __int64 v9; // rbx
  signed int v10; // r15d
  CFlexArray *v11; // rbx
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int v13; // edi
  int Request; // r14d
  __int64 v15; // rbx
  CWmiMerger *v16; // r15
  __int64 v17; // rdi
  int v18; // r14d
  unsigned int v19; // r13d
  __int64 (__fastcall ***v20)(_QWORD, GUID *, CWmiMerger **); // rcx
  CMemoryLog *v22; // rax
  CMemoryLog *MemLogObject; // rax
  CAsyncReq_DynAux_ExecQueryAsync *v24; // rax
  CAsyncReq_DynAux_ExecQueryAsync *Async; // rdi
  CMemoryLog *v26; // rax
  CClientCnt *v27; // rcx
  __int64 v28; // rdx
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  const unsigned __int16 *v31; // [rsp+20h] [rbp-98h]
  __int64 v32; // [rsp+40h] [rbp-78h] BYREF
  CWmiMerger *v33; // [rsp+48h] [rbp-70h] BYREF
  CWmiMerger *v34; // [rsp+50h] [rbp-68h]
  __int64 v35; // [rsp+58h] [rbp-60h] BYREF
  CAsyncReq_DynAux_ExecQueryAsync *v36; // [rsp+60h] [rbp-58h]
  char v37[8]; // [rsp+68h] [rbp-50h] BYREF
  char v38[8]; // [rsp+70h] [rbp-48h] BYREF
  const unsigned __int16 *v39; // [rsp+78h] [rbp-40h]
  CAsyncReq_DynAux_ExecQueryAsync *v40; // [rsp+80h] [rbp-38h]
  const unsigned __int16 *v44; // [rsp+D8h] [rbp+20h] BYREF

  v44 = a4;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      372,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)L"WQL");
  }
  CurrentRequest = CWbemQueue::GetCurrentRequest();
  if ( CurrentRequest )
  {
    v8 = (const unsigned __int16 *)((char *)CurrentRequest + 32);
    v44 = (const unsigned __int16 *)((char *)CurrentRequest + 32);
    if ( *((_QWORD *)CurrentRequest + 4) )
    {
      v32 = 0;
      v9 = *(_QWORD *)v8;
      CInCritSec::CInCritSec((CInCritSec *)v37, (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)v8 + 272LL));
      v10 = 0;
      v11 = (CFlexArray *)(v9 + 184);
      if ( (int)CFlexArray::Size(v11) > 0 )
      {
        do
        {
          v12 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))CFlexArray::operator[](v11, (unsigned int)v10);
          if ( v12 && (**v12)(v12, &IID__IWmiFinalizer, &v32) >= 0 )
            break;
          ++v10;
        }
        while ( v10 < CFlexArray::Size(v11) );
      }
      v13 = CFlexArray::Size(v11);
      Request = 0;
      if ( v10 >= v13 )
        Request = -2147217406;
      CInCritSec::~CInCritSec((CInCritSec *)v37);
      v15 = v32;
      v35 = v32;
      if ( v10 >= v13 )
        goto LABEL_32;
      v39 = v8;
      v16 = 0;
      v34 = 0;
      if ( (unsigned int)ConfigMgr::GetEnableQueryArbitration() )
      {
        v33 = 0;
        v17 = *(_QWORD *)v8;
        v18 = -2147467262;
        CInCritSec::CInCritSec((CInCritSec *)v38, (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)v8 + 272LL));
        v19 = 0;
        do
        {
          if ( (signed int)v19 >= CFlexArray::Size((CFlexArray *)(v17 + 184)) )
            break;
          v20 = *(__int64 (__fastcall ****)(_QWORD, GUID *, CWmiMerger **))CFlexArray::operator[](v17 + 184, v19);
          if ( v20 )
            v18 = (**v20)(v20, &IID__IWmiArbitratedQuery, &v33);
          ++v19;
        }
        while ( v18 < 0 );
        CInCritSec::~CInCritSec((CInCritSec *)v38);
        if ( v18 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v18);
        }
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids,
            (unsigned int)v18);
        }
        if ( v18 >= 0 )
        {
          if ( (*(int (__fastcall **)(CWmiMerger *))(*(_QWORD *)v33 + 24LL))(v33) >= 0 )
          {
            v16 = v33;
            v8 = v44;
            if ( v33 )
              v16 = (CWmiMerger *)((char *)v33 - 8);
            v34 = v16;
            goto LABEL_26;
          }
          (*(void (__fastcall **)(CWmiMerger *))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v8 = v44;
      }
LABEL_26:
      v44 = (const unsigned __int16 *)v16;
      if ( v16 )
      {
        Request = CWmiMerger::RegisterArbitratedQueryRequest(
                    v16,
                    a2,
                    a5,
                    a3,
                    v31,
                    a6,
                    (struct IWbemObjectSinkEx *)a7,
                    this);
        if ( Request < 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 112LL))(v32, 0);
LABEL_29:
        if ( v16 )
          (*(void (__fastcall **)(CWmiMerger *))(*(_QWORD *)v16 + 16LL))(v16);
        v44 = 0;
LABEL_32:
        if ( Request < 0 )
        {
          v30 = GetMemLogObject();
          CMemoryLog::Write(v30, Request);
        }
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            376,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)Request);
        }
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v35 = 0;
        return (unsigned int)Request;
      }
      try
      {
        v24 = (CAsyncReq_DynAux_ExecQueryAsync *)CWin32DefaultArena::WbemMemAlloc(0x98u);
        v40 = v24;
        if ( v24 )
          Async = CAsyncReq_DynAux_ExecQueryAsync::CAsyncReq_DynAux_ExecQueryAsync(v24, this, a2, a3, v31, a5, a6, a7);
        else
          Async = 0;
        v36 = Async;
      }
      catch ( CX_Exception )
      {
        v36 = 0;
        v15 = v35;
        v16 = v34;
        Async = 0;
        v8 = v39;
      }
      if ( Async )
      {
        if ( *((_QWORD *)Async + 5) )
        {
          Request = *((_DWORD *)Async + 36);
          if ( Request < 0
            || ((*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8),
                *((_QWORD *)Async + 4) = *(_QWORD *)v8,
                Request = ConfigMgr::EnqueueRequest(Async),
                Request < 0) )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 112LL))(v32, 0);
            CAsyncReq_DynAux_ExecQueryAsync::`scalar deleting destructor'(Async, 1u);
          }
          goto LABEL_29;
        }
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 112LL))(v32, 0);
        CAsyncReq_DynAux_ExecQueryAsync::`scalar deleting destructor'(Async, 1u);
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, -2147217402);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_64:
          CReleaseMe::release((CReleaseMe *)&v44);
          CReleaseMe::release((CReleaseMe *)&v35);
          return 2147749894LL;
        }
        v28 = 375;
      }
      else
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 112LL))(v32, 0);
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, -2147217402);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_64;
        }
        v28 = 374;
      }
      WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      goto LABEL_64;
    }
  }
  v22 = GetMemLogObject();
  CMemoryLog::Write(v22, -2147217407);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749889LL);
  }
  return 2147749889LL;
}

```

## disassembly

```asm
0x180044030  mov     rax, rsp
0x180044033  mov     [rax+20h], r9
0x180044037  mov     [rax+18h], r8
0x18004403b  mov     [rax+10h], rdx
0x18004403f  mov     [rax+8], rcx
0x180044043  push    rbx
0x180044044  push    rdi
0x180044045  push    r13
0x180044047  push    r14
0x180044049  push    r15
0x18004404b  sub     rsp, 90h
0x180044052  mov     rax, r8
0x180044055  mov     r8, rdx
0x180044058  lea     rbx, WPP_GLOBAL_Control
0x18004405f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044066  cmp     rcx, rbx
0x180044069  jz      short loc_180044075
0x18004406b  test    byte ptr [rcx+1Ch], 1
0x18004406f  jnz     loc_180044364
0x180044075  call    ?GetCurrentRequest@CWbemQueue@@SAPEAVCWbemRequest@@XZ; CWbemQueue::GetCurrentRequest(void)
0x18004407a  test    rax, rax
0x18004407d  jz      loc_18004432E
0x180044083  lea     r13, [rax+20h]
0x180044087  mov     [rsp+0B8h+arg_18], r13
0x18004408f  cmp     qword ptr [r13+0], 0
0x180044094  jz      loc_18004432E
0x18004409a  mov     [rsp+0B8h+var_78], 0
0x1800440a3  mov     rbx, [r13+0]
0x1800440a7  lea     rdx, [rbx+110h]
0x1800440ae  lea     rcx, [rsp+0B8h+var_50]
0x1800440b3  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800440b9  nop
0x1800440ba  xor     r15d, r15d
0x1800440bd  add     rbx, 0B8h
0x1800440c4  mov     rcx, rbx
0x1800440c7  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800440cd  test    eax, eax
0x1800440cf  jle     short loc_180044108
0x1800440d1  mov     edx, r15d
0x1800440d4  mov     rcx, rbx
0x1800440d7  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x1800440dd  mov     rcx, [rax]
0x1800440e0  test    rcx, rcx
0x1800440e3  jz      loc_180044314
0x1800440e9  mov     rax, [rcx]
0x1800440ec  lea     r8, [rsp+0B8h+var_78]
0x1800440f1  lea     rdx, IID__IWmiFinalizer
0x1800440f8  mov     rax, [rax]
0x1800440fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044100  test    eax, eax
0x180044102  js      loc_180044314
0x180044108  mov     rcx, rbx
0x18004410b  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180044111  mov     edi, eax
0x180044113  xor     r14d, r14d
0x180044116  mov     eax, 80041002h
0x18004411b  cmp     r15d, edi
0x18004411e  cmovge  r14d, eax
0x180044122  lea     rcx, [rsp+0B8h+var_50]
0x180044127  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18004412d  mov     rbx, [rsp+0B8h+var_78]
0x180044132  mov     [rsp+0B8h+var_60], rbx
0x180044137  cmp     r15d, edi
0x18004413a  jge     loc_18004430B
0x180044140  mov     [rsp+0B8h+var_40], r13
0x180044145  xor     r15d, r15d
0x180044148  mov     [rsp+0B8h+var_68], r15
0x18004414d  call    ?GetEnableQueryArbitration@ConfigMgr@@SAHXZ; ConfigMgr::GetEnableQueryArbitration(void)
0x180044152  test    eax, eax
0x180044154  jz      loc_180044358
0x18004415a  mov     [rsp+0B8h+var_70], r15
0x18004415f  mov     rdi, [r13+0]
0x180044163  mov     r14d, 80004002h
0x180044169  lea     rdx, [rdi+110h]
0x180044170  lea     rcx, [rsp+0B8h+var_48]
0x180044175  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18004417b  nop
0x18004417c  xor     r13d, r13d
0x18004417f  lea     rcx, [rdi+0B8h]
0x180044186  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004418c  cmp     r13d, eax
0x18004418f  jge     short loc_1800441CB
0x180044191  mov     edx, r13d
0x180044194  lea     rcx, [rdi+0B8h]
0x18004419b  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x1800441a1  mov     rcx, [rax]
0x1800441a4  test    rcx, rcx
0x1800441a7  jz      short loc_1800441C3
0x1800441a9  mov     rax, [rcx]
0x1800441ac  lea     r8, [rsp+0B8h+var_70]
0x1800441b1  lea     rdx, IID__IWmiArbitratedQuery
0x1800441b8  mov     rax, [rax]
0x1800441bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441c0  mov     r14d, eax
0x1800441c3  inc     r13d
0x1800441c6  test    r14d, r14d
0x1800441c9  js      short loc_18004417F
0x1800441cb  lea     rcx, [rsp+0B8h+var_48]
0x1800441d0  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800441d6  test    r14d, r14d
0x1800441d9  js      loc_18004439C
0x1800441df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441e6  lea     rdi, WPP_GLOBAL_Control
0x1800441ed  cmp     rcx, rdi
0x1800441f0  jz      short loc_1800441FC
0x1800441f2  test    byte ptr [rcx+1Ch], 1
0x1800441f6  jnz     loc_1800443B3
0x1800441fc  test    r14d, r14d
0x1800441ff  js      loc_1800443EB
0x180044205  mov     rcx, [rsp+0B8h+var_70]
0x18004420a  mov     rax, [rcx]
0x18004420d  mov     rax, [rax+18h]
0x180044211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044216  test    eax, eax
0x180044218  js      loc_1800443DA
0x18004421e  mov     r15, [rsp+0B8h+var_70]
0x180044223  mov     r13, [rsp+0B8h+arg_18]
0x18004422b  test    r15, r15
0x18004422e  jz      short loc_180044234
0x180044230  add     r15, 0FFFFFFFFFFFFFFF8h
0x180044234  mov     [rsp+0B8h+var_68], r15
0x180044239  mov     [rsp+0B8h+arg_18], r15
0x180044241  test    r15, r15
0x180044244  jz      loc_180044410
0x18004424a  mov     rdx, [rsp+0B8h+arg_0]
0x180044252  mov     [rsp+0B8h+var_80], rdx; struct CWbemNamespace *
0x180044257  mov     rax, [rsp+0B8h+arg_30]
0x18004425f  mov     [rsp+0B8h+var_88], rax; struct CBasicObjectSink *
0x180044264  mov     rax, [rsp+0B8h+arg_28]
0x18004426c  mov     [rsp+0B8h+var_90], rax; struct IWbemContext *
0x180044271  mov     r9, [rsp+0B8h+arg_10]; unsigned __int16 *
0x180044279  mov     r8d, [rsp+0B8h+arg_20]; int
0x180044281  mov     rdx, [rsp+0B8h+arg_8]; struct CWbemObject *
0x180044289  mov     rcx, r15; this
0x18004428c  call    ?RegisterArbitratedQueryRequest@CWmiMerger@@QEAAJPEAVCWbemObject@@JPEBG1PEAUIWbemContext@@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@@Z; CWmiMerger::RegisterArbitratedQueryRequest(CWbemObject *,long,ushort const *,ushort const *,IWbemContext *,CBasicObjectSink *,CWbemNamespace *)
0x180044291  mov     r14d, eax
0x180044294  test    eax, eax
0x180044296  js      loc_1800443F8
0x18004429c  test    r15, r15
0x18004429f  jz      short loc_1800442B0
0x1800442a1  mov     rax, [r15]
0x1800442a4  mov     rcx, r15
0x1800442a7  mov     rax, [rax+10h]
0x1800442ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442b0  mov     [rsp+0B8h+arg_18], 0
0x1800442bc  test    r14d, r14d
0x1800442bf  js      loc_1800445DD
0x1800442c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800442cc  cmp     rcx, rdi
0x1800442cf  jz      short loc_1800442DB
0x1800442d1  test    byte ptr [rcx+1Ch], 1
0x1800442d5  jnz     loc_1800445F4
0x1800442db  test    rbx, rbx
0x1800442de  jz      short loc_1800442EF
0x1800442e0  mov     rax, [rbx]
0x1800442e3  mov     rcx, rbx
0x1800442e6  mov     rax, [rax+10h]
0x1800442ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442ef  mov     [rsp+0B8h+var_60], 0
0x1800442f8  mov     eax, r14d
0x1800442fb  add     rsp, 90h
0x180044302  pop     r15
0x180044304  pop     r14
0x180044306  pop     r13
0x180044308  pop     rdi
0x180044309  pop     rbx
0x18004430a  retn
0x18004430b  lea     rdi, WPP_GLOBAL_Control
0x180044312  jmp     short loc_1800442BC
0x180044314  inc     r15d
0x180044317  mov     rcx, rbx
0x18004431a  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180044320  cmp     r15d, eax
0x180044323  jge     loc_180044108
0x180044329  jmp     loc_1800440D1
0x18004432e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044334  mov     edi, 80041001h
0x180044339  mov     edx, edi
0x18004433b  mov     rcx, rax
0x18004433e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044344  mov     rcx, cs:WPP_GLOBAL_Control
0x18004434b  cmp     rcx, rbx
0x18004434e  jnz     loc_18004461B
0x180044354  mov     eax, edi
0x180044356  jmp     short loc_1800442FB
0x180044358  lea     rdi, WPP_GLOBAL_Control
0x18004435f  jmp     loc_180044239
0x180044364  cmp     byte ptr [rcx+19h], 5
0x180044368  jb      loc_180044075
0x18004436e  mov     edx, 174h
0x180044373  lea     r9, aWql; "WQL"
0x18004437a  mov     [rsp+0B8h+var_90], r9
0x18004437f  mov     [rsp+0B8h+var_98], rax
0x180044384  mov     r9, r8
0x180044387  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004438e  mov     rcx, [rcx+10h]
0x180044392  call    WPP_SF_qSS
0x180044397  jmp     loc_180044075
0x18004439c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800443a2  mov     edx, r14d
0x1800443a5  mov     rcx, rax
0x1800443a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800443ae  jmp     loc_1800441DF
0x1800443b3  cmp     byte ptr [rcx+19h], 2
0x1800443b7  jb      loc_1800441FC
0x1800443bd  mov     edx, 1Bh
0x1800443c2  mov     r9d, r14d
0x1800443c5  lea     r8, WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids
0x1800443cc  mov     rcx, [rcx+10h]
0x1800443d0  call    WPP_SF_d
0x1800443d5  jmp     loc_1800441FC
0x1800443da  mov     rcx, [rsp+0B8h+var_70]
0x1800443df  mov     rax, [rcx]
0x1800443e2  mov     rax, [rax+10h]
0x1800443e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443eb  mov     r13, [rsp+0B8h+arg_18]
0x1800443f3  jmp     loc_180044239
0x1800443f8  mov     rcx, [rsp+0B8h+var_78]
0x1800443fd  mov     rdx, [rcx]
0x180044400  mov     rax, [rdx+70h]
0x180044404  xor     edx, edx
0x180044406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004440b  jmp     loc_18004429C
0x180044410  mov     ecx, 98h
0x180044415  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004441b  mov     [rsp+0B8h+var_38], rax
0x180044423  test    rax, rax
0x180044426  jz      short loc_180044472
0x180044428  mov     rcx, [rsp+0B8h+arg_30]
0x180044430  mov     [rsp+0B8h+var_80], rcx; struct CBasicObjectSink *
0x180044435  mov     rcx, [rsp+0B8h+arg_28]
0x18004443d  mov     [rsp+0B8h+var_88], rcx; struct IWbemContext *
0x180044442  mov     ecx, [rsp+0B8h+arg_20]
0x180044449  mov     dword ptr [rsp+0B8h+var_90], ecx; int
0x18004444d  mov     r9, [rsp+0B8h+arg_10]; unsigned __int16 *
0x180044455  mov     r8, [rsp+0B8h+arg_8]; struct CWbemObject *
0x18004445d  mov     rdx, [rsp+0B8h+arg_0]; struct CWbemNamespace *
0x180044465  mov     rcx, rax; this
0x180044468  call    ??0CAsyncReq_DynAux_ExecQueryAsync@@QEAA@PEAVCWbemNamespace@@PEAVCWbemObject@@PEBG2JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CAsyncReq_DynAux_ExecQueryAsync::CAsyncReq_DynAux_ExecQueryAsync(CWbemNamespace *,CWbemObject *,ushort const *,ushort const *,long,IWbemContext *,CBasicObjectSink *)
0x18004446d  mov     rdi, rax
0x180044470  jmp     short loc_180044474
0x180044472  xor     edi, edi
0x180044474  mov     [rsp+0B8h+var_58], rdi
0x180044479  jmp     short loc_18004448F
0x18004447b  mov     rbx, [rsp+0B8h+var_60]
0x180044480  mov     r15, [rsp+0B8h+var_68]
0x180044485  mov     rdi, [rsp+0B8h+var_58]
0x18004448a  mov     r13, [rsp+0B8h+var_40]
0x18004448f  lea     r14, WPP_GLOBAL_Control
0x180044496  test    rdi, rdi
0x180044499  jnz     short loc_1800444E9
0x18004449b  mov     rcx, [rsp+0B8h+var_78]
0x1800444a0  mov     rax, [rcx]
0x1800444a3  xor     edx, edx
0x1800444a5  mov     rax, [rax+70h]
0x1800444a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800444b4  mov     edx, 80041006h
0x1800444b9  mov     rcx, rax
0x1800444bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800444c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444c9  cmp     rcx, r14
0x1800444cc  jz      loc_18004455C
0x1800444d2  test    byte ptr [rcx+1Ch], 1
0x1800444d6  jz      loc_18004455C
0x1800444dc  cmp     byte ptr [rcx+19h], 2
0x1800444e0  jb      short loc_18004455C
0x1800444e2  mov     edx, 176h
0x1800444e7  jmp     short loc_180044545
0x1800444e9  cmp     qword ptr [rdi+28h], 0
0x1800444ee  jnz     loc_18004457E
0x1800444f4  mov     rcx, [rsp+0B8h+var_78]
0x1800444f9  mov     rax, [rcx]
0x1800444fc  xor     edx, edx
0x1800444fe  mov     rax, [rax+70h]
0x180044502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044507  mov     edx, 1; unsigned int
0x18004450c  mov     rcx, rdi; this
0x18004450f  call    ??_GCAsyncReq_DynAux_ExecQueryAsync@@UEAAPEAXI@Z; CAsyncReq_DynAux_ExecQueryAsync::`scalar deleting destructor'(uint)
0x180044514  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004451a  mov     edx, 80041006h
0x18004451f  mov     rcx, rax
0x180044522  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044528  mov     rcx, cs:WPP_GLOBAL_Control
0x18004452f  cmp     rcx, r14
0x180044532  jz      short loc_18004455C
0x180044534  test    byte ptr [rcx+1Ch], 1
0x180044538  jz      short loc_18004455C
0x18004453a  cmp     byte ptr [rcx+19h], 2
0x18004453e  jb      short loc_18004455C
0x180044540  mov     edx, 177h
0x180044545  mov     r9d, 80041006h
0x18004454b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180044552  mov     rcx, [rcx+10h]
0x180044556  call    WPP_SF_d
0x18004455b  nop
0x18004455c  lea     rcx, [rsp+0B8h+arg_18]; this
0x180044564  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180044569  nop
0x18004456a  lea     rcx, [rsp+0B8h+var_60]; this
  ... truncated ...
```
