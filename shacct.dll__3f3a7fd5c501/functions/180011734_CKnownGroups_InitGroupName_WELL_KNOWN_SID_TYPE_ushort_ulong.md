# CKnownGroups::_InitGroupName(WELL_KNOWN_SID_TYPE,ushort *,ulong)

- ea: `0x180011734`
- end: `0x1800117e5`
- name: `?_InitGroupName@CKnownGroups@@AEAAJW4WELL_KNOWN_SID_TYPE@@PEAGK@Z`
- size: `177`
- prototype: `int(CKnownGroups *__hidden this, enum WELL_KNOWN_SID_TYPE, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800109d8`

## callees

- `0x18000bcc0`
- `0x18000c240`
- `0x180011734`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180011768`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180011768`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800117b9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800117b9`

## pseudocode

```c
__int64 __fastcall CKnownGroups::_InitGroupName(CKnownGroups *this, enum WELL_KNOWN_SID_TYPE a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  DWORD cbSid; // [rsp+30h] [rbp-98h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-94h] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-8Ch] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-68h] BYREF

  cbSid = 68;
  if ( CreateWellKnownSid(a2, 0, pSid, &cbSid) || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    cchName = 257;
    cchReferencedDomainName = 16;
    peUse = 0;
    if ( LookupAccountSidLocalW(pSid, a3, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      return 0;
    else
      return ResultFromKnownLastError();
  }
  return result;
}

```

## disassembly

```asm
0x180011734  push    rbx
0x180011736  sub     rsp, 0C0h
0x18001173d  mov     rax, cs:__security_cookie
0x180011744  xor     rax, rsp
0x180011747  mov     [rsp+0C8h+var_18], rax
0x18001174f  mov     rbx, r8
0x180011752  mov     [rsp+0C8h+cbSid], 44h ; 'D'
0x18001175a  mov     ecx, edx; WellKnownSidType
0x18001175c  lea     r8, [rsp+0C8h+pSid]; pSid
0x180011761  xor     edx, edx; DomainSid
0x180011763  lea     r9, [rsp+0C8h+cbSid]; cbSid
0x180011768  call    cs:__imp_CreateWellKnownSid
0x18001176e  test    eax, eax
0x180011770  jnz     short loc_18001177B
0x180011772  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011777  test    eax, eax
0x180011779  js      short loc_1800117CC
0x18001177b  lea     rax, [rsp+0C8h+var_94]
0x180011780  mov     [rsp+0C8h+cchName], 101h
0x180011788  mov     [rsp+0C8h+peUse], rax; peUse
0x18001178d  lea     r9, [rsp+0C8h+ReferencedDomainName]; ReferencedDomainName
0x180011792  lea     rax, [rsp+0C8h+var_90]
0x180011797  mov     [rsp+0C8h+var_90], 10h
0x18001179f  lea     r8, [rsp+0C8h+cchName]; cchName
0x1800117a4  mov     [rsp+0C8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800117a9  mov     rdx, rbx; Name
0x1800117ac  mov     [rsp+0C8h+var_94], 0
0x1800117b4  lea     rcx, [rsp+0C8h+pSid]; Sid
0x1800117b9  call    cs:__imp_LookupAccountSidLocalW
0x1800117bf  test    eax, eax
0x1800117c1  jz      short loc_1800117C7
0x1800117c3  xor     eax, eax
0x1800117c5  jmp     short loc_1800117CC
0x1800117c7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800117cc  mov     rcx, [rsp+0C8h+var_18]
0x1800117d4  xor     rcx, rsp; StackCookie
0x1800117d7  call    __security_check_cookie
0x1800117dc  add     rsp, 0C0h
0x1800117e3  pop     rbx
0x1800117e4  retn
```
