# ComplexPingInternal(void *,unsigned __int64 *,ushort,ulong,ulong,unsigned __int64 * const,unsigned __int64 * const,ushort *)

- ea: `0x1800c77cc`
- end: `0x1800c7f14`
- name: `?ComplexPingInternal@@YAKPEAXPEA_KGKKQEA_K2PEAG@Z`
- size: `1864`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned __int64 *@<rdx>, unsigned __int16@<r8w>, unsigned int@<r9d>, unsigned int, unsigned __int64 *const, unsigned __int64 *const, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800c8590`

## callees

- `0x18001c624`
- `0x180034260`
- `0x180039c48`
- `0x180046930`
- `0x180046994`
- `0x180059020`
- `0x18007fb90`
- `0x1800858f0`
- `0x1800a6c48`
- `0x1800a780c`
- `0x1800b7ac0`
- `0x1800b7e90`
- `0x1800c1480`
- `0x1800c1630`
- `0x1800c19e8`
- `0x1800c1a20`
- `0x1800c1af8`
- `0x1800c74f4`
- `0x1800c7590`
- `0x1800c77cc`
- `0x1800c7fb0`
- `0x1800c8028`
- `0x180112d00`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800c79bb`
- `RPCRT4!RpcImpersonateClient` at `0x1800c79bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7ac2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7b4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7b4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c79ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c79ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c79d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c79d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c7c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c7ede`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c7c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c7ede`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c7afc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c7afc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c7ab2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c7ab2`

## string_xrefs

