# ComplexPingInternal(void *,unsigned __int64 *,ushort,ulong,ulong,unsigned __int64 * const,unsigned __int64 * const,ushort *)

- ea: `0x1800c1b5c`
- end: `0x1800c2261`
- name: `?ComplexPingInternal@@YAKPEAXPEA_KGKKQEA_K2PEAG@Z`
- size: `1797`
- prototype: `__int64 __fastcall(void *, unsigned __int64 *, unsigned __int16, int, unsigned int, unsigned __int64 *const, unsigned __int64 *const, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800c28d0`

## callees

- `0x180018344`
- `0x180034540`
- `0x18003e920`
- `0x18003e97c`
- `0x1800478b8`
- `0x180053cf4`
- `0x18007b484`
- `0x18008150c`
- `0x1800a16f4`
- `0x1800a228c`
- `0x1800b27e0`
- `0x1800b2bb0`
- `0x1800bbb84`
- `0x1800bbd34`
- `0x1800bc0c8`
- `0x1800bc0fc`
- `0x1800bc1d0`
- `0x1800c18c4`
- `0x1800c1960`
- `0x1800c1b5c`
- `0x1800c22f0`
- `0x1800c2360`
- `0x18010a000`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800c1d45`
- `RPCRT4!RpcImpersonateClient` at `0x1800c1d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1e2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1eaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1eaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1d6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1d57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1d57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c2232`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c2232`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c1e62`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c1e62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c1e24`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c1e24`

## string_xrefs

- `0x1800c1c0f`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c1c8a`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c1d02`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c1db5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c1f8a`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c2020`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c20da`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c2147`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c21e4`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c1c31`: `ComplexPingInternal SetID:%I64X, sequence:%d, AddToSet:%d DelFromSet:%d`
- `0x1800c1bf1`: `ComplexPingInternal`
- `0x1800c1dae`: `ComplexPingInternal`
- `0x1800c1e9f`: `ComplexPingInternal`
- `0x1800c1f2e`: `ComplexPingInternal`
- `0x1800c1f76`: `ComplexPingInternal`
- `0x1800c204b`: `ComplexPingInternal`
- `0x1800c20bf`: `ComplexPingInternal`
- `0x1800c213b`: `ComplexPingInternal`
- `0x1800c21d1`: `ComplexPingInternal`
- `0x1800c1d13`: `Security failure %!WINERROR! SetID:%I64X`
- `0x1800c1e88`: `New remote client started pinging securely SID:%!sid!`
- `0x1800c1f14`: `Ping Quota exceeded SID:%!sid!`
- `0x1800c1f7d`: `Ping Quota exceeded SID:%ws`
- `0x1800c203a`: `Allocated server set for remote client SetID:%I64X SID:%!sid!`

## pseudocode

```c
__int64 __fastcall ComplexPingInternal(
        void *a1,
        unsigned __int64 *a2,
        unsigned __int16 a3,
        int a4,
        unsigned int a5,
        unsigned __int64 *const a6,
        unsigned __int64 *const a7,
        unsigned __int16 *a8)
{
  int v8; // esi
  unsigned int v12; // r13d
  CServerSet *v13; // rax
  CServerSet *v14; // rsi
  DWORD LastError; // ebx
  void *v16; // rdi
  HANDLE CurrentThread; // rax
  struct CPingSetQuotaManager *v18; // r15
  CUserPingSetCount *i; // rsi
  DWORD v20; // r9d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  __int64 v25; // rdx
  void *v26; // rax
  int v27; // ecx
  int v28; // r9d
  int v29; // esi
  CPingSetQuotaManager *v30; // rcx
  int v31; // ecx
  int v32; // r8d
  int v33; // r8d
  CServerSetTable *v34; // rcx
  unsigned __int16 v35; // r15
  CPingSetQuotaManager *v36; // rcx
  int v38; // edi
  int v39; // r13d
  int v40; // r8d
  DWORD v41; // eax
  unsigned int v42; // r10d
  int v43; // r8d
  unsigned __int64 v44; // [rsp+30h] [rbp-20h]
  int v45; // [rsp+38h] [rbp-18h]
  int v46; // [rsp+40h] [rbp-10h]
  unsigned int v47; // [rsp+48h] [rbp-8h]
  PSID TokenInformation; // [rsp+50h] [rbp+0h] BYREF
  int v49; // [rsp+58h] [rbp+8h]
  void *TokenHandle; // [rsp+60h] [rbp+10h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+18h] BYREF

  v8 = a3;
  v49 = a4;
  WORD2(TokenInformation) = a3;
  if ( !a2 || a4 && !a6 )
    return 87;
  v12 = a5;
  if ( a5 )
  {
    if ( !a7 )
      return 87;
  }
  if ( !a8 )
    return 87;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpServerLock);
  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
  {
    v47 = a5;
    v46 = a4;
    v45 = v8;
    v44 = *a2;
    ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ComplexPingInternal", 3612);
  }
  if ( !*a2 )
  {
    v16 = 0;
    TokenHandle = 0;
    if ( RpcImpersonateClient(a1) )
      goto LABEL_26;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_26:
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
          ComTraceMessageT<>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (unsigned int)"ComplexPingInternal",
            3678,
            3,
            (__int64)L"New remote client started pinging unsecurely");
        LastError = 0;
