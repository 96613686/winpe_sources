# CWbemNamespace::DeleteInstance(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x180064130`
- end: `0x18006461f`
- name: `?DeleteInstance@CWbemNamespace@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `1263`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemCallResult **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009bd1c`

## callees

- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x18003cfe0`
- `0x1800469a4`
- `0x180047ed0`
- `0x180064130`
- `0x180064630`
- `0x1800a21cc`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180064308`
- `wbemcomn!GetMemLogObject` at `0x180064366`
- `wbemcomn!GetMemLogObject` at `0x1800643be`
- `wbemcomn!GetMemLogObject` at `0x180064443`
- `wbemcomn!GetMemLogObject` at `0x1800644b5`
- `wbemcomn!GetMemLogObject` at `0x1800644f1`
- `wbemcomn!GetMemLogObject` at `0x180064575`
- `wbemcomn!GetMemLogObject` at `0x1800645e6`
- `wbemcomn!GetMemLogObject` at `0x180064308`
- `wbemcomn!GetMemLogObject` at `0x180064366`
- `wbemcomn!GetMemLogObject` at `0x1800643be`
- `wbemcomn!GetMemLogObject` at `0x180064443`
- `wbemcomn!GetMemLogObject` at `0x1800644b5`
- `wbemcomn!GetMemLogObject` at `0x1800644f1`
- `wbemcomn!GetMemLogObject` at `0x180064575`
- `wbemcomn!GetMemLogObject` at `0x1800645e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064373`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800643ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064450`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064582`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800645f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064373`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800643ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064450`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180064582`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800645f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemNamespace::DeleteInstance(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  int v6; // ebx
  struct IWbemCallResult **v8; // r14
  CWbemNamespace *v9; // rcx
  int v10; // edx
  int v11; // r8d
  struct IWbemContext *v12; // r13
  struct _IWmiFinalizer *v13; // rbx
  int v14; // esi
  CMemoryLog *v16; // rax
  CClientCnt *v17; // rcx
  CMemoryLog *v18; // rax
  __int64 v19; // rdx
  CMemoryLog *MemLogObject; // rax
  unsigned int v21; // ebx
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CClientCnt *v24; // rcx
  __int64 v25; // rdx
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  int v32; // [rsp+40h] [rbp-38h] BYREF
  struct _IWmiFinalizer *v33; // [rsp+48h] [rbp-30h] BYREF
  struct IWbemContext *v35; // [rsp+98h] [rbp+20h] BYREF

  v35 = a4;
  v6 = (int)a2;
  if ( (unsigned int)IsCallFromLowIntegrityClient() )
  {
    MemLogObject = GetMemLogObject();
    v21 = -2147217405;
    CMemoryLog::Write(MemLogObject, -2147217405);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 766, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
    }
    return v21;
  }
  v8 = a5;
  if ( a5 && *a5 )
  {
    ((void (__fastcall *)(_QWORD))(*a5)->lpVtbl->Release)(*a5);
    *v8 = 0;
  }
  v32 = CWbemNamespace::CheckNs(this);
  if ( v32 < 0 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, v32);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v32;
    }
    v19 = 767;
    goto LABEL_62;
  }
  v32 = CWbemNamespace::AdjustCtx(v9, &v35);
  if ( v32 < 0 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, v32);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v32;
    }
    v19 = 768;
    goto LABEL_62;
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdl(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v6, a3, *((_DWORD *)this + 76));
  }
  if ( (a3 & 0xFFFEFFEF) != 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217400);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v25 = 770;
    goto LABEL_57;
  }
  if ( (a3 & 0x10) != 0 && !v8 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2147217400);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v25 = 771;
LABEL_57:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v33 = 0;
  v12 = v35;
  v32 = CWbemNamespace::CreateSyncFinalizer(this, v35, &v33);
  if ( v32 < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v32);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v32;
    }
    v19 = 772;
LABEL_62:
    WPP_SF_d(*((_QWORD *)v17 + 2), v19, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v32);
    return (unsigned int)v32;
  }
  v13 = v33;
  try
  {
    v32 = CWbemNamespace::_DeleteInstanceAsync(this, v8 != 0 ? 33554436 : 16777220, v33, 0, a2, a3 & 0xFFFFFFEF, v12, 0);
  }
  catch ( CX_MemoryException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 773, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v21 = -2147217402;
    goto LABEL_68;
  }
  catch ( SafeIntException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 774, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    v21 = -2147217398;
    goto LABEL_68;
  }
  catch ( CX_Exception )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 775, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    v21 = -2147217398;
    goto LABEL_68;
  }
  v14 = v32;
  if ( v32 >= 0 )
  {
    if ( (a3 & 0x10) == 0 )
    {
      v14 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, int *))(*(_QWORD *)v13 + 104LL))(
              v13,
              0,
              0xFFFFFFFFLL,
              &v32);
      if ( v14 < 0 )
        goto LABEL_20;
      v14 = v32;
    }
    if ( v8 )
    {
      v14 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemCallResult **))(*(_QWORD *)v13 + 88LL))(
              v13,
              0,
              &IID_IWbemCallResult,
              v8);
      v32 = v14;
    }
    if ( v14 == -2147217406 )
    {
      if ( v13 )
        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v13 + 16LL))(v13);
      v14 = -2147217406;
      goto LABEL_21;
    }
    if ( v14 < 0 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, v32);
      v14 = v32;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        777,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v14);
      v14 = v32;
    }
    if ( !v13 )
    {
LABEL_21:
      v33 = 0;
      return (unsigned int)v14;
    }
LABEL_20:
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_21;
  }
  v27 = GetMemLogObject();
  CMemoryLog::Write(v27, v32);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      776,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)v32);
  }
  v21 = v32;
LABEL_68:
  CReleaseMe::release((CReleaseMe *)&v33);
  return v21;
}

```

