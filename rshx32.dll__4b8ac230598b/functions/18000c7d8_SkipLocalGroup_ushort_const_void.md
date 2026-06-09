# SkipLocalGroup(ushort const *,void *)

- ea: `0x18000c7d8`
- end: `0x18000c89f`
- name: `?SkipLocalGroup@@YAHPEBGPEAX@Z`
- size: `199`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf90`

## callees

- `0x18000c7d8`
- `0x18001d370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c86b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c86b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000c856`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000c856`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000c836`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000c836`

## pseudocode

```c
_BOOL8 __fastcall SkipLocalGroup(const unsigned __int16 *a1, void *a2)
{
  int v3; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-448h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-444h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-440h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+50h] [rbp-438h] BYREF
  WCHAR Name[264]; // [rsp+260h] [rbp-228h] BYREF

  peUse = 0;
  cchName = 260;
  cchReferencedDomainName = 260;
  if ( LookupAccountSidW(a1, a2, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    if ( (unsigned int)peUse <= SidTypeUnknown )
    {
      v3 = 436;
      if ( _bittest(&v3, peUse) )
        return 1;
    }
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(a2);
  if ( !SidSubAuthorityCount )
    return 1;
  if ( *SidSubAuthorityCount )
    return *GetSidSubAuthority(a2, 0) == 32;
  return 0;
}

```

## disassembly

```asm
0x18000c7d8  push    rbx
0x18000c7da  sub     rsp, 480h
0x18000c7e1  mov     rax, cs:__security_cookie
0x18000c7e8  xor     rax, rsp
0x18000c7eb  mov     [rsp+488h+var_18], rax
0x18000c7f3  mov     eax, 104h
0x18000c7f8  mov     [rsp+488h+var_448], 0
0x18000c800  mov     [rsp+488h+cchName], eax
0x18000c804  lea     r9, [rsp+488h+cchName]; cchName
0x18000c809  mov     [rsp+488h+var_444], eax
0x18000c80d  lea     r8, [rsp+488h+Name]; Name
0x18000c815  lea     rax, [rsp+488h+var_448]
0x18000c81a  mov     rbx, rdx
0x18000c81d  mov     [rsp+488h+peUse], rax; peUse
0x18000c822  lea     rax, [rsp+488h+var_444]
0x18000c827  mov     [rsp+488h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000c82c  lea     rax, [rsp+488h+var_438]
0x18000c831  mov     [rsp+488h+ReferencedDomainName], rax; ReferencedDomainName
0x18000c836  call    cs:__imp_LookupAccountSidW
0x18000c83c  test    eax, eax
0x18000c83e  jz      short loc_18000C853
0x18000c840  mov     eax, [rsp+488h+var_448]
0x18000c844  cmp     eax, 8
0x18000c847  ja      short loc_18000C853
0x18000c849  mov     ecx, 1B4h
0x18000c84e  bt      ecx, eax
0x18000c851  jb      short loc_18000C881
0x18000c853  mov     rcx, rbx; pSid
0x18000c856  call    cs:__imp_GetSidSubAuthorityCount
0x18000c85c  test    rax, rax
0x18000c85f  jz      short loc_18000C881
0x18000c861  cmp     byte ptr [rax], 1
0x18000c864  jb      short loc_18000C87D
0x18000c866  xor     edx, edx; nSubAuthority
0x18000c868  mov     rcx, rbx; pSid
0x18000c86b  call    cs:__imp_GetSidSubAuthority
0x18000c871  xor     ecx, ecx
0x18000c873  cmp     dword ptr [rax], 20h ; ' '
0x18000c876  setz    cl
0x18000c879  mov     eax, ecx
0x18000c87b  jmp     short loc_18000C886
0x18000c87d  xor     eax, eax
0x18000c87f  jmp     short loc_18000C886
0x18000c881  mov     eax, 1
0x18000c886  mov     rcx, [rsp+488h+var_18]
0x18000c88e  xor     rcx, rsp; StackCookie
0x18000c891  call    __security_check_cookie
0x18000c896  add     rsp, 480h
0x18000c89d  pop     rbx
0x18000c89e  retn
```
