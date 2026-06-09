# CWbemNamespace::ExecNotificationQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x180066730`
- end: `0x180066ce2`
- name: `?ExecNotificationQuery@CWbemNamespace@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `1458`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000b140`
- `0x18000b274`
- `0x180020870`
- `0x180020c90`
- `0x180047ed0`
- `0x180066730`
- `0x180066e10`
- `0x1800a1fc8`
- `0x1800da010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800667a5`
- `wbemcomn!GetMemLogObject` at `0x18006680a`
- `wbemcomn!GetMemLogObject` at `0x1800668a5`
- `wbemcomn!GetMemLogObject` at `0x180066908`
- `wbemcomn!GetMemLogObject` at `0x180066964`
- `wbemcomn!GetMemLogObject` at `0x1800669c3`
- `wbemcomn!GetMemLogObject` at `0x180066a42`
- `wbemcomn!GetMemLogObject` at `0x180066afc`
- `wbemcomn!GetMemLogObject` at `0x180066b96`
- `wbemcomn!GetMemLogObject` at `0x180066c4e`
- `wbemcomn!GetMemLogObject` at `0x1800667a5`
- `wbemcomn!GetMemLogObject` at `0x18006680a`
- `wbemcomn!GetMemLogObject` at `0x1800668a5`
- `wbemcomn!GetMemLogObject` at `0x180066908`
- `wbemcomn!GetMemLogObject` at `0x180066964`
- `wbemcomn!GetMemLogObject` at `0x1800669c3`
- `wbemcomn!GetMemLogObject` at `0x180066a42`
- `wbemcomn!GetMemLogObject` at `0x180066afc`
- `wbemcomn!GetMemLogObject` at `0x180066b96`
- `wbemcomn!GetMemLogObject` at `0x180066c4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800667b2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066817`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800668b5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066918`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066974`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800669d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066a4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066b09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066ba3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066c5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800667b2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066817`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800668b5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066918`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066974`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800669d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066a4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066b09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066ba3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066c5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::ExecNotificationQuery(
        CWbemNamespace *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IEnumWbemClassObject **a6)
{
  int v8; // r13d
  CMemoryLog *v10; // rax
  __int64 result; // rax
  int v12; // r8d
  CMemoryLog *v13; // rax
  struct IEnumWbemClassObject **v14; // r15
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *MemLogObject; // rax
  struct IWbemContext *v19; // r13
  CMemoryLog *v20; // rax
  struct _IWmiFinalizer *v21; // rdi
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  struct IEnumWbemClassObject *v24; // r14
  struct IEnumWbemClassObject *v25; // rcx
  unsigned int v26; // r14d
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  int v30; // [rsp+50h] [rbp-48h]
  int v31; // [rsp+50h] [rbp-48h]
  int v32; // [rsp+50h] [rbp-48h]
  int Async; // [rsp+50h] [rbp-48h]
  unsigned int v34; // [rsp+50h] [rbp-48h]
  struct IEnumWbemClassObject *v35; // [rsp+58h] [rbp-40h] BYREF
  struct _IWmiFinalizer *v36; // [rsp+60h] [rbp-38h] BYREF
  struct IEnumWbemClassObject *v37; // [rsp+68h] [rbp-30h]

  v8 = (int)a2;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      265,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a2,
      (__int64)a3);
  }
  try
  {
    v30 = CWbemNamespace::CheckNs(this);
    if ( v30 >= 0 )
    {
      v31 = CWbemNamespace::AdjustCtx(this, &a5);
      if ( v31 >= 0 )
      {
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          v14 = a6;
        }
        else
        {
          v14 = a6;
          WPP_SF_SSDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, v12, v8, (__int64)a3, a4, (char)a6);
        }
        if ( v14 )
        {
          *v14 = 0;
          if ( (a4 & 0x10) != 0 )
          {
            if ( (a4 & 0x20) != 0 )
            {
              if ( (a4 & 0xFFFDFFCF) != 0 )
              {
                MemLogObject = GetMemLogObject();
                CMemoryLog::Write(MemLogObject, -2147217400);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    272,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    2147749896LL);
                }
                result = 2147749896LL;
              }
              else
              {
                v36 = 0;
                v19 = a5;
                v32 = CWbemNamespace::CreateSyncFinalizer(this, a5, &v36);
                if ( v32 >= 0 )
                {
                  v21 = v36;
                  Async = CWbemNamespace::_ExecNotificationQueryAsync(
                            this,
                            0x2000019u,
                            v36,
                            0,
                            a2,
                            a3,
                            a4 & 0xFFFFFFCF,
                            v19,
                            0);
                  if ( Async >= 0 )
                  {
                    v35 = 0;
                    v34 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, GUID *, struct IEnumWbemClassObject **))(*(_QWORD *)v21 + 88LL))(
                            v21,
                            a4,
                            &IID_IEnumWbemClassObject,
                            &v35);
                    if ( (v34 & 0x80000000) == 0 )
                    {
                      v24 = v35;
                      v37 = v35;
                      v25 = v35;
                      *v14 = v35;
                      ((void (__fastcall *)(struct IEnumWbemClassObject *))v25->lpVtbl->AddRef)(v25);
                      if ( v24 )
                        ((void (__fastcall *)(struct IEnumWbemClassObject *))v24->lpVtbl->Release)(v24);
                      v37 = 0;
                      v26 = v34;
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          276,
                          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                          v34);
                        v26 = v34;
                      }
                      if ( v21 )
                        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v21 + 16LL))(v21);
                      v36 = 0;
                      result = v26;
                    }
                    else
                    {
                      v23 = GetMemLogObject();
                      CMemoryLog::Write(v23, v34);
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          275,
                          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                          v34);
                      }
                      if ( v21 )
                        (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v21 + 16LL))(v21);
                      v36 = 0;
                      result = v34;
                    }
                  }
                  else
                  {
                    v22 = GetMemLogObject();
                    CMemoryLog::Write(v22, Async);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        274,
                        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                        (unsigned int)Async);
                    }
                    if ( v21 )
                      (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v21 + 16LL))(v21);
                    v36 = 0;
                    result = (unsigned int)Async;
                  }
                }
                else
                {
                  v20 = GetMemLogObject();
                  CMemoryLog::Write(v20, v32);
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      273,
                      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                      (unsigned int)v32);
                  }
                  result = (unsigned int)v32;
                }
              }
            }
            else
            {
              v17 = GetMemLogObject();
              CMemoryLog::Write(v17, -2147217400);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  271,
                  WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                  2147749896LL);
              }
              result = 2147749896LL;
            }
          }
          else
          {
            v16 = GetMemLogObject();
            CMemoryLog::Write(v16, -2147217400);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                270,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                2147749896LL);
            }
            result = 2147749896LL;
          }
        }
        else
        {
          v15 = GetMemLogObject();
          CMemoryLog::Write(v15, -2147217400);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              269,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749896LL);
          }
          result = 2147749896LL;
        }
      }
      else
      {
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, v31);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            267,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v31);
        }
        result = (unsigned int)v31;
      }
    }
    else
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, v30);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          266,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v30);
      }
      result = (unsigned int)v30;
    }
  }
  catch ( CX_MemoryException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( SafeIntException )
  {
    _InterlockedIncrement(&ExceptionCounter::s_Count);
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x180066730  mov     rax, rsp
0x180066733  mov     [rax+8], rbx
0x180066737  mov     [rax+18h], r8
0x18006673b  mov     [rax+10h], rdx
0x18006673f  push    rdi
0x180066740  push    r12
0x180066742  push    r13
0x180066744  push    r14
0x180066746  push    r15
0x180066748  sub     rsp, 70h
0x18006674c  mov     r14d, r9d
0x18006674f  mov     rdi, r8
0x180066752  mov     r13, rdx
0x180066755  mov     r12, rcx
0x180066758  lea     r15, WPP_GLOBAL_Control
0x18006675f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066766  mov     bl, 1
0x180066768  cmp     rcx, r15
0x18006676b  jz      short loc_180066795
0x18006676d  test    [rcx+1Ch], bl
0x180066770  jz      short loc_180066795
0x180066772  cmp     byte ptr [rcx+19h], 5
0x180066776  jb      short loc_180066795
0x180066778  mov     edx, 109h
0x18006677d  mov     [rax-78h], r8
0x180066781  mov     r9, r13
0x180066784  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18006678b  mov     rcx, [rcx+10h]
0x18006678f  call    WPP_SF_SS
0x180066794  nop
0x180066795  mov     rcx, r12; this
0x180066798  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x18006679d  mov     [rsp+98h+var_48], eax
0x1800667a1  test    eax, eax
0x1800667a3  jns     short loc_1800667F2
0x1800667a5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800667ab  mov     edx, [rsp+98h+var_48]
0x1800667af  mov     rcx, rax
0x1800667b2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800667b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667bf  cmp     rcx, r15
0x1800667c2  jz      short loc_1800667E9
0x1800667c4  test    [rcx+1Ch], bl
0x1800667c7  jz      short loc_1800667E9
0x1800667c9  cmp     byte ptr [rcx+19h], 2
0x1800667cd  jb      short loc_1800667E9
0x1800667cf  mov     edx, 10Ah
0x1800667d4  mov     r9d, [rsp+98h+var_48]
0x1800667d9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800667e0  mov     rcx, [rcx+10h]
0x1800667e4  call    WPP_SF_d
0x1800667e9  mov     eax, [rsp+98h+var_48]
0x1800667ed  jmp     loc_180066CCB
0x1800667f2  lea     rdx, [rsp+98h+arg_20]; struct IWbemContext **
0x1800667fa  mov     rcx, r12; this
0x1800667fd  call    ?AdjustCtx@CWbemNamespace@@QEAAJAEAPEAUIWbemContext@@J@Z; CWbemNamespace::AdjustCtx(IWbemContext * &,long)
0x180066802  mov     [rsp+98h+var_48], eax
0x180066806  test    eax, eax
0x180066808  jns     short loc_180066857
0x18006680a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066810  mov     edx, [rsp+98h+var_48]
0x180066814  mov     rcx, rax
0x180066817  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006681d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066824  cmp     rcx, r15
0x180066827  jz      short loc_18006684E
0x180066829  test    [rcx+1Ch], bl
0x18006682c  jz      short loc_18006684E
0x18006682e  cmp     byte ptr [rcx+19h], 2
0x180066832  jb      short loc_18006684E
0x180066834  mov     edx, 10Bh
0x180066839  mov     r9d, [rsp+98h+var_48]
0x18006683e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066845  mov     rcx, [rcx+10h]
0x180066849  call    WPP_SF_d
0x18006684e  mov     eax, [rsp+98h+var_48]
0x180066852  jmp     loc_180066CCB
0x180066857  mov     rcx, cs:WPP_GLOBAL_Control
0x18006685e  cmp     rcx, r15
0x180066861  jz      short loc_180066898
0x180066863  test    [rcx+1Ch], bl
0x180066866  jz      short loc_180066898
0x180066868  cmp     byte ptr [rcx+19h], 5
0x18006686c  jb      short loc_180066898
0x18006686e  mov     edx, 10Ch
0x180066873  mov     r15, [rsp+98h+arg_28]
0x18006687b  mov     qword ptr [rsp+98h+var_68], r15
0x180066880  mov     dword ptr [rsp+98h+var_70], r14d
0x180066885  mov     [rsp+98h+var_78], rdi
0x18006688a  mov     r9, r13
0x18006688d  mov     rcx, [rcx+10h]
0x180066891  call    WPP_SF_SSDq
0x180066896  jmp     short loc_1800668A0
0x180066898  mov     r15, [rsp+98h+arg_28]
0x1800668a0  test    r15, r15
0x1800668a3  jnz     short loc_1800668FB
0x1800668a5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800668ab  mov     edi, 80041008h
0x1800668b0  mov     edx, edi
0x1800668b2  mov     rcx, rax
0x1800668b5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800668bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668c2  lea     rax, WPP_GLOBAL_Control
0x1800668c9  cmp     rcx, rax
0x1800668cc  jz      short loc_1800668F4
0x1800668ce  test    [rcx+1Ch], bl
0x1800668d1  jz      short loc_1800668F4
0x1800668d3  cmp     byte ptr [rcx+19h], 2
0x1800668d7  jb      short loc_1800668F4
0x1800668d9  mov     edx, 10Dh
0x1800668de  mov     r9d, 80041008h
0x1800668e4  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800668eb  mov     rcx, [rcx+10h]
0x1800668ef  call    WPP_SF_d
0x1800668f4  mov     eax, edi
0x1800668f6  jmp     loc_180066CCB
0x1800668fb  mov     qword ptr [r15], 0
0x180066902  test    r14b, 10h
0x180066906  jnz     short loc_18006695E
0x180066908  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006690e  mov     edi, 80041008h
0x180066913  mov     edx, edi
0x180066915  mov     rcx, rax
0x180066918  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006691e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066925  lea     rax, WPP_GLOBAL_Control
0x18006692c  cmp     rcx, rax
0x18006692f  jz      short loc_180066957
0x180066931  test    [rcx+1Ch], bl
0x180066934  jz      short loc_180066957
0x180066936  cmp     byte ptr [rcx+19h], 2
0x18006693a  jb      short loc_180066957
0x18006693c  mov     edx, 10Eh
0x180066941  mov     r9d, 80041008h
0x180066947  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18006694e  mov     rcx, [rcx+10h]
0x180066952  call    WPP_SF_d
0x180066957  mov     eax, edi
0x180066959  jmp     loc_180066CCB
0x18006695e  test    r14b, 20h
0x180066962  jnz     short loc_1800669BA
0x180066964  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006696a  mov     edi, 80041008h
0x18006696f  mov     edx, edi
0x180066971  mov     rcx, rax
0x180066974  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006697a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066981  lea     rax, WPP_GLOBAL_Control
0x180066988  cmp     rcx, rax
0x18006698b  jz      short loc_1800669B3
0x18006698d  test    [rcx+1Ch], bl
0x180066990  jz      short loc_1800669B3
0x180066992  cmp     byte ptr [rcx+19h], 2
0x180066996  jb      short loc_1800669B3
0x180066998  mov     edx, 10Fh
0x18006699d  mov     r9d, 80041008h
0x1800669a3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800669aa  mov     rcx, [rcx+10h]
0x1800669ae  call    WPP_SF_d
0x1800669b3  mov     eax, edi
0x1800669b5  jmp     loc_180066CCB
0x1800669ba  test    r14d, 0FFFDFFCFh
0x1800669c1  jz      short loc_180066A19
0x1800669c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800669c9  mov     edi, 80041008h
0x1800669ce  mov     edx, edi
0x1800669d0  mov     rcx, rax
0x1800669d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800669d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669e0  lea     rax, WPP_GLOBAL_Control
0x1800669e7  cmp     rcx, rax
0x1800669ea  jz      short loc_180066A12
0x1800669ec  test    [rcx+1Ch], bl
0x1800669ef  jz      short loc_180066A12
0x1800669f1  cmp     byte ptr [rcx+19h], 2
0x1800669f5  jb      short loc_180066A12
0x1800669f7  mov     edx, 110h
0x1800669fc  mov     r9d, 80041008h
0x180066a02  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066a09  mov     rcx, [rcx+10h]
0x180066a0d  call    WPP_SF_d
0x180066a12  mov     eax, edi
0x180066a14  jmp     loc_180066CCB
0x180066a19  mov     [rsp+98h+var_38], 0
0x180066a22  lea     r8, [rsp+98h+var_38]; struct _IWmiFinalizer **
0x180066a27  mov     r13, [rsp+98h+arg_20]
0x180066a2f  mov     rdx, r13; struct IWbemContext *
0x180066a32  mov     rcx, r12; this
0x180066a35  call    ?CreateSyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAPEAU_IWmiFinalizer@@@Z; CWbemNamespace::CreateSyncFinalizer(IWbemContext *,_IWmiFinalizer * *)
0x180066a3a  mov     [rsp+98h+var_48], eax
0x180066a3e  test    eax, eax
0x180066a40  jns     short loc_180066A96
0x180066a42  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066a48  mov     edx, [rsp+98h+var_48]
0x180066a4c  mov     rcx, rax
0x180066a4f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a5c  lea     rax, WPP_GLOBAL_Control
0x180066a63  cmp     rcx, rax
0x180066a66  jz      short loc_180066A8D
0x180066a68  test    [rcx+1Ch], bl
0x180066a6b  jz      short loc_180066A8D
0x180066a6d  cmp     byte ptr [rcx+19h], 2
0x180066a71  jb      short loc_180066A8D
0x180066a73  mov     edx, 111h
0x180066a78  mov     r9d, [rsp+98h+var_48]
0x180066a7d  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066a84  mov     rcx, [rcx+10h]
0x180066a88  call    WPP_SF_d
0x180066a8d  mov     eax, [rsp+98h+var_48]
0x180066a91  jmp     loc_180066CCB
0x180066a96  mov     rdi, [rsp+98h+var_38]
0x180066a9b  mov     [rsp+98h+var_38], rdi
0x180066aa0  mov     [rsp+98h+var_44], 19h
0x180066aa8  mov     edx, 2000019h; unsigned int
0x180066aad  mov     [rsp+98h+var_44], edx
0x180066ab1  mov     eax, r14d
0x180066ab4  and     eax, 0FFFFFFCFh
0x180066ab7  mov     [rsp+98h+var_58], 0; struct IWbemObjectSink *
0x180066ac0  mov     [rsp+98h+var_60], r13; struct IWbemContext *
0x180066ac5  mov     [rsp+98h+var_68], eax; int
0x180066ac9  mov     rax, [rsp+98h+arg_10]
0x180066ad1  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180066ad6  mov     rax, [rsp+98h+arg_8]
0x180066ade  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180066ae3  xor     r9d, r9d; struct _IWmiCoreHandle *
0x180066ae6  mov     r8, rdi; struct _IWmiFinalizer *
0x180066ae9  mov     rcx, r12; this
0x180066aec  call    ?_ExecNotificationQueryAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAG2JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::_ExecNotificationQueryAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x180066af1  mov     [rsp+98h+var_48], eax
0x180066af5  xor     r12d, r12d
0x180066af8  test    eax, eax
0x180066afa  jns     short loc_180066B6B
0x180066afc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066b02  mov     edx, [rsp+98h+var_48]
0x180066b06  mov     rcx, rax
0x180066b09  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b16  lea     rax, WPP_GLOBAL_Control
0x180066b1d  cmp     rcx, rax
0x180066b20  jz      short loc_180066B47
0x180066b22  test    [rcx+1Ch], bl
0x180066b25  jz      short loc_180066B47
0x180066b27  cmp     byte ptr [rcx+19h], 2
0x180066b2b  jb      short loc_180066B47
0x180066b2d  mov     edx, 112h
0x180066b32  mov     r9d, [rsp+98h+var_48]
0x180066b37  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066b3e  mov     rcx, [rcx+10h]
0x180066b42  call    WPP_SF_d
0x180066b47  mov     ebx, [rsp+98h+var_48]
0x180066b4b  test    rdi, rdi
0x180066b4e  jz      short loc_180066B5F
0x180066b50  mov     rdx, [rdi]
0x180066b53  mov     rcx, rdi
0x180066b56  mov     rax, [rdx+10h]
0x180066b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b5f  mov     [rsp+98h+var_38], r12
0x180066b64  mov     eax, ebx
0x180066b66  jmp     loc_180066CCB
0x180066b6b  mov     [rsp+98h+var_40], r12
0x180066b70  mov     rax, [rdi]
0x180066b73  lea     r9, [rsp+98h+var_40]
0x180066b78  lea     r8, IID_IEnumWbemClassObject
0x180066b7f  mov     edx, r14d
0x180066b82  mov     rcx, rdi
0x180066b85  mov     rax, [rax+58h]
0x180066b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b8e  mov     [rsp+98h+var_48], eax
0x180066b92  test    eax, eax
0x180066b94  jns     short loc_180066C05
0x180066b96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066b9c  mov     edx, [rsp+98h+var_48]
0x180066ba0  mov     rcx, rax
0x180066ba3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180066bb0  lea     rax, WPP_GLOBAL_Control
0x180066bb7  cmp     rcx, rax
0x180066bba  jz      short loc_180066BE1
0x180066bbc  test    [rcx+1Ch], bl
0x180066bbf  jz      short loc_180066BE1
0x180066bc1  cmp     byte ptr [rcx+19h], 2
0x180066bc5  jb      short loc_180066BE1
0x180066bc7  mov     edx, 113h
0x180066bcc  mov     r9d, [rsp+98h+var_48]
0x180066bd1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180066bd8  mov     rcx, [rcx+10h]
0x180066bdc  call    WPP_SF_d
0x180066be1  mov     ebx, [rsp+98h+var_48]
0x180066be5  test    rdi, rdi
0x180066be8  jz      short loc_180066BF9
0x180066bea  mov     rcx, [rdi]
0x180066bed  mov     rax, [rcx+10h]
0x180066bf1  mov     rcx, rdi
0x180066bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bf9  mov     [rsp+98h+var_38], r12
0x180066bfe  mov     eax, ebx
0x180066c00  jmp     loc_180066CCB
0x180066c05  mov     r14, [rsp+98h+var_40]
0x180066c0a  mov     [rsp+98h+var_30], r14
  ... truncated ...
```
