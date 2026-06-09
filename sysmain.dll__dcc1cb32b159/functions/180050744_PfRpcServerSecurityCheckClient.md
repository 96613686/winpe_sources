# PfRpcServerSecurityCheckClient

- ea: `0x180050744`
- end: `0x180050911`
- name: `PfRpcServerSecurityCheckClient`
- size: `461`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c5a0`

## callees

- `0x180050744`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508a6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050843`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050867`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050843`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050867`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005088f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005088f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050901`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050909`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050901`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050909`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800507d0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180050814`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800507d0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180050814`
- `RPCRT4!RpcImpersonateClient` at `0x180050825`
- `RPCRT4!RpcImpersonateClient` at `0x180050825`
- `RPCRT4!RpcRevertToSelf` at `0x1800508c5`
- `RPCRT4!RpcRevertToSelf` at `0x1800508c5`

## pseudocode

```c
__int64 __fastcall PfRpcServerSecurityCheckClient(RPC_BINDING_HANDLE BindingHandle, int *a2)
{
  char v4; // di
  DWORD LastError; // ebx
  int v6; // ebx
  WINBOOL IsMember; // [rsp+68h] [rbp+7h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp+Bh] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp+17h] BYREF
  PSID pSid; // [rsp+80h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  TokenInformation = 0;
  v4 = 0;
  ReturnLength = 0;
  IsMember = 0;
  SidToCheck = 0;
  pSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    goto LABEL_14;
  }
  LastError = RpcImpersonateClient(BindingHandle);
  if ( LastError )
    goto LABEL_15;
  v4 = 1;
  if ( !CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFBLL, SidToCheck, &IsMember) )
    goto LABEL_14;
  v6 = 0;
  if ( IsMember )
    v6 = 4;
  if ( !CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFBLL, pSid, &IsMember) )
    goto LABEL_14;
  if ( IsMember )
    v6 |= 2u;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation )
      v6 |= 1u;
    *a2 = v6;
    LastError = 0;
  }
  else
  {
LABEL_14:
    LastError = GetLastError();
  }
