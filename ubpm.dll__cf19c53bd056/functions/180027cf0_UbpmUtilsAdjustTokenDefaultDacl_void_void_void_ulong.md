# UbpmUtilsAdjustTokenDefaultDacl(void *,void *,void * *,ulong)

- ea: `0x180027cf0`
- end: `0x180027ead`
- name: `?UbpmUtilsAdjustTokenDefaultDacl@@YAKPEAX0PEAPEAXK@Z`
- size: `445`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, PSID pSid, void **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019480`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180027cf0`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027e8d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027e8d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180027d6c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180027d6c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027ddf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027dfc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027e20`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027ddf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027dfc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180027e20`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180027dbf`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180027dbf`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180027e46`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180027e46`
- `ntdll!RtlLengthSid` at `0x180027d7d`
- `ntdll!RtlLengthSid` at `0x180027d8d`
- `ntdll!RtlLengthSid` at `0x180027d99`
- `ntdll!RtlLengthSid` at `0x180027d7d`
- `ntdll!RtlLengthSid` at `0x180027d8d`
- `ntdll!RtlLengthSid` at `0x180027d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e9a`

## pseudocode

```c
__int64 __fastcall UbpmUtilsAdjustTokenDefaultDacl(HANDLE TokenHandle, PSID pSid, void **a3, unsigned int a4)
{
  ULONG v8; // ebx
  ULONG v9; // ebx
  ULONG v10; // ebx
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  unsigned int i; // ebx
  DWORD LastError; // ebx
  PSID Sid; // [rsp+60h] [rbp-9h] BYREF
  struct _ACL *TokenInformation; // [rsp+68h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+7h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Sid = 0;
  TokenInformation = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    v12 = 0;
LABEL_14:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v8 = a4 * (RtlLengthSid(*a3) + 12);
  v9 = RtlLengthSid(pSid) + v8;
  v10 = RtlLengthSid(Sid) + v9;
  v11 = (struct _ACL *)UbpmAlloc(v10 + 32);
  v12 = v11;
  if ( !v11
    || !InitializeAcl(v11, v10 + 32, 2u)
    || !AddAccessAllowedAce(v12, 2u, 0x10000000u, pSid)
    || !AddAccessAllowedAce(v12, 2u, 0x20000u, Sid) )
  {
    goto LABEL_14;
  }
  for ( i = 0; i < a4; ++i )
  {
    if ( !AddAccessAllowedAce(v12, 2u, 0x10000000u, a3[i]) )
      goto LABEL_14;
  }
  TokenInformation = v12;
  LastError = 0;
  if ( !SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u) )
  {
    LastError = GetLastError();
    if ( LastError == 1344 )
      LastError = 0;
  }
LABEL_11:
  UBPM_MIDL_user_free(v12);
  if ( Sid )
    FreeSid(Sid);
  return LastError;
}

```

## disassembly

