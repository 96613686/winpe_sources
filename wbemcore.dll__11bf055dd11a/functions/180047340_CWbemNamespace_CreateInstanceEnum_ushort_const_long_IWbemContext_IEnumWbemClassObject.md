# CWbemNamespace::CreateInstanceEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x180047340`
- end: `0x18004779c`
- name: `?CreateInstanceEnum@CWbemNamespace@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `1116`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x18003cfe0`
- `0x180047340`
- `0x1800477b0`
- `0x180047ed0`
- `0x1800a1c20`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180047558`
- `wbemcomn!GetMemLogObject` at `0x180047572`
- `wbemcomn!GetMemLogObject` at `0x1800475ba`
- `wbemcomn!GetMemLogObject` at `0x180047639`
- `wbemcomn!GetMemLogObject` at `0x18004766c`
- `wbemcomn!GetMemLogObject` at `0x1800476bd`
- `wbemcomn!GetMemLogObject` at `0x18004770b`
- `wbemcomn!GetMemLogObject` at `0x180047558`
- `wbemcomn!GetMemLogObject` at `0x180047572`
- `wbemcomn!GetMemLogObject` at `0x1800475ba`
- `wbemcomn!GetMemLogObject` at `0x180047639`
- `wbemcomn!GetMemLogObject` at `0x18004766c`
- `wbemcomn!GetMemLogObject` at `0x1800476bd`
- `wbemcomn!GetMemLogObject` at `0x18004770b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047566`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004757f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800475c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047647`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004767a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800476ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047718`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047566`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004757f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800475c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047647`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004767a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800476ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047718`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::CreateInstanceEnum(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  CWbemNamespace *v8; // rcx
  int v9; // edx
  int v10; // r8d
  struct IEnumWbemClassObject **v11; // r14
  struct IWbemContext *v12; // r13
  struct _IWmiFinalizer *v13; // rsi
  int v14; // eax
  unsigned int v15; // ebx
  struct _IWmiFinalizer *v16; // rbx
  struct _IWmiFinalizer *v17; // rcx
  CMemoryLog *v19; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v21; // rcx
  __int64 v22; // rdx
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CClientCnt *v25; // rcx
  __int64 v26; // rdx
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  int InstanceEnumAsync; // [rsp+40h] [rbp-48h] BYREF
  struct _IWmiFinalizer *v34; // [rsp+48h] [rbp-40h] BYREF
  struct _IWmiFinalizer *v35; // [rsp+50h] [rbp-38h] BYREF
  struct _IWmiFinalizer *v36; // [rsp+58h] [rbp-30h]
  struct IWbemContext *v38; // [rsp+A8h] [rbp+20h] BYREF

  v38 = a4;
  InstanceEnumAsync = CWbemNamespace::CheckNs(this);
  if ( InstanceEnumAsync < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, InstanceEnumAsync);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)InstanceEnumAsync;
    }
    v22 = 810;
    goto LABEL_49;
  }
  InstanceEnumAsync = CWbemNamespace::AdjustCtx(v8, &v38);
  if ( InstanceEnumAsync >= 0 )
  {
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      v11 = a5;
    }
    else
    {
      v11 = a5;
      WPP_SF_DSql(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a3, (__int64)a2, (char)a5, *((_DWORD *)this + 76));
    }
    if ( (a3 & 0xFFFDFDCE) != 0 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, -2147217400);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v26 = 813;
    }
    else
    {
      if ( v11 )
      {
        *v11 = 0;
        v34 = 0;
        v12 = v38;
        InstanceEnumAsync = CWbemNamespace::CreateSyncFinalizer(this, v38, &v34);
        if ( InstanceEnumAsync >= 0 )
        {
          v13 = v34;
          v35 = v34;
          try
          {
            InstanceEnumAsync = CWbemNamespace::_CreateInstanceEnumAsync(
                                  this,
                                  (a3 & 0x10) != 0 ? 33554437 : 16777221,
                                  v34,
                                  0,
                                  a2,
                                  a3 & 0xFFFFFFCF,
                                  v12,
                                  0);
          }
          catch ( CX_MemoryException )
          {
            _InterlockedIncrement(&ExceptionCounter::s_Count);
            v30 = GetMemLogObject();
            CMemoryLog::Write(v30, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                816,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749894LL);
            }
            v15 = -2147217402;
            goto LABEL_58;
          }
          catch ( SafeIntException )
          {
            _InterlockedIncrement(&ExceptionCounter::s_Count);
            v31 = GetMemLogObject();
            CMemoryLog::Write(v31, -2147217398);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                817,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749898LL);
            }
            v15 = -2147217398;
            goto LABEL_58;
          }
          catch ( CX_Exception )
          {
            _InterlockedIncrement(&ExceptionCounter::s_Count);
            v32 = GetMemLogObject();
            CMemoryLog::Write(v32, -2147217398);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                818,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749898LL);
            }
            v15 = -2147217398;
            goto LABEL_58;
          }
          v14 = InstanceEnumAsync;
          if ( InstanceEnumAsync < 0 )
          {
            v29 = GetMemLogObject();
            CMemoryLog::Write(v29, InstanceEnumAsync);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                819,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)InstanceEnumAsync);
            }
            v15 = InstanceEnumAsync;
