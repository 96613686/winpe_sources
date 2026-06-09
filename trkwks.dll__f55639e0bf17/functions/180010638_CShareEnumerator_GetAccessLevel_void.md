# CShareEnumerator::_GetAccessLevel(void)

- ea: `0x180010638`
- end: `0x180010c7f`
- name: `?_GetAccessLevel@CShareEnumerator@@AEAA?AW4enumAccessLevels@PShareMerit@@XZ`
- size: `1607`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800103b0`

## callees

- `0x18000ada0`
- `0x18000aec4`
- `0x18000afcc`
- `0x18000b060`
- `0x18000c87c`
- `0x18000d020`
- `0x18000d038`
- `0x18000d1d0`
- `0x18000d228`
- `0x18000d440`
- `0x18000d594`
- `0x18000dae8`
- `0x18000db28`
- `0x180010498`
- `0x180010638`
- `0x180010c88`
- `0x180011000`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180010a68`
- `RPCRT4!RpcRevertToSelf` at `0x180011d2c`
- `RPCRT4!RpcRevertToSelf` at `0x180010a68`
- `RPCRT4!RpcRevertToSelf` at `0x180011d2c`
- `RPCRT4!RpcImpersonateClient` at `0x1800107d2`
- `RPCRT4!RpcImpersonateClient` at `0x1800107d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d16`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010a70`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011d34`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010a70`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011d34`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800107e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800107e8`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b14`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b2e`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b48`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b62`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b14`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b2e`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b48`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180010b62`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010abe`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010abe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010859`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800108cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010859`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800108cf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180010a2f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180010a2f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180010a48`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180010a48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010818`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107ff`

## pseudocode

```c
__int64 __fastcall CShareEnumerator::_GetAccessLevel(__int64 a1)
{
  int v2; // ebx
  DWORD v3; // esi
  PSID *v4; // r12
  PSID *v5; // r14
  struct _PRIVILEGE_SET *v6; // r13
  RPC_STATUS v8; // eax
  HANDLE CurrentThread; // rax
  int v10; // ebx
  DWORD v11; // esi
  __int64 v12; // rdx
  __int64 v13; // r8
  void *v14; // rsi
  int i; // ebx
  unsigned int v16; // ebx
  DWORD GrantedAccess; // [rsp+64h] [rbp-BF4h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-BF0h] BYREF
  int v19; // [rsp+6Ch] [rbp-BECh]
  void *TokenHandle; // [rsp+70h] [rbp-BE8h] BYREF
  WINBOOL AccessStatus; // [rsp+78h] [rbp-BE0h] BYREF
  DWORD PrivilegeSetLength; // [rsp+7Ch] [rbp-BDCh] BYREF
  int v23; // [rsp+80h] [rbp-BD8h]
  void *Block; // [rsp+88h] [rbp-BD0h] BYREF
  DWORD v25; // [rsp+90h] [rbp-BC8h]
  unsigned int v26; // [rsp+94h] [rbp-BC4h] BYREF
  unsigned int v27; // [rsp+98h] [rbp-BC0h] BYREF
  unsigned int v28; // [rsp+9Ch] [rbp-BBCh] BYREF
  unsigned int v29; // [rsp+A0h] [rbp-BB8h] BYREF
  unsigned int v30; // [rsp+A4h] [rbp-BB4h] BYREF
  void *v31; // [rsp+A8h] [rbp-BB0h] BYREF
  void *v32; // [rsp+B0h] [rbp-BA8h] BYREF
  struct _ACL *v33; // [rsp+B8h] [rbp-BA0h] BYREF
  struct _ACL *v34; // [rsp+C0h] [rbp-B98h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-B90h] BYREF
  struct _PRIVILEGE_SET *v36; // [rsp+D8h] [rbp-B80h]
  PSID *v37; // [rsp+E0h] [rbp-B78h]
  PSID *v38; // [rsp+E8h] [rbp-B70h]
  DWORD v39; // [rsp+F0h] [rbp-B68h]
  DWORD v40; // [rsp+F4h] [rbp-B64h]
  _BYTE v41[48]; // [rsp+F8h] [rbp-B60h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+128h] [rbp-B30h] BYREF
  _BYTE v43[208]; // [rsp+140h] [rbp-B18h] BYREF
  _BYTE v44[256]; // [rsp+210h] [rbp-A48h] BYREF
  _BYTE v45[256]; // [rsp+310h] [rbp-948h] BYREF
  _BYTE v46[256]; // [rsp+410h] [rbp-848h] BYREF
  _BYTE v47[256]; // [rsp+510h] [rbp-748h] BYREF
  _BYTE v48[256]; // [rsp+610h] [rbp-648h] BYREF
  _BYTE v49[256]; // [rsp+710h] [rbp-548h] BYREF
  _BYTE v50[1024]; // [rsp+810h] [rbp-448h] BYREF

  v2 = 0;
  TokenHandle = 0;
  v23 = 0;
  ReturnLength = 0;
  v19 = 0;
  v3 = 256;
  v4 = (PSID *)v44;
  v37 = (PSID *)v44;
  v5 = (PSID *)v50;
  v38 = (PSID *)v50;
  v30 = 256;
  Block = v45;
  v29 = 256;
  v33 = (struct _ACL *)v46;
  v28 = 256;
  v34 = (struct _ACL *)v47;
  v27 = 256;
  v31 = v48;
  v26 = 256;
  v32 = v49;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  PrivilegeSetLength = 200;
  v6 = (struct _PRIVILEGE_SET *)v43;
  v36 = (struct _PRIVILEGE_SET *)v43;
  GrantedAccess = 0;
  AccessStatus = 0;
  v35 = 0;
  CSecDescriptor::CSecDescriptor((CSecDescriptor *)v41);
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 56) + 72LL * *(unsigned int *)(a1 + 48) + 64)
    || (unsigned int)CShareEnumerator::_IsAdminShare((CShareEnumerator *)a1) )
  {
    if ( (unsigned int)CTrkRpcConfig::RpcSecurityEnabled() )
    {
      v8 = RpcImpersonateClient(*(RPC_BINDING_HANDLE *)(a1 + 600));
      if ( v8 )
        TrkRaiseWin32Error(v8);
    }
    else if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      TrkRaiseLastError();
    }
    v19 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
      TrkRaiseLastError();
    v23 = 1;
    while ( v2 < 2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v4, v3, &ReturnLength) )
      {
        if ( v2 > 0 || GetLastError() != 122 )
          TrkRaiseLastError();
        v3 = ReturnLength;
        v39 = ReturnLength;
        v4 = (PSID *)operator new(ReturnLength);
        v37 = v4;
        if ( !v4 )
          TrkRaiseWin32Error(8);
      }
      ++v2;
    }
    v10 = 0;
    v11 = 1024;
    while ( v10 < 2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenGroups, v5, v11, &ReturnLength) )
      {
        if ( v10 > 0 || GetLastError() != 122 )
          TrkRaiseLastError();
        v25 = ReturnLength;
        v40 = ReturnLength;
        v5 = (PSID *)operator new(ReturnLength);
        v38 = v5;
        if ( !v5 )
          TrkRaiseWin32Error(8);
        v11 = v25;
      }
      ++v10;
    }
    if ( (unsigned int)CShareEnumerator::_IsAdminShare((CShareEnumerator *)a1) )
    {
      LOBYTE(v13) = 2;
      CSID::Initialize(&v35, v12, v13, 32, 544);
      CSecDescriptor::Initialize((CSecDescriptor *)v41);
      CSecDescriptor::AddAce(v41);
      v14 = (void *)CSecDescriptor::operator void * const((__int64)v41);
    }
    else
    {
      CShareEnumerator::_AbsoluteSDHelper(
        (CShareEnumerator *)(9LL * *(unsigned int *)(a1 + 48)),
        *(void *const *)(*(_QWORD *)(a1 + 56) + 72LL * *(unsigned int *)(a1 + 48) + 64),
        &Block,
        &v30,
        &v33,
        &v29,
        &v34,
        &v28,
        &v31,
        &v27,
        &v32,
        &v26);
      v14 = Block;
    }
    if ( !SetSecurityDescriptorOwner(v14, *v4, 0) )
      TrkRaiseLastError();
    if ( !SetSecurityDescriptorGroup(v14, v5[1], 0) )
      TrkRaiseLastError();
    v19 = 0;
    if ( (unsigned int)CTrkRpcConfig::RpcSecurityEnabled() )
      RpcRevertToSelf();
    else
      RevertToSelf();
    for ( i = 0; i < 2; ++i )
    {
      if ( !AccessCheck(
              v14,
              TokenHandle,
              0x2000000u,
              &GenericMapping,
              v6,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus)
        || !AccessStatus )
      {
        if ( i > 0 || GetLastError() != 122 )
          TrkRaiseLastError();
        v6 = (struct _PRIVILEGE_SET *)operator new(PrivilegeSetLength);
        v36 = v6;
        if ( !v6 )
          TrkRaiseWin32Error(8);
      }
    }
    if ( AreAllAccessesGranted(GrantedAccess, 0x1F01FFu) )
    {
      v16 = 393216;
    }
    else if ( AreAllAccessesGranted(GrantedAccess, 0x12019Fu) )
    {
      v16 = 327680;
    }
    else if ( AreAllAccessesGranted(GrantedAccess, 0x120089u) )
    {
      v16 = 0x40000;
    }
    else
    {
      v16 = AreAllAccessesGranted(GrantedAccess, 0x120116u) ? 196608 : 0x20000;
    }
    CSecDescriptor::UnInitialize((CSecDescriptor *)v41);
    CSID::UnInitialize((CSID *)&v35);
    CloseHandle(TokenHandle);
    if ( v43 != (_BYTE *)v6 )
      operator delete(v6);
    if ( v44 != (_BYTE *)v4 )
      operator delete(v4);
    if ( v50 != (_BYTE *)v5 )
      operator delete(v5);
    if ( v45 != Block )
      operator delete(Block);
    if ( v46 != (_BYTE *)v33 )
      operator delete(v33);
    if ( v47 != (_BYTE *)v34 )
      operator delete(v34);
    if ( v48 != v31 )
      operator delete(v31);
    if ( v49 != v32 )
      operator delete(v32);
    CSecDescriptor::~CSecDescriptor((CSecDescriptor *)v41);
    CSID::UnInitialize((CSID *)&v35);
    return v16;
  }
  else
  {
    CSecDescriptor::~CSecDescriptor((CSecDescriptor *)v41);
    CSID::UnInitialize((CSID *)&v35);
    return 393216;
  }
}

