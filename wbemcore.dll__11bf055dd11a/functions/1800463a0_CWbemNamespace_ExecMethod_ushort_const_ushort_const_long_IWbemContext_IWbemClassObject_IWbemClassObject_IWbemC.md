# CWbemNamespace::ExecMethod(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x1800463a0`
- end: `0x18004699b`
- name: `?ExecMethod@CWbemNamespace@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAPEAU3@PEAPEAUIWbemCallResult@@@Z`
- size: `1531`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000a9a0`
- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x18003cfe0`
- `0x1800463a0`
- `0x1800469a4`
- `0x180046a20`
- `0x180047ed0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800465e9`
- `wbemcomn!GetMemLogObject` at `0x180046613`
- `wbemcomn!GetMemLogObject` at `0x180046666`
- `wbemcomn!GetMemLogObject` at `0x180046711`
- `wbemcomn!GetMemLogObject` at `0x180046746`
- `wbemcomn!GetMemLogObject` at `0x1800467d8`
- `wbemcomn!GetMemLogObject` at `0x180046820`
- `wbemcomn!GetMemLogObject` at `0x1800468a9`
- `wbemcomn!GetMemLogObject` at `0x1800468e8`
- `wbemcomn!GetMemLogObject` at `0x1800465e9`
- `wbemcomn!GetMemLogObject` at `0x180046613`
- `wbemcomn!GetMemLogObject` at `0x180046666`
- `wbemcomn!GetMemLogObject` at `0x180046711`
- `wbemcomn!GetMemLogObject` at `0x180046746`
- `wbemcomn!GetMemLogObject` at `0x1800467d8`
- `wbemcomn!GetMemLogObject` at `0x180046820`
- `wbemcomn!GetMemLogObject` at `0x1800468a9`
- `wbemcomn!GetMemLogObject` at `0x1800468e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800465f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046620`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046673`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004671e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046756`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800467e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004682d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800465f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046620`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046673`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004671e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046756`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800467e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004682d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CWbemNamespace::ExecMethod(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemClassObject **a7,
        struct IWbemCallResult **a8)
{
  int v10; // r12d
  struct IWbemClassObject **v12; // r15
  struct IWbemCallResult **v13; // r14
  CWbemNamespace *v14; // rcx
  int v15; // r8d
  int v16; // r8d
  struct IWbemContext *v17; // r12
  struct _IWmiFinalizer *v18; // rdi
  __int64 v19; // rax
  unsigned int v20; // ebx
  __int64 (__fastcall *v21)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemClassObject **); // rax
  int v22; // eax
  CClientCnt *v23; // rcx
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  CMemoryLog *v30; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  CMemoryLog *v35; // rax
  CClientCnt *v36; // rcx
  __int64 v37; // rdx
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  int v44; // [rsp+50h] [rbp-38h] BYREF
  struct _IWmiFinalizer *v45; // [rsp+58h] [rbp-30h] BYREF

  v10 = (int)a2;
  if ( (unsigned int)IsCallFromLowIntegrityClient() )
  {
    MemLogObject = GetMemLogObject();
    v20 = -2147217405;
    CMemoryLog::Write(MemLogObject, -2147217405);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v20;
    }
    v33 = 797;
    v34 = 2147749891LL;
LABEL_54:
    WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v34);
    return v20;
  }
  v12 = a7;
  if ( a7 && *a7 )
  {
    ((void (__fastcall *)(_QWORD))(*a7)->lpVtbl->Release)(*a7);
    *v12 = 0;
  }
  v13 = a8;
  if ( a8 && *a8 )
  {
    ((void (__fastcall *)(_QWORD))(*a8)->lpVtbl->Release)(*a8);
    *v13 = 0;
  }
  v44 = CWbemNamespace::CheckNs(this);
  if ( v44 < 0 )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, v44);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v44;
    }
    v37 = 798;
    goto LABEL_75;
  }
  v44 = CWbemNamespace::AdjustCtx(v14, &a5, v15);
  if ( v44 < 0 )
  {
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, v44);
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v44;
    }
    v37 = 799;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 800, v16, v10, (__int64)a3, a4, (char)a6, *((_DWORD *)this + 76));
  }
  if ( v12 )
    *v12 = 0;
  if ( (a4 & 0xFFFFFFEF) != 0 )
  {
    v39 = GetMemLogObject();
    v20 = -2147217400;
    CMemoryLog::Write(v39, -2147217400);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v20;
    }
    v33 = 801;
    v34 = 2147749896LL;
    goto LABEL_54;
  }
  v45 = 0;
  v17 = a5;
  v44 = CWbemNamespace::CreateSyncFinalizer(this, a5, &v45);
  if ( v44 >= 0 )
  {
    v18 = v45;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v44 = CWbemNamespace::_ExecMethodAsync(this, v13 != 0 ? 33554443 : 16777227, v45, 0, a2, a3, 0, v17, a6, 0);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
      {
        _InterlockedIncrement(&ExceptionCounter::s_Count);
        v41 = GetMemLogObject();
        CMemoryLog::Write(v41, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            803,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749894LL);
        }
        v20 = -2147217402;
        __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_180046980);
LABEL_82:
        CReleaseMe::release((CReleaseMe *)&v45);
        return v20;
      }
      if ( __eh34_catch_type(0, &SafeIntException `RTTI Type Descriptor', 0) )
      {
        _InterlockedIncrement(&ExceptionCounter::s_Count);
        v42 = GetMemLogObject();
        CMemoryLog::Write(v42, -2147217398);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            804,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749898LL);
        }
        v20 = -2147217398;
        __eh34_try_continuation(0, &SafeIntException `RTTI Type Descriptor', &loc_180046987);
        goto LABEL_82;
      }
      if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
      {
        _InterlockedIncrement(&ExceptionCounter::s_Count);
        v43 = GetMemLogObject();
        CMemoryLog::Write(v43, -2147217398);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            805,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749898LL);
        }
        v20 = -2147217398;
        __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_180046987);
        goto LABEL_82;
      }
    }
    if ( v44 < 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, v44);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          806,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v44);
      }
      v20 = v44;
      if ( !v18 )
        goto LABEL_26;
      goto LABEL_25;
    }
    v19 = *(_QWORD *)v18;
    if ( (a4 & 0x10) != 0 )
    {
      if ( !v13 )
      {
        (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(v19 + 112))(v18, 0);
        v20 = 0;
        v44 = 0;
LABEL_23:
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_25;
        }
        v28 = 809;
        v29 = v20;
        goto LABEL_40;
      }
      v22 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemCallResult **))(v19 + 88))(
              v18,
              0,
              &IID_IWbemCallResult,
              v13);
      goto LABEL_19;
    }
    v20 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, int *))(v19 + 104))(
            v18,
            0,
            0xFFFFFFFFLL,
            &v44);
    if ( (v20 & 0x80000000) != 0 )
    {
LABEL_25:
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_26:
      v45 = 0;
      return v20;
    }
    if ( v44 < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v44);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v28 = 807;
    }
    else
    {
      v21 = *(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemClassObject **))(*(_QWORD *)v18 + 88LL);
      if ( !v13 )
      {
        v22 = v21(v18, 0, &IID_IWbemClassObject, v12);
        goto LABEL_19;
      }
      v22 = v21(v18, 0, &IID_IWbemCallResult, (struct IWbemClassObject **)v13);
      v20 = v22;
      v44 = v22;
      if ( v22 >= 0 )
      {
        if ( !v12 )
        {
LABEL_21:
          if ( v22 < 0 )
          {
            v26 = GetMemLogObject();
            CMemoryLog::Write(v26, v44);
            v20 = v44;
          }
          goto LABEL_23;
        }
        v22 = ((__int64 (__fastcall *)(struct IWbemCallResult *, __int64, struct IWbemClassObject **))(*v13)->lpVtbl->GetResultObject)(
                *v13,
                0xFFFFFFFFLL,
                v12);
LABEL_19:
        v44 = v22;
        v20 = v22;
        if ( v22 == -2147217406 )
        {
          v20 = 0;
          v22 = 0;
          v44 = 0;
        }
        goto LABEL_21;
      }
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, v44);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v28 = 808;
    }
    v29 = (unsigned int)v44;
LABEL_40:
    WPP_SF_d(*((_QWORD *)v23 + 2), v28, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v29);
LABEL_31:
    v20 = v44;
    goto LABEL_25;
  }
  v40 = GetMemLogObject();
  CMemoryLog::Write(v40, v44);
  v36 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v37 = 802;
LABEL_75:
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v44);
  }
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x1800463a0  mov     rax, rsp
0x1800463a3  mov     [rax+8], rbx
0x1800463a7  mov     [rax+20h], rsi
0x1800463ab  mov     [rax+18h], r8
0x1800463af  mov     [rax+10h], rdx
0x1800463b3  push    rdi
0x1800463b4  push    r12
0x1800463b6  push    r13
0x1800463b8  push    r14
0x1800463ba  push    r15
0x1800463bc  sub     rsp, 60h
0x1800463c0  mov     r13d, r9d
0x1800463c3  mov     rdi, r8
0x1800463c6  mov     r12, rdx
0x1800463c9  mov     rbx, rcx
0x1800463cc  call    ?IsCallFromLowIntegrityClient@@YAHXZ; IsCallFromLowIntegrityClient(void)
0x1800463d1  test    eax, eax
0x1800463d3  jnz     loc_180046746
0x1800463d9  mov     r15, [rsp+88h+arg_30]
0x1800463e1  test    r15, r15
0x1800463e4  jnz     loc_1800465C5
0x1800463ea  mov     r14, [rsp+88h+arg_38]
0x1800463f2  test    r14, r14
0x1800463f5  jnz     loc_1800467B4
0x1800463fb  mov     rcx, rbx; this
0x1800463fe  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180046403  mov     [rsp+88h+var_38], eax
0x180046407  test    eax, eax
0x180046409  js      loc_1800467D8
0x18004640f  lea     rdx, [rsp+88h+arg_20]; struct IWbemContext **
0x180046417  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x18004641c  mov     [rsp+88h+var_38], eax
0x180046420  test    eax, eax
0x180046422  js      loc_180046820
0x180046428  lea     rsi, WPP_GLOBAL_Control
0x18004642f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046436  cmp     rcx, rsi
0x180046439  jz      short loc_180046445
0x18004643b  test    byte ptr [rcx+1Ch], 1
0x18004643f  jnz     loc_180046868
0x180046445  test    r15, r15
0x180046448  jz      short loc_180046451
0x18004644a  mov     qword ptr [r15], 0
0x180046451  test    r13d, 0FFFFFFEFh
0x180046458  jnz     loc_1800468A9
0x18004645e  mov     [rsp+88h+var_30], 0
0x180046467  lea     r8, [rsp+88h+var_30]; struct _IWmiFinalizer **
0x18004646c  mov     r12, [rsp+88h+arg_20]
0x180046474  mov     rdx, r12; struct IWbemContext *
0x180046477  mov     rcx, rbx; this
0x18004647a  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x18004647f  mov     [rsp+88h+var_38], eax
0x180046483  test    eax, eax
0x180046485  js      loc_1800468E8
0x18004648b  mov     rdi, [rsp+88h+var_30]
0x180046490  mov     [rsp+88h+var_30], rdi
0x180046495  mov     rax, r14
0x180046498  neg     rax
0x18004649b  sbb     edx, edx
0x18004649d  and     edx, 1000000h
0x1800464a3  add     edx, 100000Bh; unsigned int
0x1800464a9  mov     [rsp+88h+var_40], 0; struct IWbemObjectSink *
0x1800464b2  mov     rax, [rsp+88h+arg_28]
0x1800464ba  mov     [rsp+88h+var_48], rax; struct IWbemClassObject *
0x1800464bf  mov     [rsp+88h+var_50], r12; struct IWbemContext *
0x1800464c4  xor     r12d, r12d
0x1800464c7  mov     [rsp+88h+var_58], r12d; int
0x1800464cc  mov     rax, [rsp+88h+arg_10]
0x1800464d4  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800464d9  mov     rax, [rsp+88h+arg_8]
0x1800464e1  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x1800464e6  xor     r9d, r9d; struct _IWmiCoreHandle *
0x1800464e9  mov     r8, rdi; struct _IWmiFinalizer *
0x1800464ec  mov     rcx, rbx; this
0x1800464ef  call    ?_ExecMethodAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_ExecMethodAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)
0x1800464f4  mov     [rsp+88h+var_38], eax
0x1800464f8  cmp     [rsp+88h+var_38], r12d
0x1800464fd  jl      loc_180046711
0x180046503  mov     rax, [rdi]
0x180046506  xor     edx, edx
0x180046508  mov     rcx, rdi
0x18004650b  test    r13b, 10h
0x18004650f  jnz     loc_18004662F
0x180046515  lea     r9, [rsp+88h+var_38]
0x18004651a  or      r8d, 0FFFFFFFFh
0x18004651e  mov     rax, [rax+68h]
0x180046522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046527  mov     ebx, eax
0x180046529  test    eax, eax
0x18004652b  js      loc_180046705
0x180046531  cmp     [rsp+88h+var_38], r12d
0x180046536  jl      loc_1800465E9
0x18004653c  mov     rax, [rdi]
0x18004653f  xor     edx, edx
0x180046541  mov     rcx, rdi
0x180046544  mov     rax, [rax+58h]
0x180046548  test    r14, r14
0x18004654b  jnz     loc_18004664D
0x180046551  mov     r9, r15
0x180046554  lea     r8, IID_IWbemClassObject
0x18004655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046560  cmp     eax, 80041002h
0x180046565  mov     [rsp+88h+var_38], eax
0x180046569  mov     ebx, eax
0x18004656b  jnz     short loc_180046577
0x18004656d  mov     ebx, r12d
0x180046570  mov     eax, r12d
0x180046573  mov     [rsp+88h+var_38], ebx
0x180046577  test    eax, eax
0x180046579  js      loc_180046613
0x18004657f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046586  cmp     rcx, rsi
0x180046589  jz      short loc_180046595
0x18004658b  test    byte ptr [rcx+1Ch], 1
0x18004658f  jnz     loc_180046969
0x180046595  mov     rax, [rdi]
0x180046598  mov     rax, [rax+10h]
0x18004659c  mov     rcx, rdi
0x18004659f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465a4  mov     [rsp+88h+var_30], r12
0x1800465a9  mov     eax, ebx
0x1800465ab  lea     r11, [rsp+88h+var_28]
0x1800465b0  mov     rbx, [r11+30h]
0x1800465b4  mov     rsi, [r11+48h]
0x1800465b8  mov     rsp, r11
0x1800465bb  pop     r15
0x1800465bd  pop     r14
0x1800465bf  pop     r13
0x1800465c1  pop     r12
0x1800465c3  pop     rdi
0x1800465c4  retn
0x1800465c5  mov     rcx, [r15]
0x1800465c8  test    rcx, rcx
0x1800465cb  jz      loc_1800463EA
0x1800465d1  mov     rax, [rcx]
0x1800465d4  mov     rax, [rax+10h]
0x1800465d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465dd  mov     qword ptr [r15], 0
0x1800465e4  jmp     loc_1800463EA
0x1800465e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800465ef  nop
0x1800465f0  mov     edx, [rsp+88h+var_38]
0x1800465f4  mov     rcx, rax
0x1800465f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800465fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180046604  cmp     rcx, rsi
0x180046607  jnz     loc_1800466B4
0x18004660d  mov     ebx, [rsp+88h+var_38]
0x180046611  jmp     short loc_180046595
0x180046613  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046619  mov     edx, [rsp+88h+var_38]
0x18004661d  mov     rcx, rax
0x180046620  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046626  mov     ebx, [rsp+88h+var_38]
0x18004662a  jmp     loc_18004657F
0x18004662f  test    r14, r14
0x180046632  jnz     loc_1800466F2
0x180046638  mov     rax, [rax+70h]
0x18004663c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046641  mov     ebx, r12d
0x180046644  mov     [rsp+88h+var_38], ebx
0x180046648  jmp     loc_18004657F
0x18004664d  mov     r9, r14
0x180046650  lea     r8, IID_IWbemCallResult
0x180046657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004665c  mov     ebx, eax
0x18004665e  mov     [rsp+88h+var_38], eax
0x180046662  test    eax, eax
0x180046664  jns     short loc_1800466CF
0x180046666  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004666c  mov     edx, [rsp+88h+var_38]
0x180046670  mov     rcx, rax
0x180046673  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046679  mov     rcx, cs:WPP_GLOBAL_Control
0x180046680  cmp     rcx, rsi
0x180046683  jz      short loc_18004660D
0x180046685  test    byte ptr [rcx+1Ch], 1
0x180046689  jz      short loc_18004660D
0x18004668b  cmp     byte ptr [rcx+19h], 2
0x18004668f  jb      loc_18004660D
0x180046695  mov     edx, 328h
0x18004669a  mov     r9d, [rsp+88h+var_38]
0x18004669f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800466a6  mov     rcx, [rcx+10h]
0x1800466aa  call    WPP_SF_d
0x1800466af  jmp     loc_18004660D
0x1800466b4  test    byte ptr [rcx+1Ch], 1
0x1800466b8  jz      loc_18004660D
0x1800466be  cmp     byte ptr [rcx+19h], 2
0x1800466c2  jb      loc_18004660D
0x1800466c8  mov     edx, 327h
0x1800466cd  jmp     short loc_18004669A
0x1800466cf  test    r15, r15
0x1800466d2  jz      loc_180046577
0x1800466d8  mov     rcx, [r14]
0x1800466db  mov     rax, [rcx]
0x1800466de  mov     r8, r15
0x1800466e1  or      edx, 0FFFFFFFFh
0x1800466e4  mov     rax, [rax+18h]
0x1800466e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466ed  jmp     loc_180046560
0x1800466f2  mov     r9, r14
0x1800466f5  lea     r8, IID_IWbemCallResult
0x1800466fc  mov     rax, [rax+58h]
0x180046700  jmp     loc_18004655B
0x180046705  mov     rcx, [rdi]
0x180046708  mov     rax, [rcx+10h]
0x18004670c  jmp     loc_18004659C
0x180046711  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046717  mov     edx, [rsp+88h+var_38]
0x18004671b  mov     rcx, rax
0x18004671e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046724  mov     rcx, cs:WPP_GLOBAL_Control
0x18004672b  cmp     rcx, rsi
0x18004672e  jnz     loc_180046936
0x180046734  mov     ebx, [rsp+88h+var_38]
0x180046738  test    rdi, rdi
0x18004673b  jnz     loc_180046595
0x180046741  jmp     loc_1800465A4
0x180046746  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004674c  mov     ebx, 80041003h
0x180046751  mov     edx, ebx
0x180046753  mov     rcx, rax
0x180046756  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004675c  lea     rsi, WPP_GLOBAL_Control
0x180046763  mov     rcx, cs:WPP_GLOBAL_Control
0x18004676a  cmp     rcx, rsi
0x18004676d  jz      loc_1800465A9
0x180046773  test    byte ptr [rcx+1Ch], 1
0x180046777  jz      loc_1800465A9
0x18004677d  cmp     byte ptr [rcx+19h], 2
0x180046781  jb      loc_1800465A9
0x180046787  mov     edx, 31Dh
0x18004678c  mov     r9d, 80041003h
0x180046792  jmp     short loc_18004679F
0x180046794  mov     edx, 321h
0x180046799  mov     r9d, 80041008h
0x18004679f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800467a6  mov     rcx, [rcx+10h]
0x1800467aa  call    WPP_SF_d
0x1800467af  jmp     loc_1800465A9
0x1800467b4  mov     rcx, [r14]
0x1800467b7  test    rcx, rcx
0x1800467ba  jz      loc_1800463FB
0x1800467c0  mov     rax, [rcx]
0x1800467c3  mov     rax, [rax+10h]
0x1800467c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467cc  mov     qword ptr [r14], 0
0x1800467d3  jmp     loc_1800463FB
0x1800467d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800467de  mov     edx, [rsp+88h+var_38]
0x1800467e2  mov     rcx, rax
0x1800467e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800467eb  lea     rsi, WPP_GLOBAL_Control
0x1800467f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467f9  cmp     rcx, rsi
0x1800467fc  jz      loc_18004692D
0x180046802  test    byte ptr [rcx+1Ch], 1
0x180046806  jz      loc_18004692D
0x18004680c  cmp     byte ptr [rcx+19h], 2
0x180046810  jb      loc_18004692D
0x180046816  mov     edx, 31Eh
0x18004681b  jmp     loc_180046918
0x180046820  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046826  mov     edx, [rsp+88h+var_38]
0x18004682a  mov     rcx, rax
0x18004682d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046833  lea     rsi, WPP_GLOBAL_Control
0x18004683a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046841  cmp     rcx, rsi
0x180046844  jz      loc_18004692D
0x18004684a  test    byte ptr [rcx+1Ch], 1
0x18004684e  jz      loc_18004692D
0x180046854  cmp     byte ptr [rcx+19h], 2
0x180046858  jb      loc_18004692D
0x18004685e  mov     edx, 31Fh
0x180046863  jmp     loc_180046918
0x180046868  cmp     byte ptr [rcx+19h], 5
0x18004686c  jb      loc_180046445
0x180046872  mov     edx, 320h
0x180046877  mov     eax, [rbx+130h]
0x18004687d  mov     dword ptr [rsp+88h+var_50], eax
0x180046881  mov     rax, [rsp+88h+arg_28]
0x180046889  mov     qword ptr [rsp+88h+var_58], rax
0x18004688e  mov     dword ptr [rsp+88h+var_60], r13d
0x180046893  mov     [rsp+88h+var_68], rdi
0x180046898  mov     r9, r12
0x18004689b  mov     rcx, [rcx+10h]
0x18004689f  call    WPP_SF_SSdql
0x1800468a4  jmp     loc_180046445
0x1800468a9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800468af  mov     ebx, 80041008h
0x1800468b4  mov     edx, ebx
0x1800468b6  mov     rcx, rax
0x1800468b9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800468bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468c6  cmp     rcx, rsi
0x1800468c9  jz      loc_1800465A9
0x1800468cf  test    byte ptr [rcx+1Ch], 1
0x1800468d3  jz      loc_1800465A9
  ... truncated ...
```
