# IsUserAdminOrLocalService(void)

- ea: `0x18001aa9c`
- end: `0x18001ab6f`
- name: `?IsUserAdminOrLocalService@@YAHXZ`
- size: `211`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001bd30`
- `0x18001c350`
- `0x18001c780`
- `0x18001ca90`
- `0x18001cb20`

## callees

- `0x18001aa9c`
- `0x180026cbc`
- `0x180027510`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ab0c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ab0c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ab29`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ab29`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ab3f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ab3f`

## pseudocode

```c
__int64 IsUserAdminOrLocalService(void)
{
  unsigned int v1; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( (unsigned int)IsUserAdmin() )
    return 1;
  v1 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    IsMember = 0;
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
      v1 = IsMember;
    FreeSid(SidToCheck);
  }
  return v1;
}

```

## disassembly

```asm
0x18001aa9c  mov     [rsp-8+arg_0], rbx
0x18001aaa1  mov     [rsp-8+arg_8], rdi
0x18001aaa6  push    rbp
0x18001aaa7  mov     rbp, rsp
0x18001aaaa  sub     rsp, 80h
0x18001aab1  mov     rax, cs:__security_cookie
0x18001aab8  xor     rax, rsp
0x18001aabb  mov     [rbp+var_8], rax
0x18001aabf  xor     edi, edi
0x18001aac1  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18001aac7  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18001aaca  mov     [rbp+SidToCheck], rdi
0x18001aace  call    IsUserAdmin
0x18001aad3  test    eax, eax
0x18001aad5  jz      short loc_18001AADC
0x18001aad7  lea     eax, [rdi+1]
0x18001aada  jmp     short loc_18001AB4D
0x18001aadc  lea     rax, [rbp+SidToCheck]
0x18001aae0  xor     r9d, r9d; nSubAuthority1
0x18001aae3  mov     [rsp+80h+pSid], rax; pSid
0x18001aae8  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001aaec  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18001aaf0  mov     dl, 1; nSubAuthorityCount
0x18001aaf2  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18001aaf6  mov     ebx, edi
0x18001aaf8  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18001aafc  lea     r8d, [r9+13h]; nSubAuthority0
0x18001ab00  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18001ab04  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18001ab08  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18001ab0c  call    cs:__imp_AllocateAndInitializeSid
0x18001ab13  nop     dword ptr [rax+rax+00h]
0x18001ab18  test    eax, eax
0x18001ab1a  jz      short loc_18001AB4B
0x18001ab1c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18001ab20  lea     r8, [rbp+IsMember]; IsMember
0x18001ab24  xor     ecx, ecx; TokenHandle
0x18001ab26  mov     [rbp+IsMember], edi
0x18001ab29  call    cs:__imp_CheckTokenMembership
0x18001ab30  nop     dword ptr [rax+rax+00h]
0x18001ab35  mov     rcx, [rbp+SidToCheck]; pSid
0x18001ab39  test    eax, eax
0x18001ab3b  cmovnz  ebx, [rbp+IsMember]
0x18001ab3f  call    cs:__imp_FreeSid
0x18001ab46  nop     dword ptr [rax+rax+00h]
0x18001ab4b  mov     eax, ebx
0x18001ab4d  mov     rcx, [rbp+var_8]
0x18001ab51  xor     rcx, rsp; StackCookie
0x18001ab54  call    __security_check_cookie
0x18001ab59  lea     r11, [rsp+80h+var_s0]
0x18001ab61  mov     rbx, [r11+10h]
0x18001ab65  mov     rdi, [r11+18h]
0x18001ab69  mov     rsp, r11
0x18001ab6c  pop     rbp
0x18001ab6d  retn
```
