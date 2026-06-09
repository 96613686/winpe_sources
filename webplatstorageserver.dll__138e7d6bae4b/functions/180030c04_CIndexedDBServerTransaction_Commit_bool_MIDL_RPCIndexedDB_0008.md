# CIndexedDBServerTransaction::Commit(bool *,__MIDL_RPCIndexedDB_0008 *)

- ea: `0x180030c04`
- end: `0x180031077`
- name: `?Commit@CIndexedDBServerTransaction@@QEAAJPEA_NPEAU__MIDL_RPCIndexedDB_0008@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(CIndexedDBServerTransaction *__hidden this, bool *, struct __MIDL_RPCIndexedDB_0008 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028fa0`

## callees

- `0x18000ac20`
- `0x18000b1c0`
- `0x180017c20`
- `0x180024720`
- `0x1800247f4`
- `0x18002491c`
- `0x18002fe7c`
- `0x18002ff40`
- `0x180030c04`
- `0x180031080`
- `0x180031bdc`
- `0x18003233c`
- `0x180032498`
- `0x1800456ec`
- `0x18006772c`
- `0x18007176c`
- `0x1800929e4`
- `0x1800b13f0`
- `0x1800c5144`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030cec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030cec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030cb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030cb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030e89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030f24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030e89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030f24`

## string_xrefs

- `0x180031004`: `CIndexedDBServerTransaction::Commit`
- `0x180031047`: `CIndexedDBServerTransaction::Commit`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIndexedDBServerTransaction::Commit(
        CIndexedDBServerTransaction *this,
        bool *a2,
        struct __MIDL_RPCIndexedDB_0008 *a3)
{
  signed int DatabaseValuesWithTransaction; // edi
  struct _RTL_CRITICAL_SECTION *v6; // r12
  int v7; // r13d
  __int64 v8; // rbx
  void (__fastcall ***v9)(_QWORD); // rbx
  CIndexedDBServerDatabase *v10; // r14
  JET_SESID v11; // rcx
  int QuotaSizeForApp_Helper; // eax
  __int64 v13; // rdx
  __int64 v14; // r14
  unsigned int v15; // r8d
  unsigned int v16; // edx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  char v22[8]; // [rsp+30h] [rbp-20h] BYREF
  CIndexedDBServerTransaction *v23; // [rsp+38h] [rbp-18h]
  char *v24; // [rsp+40h] [rbp-10h]
  int v25; // [rsp+48h] [rbp-8h]
  unsigned __int64 v26; // [rsp+90h] [rbp+40h] BYREF
  bool *v27; // [rsp+98h] [rbp+48h]
  void (__fastcall ***v28)(_QWORD); // [rsp+A8h] [rbp+58h] BYREF

  v27 = a2;
  *a2 = 0;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_OWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 6) = 0;
  DatabaseValuesWithTransaction = -2147024891;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v24 = (char *)this + 16;
  v7 = 0;
  v25 = 0;
  if ( this != (CIndexedDBServerTransaction *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v7 = 1;
    v25 = 1;
    a2 = v27;
  }
  if ( !*((_BYTE *)this + 56) )
    goto LABEL_30;
  if ( *((_QWORD *)this + 21) )
  {
    if ( *((_DWORD *)this + 40) != 2
      || (*a2 = 1,
          DatabaseValuesWithTransaction = CIndexedDBServerDatabase::GetDatabaseValuesWithTransaction(
                                            *((CIndexedDBServerDatabase **)this + 23),
                                            this,
                                            a3),
          DatabaseValuesWithTransaction >= 0) )
    {
      v22[0] = 0;
      v23 = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 22);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
      DatabaseValuesWithTransaction = -2147024891;
      if ( !*((_BYTE *)this + 56)
        || (v8 = *((_QWORD *)this + 21), !*(_BYTE *)(v8 + 8))
        || (DatabaseValuesWithTransaction = HrJetSetSessionContext(*(_QWORD *)(v8 + 24), *((_QWORD *)this + 21)),
            DatabaseValuesWithTransaction < 0) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
        goto LABEL_28;
      }
      *(_DWORD *)(v8 + 12) = GetCurrentThreadId();
      v22[0] = 1;
      v9 = 0;
      v28 = 0;
      if ( *((_QWORD *)this + 8) )
      {
        DatabaseValuesWithTransaction = CIndexedDBServerTransactionBase::ReserveQuota(this, &v28);
        v9 = v28;
      }
      else
      {
        if ( !*((_BYTE *)this + 164) )
          goto LABEL_18;
        v10 = (CIndexedDBServerDatabase *)*((_QWORD *)this + 23);
        DatabaseValuesWithTransaction = 0;
        if ( (*(unsigned int (__fastcall **)(CIndexedDBServerTransaction *))(*(_QWORD *)this + 24LL))(this) )
        {
          v26 = 0;
          if ( (*(_DWORD *)(*((_QWORD *)v10 + 52) + 52LL) & 8) != 0 )
            QuotaSizeForApp_Helper = CIndexedDBServerDatabase::GetQuotaSizeForApp_Helper(v10, this, &v26);
          else
            QuotaSizeForApp_Helper = CIndexedDBServerDatabase::GetQuotaSizeForBrowser_Helper(
                                       v10,
                                       this,
                                       (*(_DWORD *)(*((_QWORD *)v10 + 52) + 52LL) & 0x40) != 0 ? 0x40 : 0,
                                       (*(_DWORD *)(*((_QWORD *)v10 + 52) + 52LL) & 0x40) != 0 ? 71 : 7,
                                       &v26);
          DatabaseValuesWithTransaction = QuotaSizeForApp_Helper;
          if ( QuotaSizeForApp_Helper < 0 )
            goto LABEL_26;
          v13 = *((_QWORD *)v10 + 52);
          if ( (*(_BYTE *)(v13 + 52) & 8) != 0 )
          {
            if ( *(_BYTE *)(v13 + 49) )
            {
              if ( !*(_BYTE *)(v13 + 48) )
              {
                v11 = *(_QWORD *)(*((_QWORD *)v10 + 100) + 8LL);
                if ( v26 <= v11 || (v18 = *(_DWORD *)(v13 + 4), v18 == 1) )
                  DatabaseValuesWithTransaction = 0;
                else
                  DatabaseValuesWithTransaction = -(v18 != 2) - 2140082175;
              }
            }
            else
            {
              v11 = *(_QWORD *)(*((_QWORD *)v10 + 100) + 8LL);
              if ( v26 > v11 )
                DatabaseValuesWithTransaction = -2140143594;
            }
          }
          else
          {
            v11 = *((_QWORD *)v10 + 100);
            DatabaseValuesWithTransaction = *(_QWORD *)(v11 + 8) < v26 ? 0x8070F001 : 0;
          }
        }
      }
      if ( DatabaseValuesWithTransaction >= 0 )
      {
LABEL_18:
        v14 = *((_QWORD *)this + 21);
        v11 = *(_QWORD *)(v14 + 24);
        if ( v11 == -1 )
        {
          DatabaseValuesWithTransaction = -1906377808;
        }
        else
        {
          DatabaseValuesWithTransaction = HrJetCommitTransaction(v11, 1u);
          if ( DatabaseValuesWithTransaction < 0
            || (DatabaseValuesWithTransaction = HrJetCloseDatabase(*(_QWORD *)(v14 + 24), *(_DWORD *)(v14 + 32), v15),
                DatabaseValuesWithTransaction < 0)
            || (*(_DWORD *)(v14 + 32) = -1,
                DatabaseValuesWithTransaction = HrJetResetSessionContext(*(_QWORD *)(v14 + 24)),
                DatabaseValuesWithTransaction < 0)
            || (DatabaseValuesWithTransaction = HrJetEndSession(*(_QWORD *)(v14 + 24), v16),
                DatabaseValuesWithTransaction < 0) )
          {
            if ( DatabaseValuesWithTransaction == -1906377716 )
              DatabaseValuesWithTransaction = -2140082174;
          }
          else
          {
            *(_QWORD *)(v14 + 24) = -1;
            *(_BYTE *)(v14 + 8) = 0;
            if ( v9 )
              (**v9)(v9);
            CIndexedDBServerTransactionsScheduler::RemoveTransFromRunningAndUnblockNext(
              (CIndexedDBServerTransactionsScheduler *)(*((_QWORD *)this + 23) + 568LL),
              this);
            if ( *((_DWORD *)this + 40) == 2 )
              CExclusiveConnectionsHelper::DowngrateExclusiveToNormalConnection((CExclusiveConnectionsHelper *)(*((_QWORD *)this + 23) + 104LL));
          }
        }
      }
LABEL_26:
      if ( v9 )
        std::default_delete<IQuotaReservation>::operator()(v11, v9);
LABEL_28:
      CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope((CIndexedDBServerTransaction::CTransactionThreadScope *)v22);
      if ( DatabaseValuesWithTransaction >= 0 )
      {
        CIndexedDBServerTransaction::Close(this);
        goto LABEL_30;
      }
    }
  }
  *v27 = 0;
  DatabaseValuesFree(a3);
  if ( DatabaseValuesWithTransaction != -2140082176
    && DatabaseValuesWithTransaction != -2140082175
    && DatabaseValuesWithTransaction != -2140082174 )
  {
    if ( (byte_180113B13 & 8) != 0 )
      WPP_SF_s(v20, 11, WPP_5867a90fb5d23b63feacd440fe71ecb3_Traceguids, "CIndexedDBServerTransaction::Commit");
    goto LABEL_59;
  }
  if ( (byte_180113B13 & 8) != 0 )
    WPP_SF_s(v20, 10, WPP_5867a90fb5d23b63feacd440fe71ecb3_Traceguids, "CIndexedDBServerTransaction::Commit");
  if ( DatabaseValuesWithTransaction != -2140082176 )
  {
    if ( (unsigned int)(DatabaseValuesWithTransaction + 2140082175) <= 1 )
    {
      v21 = L"QuotaLimit";
      goto LABEL_60;
    }
LABEL_59:
    v21 = L"InternalError";
LABEL_60:
    if ( (byte_180113DC6 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v20, v19, v21);
    CIndexedDBServerTransaction::Abort(this);
  }
LABEL_30:
  if ( v7 && v6 )
    LeaveCriticalSection(v6);
  return (unsigned int)DatabaseValuesWithTransaction;
}

```