LABEL_30:
        v18 = gpPingSetQuotaManager;
        CSharedLock::LockShared(*((LPCRITICAL_SECTION *)gpPingSetQuotaManager + 2));
        for ( i = *(CUserPingSetCount **)v18; ; i = *(CUserPingSetCount **)i )
        {
          if ( !i )
            goto LABEL_49;
          if ( (unsigned int)CUserPingSetCount::IsEqual(i, v16) )
            break;
        }
        if ( *((_DWORD *)i + 6) < CPingSetQuotaManager::_dwPerUserPingSetQuota )
        {
LABEL_49:
          v29 = 0;
          goto LABEL_50;
        }
        v29 = 1;
LABEL_50:
        CSharedLock::UnlockShared(*((CSharedLock **)v18 + 2));
        if ( v29 )
        {
          if ( v16 )
          {
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
              ComTraceMessageT<void *>(
                v31,
                (unsigned int)"ComplexPingInternal",
                3739,
                v32,
                (__int64)L"Ping Quota exceeded SID:%!sid!",
                v16);
          }
          else if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
          {
            ComTraceMessageT<unsigned short const *>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
              (unsigned int)"ComplexPingInternal",
              3743,
              v33,
              (__int64)L"Ping Quota exceeded SID:%ws",
              L"Anonymous");
          }
          LastError = 1721;
        }
        else
        {
          if ( CPingSetQuotaManager::ManageQuotaForUser(v30, v16, 1) )
          {
            v35 = WORD2(TokenInformation);
            v14 = CServerSetTable::Allocate(v34, WORD2(TokenInformation), v16, a2);
            if ( v14 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                  "ComplexPingInternal",
                  3769);
              goto LABEL_74;
            }
            CPingSetQuotaManager::ManageQuotaForUser(v36, v16, 0);
          }
          LastError = 14;
        }
LABEL_65:
        if ( v16 )
          operator delete(v16, 0);
        goto LABEL_67;
      }
    }
    v20 = 24;
    LODWORD(TokenInformation) = 24;
    while ( 1 )
    {
      v21 = v20 + 15LL;
      if ( v21 <= v20 )
        v21 = 0xFFFFFFFFFFFFFF0LL;
      v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
      v23 = alloca(v22);
      v24 = alloca(v22);
      if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, v20, (PDWORD)&TokenInformation) )
        break;
      if ( GetLastError() != 122 )
        goto LABEL_40;
      v20 = (unsigned int)TokenInformation;
    }
    v26 = (void *)operator new(12, v25, (unsigned int)TokenInformation - 12LL);
    v16 = v26;
    if ( v26 )
    {
      CopySid((DWORD)TokenInformation, v26, TokenInformation);
      goto LABEL_41;
    }
LABEL_40:
    LastError = 14;