LABEL_58:
            CReleaseMe::release((CReleaseMe *)&v35);
            return v15;
          }
          if ( (a3 & 0x10) == 0 )
          {
            (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, int *))(*(_QWORD *)v13 + 104LL))(
              v13,
              0,
              0xFFFFFFFFLL,
              &InstanceEnumAsync);
            v14 = InstanceEnumAsync;
          }
          if ( v14 < 0 )
            goto LABEL_24;
          v34 = 0;
          v15 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct _IWmiFinalizer **))(*(_QWORD *)v13 + 88LL))(
                  v13,
                  a3,
                  &IID_IEnumWbemClassObject,
                  &v34);
          if ( (v15 & 0x80000000) != 0 )
          {
LABEL_21:
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_22:
            v35 = 0;
            return v15;
          }
          v16 = v34;
          v36 = v34;
          v17 = v34;
          *v11 = (struct IEnumWbemClassObject *)v34;
          (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v17 + 8LL))(v17);
          if ( v16 )
            (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v16 + 16LL))(v16);
          v36 = 0;
          v15 = InstanceEnumAsync;
          if ( InstanceEnumAsync < 0 )
          {
LABEL_24:
            v19 = GetMemLogObject();
            CMemoryLog::Write(v19, InstanceEnumAsync);
            v15 = InstanceEnumAsync;
          }
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 820, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v15);
            v15 = InstanceEnumAsync;
          }
          if ( !v13 )
            goto LABEL_22;
          goto LABEL_21;
        }
        v28 = GetMemLogObject();
        CMemoryLog::Write(v28, InstanceEnumAsync);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)InstanceEnumAsync;
        }
        v22 = 815;
        goto LABEL_49;
      }
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, -2147217400);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v26 = 814;
    }
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v23 = GetMemLogObject();
  CMemoryLog::Write(v23, InstanceEnumAsync);
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)InstanceEnumAsync;
  }
  v22 = 811;
LABEL_49:
  WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)InstanceEnumAsync);
  return (unsigned int)InstanceEnumAsync;
}

