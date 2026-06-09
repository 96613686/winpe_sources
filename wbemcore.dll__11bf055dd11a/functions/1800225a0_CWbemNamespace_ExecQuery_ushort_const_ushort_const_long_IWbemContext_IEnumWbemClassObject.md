# CWbemNamespace::ExecQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1800225a0`
- end: `0x180022a7b`
- name: `?ExecQuery@CWbemNamespace@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `1243`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ac94`
- `0x18000b140`
- `0x180020870`
- `0x180020c90`
- `0x1800225a0`
- `0x180022a90`
- `0x18003cfe0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800227cb`
- `wbemcomn!GetMemLogObject` at `0x180022801`
- `wbemcomn!GetMemLogObject` at `0x180022893`
- `wbemcomn!GetMemLogObject` at `0x1800228f6`
- `wbemcomn!GetMemLogObject` at `0x18002294e`
- `wbemcomn!GetMemLogObject` at `0x18002299c`
- `wbemcomn!GetMemLogObject` at `0x180022a26`
- `wbemcomn!GetMemLogObject` at `0x1800227cb`
- `wbemcomn!GetMemLogObject` at `0x180022801`
- `wbemcomn!GetMemLogObject` at `0x180022893`
- `wbemcomn!GetMemLogObject` at `0x1800228f6`
- `wbemcomn!GetMemLogObject` at `0x18002294e`
- `wbemcomn!GetMemLogObject` at `0x18002299c`
- `wbemcomn!GetMemLogObject` at `0x180022a26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800227d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002280f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800228a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022904`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002295b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800229a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022a33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800227d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002280f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800228a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022904`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002295b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800229a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022a33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::ExecQuery(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IEnumWbemClassObject **a6)
{
  int v8; // r14d
  int v10; // eax
  int v11; // r8d
  struct IEnumWbemClassObject **v12; // r15
  struct IWbemContext *v13; // r13
  struct _IWmiFinalizer *v14; // rdi
  unsigned int v15; // edx
  int v16; // eax
  int v17; // ebx
  struct _IWmiFinalizer *v18; // rbx
  struct _IWmiFinalizer *v19; // rcx
  unsigned int v20; // ebx
  __int64 result; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CClientCnt *v24; // rcx
  CMemoryLog *v25; // rax
  CClientCnt *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  unsigned int Async; // [rsp+50h] [rbp-58h] BYREF
  int v37; // [rsp+54h] [rbp-54h]
  int v38; // [rsp+58h] [rbp-50h]
  struct _IWmiFinalizer *v39; // [rsp+60h] [rbp-48h] BYREF
  struct _IWmiFinalizer *v40; // [rsp+68h] [rbp-40h] BYREF
  struct _IWmiFinalizer *v41; // [rsp+70h] [rbp-38h] BYREF

  v8 = (int)a2;
  if ( g_bDontAllowNewConnections || *((_DWORD *)this + 7) )
  {
    Async = -2147217357;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217357);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return Async;
    }
    v27 = 830;
    goto LABEL_63;
  }
  v10 = CWbemNamespace::AdjustCtx(this, &a5);
  Async = v10;
  if ( v10 < 0 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, Async);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return Async;
    }
    v27 = 831;
LABEL_63:
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, Async);
    return Async;
  }
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
  {
    v12 = a6;
  }
  else
  {
    v12 = a6;
    WPP_SF_SSql(*((_QWORD *)WPP_GLOBAL_Control + 2), 832, v11, v8, (__int64)a3, (char)a6, *((_DWORD *)this + 76));
  }
  if ( (a4 & 0xFFEDFCCD) != 0 )
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
    v28 = 833;
    goto LABEL_48;
  }
  if ( !v12 )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217400);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v28 = 834;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v24 + 2), v28, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  try
  {
    *v12 = 0;
    v41 = 0;
    v13 = a5;
    Async = CWbemNamespace::CreateSyncFinalizer(this, a5, &v41);
    if ( (Async & 0x80000000) != 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, Async);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 835, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, Async);
      }
      return Async;
    }
    v14 = v41;
    v39 = v41;
    v37 = 10;
    v15 = 16777226;
    if ( (a4 & 0x10) != 0 )
      v15 = 33554442;
    v37 = v15;
    try
    {
      Async = CWbemNamespace::_ExecQueryAsync(this, v15, v41, 0, a2, a3, a4 & 0xFFFFFFCF, v13, 0);
    }
    catch ( SafeIntException )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          836,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749898LL);
      }
      v38 = -2147217398;
      CReleaseMe::release((CReleaseMe *)&v39);
      return 2147749898LL;
    }
    v16 = Async;
    if ( (Async & 0x80000000) != 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, Async);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 837, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, Async);
      }
      CReleaseMe::release((CReleaseMe *)&v39);
      return Async;
    }
    if ( (a4 & 0x10) == 0 )
    {
      (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, unsigned int *))(*(_QWORD *)v14 + 104LL))(
        v14,
        0,
        0xFFFFFFFFLL,
        &Async);
      v16 = Async;
    }
    if ( v16 < 0 )
      goto LABEL_27;
    v40 = 0;
    v17 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct _IWmiFinalizer **))(*(_QWORD *)v14 + 88LL))(
            v14,
            a4,
            &IID_IEnumWbemClassObject,
            &v40);
    if ( v17 < 0 )
    {
      if ( v14 )
        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v14 + 16LL))(v14);
      v39 = 0;
      return (unsigned int)v17;
    }
    v18 = v40;
    v41 = v40;
    v19 = v40;
    *v12 = (struct IEnumWbemClassObject *)v40;
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v19 + 8LL))(v19);
    if ( v18 )
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v18 + 16LL))(v18);
    v41 = 0;
    v20 = Async;
    if ( (Async & 0x80000000) != 0 )
    {
LABEL_27:
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, Async);
      v20 = Async;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 838, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v20);
      v20 = Async;
    }
    if ( v14 )
      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v14 + 16LL))(v14);
    v39 = 0;
    result = v20;
  }
  catch ( CX_MemoryException )
  {
    v34 = GetMemLogObject();
    CMemoryLog::Write(v34, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 839, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 840, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800225a0  mov     rax, rsp
0x1800225a3  mov     [rax+8], rbx
0x1800225a7  mov     [rax+20h], rsi
0x1800225ab  mov     [rax+18h], r8
0x1800225af  mov     [rax+10h], rdx
0x1800225b3  push    rdi
0x1800225b4  push    r12
0x1800225b6  push    r13
0x1800225b8  push    r14
0x1800225ba  push    r15
0x1800225bc  sub     rsp, 80h
0x1800225c3  mov     esi, r9d
0x1800225c6  mov     rdi, r8
0x1800225c9  mov     r14, rdx
0x1800225cc  mov     rbx, rcx
0x1800225cf  cmp     cs:?g_bDontAllowNewConnections@@3HA, 0; int g_bDontAllowNewConnections
0x1800225d6  jnz     loc_180022A1E
0x1800225dc  cmp     dword ptr [rcx+1Ch], 0
0x1800225e0  jnz     loc_180022A1E
0x1800225e6  xor     r13d, r13d
0x1800225e9  mov     [rax-58h], r13d
0x1800225ed  lea     rdx, [rax+28h]; struct IWbemContext **
0x1800225f1  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x1800225f6  mov     [rsp+0A8h+var_58], eax
0x1800225fa  test    eax, eax
0x1800225fc  js      loc_180022893
0x180022602  lea     r12, WPP_GLOBAL_Control
0x180022609  mov     rcx, cs:WPP_GLOBAL_Control
0x180022610  cmp     rcx, r12
0x180022613  jz      short loc_18002261F
0x180022615  test    byte ptr [rcx+1Ch], 1
0x180022619  jnz     loc_18002282C
0x18002261f  mov     r15, [rsp+0A8h+arg_28]
0x180022627  test    esi, 0FFEDFCCDh
0x18002262d  jnz     loc_180022801
0x180022633  test    r15, r15
0x180022636  jz      loc_1800228F6
0x18002263c  mov     [r15], r13
0x18002263f  mov     [rsp+0A8h+var_38], r13
0x180022644  lea     r8, [rsp+0A8h+var_38]; struct _IWmiFinalizer **
0x180022649  mov     r13, [rsp+0A8h+arg_20]
0x180022651  mov     rdx, r13; struct IWbemContext *
0x180022654  mov     rcx, rbx; this
0x180022657  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x18002265c  mov     [rsp+0A8h+var_58], eax
0x180022660  test    eax, eax
0x180022662  js      loc_18002294E
0x180022668  mov     rdi, [rsp+0A8h+var_38]
0x18002266d  mov     [rsp+0A8h+var_48], rdi
0x180022672  mov     [rsp+0A8h+var_54], 0Ah
0x18002267a  mov     r14d, esi
0x18002267d  and     r14d, 10h
0x180022681  mov     edx, 100000Ah
0x180022686  mov     eax, 200000Ah
0x18002268b  cmovnz  edx, eax; unsigned int
0x18002268e  mov     [rsp+0A8h+var_54], edx
0x180022692  mov     eax, esi
0x180022694  and     eax, 0FFFFFFCFh
0x180022697  mov     [rsp+0A8h+var_68], 0; struct IWbemObjectSink *
0x1800226a0  mov     [rsp+0A8h+var_70], r13; struct IWbemContext *
0x1800226a5  mov     [rsp+0A8h+var_78], eax; int
0x1800226a9  mov     rax, [rsp+0A8h+arg_10]
0x1800226b1  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x1800226b6  mov     rax, [rsp+0A8h+arg_8]
0x1800226be  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x1800226c3  xor     r9d, r9d; struct _IWmiCoreHandle *
0x1800226c6  mov     r8, rdi; struct _IWmiFinalizer *
0x1800226c9  mov     rcx, rbx; this
0x1800226cc  call    ?_ExecQueryAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_ExecQueryAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x1800226d1  mov     [rsp+0A8h+var_58], eax
0x1800226d5  mov     eax, [rsp+0A8h+var_58]
0x1800226d9  test    eax, eax
0x1800226db  js      loc_18002299C
0x1800226e1  test    r14d, r14d
0x1800226e4  jnz     short loc_180022706
0x1800226e6  mov     rax, [rdi]
0x1800226e9  lea     r9, [rsp+0A8h+var_58]
0x1800226ee  xor     edx, edx
0x1800226f0  mov     r8d, 0FFFFFFFFh
0x1800226f6  mov     rcx, rdi
0x1800226f9  mov     rax, [rax+68h]
0x1800226fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022702  mov     eax, [rsp+0A8h+var_58]
0x180022706  xor     r14d, r14d
0x180022709  test    eax, eax
0x18002270b  js      loc_1800227CB
0x180022711  mov     [rsp+0A8h+var_40], r14
0x180022716  mov     rax, [rdi]
0x180022719  lea     r9, [rsp+0A8h+var_40]
0x18002271e  lea     r8, IID_IEnumWbemClassObject
0x180022725  mov     edx, esi
0x180022727  mov     rcx, rdi
0x18002272a  mov     rax, [rax+58h]
0x18002272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022733  mov     ebx, eax
0x180022735  test    eax, eax
0x180022737  js      loc_1800227E4
0x18002273d  mov     rbx, [rsp+0A8h+var_40]
0x180022742  mov     [rsp+0A8h+var_38], rbx
0x180022747  mov     rcx, [rsp+0A8h+var_40]
0x18002274c  mov     [r15], rcx
0x18002274f  mov     rax, [rcx]
0x180022752  mov     rax, [rax+8]
0x180022756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275b  nop
0x18002275c  test    rbx, rbx
0x18002275f  jz      short loc_180022770
0x180022761  mov     rax, [rbx]
0x180022764  mov     rcx, rbx
0x180022767  mov     rax, [rax+10h]
0x18002276b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022770  mov     [rsp+0A8h+var_38], r14
0x180022775  mov     ebx, [rsp+0A8h+var_58]
0x180022779  test    ebx, ebx
0x18002277b  js      short loc_1800227CB
0x18002277d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022784  cmp     rcx, r12
0x180022787  jz      short loc_180022793
0x180022789  test    byte ptr [rcx+1Ch], 1
0x18002278d  jnz     loc_180022868
0x180022793  test    rdi, rdi
0x180022796  jz      short loc_1800227A7
0x180022798  mov     rcx, [rdi]
0x18002279b  mov     rax, [rcx+10h]
0x18002279f  mov     rcx, rdi
0x1800227a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a7  mov     [rsp+0A8h+var_48], r14
0x1800227ac  mov     eax, ebx
0x1800227ae  lea     r11, [rsp+0A8h+var_28]
0x1800227b6  mov     rbx, [r11+30h]
0x1800227ba  mov     rsi, [r11+48h]
0x1800227be  mov     rsp, r11
0x1800227c1  pop     r15
0x1800227c3  pop     r14
0x1800227c5  pop     r13
0x1800227c7  pop     r12
0x1800227c9  pop     rdi
0x1800227ca  retn
0x1800227cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800227d1  mov     edx, [rsp+0A8h+var_58]
0x1800227d5  mov     rcx, rax
0x1800227d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800227de  mov     ebx, [rsp+0A8h+var_58]
0x1800227e2  jmp     short loc_18002277D
0x1800227e4  test    rdi, rdi
0x1800227e7  jz      short loc_1800227F8
0x1800227e9  mov     rdx, [rdi]
0x1800227ec  mov     rcx, rdi
0x1800227ef  mov     rax, [rdx+10h]
0x1800227f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227f8  mov     [rsp+0A8h+var_48], r14
0x1800227fd  mov     eax, ebx
0x1800227ff  jmp     short loc_1800227AE
0x180022801  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022807  mov     edx, 80041008h
0x18002280c  mov     rcx, rax
0x18002280f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022815  mov     rcx, cs:WPP_GLOBAL_Control
0x18002281c  cmp     rcx, r12
0x18002281f  jnz     loc_1800228DB
0x180022825  mov     eax, 80041008h
0x18002282a  jmp     short loc_1800227AE
0x18002282c  cmp     byte ptr [rcx+19h], 5
0x180022830  jb      loc_18002261F
0x180022836  mov     edx, 340h
0x18002283b  mov     eax, [rbx+130h]
0x180022841  mov     [rsp+0A8h+var_78], eax
0x180022845  mov     r15, [rsp+0A8h+arg_28]
0x18002284d  mov     [rsp+0A8h+var_80], r15
0x180022852  mov     [rsp+0A8h+var_88], rdi
0x180022857  mov     r9, r14
0x18002285a  mov     rcx, [rcx+10h]
0x18002285e  call    WPP_SF_SSql
0x180022863  jmp     loc_180022627
0x180022868  cmp     byte ptr [rcx+19h], 2
0x18002286c  jb      loc_180022793
0x180022872  mov     edx, 346h
0x180022877  mov     r9d, ebx
0x18002287a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180022881  mov     rcx, [rcx+10h]
0x180022885  call    WPP_SF_d
0x18002288a  mov     ebx, [rsp+0A8h+var_58]
0x18002288e  jmp     loc_180022793
0x180022893  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022899  mov     edx, [rsp+0A8h+var_58]
0x18002289d  mov     rcx, rax
0x1800228a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800228a6  lea     r12, WPP_GLOBAL_Control
0x1800228ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228b4  cmp     rcx, r12
0x1800228b7  jz      loc_180022A72
0x1800228bd  test    byte ptr [rcx+1Ch], 1
0x1800228c1  jz      loc_180022A72
0x1800228c7  cmp     byte ptr [rcx+19h], 2
0x1800228cb  jb      loc_180022A72
0x1800228d1  mov     edx, 33Fh
0x1800228d6  jmp     loc_180022A5D
0x1800228db  test    byte ptr [rcx+1Ch], 1
0x1800228df  jz      loc_180022825
0x1800228e5  cmp     byte ptr [rcx+19h], 2
0x1800228e9  jb      loc_180022825
0x1800228ef  mov     edx, 341h
0x1800228f4  jmp     short loc_180022933
0x1800228f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800228fc  mov     edx, 80041008h
0x180022901  mov     rcx, rax
0x180022904  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002290a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022911  cmp     rcx, r12
0x180022914  jz      loc_180022825
0x18002291a  test    byte ptr [rcx+1Ch], 1
0x18002291e  jz      loc_180022825
0x180022924  cmp     byte ptr [rcx+19h], 2
0x180022928  jb      loc_180022825
0x18002292e  mov     edx, 342h
0x180022933  mov     r9d, 80041008h
0x180022939  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180022940  mov     rcx, [rcx+10h]
0x180022944  call    WPP_SF_d
0x180022949  jmp     loc_180022825
0x18002294e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022954  mov     edx, [rsp+0A8h+var_58]
0x180022958  mov     rcx, rax
0x18002295b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022961  mov     rcx, cs:WPP_GLOBAL_Control
0x180022968  cmp     rcx, r12
0x18002296b  jz      short loc_180022993
0x18002296d  test    byte ptr [rcx+1Ch], 1
0x180022971  jz      short loc_180022993
0x180022973  cmp     byte ptr [rcx+19h], 2
0x180022977  jb      short loc_180022993
0x180022979  mov     edx, 343h
0x18002297e  mov     r9d, [rsp+0A8h+var_58]
0x180022983  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002298a  mov     rcx, [rcx+10h]
0x18002298e  call    WPP_SF_d
0x180022993  mov     eax, [rsp+0A8h+var_58]
0x180022997  jmp     loc_1800227AE
0x18002299c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800229a2  mov     edx, [rsp+0A8h+var_58]
0x1800229a6  mov     rcx, rax
0x1800229a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800229af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229b6  cmp     rcx, r12
0x1800229b9  jz      short loc_1800229E1
0x1800229bb  test    byte ptr [rcx+1Ch], 1
0x1800229bf  jz      short loc_1800229E1
0x1800229c1  cmp     byte ptr [rcx+19h], 2
0x1800229c5  jb      short loc_1800229E1
0x1800229c7  mov     edx, 345h
0x1800229cc  mov     r9d, [rsp+0A8h+var_58]
0x1800229d1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800229d8  mov     rcx, [rcx+10h]
0x1800229dc  call    WPP_SF_d
0x1800229e1  mov     ebx, [rsp+0A8h+var_58]
0x1800229e5  lea     rcx, [rsp+0A8h+var_48]; this
0x1800229ea  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800229ef  mov     eax, ebx
0x1800229f1  jmp     loc_1800227AE
0x1800229f6  lea     rcx, [rsp+0A8h+var_48]; this
0x1800229fb  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180022a00  mov     eax, 8004100Ah
0x180022a05  jmp     loc_1800227AE
0x180022a0a  mov     eax, 80041006h
0x180022a0f  jmp     loc_1800227AE
0x180022a14  mov     eax, 8004100Ah
0x180022a19  jmp     loc_1800227AE
0x180022a1e  mov     [rsp+0A8h+var_58], 80041033h
0x180022a26  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022a2c  mov     edx, [rsp+0A8h+var_58]
0x180022a30  mov     rcx, rax
0x180022a33  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022a39  lea     r12, WPP_GLOBAL_Control
0x180022a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a47  cmp     rcx, r12
0x180022a4a  jz      short loc_180022A72
0x180022a4c  test    byte ptr [rcx+1Ch], 1
0x180022a50  jz      short loc_180022A72
0x180022a52  cmp     byte ptr [rcx+19h], 2
0x180022a56  jb      short loc_180022A72
0x180022a58  mov     edx, 33Eh
0x180022a5d  mov     r9d, [rsp+0A8h+var_58]
0x180022a62  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180022a69  mov     rcx, [rcx+10h]
0x180022a6d  call    WPP_SF_d
0x180022a72  mov     eax, [rsp+0A8h+var_58]
0x180022a76  jmp     loc_1800227AE
```
