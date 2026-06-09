# NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)

- ea: `0x140015000`
- end: `0x14001528d`
- name: `?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z`
- size: `653`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400038f0`
- `0x140004e90`
- `0x140005c30`
- `0x14000c0e0`

## callees

- `0x14000eb20`
- `0x14000f300`
- `0x140015000`
- `0x14002abc0`
- `0x14002b810`
- `0x140057c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400150b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001516b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400151fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400150b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001516b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400151fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140015238`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140015238`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400151f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001521b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400151f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001521b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140015069`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140015069`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140015050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140015050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001525d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001525d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140015122`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140015122`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400150ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400150ab`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400151b6`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400151b6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140015118`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140015118`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140015161`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140015161`
- `KERNELBASE!GetIsEdpEnabled` at `0x1400150d9`
- `KERNELBASE!GetIsEdpEnabled` at `0x1400150d9`
- `ADVAPI32!IsWellKnownSid` at `0x1400150cc`
- `ADVAPI32!IsWellKnownSid` at `0x1400150cc`

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
0x140015000  mov     [rsp-8+arg_10], rbx
0x140015005  mov     [rsp-8+arg_18], rsi
0x14001500a  push    rbp
0x14001500b  push    rdi
0x14001500c  push    r12
0x14001500e  push    r13
0x140015010  push    r14
0x140015012  lea     rbp, [rsp-10h]
0x140015017  sub     rsp, 110h
0x14001501e  mov     rax, cs:__security_cookie
0x140015025  xor     rax, rsp
0x140015028  mov     [rbp+30h+var_30], rax
0x14001502c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140015030  xor     edi, edi
0x140015032  mov     [rcx], rdi
0x140015035  mov     rbx, rdx
0x140015038  mov     r14, rcx
0x14001503b  mov     [rsp+130h+TokenHandle], r12
0x140015040  mov     [rsp+130h+Token], r12
0x140015045  lea     esi, [r12+59h]
0x14001504a  mov     [rdx], edi
0x14001504c  mov     [rsp+130h+TokenInformationLength], esi
0x140015050  call    cs:__imp_GetCurrentThread
0x140015056  lea     r13d, [r12+2]
0x14001505b  mov     rcx, rax; ThreadHandle
0x14001505e  mov     r8d, r13d; OpenAsSelf
0x140015061  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x140015066  lea     edx, [rsi-4Ah]; DesiredAccess
0x140015069  call    cs:__imp_OpenThreadToken
0x14001506f  test    eax, eax
0x140015071  jz      loc_14001523E
0x140015077  mov     r8d, esi; Size
0x14001507a  lea     rcx, [rsp+130h+TokenInformation]; void *
0x14001507f  xor     edx, edx; Val
0x140015081  call    memset_0
0x140015086  mov     rcx, [rsp+130h+TokenHandle]
0x14001508b  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x140015090  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x140015095  lea     edx, [rsi-3Fh]; TokenInformationClass
0x140015098  xor     eax, eax
0x14001509a  cmp     rcx, r12
0x14001509d  cmovz   rcx, rax; TokenHandle
0x1400150a1  lea     rax, [rsp+130h+TokenInformationLength]
0x1400150a6  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x1400150ab  call    cs:__imp_GetTokenInformation
0x1400150b1  test    eax, eax
0x1400150b3  jnz     short loc_1400150C2
0x1400150b5  call    cs:__imp_GetLastError
0x1400150bb  mov     ebx, eax
0x1400150bd  jmp     loc_140015232
0x1400150c2  mov     rcx, [rsp+130h+TokenInformation]; pSid
0x1400150c7  mov     edx, 42h ; 'B'; WellKnownSidType
0x1400150cc  call    cs:__imp_IsWellKnownSid
0x1400150d2  test    eax, eax
0x1400150d4  jz      short loc_1400150D9
0x1400150d6  mov     [rbx], r13d
0x1400150d9  call    cs:__imp_GetIsEdpEnabled
0x1400150df  mov     esi, eax
0x1400150e1  cmp     [rbx], edi
0x1400150e3  jnz     short loc_1400150ED
0x1400150e5  test    eax, eax
0x1400150e7  jz      loc_1400151DA
0x1400150ed  mov     rcx, [rsp+130h+TokenHandle]
0x1400150f2  xor     eax, eax
0x1400150f4  cmp     rcx, r12
0x1400150f7  mov     r9d, 2; ImpersonationLevel
0x1400150fd  mov     edx, 8Eh; dwDesiredAccess
0x140015102  cmovz   rcx, rax; hExistingToken
0x140015106  lea     rax, [rsp+130h+Token]
0x14001510b  mov     [rsp+130h+phNewToken], rax; phNewToken
0x140015110  xor     r8d, r8d; lpTokenAttributes
0x140015113  mov     dword ptr [rsp+130h+ReturnLength], r9d; TokenType
0x140015118  call    cs:__imp_DuplicateTokenEx
0x14001511e  test    eax, eax
0x140015120  jz      short loc_1400150B5
0x140015122  call    cs:__imp_RevertToSelf
0x140015128  test    eax, eax
0x14001512a  jz      short loc_1400150B5
0x14001512c  test    esi, esi
0x14001512e  jz      short loc_140015143
0x140015130  mov     rcx, [rsp+130h+Token]
0x140015135  xor     eax, eax
0x140015137  cmp     rcx, r12
0x14001513a  cmovz   rcx, rax; TokenHandle
0x14001513e  call    SrpSetTokenEnterpriseExempt
0x140015143  cmp     [rbx], edi
0x140015145  jz      loc_1400151D7
0x14001514b  xor     edx, edx; DomainSid
0x14001514d  mov     [rsp+130h+cbSid], 44h ; 'D'
0x140015155  lea     r9, [rsp+130h+cbSid]; cbSid
0x14001515a  lea     r8, [rbp+30h+pSid]; pSid
0x14001515e  lea     ecx, [rdx+43h]; WellKnownSidType
0x140015161  call    cs:__imp_CreateWellKnownSid
0x140015167  test    eax, eax
0x140015169  jnz     short loc_140015178
0x14001516b  call    cs:__imp_GetLastError
0x140015171  mov     ebx, eax
0x140015173  jmp     loc_14001520B
0x140015178  mov     ebx, 58h ; 'X'
0x14001517d  lea     rcx, [rsp+130h+TokenInformation]; void *
0x140015182  mov     r8d, ebx; Size
0x140015185  xor     edx, edx; Val
0x140015187  call    memset_0
0x14001518c  mov     rcx, [rsp+130h+Token]
0x140015191  lea     rax, [rbp+30h+pSid]
0x140015195  mov     [rsp+130h+TokenInformation], rax
0x14001519a  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x14001519f  xor     eax, eax
0x1400151a1  mov     [rsp+130h+var_D8], 60h ; '`'
0x1400151a9  cmp     rcx, r12
0x1400151ac  lea     edx, [rbx-3Fh]; TokenInformationClass
0x1400151af  mov     r9d, ebx; TokenInformationLength
0x1400151b2  cmovz   rcx, rax; TokenHandle
0x1400151b6  call    cs:__imp_SetTokenInformation
0x1400151bc  test    eax, eax
0x1400151be  jz      short loc_14001516B
0x1400151c0  mov     rcx, [rsp+130h+Token]
0x1400151c5  xor     eax, eax
0x1400151c7  cmp     rcx, r12
0x1400151ca  cmovz   rcx, rax; TokenHandle
0x1400151ce  call    ?RemoveModernAttributes@NSecurityLibrary@@YAHPEAX@Z; NSecurityLibrary::RemoveModernAttributes(void *)
0x1400151d3  test    eax, eax
0x1400151d5  jz      short loc_14001516B
0x1400151d7  mov     esi, r13d
0x1400151da  mov     edi, r13d
0x1400151dd  mov     rcx, [rsp+130h+Token]
0x1400151e2  xor     ebx, ebx
0x1400151e4  cmp     rcx, r12
0x1400151e7  jz      short loc_140015207
0x1400151e9  test    rcx, rcx
0x1400151ec  jz      short loc_140015207
0x1400151ee  mov     rdx, rcx; Token
0x1400151f1  xor     ecx, ecx; Thread
0x1400151f3  call    cs:__imp_SetThreadToken
0x1400151f9  test    eax, eax
0x1400151fb  jnz     short loc_140015221
0x1400151fd  call    cs:__imp_GetLastError
0x140015203  mov     ebx, eax
0x140015205  xor     edi, edi
0x140015207  test    esi, esi
0x140015209  jz      short loc_140015221
0x14001520b  mov     rdx, [rsp+130h+TokenHandle]
0x140015210  xor     eax, eax
0x140015212  cmp     rdx, r12
0x140015215  cmovz   rdx, rax; Token
0x140015219  xor     ecx, ecx; Thread
0x14001521b  call    cs:__imp_SetThreadToken
0x140015221  test    edi, edi
0x140015223  jz      short loc_140015232
0x140015225  lea     rcx, [rsp+130h+TokenHandle]
0x14001522a  call    ?Detach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAPEAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Detach(void)
0x14001522f  mov     [r14], rax
0x140015232  test    ebx, ebx
0x140015234  jz      short loc_14001523E
0x140015236  mov     ecx, ebx; dwErrCode
0x140015238  call    cs:__imp_SetLastError
0x14001523e  mov     rcx, [rsp+130h+Token]; hObject
0x140015243  cmp     rcx, r12
0x140015246  jz      short loc_140015253
0x140015248  call    cs:__imp_CloseHandle
0x14001524e  mov     [rsp+130h+Token], r12
0x140015253  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x140015258  cmp     rcx, r12
0x14001525b  jz      short loc_140015263
0x14001525d  call    cs:__imp_CloseHandle
0x140015263  mov     eax, edi
0x140015265  mov     rcx, [rbp+30h+var_30]
0x140015269  xor     rcx, rsp; StackCookie
0x14001526c  call    __security_check_cookie
0x140015271  lea     r11, [rsp+130h+var_20]
0x140015279  mov     rbx, [r11+40h]
0x14001527d  mov     rsi, [r11+48h]
0x140015281  mov     rsp, r11
0x140015284  pop     r14
0x140015286  pop     r13
0x140015288  pop     r12
0x14001528a  pop     rdi
0x14001528b  pop     rbp
0x14001528c  retn
```
