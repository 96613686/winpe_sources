# RenameDomainConnectedAccount(RenameAccountData &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18008f808`
- end: `0x18008fa3b`
- name: `?RenameDomainConnectedAccount@@YAJAEAURenameAccountData@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1f78`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800204ac`
- `0x18003c3c0`
- `0x18008f808`
- `0x180094b4c`
- `0x1800b1afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f9d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f9d4`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x18008f8d5`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x18008f8d5`
- `ktmw32!CreateTransaction` at `0x18008f916`
- `ktmw32!CreateTransaction` at `0x18008f916`
- `ktmw32!CommitTransaction` at `0x18008f9ca`
- `ktmw32!CommitTransaction` at `0x18008f9ca`

## string_xrefs

- `0x18008f9e6`: `Failure - CommitTransaction, HRESULT: 0x%08X\n`
- `0x18008f943`: `Failure - CreateTransaction, HRESULT: 0x%08X\n`
- `0x18008f874`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x18008f84d`: `RenameDomainConnectedAccount`
- `0x18008f98b`: `RenameDomainConnectedAccount`
- `0x18008f976`: `hr = DeleteIdentityStore(renameAccountData.hOldUser, true, hTransaction, cid, isAssociated)`
- `0x18008f9b3`: `hr = HandleConnectIdentity(renameAccountData.hNewUser, &connectFlags, hTransaction)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RenameDomainConnectedAccount(__int64 a1)
{
  HANDLE Transaction; // rbx
  char v3; // di
  signed int LastError; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  int v7; // eax
  const char *v8; // rcx
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  const unsigned __int16 *IsolationFlags; // [rsp+20h] [rbp-69h]
  const unsigned __int16 *IsolationFlagsb; // [rsp+20h] [rbp-69h]
  DWORD IsolationFlagsa[2]; // [rsp+20h] [rbp-69h]
  int v15; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v17[4]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v18; // [rsp+80h] [rbp-9h] BYREF
  __int128 v19; // [rsp+90h] [rbp+7h]
  _QWORD v20[4]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+100h] [rbp+77h] BYREF
  signed int v22; // [rsp+108h] [rbp+7Fh] BYREF

  v22 = 0;
  v18 = 0;
  v19 = 0;
  Transaction = 0;
  memset(v16, 0, sizeof(v16));
  v20[0] = "RenameDomainConnectedAccount";
  v20[1] = &v22;
  v20[2] = 0;
  v20[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "RenameDomainConnectedAccount",
    (const char *)0x15C,
    0,
    IsolationFlags);
  *(_QWORD *)&v18 = 1;
  DWORD2(v19) = 1;
  v15 = -1073741811;
  LOBYTE(v21) = 0;
  v17[0] = "IsTransactionAPIPresent";
  v17[1] = &v15;
  v17[2] = 0;
  v17[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "IsTransactionAPIPresent",
    (const char *)0x246,
    0,
    IsolationFlagsb);
  v15 = ApiSetQueryApiSetPresence(L"24", &v21);
  if ( v15 < 0 || (v3 = 1, !(_BYTE)v21) )
    v3 = 0;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v17);
  if ( v3 )
  {
    Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
    Auto<void *,HandleFunctor,IWinApiLite>::Clear(v16);
    v16[0] = Transaction;
    if ( !Transaction )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = L"Failure - CreateTransaction, HRESULT: 0x%08X\n";
      v6 = 359;
LABEL_19:
      IsolationFlagsa[0] = LastError;
      v22 = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
        v6,
        v5,
        *(_QWORD *)IsolationFlagsa);
      goto LABEL_20;
    }
  }
  v7 = DeleteIdentityStore(*(void **)(a1 + 32), (__int64)&v21);
  v22 = v7;
  if ( v7 < 0 )
  {
    v8 = "hr = DeleteIdentityStore(renameAccountData.hOldUser, true, hTransaction, cid, isAssociated)";
    v9 = 363;
LABEL_11:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
      "RenameDomainConnectedAccount",
      v9,
      v7,
      v8);
    goto LABEL_20;
  }
  v7 = HandleConnectIdentity(*(void *const *)(a1 + 40), (struct _WLID_CONNECT_PARAM *const)&v18, Transaction);
  v22 = v7;
  if ( v7 < 0 )
  {
    v8 = "hr = HandleConnectIdentity(renameAccountData.hNewUser, &connectFlags, hTransaction)";
    v9 = 365;
    goto LABEL_11;
  }
  if ( Transaction && !CommitTransaction(Transaction) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = L"Failure - CommitTransaction, HRESULT: 0x%08X\n";
    v6 = 373;
    goto LABEL_19;
  }
LABEL_20:
  v10 = v22;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v20);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v16);
  return v10;
}

```