## disassembly

```asm
0x180030c04  mov     [rsp-38h+arg_10], rbx
0x180030c09  mov     [rsp-38h+arg_8], rdx
0x180030c0e  push    rbp
0x180030c0f  push    rsi
0x180030c10  push    rdi
0x180030c11  push    r12
0x180030c13  push    r13
0x180030c15  push    r14
0x180030c17  push    r15
0x180030c19  mov     rbp, rsp
0x180030c1c  sub     rsp, 50h
0x180030c20  mov     r15, r8
0x180030c23  mov     rsi, rcx
0x180030c26  mov     byte ptr [rdx], 0
0x180030c29  xorps   xmm0, xmm0
0x180030c2c  xor     eax, eax
0x180030c2e  movups  xmmword ptr [r8], xmm0
0x180030c32  movups  xmmword ptr [r8+10h], xmm0
0x180030c37  movups  xmmword ptr [r8+20h], xmm0
0x180030c3c  mov     [r8+30h], rax
0x180030c40  mov     ebx, 80070005h
0x180030c45  mov     edi, ebx
0x180030c47  lea     r12, [rcx+10h]
0x180030c4b  mov     [rbp+var_10], r12
0x180030c4f  xor     r13d, r13d
0x180030c52  mov     [rbp+var_8], r13d
0x180030c56  test    r12, r12
0x180030c59  jz      short loc_180030C72
0x180030c5b  mov     rcx, r12; lpCriticalSection
0x180030c5e  call    cs:__imp_EnterCriticalSection
0x180030c64  mov     r13d, 1
0x180030c6a  mov     [rbp+var_8], r13d
0x180030c6e  mov     rdx, [rbp+arg_8]
0x180030c72  mov     al, [rsi+38h]
0x180030c75  nop
0x180030c76  test    al, al
0x180030c78  jz      loc_180030E7C
0x180030c7e  mov     r14d, 8070F002h
0x180030c84  cmp     qword ptr [rsi+0A8h], 0
0x180030c8c  jz      loc_180030FD1
0x180030c92  cmp     dword ptr [rsi+0A0h], 2
0x180030c99  jz      loc_180030F63
0x180030c9f  mov     [rbp+var_20], 0
0x180030ca3  mov     [rbp+var_18], rsi
0x180030ca7  lock inc dword ptr [rsi+58h]
0x180030cab  lea     r14, [rsi+0C0h]
0x180030cb2  mov     rcx, r14; lpCriticalSection
0x180030cb5  call    cs:__imp_EnterCriticalSection
0x180030cbb  mov     edi, ebx
0x180030cbd  mov     al, [rsi+38h]
0x180030cc0  nop
0x180030cc1  test    al, al
0x180030cc3  jz      loc_180030F21
0x180030cc9  mov     rbx, [rsi+0A8h]
0x180030cd0  cmp     byte ptr [rbx+8], 0
0x180030cd4  jz      loc_180030F21
0x180030cda  mov     rdx, rbx; unsigned __int64
0x180030cdd  mov     rcx, [rbx+18h]; unsigned __int64
0x180030ce1  call    ?HrJetSetSessionContext@@YAJ_K0@Z; HrJetSetSessionContext(unsigned __int64,unsigned __int64)
0x180030ce6  mov     edi, eax
0x180030ce8  test    eax, eax
0x180030cea  js      short loc_180030CF5
0x180030cec  call    cs:__imp_GetCurrentThreadId
0x180030cf2  mov     [rbx+0Ch], eax
0x180030cf5  test    edi, edi
0x180030cf7  js      loc_180030F21
0x180030cfd  mov     [rbp+var_20], 1
0x180030d01  xor     ebx, ebx
0x180030d03  mov     [rbp+arg_18], rbx
0x180030d07  cmp     [rsi+40h], rbx
0x180030d0b  jnz     loc_180030F2F
0x180030d11  cmp     [rsi+0A4h], bl
0x180030d17  jz      loc_180030DB9
0x180030d1d  mov     r14, [rsi+0B8h]
0x180030d24  xor     edi, edi
0x180030d26  mov     rax, [rsi]
0x180030d29  mov     rcx, rsi
0x180030d2c  mov     rax, [rax+18h]
0x180030d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d35  test    eax, eax
0x180030d37  jz      short loc_180030DB1
0x180030d39  mov     [rbp+arg_0], rdi
0x180030d3d  mov     rax, [r14+1A0h]
0x180030d44  mov     ecx, [rax+34h]
0x180030d47  mov     rdx, rsi; struct CIndexedDBServerTransactionBase *
0x180030d4a  test    cl, 8
0x180030d4d  jnz     loc_180030EC9
0x180030d53  and     ecx, 40h
0x180030d56  mov     eax, ecx
0x180030d58  neg     eax
0x180030d5a  sbb     r9d, r9d
0x180030d5d  and     r9d, 40h
0x180030d61  add     r9d, 7; unsigned int
0x180030d65  neg     ecx
0x180030d67  sbb     r8d, r8d
0x180030d6a  and     r8d, 40h; unsigned int
0x180030d6e  lea     rax, [rbp+arg_0]
0x180030d72  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180030d77  mov     rcx, r14; this
0x180030d7a  call    ?GetQuotaSizeForBrowser_Helper@CIndexedDBServerDatabase@@AEAAJPEAVCIndexedDBServerTransactionBase@@KKPEA_K@Z; CIndexedDBServerDatabase::GetQuotaSizeForBrowser_Helper(CIndexedDBServerTransactionBase *,ulong,ulong,unsigned __int64 *)
0x180030d7f  mov     edi, eax
0x180030d81  test    eax, eax
0x180030d83  js      loc_180030E59
0x180030d89  mov     rdx, [r14+1A0h]
0x180030d90  test    byte ptr [rdx+34h], 8
0x180030d94  jnz     loc_180030EDA
0x180030d9a  mov     rcx, [r14+320h]
0x180030da1  mov     rax, [rbp+arg_0]
0x180030da5  cmp     [rcx+8], rax
0x180030da9  sbb     edi, edi
0x180030dab  and     edi, 8070F001h
0x180030db1  test    edi, edi
0x180030db3  js      loc_180030E59
0x180030db9  mov     r14, [rsi+0A8h]
0x180030dc0  mov     rcx, [r14+18h]; unsigned __int64
0x180030dc4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180030dc8  jz      loc_180030F59
0x180030dce  mov     edx, 1; unsigned int
0x180030dd3  call    ?HrJetCommitTransaction@@YAJ_KK@Z; HrJetCommitTransaction(unsigned __int64,ulong)
0x180030dd8  mov     edi, eax
0x180030dda  test    eax, eax
0x180030ddc  js      loc_180030EA9
0x180030de2  mov     edx, [r14+20h]; unsigned int
0x180030de6  mov     rcx, [r14+18h]; unsigned __int64
0x180030dea  call    ?HrJetCloseDatabase@@YAJ_KKK@Z; HrJetCloseDatabase(unsigned __int64,ulong,ulong)
0x180030def  mov     edi, eax
0x180030df1  test    eax, eax
0x180030df3  js      loc_180030EA9
0x180030df9  mov     dword ptr [r14+20h], 0FFFFFFFFh
0x180030e01  mov     rcx, [r14+18h]; unsigned __int64
0x180030e05  call    ?HrJetResetSessionContext@@YAJ_K@Z; HrJetResetSessionContext(unsigned __int64)
0x180030e0a  mov     edi, eax
0x180030e0c  test    eax, eax
0x180030e0e  js      loc_180030EA9
0x180030e14  mov     rcx, [r14+18h]; unsigned __int64
0x180030e18  call    ?HrJetEndSession@@YAJ_KK@Z; HrJetEndSession(unsigned __int64,ulong)
0x180030e1d  mov     edi, eax
0x180030e1f  test    eax, eax
0x180030e21  js      loc_180030EA9
0x180030e27  mov     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFFh
0x180030e2f  mov     byte ptr [r14+8], 0
0x180030e34  jmp     short loc_180030EB1
0x180030e36  mov     rcx, [rsi+0B8h]
0x180030e3d  add     rcx, 238h; this
0x180030e44  mov     rdx, rsi; struct CIndexedDBServerTransaction *
0x180030e47  call    ?RemoveTransFromRunningAndUnblockNext@CIndexedDBServerTransactionsScheduler@@QEAAXPEAVCIndexedDBServerTransaction@@@Z; CIndexedDBServerTransactionsScheduler::RemoveTransFromRunningAndUnblockNext(CIndexedDBServerTransaction *)
0x180030e4c  cmp     dword ptr [rsi+0A0h], 2
0x180030e53  jz      loc_180030FA9
0x180030e59  test    rbx, rbx
0x180030e5c  jnz     loc_180030FBE
0x180030e62  lea     rcx, [rbp+var_20]; this
0x180030e66  call    ??1CTransactionThreadScope@CIndexedDBServerTransaction@@QEAA@XZ; CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope(void)
0x180030e6b  test    edi, edi
0x180030e6d  js      loc_180030FCB
0x180030e73  mov     rcx, rsi; this
0x180030e76  call    ?Close@CIndexedDBServerTransaction@@AEAAXXZ; CIndexedDBServerTransaction::Close(void)
0x180030e7b  nop
0x180030e7c  test    r13d, r13d
0x180030e7f  jz      short loc_180030E8F
0x180030e81  test    r12, r12
0x180030e84  jz      short loc_180030E8F
0x180030e86  mov     rcx, r12; lpCriticalSection
0x180030e89  call    cs:__imp_LeaveCriticalSection
0x180030e8f  mov     eax, edi
0x180030e91  mov     rbx, [rsp+50h+arg_10]
0x180030e99  add     rsp, 50h
0x180030e9d  pop     r15
0x180030e9f  pop     r14
0x180030ea1  pop     r13
0x180030ea3  pop     r12
0x180030ea5  pop     rdi
0x180030ea6  pop     rsi
0x180030ea7  pop     rbp
0x180030ea8  retn
0x180030ea9  test    edi, edi
0x180030eab  js      loc_180030F46
0x180030eb1  test    rbx, rbx
0x180030eb4  jz      short loc_180030E36
0x180030eb6  mov     rax, [rbx]
0x180030eb9  mov     rcx, rbx
0x180030ebc  mov     rax, [rax]
0x180030ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ec4  jmp     loc_180030E36
0x180030ec9  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x180030ecd  mov     rcx, r14; this
0x180030ed0  call    ?GetQuotaSizeForApp_Helper@CIndexedDBServerDatabase@@AEAAJPEAVCIndexedDBServerTransactionBase@@PEA_K@Z; CIndexedDBServerDatabase::GetQuotaSizeForApp_Helper(CIndexedDBServerTransactionBase *,unsigned __int64 *)
0x180030ed5  jmp     loc_180030D7F
0x180030eda  cmp     byte ptr [rdx+31h], 0
0x180030ede  jz      loc_180030F83
0x180030ee4  cmp     byte ptr [rdx+30h], 0
0x180030ee8  jnz     loc_180030DB1
0x180030eee  mov     rax, [r14+320h]
0x180030ef5  mov     rcx, [rax+8]
0x180030ef9  cmp     [rbp+arg_0], rcx
0x180030efd  jbe     loc_180030FA2
0x180030f03  mov     eax, [rdx+4]
0x180030f06  cmp     eax, 1
0x180030f09  jz      loc_180030FA2
0x180030f0f  sub     eax, 2
0x180030f12  neg     eax
0x180030f14  sbb     edi, edi
0x180030f16  add     edi, 8070F001h
0x180030f1c  jmp     loc_180030DB1
0x180030f21  mov     rcx, r14; lpCriticalSection
0x180030f24  call    cs:__imp_LeaveCriticalSection
0x180030f2a  jmp     loc_180030E62
0x180030f2f  lea     rdx, [rbp+arg_18]
0x180030f33  mov     rcx, rsi
0x180030f36  call    ?ReserveQuota@CIndexedDBServerTransactionBase@@IEAAJAEAV?$unique_ptr@UIQuotaReservation@@U?$default_delete@UIQuotaReservation@@@std@@@std@@@Z; CIndexedDBServerTransactionBase::ReserveQuota(std::unique_ptr<IQuotaReservation> &)
0x180030f3b  mov     edi, eax
0x180030f3d  mov     rbx, [rbp+arg_18]
0x180030f41  jmp     loc_180030DB1
0x180030f46  cmp     edi, 8E5EFC0Ch
0x180030f4c  mov     eax, 8070F002h
0x180030f51  cmovz   edi, eax
0x180030f54  jmp     loc_180030E59
0x180030f59  mov     edi, 8E5EFBB0h
0x180030f5e  jmp     loc_180030E59
0x180030f63  mov     byte ptr [rdx], 1
0x180030f66  mov     r8, r15; struct __MIDL_RPCIndexedDB_0008 *
0x180030f69  mov     rdx, rsi; struct CIndexedDBServerTransaction *
0x180030f6c  mov     rcx, [rsi+0B8h]; this
0x180030f73  call    ?GetDatabaseValuesWithTransaction@CIndexedDBServerDatabase@@QEAAJPEAVCIndexedDBServerTransaction@@PEAU__MIDL_RPCIndexedDB_0008@@@Z; CIndexedDBServerDatabase::GetDatabaseValuesWithTransaction(CIndexedDBServerTransaction *,__MIDL_RPCIndexedDB_0008 *)
0x180030f78  mov     edi, eax
0x180030f7a  test    eax, eax
0x180030f7c  js      short loc_180030FD1
0x180030f7e  jmp     loc_180030C9F
0x180030f83  mov     rax, [r14+320h]
0x180030f8a  mov     rcx, [rax+8]
0x180030f8e  cmp     [rbp+arg_0], rcx
0x180030f92  jbe     loc_180030DB1
0x180030f98  mov     edi, 80700016h
0x180030f9d  jmp     loc_180030DB1
0x180030fa2  xor     edi, edi
0x180030fa4  jmp     loc_180030DB1
0x180030fa9  mov     rcx, [rsi+0B8h]
0x180030fb0  add     rcx, 68h ; 'h'; this
0x180030fb4  call    ?DowngrateExclusiveToNormalConnection@CExclusiveConnectionsHelper@@QEAAXXZ; CExclusiveConnectionsHelper::DowngrateExclusiveToNormalConnection(void)
0x180030fb9  jmp     loc_180030E59
0x180030fbe  mov     rdx, rbx
0x180030fc1  call    ??R?$default_delete@UIQuotaReservation@@@std@@QEBAXPEAUIQuotaReservation@@@Z; std::default_delete<IQuotaReservation>::operator()(IQuotaReservation *)
0x180030fc6  jmp     loc_180030E62
0x180030fcb  mov     r14d, 8070F002h
0x180030fd1  mov     rax, [rbp+arg_8]
0x180030fd5  mov     byte ptr [rax], 0
0x180030fd8  mov     rcx, r15; struct __MIDL_RPCIndexedDB_0008 *
0x180030fdb  call    ?DatabaseValuesFree@@YAXPEAU__MIDL_RPCIndexedDB_0008@@@Z; DatabaseValuesFree(__MIDL_RPCIndexedDB_0008 *)
0x180030fe0  mov     ebx, 8070F000h
0x180030fe5  cmp     edi, ebx
0x180030fe7  jz      short loc_180031039
0x180030fe9  cmp     edi, 8070F001h
0x180030fef  jz      short loc_180031039
0x180030ff1  cmp     edi, r14d
0x180030ff4  jz      short loc_180031039
0x180030ff6  test    cs:byte_180113B13, 8
0x180030ffd  jz      short loc_180031017
0x180030fff  mov     edx, 0Bh
0x180031004  lea     r9, aCindexeddbserv_2; "CIndexedDBServerTransaction::Commit"
0x18003100b  lea     r8, WPP_5867a90fb5d23b63feacd440fe71ecb3_Traceguids
0x180031012  call    WPP_SF_s
0x180031017  mov     r8, cs:off_1800D3840; "InternalError"
0x18003101e  test    cs:byte_180113DC6, 1
0x180031025  jz      short loc_18003102C
0x180031027  call    McTemplateU0z_EventWriteTransfer
0x18003102c  mov     rcx, rsi; this
0x18003102f  call    ?Abort@CIndexedDBServerTransaction@@UEAAJXZ; CIndexedDBServerTransaction::Abort(void)
0x180031034  jmp     loc_180030E7C
0x180031039  test    cs:byte_180113B13, 8
0x180031040  jz      short loc_18003105A
0x180031042  mov     edx, 0Ah
0x180031047  lea     r9, aCindexeddbserv_2; "CIndexedDBServerTransaction::Commit"
0x18003104e  lea     r8, WPP_5867a90fb5d23b63feacd440fe71ecb3_Traceguids
0x180031055  call    WPP_SF_s
0x18003105a  cmp     edi, ebx
0x18003105c  jz      loc_180030E7C
0x180031062  lea     eax, [rdi+7F8F0FFFh]
0x180031068  cmp     eax, 1
0x18003106b  ja      short loc_180031017
0x18003106d  mov     r8, cs:off_1800D3830; "QuotaLimit"
0x180031074  jmp     short loc_18003101E
```