LABEL_15:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( pSid )
    FreeSid(pSid);
  if ( v4 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180050744  mov     r11, rsp
0x180050747  mov     [r11+18h], rbx
0x18005074b  mov     [r11+20h], rsi
0x18005074f  push    rbp
0x180050750  push    rdi
0x180050751  push    r12
0x180050753  push    r14
0x180050755  push    r15
0x180050757  lea     rbp, [r11-5Fh]
0x18005075b  sub     rsp, 90h
0x180050762  mov     rax, cs:__security_cookie
0x180050769  xor     rax, rsp
0x18005076c  mov     [rbp+57h+var_28], rax
0x180050770  xor     r14d, r14d
0x180050773  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180050779  lea     rax, [rbp+57h+SidToCheck]
0x18005077d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180050781  mov     [r11-68h], rax
0x180050785  mov     rsi, rdx
0x180050788  mov     [r11-70h], r14d
0x18005078c  mov     rbx, rcx
0x18005078f  mov     [r11-78h], r14d
0x180050793  lea     r15d, [r14+20h]
0x180050797  mov     [r11-80h], r14d
0x18005079b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18005079f  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x1800507a4  mov     r8d, r15d; nSubAuthority0
0x1800507a7  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x1800507ac  mov     r9d, 220h; nSubAuthority1
0x1800507b2  mov     dl, 2; nSubAuthorityCount
0x1800507b4  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x1800507b9  mov     [rbp+57h+TokenInformation], r14d
0x1800507bd  mov     dil, r14b
0x1800507c0  mov     [rbp+57h+ReturnLength], r14d
0x1800507c4  mov     [rbp+57h+IsMember], r14d
0x1800507c8  mov     [rbp+57h+SidToCheck], r14
0x1800507cc  mov     [rbp+57h+var_38], r14
0x1800507d0  call    cs:__imp_AllocateAndInitializeSid
0x1800507d6  test    eax, eax
0x1800507d8  jz      loc_1800508A6
0x1800507de  lea     rax, [rbp+57h+var_38]
0x1800507e2  mov     r9d, 221h; nSubAuthority1
0x1800507e8  mov     [rsp+0B0h+pSid], rax; pSid
0x1800507ed  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800507f1  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x1800507f6  mov     r8d, r15d; nSubAuthority0
0x1800507f9  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x1800507fe  mov     dl, 2; nSubAuthorityCount
0x180050800  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x180050805  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x18005080a  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x18005080f  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x180050814  call    cs:__imp_AllocateAndInitializeSid
0x18005081a  test    eax, eax
0x18005081c  jz      loc_1800508A6
0x180050822  mov     rcx, rbx; BindingHandle
0x180050825  call    cs:__imp_RpcImpersonateClient
0x18005082b  mov     ebx, eax
0x18005082d  test    eax, eax
0x18005082f  jnz     short loc_1800508AE
0x180050831  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180050835  lea     r15, [r14-5]
0x180050839  mov     rcx, r15; TokenHandle
0x18005083c  lea     r8, [rbp+57h+IsMember]; IsMember
0x180050840  lea     edi, [rax+1]
0x180050843  call    cs:__imp_CheckTokenMembership
0x180050849  test    eax, eax
0x18005084b  jz      short loc_1800508A6
0x18005084d  cmp     [rbp+57h+IsMember], r14d
0x180050851  lea     r12d, [r14+4]
0x180050855  mov     rdx, [rbp+57h+var_38]; SidToCheck
0x180050859  lea     r8, [rbp+57h+IsMember]; IsMember
0x18005085d  mov     ebx, r14d
0x180050860  mov     rcx, r15; TokenHandle
0x180050863  cmovnz  ebx, r12d
0x180050867  call    cs:__imp_CheckTokenMembership
0x18005086d  test    eax, eax
0x18005086f  jz      short loc_1800508A6
0x180050871  cmp     [rbp+57h+IsMember], r14d
0x180050875  jnz     short loc_1800508F5
0x180050877  lea     rax, [rbp+57h+ReturnLength]
0x18005087b  mov     r9d, r12d; TokenInformationLength
0x18005087e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180050882  mov     qword ptr [rsp+0B0h+nSubAuthority2], rax; ReturnLength
0x180050887  mov     edx, 1Dh; TokenInformationClass
0x18005088c  mov     rcx, r15; TokenHandle
0x18005088f  call    cs:__imp_GetTokenInformation
0x180050895  test    eax, eax
0x180050897  jz      short loc_1800508A6
0x180050899  cmp     [rbp+57h+TokenInformation], r14d
0x18005089d  jnz     short loc_1800508FD
0x18005089f  mov     [rsi], ebx
0x1800508a1  mov     ebx, r14d
0x1800508a4  jmp     short loc_1800508AE
0x1800508a6  call    cs:__imp_GetLastError
0x1800508ac  mov     ebx, eax
0x1800508ae  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800508b2  test    rcx, rcx
0x1800508b5  jnz     short loc_180050901
0x1800508b7  mov     rcx, [rbp+57h+var_38]; pSid
0x1800508bb  test    rcx, rcx
0x1800508be  jnz     short loc_180050909
0x1800508c0  test    dil, dil
0x1800508c3  jz      short loc_1800508CB
0x1800508c5  call    cs:__imp_RpcRevertToSelf
0x1800508cb  mov     eax, ebx
0x1800508cd  mov     rcx, [rbp+57h+var_28]
0x1800508d1  xor     rcx, rsp; StackCookie
0x1800508d4  call    __security_check_cookie
0x1800508d9  lea     r11, [rsp+0B0h+var_20]
0x1800508e1  mov     rbx, [r11+40h]
0x1800508e5  mov     rsi, [r11+48h]
0x1800508e9  mov     rsp, r11
0x1800508ec  pop     r15
0x1800508ee  pop     r14
0x1800508f0  pop     r12
0x1800508f2  pop     rdi
0x1800508f3  pop     rbp
0x1800508f4  retn
0x1800508f5  or      ebx, 2
0x1800508f8  jmp     loc_180050877
0x1800508fd  or      ebx, edi
0x1800508ff  jmp     short loc_18005089F
0x180050901  call    cs:__imp_FreeSid
0x180050907  jmp     short loc_1800508B7
0x180050909  call    cs:__imp_FreeSid
0x18005090f  jmp     short loc_1800508C0
```
