# CWbemNamespace::Exec_GetClass(ushort const *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18003c2c0`
- end: `0x18003cd7f`
- name: `?Exec_GetClass@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `2751`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, OLECHAR *psz@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ad40`

## callees

- `0x180007fb0`
- `0x18000b140`
- `0x18000b17c`
- `0x18000b1dc`
- `0x18000b46c`
- `0x18001307c`
- `0x18002c9f0`
- `0x180039c50`
- `0x18003c2c0`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18003d010`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18003c352`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18003c352`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18003c366`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c5b1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c5b1`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003c68b`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18003c68b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003c649`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003c649`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003c664`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003c664`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003c676`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003c676`
- `wbemcomn!GetMemLogObject` at `0x18003c794`
- `wbemcomn!GetMemLogObject` at `0x18003c8fa`
- `wbemcomn!GetMemLogObject` at `0x18003c949`
- `wbemcomn!GetMemLogObject` at `0x18003c9b3`
- `wbemcomn!GetMemLogObject` at `0x18003ca65`
- `wbemcomn!GetMemLogObject` at `0x18003ca85`
- `wbemcomn!GetMemLogObject` at `0x18003cb50`
- `wbemcomn!GetMemLogObject` at `0x18003cb94`
- `wbemcomn!GetMemLogObject` at `0x18003cbdf`
- `wbemcomn!GetMemLogObject` at `0x18003cc5a`
- `wbemcomn!GetMemLogObject` at `0x18003cd1c`
- `wbemcomn!GetMemLogObject` at `0x18003c794`
- `wbemcomn!GetMemLogObject` at `0x18003c8fa`
- `wbemcomn!GetMemLogObject` at `0x18003c949`
- `wbemcomn!GetMemLogObject` at `0x18003c9b3`
- `wbemcomn!GetMemLogObject` at `0x18003ca65`
- `wbemcomn!GetMemLogObject` at `0x18003ca85`
- `wbemcomn!GetMemLogObject` at `0x18003cb50`
- `wbemcomn!GetMemLogObject` at `0x18003cb94`
- `wbemcomn!GetMemLogObject` at `0x18003cbdf`
- `wbemcomn!GetMemLogObject` at `0x18003cc5a`
- `wbemcomn!GetMemLogObject` at `0x18003cd1c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c7a2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c905`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c954`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c9c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ca71`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ca93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cb5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cba2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cbeb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cc65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cd2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c7a2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c905`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c954`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c9c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ca71`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ca93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cb5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cba2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cbeb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cc65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cd2a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c596`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c596`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c6e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c781`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c7db`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cca6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c6e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c781`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c7db`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cca6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CWbemNamespace::Exec_GetClass(
        CWbemNamespace *this,
        OLECHAR *psz,
        int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  struct IWbemContext *v5; // r14
  struct CBasicObjectSink *v9; // r15
  int First_ms_XXX_Locale; // ebx
  unsigned int v11; // ebx
  unsigned __int16 *v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rdi
  struct CSynchronousSink *v15; // rdi
  int v16; // r14d
  struct CSynchronousSink *v18; // rax
  struct CSynchronousSink *v19; // rdi
  BSTR v20; // rax
  OLECHAR *v21; // r12
  CDecoratingSink *v22; // rax
  CDecoratingSink *v23; // rsi
  int v24; // r14d
  unsigned int v25; // esi
  struct IWbemClassObject *v26; // r14
  int v27; // edx
  CMemoryLog *v28; // rax
  unsigned int v29; // esi
  CMemoryLog *v30; // rax
  int v31; // edx
  CMemoryLog *v32; // rax
  struct IWbemPath *NewPath; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  int v37; // edx
  unsigned int v38; // ebx
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *MemLogObject; // rax
  struct CSynchronousSink *v44; // [rsp+58h] [rbp-29h] BYREF
  void *v45; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 *v46; // [rsp+68h] [rbp-19h] BYREF
  void *v47; // [rsp+70h] [rbp-11h]
  void *v48; // [rsp+78h] [rbp-9h] BYREF
  char v49[8]; // [rsp+80h] [rbp-1h] BYREF
  void (__fastcall *v50)(__int64); // [rsp+88h] [rbp+7h]
  __int64 v51; // [rsp+90h] [rbp+Fh]
  unsigned __int16 *v52; // [rsp+E8h] [rbp+67h] BYREF
  struct IWbemContext *v53; // [rsp+F8h] [rbp+77h]

  v53 = a4;
  v5 = a4;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, psz);
  }
  v46 = 0;
  v45 = 0;
  v9 = a5;
  if ( !psz || !a5 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    v31 = -2147217400;
    return CBasicObjectSink::Return(v9, v31, 0);
  }
  if ( *((_DWORD *)this + 66) || !*((_QWORD *)this + 31) )
    goto LABEL_11;
  v52 = 0;
  First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale((CWbemNamespace *)((char *)this + 176), &v52);
  if ( First_ms_XXX_Locale < 0 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, First_ms_XXX_Locale);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        256,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)First_ms_XXX_Locale);
    }
    v31 = First_ms_XXX_Locale;
    return CBasicObjectSink::Return(v9, v31, 0);
  }
  MakeGuard<int (*)(void *),unsigned short *>(v49, CMUILocale::_Free, v52);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemContext *, _QWORD, unsigned __int16 *, _QWORD, _QWORD, GUID *, unsigned __int16 **))(**((_QWORD **)this + 31) + 32LL))(
          *((_QWORD *)this + 31),
          0,
          v5,
          *((_QWORD *)this + 14),
          v52,
          *((_QWORD *)this + 12),
          0,
          &IID_IWbemServices,
          &v46);
  if ( (v11 & 0x80000000) != 0 )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, v11);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v11);
    }
    (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
      v9,
      0,
      v11,
      0,
      0);
    if ( !v49[0] )
      v50(v51);
    return v11;
  }
  if ( !v49[0] )
    v50(v51);
LABEL_11:
  v12 = v46;
  v52 = v46;
  if ( a3 < 0 )
    goto LABEL_29;
  v13 = *((_QWORD *)this + 7);
  if ( !v13 )
  {
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 258, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    v37 = -2147217398;
    goto LABEL_92;
  }
  v14 = *((_QWORD *)this + 5);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      v14,
      v13,
      (__int64)psz);
  }
  v44 = 0;
  if ( (**(int (__fastcall ***)(__int64, GUID *, struct CSynchronousSink **))v14)(v14, &IID_IWmiDbSessionEx, &v44) < 0 )
  {
    NewPath = ConfigMgr::GetNewPath();
    v47 = NewPath;
    if ( !NewPath )
    {
      v34 = GetMemLogObject();
      CMemoryLog::Write(v34, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
      }
      v5 = v53;
      goto LABEL_29;
    }
    v48 = NewPath;
    ((void (__fastcall *)(struct IWbemPath *, __int64, OLECHAR *))NewPath->lpVtbl->SetText)(NewPath, 4, psz);
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, void *, _QWORD, GUID *, void **))(*(_QWORD *)v14 + 32LL))(
            v14,
            v13,
            v47,
            0,
            &IID_IWbemClassObject,
            &v45);
    CReleaseMe::release((CReleaseMe *)&v48);
  }
  else
  {
    v15 = v44;
    v47 = v44;
    v16 = (*(__int64 (__fastcall **)(struct CSynchronousSink *, __int64, OLECHAR *, _QWORD, GUID *, void **))(*(_QWORD *)v44 + 96LL))(
            v44,
            v13,
            psz,
            0,
            &IID_IWbemClassObject,
            &v45);
    if ( v15 )
      (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v15 + 16LL))(v15);
    v47 = 0;
  }
  if ( v16 != -2147217406 )
  {
    if ( v16 < 0 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, v16);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
        (unsigned int)v16);
    }
    if ( v16 >= 0 && v45 )
    {
      (**((void (__fastcall ***)(__int64))v9 + 1))((__int64)v9 + 8);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
      (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
        v9,
        0,
        (unsigned int)v16,
        0,
        0);
      if ( v12 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
      v52 = 0;
      return (unsigned int)v16;
    }
  }
  v5 = v53;
LABEL_29:
  if ( *((_DWORD *)this + 66) || !*((_QWORD *)this + 31) )
  {
    (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
      v9,
      0,
      2147749890LL,
      0,
      0);
    if ( v12 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
    v52 = 0;
    return 2147749890LL;
  }
  v18 = CSynchronousSink::Create(0);
  v19 = v18;
  if ( !v18 )
  {
    v39 = GetMemLogObject();
    CMemoryLog::Write(v39, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v37 = -2147217402;
LABEL_92:
    v38 = CBasicObjectSink::Return(v9, v37, 0);
LABEL_94:
    CReleaseMe::release((CReleaseMe *)&v52);
    return v38;
  }
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v18 + 8LL))(v18);
  v44 = v19;
  v20 = SysAllocString(psz);
  v21 = v20;
  if ( !v20 )
  {
    v40 = GetMemLogObject();
    CMemoryLog::Write(v40, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v38 = CBasicObjectSink::Return(v9, -2147217402, 0);
    CReleaseMe::release((CReleaseMe *)&v44);
    goto LABEL_94;
  }
  v47 = v20;
  v22 = (CDecoratingSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
  v48 = v22;
  if ( v22 )
    v23 = CDecoratingSink::CDecoratingSink(v22, v19, this);
  else
    v23 = 0;
  if ( v23 )
  {
    (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v23 + 8LL))(v23);
    v48 = v23;
    v24 = (*(__int64 (__fastcall **)(unsigned __int16 *, OLECHAR *, _QWORD, struct IWbemContext *, CDecoratingSink *))(*(_QWORD *)v46 + 56LL))(
            v46,
            v21,
            (unsigned int)a3,
            v5,
            v23);
    (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v23 + 16LL))(v23);
    v48 = 0;
    if ( v24 < 0 )
    {
      if ( v24 != -2147217406 )
      {
        v41 = GetMemLogObject();
        CMemoryLog::Write(v41, v24);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            261,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v24);
        }
      }
      v27 = v24;
      goto LABEL_54;
    }
    if ( *((_DWORD *)v19 + 8) == -2147217398 )
      CCoreQueue::QueueWaitForSingleObject(*((void **)v19 + 3), 0xFFFFFFFF);
    CInCritSec::CInCritSec((CInCritSec *)&v48, (struct _RTL_CRITICAL_SECTION *)v19 + 4);
    v25 = *((_DWORD *)v19 + 8);
    v26 = (struct IWbemClassObject *)*((_QWORD *)v19 + 6);
    if ( v26 )
      ((void (__fastcall *)(_QWORD))v26->lpVtbl->AddRef)(*((_QWORD *)v19 + 6));
    CInCritSec::~CInCritSec((CInCritSec *)&v48);
    if ( (v25 & 0x80000000) == 0 )
    {
      if ( (int)CFlexArray::Size((struct CSynchronousSink *)((char *)v19 + 64)) >= 1 )
      {
        v45 = CFlexArray::GetAt((struct CSynchronousSink *)((char *)v19 + 64), 0);
        (**((void (__fastcall ***)(__int64, void *))v9 + 1))((__int64)v9 + 8, v45);
        (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 32LL))(
          v9,
          0,
          0,
          0,
          0);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v25);
        }
        SysFreeString(v21);
        (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v19 + 16LL))(v19);
        goto LABEL_46;
      }
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids);
      }
      v27 = -2147217398;
LABEL_54:
      v25 = CBasicObjectSink::Return(v9, v27, 0);
      SysFreeString(v21);
      (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_46:
      v44 = 0;
      if ( v12 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
      v52 = 0;
      return v25;
    }
    CBasicObjectSink::Return(v9, v25, v26);
    if ( v26 )
      ((void (__fastcall *)(struct IWbemClassObject *))v26->lpVtbl->Release)(v26);
    v42 = GetMemLogObject();
    CMemoryLog::Write(v42, v25);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v25);
    }
    SysFreeString(v21);
    CReleaseMe::release((CReleaseMe *)&v44);
    CReleaseMe::release((CReleaseMe *)&v52);
    return v25;
  }
  else
  {
    v29 = CBasicObjectSink::Return(v9, -2147217402, 0);
    SysFreeString(v21);
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v19 + 16LL))(v19);
    v44 = 0;
    if ( v12 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
    v52 = 0;
    return v29;
  }
}

```