```

## disassembly

```asm
0x180010638  mov     r11, rsp
0x18001063b  push    rbx
0x18001063c  push    rsi
0x18001063d  push    r12
0x18001063f  push    r13
0x180010641  push    r14
0x180010643  push    r15
0x180010645  sub     rsp, 0C28h
0x18001064c  mov     rax, cs:__security_cookie
0x180010653  xor     rax, rsp
0x180010656  mov     [rsp+0C58h+var_48], rax
0x18001065e  mov     r15, rcx
0x180010661  xor     ebx, ebx
0x180010663  mov     [rsp+0C58h+TokenHandle], rbx
0x180010668  mov     [rsp+0C58h+var_BD8], ebx
0x18001066f  mov     [rsp+0C58h+var_BF0], ebx
0x180010673  mov     [rsp+0C58h+var_BEC], ebx
0x180010677  mov     esi, 100h
0x18001067c  lea     r12, [r11-0A48h]
0x180010683  mov     [r11-0B78h], r12
0x18001068a  lea     r14, [r11-448h]
0x180010691  mov     [r11-0B70h], r14
0x180010698  mov     [rsp+0C58h+var_BB4], esi
0x18001069f  lea     rax, [r11-948h]
0x1800106a6  mov     [r11-0BD0h], rax
0x1800106ad  mov     [rsp+0C58h+var_BB8], esi
0x1800106b4  lea     rax, [r11-848h]
0x1800106bb  mov     [r11-0BA0h], rax
0x1800106c2  mov     [rsp+0C58h+var_BBC], esi
0x1800106c9  lea     rax, [r11-748h]
0x1800106d0  mov     [r11-0B98h], rax
0x1800106d7  mov     [rsp+0C58h+var_BC0], esi
0x1800106de  lea     rax, [r11-648h]
0x1800106e5  mov     [r11-0BB0h], rax
0x1800106ec  mov     [rsp+0C58h+var_BC4], esi
0x1800106f3  lea     rax, [r11-548h]
0x1800106fa  mov     [r11-0BA8h], rax
0x180010701  mov     [rsp+0C58h+GenericMapping.GenericRead], 120089h
0x18001070c  mov     [rsp+0C58h+GenericMapping.GenericWrite], 120116h
0x180010717  mov     [rsp+0C58h+GenericMapping.GenericExecute], 1200A0h
0x180010722  mov     [rsp+0C58h+GenericMapping.GenericAll], 1F01FFh
0x18001072d  mov     [rsp+0C58h+var_BDC], 0C8h
0x180010735  lea     r13, [r11-0B18h]
0x18001073c  mov     [r11-0B80h], r13
0x180010743  mov     [rsp+0C58h+var_BF4], ebx
0x180010747  mov     [rsp+0C58h+var_BE0], ebx
0x18001074b  xorps   xmm0, xmm0
0x18001074e  movups  [rsp+0C58h+var_B90], xmm0
0x180010756  lea     rcx, [r11-0B60h]; this
0x18001075d  call    ??0CSecDescriptor@@QEAA@XZ; CSecDescriptor::CSecDescriptor(void)
0x180010762  mov     eax, [r15+30h]
0x180010766  lea     rcx, [rax+rax*8]
0x18001076a  mov     rax, [r15+38h]
0x18001076e  cmp     [rax+rcx*8+40h], rbx
0x180010773  jnz     short loc_1800107C2
0x180010775  mov     rcx, r15; this
0x180010778  call    ?_IsAdminShare@CShareEnumerator@@AEAAHXZ; CShareEnumerator::_IsAdminShare(void)
0x18001077d  test    eax, eax
0x18001077f  jnz     short loc_1800107C2
0x180010781  lea     rcx, [rsp+0C58h+var_B60]; this
0x180010789  call    ??1CSecDescriptor@@QEAA@XZ; CSecDescriptor::~CSecDescriptor(void)
0x18001078e  lea     rcx, [rsp+0C58h+var_B90]; this
0x180010796  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x18001079b  mov     eax, 60000h
0x1800107a0  mov     rcx, [rsp+0C58h+var_48]
0x1800107a8  xor     rcx, rsp; StackCookie
0x1800107ab  call    __security_check_cookie
0x1800107b0  add     rsp, 0C28h
0x1800107b7  pop     r15
0x1800107b9  pop     r14
0x1800107bb  pop     r13
0x1800107bd  pop     r12
0x1800107bf  pop     rsi
0x1800107c0  pop     rbx
0x1800107c1  retn
0x1800107c2  call    ?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ; CTrkRpcConfig::RpcSecurityEnabled(void)
0x1800107c7  test    eax, eax
0x1800107c9  jz      short loc_1800107E3
0x1800107cb  mov     rcx, [r15+258h]; BindingHandle
0x1800107d2  call    cs:__imp_RpcImpersonateClient
0x1800107d8  test    eax, eax
0x1800107da  jz      short loc_1800107F7
0x1800107dc  mov     ecx, eax; int
0x1800107de  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x1800107e3  mov     ecx, 2; ImpersonationLevel
0x1800107e8  call    cs:__imp_ImpersonateSelf
0x1800107ee  test    eax, eax
0x1800107f0  jnz     short loc_1800107F7
0x1800107f2  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x1800107f7  mov     [rsp+0C58h+var_BEC], 1
0x1800107ff  call    cs:__imp_GetCurrentThread
0x180010805  mov     rcx, rax; ThreadHandle
0x180010808  lea     r9, [rsp+0C58h+TokenHandle]; TokenHandle
0x18001080d  mov     edx, 20008h; DesiredAccess
0x180010812  mov     r8d, 1; OpenAsSelf
0x180010818  call    cs:__imp_OpenThreadToken
0x18001081e  test    eax, eax
0x180010820  jnz     short loc_180010827
0x180010822  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180010827  mov     [rsp+0C58h+var_BD8], 1
0x180010832  mov     [rsp+0C58h+var_BF8], ebx
0x180010836  mov     [rsp+0C58h+var_BF8], ebx
0x18001083a  cmp     ebx, 2
0x18001083d  jge     short loc_1800108A5
0x18001083f  lea     rax, [rsp+0C58h+var_BF0]
0x180010844  mov     [rsp+0C58h+ReturnLength], rax; ReturnLength
0x180010849  mov     r9d, esi; TokenInformationLength
0x18001084c  mov     r8, r12; TokenInformation
0x18001084f  mov     edx, 1; TokenInformationClass
0x180010854  mov     rcx, [rsp+0C58h+TokenHandle]; TokenHandle
0x180010859  call    cs:__imp_GetTokenInformation
0x18001085f  test    eax, eax
0x180010861  jnz     short loc_1800108A1
0x180010863  test    ebx, ebx
0x180010865  jg      short loc_18001089C
0x180010867  call    cs:__imp_GetLastError
0x18001086d  cmp     eax, 7Ah ; 'z'
0x180010870  jnz     short loc_18001089C
0x180010872  mov     esi, [rsp+0C58h+var_BF0]
0x180010876  mov     [rsp+0C58h+var_B68], esi
0x18001087d  mov     ecx, esi; Size
0x18001087f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010884  mov     r12, rax
0x180010887  mov     [rsp+0C58h+var_B78], rax
0x18001088f  test    rax, rax
0x180010892  jnz     short loc_1800108A1
0x180010894  lea     ecx, [rax+8]; int
0x180010897  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18001089c  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x1800108a1  inc     ebx
0x1800108a3  jmp     short loc_180010836
0x1800108a5  xor     ebx, ebx
0x1800108a7  mov     esi, 400h
0x1800108ac  mov     [rsp+0C58h+var_BF8], ebx
0x1800108b0  cmp     ebx, 2
0x1800108b3  jge     short loc_180010929
0x1800108b5  lea     rax, [rsp+0C58h+var_BF0]
0x1800108ba  mov     [rsp+0C58h+ReturnLength], rax; ReturnLength
0x1800108bf  mov     r9d, esi; TokenInformationLength
0x1800108c2  mov     r8, r14; TokenInformation
0x1800108c5  mov     edx, 2; TokenInformationClass
0x1800108ca  mov     rcx, [rsp+0C58h+TokenHandle]; TokenHandle
0x1800108cf  call    cs:__imp_GetTokenInformation
0x1800108d5  test    eax, eax
0x1800108d7  jnz     short loc_180010925
0x1800108d9  test    ebx, ebx
0x1800108db  jg      short loc_180010919
0x1800108dd  call    cs:__imp_GetLastError
0x1800108e3  cmp     eax, 7Ah ; 'z'
0x1800108e6  jnz     short loc_180010919
0x1800108e8  mov     eax, [rsp+0C58h+var_BF0]
0x1800108ec  mov     [rsp+0C58h+var_BC8], eax
0x1800108f3  mov     [rsp+0C58h+var_B64], eax
0x1800108fa  mov     ecx, eax; Size
0x1800108fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010901  mov     r14, rax
0x180010904  mov     [rsp+0C58h+var_B70], rax
0x18001090c  test    rax, rax
0x18001090f  jnz     short loc_18001091E
0x180010911  lea     ecx, [rax+8]; int
0x180010914  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180010919  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x18001091e  mov     esi, [rsp+0C58h+var_BC8]
0x180010925  inc     ebx
0x180010927  jmp     short loc_1800108AC
0x180010929  mov     rcx, r15; this
0x18001092c  call    ?_IsAdminShare@CShareEnumerator@@AEAAHXZ; CShareEnumerator::_IsAdminShare(void)
0x180010931  test    eax, eax
0x180010933  jz      short loc_18001098F
0x180010935  mov     dword ptr [rsp+0C58h+ReturnLength], 220h
0x18001093d  mov     r9d, 20h ; ' '
0x180010943  mov     r8b, 2
0x180010946  lea     rcx, [rsp+0C58h+var_B90]
0x18001094e  call    ?Initialize@CSID@@QEAAXW4enumCSIDAuthority@1@EKKKKKKKK@Z; CSID::Initialize(CSID::enumCSIDAuthority,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong)
0x180010953  lea     rcx, [rsp+0C58h+var_B60]; this
0x18001095b  call    ?Initialize@CSecDescriptor@@QEAAXXZ; CSecDescriptor::Initialize(void)
0x180010960  mov     rax, qword ptr [rsp+0C58h+var_B90+8]
0x180010968  mov     [rsp+0C58h+ReturnLength], rax
0x18001096d  lea     rcx, [rsp+0C58h+var_B60]
0x180010975  call    ?AddAce@CSecDescriptor@@QEAAXW4enumAclType@1@W4enumAccessType@1@KQEAX@Z; CSecDescriptor::AddAce(CSecDescriptor::enumAclType,CSecDescriptor::enumAccessType,ulong,void * const)
0x18001097a  lea     rcx, [rsp+0C58h+var_B60]
0x180010982  call    ??BCSecDescriptor@@QEAAQEAXXZ; CSecDescriptor::operator void * const(void)
0x180010987  mov     rsi, rax
0x18001098a  jmp     loc_180010A25
0x18001098f  mov     eax, [r15+30h]
0x180010993  lea     rcx, [rax+rax*8]; this
0x180010997  mov     rdx, [r15+38h]
0x18001099b  lea     rax, [rsp+0C58h+var_BC4]
0x1800109a3  mov     [rsp+0C58h+var_C00], rax; unsigned int *
0x1800109a8  lea     rax, [rsp+0C58h+var_BA8]
0x1800109b0  mov     [rsp+0C58h+var_C08], rax; void **
0x1800109b5  lea     rax, [rsp+0C58h+var_BC0]
0x1800109bd  mov     [rsp+0C58h+var_C10], rax; unsigned int *
0x1800109c2  lea     rax, [rsp+0C58h+var_BB0]
0x1800109ca  mov     [rsp+0C58h+var_C18], rax; void **
0x1800109cf  lea     rax, [rsp+0C58h+var_BBC]
0x1800109d7  mov     [rsp+0C58h+AccessStatus], rax; unsigned int *
0x1800109dc  lea     rax, [rsp+0C58h+var_B98]
0x1800109e4  mov     [rsp+0C58h+GrantedAccess], rax; struct _ACL **
0x1800109e9  lea     rax, [rsp+0C58h+var_BB8]
0x1800109f1  mov     [rsp+0C58h+PrivilegeSetLength], rax; unsigned int *
0x1800109f6  lea     rax, [rsp+0C58h+var_BA0]
0x1800109fe  mov     [rsp+0C58h+ReturnLength], rax; struct _ACL **
0x180010a03  lea     r9, [rsp+0C58h+var_BB4]; unsigned int *
0x180010a0b  lea     r8, [rsp+0C58h+Block]; void **
0x180010a13  mov     rdx, [rdx+rcx*8+40h]; void *
0x180010a18  call    ?_AbsoluteSDHelper@CShareEnumerator@@AEAAXQEAXPEAPEAXPEAKPEAPEAU_ACL@@2321212@Z; CShareEnumerator::_AbsoluteSDHelper(void * const,void * *,ulong *,_ACL * *,ulong *,_ACL * *,ulong *,void * *,ulong *,void * *,ulong *)
0x180010a1d  mov     rsi, [rsp+0C58h+Block]
0x180010a25  xor     r8d, r8d; bOwnerDefaulted
0x180010a28  mov     rdx, [r12]; pOwner
0x180010a2c  mov     rcx, rsi; pSecurityDescriptor
0x180010a2f  call    cs:__imp_SetSecurityDescriptorOwner
0x180010a35  test    eax, eax
0x180010a37  jnz     short loc_180010A3E
0x180010a39  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180010a3e  xor     r8d, r8d; bGroupDefaulted
0x180010a41  mov     rdx, [r14+8]; pGroup
0x180010a45  mov     rcx, rsi; pSecurityDescriptor
0x180010a48  call    cs:__imp_SetSecurityDescriptorGroup
0x180010a4e  test    eax, eax
0x180010a50  jnz     short loc_180010A57
0x180010a52  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180010a57  mov     [rsp+0C58h+var_BEC], 0
0x180010a5f  call    ?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ; CTrkRpcConfig::RpcSecurityEnabled(void)
0x180010a64  test    eax, eax
0x180010a66  jz      short loc_180010A70
0x180010a68  call    cs:__imp_RpcRevertToSelf
0x180010a6e  jmp     short loc_180010A76
0x180010a70  call    cs:__imp_RevertToSelf
0x180010a76  xor     ebx, ebx
0x180010a78  mov     [rsp+0C58h+var_BF8], ebx
0x180010a7c  cmp     ebx, 2
0x180010a7f  jge     loc_180010B0B
0x180010a85  lea     rax, [rsp+0C58h+var_BE0]
0x180010a8a  mov     [rsp+0C58h+AccessStatus], rax; AccessStatus
0x180010a8f  lea     rax, [rsp+0C58h+var_BF4]
0x180010a94  mov     [rsp+0C58h+GrantedAccess], rax; GrantedAccess
0x180010a99  lea     rax, [rsp+0C58h+var_BDC]
0x180010a9e  mov     [rsp+0C58h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180010aa3  mov     [rsp+0C58h+ReturnLength], r13; PrivilegeSet
0x180010aa8  lea     r9, [rsp+0C58h+GenericMapping]; GenericMapping
0x180010ab0  mov     r8d, 2000000h; DesiredAccess
0x180010ab6  mov     rdx, [rsp+0C58h+TokenHandle]; ClientToken
0x180010abb  mov     rcx, rsi; pSecurityDescriptor
0x180010abe  call    cs:__imp_AccessCheck
0x180010ac4  test    eax, eax
0x180010ac6  jz      short loc_180010ACF
0x180010ac8  cmp     [rsp+0C58h+var_BE0], 0
0x180010acd  jnz     short loc_180010AFF
0x180010acf  test    ebx, ebx
0x180010ad1  jg      short loc_180010B06
0x180010ad3  call    cs:__imp_GetLastError
0x180010ad9  cmp     eax, 7Ah ; 'z'
0x180010adc  jnz     short loc_180010B06
0x180010ade  mov     ecx, [rsp+0C58h+var_BDC]; Size
0x180010ae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ae7  mov     r13, rax
0x180010aea  mov     [rsp+0C58h+var_B80], rax
0x180010af2  test    rax, rax
0x180010af5  jnz     short loc_180010AFF
0x180010af7  lea     ecx, [rax+8]; int
0x180010afa  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180010aff  inc     ebx
0x180010b01  jmp     loc_180010A78
0x180010b06  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180010b0b  mov     edx, 1F01FFh; DesiredAccess
0x180010b10  mov     ecx, [rsp+0C58h+var_BF4]; GrantedAccess
0x180010b14  call    cs:__imp_AreAllAccessesGranted
0x180010b1a  test    eax, eax
0x180010b1c  jz      short loc_180010B25
0x180010b1e  mov     ebx, 60000h
0x180010b23  jmp     short loc_180010B78
0x180010b25  mov     edx, 12019Fh; DesiredAccess
0x180010b2a  mov     ecx, [rsp+0C58h+var_BF4]; GrantedAccess
0x180010b2e  call    cs:__imp_AreAllAccessesGranted
0x180010b34  test    eax, eax
0x180010b36  jz      short loc_180010B3F
0x180010b38  mov     ebx, 50000h
0x180010b3d  jmp     short loc_180010B78
0x180010b3f  mov     edx, 120089h; DesiredAccess
0x180010b44  mov     ecx, [rsp+0C58h+var_BF4]; GrantedAccess
0x180010b48  call    cs:__imp_AreAllAccessesGranted
0x180010b4e  test    eax, eax
0x180010b50  jz      short loc_180010B59
0x180010b52  mov     ebx, 40000h
0x180010b57  jmp     short loc_180010B78
0x180010b59  mov     edx, 120116h; DesiredAccess
0x180010b5e  mov     ecx, [rsp+0C58h+var_BF4]; GrantedAccess
0x180010b62  call    cs:__imp_AreAllAccessesGranted
0x180010b68  neg     eax
0x180010b6a  sbb     ebx, ebx
0x180010b6c  and     ebx, 10000h
0x180010b72  add     ebx, 20000h
0x180010b78  lea     rcx, [rsp+0C58h+var_B60]; this
0x180010b80  call    ?UnInitialize@CSecDescriptor@@QEAAXXZ; CSecDescriptor::UnInitialize(void)
0x180010b85  lea     rcx, [rsp+0C58h+var_B90]; this
0x180010b8d  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x180010b92  mov     rcx, [rsp+0C58h+TokenHandle]; hObject
0x180010b97  call    cs:__imp_CloseHandle
0x180010b9d  lea     rax, [rsp+0C58h+var_B18]
  ... truncated ...
```