## disassembly

```asm
0x180064130  mov     rax, rsp
0x180064133  mov     [rax+8], rbx
0x180064137  mov     [rax+18h], rsi
0x18006413b  mov     [rax+20h], r9
0x18006413f  mov     [rax+10h], rdx
0x180064143  push    rdi
0x180064144  push    r12
0x180064146  push    r13
0x180064148  push    r14
0x18006414a  push    r15
0x18006414c  sub     rsp, 50h
0x180064150  mov     r15d, r8d
0x180064153  mov     rbx, rdx
0x180064156  mov     rsi, rcx
0x180064159  call    ?IsCallFromLowIntegrityClient@@YAHXZ; IsCallFromLowIntegrityClient(void)
0x18006415e  test    eax, eax
0x180064160  jnz     loc_1800643BE
0x180064166  mov     r14, [rsp+78h+arg_20]
0x18006416e  test    r14, r14
0x180064171  jnz     loc_18006441F
0x180064177  mov     rcx, rsi; this
0x18006417a  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18006417f  mov     [rsp+78h+var_38], eax
0x180064183  test    eax, eax
0x180064185  js      loc_180064366
0x18006418b  lea     rdx, [rsp+78h+arg_18]; struct IWbemContext **
0x180064193  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x180064198  mov     [rsp+78h+var_38], eax
0x18006419c  test    eax, eax
0x18006419e  js      loc_180064443
0x1800641a4  lea     rdi, WPP_GLOBAL_Control
0x1800641ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800641b2  cmp     rcx, rdi
0x1800641b5  jz      short loc_1800641C1
0x1800641b7  test    byte ptr [rcx+1Ch], 1
0x1800641bb  jnz     loc_18006448B
0x1800641c1  test    r15d, 0FFFEFFEFh
0x1800641c8  jnz     loc_1800644B5
0x1800641ce  mov     r12d, r15d
0x1800641d1  and     r12d, 10h
0x1800641d5  jnz     loc_1800644E8
0x1800641db  mov     [rsp+78h+var_30], 0
0x1800641e4  lea     r8, [rsp+78h+var_30]; struct _IWmiFinalizer **
0x1800641e9  mov     r13, [rsp+78h+arg_18]
0x1800641f1  mov     rdx, r13; struct IWbemContext *
0x1800641f4  mov     rcx, rsi; this
0x1800641f7  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x1800641fc  mov     [rsp+78h+var_38], eax
0x180064200  test    eax, eax
0x180064202  js      loc_180064308
0x180064208  mov     rbx, [rsp+78h+var_30]
0x18006420d  mov     [rsp+78h+var_30], rbx
0x180064212  mov     rax, r14
0x180064215  neg     rax
0x180064218  sbb     edx, edx
0x18006421a  and     edx, 1000000h
0x180064220  add     edx, 1000004h; unsigned int
0x180064226  and     r15d, 0FFFFFFEFh
0x18006422a  mov     [rsp+78h+var_40], 0; struct IWbemObjectSink *
0x180064233  mov     [rsp+78h+var_48], r13; struct IWbemContext *
0x180064238  mov     [rsp+78h+var_50], r15d; int
0x18006423d  mov     rax, [rsp+78h+arg_8]
0x180064245  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18006424a  xor     r9d, r9d; struct _IWmiCoreHandle *
0x18006424d  mov     r8, rbx; struct _IWmiFinalizer *
0x180064250  mov     rcx, rsi; this
0x180064253  call    ?_DeleteInstanceAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_DeleteInstanceAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x180064258  mov     [rsp+78h+var_38], eax
0x18006425c  mov     esi, [rsp+78h+var_38]
0x180064260  test    esi, esi
0x180064262  js      loc_180064575
0x180064268  test    r12d, r12d
0x18006426b  jz      short loc_1800642D6
0x18006426d  test    r14, r14
0x180064270  jnz     loc_1800645C0
0x180064276  mov     r14d, 80041002h
0x18006427c  cmp     esi, r14d
0x18006427f  jz      loc_1800643A2
0x180064285  test    esi, esi
0x180064287  js      loc_1800645E6
0x18006428d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064294  cmp     rcx, rdi
0x180064297  jnz     loc_180064331
0x18006429d  test    rbx, rbx
0x1800642a0  jz      short loc_1800642B1
0x1800642a2  mov     rax, [rbx]
0x1800642a5  mov     rax, [rax+10h]
0x1800642a9  mov     rcx, rbx
0x1800642ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642b1  mov     [rsp+78h+var_30], 0
0x1800642ba  mov     eax, esi
0x1800642bc  lea     r11, [rsp+78h+var_28]
0x1800642c1  mov     rbx, [r11+30h]
0x1800642c5  mov     rsi, [r11+40h]
0x1800642c9  mov     rsp, r11
0x1800642cc  pop     r15
0x1800642ce  pop     r14
0x1800642d0  pop     r13
0x1800642d2  pop     r12
0x1800642d4  pop     rdi
0x1800642d5  retn
0x1800642d6  mov     rax, [rbx]
0x1800642d9  lea     r9, [rsp+78h+var_38]
0x1800642de  or      r8d, 0FFFFFFFFh
0x1800642e2  xor     edx, edx
0x1800642e4  mov     rcx, rbx
0x1800642e7  mov     rax, [rax+68h]
0x1800642eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642f0  mov     esi, eax
0x1800642f2  test    eax, eax
0x1800642f4  jns     short loc_1800642FF
0x1800642f6  mov     rdx, [rbx]
0x1800642f9  mov     rax, [rdx+10h]
0x1800642fd  jmp     short loc_1800642A9
0x1800642ff  mov     esi, [rsp+78h+var_38]
0x180064303  jmp     loc_18006426D
0x180064308  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006430e  mov     edx, [rsp+78h+var_38]
0x180064312  mov     rcx, rax
0x180064315  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006431b  mov     rcx, cs:WPP_GLOBAL_Control
0x180064322  cmp     rcx, rdi
0x180064325  jnz     loc_180064542
0x18006432b  mov     eax, [rsp+78h+var_38]
0x18006432f  jmp     short loc_1800642BC
0x180064331  test    byte ptr [rcx+1Ch], 1
0x180064335  jz      loc_18006429D
0x18006433b  cmp     byte ptr [rcx+19h], 2
0x18006433f  jb      loc_18006429D
0x180064345  mov     edx, 309h
0x18006434a  mov     r9d, esi
0x18006434d  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180064354  mov     rcx, [rcx+10h]
0x180064358  call    WPP_SF_d
0x18006435d  mov     esi, [rsp+78h+var_38]
0x180064361  jmp     loc_18006429D
0x180064366  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006436c  mov     edx, [rsp+78h+var_38]
0x180064370  mov     rcx, rax
0x180064373  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064379  lea     rdi, WPP_GLOBAL_Control
0x180064380  mov     rcx, cs:WPP_GLOBAL_Control
0x180064387  cmp     rcx, rdi
0x18006438a  jz      short loc_18006432B
0x18006438c  test    byte ptr [rcx+1Ch], 1
0x180064390  jz      short loc_18006432B
0x180064392  cmp     byte ptr [rcx+19h], 2
0x180064396  jb      short loc_18006432B
0x180064398  mov     edx, 2FFh
0x18006439d  jmp     loc_18006455B
0x1800643a2  test    rbx, rbx
0x1800643a5  jz      short loc_1800643B6
0x1800643a7  mov     rax, [rbx]
0x1800643aa  mov     rcx, rbx
0x1800643ad  mov     rax, [rax+10h]
0x1800643b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643b6  mov     esi, r14d
0x1800643b9  jmp     loc_1800642B1
0x1800643be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800643c4  mov     ebx, 80041003h
0x1800643c9  mov     edx, ebx
0x1800643cb  mov     rcx, rax
0x1800643ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800643d4  lea     rdi, WPP_GLOBAL_Control
0x1800643db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800643e2  cmp     rcx, rdi
0x1800643e5  jz      loc_180064618
0x1800643eb  test    byte ptr [rcx+1Ch], 1
0x1800643ef  jz      loc_180064618
0x1800643f5  cmp     byte ptr [rcx+19h], 2
0x1800643f9  jb      loc_180064618
0x1800643ff  mov     edx, 2FEh
0x180064404  mov     r9d, 80041003h
0x18006440a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180064411  mov     rcx, [rcx+10h]
0x180064415  call    WPP_SF_d
0x18006441a  jmp     loc_180064618
0x18006441f  mov     rcx, [r14]
0x180064422  test    rcx, rcx
0x180064425  jz      loc_180064177
0x18006442b  mov     rax, [rcx]
0x18006442e  mov     rax, [rax+10h]
0x180064432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064437  mov     qword ptr [r14], 0
0x18006443e  jmp     loc_180064177
0x180064443  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180064449  mov     edx, [rsp+78h+var_38]
0x18006444d  mov     rcx, rax
0x180064450  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064456  lea     rdi, WPP_GLOBAL_Control
0x18006445d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064464  cmp     rcx, rdi
0x180064467  jz      loc_18006432B
0x18006446d  test    byte ptr [rcx+1Ch], 1
0x180064471  jz      loc_18006432B
0x180064477  cmp     byte ptr [rcx+19h], 2
0x18006447b  jb      loc_18006432B
0x180064481  mov     edx, 300h
0x180064486  jmp     loc_18006455B
0x18006448b  cmp     byte ptr [rcx+19h], 5
0x18006448f  jb      loc_1800641C1
0x180064495  mov     eax, [rsi+130h]
0x18006449b  mov     [rsp+78h+var_50], eax
0x18006449f  mov     dword ptr [rsp+78h+var_58], r15d
0x1800644a4  mov     r9, rbx
0x1800644a7  mov     rcx, [rcx+10h]
0x1800644ab  call    WPP_SF_Sdl
0x1800644b0  jmp     loc_1800641C1
0x1800644b5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800644bb  mov     edx, 80041008h
0x1800644c0  mov     rcx, rax
0x1800644c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800644c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644d0  cmp     rcx, rdi
0x1800644d3  jz      short loc_180064538
0x1800644d5  test    byte ptr [rcx+1Ch], 1
0x1800644d9  jz      short loc_180064538
0x1800644db  cmp     byte ptr [rcx+19h], 2
0x1800644df  jb      short loc_180064538
0x1800644e1  mov     edx, 302h
0x1800644e6  jmp     short loc_180064522
0x1800644e8  test    r14, r14
0x1800644eb  jnz     loc_1800641DB
0x1800644f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800644f7  mov     edx, 80041008h
0x1800644fc  mov     rcx, rax
0x1800644ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064505  mov     rcx, cs:WPP_GLOBAL_Control
0x18006450c  cmp     rcx, rdi
0x18006450f  jz      short loc_180064538
0x180064511  test    byte ptr [rcx+1Ch], 1
0x180064515  jz      short loc_180064538
0x180064517  cmp     byte ptr [rcx+19h], 2
0x18006451b  jb      short loc_180064538
0x18006451d  mov     edx, 303h
0x180064522  mov     r9d, 80041008h
0x180064528  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18006452f  mov     rcx, [rcx+10h]
0x180064533  call    WPP_SF_d
0x180064538  mov     eax, 80041008h
0x18006453d  jmp     loc_1800642BC
0x180064542  test    byte ptr [rcx+1Ch], 1
0x180064546  jz      loc_18006432B
0x18006454c  cmp     byte ptr [rcx+19h], 2
0x180064550  jb      loc_18006432B
0x180064556  mov     edx, 304h
0x18006455b  mov     r9d, [rsp+78h+var_38]
0x180064560  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180064567  mov     rcx, [rcx+10h]
0x18006456b  call    WPP_SF_d
0x180064570  jmp     loc_18006432B
0x180064575  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006457b  mov     edx, [rsp+78h+var_38]
0x18006457f  mov     rcx, rax
0x180064582  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180064588  mov     rcx, cs:WPP_GLOBAL_Control
0x18006458f  cmp     rcx, rdi
0x180064592  jz      short loc_1800645BA
0x180064594  test    byte ptr [rcx+1Ch], 1
0x180064598  jz      short loc_1800645BA
0x18006459a  cmp     byte ptr [rcx+19h], 2
0x18006459e  jb      short loc_1800645BA
0x1800645a0  mov     edx, 308h
0x1800645a5  mov     r9d, [rsp+78h+var_38]
0x1800645aa  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800645b1  mov     rcx, [rcx+10h]
0x1800645b5  call    WPP_SF_d
0x1800645ba  mov     ebx, [rsp+78h+var_38]
0x1800645be  jmp     short loc_18006460E
0x1800645c0  mov     rax, [rbx]
0x1800645c3  mov     r9, r14
0x1800645c6  lea     r8, IID_IWbemCallResult
0x1800645cd  xor     edx, edx
0x1800645cf  mov     rcx, rbx
0x1800645d2  mov     rax, [rax+58h]
0x1800645d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645db  mov     esi, eax
0x1800645dd  mov     [rsp+78h+var_38], eax
0x1800645e1  jmp     loc_180064276
0x1800645e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800645ec  mov     edx, [rsp+78h+var_38]
0x1800645f0  mov     rcx, rax
0x1800645f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800645f9  mov     esi, [rsp+78h+var_38]
0x1800645fd  jmp     loc_18006428D
0x180064602  mov     ebx, 80041006h
0x180064607  jmp     short loc_18006460E
0x180064609  mov     ebx, 8004100Ah
0x18006460e  lea     rcx, [rsp+78h+var_30]; this
0x180064613  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180064618  mov     eax, ebx
0x18006461a  jmp     loc_1800642BC
```
