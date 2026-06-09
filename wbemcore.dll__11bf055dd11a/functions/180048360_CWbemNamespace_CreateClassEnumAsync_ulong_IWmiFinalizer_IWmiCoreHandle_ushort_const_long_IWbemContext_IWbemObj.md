# CWbemNamespace::_CreateClassEnumAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180048360`
- end: `0x180048a49`
- name: `?_CreateClassEnumAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1769`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180047f00`
- `0x18009b580`

## callees

- `0x18000ae2c`
- `0x18000b140`
- `0x18000f474`
- `0x18001f6d0`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x180047ed0`
- `0x180048360`
- `0x180049580`
- `0x1800523c0`
- `0x180062ed0`
- `0x1800903d0`
- `0x1800a093c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18004883a`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18004883a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800487fb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800487fb`
- `wbemcomn!GetMemLogObject` at `0x180048396`
- `wbemcomn!GetMemLogObject` at `0x18004841a`
- `wbemcomn!GetMemLogObject` at `0x1800484c5`
- `wbemcomn!GetMemLogObject` at `0x18004851f`
- `wbemcomn!GetMemLogObject` at `0x180048571`
- `wbemcomn!GetMemLogObject` at `0x1800485f1`
- `wbemcomn!GetMemLogObject` at `0x180048651`
- `wbemcomn!GetMemLogObject` at `0x1800486cf`
- `wbemcomn!GetMemLogObject` at `0x180048794`
- `wbemcomn!GetMemLogObject` at `0x18004886a`
- `wbemcomn!GetMemLogObject` at `0x1800488d1`
- `wbemcomn!GetMemLogObject` at `0x180048957`
- `wbemcomn!GetMemLogObject` at `0x1800489b9`
- `wbemcomn!GetMemLogObject` at `0x180048396`
- `wbemcomn!GetMemLogObject` at `0x18004841a`
- `wbemcomn!GetMemLogObject` at `0x1800484c5`
- `wbemcomn!GetMemLogObject` at `0x18004851f`
- `wbemcomn!GetMemLogObject` at `0x180048571`
- `wbemcomn!GetMemLogObject` at `0x1800485f1`
- `wbemcomn!GetMemLogObject` at `0x180048651`
- `wbemcomn!GetMemLogObject` at `0x1800486cf`
- `wbemcomn!GetMemLogObject` at `0x180048794`
- `wbemcomn!GetMemLogObject` at `0x18004886a`
- `wbemcomn!GetMemLogObject` at `0x1800488d1`
- `wbemcomn!GetMemLogObject` at `0x180048957`
- `wbemcomn!GetMemLogObject` at `0x1800489b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800483a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004842a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800484d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004852f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004857f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800485fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004865c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800486da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004879f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004887a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800488dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048962`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800489c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800483a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004842a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800484d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004852f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004857f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800485fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004865c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800486da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004879f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004887a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800488dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048962`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800489c9`

## string_xrefs

- `0x180048404`: `Read (CreateClassEnum)`
- `0x1800486ba`: `IWbemServices::CreateClassEnum`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CWbemNamespace::_CreateClassEnumAsync(
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
  unsigned __int16 *v16; // r12
  int v17; // r8d
  CMemoryLog *v18; // rax
  struct IWbemObjectSink *v19; // r13
  int v20; // esi
  CMemoryLog *v21; // rax
  CClientCnt *v22; // rcx
  __int64 v23; // rdx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CClientCnt *v32; // rcx
  __int64 v33; // rdx
  const wchar_t *v34; // r8
  CMemoryLog *v35; // rax
  CNamespaceReq *v36; // rax
  CNamespaceReq *v37; // rsi
  struct IWbemContext *v38; // rax
  CMemoryLog *v39; // rax
  CClientCnt *v40; // rcx
  __int64 v41; // rdx
  int inited; // r15d
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  __int64 v45; // r9
  CMemoryLog *v46; // rax
  struct IWbemObjectSink **v47; // [rsp+20h] [rbp-60h]
  bool v48; // [rsp+28h] [rbp-58h]
  struct IWbemObjectSink *v49; // [rsp+28h] [rbp-58h]
  __int64 v50; // [rsp+30h] [rbp-50h]
  CNamespaceReq *v51; // [rsp+40h] [rbp-40h] BYREF
  struct IWbemObjectSink *v52; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSinkEx *v53; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v54; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSink *v55; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v56[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _IWmiFinalizer *v58; // [rsp+C0h] [rbp+40h] BYREF

  v58 = a3;
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
    v14 = 604;
    goto LABEL_6;
  }
  v16 = a5;
  if ( !CWbemNamespace::InnerAllowedWithSD(
          (CWbemNamespace *)v10,
          (struct CNtSecurityDescriptor *)(v10 + 216),
          1u,
          L"Read (CreateClassEnum)",
          a5,
          v48,
          1) )
  {
    v18 = GetMemLogObject();
    v11 = -2147217405;
    CMemoryLog::Write(v18, -2147217405);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v11;
    }
    v14 = 605;
    v15 = 2147749891LL;
    goto LABEL_7;
  }
  v19 = a8;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v20 = a6;
  }
  else
  {
    v20 = a6;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 606, v17, (_DWORD)v16, a6, (char)a8, *((_DWORD *)this + 76));
  }
  if ( !v8 && !v19 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v23 = 607;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  if ( v16 )
  {
    v24 = wcslen_max(v16, (unsigned int)g_IdentifierLimit);
    if ( v24 > v25 )
    {
      v26 = GetMemLogObject();
      v11 = -2147217300;
      CMemoryLog::Write(v26, -2147217300);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v14 = 608;
      v15 = 2147749996LL;
      goto LABEL_7;
    }
  }
  if ( (v20 & 0xFFFDFF7E) != 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v23 = 609;
    goto LABEL_35;
  }
  v52 = 0;
  if ( !v8 )
  {
    v11 = CWbemNamespace::CreateAsyncFinalizer(this, a7, v19, &v58, &v52);
    if ( v11 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v11);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v14 = 610;
      goto LABEL_6;
    }
    v8 = v58;
LABEL_50:
    v55 = v52;
    v56[0] = v8;
    v11 = CWbemNamespace::PublishInfo(this, L"IWbemServices::CreateClassEnum", v16, v8, a7);
    if ( v11 < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v11);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v33 = 612;
      goto LABEL_65;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v34 = L"Async";
      if ( !v19 )
        v34 = L"(Semi)Sync";
      LODWORD(v50) = *((_DWORD *)this + 76);
      LODWORD(v49) = *((_DWORD *)this + 95);
      LODWORD(v47) = a6;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 7, v34, v16, v47, v49, v50, *((_QWORD *)this + 11));
    }
    v53 = 0;
    v11 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v52->lpVtbl->QueryInterface)(
            v52,
            &IID_IWbemObjectSinkEx,
            &v53);
    if ( v11 < 0 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, v11);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v33 = 613;
LABEL_65:
      WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v11);
LABEL_98:
      CReleaseMe::release((CReleaseMe *)v56);
      CReleaseMe::release((CReleaseMe *)&v55);
      return (unsigned int)v11;
    }
    v54 = v53;
    v51 = 0;
    v36 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v37 = v36;
    v56[1] = v36;
    if ( v36 )
    {
      CNamespaceReq::CNamespaceReq(v36, this, v53, a7, 0);
      *(_QWORD *)v37 = &CAsyncReq_CreateClassEnumAsync::`vftable';
      WString::WString((CNamespaceReq *)((char *)v37 + 96), v16, 0);
      *((_DWORD *)v37 + 26) = a6;
    }
    else
    {
      v37 = 0;
    }
    if ( v37 )
    {
      std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v51);
      v51 = v37;
      v38 = (struct IWbemContext *)*((_QWORD *)v37 + 5);
      if ( v38 )
      {
        inited = CWbemNamespace::InitNewTask(this, v37, v8, a2, v38, v19);
        if ( inited < 0 )
        {
          v43 = GetMemLogObject();
          CMemoryLog::Write(v43, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              616,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v51);
          CReleaseMe::release((CReleaseMe *)&v54);
          v11 = inited;
          goto LABEL_98;
        }
        CReleaseMe::release((CReleaseMe *)&v55);
        v11 = ConfigMgr::EnqueueRequest(v37);
        if ( v11 >= 0 )
        {
          v51 = 0;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_97;
          }
          v41 = 618;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v44 = GetMemLogObject();
          CMemoryLog::Write(v44, v11);
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_97;
          }
          v41 = 617;
        }
        v45 = (unsigned int)v11;
        goto LABEL_96;
      }
      v39 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v39, -2147217402);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_97;
      }
      v41 = 615;
    }
    else
    {
      v46 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v46, -2147217402);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_97;
      }
      v41 = 614;
    }
    v45 = 2147749894LL;