## disassembly

```asm
0x18003c2c0  mov     [rsp-8+arg_0], rbx
0x18003c2c5  mov     [rsp-8+arg_18], r9
0x18003c2ca  push    rbp
0x18003c2cb  push    rsi
0x18003c2cc  push    rdi
0x18003c2cd  push    r12
0x18003c2cf  push    r13
0x18003c2d1  push    r14
0x18003c2d3  push    r15
0x18003c2d5  lea     rbp, [rsp-1Fh]
0x18003c2da  sub     rsp, 0A0h
0x18003c2e1  mov     r14, r9
0x18003c2e4  mov     r13d, r8d
0x18003c2e7  mov     r12, rdx
0x18003c2ea  mov     rsi, rcx
0x18003c2ed  xor     edi, edi
0x18003c2ef  lea     rax, WPP_GLOBAL_Control
0x18003c2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2fd  cmp     rcx, rax
0x18003c300  jz      short loc_18003C30C
0x18003c302  test    byte ptr [rcx+1Ch], 1
0x18003c306  jnz     loc_18003C86E
0x18003c30c  mov     [rbp+4Fh+var_68], rdi
0x18003c310  mov     [rbp+4Fh+var_70], rdi
0x18003c314  mov     r15, [rbp+4Fh+arg_20]
0x18003c318  test    r12, r12
0x18003c31b  jz      loc_18003CD1C
0x18003c321  test    r15, r15
0x18003c324  jz      loc_18003CD1C
0x18003c32a  cmp     [rsi+108h], edi
0x18003c330  jnz     loc_18003C3E3
0x18003c336  cmp     [rsi+0F8h], rdi
0x18003c33d  jz      loc_18003C3E3
0x18003c343  mov     [rbp+4Fh+arg_8], rdi
0x18003c347  lea     rcx, [rsi+0B0h]
0x18003c34e  lea     rdx, [rbp+4Fh+arg_8]
0x18003c352  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x18003c358  mov     ebx, eax
0x18003c35a  test    eax, eax
0x18003c35c  js      loc_18003C8FA
0x18003c362  mov     r8, [rbp+4Fh+arg_8]
0x18003c366  mov     rdx, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003c36d  lea     rcx, [rbp+4Fh+var_50]
0x18003c371  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x18003c376  nop
0x18003c377  mov     rcx, [rsi+0F8h]
0x18003c37e  mov     rax, [rcx]
0x18003c381  lea     rdx, [rbp+4Fh+var_68]
0x18003c385  mov     [rsp+0D0h+var_90], rdx
0x18003c38a  lea     rdx, IID_IWbemServices
0x18003c391  mov     [rsp+0D0h+var_98], rdx
0x18003c396  mov     [rsp+0D0h+var_A0], rdi
0x18003c39b  mov     rdx, [rsi+60h]
0x18003c39f  mov     [rsp+0D0h+var_A8], rdx
0x18003c3a4  mov     rdx, [rbp+4Fh+arg_8]
0x18003c3a8  mov     [rsp+0D0h+var_B0], rdx
0x18003c3ad  mov     r9, [rsi+70h]
0x18003c3b1  mov     r8, r14
0x18003c3b4  xor     edx, edx
0x18003c3b6  mov     rax, [rax+20h]
0x18003c3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3bf  mov     ebx, eax
0x18003c3c1  test    eax, eax
0x18003c3c3  js      loc_18003C949
0x18003c3c9  cmp     [rbp+4Fh+var_50], 0
0x18003c3cd  jnz     short loc_18003C3DC
0x18003c3cf  mov     rcx, [rbp+4Fh+var_40]
0x18003c3d3  mov     rax, [rbp+4Fh+var_48]
0x18003c3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3dc  lea     rax, WPP_GLOBAL_Control
0x18003c3e3  mov     rbx, [rbp+4Fh+var_68]
0x18003c3e7  mov     [rbp+4Fh+arg_8], rbx
0x18003c3eb  test    r13d, r13d
0x18003c3ee  js      loc_18003C552
0x18003c3f4  mov     r14, [rsi+38h]
0x18003c3f8  test    r14, r14
0x18003c3fb  jz      loc_18003CA85
0x18003c401  mov     rdi, [rsi+28h]
0x18003c405  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c40c  cmp     rcx, rax
0x18003c40f  jz      short loc_18003C41B
0x18003c411  test    byte ptr [rcx+1Ch], 1
0x18003c415  jnz     loc_18003C816
0x18003c41b  mov     [rbp+4Fh+var_78], 0
0x18003c423  mov     rax, [rdi]
0x18003c426  lea     r8, [rbp+4Fh+var_78]
0x18003c42a  lea     rdx, IID_IWmiDbSessionEx
0x18003c431  mov     rcx, rdi
0x18003c434  mov     rax, [rax]
0x18003c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c43c  test    eax, eax
0x18003c43e  js      loc_18003C9A2
0x18003c444  mov     rdi, [rbp+4Fh+var_78]
0x18003c448  mov     [rbp+4Fh+var_60], rdi
0x18003c44c  mov     rcx, [rbp+4Fh+var_78]
0x18003c450  mov     rax, [rcx]
0x18003c453  lea     rdx, [rbp+4Fh+var_70]
0x18003c457  mov     [rsp+0D0h+var_A8], rdx
0x18003c45c  lea     rdx, IID_IWbemClassObject
0x18003c463  mov     [rsp+0D0h+var_B0], rdx
0x18003c468  xor     r9d, r9d
0x18003c46b  mov     r8, r12
0x18003c46e  mov     rdx, r14
0x18003c471  mov     rax, [rax+60h]
0x18003c475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c47a  mov     r14d, eax
0x18003c47d  test    rdi, rdi
0x18003c480  jz      short loc_18003C491
0x18003c482  mov     rcx, [rdi]
0x18003c485  mov     rax, [rcx+10h]
0x18003c489  mov     rcx, rdi
0x18003c48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c491  xor     edi, edi
0x18003c493  mov     [rbp+4Fh+var_60], rdi
0x18003c497  cmp     r14d, 80041002h
0x18003c49e  jz      loc_18003CA7C
0x18003c4a4  test    r14d, r14d
0x18003c4a7  js      loc_18003CA65
0x18003c4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c4b4  lea     rax, WPP_GLOBAL_Control
0x18003c4bb  cmp     rcx, rax
0x18003c4be  jz      short loc_18003C4CA
0x18003c4c0  test    byte ptr [rcx+1Ch], 1
0x18003c4c4  jnz     loc_18003C847
0x18003c4ca  test    r14d, r14d
0x18003c4cd  js      loc_18003CA7C
0x18003c4d3  mov     rdx, [rbp+4Fh+var_70]
0x18003c4d7  test    rdx, rdx
0x18003c4da  jz      loc_18003CA7C
0x18003c4e0  lea     rcx, [r15+8]
0x18003c4e4  mov     rax, [rcx]
0x18003c4e7  mov     rax, [rax]
0x18003c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ef  mov     rcx, [rbp+4Fh+var_70]
0x18003c4f3  mov     rax, [rcx]
0x18003c4f6  mov     rax, [rax+10h]
0x18003c4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ff  mov     rax, [r15]
0x18003c502  mov     [rsp+0D0h+var_B0], rdi
0x18003c507  xor     r9d, r9d
0x18003c50a  mov     r8d, r14d
0x18003c50d  xor     edx, edx
0x18003c50f  mov     rcx, r15
0x18003c512  mov     rax, [rax+20h]
0x18003c516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c51b  nop
0x18003c51c  test    rbx, rbx
0x18003c51f  jz      short loc_18003C530
0x18003c521  mov     rax, [rbx]
0x18003c524  mov     rcx, rbx
0x18003c527  mov     rax, [rax+10h]
0x18003c52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c530  mov     [rbp+4Fh+arg_8], rdi
0x18003c534  mov     eax, r14d
0x18003c537  mov     rbx, [rsp+0D0h+arg_0]
0x18003c53f  add     rsp, 0A0h
0x18003c546  pop     r15
0x18003c548  pop     r14
0x18003c54a  pop     r13
0x18003c54c  pop     r12
0x18003c54e  pop     rdi
0x18003c54f  pop     rsi
0x18003c550  pop     rbp
0x18003c551  retn
0x18003c552  cmp     dword ptr [rsi+108h], 0
0x18003c559  jnz     loc_18003C71F
0x18003c55f  cmp     qword ptr [rsi+0F8h], 0
0x18003c567  jz      loc_18003C71F
0x18003c56d  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18003c56f  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18003c574  mov     rdi, rax
0x18003c577  test    rax, rax
0x18003c57a  jz      loc_18003CB50
0x18003c580  mov     rax, [rax]
0x18003c583  mov     rcx, rdi
0x18003c586  mov     rax, [rax+8]
0x18003c58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c58f  mov     [rbp+4Fh+var_78], rdi
0x18003c593  mov     rcx, r12; psz
0x18003c596  call    cs:__imp_SysAllocString
0x18003c59c  mov     r12, rax
0x18003c59f  test    rax, rax
0x18003c5a2  jz      loc_18003CB94
0x18003c5a8  mov     [rbp+4Fh+var_60], rax
0x18003c5ac  mov     ecx, 38h ; '8'
0x18003c5b1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003c5b7  mov     [rbp+4Fh+var_58], rax
0x18003c5bb  test    rax, rax
0x18003c5be  jz      loc_18003CBD8
0x18003c5c4  mov     r8, rsi; struct CWbemNamespace *
0x18003c5c7  mov     rdx, rdi; struct CBasicObjectSink *
0x18003c5ca  mov     rcx, rax; this
0x18003c5cd  call    ??0CDecoratingSink@@QEAA@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@@Z; CDecoratingSink::CDecoratingSink(CBasicObjectSink *,CWbemNamespace *)
0x18003c5d2  mov     rsi, rax
0x18003c5d5  test    rsi, rsi
0x18003c5d8  jz      loc_18003C7C6
0x18003c5de  mov     rax, [rsi]
0x18003c5e1  mov     rcx, rsi
0x18003c5e4  mov     rax, [rax+8]
0x18003c5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5ed  mov     [rbp+4Fh+var_58], rsi
0x18003c5f1  mov     rcx, [rbp+4Fh+var_68]
0x18003c5f5  mov     rax, [rcx]
0x18003c5f8  mov     [rsp+0D0h+var_B0], rsi
0x18003c5fd  mov     r9, r14
0x18003c600  mov     r8d, r13d
0x18003c603  mov     rdx, r12
0x18003c606  mov     rax, [rax+38h]
0x18003c60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c60f  mov     r14d, eax
0x18003c612  mov     rcx, [rsi]
0x18003c615  mov     rax, [rcx+10h]
0x18003c619  mov     rcx, rsi
0x18003c61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c621  xor     r13d, r13d
0x18003c624  mov     [rbp+4Fh+var_58], r13
0x18003c628  test    r14d, r14d
0x18003c62b  js      loc_18003C761
0x18003c631  cmp     dword ptr [rdi+20h], 8004100Ah
0x18003c638  jz      loc_18003C8B0
0x18003c63e  lea     rdx, [rdi+0A0h]
0x18003c645  lea     rcx, [rbp+4Fh+var_58]
0x18003c649  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003c64f  nop
0x18003c650  mov     esi, [rdi+20h]
0x18003c653  mov     r14, [rdi+30h]
0x18003c657  test    r14, r14
0x18003c65a  jnz     loc_18003C89C
0x18003c660  lea     rcx, [rbp+4Fh+var_58]
0x18003c664  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003c66a  test    esi, esi
0x18003c66c  js      loc_18003CC39
0x18003c672  lea     rcx, [rdi+40h]
0x18003c676  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18003c67c  cmp     eax, 1
0x18003c67f  jl      loc_18003C794
0x18003c685  xor     edx, edx
0x18003c687  lea     rcx, [rdi+40h]
0x18003c68b  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18003c691  mov     r8, rax
0x18003c694  mov     [rbp+4Fh+var_70], rax
0x18003c698  lea     rcx, [r15+8]
0x18003c69c  mov     rdx, [rcx]
0x18003c69f  mov     rax, [rdx]
0x18003c6a2  mov     rdx, r8
0x18003c6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6aa  mov     rax, [r15]
0x18003c6ad  mov     [rsp+0D0h+var_B0], r13
0x18003c6b2  xor     r9d, r9d
0x18003c6b5  xor     r8d, r8d
0x18003c6b8  xor     edx, edx
0x18003c6ba  mov     rcx, r15
0x18003c6bd  mov     rax, [rax+20h]
0x18003c6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6cd  lea     rax, WPP_GLOBAL_Control
0x18003c6d4  cmp     rcx, rax
0x18003c6d7  jz      short loc_18003C6E3
0x18003c6d9  test    byte ptr [rcx+1Ch], 1
0x18003c6dd  jnz     loc_18003CCF5
0x18003c6e3  mov     rcx, r12; bstrString
0x18003c6e6  call    cs:__imp_SysFreeString
0x18003c6ec  nop
0x18003c6ed  mov     rax, [rdi]
0x18003c6f0  mov     rax, [rax+10h]
0x18003c6f4  mov     rcx, rdi
0x18003c6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6fc  mov     [rbp+4Fh+var_78], r13
0x18003c700  test    rbx, rbx
0x18003c703  jz      short loc_18003C714
0x18003c705  mov     rax, [rbx]
0x18003c708  mov     rcx, rbx
0x18003c70b  mov     rax, [rax+10h]
0x18003c70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c714  mov     [rbp+4Fh+arg_8], r13
0x18003c718  mov     eax, esi
0x18003c71a  jmp     loc_18003C537
0x18003c71f  mov     rax, [r15]
0x18003c722  mov     [rsp+0D0h+var_B0], rdi
0x18003c727  xor     r9d, r9d
0x18003c72a  xor     edx, edx
0x18003c72c  mov     r8d, 80041002h
0x18003c732  mov     rcx, r15
0x18003c735  mov     rax, [rax+20h]
0x18003c739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c73e  nop
0x18003c73f  test    rbx, rbx
0x18003c742  jz      short loc_18003C753
0x18003c744  mov     rcx, [rbx]
0x18003c747  mov     rax, [rcx+10h]
0x18003c74b  mov     rcx, rbx
0x18003c74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c753  mov     [rbp+4Fh+arg_8], rdi
0x18003c757  mov     eax, 80041002h
0x18003c75c  jmp     loc_18003C537
0x18003c761  cmp     r14d, 80041002h
0x18003c768  jnz     loc_18003CBDF
0x18003c76e  mov     edx, r14d; int
0x18003c771  xor     r8d, r8d; struct IWbemClassObject *
0x18003c774  mov     rcx, r15; this
  ... truncated ...
```
