# CVerifyAuthentication::Initialize(void)

- ea: `0x180001c1c`
- end: `0x180001caf`
- name: `?Initialize@CVerifyAuthentication@@SAXXZ`
- size: `147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e28`

## callees

- `0x180001c1c`
- `0x18000d038`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c8e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180001c84`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180001c84`

## pseudocode

```c
void CVerifyAuthentication::Initialize(void)
{
  DWORD LastError; // eax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( CVerifyAuthentication::_psidAuthenticatedUsersGroup )
    TrkRaiseWin32Error(1358);
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          1u,
          0xBu,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          &CVerifyAuthentication::_psidAuthenticatedUsersGroup) )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
}

```

## disassembly

```asm
0x180001c1c  push    rbx
0x180001c1e  sub     rsp, 70h
0x180001c22  mov     rax, cs:__security_cookie
0x180001c29  xor     rax, rsp
0x180001c2c  mov     [rsp+78h+var_10], rax
0x180001c31  xor     ebx, ebx
0x180001c33  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 500h
0x180001c3a  cmp     cs:?_psidAuthenticatedUsersGroup@CVerifyAuthentication@@0PEAXEA, rbx; void * CVerifyAuthentication::_psidAuthenticatedUsersGroup
0x180001c41  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x180001c45  jz      short loc_180001C52
0x180001c47  mov     ecx, 54Eh; int
0x180001c4c  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180001c52  lea     rax, ?_psidAuthenticatedUsersGroup@CVerifyAuthentication@@0PEAXEA; void * CVerifyAuthentication::_psidAuthenticatedUsersGroup
0x180001c59  xor     r9d, r9d; nSubAuthority1
0x180001c5c  mov     [rsp+78h+pSid], rax; pSid
0x180001c61  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x180001c66  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x180001c6a  mov     dl, 1; nSubAuthorityCount
0x180001c6c  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x180001c70  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x180001c74  lea     r8d, [r9+0Bh]; nSubAuthority0
0x180001c78  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x180001c7c  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x180001c80  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x180001c84  call    cs:__imp_AllocateAndInitializeSid
0x180001c8a  test    eax, eax
0x180001c8c  jnz     short loc_180001C9C
0x180001c8e  call    cs:__imp_GetLastError
0x180001c94  mov     ecx, eax; int
0x180001c96  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180001c9c  mov     rcx, [rsp+78h+var_10]
0x180001ca1  xor     rcx, rsp; StackCookie
0x180001ca4  call    __security_check_cookie
0x180001ca9  add     rsp, 70h
0x180001cad  pop     rbx
0x180001cae  retn
```