- `0x1800c787f`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c78fa`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7978`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7a43`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7c30`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7ccc`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7d86`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7df3`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c7e90`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800c78a1`: `ComplexPingInternal SetID:%I64X, sequence:%d, AddToSet:%d DelFromSet:%d`
- `0x1800c7861`: `ComplexPingInternal`
- `0x1800c7a3c`: `ComplexPingInternal`
- `0x1800c7b3f`: `ComplexPingInternal`
- `0x1800c7bd4`: `ComplexPingInternal`
- `0x1800c7c1c`: `ComplexPingInternal`
- `0x1800c7cf7`: `ComplexPingInternal`
- `0x1800c7d6b`: `ComplexPingInternal`
- `0x1800c7de7`: `ComplexPingInternal`
- `0x1800c7e7d`: `ComplexPingInternal`
- `0x1800c7989`: `Security failure %!WINERROR! SetID:%I64X`
- `0x1800c7b28`: `New remote client started pinging securely SID:%!sid!`
- `0x1800c7bba`: `Ping Quota exceeded SID:%!sid!`
- `0x1800c7c23`: `Ping Quota exceeded SID:%ws`
- `0x1800c7ce6`: `Allocated server set for remote client SetID:%I64X SID:%!sid!`

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
  int v13; // r8d
  CServerSet *v14; // rax
  CServerSet *v15; // rsi
  DWORD LastError; // ebx
  unsigned __int64 v17; // rbx
  void *v18; // rdi
  HANDLE CurrentThread; // rax
  struct CPingSetQuotaManager *v20; // r15
  CUserPingSetCount *i; // rsi
  DWORD v22; // r9d
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  __int64 v27; // rdx
  void *v28; // rax
  int v29; // ecx
  int v30; // r9d
  int v31; // esi
  CPingSetQuotaManager *v32; // rcx
  int v33; // ecx
  int v34; // r8d
  int v35; // r8d
  CServerSetTable *v36; // rcx
  unsigned __int16 v37; // r15
  CPingSetQuotaManager *v38; // rcx
  int v40; // r8d
  int v41; // edi
  int v42; // r13d
  int v43; // r8d
  DWORD v44; // eax
  unsigned int v45; // r10d
  int v46; // r8d
  PDWORD ReturnLength; // [rsp+20h] [rbp-30h]
  __int64 v48; // [rsp+30h] [rbp-20h]
  __int64 v49; // [rsp+40h] [rbp-10h]
  PSID TokenInformation; // [rsp+50h] [rbp+0h] BYREF
  int v51; // [rsp+58h] [rbp+8h]
  void *TokenHandle; // [rsp+60h] [rbp+10h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+18h] BYREF

  v8 = a3;
  v51 = a4;
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
    LODWORD(ReturnLength) = v13;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      "ComplexPingInternal",
      3612,
      ReturnLength,
      L"ComplexPingInternal SetID:%I64X, sequence:%d, AddToSet:%d DelFromSet:%d",
      *a2,
      v8,
      a4,
      a5);
  }
  if ( !*a2 )
  {
    v18 = 0;
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
        v20 = gpPingSetQuotaManager;
        CSharedLock::LockShared(*((LPCRITICAL_SECTION *)gpPingSetQuotaManager + 2));
        for ( i = *(CUserPingSetCount **)v20; ; i = *(CUserPingSetCount **)i )
        {
          if ( !i )
            goto LABEL_49;
          if ( (unsigned int)CUserPingSetCount::IsEqual(i, v18) )
            break;
        }
        if ( *((_DWORD *)i + 6) < CPingSetQuotaManager::_dwPerUserPingSetQuota )
        {
LABEL_49:
          v31 = 0;
          goto LABEL_50;
        }
        v31 = 1;
LABEL_50:
        CSharedLock::UnlockShared(*((CSharedLock **)v20 + 2));
        if ( v31 )
        {
          if ( v18 )
          {
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
              ComTraceMessageT<void *>(
                v33,
                (unsigned int)"ComplexPingInternal",
                3739,
                v34,
                (__int64)L"Ping Quota exceeded SID:%!sid!",
                v18);
          }
          else if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
          {
            ComTraceMessageT<unsigned short const *>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
              (unsigned int)"ComplexPingInternal",
              3743,
              v35,
              (__int64)L"Ping Quota exceeded SID:%ws",
              L"Anonymous");
          }
          LastError = 1721;
        }
        else
        {
          if ( CPingSetQuotaManager::ManageQuotaForUser(v32, v18, 1) )
          {
            v37 = WORD2(TokenInformation);
            v15 = CServerSetTable::Allocate(v36, WORD2(TokenInformation), v18, a2);
            if ( v15 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
              {
                LODWORD(ReturnLength) = v40;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                  "ComplexPingInternal",
                  3769,
                  ReturnLength,
                  L"Allocated server set for remote client SetID:%I64X SID:%!sid!",
                  *a2,
                  v18);
              }
              goto LABEL_74;
            }
            CPingSetQuotaManager::ManageQuotaForUser(v38, v18, 0);
          }
          LastError = 14;
        }
LABEL_65:
        if ( v18 )
          operator delete(v18, 0);
        goto LABEL_67;
      }
    }
    v22 = 24;
    LODWORD(TokenInformation) = 24;
    while ( 1 )
    {
      v23 = v22 + 15LL;
      if ( v23 <= v22 )
        v23 = 0xFFFFFFFFFFFFFF0LL;
      v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
      v25 = alloca(v24);
      v26 = alloca(v24);
      if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, v22, (PDWORD)&TokenInformation) )
        break;
      if ( GetLastError() != 122 )
        goto LABEL_40;
      v22 = (unsigned int)TokenInformation;
    }
    v28 = (void *)operator new(12, v27, (unsigned int)TokenInformation - 12LL);
    v18 = v28;
    if ( v28 )
    {
      CopySid((DWORD)TokenInformation, v28, TokenInformation);
      goto LABEL_41;
    }
LABEL_40:
    LastError = 14;
LABEL_41:
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<void *>(
        v29,
        (unsigned int)"ComplexPingInternal",
        3726,
        v30,
        (__int64)L"New remote client started pinging securely SID:%!sid!",
        v18);
    CloseHandle(TokenHandle);
    if ( LastError )
      goto LABEL_65;
    goto LABEL_30;
  }
  v14 = CServerSetTable::Lookup(gpServerSetTable, *a2);
  v15 = v14;
  if ( !v14 )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      ComTraceMessageT<unsigned short const *>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (unsigned int)"ComplexPingInternal",
        3620,
        0,
        (__int64)L"Invalid SetID:%I64X",
        *a2);
    LastError = 1912;
LABEL_67:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return LastError;
  }
  LastError = 0;
  if ( CServerSet::CheckSecurity(v14, a1) != 1 )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v17 = *a2;
      LODWORD(v48) = GetLastError();
      LODWORD(ReturnLength) = 0;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        "ComplexPingInternal",
        3634,
        ReturnLength,
        L"Security failure %!WINERROR! SetID:%I64X",
        v48,
        v17);
    }
    LastError = 5;
    goto LABEL_67;
  }
  v37 = WORD2(TokenInformation);
LABEL_74:
  if ( !(unsigned int)CServerSet::CheckAndUpdateSequenceNumber(v15, v37) )
    goto LABEL_67;
  v41 = 0;
  LODWORD(TokenInformation) = 0;
  CServerSet::Ping(v15);
  *a8 = 0;
  if ( v51 )
  {
    v42 = v51;
    do
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (unsigned int)"ComplexPingInternal",
          3805,
          v43,
          (__int64)L"Adding to set OID:%I64X SetID:%I64X",
          a6[v42 - 1],
          *a2);
      v44 = CServerSet::AddObject(v15, a6[--v42]);
      v45 = 1911;
      LastError = v44;
      if ( v44 == 1911 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
        {
          LODWORD(v49) = v45;
          LODWORD(ReturnLength) = 1;
          ComTraceMessage(
            v45,
            "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            "ComplexPingInternal",
            3810,
            ReturnLength,
            L"Adding to set OID:%I64X SetID:%I64X %!WINERROR!",
            a6[v42],
            *a2,
            v49);
        }
        v41 = 1;
      }
      else if ( v44 )
      {
        break;
      }
    }
    while ( v42 );
    v12 = a5;
    LODWORD(TokenInformation) = v41;
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
          v46,
          (__int64)L"Removing from set OID:%I64X SetID:%I64X",
          a7[v12 - 1],
          *a2);
      CServerSet::RemoveObject(v15, &a7[--v12]);
    }
    while ( v12 );
    v41 = (int)TokenInformation;
  }
  if ( LastError || !v41 )
    goto LABEL_67;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1911;
}

```

