# CWbemNamespace::_CreateInstanceEnumAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1800477b0`
- end: `0x180047ec7`
- name: `?_CreateInstanceEnumAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1815`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180047340`
- `0x180075d00`

## callees

- `0x18000ae2c`
- `0x18000b140`
- `0x18000f474`
- `0x18001f6d0`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x1800477b0`
- `0x180047ed0`
- `0x180049580`
- `0x1800523c0`
- `0x180062ed0`
- `0x1800903d0`
- `0x1800a093c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x180047c7e`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x180047c7e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180047c3f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180047c3f`
- `wbemcomn!GetMemLogObject` at `0x1800477e6`
- `wbemcomn!GetMemLogObject` at `0x180047863`
- `wbemcomn!GetMemLogObject` at `0x180047905`
- `wbemcomn!GetMemLogObject` at `0x18004796e`
- `wbemcomn!GetMemLogObject` at `0x1800479c0`
- `wbemcomn!GetMemLogObject` at `0x180047a2d`
- `wbemcomn!GetMemLogObject` at `0x180047a8d`
- `wbemcomn!GetMemLogObject` at `0x180047b0b`
- `wbemcomn!GetMemLogObject` at `0x180047beb`
- `wbemcomn!GetMemLogObject` at `0x180047cb5`
- `wbemcomn!GetMemLogObject` at `0x180047d1c`
- `wbemcomn!GetMemLogObject` at `0x180047da2`
- `wbemcomn!GetMemLogObject` at `0x180047dfc`
- `wbemcomn!GetMemLogObject` at `0x180047e5e`
- `wbemcomn!GetMemLogObject` at `0x1800477e6`
- `wbemcomn!GetMemLogObject` at `0x180047863`
- `wbemcomn!GetMemLogObject` at `0x180047905`
- `wbemcomn!GetMemLogObject` at `0x18004796e`
- `wbemcomn!GetMemLogObject` at `0x1800479c0`
- `wbemcomn!GetMemLogObject` at `0x180047a2d`
- `wbemcomn!GetMemLogObject` at `0x180047a8d`
- `wbemcomn!GetMemLogObject` at `0x180047b0b`
- `wbemcomn!GetMemLogObject` at `0x180047beb`
- `wbemcomn!GetMemLogObject` at `0x180047cb5`
- `wbemcomn!GetMemLogObject` at `0x180047d1c`
- `wbemcomn!GetMemLogObject` at `0x180047da2`
- `wbemcomn!GetMemLogObject` at `0x180047dfc`
- `wbemcomn!GetMemLogObject` at `0x180047e5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800477f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047873`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047913`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004797e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800479ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047a38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047a98`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047b16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047bf6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047cc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047d28`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047dad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800477f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047873`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047913`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004797e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800479ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047a38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047a98`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047b16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047bf6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047cc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047d28`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047dad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e0c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e6c`

## string_xrefs

- `0x18004784a`: `Read (CreateInstanceEnum)`
- `0x180047af6`: `IWbemServices::CreateInstanceEnum`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CWbemNamespace::_CreateInstanceEnumAsync(
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
  __int64 v10; // rcx
  int v11; // esi
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned __int16 *v17; // r12
  int v18; // r8d
  CMemoryLog *v19; // rax
  struct IWbemObjectSink *v20; // r13
  int v21; // esi
  CMemoryLog *v22; // rax
  CClientCnt *v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  struct IWbemObjectSink *v26; // r9
  unsigned __int64 v27; // rdx
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CClientCnt *v33; // rcx
  __int64 v34; // rdx
  const wchar_t *v35; // r8
  CMemoryLog *v36; // rax
  CNamespaceReq *v37; // rax
  CNamespaceReq *v38; // rsi
  struct IWbemContext *v39; // rax
  CMemoryLog *v40; // rax
  CClientCnt *v41; // rcx
  __int64 v42; // rdx
  int inited; // r15d
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  __int64 v46; // r9
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  struct IWbemObjectSink **v49; // [rsp+20h] [rbp-60h]
  bool v50; // [rsp+28h] [rbp-58h]
  struct IWbemObjectSink *v51; // [rsp+28h] [rbp-58h]
  __int64 v52; // [rsp+30h] [rbp-50h]
  CNamespaceReq *v53; // [rsp+40h] [rbp-40h] BYREF
  struct IWbemObjectSink *v54; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSinkEx *v55; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v56; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSink *v57; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v58[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _IWmiFinalizer *v60; // [rsp+C0h] [rbp+40h] BYREF

  v60 = a3;
  v8 = a3;
  v11 = CWbemNamespace::CheckNs(this);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v11;
    }
    v14 = 651;
    goto LABEL_6;
  }
  v17 = a5;
  if ( !CWbemNamespace::InnerAllowedWithSD(
          (CWbemNamespace *)v10,
          (struct CNtSecurityDescriptor *)(v10 + 216),
          1u,
          L"Read (CreateInstanceEnum)",
          a5,
          v50,
          1) )
  {
    v19 = GetMemLogObject();
    v11 = -2147217405;
    CMemoryLog::Write(v19, -2147217405);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v11;
    }
    v14 = 652;
    v15 = 2147749891LL;
    goto LABEL_7;
  }
  v20 = a8;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v21 = a6;
  }
  else
  {
    v21 = a6;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 653, v18, (_DWORD)v17, a6, (char)a8, *((_DWORD *)this + 76));
  }
  if ( v8 || v20 )
  {
    if ( !v17 || !*v17 )
    {
      v48 = GetMemLogObject();
      CMemoryLog::Write(v48, -2147217400);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v24 = 655;
      goto LABEL_103;
    }
    v25 = wcslen_max(v17, (unsigned int)g_IdentifierLimit);
    if ( v25 > v27 )
    {
      v28 = GetMemLogObject();
      v11 = -2147217300;
      CMemoryLog::Write(v28, -2147217300);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v14 = 656;
      v15 = 2147749996LL;
      goto LABEL_7;
    }
    if ( (v21 & 0xFFFDFD7E) != 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, -2147217400);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v24 = 657;
      goto LABEL_103;
    }
    v54 = v26;
    if ( v8 )
    {
      v11 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
              v8,
              0,
              &v54);
      if ( v11 < 0 )
      {
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, v11);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v11;
        }
        v14 = 659;
LABEL_6:
        v15 = (unsigned int)v11;
LABEL_7:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v15);
        return (unsigned int)v11;
      }
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    else
    {
      v11 = CWbemNamespace::CreateAsyncFinalizer(this, a7, v20, &v60, &v54);
      if ( v11 < 0 )
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, v11);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v11;
        }
        v14 = 658;
        goto LABEL_6;
      }
      v8 = v60;
    }
    v57 = v54;
    v58[0] = v8;
    v11 = CWbemNamespace::PublishInfo(this, L"IWbemServices::CreateInstanceEnum", v17, v8, a7);
    if ( v11 < 0 )
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, v11);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_56;
      }
      v34 = 660;
      goto LABEL_55;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v35 = L"Async";
      if ( !v20 )
        v35 = L"(Semi)Sync";
      LODWORD(v52) = *((_DWORD *)this + 76);
      LODWORD(v51) = *((_DWORD *)this + 95);
      LODWORD(v49) = a6;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 6, v35, v17, v49, v51, v52, *((_QWORD *)this + 11));
    }
    v55 = 0;
    v11 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v54->lpVtbl->QueryInterface)(
            v54,
            &IID_IWbemObjectSinkEx,
            &v55);
    if ( v11 < 0 )
    {
      v36 = GetMemLogObject();
      CMemoryLog::Write(v36, v11);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_56;
      }
      v34 = 661;
LABEL_55:
      WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v11);
LABEL_56:
      CReleaseMe::release((CReleaseMe *)v58);
      CReleaseMe::release((CReleaseMe *)&v57);
      return (unsigned int)v11;
    }
    v56 = v55;
    v53 = 0;
    v37 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v38 = v37;
    v58[1] = v37;
    if ( v37 )
    {
      CNamespaceReq::CNamespaceReq(v37, this, v55, a7, 0);
      *(_QWORD *)v38 = &CAsyncReq_CreateInstanceEnumAsync::`vftable';
      WString::WString((CNamespaceReq *)((char *)v38 + 96), v17, 0);
      *((_DWORD *)v38 + 26) = a6;
    }
    else
    {
      v38 = 0;
    }
    if ( v38 )
    {
      std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v53);
      v53 = v38;
      v39 = (struct IWbemContext *)*((_QWORD *)v38 + 5);
      if ( v39 )
      {
        inited = CWbemNamespace::InitNewTask(this, v38, v8, a2, v39, v20);
        if ( inited < 0 )
        {
          v44 = GetMemLogObject();
          CMemoryLog::Write(v44, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              664,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v53);
          CReleaseMe::release((CReleaseMe *)&v56);
          v11 = inited;
          goto LABEL_56;
        }
        CReleaseMe::release((CReleaseMe *)&v57);
        v11 = ConfigMgr::EnqueueRequest(v38);
        if ( v11 >= 0 )
        {
          v53 = 0;
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_98;
          }
          v42 = 666;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v45 = GetMemLogObject();
          CMemoryLog::Write(v45, v11);
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_98;
          }
          v42 = 665;
        }
        v46 = (unsigned int)v11;
        goto LABEL_97;
      }
      v40 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v40, -2147217402);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v42 = 663;
    }
    else
    {
      v47 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v47, -2147217402);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v42 = 662;
    }
    v46 = 2147749894LL;
