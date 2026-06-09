# CWbemNamespace::_DeleteInstanceAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180064630`
- end: `0x180064d21`
- name: `?_DeleteInstanceAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1777`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064130`
- `0x18009bc00`

## callees

- `0x18000ae2c`
- `0x18000b140`
- `0x18000f474`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x180047ed0`
- `0x180049580`
- `0x1800523c0`
- `0x180062ed0`
- `0x180064630`
- `0x1800903d0`
- `0x1800a093c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180064ae3`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180064ae3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180064aa7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180064aa7`
- `wbemcomn!GetMemLogObject` at `0x180064667`
- `wbemcomn!GetMemLogObject` at `0x180064714`
- `wbemcomn!GetMemLogObject` at `0x18006477c`
- `wbemcomn!GetMemLogObject` at `0x1800647d6`
- `wbemcomn!GetMemLogObject` at `0x18006481f`
- `wbemcomn!GetMemLogObject` at `0x180064899`
- `wbemcomn!GetMemLogObject` at `0x1800648f8`
- `wbemcomn!GetMemLogObject` at `0x180064975`
- `wbemcomn!GetMemLogObject` at `0x180064a54`
- `wbemcomn!GetMemLogObject` at `0x180064b13`
- `wbemcomn!GetMemLogObject` at `0x180064b79`
- `wbemcomn!GetMemLogObject` at `0x180064bfe`
- `wbemcomn!GetMemLogObject` at `0x180064c5a`
- `wbemcomn!GetMemLogObject` at `0x180064cbb`
- `wbemcomn!GetMemLogObject` at `0x180064667`
- `wbemcomn!GetMemLogObject` at `0x180064714`
- `wbemcomn!GetMemLogObject` at `0x18006477c`
- `wbemcomn!GetMemLogObject` at `0x1800647d6`
- `wbemcomn!GetMemLogObject` at `0x18006481f`
- `wbemcomn!GetMemLogObject` at `0x180064899`
- `wbemcomn!GetMemLogObject` at `0x1800648f8`
- `wbemcomn!GetMemLogObject` at `0x180064975`
- `wbemcomn!GetMemLogObject` at `0x180064a54`
- `wbemcomn!GetMemLogObject` at `0x180064b13`
- `wbemcomn!GetMemLogObject` at `0x180064b79`
- `wbemcomn!GetMemLogObject` at `0x180064bfe`
- `wbemcomn!GetMemLogObject` at `0x180064c5a`
- `wbemcomn!GetMemLogObject` at `0x180064cbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064672`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064722`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006478c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800647e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006482d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800648a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064903`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064980`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064a5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064b23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064b85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064c09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064c6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064cc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064672`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064722`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006478c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800647e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006482d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800648a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064903`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064980`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064a5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064b23`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064b85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064c09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064c6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064cc9`

## string_xrefs

