# AuthorizationProvider::GetActiveUserToken(void * *)

- ea: `0x180030458`
- end: `0x1800305f1`
- name: `?GetActiveUserToken@AuthorizationProvider@@AEAAJPEAPEAX@Z`
- size: `409`
- prototype: `int(AuthorizationProvider *__hidden this, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800313ac`

## callees

- `0x180003ca0`
- `0x180003db8`
- `0x180003eac`
- `0x18000e5ac`
- `0x18001e06c`
- `0x18002fe68`
- `0x180030458`
- `0x1800316f4`
- `0x180031ae0`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800305bc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800305bc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18003050e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18003050e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800304b2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800304b2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800305dc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800305dc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18003058b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18003058b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800305c8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800305c8`

## pseudocode

```c
__int64 __fastcall AuthorizationProvider::GetActiveUserToken(AuthorizationProvider *this, void **a2)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  __int64 i; // rbx
  PWTS_SESSION_INFOW v6; // r14
  const char *v8; // r9
  __int64 v9; // rdx
  int pCount; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  AuthorizationProvider *v12; // [rsp+60h] [rbp+30h] BYREF
  DWORD v13; // [rsp+68h] [rbp+38h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+70h] [rbp+40h] BYREF

  v12 = this;
  *a2 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() && (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v13 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v13) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x184,
                    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
                    v3);
LABEL_14:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
      return LastError;
    }
    for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
    {
      v6 = ppSessionInfo;
      LOBYTE(v12) = 0;
      if ( (ppSessionInfo[i].State == WTSActive || (int)IsSessionLocked(ppSessionInfo[i].SessionId) >= 0 && (_BYTE)v12)
        && (WTSQueryUserToken(v6[i].SessionId, a2) || (int)ResultFromKnownLastError() >= 0) )
      {
        LastError = 0;
        goto LABEL_14;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
LABEL_16:
    LastError = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)0x80070490LL,
      pCount);
    return LastError;
  }
  if ( !(unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent()
    || !(unsigned __int8)IsQueryActiveSessionPresent()
    || !(unsigned __int8)IsQueryActiveSessionPresent() )
  {
    goto LABEL_16;
  }
  LODWORD(v12) = 0;
  if ( (unsigned int)QueryActiveSession(&v12) )
  {
    v13 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v13, 0);
    if ( (int)UMgrGetSessionActiveShellUserToken((unsigned int)v12, a2) >= 0
      || (unsigned int)QueryUserToken((unsigned int)v12, a2) )
    {
      goto LABEL_16;
    }
    v9 = 422;
  }
  else
  {
    v9 = 411;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
           v8);
}

