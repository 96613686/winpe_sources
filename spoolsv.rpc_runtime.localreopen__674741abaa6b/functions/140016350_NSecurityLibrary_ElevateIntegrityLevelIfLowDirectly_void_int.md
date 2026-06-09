# NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)

- ea: `0x140016350`
- end: `0x14001664c`
- name: `?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z`
- size: `764`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400043e0`
- `0x140005630`
- `0x1400065e0`
- `0x14000cfe0`

## callees

- `0x14000f4f0`
- `0x1400105c0`
- `0x140016350`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14005d2d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001659d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001659d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400165e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400165e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001658d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400165c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001658d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400165c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400163bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400163bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400163a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400163a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400165fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400165fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016615`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400164a0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400164a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016407`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016407`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14001654a`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14001654a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14001648c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14001648c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400164e9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400164e9`
- `KERNELBASE!GetIsEdpEnabled` at `0x140016447`
- `KERNELBASE!GetIsEdpEnabled` at `0x140016447`
- `ADVAPI32!IsWellKnownSid` at `0x140016434`
- `ADVAPI32!IsWellKnownSid` at `0x140016434`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(NSecurityLibrary *this, void **a2, int *a3)
{
  unsigned int v3; // edi
  HANDLE CurrentThread; // rax
  HANDLE v7; // rcx
  DWORD LastError; // ebx
  int IsEdpEnabled; // eax
  int v10; // esi
  HANDLE v11; // rcx
  HANDLE v12; // rcx
  HANDLE v13; // rcx
  void *v14; // rdx
  HANDLE v15; // rcx
  HANDLE v16; // rdx
  HANDLE Token; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE *TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  _BYTE pSid[80]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = 0;
  *(_QWORD *)this = 0;
  TokenHandle = (HANDLE)-1LL;
  Token = (HANDLE)-1LL;
  *(_DWORD *)a2 = 0;
  TokenInformationLength = 88;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    goto LABEL_40;
  memset_0(&TokenInformation, 0, 0x58u);
  v7 = TokenHandle;
  if ( TokenHandle == (HANDLE)-1LL )
    v7 = 0;
  if ( !GetTokenInformation(v7, TokenIntegrityLevel, &TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_5;
  if ( IsWellKnownSid(TokenInformation, WinLowLabelSid) )
    *(_DWORD *)a2 = 1;
  IsEdpEnabled = GetIsEdpEnabled();
  v10 = IsEdpEnabled;
  if ( !*(_DWORD *)a2 && !IsEdpEnabled )
    goto LABEL_28;
  v11 = TokenHandle;
  if ( TokenHandle == (HANDLE)-1LL )
    v11 = 0;
  if ( DuplicateTokenEx(v11, 0x8Eu, 0, SecurityImpersonation, TokenImpersonation, &Token) && RevertToSelf() )
  {
    if ( v10 )
    {
      v12 = Token;
      if ( Token == (HANDLE)-1LL )
        v12 = 0;
      SrpSetTokenEnterpriseExempt(v12);
    }
    if ( *(_DWORD *)a2 )
    {
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinMediumLabelSid, 0, pSid, cbSid) )
        goto LABEL_20;
      memset_0(&TokenInformation, 0, 0x58u);
      v13 = Token;
      TokenInformation = pSid;
      v23 = 96;
      if ( Token == (HANDLE)-1LL )
        v13 = 0;
      if ( !SetTokenInformation(v13, TokenIntegrityLevel, &TokenInformation, 0x58u) )
        goto LABEL_20;
      v15 = Token;
      if ( Token == (HANDLE)-1LL )
        v15 = 0;
      if ( !(unsigned int)NSecurityLibrary::RemoveModernAttributes(v15, v14) )
      {
LABEL_20:
        LastError = GetLastError();
LABEL_33:
        v16 = TokenHandle;
        if ( TokenHandle == (HANDLE)-1LL )
          v16 = 0;
        SetThreadToken(0, v16);
        goto LABEL_36;
      }
    }
    v10 = 1;
LABEL_28:
    v3 = 1;
    LastError = 0;
    if ( Token != (HANDLE)-1LL && Token )
    {
      if ( SetThreadToken(0, Token) )
        goto LABEL_36;
      LastError = GetLastError();
      v3 = 0;
    }
    if ( v10 )
      goto LABEL_33;
LABEL_36:
    if ( v3 )
      *(_QWORD *)this = NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(&TokenHandle);
    goto LABEL_38;
  }
LABEL_5:
  LastError = GetLastError();
LABEL_38:
  if ( LastError )
    SetLastError(LastError);
LABEL_40:
  if ( Token != (HANDLE)-1LL )
  {
    CloseHandle(Token);
    Token = (HANDLE)-1LL;
  }
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x140016350  mov     [rsp-8+arg_10], rbx
0x140016355  mov     [rsp-8+arg_18], rsi
0x14001635a  push    rbp
0x14001635b  push    rdi
0x14001635c  push    r12
0x14001635e  push    r13
0x140016360  push    r14
0x140016362  lea     rbp, [rsp-10h]
0x140016367  sub     rsp, 110h
0x14001636e  mov     rax, cs:__security_cookie
0x140016375  xor     rax, rsp
0x140016378  mov     [rbp+30h+var_30], rax
0x14001637c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140016380  xor     edi, edi
0x140016382  mov     [rcx], rdi
0x140016385  mov     rbx, rdx
0x140016388  mov     r14, rcx
0x14001638b  mov     [rsp+130h+TokenHandle], r12
0x140016390  mov     [rsp+130h+Token], r12
0x140016395  lea     esi, [r12+59h]
0x14001639a  mov     [rdx], edi
0x14001639c  mov     [rsp+130h+TokenInformationLength], esi
0x1400163a0  call    cs:__imp_GetCurrentThread
0x1400163a7  nop     dword ptr [rax+rax+00h]
0x1400163ac  lea     r13d, [r12+2]
0x1400163b1  mov     rcx, rax; ThreadHandle
0x1400163b4  mov     r8d, r13d; OpenAsSelf
0x1400163b7  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x1400163bc  lea     edx, [rsi-4Ah]; DesiredAccess
0x1400163bf  call    cs:__imp_OpenThreadToken
0x1400163c6  nop     dword ptr [rax+rax+00h]
0x1400163cb  test    eax, eax
0x1400163cd  jz      loc_1400165F0
0x1400163d3  mov     r8d, esi; Size
0x1400163d6  lea     rcx, [rsp+130h+TokenInformation]; void *
0x1400163db  xor     edx, edx; Val
0x1400163dd  call    memset_0
0x1400163e2  mov     rcx, [rsp+130h+TokenHandle]
0x1400163e7  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x1400163ec  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x1400163f1  lea     edx, [rsi-3Fh]; TokenInformationClass
0x1400163f4  xor     eax, eax
0x1400163f6  cmp     rcx, r12
0x1400163f9  cmovz   rcx, rax; TokenHandle
0x1400163fd  lea     rax, [rsp+130h+TokenInformationLength]
0x140016402  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x140016407  call    cs:__imp_GetTokenInformation
0x14001640e  nop     dword ptr [rax+rax+00h]
0x140016413  test    eax, eax
0x140016415  jnz     short loc_14001642A
0x140016417  call    cs:__imp_GetLastError
0x14001641e  nop     dword ptr [rax+rax+00h]
0x140016423  mov     ebx, eax
0x140016425  jmp     loc_1400165DE
0x14001642a  mov     rcx, [rsp+130h+TokenInformation]; pSid
0x14001642f  mov     edx, 42h ; 'B'; WellKnownSidType
0x140016434  call    cs:__imp_IsWellKnownSid
0x14001643b  nop     dword ptr [rax+rax+00h]
0x140016440  test    eax, eax
0x140016442  jz      short loc_140016447
0x140016444  mov     [rbx], r13d
0x140016447  call    cs:__imp_GetIsEdpEnabled
0x14001644e  nop     dword ptr [rax+rax+00h]
0x140016453  mov     esi, eax
0x140016455  cmp     [rbx], edi
0x140016457  jnz     short loc_140016461
0x140016459  test    eax, eax
0x14001645b  jz      loc_140016574
0x140016461  mov     rcx, [rsp+130h+TokenHandle]
0x140016466  xor     eax, eax
0x140016468  cmp     rcx, r12
0x14001646b  mov     r9d, 2; ImpersonationLevel
0x140016471  mov     edx, 8Eh; dwDesiredAccess
0x140016476  cmovz   rcx, rax; hExistingToken
0x14001647a  lea     rax, [rsp+130h+Token]
0x14001647f  mov     [rsp+130h+phNewToken], rax; phNewToken
0x140016484  xor     r8d, r8d; lpTokenAttributes
0x140016487  mov     dword ptr [rsp+130h+ReturnLength], r9d; TokenType
0x14001648c  call    cs:__imp_DuplicateTokenEx
0x140016493  nop     dword ptr [rax+rax+00h]
0x140016498  test    eax, eax
0x14001649a  jz      loc_140016417
0x1400164a0  call    cs:__imp_RevertToSelf
0x1400164a7  nop     dword ptr [rax+rax+00h]
0x1400164ac  test    eax, eax
0x1400164ae  jz      loc_140016417
0x1400164b4  test    esi, esi
0x1400164b6  jz      short loc_1400164CB
0x1400164b8  mov     rcx, [rsp+130h+Token]
0x1400164bd  xor     eax, eax
0x1400164bf  cmp     rcx, r12
0x1400164c2  cmovz   rcx, rax; TokenHandle
0x1400164c6  call    SrpSetTokenEnterpriseExempt
0x1400164cb  cmp     [rbx], edi
0x1400164cd  jz      loc_140016571
0x1400164d3  xor     edx, edx; DomainSid
0x1400164d5  mov     [rsp+130h+cbSid], 44h ; 'D'
0x1400164dd  lea     r9, [rsp+130h+cbSid]; cbSid
0x1400164e2  lea     r8, [rbp+30h+pSid]; pSid
0x1400164e6  lea     ecx, [rdx+43h]; WellKnownSidType
0x1400164e9  call    cs:__imp_CreateWellKnownSid
0x1400164f0  nop     dword ptr [rax+rax+00h]
0x1400164f5  test    eax, eax
0x1400164f7  jnz     short loc_14001650C
0x1400164f9  call    cs:__imp_GetLastError
0x140016500  nop     dword ptr [rax+rax+00h]
0x140016505  mov     ebx, eax
0x140016507  jmp     loc_1400165B1
0x14001650c  mov     ebx, 58h ; 'X'
0x140016511  lea     rcx, [rsp+130h+TokenInformation]; void *
0x140016516  mov     r8d, ebx; Size
0x140016519  xor     edx, edx; Val
0x14001651b  call    memset_0
0x140016520  mov     rcx, [rsp+130h+Token]
0x140016525  lea     rax, [rbp+30h+pSid]
0x140016529  mov     [rsp+130h+TokenInformation], rax
0x14001652e  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x140016533  xor     eax, eax
0x140016535  mov     [rsp+130h+var_D8], 60h ; '`'
0x14001653d  cmp     rcx, r12
0x140016540  lea     edx, [rbx-3Fh]; TokenInformationClass
0x140016543  mov     r9d, ebx; TokenInformationLength
0x140016546  cmovz   rcx, rax; TokenHandle
0x14001654a  call    cs:__imp_SetTokenInformation
0x140016551  nop     dword ptr [rax+rax+00h]
0x140016556  test    eax, eax
0x140016558  jz      short loc_1400164F9
0x14001655a  mov     rcx, [rsp+130h+Token]
0x14001655f  xor     eax, eax
0x140016561  cmp     rcx, r12
0x140016564  cmovz   rcx, rax; TokenHandle
0x140016568  call    ?RemoveModernAttributes@NSecurityLibrary@@YAHPEAX@Z; NSecurityLibrary::RemoveModernAttributes(void *)
0x14001656d  test    eax, eax
0x14001656f  jz      short loc_1400164F9
0x140016571  mov     esi, r13d
0x140016574  mov     edi, r13d
0x140016577  mov     rcx, [rsp+130h+Token]
0x14001657c  xor     ebx, ebx
0x14001657e  cmp     rcx, r12
0x140016581  jz      short loc_1400165AD
0x140016583  test    rcx, rcx
0x140016586  jz      short loc_1400165AD
0x140016588  mov     rdx, rcx; Token
0x14001658b  xor     ecx, ecx; Thread
0x14001658d  call    cs:__imp_SetThreadToken
0x140016594  nop     dword ptr [rax+rax+00h]
0x140016599  test    eax, eax
0x14001659b  jnz     short loc_1400165CD
0x14001659d  call    cs:__imp_GetLastError
0x1400165a4  nop     dword ptr [rax+rax+00h]
0x1400165a9  mov     ebx, eax
0x1400165ab  xor     edi, edi
0x1400165ad  test    esi, esi
0x1400165af  jz      short loc_1400165CD
0x1400165b1  mov     rdx, [rsp+130h+TokenHandle]
0x1400165b6  xor     eax, eax
0x1400165b8  cmp     rdx, r12
0x1400165bb  cmovz   rdx, rax; Token
0x1400165bf  xor     ecx, ecx; Thread
0x1400165c1  call    cs:__imp_SetThreadToken
0x1400165c8  nop     dword ptr [rax+rax+00h]
0x1400165cd  test    edi, edi
0x1400165cf  jz      short loc_1400165DE
0x1400165d1  lea     rcx, [rsp+130h+TokenHandle]
0x1400165d6  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x1400165db  mov     [r14], rax
0x1400165de  test    ebx, ebx
0x1400165e0  jz      short loc_1400165F0
0x1400165e2  mov     ecx, ebx; dwErrCode
0x1400165e4  call    cs:__imp_SetLastError
0x1400165eb  nop     dword ptr [rax+rax+00h]
0x1400165f0  mov     rcx, [rsp+130h+Token]; hObject
0x1400165f5  cmp     rcx, r12
0x1400165f8  jz      short loc_14001660B
0x1400165fa  call    cs:__imp_CloseHandle
0x140016601  nop     dword ptr [rax+rax+00h]
0x140016606  mov     [rsp+130h+Token], r12
0x14001660b  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x140016610  cmp     rcx, r12
0x140016613  jz      short loc_140016621
0x140016615  call    cs:__imp_CloseHandle
0x14001661c  nop     dword ptr [rax+rax+00h]
0x140016621  mov     eax, edi
0x140016623  mov     rcx, [rbp+30h+var_30]
0x140016627  xor     rcx, rsp; StackCookie
0x14001662a  call    __security_check_cookie
0x14001662f  lea     r11, [rsp+130h+var_20]
0x140016637  mov     rbx, [r11+40h]
0x14001663b  mov     rsi, [r11+48h]
0x14001663f  mov     rsp, r11
0x140016642  pop     r14
0x140016644  pop     r13
0x140016646  pop     r12
0x140016648  pop     rdi
0x140016649  pop     rbp
0x14001664a  retn
```