- `0x180064960`: `IWbemServices::DeleteInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWbemNamespace::_DeleteInstanceAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        unsigned __int16 *const a5,
        int a6,
        struct IWbemContext *a7,
        struct IWbemObjectSink *a8)
{
  struct _IWmiFinalizer *v8; // r14
  int v10; // esi
  int v11; // r8d
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  struct IWbemObjectSink *v17; // r13
  int v18; // esi
  unsigned __int16 *v19; // r12
  CMemoryLog *v20; // rax
  CClientCnt *v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  struct IWbemObjectSink *v24; // r9
  unsigned __int64 v25; // rdx
  CMemoryLog *v26; // rax
  int v27; // eax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  int v30; // ecx
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CClientCnt *v34; // rcx
  __int64 v35; // rdx
  const wchar_t *v36; // r8
  CMemoryLog *v37; // rax
  CNamespaceReq *v38; // rax
  CNamespaceReq *v39; // rsi
  struct IWbemContext *v40; // rax
  CMemoryLog *v41; // rax
  CClientCnt *v42; // rcx
  __int64 v43; // rdx
  int inited; // r15d
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  __int64 v47; // r9
  CMemoryLog *v48; // rax
  CMemoryLog *v49; // rax
  struct IWbemObjectSink **v50; // [rsp+20h] [rbp-60h]
  struct IWbemObjectSink *v51; // [rsp+28h] [rbp-58h]
  __int64 v52; // [rsp+30h] [rbp-50h]
  int v53; // [rsp+40h] [rbp-40h]
  CAsyncReq_GetObjectAsync *v54; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSink *v55; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v56; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSinkEx *v57; // [rsp+60h] [rbp-20h] BYREF
  struct IWbemObjectSink *v58; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v59[2]; // [rsp+70h] [rbp-10h] BYREF
  struct _IWmiFinalizer *v61; // [rsp+D0h] [rbp+50h] BYREF

  v61 = a3;
  v8 = a3;
  v10 = CWbemNamespace::CheckNs(this);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v10;
    }
    v14 = 635;
    goto LABEL_6;
  }
  v17 = a8;
  v18 = a6;
  v19 = a5;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 636, v11, (_DWORD)a5, a6, (char)a8, *((_DWORD *)this + 76));
  }
  if ( v8 || v17 )
  {
    if ( !v19 || !*v19 )
    {
      v49 = GetMemLogObject();
      CMemoryLog::Write(v49, -2147217400);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v22 = 638;
      goto LABEL_105;
    }
    v23 = wcslen_max(v19, (unsigned int)g_PathLimit);
    if ( v23 > v25 )
    {
      v26 = GetMemLogObject();
      v10 = -2147217300;
      CMemoryLog::Write(v26, -2147217300);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v10;
      }
      v14 = 639;
      v15 = 2147749996LL;
      goto LABEL_7;
    }
    v27 = v18 & 0x10000;
    if ( *((_DWORD *)this + 30) == (_DWORD)v24 && v27 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, -2147217400);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v22 = 640;
      goto LABEL_105;
    }
    if ( (v18 & 0xFFFEFF7F) != 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, -2147217400);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v22 = 641;
      goto LABEL_105;
    }
    v30 = v18 - 49152;
    if ( !v27 )
      v30 = v18;
    v53 = v30;
    v55 = v24;
    if ( v8 )
    {
      v10 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
              v8,
              0,
              &v55);
      if ( v10 < 0 )
      {
        v32 = GetMemLogObject();
        CMemoryLog::Write(v32, v10);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v10;
        }
        v14 = 643;
LABEL_6:
        v15 = (unsigned int)v10;
LABEL_7:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v15);
        return (unsigned int)v10;
      }
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    else
    {
      v10 = CWbemNamespace::CreateAsyncFinalizer(this, a7, v17, &v61, &v55);
      if ( v10 < 0 )
      {
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, v10);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v10;
        }
        v14 = 642;
        goto LABEL_6;
      }
      v8 = v61;
    }
    v58 = v55;
    v59[0] = v8;
    v10 = CWbemNamespace::PublishInfo(this, L"IWbemServices::DeleteInstance", v19, v8, a7);
    if ( v10 < 0 )
    {
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, v10);
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_58;
      }
      v35 = 644;
      goto LABEL_57;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v36 = L"Async";
      if ( !v17 )
        v36 = L"(Semi)Sync";
      LODWORD(v52) = *((_DWORD *)this + 76);
      LODWORD(v51) = *((_DWORD *)this + 95);
      LODWORD(v50) = v53;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 4, v36, v19, v50, v51, v52, *((_QWORD *)this + 11));
    }
    v56 = 0;
    v10 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v55->lpVtbl->QueryInterface)(
            v55,
            &IID_IWbemObjectSinkEx,
            &v56);
    if ( v10 < 0 )
    {
      v37 = GetMemLogObject();
      CMemoryLog::Write(v37, v10);
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_58;
      }
      v35 = 645;
LABEL_57:
      WPP_SF_d(*((_QWORD *)v34 + 2), v35, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v10);
LABEL_58:
      CReleaseMe::release((CReleaseMe *)v59);
      CReleaseMe::release((CReleaseMe *)&v58);
      return (unsigned int)v10;
    }
    v57 = v56;
    v54 = 0;
    v38 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v39 = v38;
    v59[1] = v38;
    if ( v38 )
    {
      CNamespaceReq::CNamespaceReq(v38, this, v56, a7, 0);
      *(_QWORD *)v39 = &CAsyncReq_DeleteInstanceAsync::`vftable';
      WString::WString((CNamespaceReq *)((char *)v39 + 96), v19);
      *((_DWORD *)v39 + 26) = v53;
    }
    else
    {
      v39 = 0;
    }
    if ( v39 )
    {
      std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v54);
      v54 = v39;
      v40 = (struct IWbemContext *)*((_QWORD *)v39 + 5);
      if ( v40 )
      {
        inited = CWbemNamespace::InitNewTask(this, v39, v8, a2, v40, v17);
        if ( inited < 0 )
        {
          v45 = GetMemLogObject();
          CMemoryLog::Write(v45, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              648,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v54);
          CReleaseMe::release((CReleaseMe *)&v57);
          v10 = inited;
          goto LABEL_58;
        }
        CReleaseMe::release((CReleaseMe *)&v58);
        v10 = ConfigMgr::EnqueueRequest(v39);
        if ( v10 >= 0 )
        {
          v54 = 0;
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_100;
          }
          v43 = 650;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v46 = GetMemLogObject();
          CMemoryLog::Write(v46, v10);
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_100;
          }
          v43 = 649;
        }
        v47 = (unsigned int)v10;
        goto LABEL_99;
      }
      v41 = GetMemLogObject();
      v10 = -2147217402;
      CMemoryLog::Write(v41, -2147217402);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v43 = 647;
    }
    else
    {
      v48 = GetMemLogObject();
      v10 = -2147217402;
      CMemoryLog::Write(v48, -2147217402);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v43 = 646;
    }
    v47 = 2147749894LL;
