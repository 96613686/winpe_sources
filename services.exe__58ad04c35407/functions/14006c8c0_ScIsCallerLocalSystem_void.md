# ScIsCallerLocalSystem(void *)

- ea: `0x14006c8c0`
- end: `0x14006c9ef`
- name: `?ScIsCallerLocalSystem@@YAHPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002fce0`

## callees

- `0x140004c58`
- `0x1400575b0`
- `0x14006c8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c9a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c9a6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14006c93b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14006c93b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14006c985`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14006c985`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14006c926`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14006c926`

## pseudocode

```c
__int64 __fastcall ScIsCallerLocalSystem(HANDLE TokenHandle)
{
  DWORD LastError; // eax
  DWORD v3; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember)
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 77, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, LastError);
    }
    FreeSid(SidToCheck);
  }
  else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v3 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 78, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v3);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x14006c8c0  mov     [rsp-8+arg_8], rbx
0x14006c8c5  mov     [rsp-8+arg_10], rdi
0x14006c8ca  push    rbp
0x14006c8cb  mov     rbp, rsp
0x14006c8ce  sub     rsp, 80h
0x14006c8d5  mov     rax, cs:__security_cookie
0x14006c8dc  xor     rax, rsp
0x14006c8df  mov     [rbp+var_8], rax
0x14006c8e3  xor     edi, edi
0x14006c8e5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14006c8eb  lea     rax, [rbp+SidToCheck]
0x14006c8ef  mov     [rbp+IsMember], edi
0x14006c8f2  mov     [rsp+80h+pSid], rax; pSid
0x14006c8f7  mov     rbx, rcx
0x14006c8fa  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14006c8fe  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14006c902  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14006c906  lea     r8d, [rdi+12h]; nSubAuthority0
0x14006c90a  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14006c90e  xor     r9d, r9d; nSubAuthority1
0x14006c911  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14006c915  mov     dl, 1; nSubAuthorityCount
0x14006c917  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14006c91b  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14006c91f  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14006c922  mov     [rbp+SidToCheck], rdi
0x14006c926  call    cs:__imp_AllocateAndInitializeSid
0x14006c92c  test    eax, eax
0x14006c92e  jz      short loc_14006C98D
0x14006c930  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14006c934  lea     r8, [rbp+IsMember]; IsMember
0x14006c938  mov     rcx, rbx; TokenHandle
0x14006c93b  call    cs:__imp_CheckTokenMembership
0x14006c941  test    eax, eax
0x14006c943  jnz     short loc_14006C981
0x14006c945  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c94c  lea     rax, WPP_GLOBAL_Control
0x14006c953  cmp     rcx, rax
0x14006c956  jz      short loc_14006C981
0x14006c958  test    byte ptr [rcx+1Ch], 1
0x14006c95c  jz      short loc_14006C981
0x14006c95e  call    cs:__imp_GetLastError
0x14006c964  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c96b  lea     edx, [rdi+4Dh]
0x14006c96e  mov     r9d, eax
0x14006c971  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14006c978  mov     rcx, [rcx+10h]
0x14006c97c  call    WPP_SF_d
0x14006c981  mov     rcx, [rbp+SidToCheck]; pSid
0x14006c985  call    cs:__imp_FreeSid
0x14006c98b  jmp     short loc_14006C9CB
0x14006c98d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c994  lea     rax, WPP_GLOBAL_Control
0x14006c99b  cmp     rcx, rax
0x14006c99e  jz      short loc_14006C9CB
0x14006c9a0  test    byte ptr [rcx+1Ch], 1
0x14006c9a4  jz      short loc_14006C9CB
0x14006c9a6  call    cs:__imp_GetLastError
0x14006c9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c9b3  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14006c9ba  mov     edx, 4Eh ; 'N'
0x14006c9bf  mov     r9d, eax
0x14006c9c2  mov     rcx, [rcx+10h]
0x14006c9c6  call    WPP_SF_d
0x14006c9cb  mov     eax, [rbp+IsMember]
0x14006c9ce  mov     rcx, [rbp+var_8]
0x14006c9d2  xor     rcx, rsp; StackCookie
0x14006c9d5  call    __security_check_cookie
0x14006c9da  lea     r11, [rsp+80h+var_s0]
0x14006c9e2  mov     rbx, [r11+18h]
0x14006c9e6  mov     rdi, [r11+20h]
0x14006c9ea  mov     rsp, r11
0x14006c9ed  pop     rbp
0x14006c9ee  retn
```