```

## disassembly

```asm
0x180047340  mov     rax, rsp
0x180047343  mov     [rax+8], rbx
0x180047347  mov     [rax+18h], rsi
0x18004734b  mov     [rax+20h], r9
0x18004734f  mov     [rax+10h], rdx
0x180047353  push    rdi
0x180047354  push    r12
0x180047356  push    r13
0x180047358  push    r14
0x18004735a  push    r15
0x18004735c  sub     rsp, 60h
0x180047360  mov     r12d, r8d
0x180047363  mov     rsi, rdx
0x180047366  mov     rbx, rcx
0x180047369  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18004736e  mov     [rsp+88h+var_48], eax
0x180047372  test    eax, eax
0x180047374  js      loc_180047572
0x18004737a  lea     rdx, [rsp+88h+arg_18]; struct IWbemContext **
0x180047382  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x180047387  mov     [rsp+88h+var_48], eax
0x18004738b  test    eax, eax
0x18004738d  js      loc_1800475BA
0x180047393  lea     rdi, WPP_GLOBAL_Control
0x18004739a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473a1  cmp     rcx, rdi
0x1800473a4  jz      short loc_1800473B0
0x1800473a6  test    byte ptr [rcx+1Ch], 1
0x1800473aa  jnz     loc_180047602
0x1800473b0  mov     r14, [rsp+88h+arg_20]
0x1800473b8  test    r12d, 0FFFDFDCEh
0x1800473bf  jnz     loc_180047639
0x1800473c5  test    r14, r14
0x1800473c8  jz      loc_18004766C
0x1800473ce  mov     qword ptr [r14], 0
0x1800473d5  mov     [rsp+88h+var_40], 0
0x1800473de  lea     r8, [rsp+88h+var_40]; struct _IWmiFinalizer **
0x1800473e3  mov     r13, [rsp+88h+arg_18]
0x1800473eb  mov     rdx, r13; struct IWbemContext *
0x1800473ee  mov     rcx, rbx; this
0x1800473f1  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x1800473f6  mov     [rsp+88h+var_48], eax
0x1800473fa  test    eax, eax
0x1800473fc  js      loc_1800476BD
0x180047402  mov     rsi, [rsp+88h+var_40]
0x180047407  mov     [rsp+88h+var_38], rsi
0x18004740c  mov     r15d, r12d
0x18004740f  and     r15d, 10h
0x180047413  mov     eax, r15d
0x180047416  neg     eax
0x180047418  sbb     edx, edx
0x18004741a  and     edx, 1000000h
0x180047420  add     edx, 1000005h; unsigned int
0x180047426  mov     eax, r12d
0x180047429  and     eax, 0FFFFFFCFh
0x18004742c  mov     [rsp+88h+var_50], 0; struct IWbemObjectSink *
0x180047435  mov     [rsp+88h+var_58], r13; struct IWbemContext *
0x18004743a  mov     [rsp+88h+var_60], eax; int
0x18004743e  mov     rax, [rsp+88h+arg_8]
0x180047446  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004744b  xor     r9d, r9d; struct _IWmiCoreHandle *
0x18004744e  mov     r8, rsi; struct _IWmiFinalizer *
0x180047451  mov     rcx, rbx; this
0x180047454  call    ?_CreateInstanceEnumAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_CreateInstanceEnumAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x180047459  mov     [rsp+88h+var_48], eax
0x18004745d  mov     eax, [rsp+88h+var_48]
0x180047461  xor     r13d, r13d
0x180047464  test    eax, eax
0x180047466  js      loc_18004770B
0x18004746c  test    r15d, r15d
0x18004746f  jnz     short loc_18004748F
0x180047471  mov     rax, [rsi]
0x180047474  lea     r9, [rsp+88h+var_48]
0x180047479  or      r8d, 0FFFFFFFFh
0x18004747d  xor     edx, edx
0x18004747f  mov     rcx, rsi
0x180047482  mov     rax, [rax+68h]
0x180047486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004748b  mov     eax, [rsp+88h+var_48]
0x18004748f  test    eax, eax
0x180047491  js      loc_180047558
0x180047497  mov     [rsp+88h+var_40], r13
0x18004749c  mov     rax, [rsi]
0x18004749f  lea     r9, [rsp+88h+var_40]
0x1800474a4  lea     r8, IID_IEnumWbemClassObject
0x1800474ab  mov     edx, r12d
0x1800474ae  mov     rcx, rsi
0x1800474b1  mov     rax, [rax+58h]
0x1800474b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474ba  mov     ebx, eax
0x1800474bc  test    eax, eax
0x1800474be  js      loc_18004754F
0x1800474c4  mov     rbx, [rsp+88h+var_40]
0x1800474c9  mov     [rsp+88h+var_30], rbx
0x1800474ce  mov     rcx, [rsp+88h+var_40]
0x1800474d3  mov     [r14], rcx
0x1800474d6  mov     rax, [rcx]
0x1800474d9  mov     rax, [rax+8]
0x1800474dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474e2  nop
0x1800474e3  test    rbx, rbx
0x1800474e6  jz      short loc_1800474F7
0x1800474e8  mov     rax, [rbx]
0x1800474eb  mov     rcx, rbx
0x1800474ee  mov     rax, [rax+10h]
0x1800474f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474f7  mov     [rsp+88h+var_30], r13
0x1800474fc  mov     ebx, [rsp+88h+var_48]
0x180047500  test    ebx, ebx
0x180047502  js      short loc_180047558
0x180047504  mov     rcx, cs:WPP_GLOBAL_Control
0x18004750b  cmp     rcx, rdi
0x18004750e  jz      short loc_18004751A
0x180047510  test    byte ptr [rcx+1Ch], 1
0x180047514  jnz     loc_180047756
0x18004751a  test    rsi, rsi
0x18004751d  jz      short loc_18004752E
0x18004751f  mov     rax, [rsi]
0x180047522  mov     rax, [rax+10h]
0x180047526  mov     rcx, rsi
0x180047529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004752e  mov     [rsp+88h+var_38], r13
0x180047533  mov     eax, ebx
0x180047535  lea     r11, [rsp+88h+var_28]
0x18004753a  mov     rbx, [r11+30h]
0x18004753e  mov     rsi, [r11+40h]
0x180047542  mov     rsp, r11
0x180047545  pop     r15
0x180047547  pop     r14
0x180047549  pop     r13
0x18004754b  pop     r12
0x18004754d  pop     rdi
0x18004754e  retn
0x18004754f  mov     rdx, [rsi]
0x180047552  mov     rax, [rdx+10h]
0x180047556  jmp     short loc_180047526
0x180047558  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004755e  nop
0x18004755f  mov     edx, [rsp+88h+var_48]
0x180047563  mov     rcx, rax
0x180047566  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004756c  mov     ebx, [rsp+88h+var_48]
0x180047570  jmp     short loc_180047504
0x180047572  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047578  mov     edx, [rsp+88h+var_48]
0x18004757c  mov     rcx, rax
0x18004757f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047585  lea     rdi, WPP_GLOBAL_Control
0x18004758c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047593  cmp     rcx, rdi
0x180047596  jz      loc_180047702
0x18004759c  test    byte ptr [rcx+1Ch], 1
0x1800475a0  jz      loc_180047702
0x1800475a6  cmp     byte ptr [rcx+19h], 2
0x1800475aa  jb      loc_180047702
0x1800475b0  mov     edx, 32Ah
0x1800475b5  jmp     loc_1800476ED
0x1800475ba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800475c0  mov     edx, [rsp+88h+var_48]
0x1800475c4  mov     rcx, rax
0x1800475c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800475cd  lea     rdi, WPP_GLOBAL_Control
0x1800475d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475db  cmp     rcx, rdi
0x1800475de  jz      loc_180047702
0x1800475e4  test    byte ptr [rcx+1Ch], 1
0x1800475e8  jz      loc_180047702
0x1800475ee  cmp     byte ptr [rcx+19h], 2
0x1800475f2  jb      loc_180047702
0x1800475f8  mov     edx, 32Bh
0x1800475fd  jmp     loc_1800476ED
0x180047602  cmp     byte ptr [rcx+19h], 5
0x180047606  jb      loc_1800473B0
0x18004760c  mov     eax, [rbx+130h]
0x180047612  mov     dword ptr [rsp+88h+var_58], eax
0x180047616  mov     r14, [rsp+88h+arg_20]
0x18004761e  mov     qword ptr [rsp+88h+var_60], r14
0x180047623  mov     [rsp+88h+var_68], rsi
0x180047628  mov     r9d, r12d
0x18004762b  mov     rcx, [rcx+10h]
0x18004762f  call    WPP_SF_DSql
0x180047634  jmp     loc_1800473B8
0x180047639  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004763f  mov     edx, 80041008h
0x180047644  mov     rcx, rax
0x180047647  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004764d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047654  cmp     rcx, rdi
0x180047657  jz      short loc_1800476B3
0x180047659  test    byte ptr [rcx+1Ch], 1
0x18004765d  jz      short loc_1800476B3
0x18004765f  cmp     byte ptr [rcx+19h], 2
0x180047663  jb      short loc_1800476B3
0x180047665  mov     edx, 32Dh
0x18004766a  jmp     short loc_18004769D
0x18004766c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047672  mov     edx, 80041008h
0x180047677  mov     rcx, rax
0x18004767a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047680  mov     rcx, cs:WPP_GLOBAL_Control
0x180047687  cmp     rcx, rdi
0x18004768a  jz      short loc_1800476B3
0x18004768c  test    byte ptr [rcx+1Ch], 1
0x180047690  jz      short loc_1800476B3
0x180047692  cmp     byte ptr [rcx+19h], 2
0x180047696  jb      short loc_1800476B3
0x180047698  mov     edx, 32Eh
0x18004769d  mov     r9d, 80041008h
0x1800476a3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800476aa  mov     rcx, [rcx+10h]
0x1800476ae  call    WPP_SF_d
0x1800476b3  mov     eax, 80041008h
0x1800476b8  jmp     loc_180047535
0x1800476bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800476c3  mov     edx, [rsp+88h+var_48]
0x1800476c7  mov     rcx, rax
0x1800476ca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800476d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476d7  cmp     rcx, rdi
0x1800476da  jz      short loc_180047702
0x1800476dc  test    byte ptr [rcx+1Ch], 1
0x1800476e0  jz      short loc_180047702
0x1800476e2  cmp     byte ptr [rcx+19h], 2
0x1800476e6  jb      short loc_180047702
0x1800476e8  mov     edx, 32Fh
0x1800476ed  mov     r9d, [rsp+88h+var_48]
0x1800476f2  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800476f9  mov     rcx, [rcx+10h]
0x1800476fd  call    WPP_SF_d
0x180047702  mov     eax, [rsp+88h+var_48]
0x180047706  jmp     loc_180047535
0x18004770b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047711  mov     edx, [rsp+88h+var_48]
0x180047715  mov     rcx, rax
0x180047718  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047725  cmp     rcx, rdi
0x180047728  jz      short loc_180047750
0x18004772a  test    byte ptr [rcx+1Ch], 1
0x18004772e  jz      short loc_180047750
0x180047730  cmp     byte ptr [rcx+19h], 2
0x180047734  jb      short loc_180047750
0x180047736  mov     edx, 333h
0x18004773b  mov     r9d, [rsp+88h+var_48]
0x180047740  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180047747  mov     rcx, [rcx+10h]
0x18004774b  call    WPP_SF_d
0x180047750  mov     ebx, [rsp+88h+var_48]
0x180047754  jmp     short loc_18004778D
0x180047756  cmp     byte ptr [rcx+19h], 2
0x18004775a  jb      loc_18004751A
0x180047760  mov     edx, 334h
0x180047765  mov     r9d, ebx
0x180047768  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004776f  mov     rcx, [rcx+10h]
0x180047773  call    WPP_SF_d
0x180047778  mov     ebx, [rsp+88h+var_48]
0x18004777c  jmp     loc_18004751A
0x180047781  mov     ebx, 80041006h
0x180047786  jmp     short loc_18004778D
0x180047788  mov     ebx, 8004100Ah
0x18004778d  lea     rcx, [rsp+88h+var_38]; this
0x180047792  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180047797  jmp     loc_180047533
```