LABEL_99:
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v47);
LABEL_100:
    std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v54);
    CReleaseMe::release((CReleaseMe *)&v57);
    goto LABEL_58;
  }
  v20 = GetMemLogObject();
  CMemoryLog::Write(v20, -2147217400);
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749896LL;
  }
  v22 = 637;
LABEL_105:
  WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180064630  mov     [rsp-38h+arg_0], rbx
0x180064635  mov     [rsp-38h+arg_10], r8
0x18006463a  mov     [rsp-38h+arg_8], edx
0x18006463e  push    rbp
0x18006463f  push    rsi
0x180064640  push    rdi
0x180064641  push    r12
0x180064643  push    r13
0x180064645  push    r14
0x180064647  push    r15
0x180064649  mov     rbp, rsp
0x18006464c  sub     rsp, 80h
0x180064653  mov     r14, r8
0x180064656  mov     r15, rcx
0x180064659  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18006465e  mov     esi, eax
0x180064660  xor     r9d, r9d
0x180064663  test    eax, eax
0x180064665  jns     short loc_1800646B7
0x180064667  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006466d  mov     edx, esi
0x18006466f  mov     rcx, rax
0x180064672  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064678  lea     rdi, WPP_GLOBAL_Control
0x18006467f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064686  cmp     rcx, rdi
0x180064689  jz      short loc_1800646B0
0x18006468b  mov     bl, 1
0x18006468d  test    [rcx+1Ch], bl
0x180064690  jz      short loc_1800646B0
0x180064692  cmp     byte ptr [rcx+19h], 2
0x180064696  jb      short loc_1800646B0
0x180064698  mov     edx, 27Bh
0x18006469d  mov     r9d, esi
0x1800646a0  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800646a7  mov     rcx, [rcx+10h]
0x1800646ab  call    WPP_SF_d
0x1800646b0  mov     eax, esi
0x1800646b2  jmp     loc_180064D06
0x1800646b7  lea     rdi, WPP_GLOBAL_Control
0x1800646be  mov     r13, [rbp+arg_38]
0x1800646c2  mov     esi, [rbp+arg_28]
0x1800646c5  mov     r12, [rbp+arg_20]
0x1800646c9  mov     bl, 1
0x1800646cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800646d2  cmp     rcx, rdi
0x1800646d5  jz      short loc_18006470A
0x1800646d7  test    [rcx+1Ch], bl
0x1800646da  jz      short loc_18006470A
0x1800646dc  cmp     byte ptr [rcx+19h], 5
0x1800646e0  jb      short loc_18006470A
0x1800646e2  mov     edx, 27Ch
0x1800646e7  mov     eax, [r15+130h]
0x1800646ee  mov     dword ptr [rsp+80h+var_50], eax
0x1800646f2  mov     [rsp+80h+var_58], r13
0x1800646f7  mov     dword ptr [rsp+80h+var_60], esi
0x1800646fb  mov     r9, r12
0x1800646fe  mov     rcx, [rcx+10h]
0x180064702  call    WPP_SF_Sdql
0x180064707  xor     r9d, r9d
0x18006470a  test    r14, r14
0x18006470d  jnz     short loc_180064755
0x18006470f  test    r13, r13
0x180064712  jnz     short loc_180064755
0x180064714  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006471a  mov     edx, 80041008h
0x18006471f  mov     rcx, rax
0x180064722  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064728  mov     rcx, cs:WPP_GLOBAL_Control
0x18006472f  cmp     rcx, rdi
0x180064732  jz      loc_180064D01
0x180064738  test    [rcx+1Ch], bl
0x18006473b  jz      loc_180064D01
0x180064741  cmp     byte ptr [rcx+19h], 2
0x180064745  jb      loc_180064D01
0x18006474b  mov     edx, 27Dh
0x180064750  jmp     loc_180064CEB
0x180064755  test    r12, r12
0x180064758  jz      loc_180064CBB
0x18006475e  cmp     [r12], r9w
0x180064763  jz      loc_180064CBB
0x180064769  mov     edx, cs:?g_PathLimit@@3KA; unsigned __int64
0x18006476f  mov     rcx, r12; unsigned __int16 *
0x180064772  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x180064777  cmp     rax, rdx
0x18006477a  jbe     short loc_1800647C5
0x18006477c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180064782  mov     esi, 8004106Ch
0x180064787  mov     edx, esi
0x180064789  mov     rcx, rax
0x18006478c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064792  mov     rcx, cs:WPP_GLOBAL_Control
0x180064799  cmp     rcx, rdi
0x18006479c  jz      loc_1800646B0
0x1800647a2  test    [rcx+1Ch], bl
0x1800647a5  jz      loc_1800646B0
0x1800647ab  cmp     byte ptr [rcx+19h], 2
0x1800647af  jb      loc_1800646B0
0x1800647b5  mov     edx, 27Fh
0x1800647ba  mov     r9d, 8004106Ch
0x1800647c0  jmp     loc_1800646A0
0x1800647c5  mov     eax, esi
0x1800647c7  and     eax, 10000h
0x1800647cc  cmp     [r15+78h], r9d
0x1800647d0  jnz     short loc_180064817
0x1800647d2  test    eax, eax
0x1800647d4  jz      short loc_180064817
0x1800647d6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800647dc  mov     edx, 80041008h
0x1800647e1  mov     rcx, rax
0x1800647e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800647ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647f1  cmp     rcx, rdi
0x1800647f4  jz      loc_180064D01
0x1800647fa  test    [rcx+1Ch], bl
0x1800647fd  jz      loc_180064D01
0x180064803  cmp     byte ptr [rcx+19h], 2
0x180064807  jb      loc_180064D01
0x18006480d  mov     edx, 280h
0x180064812  jmp     loc_180064CEB
0x180064817  test    esi, 0FFFEFF7Fh
0x18006481d  jz      short loc_180064860
0x18006481f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180064825  mov     edx, 80041008h
0x18006482a  mov     rcx, rax
0x18006482d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064833  mov     rcx, cs:WPP_GLOBAL_Control
0x18006483a  cmp     rcx, rdi
0x18006483d  jz      loc_180064D01
0x180064843  test    [rcx+1Ch], bl
0x180064846  jz      loc_180064D01
0x18006484c  cmp     byte ptr [rcx+19h], 2
0x180064850  jb      loc_180064D01
0x180064856  mov     edx, 281h
0x18006485b  jmp     loc_180064CEB
0x180064860  lea     ecx, [rsi-0C000h]
0x180064866  test    eax, eax
0x180064868  cmovz   ecx, esi
0x18006486b  mov     [rbp+var_40], ecx
0x18006486e  mov     [rbp+var_30], r9
0x180064872  test    r14, r14
0x180064875  jnz     short loc_1800648DD
0x180064877  lea     rax, [rbp+var_30]
0x18006487b  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x180064880  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x180064884  mov     r8, r13; struct IWbemObjectSink *
0x180064887  mov     rdx, [rbp+arg_30]; struct IWbemContext *
0x18006488b  mov     rcx, r15; this
0x18006488e  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x180064893  mov     esi, eax
0x180064895  test    eax, eax
0x180064897  jns     short loc_1800648D7
0x180064899  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006489f  mov     edx, esi
0x1800648a1  mov     rcx, rax
0x1800648a4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800648aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800648b1  cmp     rcx, rdi
0x1800648b4  jz      loc_1800646B0
0x1800648ba  test    [rcx+1Ch], bl
0x1800648bd  jz      loc_1800646B0
0x1800648c3  cmp     byte ptr [rcx+19h], 2
0x1800648c7  jb      loc_1800646B0
0x1800648cd  mov     edx, 282h
0x1800648d2  jmp     loc_18006469D
0x1800648d7  mov     r14, [rbp+arg_10]
0x1800648db  jmp     short loc_180064945
0x1800648dd  mov     rax, [r14]
0x1800648e0  lea     r8, [rbp+var_30]
0x1800648e4  xor     edx, edx
0x1800648e6  mov     rcx, r14
0x1800648e9  mov     rax, [rax+40h]
0x1800648ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648f2  mov     esi, eax
0x1800648f4  test    eax, eax
0x1800648f6  jns     short loc_180064936
0x1800648f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800648fe  mov     edx, esi
0x180064900  mov     rcx, rax
0x180064903  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064909  mov     rcx, cs:WPP_GLOBAL_Control
0x180064910  cmp     rcx, rdi
0x180064913  jz      loc_1800646B0
0x180064919  test    [rcx+1Ch], bl
0x18006491c  jz      loc_1800646B0
0x180064922  cmp     byte ptr [rcx+19h], 2
0x180064926  jb      loc_1800646B0
0x18006492c  mov     edx, 283h
0x180064931  jmp     loc_18006469D
0x180064936  mov     rax, [r14]
0x180064939  mov     rcx, r14
0x18006493c  mov     rax, [rax+8]
0x180064940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064945  mov     rax, [rbp+var_30]
0x180064949  mov     [rbp+var_18], rax
0x18006494d  mov     [rbp+var_10], r14
0x180064951  mov     rax, [rbp+arg_30]
0x180064955  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x18006495a  mov     r9, r14; struct _IWmiFinalizer *
0x18006495d  mov     r8, r12; unsigned __int16 *
0x180064960  lea     rdx, aIwbemservicesD; "IWbemServices::DeleteInstance"
0x180064967  mov     rcx, r15; this
0x18006496a  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x18006496f  mov     esi, eax
0x180064971  test    eax, eax
0x180064973  jns     short loc_1800649CE
0x180064975  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006497b  mov     edx, esi
0x18006497d  mov     rcx, rax
0x180064980  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064986  mov     rcx, cs:WPP_GLOBAL_Control
0x18006498d  cmp     rcx, rdi
0x180064990  jz      short loc_1800649B6
0x180064992  test    [rcx+1Ch], bl
0x180064995  jz      short loc_1800649B6
0x180064997  cmp     byte ptr [rcx+19h], 2
0x18006499b  jb      short loc_1800649B6
0x18006499d  mov     edx, 284h
0x1800649a2  mov     r9d, esi
0x1800649a5  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800649ac  mov     rcx, [rcx+10h]
0x1800649b0  call    WPP_SF_d
0x1800649b5  nop
0x1800649b6  lea     rcx, [rbp+var_10]; this
0x1800649ba  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800649bf  nop
0x1800649c0  lea     rcx, [rbp+var_18]; this
0x1800649c4  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800649c9  jmp     loc_1800646B0
0x1800649ce  mov     ecx, [r15+130h]
0x1800649d5  cmp     ecx, 0FFFFFFFFh
0x1800649d8  jz      short loc_180064A2C
0x1800649da  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x1800649e2  jz      short loc_180064A2C
0x1800649e4  lea     rax, aSemiSync; "(Semi)Sync"
0x1800649eb  lea     r8, aAsync; "Async"
0x1800649f2  test    r13, r13
0x1800649f5  cmovz   r8, rax
0x1800649f9  mov     rax, [r15+58h]
0x1800649fd  mov     [rsp+80h+var_48], rax
0x180064a02  mov     dword ptr [rsp+80h+var_50], ecx
0x180064a06  mov     eax, [r15+17Ch]
0x180064a0d  mov     dword ptr [rsp+80h+var_58], eax
0x180064a11  mov     eax, [rbp+var_40]
0x180064a14  mov     dword ptr [rsp+80h+var_60], eax
0x180064a18  mov     r9, r12
0x180064a1b  mov     edx, 4
0x180064a20  mov     ecx, [r14+2D4h]; unsigned int
0x180064a27  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x180064a2c  mov     [rbp+var_28], 0
0x180064a34  mov     rcx, [rbp+var_30]
0x180064a38  mov     rax, [rcx]
0x180064a3b  lea     r8, [rbp+var_28]
0x180064a3f  lea     rdx, IID_IWbemObjectSinkEx
0x180064a46  mov     rax, [rax]
0x180064a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a4e  mov     esi, eax
0x180064a50  test    eax, eax
0x180064a52  jns     short loc_180064A92
0x180064a54  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180064a5a  mov     edx, esi
0x180064a5c  mov     rcx, rax
0x180064a5f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a6c  cmp     rcx, rdi
0x180064a6f  jz      loc_1800649B6
0x180064a75  test    [rcx+1Ch], bl
0x180064a78  jz      loc_1800649B6
0x180064a7e  cmp     byte ptr [rcx+19h], 2
0x180064a82  jb      loc_1800649B6
0x180064a88  mov     edx, 285h
0x180064a8d  jmp     loc_1800649A2
0x180064a92  mov     rax, [rbp+var_28]
0x180064a96  mov     [rbp+var_20], rax
0x180064a9a  mov     [rbp+var_38], 0
0x180064aa2  mov     ecx, 70h ; 'p'
0x180064aa7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180064aad  mov     rsi, rax
0x180064ab0  mov     [rbp+var_8], rax
0x180064ab4  test    rax, rax
0x180064ab7  jz      short loc_180064AF2
0x180064ab9  mov     byte ptr [rsp+80h+var_60], 0; bool
0x180064abe  mov     r9, [rbp+arg_30]; struct IWbemContext *
0x180064ac2  mov     r8, [rbp+var_28]; struct IWbemObjectSinkEx *
0x180064ac6  mov     rdx, r15; struct CWbemNamespace *
0x180064ac9  mov     rcx, rax; this
0x180064acc  call    ??0CNamespaceReq@@QEAA@PEAVCWbemNamespace@@PEAUIWbemObjectSinkEx@@PEAUIWbemContext@@_N@Z; CNamespaceReq::CNamespaceReq(CWbemNamespace *,IWbemObjectSinkEx *,IWbemContext *,bool)
0x180064ad1  nop
0x180064ad2  lea     rax, ??_7CAsyncReq_DeleteInstanceAsync@@6B@; const CAsyncReq_DeleteInstanceAsync::`vftable'
0x180064ad9  mov     [rsi], rax
0x180064adc  lea     rcx, [rsi+60h]
0x180064ae0  mov     rdx, r12
0x180064ae3  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x180064ae9  nop
0x180064aea  mov     eax, [rbp+var_40]
0x180064aed  mov     [rsi+68h], eax
0x180064af0  jmp     short loc_180064AF4
0x180064af2  xor     esi, esi
0x180064af4  test    rsi, rsi
0x180064af7  jz      loc_180064C5A
  ... truncated ...
```