```asm
0x180027cf0  push    rbp
0x180027cf2  push    rbx
0x180027cf3  push    rsi
0x180027cf4  push    rdi
0x180027cf5  push    r12
0x180027cf7  push    r13
0x180027cf9  push    r14
0x180027cfb  push    r15
0x180027cfd  lea     rbp, [rsp-1Fh]
0x180027d02  sub     rsp, 88h
0x180027d09  mov     rax, cs:__security_cookie
0x180027d10  xor     rax, rsp
0x180027d13  mov     [rbp+57h+var_48], rax
0x180027d17  xor     r13d, r13d
0x180027d1a  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 300h
0x180027d20  lea     rax, [rbp+57h+Sid]
0x180027d24  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180027d28  mov     [rsp+0C0h+pSid], rax; pSid
0x180027d2d  mov     r14d, r9d
0x180027d30  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180027d35  mov     r15, r8
0x180027d38  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180027d3d  lea     r8d, [r13+4]; nSubAuthority0
0x180027d41  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180027d46  mov     rsi, rdx
0x180027d49  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180027d4e  mov     r12, rcx
0x180027d51  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180027d56  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180027d5a  xor     r9d, r9d; nSubAuthority1
0x180027d5d  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180027d62  mov     dl, 1; nSubAuthorityCount
0x180027d64  mov     [rbp+57h+Sid], r13
0x180027d68  mov     [rbp+57h+TokenInformation], r13
0x180027d6c  call    cs:__imp_AllocateAndInitializeSid
0x180027d72  test    eax, eax
0x180027d74  jz      loc_180027E95
0x180027d7a  mov     rcx, [r15]; Sid
0x180027d7d  call    cs:__imp_RtlLengthSid
0x180027d83  mov     rcx, rsi; Sid
0x180027d86  lea     ebx, [rax+0Ch]
0x180027d89  imul    ebx, r14d
0x180027d8d  call    cs:__imp_RtlLengthSid
0x180027d93  mov     rcx, [rbp+57h+Sid]; Sid
0x180027d97  add     ebx, eax
0x180027d99  call    cs:__imp_RtlLengthSid
0x180027d9f  add     ebx, eax
0x180027da1  lea     ecx, [rbx+20h]; Size
0x180027da4  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180027da9  mov     rdi, rax
0x180027dac  test    rax, rax
0x180027daf  jz      loc_180027E83
0x180027db5  lea     r8d, [r13+2]; dwAclRevision
0x180027db9  mov     rcx, rax; pAcl
0x180027dbc  lea     edx, [rbx+20h]; nAclLength
0x180027dbf  call    cs:__imp_InitializeAcl
0x180027dc5  test    eax, eax
0x180027dc7  jz      loc_180027E83
0x180027dcd  mov     r9, rsi; pSid
0x180027dd0  mov     r8d, 10000000h; AccessMask
0x180027dd6  lea     esi, [r13+2]
0x180027dda  mov     rcx, rdi; pAcl
0x180027ddd  mov     edx, esi; dwAceRevision
0x180027ddf  call    cs:__imp_AddAccessAllowedAce
0x180027de5  test    eax, eax
0x180027de7  jz      loc_180027E83
0x180027ded  mov     r9, [rbp+57h+Sid]; pSid
0x180027df1  mov     r8d, 20000h; AccessMask
0x180027df7  mov     edx, esi; dwAceRevision
0x180027df9  mov     rcx, rdi; pAcl
0x180027dfc  call    cs:__imp_AddAccessAllowedAce
0x180027e02  test    eax, eax
0x180027e04  jz      short loc_180027E83
0x180027e06  mov     ebx, r13d
0x180027e09  cmp     ebx, r14d
0x180027e0c  jnb     short loc_180027E2E
0x180027e0e  mov     r9d, ebx
0x180027e11  mov     r8d, 10000000h; AccessMask
0x180027e17  mov     edx, esi; dwAceRevision
0x180027e19  mov     rcx, rdi; pAcl
0x180027e1c  mov     r9, [r15+r9*8]; pSid
0x180027e20  call    cs:__imp_AddAccessAllowedAce
0x180027e26  test    eax, eax
0x180027e28  jz      short loc_180027E83
0x180027e2a  inc     ebx
0x180027e2c  jmp     short loc_180027E09
0x180027e2e  mov     r9d, 8; TokenInformationLength
0x180027e34  mov     [rbp+57h+TokenInformation], rdi
0x180027e38  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027e3c  mov     rcx, r12; TokenHandle
0x180027e3f  mov     ebx, r13d
0x180027e42  lea     edx, [r9-2]; TokenInformationClass
0x180027e46  call    cs:__imp_SetTokenInformation
0x180027e4c  test    eax, eax
0x180027e4e  jz      short loc_180027E9A
0x180027e50  mov     rcx, rdi
0x180027e53  call    UBPM_MIDL_user_free
0x180027e58  mov     rcx, [rbp+57h+Sid]; pSid
0x180027e5c  test    rcx, rcx
0x180027e5f  jnz     short loc_180027E8D
0x180027e61  mov     eax, ebx
0x180027e63  mov     rcx, [rbp+57h+var_48]
0x180027e67  xor     rcx, rsp; StackCookie
0x180027e6a  call    __security_check_cookie
0x180027e6f  add     rsp, 88h
0x180027e76  pop     r15
0x180027e78  pop     r14
0x180027e7a  pop     r13
0x180027e7c  pop     r12
0x180027e7e  pop     rdi
0x180027e7f  pop     rsi
0x180027e80  pop     rbx
0x180027e81  pop     rbp
0x180027e82  retn
0x180027e83  call    cs:__imp_GetLastError
0x180027e89  mov     ebx, eax
0x180027e8b  jmp     short loc_180027E50
0x180027e8d  call    cs:__imp_FreeSid
0x180027e93  jmp     short loc_180027E61
0x180027e95  mov     rdi, r13
0x180027e98  jmp     short loc_180027E83
0x180027e9a  call    cs:__imp_GetLastError
0x180027ea0  cmp     eax, 540h
0x180027ea5  mov     ebx, eax
0x180027ea7  cmovz   ebx, r13d
0x180027eab  jmp     short loc_180027E50
```