LABEL_41:
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<void *>(
        v27,
        (unsigned int)"ComplexPingInternal",
        3726,
        v28,
        (__int64)L"New remote client started pinging securely SID:%!sid!",
        v16);
    CloseHandle(TokenHandle);
    if ( LastError )
      goto LABEL_65;
    goto LABEL_30;
  }
  v13 = CServerSetTable::Lookup(gpServerSetTable, *a2);
  v14 = v13;
  if ( !v13 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (unsigned int)"ComplexPingInternal",
        3620,
        0,
        (__int64)L"Invalid SetID:%I64X",
        *a2,
        v44,
        v45,
        v46,
        v47);
    LastError = 1912;
LABEL_67:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return LastError;
  }
  LastError = 0;
  if ( CServerSet::CheckSecurity(v13, a1) != 1 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      GetLastError();
      ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ComplexPingInternal", 3634);
    }
    LastError = 5;
    goto LABEL_67;
  }
  v35 = WORD2(TokenInformation);
LABEL_74:
  if ( !(unsigned int)CServerSet::CheckAndUpdateSequenceNumber(v14, v35) )
    goto LABEL_67;
  v38 = 0;
  LODWORD(TokenInformation) = 0;
  CServerSet::Ping(v14);
  *a8 = 0;
  if ( v49 )
  {
    v39 = v49;
    do
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (unsigned int)"ComplexPingInternal",
          3805,
          v40,
          (__int64)L"Adding to set OID:%I64X SetID:%I64X",
          a6[v39 - 1],
          *a2);
      v41 = CServerSet::AddObject(v14, a6[--v39]);
      v42 = 1911;
      LastError = v41;
      if ( v41 == 1911 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
          ComTraceMessage(v42, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ComplexPingInternal", 3810);
        v38 = 1;
      }
      else if ( v41 )
      {
        break;
      }
    }
    while ( v39 );
    v12 = a5;
    LODWORD(TokenInformation) = v38;
  }
  if ( v12 )
  {
    do
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (unsigned int)"ComplexPingInternal",
          3824,
          v43,
          (__int64)L"Removing from set OID:%I64X SetID:%I64X",
          a7[v12 - 1],
          *a2);
      CServerSet::RemoveObject(v14, &a7[--v12]);
    }
    while ( v12 );
    v38 = (int)TokenInformation;
  }
  if ( LastError || !v38 )
    goto LABEL_67;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1911;
}

