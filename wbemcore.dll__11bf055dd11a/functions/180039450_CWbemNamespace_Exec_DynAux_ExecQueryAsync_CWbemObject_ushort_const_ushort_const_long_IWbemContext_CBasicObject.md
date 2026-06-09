# CWbemNamespace::Exec_DynAux_ExecQueryAsync(CWbemObject *,ushort const *,ushort const *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x180039450`
- end: `0x180039c4a`
- name: `?Exec_DynAux_ExecQueryAsync@CWbemNamespace@@QEAAJPEAVCWbemObject@@PEBG1JPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `2042`
- prototype: `int(CWbemNamespace *__hidden this, struct CWbemObject *, const unsigned __int16 *, const unsigned __int16 *, int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038480`
- `0x1800b1bb0`

## callees

- `0x18000af58`
- `0x18000b140`
- `0x18001307c`
- `0x180039134`
- `0x180039450`
- `0x180039c50`
- `0x180039d40`
- `0x180039f68`
- `0x180039f98`
- `0x18003be20`
- `0x18003cfe0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18003953b`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18003953b`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x180039590`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x180039590`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x180039550`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800394ce`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800394ce`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180039506`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180039506`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18003985a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800398b2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800399c9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180039c32`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18003985a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800398b2`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800399c9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180039c32`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039618`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003969d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039737`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039618`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003969d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039737`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003964a`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003964a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180039702`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180039702`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003971e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003971e`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180039713`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180039713`
- `wbemcomn!GetMemLogObject` at `0x180039970`
- `wbemcomn!GetMemLogObject` at `0x1800399e5`
- `wbemcomn!GetMemLogObject` at `0x180039a4a`
- `wbemcomn!GetMemLogObject` at `0x180039aab`
- `wbemcomn!GetMemLogObject` at `0x180039ae7`
- `wbemcomn!GetMemLogObject` at `0x180039b4e`
- `wbemcomn!GetMemLogObject` at `0x180039bad`
- `wbemcomn!GetMemLogObject` at `0x180039970`
- `wbemcomn!GetMemLogObject` at `0x1800399e5`
- `wbemcomn!GetMemLogObject` at `0x180039a4a`
- `wbemcomn!GetMemLogObject` at `0x180039aab`
- `wbemcomn!GetMemLogObject` at `0x180039ae7`
- `wbemcomn!GetMemLogObject` at `0x180039b4e`
- `wbemcomn!GetMemLogObject` at `0x180039bad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003997c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800399f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039a55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039ab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039af5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039b5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039bb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003997c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800399f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039a55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039ab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039af5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039b5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x180039797`
- `OLEAUT32!__imp_SysAllocString` at `0x1800397a8`
- `OLEAUT32!__imp_SysAllocString` at `0x180039797`
- `OLEAUT32!__imp_SysAllocString` at `0x1800397a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003980c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003981b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003980c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003981b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWbemNamespace::Exec_DynAux_ExecQueryAsync(
        CWbemNamespace *this,
        struct CWbemObject *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct IWbemContext *a6,
        struct CBasicObjectSink *a7)
{
  int First_ms_XXX_Locale; // ebx
  unsigned __int16 *v11; // r14
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, struct IWbemServices *, _QWORD, __int64, GUID *, struct IWbemServices **); // rbx
  __int64 v14; // rax
  struct IWbemServices *v15; // rbx
  _QWORD *v16; // rsi
  __int64 v17; // rdi
  unsigned __int64 v18; // rdi
  unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  unsigned __int16 *v21; // r8
  unsigned __int16 v22; // dx
  unsigned __int16 *v23; // rcx
  CDecoratingSink *v24; // rax
  CDecoratingSink *v25; // rcx
  unsigned int v26; // edx
  CWmiArbitrator *v27; // rcx
  int v28; // edi
  OLECHAR *v29; // rdi
  OLECHAR *v30; // r14
  int v31; // r15d
  CObjectSink *v33; // rcx
  CMemoryLog *v34; // rax
  unsigned int v35; // edi
  CMemoryLog *MemLogObject; // rax
  unsigned int v37; // ebx
  CMemoryLog *v38; // rax
  CClientCnt *v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  struct IWbemServices *v46; // [rsp+70h] [rbp-89h] BYREF
  char v47[8]; // [rsp+78h] [rbp-81h] BYREF
  CObjectSink *v48; // [rsp+80h] [rbp-79h]
  struct IWbemServices *v49; // [rsp+88h] [rbp-71h] BYREF
  _QWORD *v50; // [rsp+90h] [rbp-69h] BYREF
  _BYTE v51[32]; // [rsp+98h] [rbp-61h] BYREF
  char v52[8]; // [rsp+B8h] [rbp-41h] BYREF
  void *v53; // [rsp+C0h] [rbp-39h]
  __int128 v54; // [rsp+C8h] [rbp-31h] BYREF
  _QWORD *v55; // [rsp+D8h] [rbp-21h]
  char v56; // [rsp+E0h] [rbp-19h]
  _DWORD (*v57)(void *); // [rsp+E8h] [rbp-11h]
  __int128 v58; // [rsp+F0h] [rbp-9h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      377,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)a4);
  }
  COperationError::COperationError((COperationError *)v47, a7, L"ExecQuery", a3, 0);
  if ( !v47[0] )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v37 = CBasicObjectSink::Return(a7, -2147217402, 0);
    goto LABEL_93;
  }
  CVar::CVar((CVar *)v51);
  if ( (*(int (__fastcall **)(struct CWbemObject *, const wchar_t *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a2 + 976LL))(
         a2,
         L"Provider",
         v51,
         0,
         0) < 0
    || CVar::GetType((CVar *)v51) != 8 )
  {
    v41 = COperationError::ErrorOccurred((COperationError *)v47, -2147217390, 0);
    goto LABEL_91;
  }
  v49 = 0;
  if ( !*((_QWORD *)this + 31) )
  {
    First_ms_XXX_Locale = -2147217398;
    goto LABEL_70;
  }
  v46 = 0;
  First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale(
                          (CWbemNamespace *)((char *)this + 176),
                          (unsigned __int16 **)&v46);
  if ( First_ms_XXX_Locale < 0 )
  {
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, First_ms_XXX_Locale);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v40 = 379;
    goto LABEL_68;
  }
  v11 = (unsigned __int16 *)v46;
  v56 = 0;
  v57 = CMUILocale::_Free;
  *(_QWORD *)&v58 = v46;
  v12 = *((_QWORD *)this + 31);
  v13 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, struct IWbemServices *, _QWORD, __int64, GUID *, struct IWbemServices **))(*(_QWORD *)v12 + 40LL);
  v14 = CVar::operator unsigned short *(v51);
  v54 = 0;
  First_ms_XXX_Locale = v13(v12, &v54, 0, a6, 0, *((_QWORD *)this + 14), v46, 0, v14, &IID_IWbemServices, &v49);
  ((void (__fastcall *)(unsigned __int16 *))CMUILocale::_Free)(v11);
  if ( First_ms_XXX_Locale < 0 )
  {
LABEL_70:
    v42 = GetMemLogObject();
    CMemoryLog::Write(v42, First_ms_XXX_Locale);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v40 = 380;
LABEL_68:
    WPP_SF_d(
      *((_QWORD *)v39 + 2),
      v40,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)First_ms_XXX_Locale);
LABEL_69:
    v41 = CBasicObjectSink::Return(a7, First_ms_XXX_Locale, 0);
LABEL_91:
    v37 = v41;
LABEL_92:
    CVar::~CVar((CVar *)v51);
LABEL_93:
    COperationError::~COperationError((COperationError *)v47);
    return v37;
  }
  v15 = v49;
  v46 = v49;
  v16 = CWin32DefaultArena::WbemMemAlloc(0x50u);
  v55 = v16;
  if ( v16 )
  {
    *v16 = &CProviderSink::`vftable';
    v16[3] = 0;
    CCritSec::CCritSec((CCritSec *)(v16 + 5));
    *((_DWORD *)v16 + 2) = 1;
    _InterlockedIncrement(&g_nSinkCount);
    _InterlockedIncrement(&g_nProviderSinkCount);
    v16[4] = 0;
    *((_DWORD *)v16 + 3) = 0;
    v16[2] = 0;
    if ( a3 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
      v18 = v17 + 1;
      v19 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v18, 2u));
      v16[2] = v19;
      if ( v19 )
      {
        if ( v18 )
        {
          if ( v18 > 0x7FFFFFFF )
          {
            *v19 = 0;
          }
          else
          {
            v20 = 2147483646;
            v21 = a3;
            do
            {
              if ( !v20 )
                break;
              v22 = *v21;
              if ( !*v21 )
                break;
              ++v21;
              *v19++ = v22;
              --v20;
              --v18;
            }
            while ( v18 );
            v23 = v19 - 1;
            if ( v18 )
              v23 = v19;
            *v23 = 0;
          }
        }
      }
    }
    CInCritSec::CInCritSec((CInCritSec *)v52, (struct _RTL_CRITICAL_SECTION *)g_csProvSinkCs);
    CFlexArray::Add((CFlexArray *)&g_aProviderSinks, v16);
    CInCritSec::~CInCritSec((CInCritSec *)v52);
  }
  else
  {
    v16 = 0;
  }
  if ( v16 )
  {
    v50 = v16;
    v24 = (CDecoratingSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
    v53 = v24;
    if ( v24 )
      v25 = CDecoratingSink::CDecoratingSink(v24, a7, this);
    else
      v25 = 0;
    if ( v25 )
    {
      v16[3] = v25;
      (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v25 + 8LL))(v25);
      v28 = CWmiArbitrator::MapProviderToTask(v27, v26, a6, v49, (struct CProviderSink *)v16);
      if ( v28 >= 0 )
      {
        v29 = SysAllocString(a3);
        v53 = v29;
        v30 = SysAllocString(a4);
        *(_QWORD *)&v54 = v30;
        v31 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, OLECHAR *, _QWORD, struct IWbemContext *, _QWORD *))v49->lpVtbl->ExecQueryAsync)(
                v49,
                v30,
                v29,
                a5,
                a6,
                v16);
        if ( v31 < 0 )
        {
          v34 = GetMemLogObject();
          CMemoryLog::Write(v34, v31);
        }
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            384,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v31);
        }
        if ( v30 )
          SysFreeString(v30);
        if ( v29 )
          SysFreeString(v29);
        (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
        v50 = 0;
        if ( v15 )
          ((void (__fastcall *)(struct IWbemServices *))v15->lpVtbl->Release)(v15);
        v46 = 0;
        CVar::~CVar((CVar *)v51);
        if ( v48 )
          CObjectSink::Release(v48);
        return (unsigned int)v31;
      }
      v45 = GetMemLogObject();
      CMemoryLog::Write(v45, v28);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          383,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v28);
      }
      v37 = CBasicObjectSink::Return(a7, v28, 0);
      CReleaseMe::release((CReleaseMe *)&v50);
      CReleaseMe::release((CReleaseMe *)&v46);
      goto LABEL_92;
    }
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 382, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v35 = CBasicObjectSink::Return(a7, -2147217402, 0);
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    v50 = 0;
    if ( v15 )
      ((void (__fastcall *)(struct IWbemServices *))v15->lpVtbl->Release)(v15);
    v46 = 0;
    CVar::~CVar((CVar *)v51);
    if ( v48 )
      CObjectSink::Release(v48);
    return v35;
  }
  else
  {
    v43 = GetMemLogObject();
    CMemoryLog::Write(v43, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 381, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    (*(void (__fastcall **)(struct CBasicObjectSink *, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)a7 + 32LL))(
      a7,
      0,
      2147749894LL,
      0,
      0);
    if ( v15 )
      ((void (__fastcall *)(struct IWbemServices *))v15->lpVtbl->Release)(v15);
    v46 = 0;
    CVar::~CVar((CVar *)v51);
    v33 = v48;
    if ( v48 && _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v33 )
      (*(void (__fastcall **)(CObjectSink *, __int64))(*(_QWORD *)v33 + 80LL))(v33, 1);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180039450  mov     rax, rsp
0x180039453  mov     [rax+10h], rbx
0x180039457  mov     [rax+20h], r9
0x18003945b  mov     [rax+8], rcx
0x18003945f  push    rbp
0x180039460  push    rsi
0x180039461  push    rdi
0x180039462  push    r12
0x180039464  push    r13
0x180039466  push    r14
0x180039468  push    r15
0x18003946a  lea     rbp, [rax-47h]
0x18003946e  sub     rsp, 100h
0x180039475  movaps  xmmword ptr [rax-48h], xmm6
0x180039479  mov     r12, r8
0x18003947c  mov     rbx, rdx
0x18003947f  mov     rdi, rcx
0x180039482  xor     esi, esi
0x180039484  mov     dword ptr [rsp+130h+var_D0], esi
0x180039488  lea     r14, WPP_GLOBAL_Control
0x18003948f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039496  cmp     rcx, r14
0x180039499  jnz     loc_18003990E
0x18003949f  mov     dword ptr [rsp+130h+var_110], esi; int
0x1800394a3  mov     r9, r12; unsigned __int16 *
0x1800394a6  lea     r8, aExecquery; "ExecQuery"
0x1800394ad  mov     r13, [rbp+3Fh+arg_30]
0x1800394b1  mov     rdx, r13; struct CBasicObjectSink *
0x1800394b4  lea     rcx, [rsp+130h+var_C0]; this
0x1800394b9  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x1800394be  nop
0x1800394bf  cmp     [rsp+130h+var_C0], 0
0x1800394c4  jz      loc_1800399E5
0x1800394ca  lea     rcx, [rbp+3Fh+var_A0]
0x1800394ce  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800394d4  nop
0x1800394d5  mov     rax, [rbx]
0x1800394d8  mov     [rsp+130h+var_110], rsi
0x1800394dd  xor     r9d, r9d
0x1800394e0  lea     r8, [rbp+3Fh+var_A0]
0x1800394e4  lea     rdx, aProvider_0; "Provider"
0x1800394eb  mov     rcx, rbx
0x1800394ee  mov     rax, [rax+3D0h]
0x1800394f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394fa  test    eax, eax
0x1800394fc  js      loc_180039C1A
0x180039502  lea     rcx, [rbp+3Fh+var_A0]
0x180039506  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x18003950c  cmp     eax, 8
0x18003950f  jnz     loc_180039C1A
0x180039515  mov     [rbp+3Fh+var_B0], rsi
0x180039519  cmp     qword ptr [rdi+0F8h], 0
0x180039521  jz      loc_180039A43
0x180039527  xorps   xmm6, xmm6
0x18003952a  mov     [rsp+130h+var_C8], rsi
0x18003952f  lea     rcx, [rdi+0B0h]
0x180039536  lea     rdx, [rsp+130h+var_C8]
0x18003953b  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x180039541  mov     ebx, eax
0x180039543  test    eax, eax
0x180039545  js      loc_180039A4A
0x18003954b  mov     r14, [rsp+130h+var_C8]
0x180039550  mov     r15, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180039557  mov     [rbp+3Fh+var_58], 0
0x18003955b  mov     [rbp+3Fh+var_50], r15
0x18003955f  mov     qword ptr [rbp+3Fh+var_48], r14
0x180039563  mov     dword ptr [rsp+130h+var_D0], 2
0x18003956b  mov     esi, 2
0x180039570  and     esi, 0FFFFFFFDh
0x180039573  mov     dword ptr [rsp+130h+var_D0], esi
0x180039577  or      esi, 1
0x18003957a  mov     dword ptr [rsp+130h+var_D0], esi
0x18003957e  mov     rdi, [rdi+0F8h]
0x180039585  mov     rax, [rdi]
0x180039588  mov     rbx, [rax+28h]
0x18003958c  lea     rcx, [rbp+3Fh+var_A0]
0x180039590  call    cs:__imp_??BCVar@@QEAAPEAGXZ; CVar::operator ushort *(void)
0x180039596  mov     rdx, [rsp+130h+var_C8]
0x18003959b  movdqa  [rbp+3Fh+var_70], xmm6
0x1800395a0  lea     rcx, [rbp+3Fh+var_B0]
0x1800395a4  mov     [rsp+50h], rcx
0x1800395a9  lea     rcx, IID_IWbemServices
0x1800395b0  mov     [rsp+130h+var_E8], rcx
0x1800395b5  mov     [rsp+130h+var_F0], rax
0x1800395ba  xor     ecx, ecx
0x1800395bc  mov     [rsp+130h+var_F8], rcx
0x1800395c1  mov     [rsp+130h+var_100], rdx
0x1800395c6  mov     rax, [rbp+3Fh+arg_0]
0x1800395ca  mov     rdx, [rax+70h]
0x1800395ce  mov     [rsp+130h+var_108], rdx
0x1800395d3  mov     [rsp+130h+var_110], rcx
0x1800395d8  mov     r9, [rbp+3Fh+arg_28]
0x1800395dc  xor     r8d, r8d
0x1800395df  lea     rdx, [rbp+3Fh+var_70]
0x1800395e3  mov     rcx, rdi
0x1800395e6  mov     rax, rbx
0x1800395e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395ee  mov     ebx, eax
0x1800395f0  and     esi, 0FFFFFFFEh
0x1800395f3  mov     dword ptr [rsp+130h+var_D0], esi
0x1800395f7  mov     rcx, r14
0x1800395fa  mov     rax, r15
0x1800395fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039602  test    ebx, ebx
0x180039604  js      loc_180039AA4
0x18003960a  mov     rbx, [rbp+3Fh+var_B0]
0x18003960e  mov     [rsp+130h+var_C8], rbx
0x180039613  mov     ecx, 50h ; 'P'
0x180039618  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003961e  mov     rsi, rax
0x180039621  mov     [rbp+3Fh+var_60], rax
0x180039625  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18003962c  xor     r15d, r15d
0x18003962f  test    rax, rax
0x180039632  jz      loc_180039ADF
0x180039638  lea     rax, ??_7CProviderSink@@6B@; const CProviderSink::`vftable'
0x18003963f  mov     [rsi], rax
0x180039642  mov     [rsi+18h], r15
0x180039646  lea     rcx, [rsi+28h]
0x18003964a  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180039650  nop
0x180039651  mov     dword ptr [rsi+8], 1
0x180039658  lock inc cs:?g_nSinkCount@@3JA; long g_nSinkCount
0x18003965f  lock inc cs:?g_nProviderSinkCount@@3JA; long g_nProviderSinkCount
0x180039666  mov     [rsi+20h], r15
0x18003966a  mov     [rsi+0Ch], r15d
0x18003966e  mov     [rsi+10h], r15
0x180039672  test    r12, r12
0x180039675  jz      loc_1800396F7
0x18003967b  mov     rdi, r14
0x18003967e  xchg    ax, ax
0x180039680  inc     rdi
0x180039683  cmp     word ptr [r12+rdi*2], 0
0x180039689  jnz     short loc_180039680
0x18003968b  inc     rdi
0x18003968e  mov     eax, 2
0x180039693  mul     rdi
0x180039696  cmovb   rax, r14
0x18003969a  mov     rcx, rax
0x18003969d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800396a3  mov     [rsi+10h], rax
0x1800396a7  test    rax, rax
0x1800396aa  jz      short loc_1800396F7
0x1800396ac  test    rdi, rdi
0x1800396af  jz      short loc_1800396F7
0x1800396b1  cmp     rdi, 7FFFFFFFh
0x1800396b8  ja      loc_180039AD6
0x1800396be  mov     ecx, 7FFFFFFEh
0x1800396c3  mov     r8, r12
0x1800396c6  test    rcx, rcx
0x1800396c9  jz      short loc_1800396E8
0x1800396cb  movzx   edx, word ptr [r8]
0x1800396cf  test    dx, dx
0x1800396d2  jz      short loc_1800396E8
0x1800396d4  add     r8, 2
0x1800396d8  mov     [rax], dx
0x1800396db  add     rax, 2
0x1800396df  dec     rcx
0x1800396e2  sub     rdi, 1
0x1800396e6  jnz     short loc_1800396C6
0x1800396e8  lea     rcx, [rax-2]
0x1800396ec  test    rdi, rdi
0x1800396ef  cmovnz  rcx, rax
0x1800396f3  mov     [rcx], r15w
0x1800396f7  lea     rdx, ?g_csProvSinkCs@@3VCStaticCritSec@@A; CStaticCritSec g_csProvSinkCs
0x1800396fe  lea     rcx, [rbp+3Fh+var_80]
0x180039702  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180039708  nop
0x180039709  mov     rdx, rsi
0x18003970c  lea     rcx, ?g_aProviderSinks@@3VCFlexArray@@A; CFlexArray g_aProviderSinks
0x180039713  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180039719  nop
0x18003971a  lea     rcx, [rbp+3Fh+var_80]
0x18003971e  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180039724  nop
0x180039725  test    rsi, rsi
0x180039728  jz      loc_180039AE7
0x18003972e  mov     [rbp+3Fh+var_A8], rsi
0x180039732  mov     ecx, 38h ; '8'
0x180039737  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003973d  mov     [rbp+3Fh+var_78], rax
0x180039741  test    rax, rax
0x180039744  jz      loc_180039B46
0x18003974a  mov     r8, [rbp+3Fh+arg_0]; struct CWbemNamespace *
0x18003974e  mov     rdx, r13; struct CBasicObjectSink *
0x180039751  mov     rcx, rax; this
0x180039754  call    ??0CDecoratingSink@@QEAA@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@@Z; CDecoratingSink::CDecoratingSink(CBasicObjectSink *,CWbemNamespace *)
0x180039759  mov     rcx, rax
0x18003975c  test    rcx, rcx
0x18003975f  jz      loc_180039B4E
0x180039765  mov     [rsi+18h], rcx
0x180039769  mov     rax, [rcx]
0x18003976c  mov     rax, [rax+8]
0x180039770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039775  mov     [rsp+130h+var_110], rsi; struct CProviderSink *
0x18003977a  mov     r9, [rbp+3Fh+var_B0]; struct IWbemServices *
0x18003977e  mov     r15, [rbp+3Fh+arg_28]
0x180039782  mov     r8, r15; struct IWbemContext *
0x180039785  call    ?MapProviderToTask@CWmiArbitrator@@QEAAJKPEAUIWbemContext@@PEAUIWbemServices@@PEAVCProviderSink@@@Z; CWmiArbitrator::MapProviderToTask(ulong,IWbemContext *,IWbemServices *,CProviderSink *)
0x18003978a  mov     edi, eax
0x18003978c  test    eax, eax
0x18003978e  js      loc_180039BAD
0x180039794  mov     rcx, r12; psz
0x180039797  call    cs:__imp_SysAllocString
0x18003979d  mov     rdi, rax
0x1800397a0  mov     [rbp+3Fh+var_78], rax
0x1800397a4  mov     rcx, [rbp+3Fh+psz]; psz
0x1800397a8  call    cs:__imp_SysAllocString
0x1800397ae  mov     r14, rax
0x1800397b1  mov     qword ptr [rbp+3Fh+var_70], rax
0x1800397b5  mov     rcx, [rbp+3Fh+var_B0]
0x1800397b9  mov     rdx, [rcx]
0x1800397bc  mov     rax, [rdx+0A8h]
0x1800397c3  mov     [rsp+130h+var_108], rsi
0x1800397c8  mov     [rsp+130h+var_110], r15
0x1800397cd  mov     r9d, [rbp+3Fh+arg_20]
0x1800397d1  mov     r8, rdi
0x1800397d4  mov     rdx, r14
0x1800397d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397dc  mov     r15d, eax
0x1800397df  test    eax, eax
0x1800397e1  js      loc_180039970
0x1800397e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397ee  lea     rax, WPP_GLOBAL_Control
0x1800397f5  cmp     rcx, rax
0x1800397f8  jz      short loc_180039804
0x1800397fa  test    byte ptr [rcx+1Ch], 1
0x1800397fe  jnz     loc_180039949
0x180039804  test    r14, r14
0x180039807  jz      short loc_180039813
0x180039809  mov     rcx, r14; bstrString
0x18003980c  call    cs:__imp_SysFreeString
0x180039812  nop
0x180039813  test    rdi, rdi
0x180039816  jz      short loc_180039822
0x180039818  mov     rcx, rdi; bstrString
0x18003981b  call    cs:__imp_SysFreeString
0x180039821  nop
0x180039822  mov     rax, [rsi]
0x180039825  mov     rcx, rsi
0x180039828  mov     rax, [rax+10h]
0x18003982c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039831  mov     [rbp+3Fh+var_A8], 0
0x180039839  test    rbx, rbx
0x18003983c  jz      short loc_18003984D
0x18003983e  mov     rax, [rbx]
0x180039841  mov     rcx, rbx
0x180039844  mov     rax, [rax+10h]
0x180039848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003984d  mov     [rsp+130h+var_C8], 0
0x180039856  lea     rcx, [rbp+3Fh+var_A0]
0x18003985a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180039860  nop
0x180039861  mov     rcx, [rbp+3Fh+var_B8]; this
0x180039865  test    rcx, rcx
0x180039868  jz      short loc_18003986F
0x18003986a  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x18003986f  mov     eax, r15d
0x180039872  jmp     short loc_1800398D3
0x180039874  mov     rax, [r13+0]
0x180039878  mov     [rsp+130h+var_110], r15
0x18003987d  xor     r9d, r9d
0x180039880  xor     edx, edx
0x180039882  mov     r8d, 80041006h
0x180039888  mov     rcx, r13
0x18003988b  mov     rax, [rax+20h]
0x18003988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039894  nop
0x180039895  test    rbx, rbx
0x180039898  jz      short loc_1800398A9
0x18003989a  mov     rax, [rbx]
0x18003989d  mov     rcx, rbx
0x1800398a0  mov     rax, [rax+10h]
0x1800398a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398a9  mov     [rsp+130h+var_C8], r15
0x1800398ae  lea     rcx, [rbp+3Fh+var_A0]
0x1800398b2  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800398b8  nop
0x1800398b9  mov     rcx, [rbp+3Fh+var_B8]
0x1800398bd  test    rcx, rcx
0x1800398c0  jz      short loc_1800398CE
0x1800398c2  lock xadd [rcx+10h], r14d
0x1800398c8  cmp     r14d, 1
0x1800398cc  jz      short loc_1800398F6
0x1800398ce  mov     eax, 80041006h
0x1800398d3  mov     rbx, [rsp+130h+arg_8]
0x1800398db  movaps  xmm6, [rsp+130h+var_48+8]
0x1800398e3  add     rsp, 100h
0x1800398ea  pop     r15
0x1800398ec  pop     r14
0x1800398ee  pop     r13
0x1800398f0  pop     r12
0x1800398f2  pop     rdi
0x1800398f3  pop     rsi
0x1800398f4  pop     rbp
0x1800398f5  retn
0x1800398f6  test    rcx, rcx
0x1800398f9  jz      short loc_1800398CE
0x1800398fb  mov     rax, [rcx]
0x1800398fe  mov     edx, 1
  ... truncated ...
```