LABEL_97:
    WPP_SF_d(*((_QWORD *)v41 + 2), v42, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v46);
LABEL_98:
    std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v53);
    CReleaseMe::release((CReleaseMe *)&v56);
    goto LABEL_56;
  }
  v22 = GetMemLogObject();
  CMemoryLog::Write(v22, -2147217400);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749896LL;
  }
  v24 = 654;
LABEL_103:
  WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
  return 2147749896LL;
}

```

## disassembly

```asm
0x1800477b0  mov     rax, rsp
0x1800477b3  mov     [rax+8], rsi
0x1800477b7  mov     [rax+20h], rdi
0x1800477bb  mov     [rax+18h], r8
0x1800477bf  mov     [rax+10h], edx
0x1800477c2  push    rbp
0x1800477c3  push    r12
0x1800477c5  push    r13
0x1800477c7  push    r14
0x1800477c9  push    r15
0x1800477cb  mov     rbp, rsp
0x1800477ce  sub     rsp, 80h
0x1800477d5  mov     r14, r8
0x1800477d8  mov     r15, rcx
0x1800477db  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x1800477e0  mov     esi, eax
0x1800477e2  test    eax, eax
0x1800477e4  jns     short loc_180047835
0x1800477e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800477ec  mov     edx, esi
0x1800477ee  mov     rcx, rax
0x1800477f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800477f7  lea     rdi, WPP_GLOBAL_Control
0x1800477fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180047805  cmp     rcx, rdi
0x180047808  jz      short loc_18004782E
0x18004780a  test    byte ptr [rcx+1Ch], 1
0x18004780e  jz      short loc_18004782E
0x180047810  cmp     byte ptr [rcx+19h], 2
0x180047814  jb      short loc_18004782E
0x180047816  mov     edx, 28Bh
0x18004781b  mov     r9d, esi
0x18004781e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180047825  mov     rcx, [rcx+10h]
0x180047829  call    WPP_SF_d
0x18004782e  mov     eax, esi
0x180047830  jmp     loc_180047EAA
0x180047835  lea     rdx, [rcx+0D8h]; struct CNtSecurityDescriptor *
0x18004783c  mov     [rsp+80h+var_50], 1; bool
0x180047841  mov     r12, [rbp+arg_20]
0x180047845  mov     [rsp+80h+var_60], r12; unsigned __int16 *
0x18004784a  lea     r9, aReadCreateinst; "Read (CreateInstanceEnum)"
0x180047851  mov     r8d, 1; unsigned int
0x180047857  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18004785c  xor     r9d, r9d
0x18004785f  test    al, al
0x180047861  jnz     short loc_1800478A8
0x180047863  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047869  mov     esi, 80041003h
0x18004786e  mov     edx, esi
0x180047870  mov     rcx, rax
0x180047873  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047879  lea     rdi, WPP_GLOBAL_Control
0x180047880  mov     rcx, cs:WPP_GLOBAL_Control
0x180047887  cmp     rcx, rdi
0x18004788a  jz      short loc_18004782E
0x18004788c  test    byte ptr [rcx+1Ch], 1
0x180047890  jz      short loc_18004782E
0x180047892  cmp     byte ptr [rcx+19h], 2
0x180047896  jb      short loc_18004782E
0x180047898  mov     edx, 28Ch
0x18004789d  mov     r9d, 80041003h
0x1800478a3  jmp     loc_18004781E
0x1800478a8  lea     rdi, WPP_GLOBAL_Control
0x1800478af  mov     r13, [rbp+arg_38]
0x1800478b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478ba  cmp     rcx, rdi
0x1800478bd  jz      short loc_1800478F8
0x1800478bf  test    byte ptr [rcx+1Ch], 1
0x1800478c3  jz      short loc_1800478F8
0x1800478c5  mov     esi, [rbp+arg_28]
0x1800478c8  cmp     byte ptr [rcx+19h], 5
0x1800478cc  jb      short loc_1800478FB
0x1800478ce  mov     edx, 28Dh
0x1800478d3  mov     eax, [r15+130h]
0x1800478da  mov     dword ptr [rsp+80h+var_50], eax
0x1800478de  mov     [rsp+80h+var_58], r13
0x1800478e3  mov     dword ptr [rsp+80h+var_60], esi
0x1800478e7  mov     r9, r12
0x1800478ea  mov     rcx, [rcx+10h]
0x1800478ee  call    WPP_SF_Sdql
0x1800478f3  xor     r9d, r9d
0x1800478f6  jmp     short loc_1800478FB
0x1800478f8  mov     esi, [rbp+arg_28]
0x1800478fb  test    r14, r14
0x1800478fe  jnz     short loc_180047947
0x180047900  test    r13, r13
0x180047903  jnz     short loc_180047947
0x180047905  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004790b  mov     edx, 80041008h
0x180047910  mov     rcx, rax
0x180047913  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047919  mov     rcx, cs:WPP_GLOBAL_Control
0x180047920  cmp     rcx, rdi
0x180047923  jz      loc_180047EA5
0x180047929  test    byte ptr [rcx+1Ch], 1
0x18004792d  jz      loc_180047EA5
0x180047933  cmp     byte ptr [rcx+19h], 2
0x180047937  jb      loc_180047EA5
0x18004793d  mov     edx, 28Eh
0x180047942  jmp     loc_180047E8F
0x180047947  test    r12, r12
0x18004794a  jz      loc_180047E5E
0x180047950  cmp     [r12], r9w
0x180047955  jz      loc_180047E5E
0x18004795b  mov     edx, cs:?g_IdentifierLimit@@3KA; unsigned __int64
0x180047961  mov     rcx, r12; unsigned __int16 *
0x180047964  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x180047969  cmp     rax, rdx
0x18004796c  jbe     short loc_1800479B8
0x18004796e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047974  mov     esi, 8004106Ch
0x180047979  mov     edx, esi
0x18004797b  mov     rcx, rax
0x18004797e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047984  mov     rcx, cs:WPP_GLOBAL_Control
0x18004798b  cmp     rcx, rdi
0x18004798e  jz      loc_18004782E
0x180047994  test    byte ptr [rcx+1Ch], 1
0x180047998  jz      loc_18004782E
0x18004799e  cmp     byte ptr [rcx+19h], 2
0x1800479a2  jb      loc_18004782E
0x1800479a8  mov     edx, 290h
0x1800479ad  mov     r9d, 8004106Ch
0x1800479b3  jmp     loc_18004781E
0x1800479b8  test    esi, 0FFFDFD7Eh
0x1800479be  jz      short loc_180047A02
0x1800479c0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800479c6  mov     edx, 80041008h
0x1800479cb  mov     rcx, rax
0x1800479ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800479d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800479db  cmp     rcx, rdi
0x1800479de  jz      loc_180047EA5
0x1800479e4  test    byte ptr [rcx+1Ch], 1
0x1800479e8  jz      loc_180047EA5
0x1800479ee  cmp     byte ptr [rcx+19h], 2
0x1800479f2  jb      loc_180047EA5
0x1800479f8  mov     edx, 291h
0x1800479fd  jmp     loc_180047E8F
0x180047a02  mov     [rbp+var_38], r9
0x180047a06  test    r14, r14
0x180047a09  jnz     short loc_180047A72
0x180047a0b  lea     rax, [rbp+var_38]
0x180047a0f  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x180047a14  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x180047a18  mov     r8, r13; struct IWbemObjectSink *
0x180047a1b  mov     rdx, [rbp+arg_30]; struct IWbemContext *
0x180047a1f  mov     rcx, r15; this
0x180047a22  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x180047a27  mov     esi, eax
0x180047a29  test    eax, eax
0x180047a2b  jns     short loc_180047A6C
0x180047a2d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047a33  mov     edx, esi
0x180047a35  mov     rcx, rax
0x180047a38  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a45  cmp     rcx, rdi
0x180047a48  jz      loc_18004782E
0x180047a4e  test    byte ptr [rcx+1Ch], 1
0x180047a52  jz      loc_18004782E
0x180047a58  cmp     byte ptr [rcx+19h], 2
0x180047a5c  jb      loc_18004782E
0x180047a62  mov     edx, 292h
0x180047a67  jmp     loc_18004781B
0x180047a6c  mov     r14, [rbp+arg_10]
0x180047a70  jmp     short loc_180047ADB
0x180047a72  mov     rax, [r14]
0x180047a75  lea     r8, [rbp+var_38]
0x180047a79  xor     edx, edx
0x180047a7b  mov     rcx, r14
0x180047a7e  mov     rax, [rax+40h]
0x180047a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a87  mov     esi, eax
0x180047a89  test    eax, eax
0x180047a8b  jns     short loc_180047ACC
0x180047a8d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047a93  mov     edx, esi
0x180047a95  mov     rcx, rax
0x180047a98  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047aa5  cmp     rcx, rdi
0x180047aa8  jz      loc_18004782E
0x180047aae  test    byte ptr [rcx+1Ch], 1
0x180047ab2  jz      loc_18004782E
0x180047ab8  cmp     byte ptr [rcx+19h], 2
0x180047abc  jb      loc_18004782E
0x180047ac2  mov     edx, 293h
0x180047ac7  jmp     loc_18004781B
0x180047acc  mov     rax, [r14]
0x180047acf  mov     rcx, r14
0x180047ad2  mov     rax, [rax+8]
0x180047ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047adb  mov     rax, [rbp+var_38]
0x180047adf  mov     [rbp+var_20], rax
0x180047ae3  mov     [rbp+var_18], r14
0x180047ae7  mov     rax, [rbp+arg_30]
0x180047aeb  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x180047af0  mov     r9, r14; struct _IWmiFinalizer *
0x180047af3  mov     r8, r12; unsigned __int16 *
0x180047af6  lea     rdx, aIwbemservicesC_1; "IWbemServices::CreateInstanceEnum"
0x180047afd  mov     rcx, r15; this
0x180047b00  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x180047b05  mov     esi, eax
0x180047b07  test    eax, eax
0x180047b09  jns     short loc_180047B65
0x180047b0b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047b11  mov     edx, esi
0x180047b13  mov     rcx, rax
0x180047b16  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b23  cmp     rcx, rdi
0x180047b26  jz      short loc_180047B4D
0x180047b28  test    byte ptr [rcx+1Ch], 1
0x180047b2c  jz      short loc_180047B4D
0x180047b2e  cmp     byte ptr [rcx+19h], 2
0x180047b32  jb      short loc_180047B4D
0x180047b34  mov     edx, 294h
0x180047b39  mov     r9d, esi
0x180047b3c  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180047b43  mov     rcx, [rcx+10h]
0x180047b47  call    WPP_SF_d
0x180047b4c  nop
0x180047b4d  lea     rcx, [rbp+var_18]; this
0x180047b51  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180047b56  nop
0x180047b57  lea     rcx, [rbp+var_20]; this
0x180047b5b  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180047b60  jmp     loc_18004782E
0x180047b65  mov     ecx, [r15+130h]
0x180047b6c  cmp     ecx, 0FFFFFFFFh
0x180047b6f  jz      short loc_180047BC3
0x180047b71  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x180047b79  jz      short loc_180047BC3
0x180047b7b  lea     rax, aSemiSync; "(Semi)Sync"
0x180047b82  lea     r8, aAsync; "Async"
0x180047b89  test    r13, r13
0x180047b8c  cmovz   r8, rax
0x180047b90  mov     rax, [r15+58h]
0x180047b94  mov     [rsp+80h+var_48], rax
0x180047b99  mov     dword ptr [rsp+80h+var_50], ecx
0x180047b9d  mov     eax, [r15+17Ch]
0x180047ba4  mov     dword ptr [rsp+80h+var_58], eax
0x180047ba8  mov     eax, [rbp+arg_28]
0x180047bab  mov     dword ptr [rsp+80h+var_60], eax
0x180047baf  mov     r9, r12
0x180047bb2  mov     edx, 6
0x180047bb7  mov     ecx, [r14+2D4h]; unsigned int
0x180047bbe  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x180047bc3  mov     [rbp+var_30], 0
0x180047bcb  mov     rcx, [rbp+var_38]
0x180047bcf  mov     rax, [rcx]
0x180047bd2  lea     r8, [rbp+var_30]
0x180047bd6  lea     rdx, IID_IWbemObjectSinkEx
0x180047bdd  mov     rax, [rax]
0x180047be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047be5  mov     esi, eax
0x180047be7  test    eax, eax
0x180047be9  jns     short loc_180047C2A
0x180047beb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047bf1  mov     edx, esi
0x180047bf3  mov     rcx, rax
0x180047bf6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c03  cmp     rcx, rdi
0x180047c06  jz      loc_180047B4D
0x180047c0c  test    byte ptr [rcx+1Ch], 1
0x180047c10  jz      loc_180047B4D
0x180047c16  cmp     byte ptr [rcx+19h], 2
0x180047c1a  jb      loc_180047B4D
0x180047c20  mov     edx, 295h
0x180047c25  jmp     loc_180047B39
0x180047c2a  mov     rax, [rbp+var_30]
0x180047c2e  mov     [rbp+var_28], rax
0x180047c32  mov     [rbp+var_40], 0
0x180047c3a  mov     ecx, 70h ; 'p'
0x180047c3f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180047c45  mov     rsi, rax
0x180047c48  mov     [rbp+var_10], rax
0x180047c4c  test    rax, rax
0x180047c4f  jz      short loc_180047C90
0x180047c51  mov     byte ptr [rsp+80h+var_60], 0; bool
0x180047c56  mov     r9, [rbp+arg_30]; struct IWbemContext *
0x180047c5a  mov     r8, [rbp+var_30]; struct IWbemObjectSinkEx *
0x180047c5e  mov     rdx, r15; struct CWbemNamespace *
0x180047c61  mov     rcx, rax; this
0x180047c64  call    ??0CNamespaceReq@@QEAA@PEAVCWbemNamespace@@PEAUIWbemObjectSinkEx@@PEAUIWbemContext@@_N@Z; CNamespaceReq::CNamespaceReq(CWbemNamespace *,IWbemObjectSinkEx *,IWbemContext *,bool)
0x180047c69  nop
0x180047c6a  lea     rax, ??_7CAsyncReq_CreateInstanceEnumAsync@@6B@; const CAsyncReq_CreateInstanceEnumAsync::`vftable'
0x180047c71  mov     [rsi], rax
0x180047c74  lea     rcx, [rsi+60h]
0x180047c78  xor     r8d, r8d
0x180047c7b  mov     rdx, r12
0x180047c7e  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x180047c84  nop
0x180047c85  mov     eax, [rbp+arg_28]
0x180047c88  mov     [rsi+68h], eax
0x180047c8b  xor     r12d, r12d
0x180047c8e  jmp     short loc_180047C96
  ... truncated ...
```