```

## disassembly

```asm
0x1800c1b5c  push    rbp
0x1800c1b5e  push    rbx
0x1800c1b5f  push    rsi
0x1800c1b60  push    rdi
0x1800c1b61  push    r12
0x1800c1b63  push    r13
0x1800c1b65  push    r14
0x1800c1b67  push    r15
0x1800c1b69  sub     rsp, 88h
0x1800c1b70  lea     rbp, [rsp+50h]
0x1800c1b75  mov     rax, cs:__security_cookie
0x1800c1b7c  xor     rax, rbp
0x1800c1b7f  mov     [rbp+70h+var_50], rax
0x1800c1b83  movzx   esi, r8w
0x1800c1b87  mov     ebx, r9d
0x1800c1b8a  mov     [rbp+70h+var_68], ebx
0x1800c1b8d  mov     r14, rdx
0x1800c1b90  mov     [rbp+70h+var_6C], si
0x1800c1b94  mov     r15, rcx
0x1800c1b97  test    rdx, rdx
0x1800c1b9a  jz      loc_1800C223F
0x1800c1ba0  test    ebx, ebx
0x1800c1ba2  jz      short loc_1800C1BB2
0x1800c1ba4  cmp     [rbp+70h+arg_28], 0
0x1800c1bac  jz      loc_1800C223F
0x1800c1bb2  mov     r13d, [rbp+70h+arg_20]
0x1800c1bb9  test    r13d, r13d
0x1800c1bbc  jz      short loc_1800C1BCC
0x1800c1bbe  cmp     [rbp+70h+arg_30], 0
0x1800c1bc6  jz      loc_1800C223F
0x1800c1bcc  cmp     [rbp+70h+arg_38], 0
0x1800c1bd4  jz      loc_1800C223F
0x1800c1bda  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800c1be1  lea     rcx, [rbp+70h+SRWLock]
0x1800c1be5  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800c1bea  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c1bf1  lea     rdi, aComplexpingint_0; "ComplexPingInternal"
0x1800c1bf8  jz      short loc_1800C1C4A
0x1800c1bfa  mov     r8d, 4
0x1800c1c00  mov     ecx, r8d
0x1800c1c03  call    IsWppLevelEnabled
0x1800c1c08  test    al, al
0x1800c1c0a  jz      short loc_1800C1C4A
0x1800c1c0c  mov     rax, [r14]
0x1800c1c0f  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c1c16  mov     [rsp+0C0h+var_78], r13d
0x1800c1c1b  mov     r9d, 0E1Ch
0x1800c1c21  mov     [rsp+0C0h+var_80], ebx
0x1800c1c25  or      ecx, 0FFFFFFFFh
0x1800c1c28  mov     dword ptr [rsp+0C0h+var_88], esi
0x1800c1c2c  mov     [rsp+0C0h+var_90], rax
0x1800c1c31  lea     rax, aComplexpingint; "ComplexPingInternal SetID:%I64X, sequen"...
0x1800c1c38  mov     [rsp+0C0h+var_98], rax
0x1800c1c3d  mov     dword ptr [rsp+0C0h+ReturnLength], r8d
0x1800c1c42  mov     r8, rdi
0x1800c1c45  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c1c4a  mov     rdx, [r14]; unsigned __int64
0x1800c1c4d  test    rdx, rdx
0x1800c1c50  jz      loc_1800C1D3C
0x1800c1c56  mov     rcx, cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA; this
0x1800c1c5d  call    ?Lookup@CServerSetTable@@QEAAPEAVCServerSet@@_K@Z; CServerSetTable::Lookup(unsigned __int64)
0x1800c1c62  mov     rsi, rax
0x1800c1c65  test    rax, rax
0x1800c1c68  jnz     short loc_1800C1CBD
0x1800c1c6a  mov     eax, cs:dword_18014E4B8
0x1800c1c70  test    eax, eax
0x1800c1c72  jnz     short loc_1800C1C87
0x1800c1c74  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c1c7a  jz      short loc_1800C1CB3
0x1800c1c7c  xor     ecx, ecx
0x1800c1c7e  call    IsWppLevelEnabled
0x1800c1c83  test    al, al
0x1800c1c85  jz      short loc_1800C1CB3
0x1800c1c87  mov     rax, [r14]
0x1800c1c8a  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c1c91  mov     [rsp+0C0h+var_98], rax
0x1800c1c96  xor     r9d, r9d
0x1800c1c99  lea     rax, aInvalidSetidI6; "Invalid SetID:%I64X"
0x1800c1ca0  mov     r8d, 0E24h
0x1800c1ca6  mov     rdx, rdi
0x1800c1ca9  mov     [rsp+0C0h+ReturnLength], rax
0x1800c1cae  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800c1cb3  mov     ebx, 778h
0x1800c1cb8  jmp     loc_1800C1FEC
0x1800c1cbd  mov     rdx, r15; void *
0x1800c1cc0  mov     rcx, rax; this
0x1800c1cc3  xor     ebx, ebx
0x1800c1cc5  call    ?CheckSecurity@CServerSet@@QEAAHPEAX@Z; CServerSet::CheckSecurity(void *)
0x1800c1cca  lea     r12d, [rbx+1]
0x1800c1cce  cmp     eax, r12d
0x1800c1cd1  jz      loc_1800C2059
0x1800c1cd7  mov     eax, cs:dword_18014E4B8
0x1800c1cdd  test    eax, eax
0x1800c1cdf  jnz     short loc_1800C1CF4
0x1800c1ce1  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800c1ce7  jz      short loc_1800C1D32
0x1800c1ce9  xor     ecx, ecx
0x1800c1ceb  call    IsWppLevelEnabled
0x1800c1cf0  test    al, al
0x1800c1cf2  jz      short loc_1800C1D32
0x1800c1cf4  mov     rbx, [r14]
0x1800c1cf7  call    cs:__imp_GetLastError
0x1800c1cfd  mov     [rsp+0C0h+var_88], rbx
0x1800c1d02  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c1d09  mov     dword ptr [rsp+0C0h+var_90], eax
0x1800c1d0d  mov     r9d, 0E32h
0x1800c1d13  lea     rax, aSecurityFailur; "Security failure %!WINERROR! SetID:%I64"...
0x1800c1d1a  mov     r8, rdi
0x1800c1d1d  mov     [rsp+0C0h+var_98], rax
0x1800c1d22  or      ecx, 0FFFFFFFFh
0x1800c1d25  mov     dword ptr [rsp+0C0h+ReturnLength], 0
0x1800c1d2d  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c1d32  mov     ebx, 5
0x1800c1d37  jmp     loc_1800C1FEC
0x1800c1d3c  xor     edi, edi
0x1800c1d3e  mov     rcx, r15; BindingHandle
0x1800c1d41  mov     [rbp+70h+TokenHandle], rdi
0x1800c1d45  call    cs:__imp_RpcImpersonateClient
0x1800c1d4b  lea     r15d, [rdi+0Eh]
0x1800c1d4f  lea     r12d, [rdi+1]
0x1800c1d53  test    eax, eax
0x1800c1d55  jnz     short loc_1800C1D80
0x1800c1d57  call    cs:__imp_GetCurrentThread
0x1800c1d5d  lea     r9, [rbp+70h+TokenHandle]; TokenHandle
0x1800c1d61  mov     r8d, r12d; OpenAsSelf
0x1800c1d64  mov     rcx, rax; ThreadHandle
0x1800c1d67  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800c1d6a  call    cs:__imp_OpenThreadToken
0x1800c1d70  test    eax, eax
0x1800c1d72  jnz     short loc_1800C1DDB
0x1800c1d74  call    cs:__imp_GetLastError
0x1800c1d7a  mov     ebx, eax
0x1800c1d7c  test    eax, eax
0x1800c1d7e  jz      short loc_1800C1DDD
0x1800c1d80  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800c1d86  jz      short loc_1800C1DC1
0x1800c1d88  mov     ecx, 3
0x1800c1d8d  call    IsWppLevelEnabled
0x1800c1d92  test    al, al
0x1800c1d94  jz      short loc_1800C1DC1
0x1800c1d96  lea     rax, aNewRemoteClien; "New remote client started pinging unsec"...
0x1800c1d9d  mov     r9d, 3
0x1800c1da3  mov     r8d, 0E5Eh
0x1800c1da9  mov     [rsp+0C0h+ReturnLength], rax
0x1800c1dae  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c1db5  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c1dbc  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800c1dc1  xor     ebx, ebx
0x1800c1dc3  mov     r15, cs:?gpPingSetQuotaManager@@3PEAVCPingSetQuotaManager@@EA; CPingSetQuotaManager * gpPingSetQuotaManager
0x1800c1dca  mov     rcx, [r15+10h]; lpCriticalSection
0x1800c1dce  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x1800c1dd3  mov     rsi, [r15]
0x1800c1dd6  jmp     loc_1800C1ED4
0x1800c1ddb  xor     ebx, ebx
0x1800c1ddd  mov     r9d, 18h
0x1800c1de3  mov     [rbp+70h+TokenInformation], r9d
0x1800c1de7  mov     eax, r9d
0x1800c1dea  lea     rcx, [rax+0Fh]
0x1800c1dee  cmp     rcx, rax
0x1800c1df1  ja      short loc_1800C1DFD
0x1800c1df3  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c1dfd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c1e01  mov     rax, rcx
0x1800c1e04  call    _alloca_probe
0x1800c1e09  sub     rsp, rcx
0x1800c1e0c  lea     rax, [rbp+70h+TokenInformation]
0x1800c1e10  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x1800c1e14  mov     edx, r12d; TokenInformationClass
0x1800c1e17  lea     rsi, [rsp+0C0h+TokenInformation]
0x1800c1e1c  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800c1e21  mov     r8, rsi; TokenInformation
0x1800c1e24  call    cs:__imp_GetTokenInformation
0x1800c1e2a  test    eax, eax
0x1800c1e2c  jnz     short loc_1800C1E3F
0x1800c1e2e  call    cs:__imp_GetLastError
0x1800c1e34  cmp     eax, 7Ah ; 'z'
0x1800c1e37  jnz     short loc_1800C1E6A
0x1800c1e39  mov     r9d, [rbp+70h+TokenInformation]
0x1800c1e3d  jmp     short loc_1800C1DE7
0x1800c1e3f  mov     r8d, [rbp+70h+TokenInformation]
0x1800c1e43  mov     ecx, 0Ch
0x1800c1e48  sub     r8, 0Ch
0x1800c1e4c  call    ??2@YAPEAX_KVallocateExtra_t@@0@Z; operator new(unsigned __int64,allocateExtra_t,unsigned __int64)
0x1800c1e51  mov     rdi, rax
0x1800c1e54  test    rax, rax
0x1800c1e57  jz      short loc_1800C1E6A
0x1800c1e59  mov     r8, [rsi]; pSourceSid
0x1800c1e5c  mov     rdx, rax; pDestinationSid
0x1800c1e5f  mov     ecx, [rbp+70h+TokenInformation]; nDestinationSidLength
0x1800c1e62  call    cs:__imp_CopySid
0x1800c1e68  jmp     short loc_1800C1E6D
0x1800c1e6a  mov     ebx, r15d
0x1800c1e6d  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c1e74  jz      short loc_1800C1EAB
0x1800c1e76  mov     r9d, 3
0x1800c1e7c  mov     ecx, r9d
0x1800c1e7f  call    IsWppLevelEnabled
0x1800c1e84  test    al, al
0x1800c1e86  jz      short loc_1800C1EAB
0x1800c1e88  lea     rax, aNewRemoteClien_0; "New remote client started pinging secur"...
0x1800c1e8f  mov     [rsp+0C0h+var_98], rdi
0x1800c1e94  mov     r8d, 0E8Eh
0x1800c1e9a  mov     [rsp+0C0h+ReturnLength], rax
0x1800c1e9f  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c1ea6  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x1800c1eab  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x1800c1eaf  call    cs:__imp_CloseHandle
0x1800c1eb5  test    ebx, ebx
0x1800c1eb7  jnz     loc_1800C1FDD
0x1800c1ebd  jmp     loc_1800C1DC3
0x1800c1ec2  mov     rdx, rdi; void *
0x1800c1ec5  mov     rcx, rsi; this
0x1800c1ec8  call    ?IsEqual@CUserPingSetCount@@QEAAHPEAX@Z; CUserPingSetCount::IsEqual(void *)
0x1800c1ecd  test    eax, eax
0x1800c1ecf  jnz     short loc_1800C1F3C
0x1800c1ed1  mov     rsi, [rsi]
0x1800c1ed4  test    rsi, rsi
0x1800c1ed7  jnz     short loc_1800C1EC2
0x1800c1ed9  xor     esi, esi
0x1800c1edb  mov     rcx, [r15+10h]; this
0x1800c1edf  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x1800c1ee4  test    esi, esi
0x1800c1ee6  jz      loc_1800C1FA2
0x1800c1eec  test    rdi, rdi
0x1800c1eef  jz      short loc_1800C1F4C
0x1800c1ef1  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c1ef8  jz      loc_1800C1F9B
0x1800c1efe  mov     r8d, 3
0x1800c1f04  mov     ecx, r8d
0x1800c1f07  call    IsWppLevelEnabled
0x1800c1f0c  test    al, al
0x1800c1f0e  jz      loc_1800C1F9B
0x1800c1f14  lea     rax, aPingQuotaExcee_0; "Ping Quota exceeded SID:%!sid!"
0x1800c1f1b  mov     [rsp+0C0h+var_98], rdi
0x1800c1f20  mov     r9d, r8d
0x1800c1f23  mov     [rsp+0C0h+ReturnLength], rax
0x1800c1f28  mov     r8d, 0E9Bh
0x1800c1f2e  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c1f35  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x1800c1f3a  jmp     short loc_1800C1F9B
0x1800c1f3c  mov     eax, cs:?_dwPerUserPingSetQuota@CPingSetQuotaManager@@0KA; ulong CPingSetQuotaManager::_dwPerUserPingSetQuota
0x1800c1f42  cmp     [rsi+18h], eax
0x1800c1f45  jb      short loc_1800C1ED9
0x1800c1f47  mov     esi, r12d
0x1800c1f4a  jmp     short loc_1800C1EDB
0x1800c1f4c  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c1f53  jz      short loc_1800C1F9B
0x1800c1f55  mov     r8d, 3
0x1800c1f5b  mov     ecx, r8d
0x1800c1f5e  call    IsWppLevelEnabled
0x1800c1f63  test    al, al
0x1800c1f65  jz      short loc_1800C1F9B
0x1800c1f67  lea     rax, aAnonymous; "Anonymous"
0x1800c1f6e  mov     r9d, r8d
0x1800c1f71  mov     [rsp+0C0h+var_98], rax
0x1800c1f76  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c1f7d  lea     rax, aPingQuotaExcee; "Ping Quota exceeded SID:%ws"
0x1800c1f84  mov     r8d, 0E9Fh
0x1800c1f8a  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c1f91  mov     [rsp+0C0h+ReturnLength], rax
0x1800c1f96  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800c1f9b  mov     ebx, 6B9h
0x1800c1fa0  jmp     short loc_1800C1FDD
0x1800c1fa2  mov     r8d, r12d; int
0x1800c1fa5  mov     rdx, rdi; void *
0x1800c1fa8  call    ?ManageQuotaForUser@CPingSetQuotaManager@@QEAAHPEAXH@Z; CPingSetQuotaManager::ManageQuotaForUser(void *,int)
0x1800c1fad  test    eax, eax
0x1800c1faf  jz      short loc_1800C1FD8
0x1800c1fb1  movzx   r15d, [rbp+70h+var_6C]
0x1800c1fb6  mov     r9, r14; unsigned __int64 *
0x1800c1fb9  movzx   edx, r15w; unsigned __int16
0x1800c1fbd  mov     r8, rdi; void *
0x1800c1fc0  call    ?Allocate@CServerSetTable@@QEAAPEAVCServerSet@@GPEAXAEA_K@Z; CServerSetTable::Allocate(ushort,void *,unsigned __int64 &)
0x1800c1fc5  mov     rsi, rax
0x1800c1fc8  test    rax, rax
0x1800c1fcb  jnz     short loc_1800C2002
0x1800c1fcd  xor     r8d, r8d; int
0x1800c1fd0  mov     rdx, rdi; void *
0x1800c1fd3  call    ?ManageQuotaForUser@CPingSetQuotaManager@@QEAAHPEAXH@Z; CPingSetQuotaManager::ManageQuotaForUser(void *,int)
0x1800c1fd8  mov     ebx, 0Eh
0x1800c1fdd  test    rdi, rdi
0x1800c1fe0  jz      short loc_1800C1FEC
0x1800c1fe2  xor     edx, edx; unsigned __int64
0x1800c1fe4  mov     rcx, rdi; void *
0x1800c1fe7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c1fec  mov     rcx, [rbp+70h+SRWLock]; SRWLock
0x1800c1ff0  test    rcx, rcx
0x1800c1ff3  jz      short loc_1800C1FFB
0x1800c1ff5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c1ffb  mov     eax, ebx
0x1800c1ffd  jmp     loc_1800C2244
0x1800c2002  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c2009  jz      short loc_1800C205E
0x1800c200b  mov     r8d, 3
0x1800c2011  mov     ecx, r8d
0x1800c2014  call    IsWppLevelEnabled
0x1800c2019  test    al, al
0x1800c201b  jz      short loc_1800C205E
0x1800c201d  mov     rax, [r14]
0x1800c2020  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
  ... truncated ...
```
