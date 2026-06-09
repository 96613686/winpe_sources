# CAccountGroupPage::_LookupLocalGroupName(ulong,ushort *,ulong)

- ea: `0x18000f668`
- end: `0x18000f7a1`
- name: `?_LookupLocalGroupName@CAccountGroupPage@@AEAAJKPEAGK@Z`
- size: `313`
- prototype: `__int64 __fastcall(CAccountGroupPage *this, DWORD, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ee70`

## callees

- `0x18000f668`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f751`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000f775`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000f775`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000f6e0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000f6e0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000f743`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000f743`

## pseudocode

```c
__int64 __fastcall CAccountGroupPage::_LookupLocalGroupName(CAccountGroupPage *this, DWORD a2, unsigned __int16 *a3)
{
  signed int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  _SID_NAME_USE peUse; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+80h] [rbp-80h] BYREF

  cchName = 257;
  Sid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, a2, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    cchReferencedDomainName = 257;
    peUse = 0;
    if ( LookupAccountSidW(0, Sid, a3, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    FreeSid(Sid);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f668  mov     [rsp-8+arg_0], rbx
0x18000f66d  mov     [rsp-8+arg_18], rdi
0x18000f672  push    rbp
0x18000f673  lea     rbp, [rsp-1A0h]
0x18000f67b  sub     rsp, 2A0h
0x18000f682  mov     rax, cs:__security_cookie
0x18000f689  xor     rax, rsp
0x18000f68c  mov     [rbp+1A0h+var_10], rax
0x18000f693  xor     edi, edi
0x18000f695  mov     [rsp+2A0h+cchName], 101h
0x18000f69d  lea     rax, [rsp+2A0h+Sid]
0x18000f6a2  mov     [rsp+2A0h+Sid], rdi
0x18000f6a7  mov     [rsp+2A0h+pSid], rax; pSid
0x18000f6ac  lea     rcx, [rsp+2A0h+pIdentifierAuthority]; pIdentifierAuthority
0x18000f6b1  mov     [rsp+2A0h+nSubAuthority7], edi; nSubAuthority7
0x18000f6b5  mov     rbx, r8
0x18000f6b8  mov     [rsp+2A0h+nSubAuthority6], edi; nSubAuthority6
0x18000f6bc  lea     r8d, [rdi+20h]; nSubAuthority0
0x18000f6c0  mov     [rsp+2A0h+nSubAuthority5], edi; nSubAuthority5
0x18000f6c4  mov     r9d, edx; nSubAuthority1
0x18000f6c7  mov     [rsp+2A0h+nSubAuthority4], edi; nSubAuthority4
0x18000f6cb  mov     dl, 2; nSubAuthorityCount
0x18000f6cd  mov     [rsp+2A0h+nSubAuthority3], edi; nSubAuthority3
0x18000f6d1  mov     [rsp+2A0h+nSubAuthority2], edi; nSubAuthority2
0x18000f6d5  mov     dword ptr [rsp+2A0h+pIdentifierAuthority.Value], edi
0x18000f6d9  mov     word ptr [rsp+2A0h+pIdentifierAuthority.Value+4], 500h
0x18000f6e0  call    cs:__imp_AllocateAndInitializeSid
0x18000f6e6  test    eax, eax
0x18000f6e8  jnz     short loc_18000F70B
0x18000f6ea  call    cs:__imp_GetLastError
0x18000f6f0  mov     ebx, eax
0x18000f6f2  test    eax, eax
0x18000f6f4  jle     short loc_18000F6FF
0x18000f6f6  movzx   ebx, ax
0x18000f6f9  or      ebx, 80070000h
0x18000f6ff  test    ebx, ebx
0x18000f701  mov     eax, 80004005h
0x18000f706  cmovns  ebx, eax
0x18000f709  jmp     short loc_18000F77B
0x18000f70b  mov     rdx, [rsp+2A0h+Sid]; Sid
0x18000f710  lea     rax, [rsp+2A0h+peUse]
0x18000f715  mov     qword ptr [rsp+2A0h+nSubAuthority4], rax; peUse
0x18000f71a  lea     r9, [rsp+2A0h+cchName]; cchName
0x18000f71f  lea     rax, [rsp+2A0h+cchReferencedDomainName]
0x18000f724  mov     [rsp+2A0h+cchReferencedDomainName], 101h
0x18000f72c  mov     qword ptr [rsp+2A0h+nSubAuthority3], rax; cchReferencedDomainName
0x18000f731  mov     r8, rbx; Name
0x18000f734  lea     rax, [rbp+1A0h+ReferencedDomainName]
0x18000f738  mov     [rsp+2A0h+peUse], edi
0x18000f73c  xor     ecx, ecx; lpSystemName
0x18000f73e  mov     qword ptr [rsp+2A0h+nSubAuthority2], rax; ReferencedDomainName
0x18000f743  call    cs:__imp_LookupAccountSidW
0x18000f749  test    eax, eax
0x18000f74b  jz      short loc_18000F751
0x18000f74d  mov     ebx, edi
0x18000f74f  jmp     short loc_18000F770
0x18000f751  call    cs:__imp_GetLastError
0x18000f757  mov     ebx, eax
0x18000f759  test    eax, eax
0x18000f75b  jle     short loc_18000F766
0x18000f75d  movzx   ebx, ax
0x18000f760  or      ebx, 80070000h
0x18000f766  test    ebx, ebx
0x18000f768  mov     eax, 80004005h
0x18000f76d  cmovns  ebx, eax
0x18000f770  mov     rcx, [rsp+2A0h+Sid]; pSid
0x18000f775  call    cs:__imp_FreeSid
0x18000f77b  mov     eax, ebx
0x18000f77d  mov     rcx, [rbp+1A0h+var_10]
0x18000f784  xor     rcx, rsp; StackCookie
0x18000f787  call    __security_check_cookie
0x18000f78c  lea     r11, [rsp+2A0h+var_s0]
0x18000f794  mov     rbx, [r11+10h]
0x18000f798  mov     rdi, [r11+28h]
0x18000f79c  mov     rsp, r11
0x18000f79f  pop     rbp
0x18000f7a0  retn
```
