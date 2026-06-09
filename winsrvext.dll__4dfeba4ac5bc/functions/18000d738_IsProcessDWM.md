# IsProcessDWM

- ea: `0x18000d738`
- end: `0x18000d867`
- name: `IsProcessDWM`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dda0`

## callees

- `0x18000d738`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d768`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000d768`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000d79f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000d79f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d80a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d80a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d81a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000d81a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d7ee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000d7ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d83a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d83a`

## pseudocode

```c
__int64 __fastcall IsProcessDWM(void *a1)
{
  WINBOOL IsMember; // [rsp+60h] [rbp+27h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+2Fh] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+37h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+3Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+47h] BYREF

  IsMember = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(a1, 0xAu, &TokenHandle) )
  {
    hObject = 0;
    if ( DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
      SidToCheck = 0;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
      {
        CheckTokenMembership(hObject, SidToCheck, &IsMember);
        FreeSid(SidToCheck);
      }
      CloseHandle(hObject);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18000d738  mov     [rsp-8+arg_8], rbx
0x18000d73d  push    rbp
0x18000d73e  lea     rbp, [rsp-57h]
0x18000d743  sub     rsp, 90h
0x18000d74a  mov     rax, cs:__security_cookie
0x18000d751  xor     rax, rsp
0x18000d754  mov     [rbp+57h+var_8], rax
0x18000d758  xor     ebx, ebx
0x18000d75a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000d75e  mov     [rbp+57h+IsMember], ebx
0x18000d761  mov     [rbp+57h+TokenHandle], rbx
0x18000d765  lea     edx, [rbx+0Ah]; DesiredAccess
0x18000d768  call    cs:__imp_OpenProcessToken
0x18000d76f  nop     dword ptr [rax+rax+00h]
0x18000d774  test    eax, eax
0x18000d776  jz      loc_18000D846
0x18000d77c  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18000d780  lea     rax, [rbp+57h+hObject]
0x18000d784  mov     [rsp+90h+phNewToken], rax; phNewToken
0x18000d789  lea     r9d, [rbx+2]; ImpersonationLevel
0x18000d78d  xor     r8d, r8d; lpTokenAttributes
0x18000d790  mov     [rsp+90h+TokenType], 2; TokenType
0x18000d798  lea     edx, [rbx+8]; dwDesiredAccess
0x18000d79b  mov     [rbp+57h+hObject], rbx
0x18000d79f  call    cs:__imp_DuplicateTokenEx
0x18000d7a6  nop     dword ptr [rax+rax+00h]
0x18000d7ab  test    eax, eax
0x18000d7ad  jz      loc_18000D836
0x18000d7b3  lea     rax, [rbp+57h+SidToCheck]
0x18000d7b7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x18000d7ba  mov     [rsp+90h+pSid], rax; pSid
0x18000d7bf  lea     r8d, [rbx+5Ah]; nSubAuthority0
0x18000d7c3  mov     [rsp+90h+nSubAuthority7], ebx; nSubAuthority7
0x18000d7c7  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d7cb  mov     [rsp+90h+nSubAuthority6], ebx; nSubAuthority6
0x18000d7cf  xor     r9d, r9d; nSubAuthority1
0x18000d7d2  mov     [rsp+90h+nSubAuthority5], ebx; nSubAuthority5
0x18000d7d6  mov     dl, 2; nSubAuthorityCount
0x18000d7d8  mov     [rsp+90h+nSubAuthority4], ebx; nSubAuthority4
0x18000d7dc  mov     dword ptr [rsp+90h+phNewToken], ebx; nSubAuthority3
0x18000d7e0  mov     [rsp+90h+TokenType], ebx; nSubAuthority2
0x18000d7e4  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000d7ea  mov     [rbp+57h+SidToCheck], rbx
0x18000d7ee  call    cs:__imp_AllocateAndInitializeSid
0x18000d7f5  nop     dword ptr [rax+rax+00h]
0x18000d7fa  test    eax, eax
0x18000d7fc  jz      short loc_18000D826
0x18000d7fe  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000d802  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000d806  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18000d80a  call    cs:__imp_CheckTokenMembership
0x18000d811  nop     dword ptr [rax+rax+00h]
0x18000d816  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18000d81a  call    cs:__imp_FreeSid
0x18000d821  nop     dword ptr [rax+rax+00h]
0x18000d826  mov     rcx, [rbp+57h+hObject]; hObject
0x18000d82a  call    cs:__imp_CloseHandle
0x18000d831  nop     dword ptr [rax+rax+00h]
0x18000d836  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000d83a  call    cs:__imp_CloseHandle
0x18000d841  nop     dword ptr [rax+rax+00h]
0x18000d846  mov     eax, [rbp+57h+IsMember]
0x18000d849  mov     rcx, [rbp+57h+var_8]
0x18000d84d  xor     rcx, rsp; StackCookie
0x18000d850  call    __security_check_cookie
0x18000d855  mov     rbx, [rsp+90h+arg_8]
0x18000d85d  add     rsp, 90h
0x18000d864  pop     rbp
0x18000d865  retn
```