## disassembly

```asm
0x1800c77cc  push    rbp
0x1800c77ce  push    rbx
0x1800c77cf  push    rsi
0x1800c77d0  push    rdi
0x1800c77d1  push    r12
0x1800c77d3  push    r13
0x1800c77d5  push    r14
0x1800c77d7  push    r15
0x1800c77d9  sub     rsp, 88h
0x1800c77e0  lea     rbp, [rsp+50h]
0x1800c77e5  mov     rax, cs:__security_cookie
0x1800c77ec  xor     rax, rbp
0x1800c77ef  mov     [rbp+70h+var_50], rax
0x1800c77f3  movzx   esi, r8w
0x1800c77f7  mov     ebx, r9d
0x1800c77fa  mov     [rbp+70h+var_68], ebx
0x1800c77fd  mov     r14, rdx
0x1800c7800  mov     [rbp+70h+var_6C], si
0x1800c7804  mov     r15, rcx
0x1800c7807  test    rdx, rdx
0x1800c780a  jz      loc_1800C7EF1
0x1800c7810  test    ebx, ebx
0x1800c7812  jz      short loc_1800C7822
0x1800c7814  cmp     [rbp+70h+arg_28], 0
0x1800c781c  jz      loc_1800C7EF1
0x1800c7822  mov     r13d, [rbp+70h+arg_20]
0x1800c7829  test    r13d, r13d
0x1800c782c  jz      short loc_1800C783C
0x1800c782e  cmp     [rbp+70h+arg_30], 0
0x1800c7836  jz      loc_1800C7EF1
0x1800c783c  cmp     [rbp+70h+arg_38], 0
0x1800c7844  jz      loc_1800C7EF1
0x1800c784a  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800c7851  lea     rcx, [rbp+70h+SRWLock]
0x1800c7855  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800c785a  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c7861  lea     rdi, aComplexpingint_0; "ComplexPingInternal"
0x1800c7868  jz      short loc_1800C78BA
0x1800c786a  mov     r8d, 4
0x1800c7870  mov     ecx, r8d
0x1800c7873  call    IsWppLevelEnabled
0x1800c7878  test    al, al
0x1800c787a  jz      short loc_1800C78BA
0x1800c787c  mov     rax, [r14]
0x1800c787f  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c7886  mov     [rsp+0C0h+var_78], r13d
0x1800c788b  mov     r9d, 0E1Ch
0x1800c7891  mov     dword ptr [rsp+0C0h+var_80], ebx
0x1800c7895  or      ecx, 0FFFFFFFFh
0x1800c7898  mov     dword ptr [rsp+0C0h+var_88], esi
0x1800c789c  mov     [rsp+0C0h+var_90], rax
0x1800c78a1  lea     rax, aComplexpingint; "ComplexPingInternal SetID:%I64X, sequen"...
0x1800c78a8  mov     [rsp+0C0h+var_98], rax
0x1800c78ad  mov     dword ptr [rsp+0C0h+ReturnLength], r8d
0x1800c78b2  mov     r8, rdi
0x1800c78b5  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c78ba  mov     rdx, [r14]; unsigned __int64
0x1800c78bd  test    rdx, rdx
0x1800c78c0  jz      loc_1800C79B2
0x1800c78c6  mov     rcx, cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA; this
0x1800c78cd  call    ?Lookup@CServerSetTable@@QEAAPEAVCServerSet@@_K@Z; CServerSetTable::Lookup(unsigned __int64)
0x1800c78d2  mov     rsi, rax
0x1800c78d5  test    rax, rax
0x1800c78d8  jnz     short loc_1800C792D
0x1800c78da  mov     eax, cs:dword_1801574B8
0x1800c78e0  test    eax, eax
0x1800c78e2  jnz     short loc_1800C78F7
0x1800c78e4  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800c78ea  jz      short loc_1800C7923
0x1800c78ec  xor     ecx, ecx
0x1800c78ee  call    IsWppLevelEnabled
0x1800c78f3  test    al, al
0x1800c78f5  jz      short loc_1800C7923
0x1800c78f7  mov     rax, [r14]
0x1800c78fa  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c7901  mov     [rsp+0C0h+var_98], rax
0x1800c7906  xor     r9d, r9d
0x1800c7909  lea     rax, aInvalidSetidI6; "Invalid SetID:%I64X"
0x1800c7910  mov     r8d, 0E24h
0x1800c7916  mov     rdx, rdi
0x1800c7919  mov     [rsp+0C0h+ReturnLength], rax
0x1800c791e  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800c7923  mov     ebx, 778h
0x1800c7928  jmp     loc_1800C7C92
0x1800c792d  mov     rdx, r15; void *
0x1800c7930  mov     rcx, rax; this
0x1800c7933  xor     ebx, ebx
0x1800c7935  call    ?CheckSecurity@CServerSet@@QEAAHPEAX@Z; CServerSet::CheckSecurity(void *)
0x1800c793a  lea     r12d, [rbx+1]
0x1800c793e  cmp     eax, r12d
0x1800c7941  jz      loc_1800C7D05
0x1800c7947  mov     eax, cs:dword_1801574B8
0x1800c794d  test    eax, eax
0x1800c794f  jnz     short loc_1800C7964
0x1800c7951  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800c7957  jz      short loc_1800C79A8
0x1800c7959  xor     ecx, ecx
0x1800c795b  call    IsWppLevelEnabled
0x1800c7960  test    al, al
0x1800c7962  jz      short loc_1800C79A8
0x1800c7964  mov     rbx, [r14]
0x1800c7967  call    cs:__imp_GetLastError
0x1800c796e  nop     dword ptr [rax+rax+00h]
0x1800c7973  mov     [rsp+0C0h+var_88], rbx
0x1800c7978  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c797f  mov     dword ptr [rsp+0C0h+var_90], eax
0x1800c7983  mov     r9d, 0E32h
0x1800c7989  lea     rax, aSecurityFailur; "Security failure %!WINERROR! SetID:%I64"...
0x1800c7990  mov     r8, rdi
0x1800c7993  mov     [rsp+0C0h+var_98], rax
0x1800c7998  or      ecx, 0FFFFFFFFh
0x1800c799b  mov     dword ptr [rsp+0C0h+ReturnLength], 0
0x1800c79a3  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800c79a8  mov     ebx, 5
0x1800c79ad  jmp     loc_1800C7C92
0x1800c79b2  xor     edi, edi
0x1800c79b4  mov     rcx, r15; BindingHandle
0x1800c79b7  mov     [rbp+70h+TokenHandle], rdi
0x1800c79bb  call    cs:__imp_RpcImpersonateClient
0x1800c79c2  nop     dword ptr [rax+rax+00h]
0x1800c79c7  lea     r15d, [rdi+0Eh]
0x1800c79cb  lea     r12d, [rdi+1]
0x1800c79cf  test    eax, eax
0x1800c79d1  jnz     short loc_1800C7A0E
0x1800c79d3  call    cs:__imp_GetCurrentThread
0x1800c79da  nop     dword ptr [rax+rax+00h]
0x1800c79df  lea     r9, [rbp+70h+TokenHandle]; TokenHandle
0x1800c79e3  mov     r8d, r12d; OpenAsSelf
0x1800c79e6  mov     rcx, rax; ThreadHandle
0x1800c79e9  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800c79ec  call    cs:__imp_OpenThreadToken
0x1800c79f3  nop     dword ptr [rax+rax+00h]
0x1800c79f8  test    eax, eax
0x1800c79fa  jnz     short loc_1800C7A69
0x1800c79fc  call    cs:__imp_GetLastError
0x1800c7a03  nop     dword ptr [rax+rax+00h]
0x1800c7a08  mov     ebx, eax
0x1800c7a0a  test    eax, eax
0x1800c7a0c  jz      short loc_1800C7A6B
0x1800c7a0e  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800c7a14  jz      short loc_1800C7A4F
0x1800c7a16  mov     ecx, 3
0x1800c7a1b  call    IsWppLevelEnabled
0x1800c7a20  test    al, al
0x1800c7a22  jz      short loc_1800C7A4F
0x1800c7a24  lea     rax, aNewRemoteClien; "New remote client started pinging unsec"...
0x1800c7a2b  mov     r9d, 3
0x1800c7a31  mov     r8d, 0E5Eh
0x1800c7a37  mov     [rsp+0C0h+ReturnLength], rax
0x1800c7a3c  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c7a43  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c7a4a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800c7a4f  xor     ebx, ebx
0x1800c7a51  mov     r15, cs:?gpPingSetQuotaManager@@3PEAVCPingSetQuotaManager@@EA; CPingSetQuotaManager * gpPingSetQuotaManager
0x1800c7a58  mov     rcx, [r15+10h]; lpCriticalSection
0x1800c7a5c  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x1800c7a61  mov     rsi, [r15]
0x1800c7a64  jmp     loc_1800C7B7A
0x1800c7a69  xor     ebx, ebx
0x1800c7a6b  mov     r9d, 18h
0x1800c7a71  mov     [rbp+70h+TokenInformation], r9d
0x1800c7a75  mov     eax, r9d
0x1800c7a78  lea     rcx, [rax+0Fh]
0x1800c7a7c  cmp     rcx, rax
0x1800c7a7f  ja      short loc_1800C7A8B
0x1800c7a81  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c7a8b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c7a8f  mov     rax, rcx
0x1800c7a92  call    _alloca_probe
0x1800c7a97  sub     rsp, rcx
0x1800c7a9a  lea     rax, [rbp+70h+TokenInformation]
0x1800c7a9e  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x1800c7aa2  mov     edx, r12d; TokenInformationClass
0x1800c7aa5  lea     rsi, [rsp+0C0h+TokenInformation]
0x1800c7aaa  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800c7aaf  mov     r8, rsi; TokenInformation
0x1800c7ab2  call    cs:__imp_GetTokenInformation
0x1800c7ab9  nop     dword ptr [rax+rax+00h]
0x1800c7abe  test    eax, eax
0x1800c7ac0  jnz     short loc_1800C7AD9
0x1800c7ac2  call    cs:__imp_GetLastError
0x1800c7ac9  nop     dword ptr [rax+rax+00h]
0x1800c7ace  cmp     eax, 7Ah ; 'z'
0x1800c7ad1  jnz     short loc_1800C7B0A
0x1800c7ad3  mov     r9d, [rbp+70h+TokenInformation]
0x1800c7ad7  jmp     short loc_1800C7A75
0x1800c7ad9  mov     r8d, [rbp+70h+TokenInformation]
0x1800c7add  mov     ecx, 0Ch
0x1800c7ae2  sub     r8, 0Ch
0x1800c7ae6  call    ??2@YAPEAX_KVallocateExtra_t@@0@Z; operator new(unsigned __int64,allocateExtra_t,unsigned __int64)
0x1800c7aeb  mov     rdi, rax
0x1800c7aee  test    rax, rax
0x1800c7af1  jz      short loc_1800C7B0A
0x1800c7af3  mov     r8, [rsi]; pSourceSid
0x1800c7af6  mov     rdx, rax; pDestinationSid
0x1800c7af9  mov     ecx, [rbp+70h+TokenInformation]; nDestinationSidLength
0x1800c7afc  call    cs:__imp_CopySid
0x1800c7b03  nop     dword ptr [rax+rax+00h]
0x1800c7b08  jmp     short loc_1800C7B0D
0x1800c7b0a  mov     ebx, r15d
0x1800c7b0d  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c7b14  jz      short loc_1800C7B4B
0x1800c7b16  mov     r9d, 3
0x1800c7b1c  mov     ecx, r9d
0x1800c7b1f  call    IsWppLevelEnabled
0x1800c7b24  test    al, al
0x1800c7b26  jz      short loc_1800C7B4B
0x1800c7b28  lea     rax, aNewRemoteClien_0; "New remote client started pinging secur"...
0x1800c7b2f  mov     [rsp+0C0h+var_98], rdi
0x1800c7b34  mov     r8d, 0E8Eh
0x1800c7b3a  mov     [rsp+0C0h+ReturnLength], rax
0x1800c7b3f  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c7b46  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x1800c7b4b  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x1800c7b4f  call    cs:__imp_CloseHandle
0x1800c7b56  nop     dword ptr [rax+rax+00h]
0x1800c7b5b  test    ebx, ebx
0x1800c7b5d  jnz     loc_1800C7C83
0x1800c7b63  jmp     loc_1800C7A51
0x1800c7b68  mov     rdx, rdi; void *
0x1800c7b6b  mov     rcx, rsi; this
0x1800c7b6e  call    ?IsEqual@CUserPingSetCount@@QEAAHPEAX@Z; CUserPingSetCount::IsEqual(void *)
0x1800c7b73  test    eax, eax
0x1800c7b75  jnz     short loc_1800C7BE2
0x1800c7b77  mov     rsi, [rsi]
0x1800c7b7a  test    rsi, rsi
0x1800c7b7d  jnz     short loc_1800C7B68
0x1800c7b7f  xor     esi, esi
0x1800c7b81  mov     rcx, [r15+10h]; this
0x1800c7b85  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x1800c7b8a  test    esi, esi
0x1800c7b8c  jz      loc_1800C7C48
0x1800c7b92  test    rdi, rdi
0x1800c7b95  jz      short loc_1800C7BF2
0x1800c7b97  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c7b9e  jz      loc_1800C7C41
0x1800c7ba4  mov     r8d, 3
0x1800c7baa  mov     ecx, r8d
0x1800c7bad  call    IsWppLevelEnabled
0x1800c7bb2  test    al, al
0x1800c7bb4  jz      loc_1800C7C41
0x1800c7bba  lea     rax, aPingQuotaExcee_0; "Ping Quota exceeded SID:%!sid!"
0x1800c7bc1  mov     [rsp+0C0h+var_98], rdi
0x1800c7bc6  mov     r9d, r8d
0x1800c7bc9  mov     [rsp+0C0h+ReturnLength], rax
0x1800c7bce  mov     r8d, 0E9Bh
0x1800c7bd4  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c7bdb  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x1800c7be0  jmp     short loc_1800C7C41
0x1800c7be2  mov     eax, cs:?_dwPerUserPingSetQuota@CPingSetQuotaManager@@0KA; ulong CPingSetQuotaManager::_dwPerUserPingSetQuota
0x1800c7be8  cmp     [rsi+18h], eax
0x1800c7beb  jb      short loc_1800C7B7F
0x1800c7bed  mov     esi, r12d
0x1800c7bf0  jmp     short loc_1800C7B81
0x1800c7bf2  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800c7bf9  jz      short loc_1800C7C41
0x1800c7bfb  mov     r8d, 3
0x1800c7c01  mov     ecx, r8d
0x1800c7c04  call    IsWppLevelEnabled
0x1800c7c09  test    al, al
0x1800c7c0b  jz      short loc_1800C7C41
0x1800c7c0d  lea     rax, aAnonymous; "Anonymous"
0x1800c7c14  mov     r9d, r8d
0x1800c7c17  mov     [rsp+0C0h+var_98], rax
0x1800c7c1c  lea     rdx, aComplexpingint_0; "ComplexPingInternal"
0x1800c7c23  lea     rax, aPingQuotaExcee; "Ping Quota exceeded SID:%ws"
0x1800c7c2a  mov     r8d, 0E9Fh
0x1800c7c30  lea     rcx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x1800c7c37  mov     [rsp+0C0h+ReturnLength], rax
0x1800c7c3c  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800c7c41  mov     ebx, 6B9h
0x1800c7c46  jmp     short loc_1800C7C83
0x1800c7c48  mov     r8d, r12d; int
0x1800c7c4b  mov     rdx, rdi; void *
0x1800c7c4e  call    ?ManageQuotaForUser@CPingSetQuotaManager@@QEAAHPEAXH@Z; CPingSetQuotaManager::ManageQuotaForUser(void *,int)
0x1800c7c53  test    eax, eax
0x1800c7c55  jz      short loc_1800C7C7E
0x1800c7c57  movzx   r15d, [rbp+70h+var_6C]
0x1800c7c5c  mov     r9, r14; unsigned __int64 *
0x1800c7c5f  movzx   edx, r15w; unsigned __int16
0x1800c7c63  mov     r8, rdi; void *
0x1800c7c66  call    ?Allocate@CServerSetTable@@QEAAPEAVCServerSet@@GPEAXAEA_K@Z; CServerSetTable::Allocate(ushort,void *,unsigned __int64 &)
0x1800c7c6b  mov     rsi, rax
0x1800c7c6e  test    rax, rax
0x1800c7c71  jnz     short loc_1800C7CAE
0x1800c7c73  xor     r8d, r8d; int
0x1800c7c76  mov     rdx, rdi; void *
0x1800c7c79  call    ?ManageQuotaForUser@CPingSetQuotaManager@@QEAAHPEAXH@Z; CPingSetQuotaManager::ManageQuotaForUser(void *,int)
0x1800c7c7e  mov     ebx, 0Eh
0x1800c7c83  test    rdi, rdi
0x1800c7c86  jz      short loc_1800C7C92
0x1800c7c88  xor     edx, edx; unsigned __int64
0x1800c7c8a  mov     rcx, rdi; void *
0x1800c7c8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c7c92  mov     rcx, [rbp+70h+SRWLock]; SRWLock
0x1800c7c96  test    rcx, rcx
0x1800c7c99  jz      short loc_1800C7CA7
0x1800c7c9b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c7ca2  nop     dword ptr [rax+rax+00h]
0x1800c7ca7  mov     eax, ebx
  ... truncated ...
```
