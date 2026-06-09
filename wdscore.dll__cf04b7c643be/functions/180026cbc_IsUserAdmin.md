# IsUserAdmin

- ea: `0x180026cbc`
- end: `0x180026db3`
- name: `IsUserAdmin`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001aa9c`

## callees

- `0x180026cbc`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d73`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026d21`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026d21`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026d3e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026d3e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026d65`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026d65`

## pseudocode

```c
__int64 IsUserAdmin()
{
  DWORD LastError; // ebx
  unsigned int v1; // edi
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  LastError = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v1 = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    IsMember = 0;
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
      v1 = IsMember;
    else
      LastError = GetLastError();
    FreeSid(SidToCheck);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return v1;
}

```

## disassembly

```asm
0x180026cbc  mov     [rsp-8+arg_0], rbx
0x180026cc1  mov     [rsp-8+arg_8], rdi
0x180026cc6  push    rbp
0x180026cc7  mov     rbp, rsp
0x180026cca  sub     rsp, 80h
0x180026cd1  mov     rax, cs:__security_cookie
0x180026cd8  xor     rax, rsp
0x180026cdb  mov     [rbp+var_8], rax
0x180026cdf  xor     ebx, ebx
0x180026ce1  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180026ce7  lea     rax, [rbp+SidToCheck]
0x180026ceb  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180026cee  mov     [rsp+80h+pSid], rax; pSid
0x180026cf3  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180026cf7  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180026cfb  mov     r9d, 220h; nSubAuthority1
0x180026d01  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180026d05  lea     r8d, [rbx+20h]; nSubAuthority0
0x180026d09  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180026d0d  mov     dl, 2; nSubAuthorityCount
0x180026d0f  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180026d13  mov     edi, ebx
0x180026d15  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180026d19  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180026d1d  mov     [rbp+SidToCheck], rbx
0x180026d21  call    cs:__imp_AllocateAndInitializeSid
0x180026d28  nop     dword ptr [rax+rax+00h]
0x180026d2d  test    eax, eax
0x180026d2f  jz      short loc_180026D73
0x180026d31  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180026d35  lea     r8, [rbp+IsMember]; IsMember
0x180026d39  xor     ecx, ecx; TokenHandle
0x180026d3b  mov     [rbp+IsMember], ebx
0x180026d3e  call    cs:__imp_CheckTokenMembership
0x180026d45  nop     dword ptr [rax+rax+00h]
0x180026d4a  test    eax, eax
0x180026d4c  jz      short loc_180026D53
0x180026d4e  mov     edi, [rbp+IsMember]
0x180026d51  jmp     short loc_180026D61
0x180026d53  call    cs:__imp_GetLastError
0x180026d5a  nop     dword ptr [rax+rax+00h]
0x180026d5f  mov     ebx, eax
0x180026d61  mov     rcx, [rbp+SidToCheck]; pSid
0x180026d65  call    cs:__imp_FreeSid
0x180026d6c  nop     dword ptr [rax+rax+00h]
0x180026d71  jmp     short loc_180026D81
0x180026d73  call    cs:__imp_GetLastError
0x180026d7a  nop     dword ptr [rax+rax+00h]
0x180026d7f  mov     ebx, eax
0x180026d81  mov     ecx, ebx; dwErrCode
0x180026d83  call    cs:__imp_SetLastError
0x180026d8a  nop     dword ptr [rax+rax+00h]
0x180026d8f  mov     eax, edi
0x180026d91  mov     rcx, [rbp+var_8]
0x180026d95  xor     rcx, rsp; StackCookie
0x180026d98  call    __security_check_cookie
0x180026d9d  lea     r11, [rsp+80h+var_s0]
0x180026da5  mov     rbx, [r11+10h]
0x180026da9  mov     rdi, [r11+18h]
0x180026dad  mov     rsp, r11
0x180026db0  pop     rbp
0x180026db1  retn
```