```

## disassembly

```asm
0x180030458  mov     [rsp-28h+arg_0], rcx
0x18003045d  push    rbp
0x18003045e  push    rbx
0x18003045f  push    rsi
0x180030460  push    rdi
0x180030461  push    r14
0x180030463  mov     rbp, rsp
0x180030466  sub     rsp, 30h
0x18003046a  mov     rdi, rdx
0x18003046d  mov     qword ptr [rdx], 0
0x180030474  call    IsWTSEnumerateSessionsWPresent
0x180030479  test    al, al
0x18003047b  jz      loc_180030565
0x180030481  call    IsWTSEnumerateSessionsWPresent
0x180030486  test    al, al
0x180030488  jz      loc_180030565
0x18003048e  xor     edx, edx; Reserved
0x180030490  mov     [rbp+arg_8], 0
0x180030497  lea     rax, [rbp+arg_8]
0x18003049b  mov     [rbp+ppSessionInfo], 0
0x1800304a3  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800304a7  mov     qword ptr [rsp+30h+pCount], rax; int
0x1800304ac  xor     ecx, ecx; hServer
0x1800304ae  lea     r8d, [rdx+1]; Version
0x1800304b2  call    cs:__imp_WTSEnumerateSessionsW
0x1800304b8  test    eax, eax
0x1800304ba  jnz     short loc_1800304D5
0x1800304bc  mov     rcx, [rbp+28h]; this
0x1800304c0  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x1800304c7  mov     edx, 184h; void *
0x1800304cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800304d1  mov     ebx, eax
0x1800304d3  jmp     short loc_180030527
0x1800304d5  xor     ebx, ebx
0x1800304d7  cmp     ebx, [rbp+arg_8]
0x1800304da  jnb     short loc_180030532
0x1800304dc  mov     r14, [rbp+ppSessionInfo]
0x1800304e0  lea     rsi, [rbx+rbx*2]
0x1800304e4  mov     byte ptr [rbp+arg_0], 0
0x1800304e8  cmp     dword ptr [r14+rsi*8+10h], 0
0x1800304ee  jz      short loc_180030507
0x1800304f0  mov     ecx, [r14+rsi*8]; SessionId
0x1800304f4  lea     rdx, [rbp+arg_0]
0x1800304f8  call    IsSessionLocked
0x1800304fd  test    eax, eax
0x1800304ff  js      short loc_180030521
0x180030501  cmp     byte ptr [rbp+arg_0], 0
0x180030505  jz      short loc_180030521
0x180030507  mov     ecx, [r14+rsi*8]; SessionId
0x18003050b  mov     rdx, rdi; phToken
0x18003050e  call    cs:__imp_WTSQueryUserToken
0x180030514  test    eax, eax
0x180030516  jnz     short loc_180030525
0x180030518  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003051d  test    eax, eax
0x18003051f  jns     short loc_180030525
0x180030521  inc     ebx
0x180030523  jmp     short loc_1800304D7
0x180030525  xor     ebx, ebx
0x180030527  lea     rcx, [rbp+ppSessionInfo]
0x18003052b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180030530  jmp     short loc_180030558
0x180030532  lea     rcx, [rbp+ppSessionInfo]
0x180030536  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003053b  mov     rcx, [rbp+28h]; this
0x18003053f  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030546  mov     ebx, 80070490h
0x18003054b  mov     edx, 1ABh; void *
0x180030550  mov     r9d, ebx; char *
0x180030553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030558  mov     eax, ebx
0x18003055a  add     rsp, 30h
0x18003055e  pop     r14
0x180030560  pop     rdi
0x180030561  pop     rsi
0x180030562  pop     rbx
0x180030563  pop     rbp
0x180030564  retn
0x180030565  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x18003056a  test    al, al
0x18003056c  jz      short loc_18003053B
0x18003056e  call    IsQueryActiveSessionPresent
0x180030573  test    al, al
0x180030575  jz      short loc_18003053B
0x180030577  call    IsQueryActiveSessionPresent
0x18003057c  test    al, al
0x18003057e  jz      short loc_18003053B
0x180030580  lea     rcx, [rbp+arg_0]
0x180030584  mov     dword ptr [rbp+arg_0], 0
0x18003058b  call    cs:__imp_QueryActiveSession
0x180030591  test    eax, eax
0x180030593  jnz     short loc_1800305AC
0x180030595  mov     edx, 19Bh; void *
0x18003059a  mov     rcx, [rbp+28h]; this
0x18003059e  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x1800305a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800305aa  jmp     short loc_18003055A
0x1800305ac  xor     r8d, r8d
0x1800305af  mov     [rbp+arg_8], 0
0x1800305b6  lea     rdx, [rbp+arg_8]
0x1800305ba  xor     ecx, ecx
0x1800305bc  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800305c2  mov     ecx, dword ptr [rbp+arg_0]
0x1800305c5  mov     rdx, rdi
0x1800305c8  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x1800305ce  test    eax, eax
0x1800305d0  jns     loc_18003053B
0x1800305d6  mov     ecx, dword ptr [rbp+arg_0]
0x1800305d9  mov     rdx, rdi
0x1800305dc  call    cs:__imp_QueryUserToken
0x1800305e2  test    eax, eax
0x1800305e4  jnz     loc_18003053B
0x1800305ea  mov     edx, 1A6h
0x1800305ef  jmp     short loc_18003059A
```
