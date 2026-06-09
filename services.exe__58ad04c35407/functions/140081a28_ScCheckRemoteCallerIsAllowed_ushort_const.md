# ScCheckRemoteCallerIsAllowed(ushort const *)

- ea: `0x140081a28`
- end: `0x140081b63`
- name: `?ScCheckRemoteCallerIsAllowed@@YAHPEBG@Z`
- size: `315`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400137d0`

## callees

- `0x140004c58`
- `0x1400575b0`
- `0x140081a28`
- `0x1400846d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081b15`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140081aaa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140081aaa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140081af4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140081af4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140081a96`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140081a96`

## pseudocode

```c
__int64 __fastcall ScCheckRemoteCallerIsAllowed(wchar_t *a1)
{
  DWORD LastError; // eax
  DWORD v2; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  IsMember = 0;
  if ( ScReadRemoteUserAccessCheckRequired(a1) )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    SidToCheck = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( !CheckTokenMembership(0, SidToCheck, &IsMember)
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 33, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, LastError);
      }
      FreeSid(SidToCheck);
    }
    else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
           && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v2 = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 34, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v2);
    }
  }
  else
  {
    return 1;
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x140081a28  mov     [rsp-8+arg_8], rbx
0x140081a2d  push    rbp
0x140081a2e  mov     rbp, rsp
0x140081a31  sub     rsp, 80h
0x140081a38  mov     rax, cs:__security_cookie
0x140081a3f  xor     rax, rsp
0x140081a42  mov     [rbp+var_8], rax
0x140081a46  xor     ebx, ebx
0x140081a48  mov     [rbp+IsMember], ebx
0x140081a4b  call    ?ScReadRemoteUserAccessCheckRequired@@YAEPEBG@Z; ScReadRemoteUserAccessCheckRequired(ushort const *)
0x140081a50  test    al, al
0x140081a52  jz      loc_140081B3C
0x140081a58  lea     rax, [rbp+SidToCheck]
0x140081a5c  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x140081a5f  mov     [rsp+80h+pSid], rax; pSid
0x140081a64  lea     r8d, [rbx+20h]; nSubAuthority0
0x140081a68  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x140081a6c  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140081a70  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x140081a74  mov     r9d, 220h; nSubAuthority1
0x140081a7a  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x140081a7e  mov     dl, 2; nSubAuthorityCount
0x140081a80  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x140081a84  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x140081a88  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x140081a8c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140081a92  mov     [rbp+SidToCheck], rbx
0x140081a96  call    cs:__imp_AllocateAndInitializeSid
0x140081a9c  test    eax, eax
0x140081a9e  jz      short loc_140081AFC
0x140081aa0  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x140081aa4  lea     r8, [rbp+IsMember]; IsMember
0x140081aa8  xor     ecx, ecx; TokenHandle
0x140081aaa  call    cs:__imp_CheckTokenMembership
0x140081ab0  test    eax, eax
0x140081ab2  jnz     short loc_140081AF0
0x140081ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140081abb  lea     rax, WPP_GLOBAL_Control
0x140081ac2  cmp     rcx, rax
0x140081ac5  jz      short loc_140081AF0
0x140081ac7  test    byte ptr [rcx+1Ch], 1
0x140081acb  jz      short loc_140081AF0
0x140081acd  call    cs:__imp_GetLastError
0x140081ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ada  lea     edx, [rbx+21h]
0x140081add  mov     r9d, eax
0x140081ae0  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140081ae7  mov     rcx, [rcx+10h]
0x140081aeb  call    WPP_SF_d
0x140081af0  mov     rcx, [rbp+SidToCheck]; pSid
0x140081af4  call    cs:__imp_FreeSid
0x140081afa  jmp     short loc_140081B43
0x140081afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140081b03  lea     rax, WPP_GLOBAL_Control
0x140081b0a  cmp     rcx, rax
0x140081b0d  jz      short loc_140081B43
0x140081b0f  test    byte ptr [rcx+1Ch], 1
0x140081b13  jz      short loc_140081B43
0x140081b15  call    cs:__imp_GetLastError
0x140081b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140081b22  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140081b29  mov     edx, 22h ; '"'
0x140081b2e  mov     r9d, eax
0x140081b31  mov     rcx, [rcx+10h]
0x140081b35  call    WPP_SF_d
0x140081b3a  jmp     short loc_140081B43
0x140081b3c  mov     [rbp+IsMember], 1
0x140081b43  mov     eax, [rbp+IsMember]
0x140081b46  mov     rcx, [rbp+var_8]
0x140081b4a  xor     rcx, rsp; StackCookie
0x140081b4d  call    __security_check_cookie
0x140081b52  mov     rbx, [rsp+80h+arg_8]
0x140081b5a  add     rsp, 80h
0x140081b61  pop     rbp
0x140081b62  retn
```