LABEL_96:
    WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v45);
LABEL_97:
    std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v51);
    CReleaseMe::release((CReleaseMe *)&v54);
    goto LABEL_98;
  }
  v11 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
          v8,
          0,
          &v52);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    goto LABEL_50;
  }
  v30 = GetMemLogObject();
  CMemoryLog::Write(v30, v11);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v11;
  }
  v14 = 611;
LABEL_6:
  v15 = (unsigned int)v11;
LABEL_7:
  WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180048360  mov     rax, rsp
0x180048363  mov     [rax+8], rsi
0x180048367  mov     [rax+20h], rdi
0x18004836b  mov     [rax+18h], r8
0x18004836f  mov     [rax+10h], edx
0x180048372  push    rbp
0x180048373  push    r12
0x180048375  push    r13
0x180048377  push    r14
0x180048379  push    r15
0x18004837b  mov     rbp, rsp
0x18004837e  sub     rsp, 80h
0x180048385  mov     r14, r8
0x180048388  mov     r15, rcx
0x18004838b  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180048390  mov     esi, eax
0x180048392  test    eax, eax
0x180048394  jns     short loc_1800483EF
0x180048396  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004839c  mov     edx, esi
0x18004839e  mov     rcx, rax
0x1800483a1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800483a7  lea     rdi, WPP_GLOBAL_Control
0x1800483ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483b5  cmp     rcx, rdi
0x1800483b8  jz      loc_180048A2A
0x1800483be  test    byte ptr [rcx+1Ch], 1
0x1800483c2  jz      loc_180048A2A
0x1800483c8  cmp     byte ptr [rcx+19h], 2
0x1800483cc  jb      loc_180048A2A
0x1800483d2  mov     edx, 25Ch
0x1800483d7  mov     r9d, esi
0x1800483da  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800483e1  mov     rcx, [rcx+10h]
0x1800483e5  call    WPP_SF_d
0x1800483ea  jmp     loc_180048A2A
0x1800483ef  lea     rdx, [rcx+0D8h]; struct CNtSecurityDescriptor *
0x1800483f6  mov     [rsp+80h+var_50], 1; bool
0x1800483fb  mov     r12, [rbp+arg_20]
0x1800483ff  mov     [rsp+80h+var_60], r12; unsigned __int16 *
0x180048404  lea     r9, aReadCreateclas; "Read (CreateClassEnum)"
0x18004840b  mov     r8d, 1; unsigned int
0x180048411  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x180048416  test    al, al
0x180048418  jnz     short loc_18004846B
0x18004841a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048420  mov     esi, 80041003h
0x180048425  mov     edx, esi
0x180048427  mov     rcx, rax
0x18004842a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048430  lea     rdi, WPP_GLOBAL_Control
0x180048437  mov     rcx, cs:WPP_GLOBAL_Control
0x18004843e  cmp     rcx, rdi
0x180048441  jz      loc_180048A2A
0x180048447  test    byte ptr [rcx+1Ch], 1
0x18004844b  jz      loc_180048A2A
0x180048451  cmp     byte ptr [rcx+19h], 2
0x180048455  jb      loc_180048A2A
0x18004845b  mov     edx, 25Dh
0x180048460  mov     r9d, 80041003h
0x180048466  jmp     loc_1800483DA
0x18004846b  lea     rdi, WPP_GLOBAL_Control
0x180048472  mov     r13, [rbp+arg_38]
0x180048476  mov     rcx, cs:WPP_GLOBAL_Control
0x18004847d  cmp     rcx, rdi
0x180048480  jz      short loc_1800484B8
0x180048482  test    byte ptr [rcx+1Ch], 1
0x180048486  jz      short loc_1800484B8
0x180048488  mov     esi, [rbp+arg_28]
0x18004848b  cmp     byte ptr [rcx+19h], 5
0x18004848f  jb      short loc_1800484BB
0x180048491  mov     edx, 25Eh
0x180048496  mov     eax, [r15+130h]
0x18004849d  mov     dword ptr [rsp+80h+var_50], eax
0x1800484a1  mov     [rsp+80h+var_58], r13
0x1800484a6  mov     dword ptr [rsp+80h+var_60], esi
0x1800484aa  mov     r9, r12
0x1800484ad  mov     rcx, [rcx+10h]
0x1800484b1  call    WPP_SF_Sdql
0x1800484b6  jmp     short loc_1800484BB
0x1800484b8  mov     esi, [rbp+arg_28]
0x1800484bb  test    r14, r14
0x1800484be  jnz     short loc_180048507
0x1800484c0  test    r13, r13
0x1800484c3  jnz     short loc_180048507
0x1800484c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800484cb  mov     edx, 80041008h
0x1800484d0  mov     rcx, rax
0x1800484d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800484d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484e0  cmp     rcx, rdi
0x1800484e3  jz      loc_1800485B8
0x1800484e9  test    byte ptr [rcx+1Ch], 1
0x1800484ed  jz      loc_1800485B8
0x1800484f3  cmp     byte ptr [rcx+19h], 2
0x1800484f7  jb      loc_1800485B8
0x1800484fd  mov     edx, 25Fh
0x180048502  jmp     loc_1800485A2
0x180048507  test    r12, r12
0x18004850a  jz      short loc_180048569
0x18004850c  mov     edx, cs:?g_IdentifierLimit@@3KA; unsigned __int64
0x180048512  mov     rcx, r12; unsigned __int16 *
0x180048515  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x18004851a  cmp     rax, rdx
0x18004851d  jbe     short loc_180048569
0x18004851f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048525  mov     esi, 8004106Ch
0x18004852a  mov     edx, esi
0x18004852c  mov     rcx, rax
0x18004852f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048535  mov     rcx, cs:WPP_GLOBAL_Control
0x18004853c  cmp     rcx, rdi
0x18004853f  jz      loc_180048A2A
0x180048545  test    byte ptr [rcx+1Ch], 1
0x180048549  jz      loc_180048A2A
0x18004854f  cmp     byte ptr [rcx+19h], 2
0x180048553  jb      loc_180048A2A
0x180048559  mov     edx, 260h
0x18004855e  mov     r9d, 8004106Ch
0x180048564  jmp     loc_1800483DA
0x180048569  test    esi, 0FFFDFF7Eh
0x18004856f  jz      short loc_1800485C2
0x180048571  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048577  mov     edx, 80041008h
0x18004857c  mov     rcx, rax
0x18004857f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048585  mov     rcx, cs:WPP_GLOBAL_Control
0x18004858c  cmp     rcx, rdi
0x18004858f  jz      short loc_1800485B8
0x180048591  test    byte ptr [rcx+1Ch], 1
0x180048595  jz      short loc_1800485B8
0x180048597  cmp     byte ptr [rcx+19h], 2
0x18004859b  jb      short loc_1800485B8
0x18004859d  mov     edx, 261h
0x1800485a2  mov     r9d, 80041008h
0x1800485a8  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800485af  mov     rcx, [rcx+10h]
0x1800485b3  call    WPP_SF_d
0x1800485b8  mov     eax, 80041008h
0x1800485bd  jmp     loc_180048A2C
0x1800485c2  mov     [rbp+var_38], 0
0x1800485ca  test    r14, r14
0x1800485cd  jnz     short loc_180048636
0x1800485cf  lea     rax, [rbp+var_38]
0x1800485d3  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x1800485d8  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x1800485dc  mov     r8, r13; struct IWbemObjectSink *
0x1800485df  mov     rdx, [rbp+arg_30]; struct IWbemContext *
0x1800485e3  mov     rcx, r15; this
0x1800485e6  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x1800485eb  mov     esi, eax
0x1800485ed  test    eax, eax
0x1800485ef  jns     short loc_180048630
0x1800485f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800485f7  mov     edx, esi
0x1800485f9  mov     rcx, rax
0x1800485fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048602  mov     rcx, cs:WPP_GLOBAL_Control
0x180048609  cmp     rcx, rdi
0x18004860c  jz      loc_180048A2A
0x180048612  test    byte ptr [rcx+1Ch], 1
0x180048616  jz      loc_180048A2A
0x18004861c  cmp     byte ptr [rcx+19h], 2
0x180048620  jb      loc_180048A2A
0x180048626  mov     edx, 262h
0x18004862b  jmp     loc_1800483D7
0x180048630  mov     r14, [rbp+arg_10]
0x180048634  jmp     short loc_18004869F
0x180048636  mov     rax, [r14]
0x180048639  lea     r8, [rbp+var_38]
0x18004863d  xor     edx, edx
0x18004863f  mov     rcx, r14
0x180048642  mov     rax, [rax+40h]
0x180048646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004864b  mov     esi, eax
0x18004864d  test    eax, eax
0x18004864f  jns     short loc_180048690
0x180048651  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048657  mov     edx, esi
0x180048659  mov     rcx, rax
0x18004865c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048662  mov     rcx, cs:WPP_GLOBAL_Control
0x180048669  cmp     rcx, rdi
0x18004866c  jz      loc_180048A2A
0x180048672  test    byte ptr [rcx+1Ch], 1
0x180048676  jz      loc_180048A2A
0x18004867c  cmp     byte ptr [rcx+19h], 2
0x180048680  jb      loc_180048A2A
0x180048686  mov     edx, 263h
0x18004868b  jmp     loc_1800483D7
0x180048690  mov     rax, [r14]
0x180048693  mov     rcx, r14
0x180048696  mov     rax, [rax+8]
0x18004869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004869f  mov     rax, [rbp+var_38]
0x1800486a3  mov     [rbp+var_20], rax
0x1800486a7  mov     [rbp+var_18], r14
0x1800486ab  mov     rax, [rbp+arg_30]
0x1800486af  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x1800486b4  mov     r9, r14; struct _IWmiFinalizer *
0x1800486b7  mov     r8, r12; unsigned __int16 *
0x1800486ba  lea     rdx, aIwbemservicesC; "IWbemServices::CreateClassEnum"
0x1800486c1  mov     rcx, r15; this
0x1800486c4  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x1800486c9  mov     esi, eax
0x1800486cb  test    eax, eax
0x1800486cd  jns     short loc_18004870E
0x1800486cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800486d5  mov     edx, esi
0x1800486d7  mov     rcx, rax
0x1800486da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800486e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486e7  cmp     rcx, rdi
0x1800486ea  jz      loc_180048A17
0x1800486f0  test    byte ptr [rcx+1Ch], 1
0x1800486f4  jz      loc_180048A17
0x1800486fa  cmp     byte ptr [rcx+19h], 2
0x1800486fe  jb      loc_180048A17
0x180048704  mov     edx, 264h
0x180048709  jmp     loc_1800487CE
0x18004870e  mov     ecx, [r15+130h]
0x180048715  cmp     ecx, 0FFFFFFFFh
0x180048718  jz      short loc_18004876C
0x18004871a  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x180048722  jz      short loc_18004876C
0x180048724  lea     rax, aSemiSync; "(Semi)Sync"
0x18004872b  lea     r8, aAsync; "Async"
0x180048732  test    r13, r13
0x180048735  cmovz   r8, rax
0x180048739  mov     rax, [r15+58h]
0x18004873d  mov     [rsp+80h+var_48], rax
0x180048742  mov     dword ptr [rsp+80h+var_50], ecx
0x180048746  mov     eax, [r15+17Ch]
0x18004874d  mov     dword ptr [rsp+80h+var_58], eax
0x180048751  mov     eax, [rbp+arg_28]
0x180048754  mov     dword ptr [rsp+80h+var_60], eax
0x180048758  mov     r9, r12
0x18004875b  mov     edx, 7
0x180048760  mov     ecx, [r14+2D4h]; unsigned int
0x180048767  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x18004876c  mov     [rbp+var_30], 0
0x180048774  mov     rcx, [rbp+var_38]
0x180048778  mov     rax, [rcx]
0x18004877b  lea     r8, [rbp+var_30]
0x18004877f  lea     rdx, IID_IWbemObjectSinkEx
0x180048786  mov     rax, [rax]
0x180048789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004878e  mov     esi, eax
0x180048790  test    eax, eax
0x180048792  jns     short loc_1800487E6
0x180048794  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004879a  mov     edx, esi
0x18004879c  mov     rcx, rax
0x18004879f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800487a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487ac  cmp     rcx, rdi
0x1800487af  jz      loc_180048A17
0x1800487b5  test    byte ptr [rcx+1Ch], 1
0x1800487b9  jz      loc_180048A17
0x1800487bf  cmp     byte ptr [rcx+19h], 2
0x1800487c3  jb      loc_180048A17
0x1800487c9  mov     edx, 265h
0x1800487ce  mov     r9d, esi
0x1800487d1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800487d8  mov     rcx, [rcx+10h]
0x1800487dc  call    WPP_SF_d
0x1800487e1  jmp     loc_180048A17
0x1800487e6  mov     rax, [rbp+var_30]
0x1800487ea  mov     [rbp+var_28], rax
0x1800487ee  mov     [rbp+var_40], 0
0x1800487f6  mov     ecx, 70h ; 'p'
0x1800487fb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180048801  mov     rsi, rax
0x180048804  mov     [rbp+var_10], rax
0x180048808  test    rax, rax
0x18004880b  jz      short loc_180048849
0x18004880d  mov     byte ptr [rsp+80h+var_60], 0; bool
0x180048812  mov     r9, [rbp+arg_30]; struct IWbemContext *
0x180048816  mov     r8, [rbp+var_30]; struct IWbemObjectSinkEx *
0x18004881a  mov     rdx, r15; struct CWbemNamespace *
0x18004881d  mov     rcx, rax; this
0x180048820  call    ??0CNamespaceReq@@QEAA@PEAVCWbemNamespace@@PEAUIWbemObjectSinkEx@@PEAUIWbemContext@@_N@Z; CNamespaceReq::CNamespaceReq(CWbemNamespace *,IWbemObjectSinkEx *,IWbemContext *,bool)
0x180048825  nop
0x180048826  lea     rax, ??_7CAsyncReq_CreateClassEnumAsync@@6B@; const CAsyncReq_CreateClassEnumAsync::`vftable'
0x18004882d  mov     [rsi], rax
0x180048830  lea     rcx, [rsi+60h]
0x180048834  xor     r8d, r8d
0x180048837  mov     rdx, r12
0x18004883a  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x180048840  nop
0x180048841  mov     eax, [rbp+arg_28]
0x180048844  mov     [rsi+68h], eax
0x180048847  jmp     short loc_18004884B
0x180048849  xor     esi, esi
0x18004884b  test    rsi, rsi
0x18004884e  jz      loc_1800489B9
0x180048854  lea     rcx, [rbp+var_40]
0x180048858  call    ?_Delete@?$unique_ptr@VCAsyncReq_CreateClassEnumAsync@@U?$default_delete@VCAsyncReq_CreateClassEnumAsync@@@std@@@std@@AEAAXXZ; std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(void)
0x18004885d  mov     [rbp+var_40], rsi
0x180048861  mov     rax, [rsi+28h]
  ... truncated ...
```
