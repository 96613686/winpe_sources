# CWbemNamespace::DeleteClass(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x18009b650`
- end: `0x18009bad5`
- name: `?DeleteClass@CWbemNamespace@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `1157`
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
- `0x18009b650`
- `0x1800a0a40`
- `0x1800a1f30`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18009b682`
- `wbemcomn!GetMemLogObject` at `0x18009b711`
- `wbemcomn!GetMemLogObject` at `0x18009b75f`
- `wbemcomn!GetMemLogObject` at `0x18009b7f7`
- `wbemcomn!GetMemLogObject` at `0x18009b855`
- `wbemcomn!GetMemLogObject` at `0x18009b8ce`
- `wbemcomn!GetMemLogObject` at `0x18009b984`
- `wbemcomn!GetMemLogObject` at `0x18009ba44`
- `wbemcomn!GetMemLogObject` at `0x18009b682`
- `wbemcomn!GetMemLogObject` at `0x18009b711`
- `wbemcomn!GetMemLogObject` at `0x18009b75f`
- `wbemcomn!GetMemLogObject` at `0x18009b7f7`
- `wbemcomn!GetMemLogObject` at `0x18009b855`
- `wbemcomn!GetMemLogObject` at `0x18009b8ce`
- `wbemcomn!GetMemLogObject` at `0x18009b984`
- `wbemcomn!GetMemLogObject` at `0x18009ba44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b692`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b71e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b76c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b807`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b865`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b8db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b991`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ba51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b692`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b71e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b76c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b807`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b865`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b8db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009b991`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009ba51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemNamespace::DeleteClass(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  int v6; // r15d
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  struct IWbemCallResult **v10; // rsi
  CWbemNamespace *v11; // rcx
  CMemoryLog *v12; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  struct IWbemContext *v21; // r13
  CMemoryLog *v22; // rax
  struct _IWmiFinalizer *v23; // r12
  int v24; // edi
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  _DWORD v30[4]; // [rsp+40h] [rbp-48h] BYREF
  struct _IWmiFinalizer *v31; // [rsp+50h] [rbp-38h] BYREF
  struct _IWmiFinalizer *v32; // [rsp+58h] [rbp-30h] BYREF
  struct IWbemContext *v34; // [rsp+A8h] [rbp+20h] BYREF

  v34 = a4;
  v6 = (int)a2;
  if ( (unsigned int)IsCallFromLowIntegrityClient() )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217405);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 716, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749891LL);
    }
    return 2147749891LL;
  }
  v10 = a5;
  if ( a5 && *a5 )
  {
    ((void (__fastcall *)(_QWORD))(*a5)->lpVtbl->Release)(*a5);
    *v10 = 0;
  }
  v30[0] = CWbemNamespace::CheckNs(this);
  if ( v30[0] < 0 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v30[0]);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v30[0];
    }
    v14 = 717;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v30[0]);
    return v30[0];
  }
  v15 = CWbemNamespace::AdjustCtx(v11, &v34);
  v30[0] = v15;
  if ( v15 < 0 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, v30[0]);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v30[0];
    }
    v14 = 718;
    goto LABEL_20;
  }
  try
  {
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SDl(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, v6, a3, *((_DWORD *)this + 76));
    }
    if ( (a3 & 0xFFFEFFEF) != 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          720,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749896LL);
      }
      return 2147749896LL;
    }
    if ( (a3 & 0x10) != 0 && !v10 )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          721,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749896LL);
      }
      return 2147749896LL;
    }
    v32 = 0;
    v21 = v34;
    v30[0] = CWbemNamespace::CreateSyncFinalizer(this, v34, &v32);
    if ( v30[0] < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v30[0]);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 722, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v30[0]);
      }
      return v30[0];
    }
    v23 = v32;
    v31 = v32;
    v30[1] = v10 != 0 ? 33554440 : 16777224;
    try
    {
      v30[0] = CWbemNamespace::_DeleteClassAsync(
                 this,
                 v10 != 0 ? 33554440 : 16777224,
                 v32,
                 0,
                 a2,
                 a3 & 0xFFFFFFEF,
                 v21,
                 0);
    }
    catch ( SafeIntException )
    {
      _InterlockedIncrement(&ExceptionCounter::s_Count);
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          723,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749898LL);
      }
      v30[2] = -2147217398;
      CReleaseMe::release((CReleaseMe *)&v31);
      return 2147749898LL;
    }
    v24 = v30[0];
    if ( v30[0] < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v30[0]);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 724, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v30[0]);
      }
      CReleaseMe::release((CReleaseMe *)&v31);
      return v30[0];
    }
    if ( (a3 & 0x10) == 0 )
    {
      v24 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, __int64, _DWORD *))(*(_QWORD *)v23 + 104LL))(
              v23,
              0,
              0xFFFFFFFFLL,
              v30);
      if ( v24 < 0 )
      {
LABEL_54:
        CReleaseMe::release((CReleaseMe *)&v31);
        return (unsigned int)v24;
      }
      v24 = v30[0];
    }
    if ( v10 )
    {
      v24 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IWbemCallResult **))(*(_QWORD *)v23 + 88LL))(
              v23,
              0,
              &IID_IWbemCallResult,
              v10);
      v30[0] = v24;
    }
    if ( v24 < 0 )
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, v30[0]);
      v24 = v30[0];
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        725,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v24);
      v24 = v30[0];
    }
    goto LABEL_54;
  }
  catch ( CX_MemoryException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 726, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 727, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18009b650  mov     rax, rsp
0x18009b653  mov     [rax+8], rbx
0x18009b657  mov     [rax+18h], rsi
0x18009b65b  mov     [rax+20h], r9
0x18009b65f  mov     [rax+10h], rdx
0x18009b663  push    rdi
0x18009b664  push    r12
0x18009b666  push    r13
0x18009b668  push    r14
0x18009b66a  push    r15
0x18009b66c  sub     rsp, 60h
0x18009b670  mov     r14d, r8d
0x18009b673  mov     r15, rdx
0x18009b676  mov     rdi, rcx
0x18009b679  call    ?IsCallFromLowIntegrityClient@@YAHXZ; IsCallFromLowIntegrityClient(void)
0x18009b67e  test    eax, eax
0x18009b680  jz      short loc_18009B6D9
0x18009b682  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b688  mov     edi, 80041003h
0x18009b68d  mov     edx, edi
0x18009b68f  mov     rcx, rax
0x18009b692  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b698  lea     rbx, WPP_GLOBAL_Control
0x18009b69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b6a6  cmp     rcx, rbx
0x18009b6a9  jz      short loc_18009B6D2
0x18009b6ab  test    byte ptr [rcx+1Ch], 1
0x18009b6af  jz      short loc_18009B6D2
0x18009b6b1  cmp     byte ptr [rcx+19h], 2
0x18009b6b5  jb      short loc_18009B6D2
0x18009b6b7  mov     edx, 2CCh
0x18009b6bc  mov     r9d, 80041003h
0x18009b6c2  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b6c9  mov     rcx, [rcx+10h]
0x18009b6cd  call    WPP_SF_d
0x18009b6d2  mov     eax, edi
0x18009b6d4  jmp     loc_18009BABA
0x18009b6d9  mov     rsi, [rsp+88h+arg_20]
0x18009b6e1  test    rsi, rsi
0x18009b6e4  jz      short loc_18009B701
0x18009b6e6  mov     rcx, [rsi]
0x18009b6e9  test    rcx, rcx
0x18009b6ec  jz      short loc_18009B701
0x18009b6ee  mov     rax, [rcx]
0x18009b6f1  mov     rax, [rax+10h]
0x18009b6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b6fa  mov     qword ptr [rsi], 0
0x18009b701  mov     rcx, rdi; this
0x18009b704  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18009b709  mov     [rsp+88h+var_48], eax
0x18009b70d  test    eax, eax
0x18009b70f  jns     short loc_18009B74A
0x18009b711  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b717  mov     edx, [rsp+88h+var_48]
0x18009b71b  mov     rcx, rax
0x18009b71e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b724  lea     rbx, WPP_GLOBAL_Control
0x18009b72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b732  cmp     rcx, rbx
0x18009b735  jz      short loc_18009B7AB
0x18009b737  test    byte ptr [rcx+1Ch], 1
0x18009b73b  jz      short loc_18009B7AB
0x18009b73d  cmp     byte ptr [rcx+19h], 2
0x18009b741  jb      short loc_18009B7AB
0x18009b743  mov     edx, 2CDh
0x18009b748  jmp     short loc_18009B796
0x18009b74a  lea     rdx, [rsp+88h+arg_18]; struct IWbemContext **
0x18009b752  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x18009b757  mov     [rsp+88h+var_48], eax
0x18009b75b  test    eax, eax
0x18009b75d  jns     short loc_18009B7B4
0x18009b75f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b765  mov     edx, [rsp+88h+var_48]
0x18009b769  mov     rcx, rax
0x18009b76c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b772  lea     rbx, WPP_GLOBAL_Control
0x18009b779  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b780  cmp     rcx, rbx
0x18009b783  jz      short loc_18009B7AB
0x18009b785  test    byte ptr [rcx+1Ch], 1
0x18009b789  jz      short loc_18009B7AB
0x18009b78b  cmp     byte ptr [rcx+19h], 2
0x18009b78f  jb      short loc_18009B7AB
0x18009b791  mov     edx, 2CEh
0x18009b796  mov     r9d, [rsp+88h+var_48]
0x18009b79b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b7a2  mov     rcx, [rcx+10h]
0x18009b7a6  call    WPP_SF_d
0x18009b7ab  mov     eax, [rsp+88h+var_48]
0x18009b7af  jmp     loc_18009BABA
0x18009b7b4  lea     rbx, WPP_GLOBAL_Control
0x18009b7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b7c2  cmp     rcx, rbx
0x18009b7c5  jz      short loc_18009B7EE
0x18009b7c7  test    byte ptr [rcx+1Ch], 1
0x18009b7cb  jz      short loc_18009B7EE
0x18009b7cd  cmp     byte ptr [rcx+19h], 5
0x18009b7d1  jb      short loc_18009B7EE
0x18009b7d3  mov     eax, [rdi+130h]
0x18009b7d9  mov     [rsp+88h+var_60], eax
0x18009b7dd  mov     dword ptr [rsp+88h+Str], r14d
0x18009b7e2  mov     r9, r15
0x18009b7e5  mov     rcx, [rcx+10h]
0x18009b7e9  call    WPP_SF_SDl
0x18009b7ee  test    r14d, 0FFFEFFEFh
0x18009b7f5  jz      short loc_18009B847
0x18009b7f7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b7fd  mov     edi, 80041008h
0x18009b802  mov     edx, edi
0x18009b804  mov     rcx, rax
0x18009b807  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b814  cmp     rcx, rbx
0x18009b817  jz      short loc_18009B840
0x18009b819  test    byte ptr [rcx+1Ch], 1
0x18009b81d  jz      short loc_18009B840
0x18009b81f  cmp     byte ptr [rcx+19h], 2
0x18009b823  jb      short loc_18009B840
0x18009b825  mov     edx, 2D0h
0x18009b82a  mov     r9d, 80041008h
0x18009b830  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b837  mov     rcx, [rcx+10h]
0x18009b83b  call    WPP_SF_d
0x18009b840  mov     eax, edi
0x18009b842  jmp     loc_18009BABA
0x18009b847  mov     r15d, r14d
0x18009b84a  and     r15d, 10h
0x18009b84e  jz      short loc_18009B8A5
0x18009b850  test    rsi, rsi
0x18009b853  jnz     short loc_18009B8A5
0x18009b855  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b85b  mov     edi, 80041008h
0x18009b860  mov     edx, edi
0x18009b862  mov     rcx, rax
0x18009b865  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b872  cmp     rcx, rbx
0x18009b875  jz      short loc_18009B89E
0x18009b877  test    byte ptr [rcx+1Ch], 1
0x18009b87b  jz      short loc_18009B89E
0x18009b87d  cmp     byte ptr [rcx+19h], 2
0x18009b881  jb      short loc_18009B89E
0x18009b883  mov     edx, 2D1h
0x18009b888  mov     r9d, 80041008h
0x18009b88e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b895  mov     rcx, [rcx+10h]
0x18009b899  call    WPP_SF_d
0x18009b89e  mov     eax, edi
0x18009b8a0  jmp     loc_18009BABA
0x18009b8a5  mov     [rsp+88h+var_30], 0
0x18009b8ae  lea     r8, [rsp+88h+var_30]; struct _IWmiFinalizer **
0x18009b8b3  mov     r13, [rsp+88h+arg_18]
0x18009b8bb  mov     rdx, r13; struct IWbemContext *
0x18009b8be  mov     rcx, rdi; this
0x18009b8c1  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x18009b8c6  mov     [rsp+88h+var_48], eax
0x18009b8ca  test    eax, eax
0x18009b8cc  jns     short loc_18009B91C
0x18009b8ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b8d4  mov     edx, [rsp+88h+var_48]
0x18009b8d8  mov     rcx, rax
0x18009b8db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b8e8  cmp     rcx, rbx
0x18009b8eb  jz      short loc_18009B913
0x18009b8ed  test    byte ptr [rcx+1Ch], 1
0x18009b8f1  jz      short loc_18009B913
0x18009b8f3  cmp     byte ptr [rcx+19h], 2
0x18009b8f7  jb      short loc_18009B913
0x18009b8f9  mov     edx, 2D2h
0x18009b8fe  mov     r9d, [rsp+88h+var_48]
0x18009b903  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b90a  mov     rcx, [rcx+10h]
0x18009b90e  call    WPP_SF_d
0x18009b913  mov     eax, [rsp+88h+var_48]
0x18009b917  jmp     loc_18009BABA
0x18009b91c  mov     r12, [rsp+88h+var_30]
0x18009b921  mov     [rsp+88h+var_38], r12
0x18009b926  mov     [rsp+88h+var_44], 8
0x18009b92e  mov     rax, rsi
0x18009b931  neg     rax
0x18009b934  sbb     edx, edx
0x18009b936  and     edx, 1000000h
0x18009b93c  add     edx, 1000008h; unsigned int
0x18009b942  mov     [rsp+88h+var_44], edx
0x18009b946  and     r14d, 0FFFFFFEFh
0x18009b94a  mov     [rsp+88h+var_50], 0; struct IWbemObjectSink *
0x18009b953  mov     [rsp+88h+var_58], r13; struct IWbemContext *
0x18009b958  mov     [rsp+88h+var_60], r14d; int
0x18009b95d  mov     rax, [rsp+88h+arg_8]
0x18009b965  mov     [rsp+88h+Str], rax; Str
0x18009b96a  xor     r9d, r9d; struct _IWmiCoreHandle *
0x18009b96d  mov     r8, r12; struct _IWmiFinalizer *
0x18009b970  mov     rcx, rdi; this
0x18009b973  call    ?_DeleteClassAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_DeleteClassAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x18009b978  mov     [rsp+88h+var_48], eax
0x18009b97c  mov     edi, [rsp+88h+var_48]
0x18009b980  test    edi, edi
0x18009b982  jns     short loc_18009B9DE
0x18009b984  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009b98a  mov     edx, [rsp+88h+var_48]
0x18009b98e  mov     rcx, rax
0x18009b991  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009b997  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b99e  cmp     rcx, rbx
0x18009b9a1  jz      short loc_18009B9C9
0x18009b9a3  test    byte ptr [rcx+1Ch], 1
0x18009b9a7  jz      short loc_18009B9C9
0x18009b9a9  cmp     byte ptr [rcx+19h], 2
0x18009b9ad  jb      short loc_18009B9C9
0x18009b9af  mov     edx, 2D4h
0x18009b9b4  mov     r9d, [rsp+88h+var_48]
0x18009b9b9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009b9c0  mov     rcx, [rcx+10h]
0x18009b9c4  call    WPP_SF_d
0x18009b9c9  mov     ebx, [rsp+88h+var_48]
0x18009b9cd  lea     rcx, [rsp+88h+var_38]; this
0x18009b9d2  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009b9d7  mov     eax, ebx
0x18009b9d9  jmp     loc_18009BABA
0x18009b9de  test    r15d, r15d
0x18009b9e1  jnz     short loc_18009BA19
0x18009b9e3  mov     rax, [r12]
0x18009b9e7  lea     r9, [rsp+88h+var_48]
0x18009b9ec  or      r8d, 0FFFFFFFFh
0x18009b9f0  xor     edx, edx
0x18009b9f2  mov     rcx, r12
0x18009b9f5  mov     rax, [rax+68h]
0x18009b9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b9fe  mov     edi, eax
0x18009ba00  test    eax, eax
0x18009ba02  jns     short loc_18009BA15
0x18009ba04  lea     rcx, [rsp+88h+var_38]; this
0x18009ba09  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009ba0e  mov     eax, edi
0x18009ba10  jmp     loc_18009BABA
0x18009ba15  mov     edi, [rsp+88h+var_48]
0x18009ba19  test    rsi, rsi
0x18009ba1c  jz      short loc_18009BA40
0x18009ba1e  mov     rax, [r12]
0x18009ba22  mov     r9, rsi
0x18009ba25  lea     r8, IID_IWbemCallResult
0x18009ba2c  xor     edx, edx
0x18009ba2e  mov     rcx, r12
0x18009ba31  mov     rax, [rax+58h]
0x18009ba35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba3a  mov     edi, eax
0x18009ba3c  mov     [rsp+88h+var_48], eax
0x18009ba40  test    edi, edi
0x18009ba42  jns     short loc_18009BA5B
0x18009ba44  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18009ba4a  mov     edx, [rsp+88h+var_48]
0x18009ba4e  mov     rcx, rax
0x18009ba51  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18009ba57  mov     edi, [rsp+88h+var_48]
0x18009ba5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ba62  cmp     rcx, rbx
0x18009ba65  jz      short loc_18009BA8F
0x18009ba67  test    byte ptr [rcx+1Ch], 1
0x18009ba6b  jz      short loc_18009BA8F
0x18009ba6d  cmp     byte ptr [rcx+19h], 2
0x18009ba71  jb      short loc_18009BA8F
0x18009ba73  mov     edx, 2D5h
0x18009ba78  mov     r9d, edi
0x18009ba7b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18009ba82  mov     rcx, [rcx+10h]
0x18009ba86  call    WPP_SF_d
0x18009ba8b  mov     edi, [rsp+88h+var_48]
0x18009ba8f  lea     rcx, [rsp+88h+var_38]; this
0x18009ba94  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009ba99  mov     eax, edi
0x18009ba9b  jmp     short loc_18009BABA
0x18009ba9d  lea     rcx, [rsp+88h+var_38]; this
0x18009baa2  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18009baa7  mov     eax, 8004100Ah
0x18009baac  jmp     short loc_18009BABA
0x18009baae  mov     eax, 80041006h
0x18009bab3  jmp     short loc_18009BABA
0x18009bab5  mov     eax, 8004100Ah
0x18009baba  lea     r11, [rsp+88h+var_28]
0x18009babf  mov     rbx, [r11+30h]
0x18009bac3  mov     rsi, [r11+40h]
0x18009bac7  mov     rsp, r11
0x18009baca  pop     r15
0x18009bacc  pop     r14
0x18009bace  pop     r13
0x18009bad0  pop     r12
0x18009bad2  pop     rdi
0x18009bad3  retn
```