## disassembly

```asm
0x18008f808  mov     [rsp-8+arg_0], rbx
0x18008f80d  mov     [rsp-8+arg_8], rsi
0x18008f812  push    rbp
0x18008f813  push    rdi
0x18008f814  push    r12
0x18008f816  push    r14
0x18008f818  push    r15
0x18008f81a  lea     rbp, [rsp-37h]
0x18008f81f  sub     rsp, 0C0h
0x18008f826  mov     r14, rdx
0x18008f829  mov     rsi, rcx
0x18008f82c  xor     r15d, r15d
0x18008f82f  mov     [rbp+57h+arg_18], r15d
0x18008f833  xorps   xmm0, xmm0
0x18008f836  movups  [rbp+57h+var_60], xmm0
0x18008f83a  movups  [rbp+57h+var_50], xmm0
0x18008f83e  mov     ebx, r15d
0x18008f841  mov     [rbp+57h+var_98], rbx
0x18008f845  mov     [rbp+57h+var_88], r15
0x18008f849  mov     [rbp+57h+var_90], r15
0x18008f84d  lea     rcx, aRenamedomainco; "RenameDomainConnectedAccount"
0x18008f854  mov     [rbp+57h+var_40], rcx
0x18008f858  lea     rax, [rbp+57h+arg_18]
0x18008f85c  mov     [rbp+57h+var_38], rax
0x18008f860  mov     [rbp+57h+var_30], r15
0x18008f864  mov     [rbp+57h+var_28], r15
0x18008f868  xor     r9d, r9d; unsigned int
0x18008f86b  mov     r8d, 15Ch; char *
0x18008f871  mov     rdx, rcx; char *
0x18008f874  lea     r12, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008f87b  mov     rcx, r12; this
0x18008f87e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008f883  nop
0x18008f884  mov     qword ptr [rbp+57h+var_60], 1
0x18008f88c  mov     dword ptr [rbp+57h+var_50+8], 1
0x18008f893  mov     [rbp+57h+var_A0], 0C000000Dh
0x18008f89a  mov     byte ptr [rbp+57h+arg_10], r15b
0x18008f89e  lea     rdx, aIstransactiona; "IsTransactionAPIPresent"
0x18008f8a5  mov     [rbp+57h+var_80], rdx
0x18008f8a9  lea     rax, [rbp+57h+var_A0]
0x18008f8ad  mov     [rbp+57h+var_78], rax
0x18008f8b1  mov     [rbp+57h+var_70], r15
0x18008f8b5  mov     [rbp+57h+var_68], r15
0x18008f8b9  xor     r9d, r9d; unsigned int
0x18008f8bc  mov     r8d, 246h; char *
0x18008f8c2  mov     rcx, r12; this
0x18008f8c5  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008f8ca  lea     rdx, [rbp+57h+arg_10]
0x18008f8ce  lea     rcx, a24; "24"
0x18008f8d5  call    cs:__imp_ApiSetQueryApiSetPresence
0x18008f8db  mov     [rbp+57h+var_A0], eax
0x18008f8de  test    eax, eax
0x18008f8e0  js      short loc_18008F8EB
0x18008f8e2  cmp     byte ptr [rbp+57h+arg_10], r15b
0x18008f8e6  mov     dil, 1
0x18008f8e9  jnz     short loc_18008F8EE
0x18008f8eb  mov     dil, r15b
0x18008f8ee  lea     rcx, [rbp+57h+var_80]
0x18008f8f2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18008f8f7  test    dil, dil
0x18008f8fa  jz      short loc_18008F955
0x18008f8fc  mov     [rsp+0E0h+Description], r15; Description
0x18008f901  mov     [rsp+0E0h+Timeout], r15d; Timeout
0x18008f906  mov     [rsp+0E0h+IsolationFlags], r15d; IsolationFlags
0x18008f90b  xor     r9d, r9d; IsolationLevel
0x18008f90e  xor     edx, edx; UOW
0x18008f910  xor     ecx, ecx; lpTransactionAttributes
0x18008f912  lea     r8d, [r9+1]; CreateOptions
0x18008f916  call    cs:__imp_CreateTransaction
0x18008f91c  mov     rbx, rax
0x18008f91f  lea     rcx, [rbp+57h+var_98]
0x18008f923  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x18008f928  mov     [rbp+57h+var_98], rbx
0x18008f92c  test    rbx, rbx
0x18008f92f  jnz     short loc_18008F955
0x18008f931  call    cs:__imp_GetLastError
0x18008f937  test    eax, eax
0x18008f939  jle     short loc_18008F943
0x18008f93b  movzx   eax, ax
0x18008f93e  or      eax, 80070000h
0x18008f943  lea     r9, aFailureCreatet; "Failure - CreateTransaction, HRESULT: 0"...
0x18008f94a  mov     r8d, 167h
0x18008f950  jmp     loc_18008F9F3
0x18008f955  lea     rax, [rbp+57h+arg_10]
0x18008f959  mov     qword ptr [rsp+0E0h+IsolationFlags], rax; __int64
0x18008f95e  mov     r9, r14
0x18008f961  mov     r8, rbx
0x18008f964  mov     dl, 1
0x18008f966  mov     rcx, [rsi+20h]; void *
0x18008f96a  call    ?DeleteIdentityStore@@YAJPEAX_N0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAH@Z; DeleteIdentityStore(void *,bool,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int &)
0x18008f96f  mov     [rbp+57h+arg_18], eax
0x18008f972  test    eax, eax
0x18008f974  jns     short loc_18008F99C
0x18008f976  lea     rcx, aHrDeleteidenti_0; "hr = DeleteIdentityStore(renameAccountD"...
0x18008f97d  mov     r8d, 16Bh; unsigned int
0x18008f983  mov     r9d, eax; int
0x18008f986  mov     qword ptr [rsp+0E0h+IsolationFlags], rcx; char *
0x18008f98b  lea     rdx, aRenamedomainco; "RenameDomainConnectedAccount"
0x18008f992  mov     rcx, r12; char *
0x18008f995  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18008f99a  jmp     short loc_18008FA07
0x18008f99c  mov     r8, rbx; void *
0x18008f99f  lea     rdx, [rbp+57h+var_60]; struct _WLID_CONNECT_PARAM *
0x18008f9a3  mov     rcx, [rsi+28h]; void *
0x18008f9a7  call    ?HandleConnectIdentity@@YAJQEAXQEAU_WLID_CONNECT_PARAM@@PEAX@Z; HandleConnectIdentity(void * const,_WLID_CONNECT_PARAM * const,void *)
0x18008f9ac  mov     [rbp+57h+arg_18], eax
0x18008f9af  test    eax, eax
0x18008f9b1  jns     short loc_18008F9C2
0x18008f9b3  lea     rcx, aHrHandleconnec_0; "hr = HandleConnectIdentity(renameAccoun"...
0x18008f9ba  mov     r8d, 16Dh
0x18008f9c0  jmp     short loc_18008F983
0x18008f9c2  test    rbx, rbx
0x18008f9c5  jz      short loc_18008FA07
0x18008f9c7  mov     rcx, rbx; TransactionHandle
0x18008f9ca  call    cs:__imp_CommitTransaction
0x18008f9d0  test    eax, eax
0x18008f9d2  jnz     short loc_18008FA07
0x18008f9d4  call    cs:__imp_GetLastError
0x18008f9da  test    eax, eax
0x18008f9dc  jle     short loc_18008F9E6
0x18008f9de  movzx   eax, ax
0x18008f9e1  or      eax, 80070000h
0x18008f9e6  lea     r9, aFailureCommitt; "Failure - CommitTransaction, HRESULT: 0"...
0x18008f9ed  mov     r8d, 175h; unsigned int
0x18008f9f3  mov     [rsp+0E0h+IsolationFlags], eax
0x18008f9f7  mov     [rbp+57h+arg_18], eax
0x18008f9fa  mov     rdx, r12; char *
0x18008f9fd  mov     ecx, 2; unsigned __int8
0x18008fa02  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008fa07  mov     ebx, [rbp+57h+arg_18]
0x18008fa0a  lea     rcx, [rbp+57h+var_40]
0x18008fa0e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18008fa13  nop
0x18008fa14  lea     rcx, [rbp+57h+var_98]
0x18008fa18  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x18008fa1d  mov     eax, ebx
0x18008fa1f  lea     r11, [rsp+0E0h+var_20]
0x18008fa27  mov     rbx, [r11+30h]
0x18008fa2b  mov     rsi, [r11+38h]
0x18008fa2f  mov     rsp, r11
0x18008fa32  pop     r15
0x18008fa34  pop     r14
0x18008fa36  pop     r12
0x18008fa38  pop     rdi
0x18008fa39  pop     rbp
0x18008fa3a  retn
```
