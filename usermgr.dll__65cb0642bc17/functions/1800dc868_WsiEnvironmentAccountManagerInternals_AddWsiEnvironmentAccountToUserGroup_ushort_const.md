# WsiEnvironmentAccountManagerInternals::AddWsiEnvironmentAccountToUserGroup(ushort const *)

- ea: `0x1800dc868`
- end: `0x1800dc9d4`
- name: `?AddWsiEnvironmentAccountToUserGroup@WsiEnvironmentAccountManagerInternals@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(WsiEnvironmentAccountManagerInternals *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d7da4`

## callees

- `0x18004aa68`
- `0x180061e1c`
- `0x18006f1c9`
- `0x1800dc868`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800dc8b6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800dc8b6`
- `samcli!NetLocalGroupAddMembers` at `0x1800dc96b`
- `samcli!NetLocalGroupAddMembers` at `0x1800dc96b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dc939`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dc939`

## string_xrefs

- `0x1800dc8cc`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dc97c`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`

## pseudocode

```c
__int64 __fastcall WsiEnvironmentAccountManagerInternals::AddWsiEnvironmentAccountToUserGroup(
        WsiEnvironmentAccountManagerInternals *this,
        const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  DWORD v6; // eax
  DWORD v7; // [rsp+30h] [rbp-D0h]
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE buf[8]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v14; // [rsp+68h] [rbp-98h]
  _BYTE pSid[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, pSid, &cbSid) )
  {
    v4 = 508;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
             v3);
  }
  memset_0(Name, 0, 0x202u);
  cchName = 257;
  cchReferencedDomainName = 16;
  peUse = SidTypeUnknown;
  *(_OWORD *)ReferencedDomainName = 0;
  v14 = 0;
  if ( !LookupAccountSidLocalW(pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v4 = 515;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
             v3);
  }
  *(_QWORD *)buf = this;
  v6 = NetLocalGroupAddMembers(0, Name, 3u, buf, 1u);
  if ( !v6 )
    return 0;
  v7 = v6;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x208,
    (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
    (const char *)0x80004005LL,
    (int)"group name: %ls, status: %d",
    (const char *)Name,
    v7);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800dc868  mov     [rsp-8+arg_8], rbx
0x1800dc86d  push    rbp
0x1800dc86e  lea     rbp, [rsp-1F0h]
0x1800dc876  sub     rsp, 2F0h
0x1800dc87d  mov     rax, cs:__security_cookie
0x1800dc884  xor     rax, rsp
0x1800dc887  mov     [rbp+1F0h+var_10], rax
0x1800dc88e  xor     edx, edx; Val
0x1800dc890  mov     rbx, rcx
0x1800dc893  lea     rcx, [rbp+1F0h+pSid]; void *
0x1800dc897  lea     r8d, [rdx+44h]; Size
0x1800dc89b  call    memset_0
0x1800dc8a0  xor     edx, edx; DomainSid
0x1800dc8a2  mov     [rsp+2F0h+cbSid], 44h ; 'D'
0x1800dc8aa  lea     r9, [rsp+2F0h+cbSid]; cbSid
0x1800dc8af  lea     r8, [rbp+1F0h+pSid]; pSid
0x1800dc8b3  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x1800dc8b6  call    cs:__imp_CreateWellKnownSid
0x1800dc8bc  test    eax, eax
0x1800dc8be  jnz     short loc_1800DC8DD
0x1800dc8c0  mov     edx, 1FCh; void *
0x1800dc8c5  mov     rcx, [rbp+1F8h]; this
0x1800dc8cc  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dc8d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dc8d8  jmp     loc_1800DC9B4
0x1800dc8dd  xor     edx, edx; Val
0x1800dc8df  lea     rcx, [rbp+1F0h+Name]; void *
0x1800dc8e3  mov     r8d, 202h; Size
0x1800dc8e9  call    memset_0
0x1800dc8ee  xorps   xmm0, xmm0
0x1800dc8f1  mov     [rsp+2F0h+cchName], 101h
0x1800dc8f9  lea     rax, [rsp+2F0h+var_2AC]
0x1800dc8fe  mov     [rsp+2F0h+var_2A8], 10h
0x1800dc906  mov     [rsp+2F0h+peUse], rax; peUse
0x1800dc90b  lea     r9, [rsp+2F0h+ReferencedDomainName]; ReferencedDomainName
0x1800dc910  lea     rax, [rsp+2F0h+var_2A8]
0x1800dc915  mov     [rsp+2F0h+var_2AC], 8
0x1800dc91d  lea     r8, [rsp+2F0h+cchName]; cchName
0x1800dc922  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800dc927  lea     rdx, [rbp+1F0h+Name]; Name
0x1800dc92b  lea     rcx, [rbp+1F0h+pSid]; Sid
0x1800dc92f  movups  xmmword ptr [rsp+2F0h+ReferencedDomainName], xmm0
0x1800dc934  movups  [rsp+2F0h+var_288], xmm0
0x1800dc939  call    cs:__imp_LookupAccountSidLocalW
0x1800dc93f  test    eax, eax
0x1800dc941  jnz     short loc_1800DC94D
0x1800dc943  mov     edx, 203h
0x1800dc948  jmp     loc_1800DC8C5
0x1800dc94d  lea     r9, [rsp+2F0h+buf]; buf
0x1800dc952  mov     qword ptr [rsp+2F0h+buf], rbx
0x1800dc957  mov     r8d, 3; level
0x1800dc95d  mov     dword ptr [rsp+2F0h+cchReferencedDomainName], 1; totalentries
0x1800dc965  lea     rdx, [rbp+1F0h+Name]; groupname
0x1800dc969  xor     ecx, ecx; servername
0x1800dc96b  call    cs:__imp_NetLocalGroupAddMembers
0x1800dc971  test    eax, eax
0x1800dc973  jz      short loc_1800DC9B2
0x1800dc975  mov     rcx, [rbp+1F8h]; this
0x1800dc97c  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dc983  mov     [rsp+2F0h+var_2C0], eax
0x1800dc987  mov     ebx, 80004005h
0x1800dc98c  lea     rax, [rbp+1F0h+Name]
0x1800dc990  mov     r9d, ebx; char *
0x1800dc993  mov     [rsp+2F0h+peUse], rax; char *
0x1800dc998  mov     edx, 208h; void *
0x1800dc99d  lea     rax, aGroupNameLsSta; "group name: %ls, status: %d"
0x1800dc9a4  mov     [rsp+2F0h+cchReferencedDomainName], rax; int
0x1800dc9a9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800dc9ae  mov     eax, ebx
0x1800dc9b0  jmp     short loc_1800DC9B4
0x1800dc9b2  xor     eax, eax
0x1800dc9b4  mov     rcx, [rbp+1F0h+var_10]
0x1800dc9bb  xor     rcx, rsp; StackCookie
0x1800dc9be  call    __security_check_cookie
0x1800dc9c3  mov     rbx, [rsp+2F0h+arg_8]
0x1800dc9cb  add     rsp, 2F0h
0x1800dc9d2  pop     rbp
0x1800dc9d3  retn
```
