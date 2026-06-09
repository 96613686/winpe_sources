# IsolationContainer::GetPackageCapabilitySid(void * *)

- ea: `0x1800466a0`
- end: `0x180046802`
- name: `?GetPackageCapabilitySid@IsolationContainer@@AEBA_NPEAPEAX@Z`
- size: `354`
- prototype: `bool __fastcall(IsolationContainer *__hidden this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a2a8`

## callees

- `0x18001b600`
- `0x1800466a0`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1800467be`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800467be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046720`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046731`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046742`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046752`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046762`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046772`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046786`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046720`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046731`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046742`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046752`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046762`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046772`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180046786`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180046709`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180046709`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1800466f3`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1800466f3`

## pseudocode

```c
char __fastcall IsolationContainer::GetPackageCapabilitySid(IsolationContainer *this, void **a2)
{
  _QWORD *v2; // rcx
  PSID v3; // r12
  DWORD SubAuthority7; // r15d
  DWORD SubAuthority6; // r14d
  DWORD SubAuthority5; // ebp
  DWORD SubAuthority4; // esi
  DWORD SubAuthority3; // edi
  char v9; // r13
  DWORD SubAuthority2; // ebx
  ULONG *SidSubAuthority; // rax
  PSID pSid; // [rsp+60h] [rbp-58h] BYREF
  PSID *Sid; // [rsp+68h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-48h] BYREF

  Sid = a2;
  v2 = (_QWORD *)((char *)this + 192);
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  pSid = 0;
  if ( v2[3] >= 8u )
    v2 = (_QWORD *)*v2;
  if ( (int)DeriveAppContainerSidFromAppContainerName(v2, &pSid) < 0 )
    goto LABEL_6;
  v3 = pSid;
  if ( *GetSidSubAuthorityCount(pSid) < 8u )
    goto LABEL_6;
  SubAuthority7 = *GetSidSubAuthority(v3, 7u);
  SubAuthority6 = *GetSidSubAuthority(v3, 6u);
  SubAuthority5 = *GetSidSubAuthority(v3, 5u);
  SubAuthority4 = *GetSidSubAuthority(v3, 4u);
  SubAuthority3 = *GetSidSubAuthority(v3, 3u);
  v9 = 1;
  SubAuthority2 = *GetSidSubAuthority(v3, 2u);
  SidSubAuthority = GetSidSubAuthority(v3, 1u);
  if ( RtlAllocateAndInitializeSid(
         &IdentifierAuthority,
         8u,
         3u,
         *SidSubAuthority,
         SubAuthority2,
         SubAuthority3,
         SubAuthority4,
         SubAuthority5,
         SubAuthority6,
         SubAuthority7,
         Sid) < 0 )
LABEL_6:
    v9 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
  return v9;
}

```

## disassembly

```asm
0x1800466a0  mov     [rsp+arg_10], rbx
0x1800466a5  push    rbp
0x1800466a6  push    rsi
0x1800466a7  push    rdi
0x1800466a8  push    r12
0x1800466aa  push    r13
0x1800466ac  push    r14
0x1800466ae  push    r15
0x1800466b0  sub     rsp, 80h
0x1800466b7  mov     rax, cs:__security_cookie
0x1800466be  xor     rax, rsp
0x1800466c1  mov     [rsp+0B8h+var_40], rax
0x1800466c6  xor     ebx, ebx
0x1800466c8  mov     [rsp+0B8h+var_50], rdx
0x1800466cd  add     rcx, 0C0h
0x1800466d4  mov     dword ptr [rsp+0B8h+IdentifierAuthority.Value], ebx
0x1800466d8  mov     word ptr [rsp+0B8h+IdentifierAuthority.Value+4], 0F00h
0x1800466df  mov     [rsp+0B8h+pSid], rbx
0x1800466e4  cmp     qword ptr [rcx+18h], 8
0x1800466e9  jb      short loc_1800466EE
0x1800466eb  mov     rcx, [rcx]
0x1800466ee  lea     rdx, [rsp+0B8h+pSid]
0x1800466f3  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x1800466f9  test    eax, eax
0x1800466fb  js      loc_1800467CA
0x180046701  mov     r12, [rsp+0B8h+pSid]
0x180046706  mov     rcx, r12; pSid
0x180046709  call    cs:__imp_GetSidSubAuthorityCount
0x18004670f  cmp     byte ptr [rax], 8
0x180046712  jb      loc_1800467CA
0x180046718  mov     edx, 7; nSubAuthority
0x18004671d  mov     rcx, r12; pSid
0x180046720  call    cs:__imp_GetSidSubAuthority
0x180046726  mov     edx, 6; nSubAuthority
0x18004672b  mov     rcx, r12; pSid
0x18004672e  mov     r15d, [rax]
0x180046731  call    cs:__imp_GetSidSubAuthority
0x180046737  mov     edx, 5; nSubAuthority
0x18004673c  mov     rcx, r12; pSid
0x18004673f  mov     r14d, [rax]
0x180046742  call    cs:__imp_GetSidSubAuthority
0x180046748  mov     edx, 4; nSubAuthority
0x18004674d  mov     rcx, r12; pSid
0x180046750  mov     ebp, [rax]
0x180046752  call    cs:__imp_GetSidSubAuthority
0x180046758  mov     edx, 3; nSubAuthority
0x18004675d  mov     rcx, r12; pSid
0x180046760  mov     esi, [rax]
0x180046762  call    cs:__imp_GetSidSubAuthority
0x180046768  mov     edx, 2; nSubAuthority
0x18004676d  mov     rcx, r12; pSid
0x180046770  mov     edi, [rax]
0x180046772  call    cs:__imp_GetSidSubAuthority
0x180046778  mov     r13d, 1
0x18004677e  mov     rcx, r12; pSid
0x180046781  mov     edx, r13d; nSubAuthority
0x180046784  mov     ebx, [rax]
0x180046786  call    cs:__imp_GetSidSubAuthority
0x18004678c  mov     rcx, [rsp+0B8h+var_50]
0x180046791  lea     r8d, [r13+2]; SubAuthority0
0x180046795  mov     [rsp+0B8h+Sid], rcx; Sid
0x18004679a  mov     dl, 8; SubAuthorityCount
0x18004679c  mov     [rsp+0B8h+SubAuthority7], r15d; SubAuthority7
0x1800467a1  lea     rcx, [rsp+0B8h+IdentifierAuthority]; IdentifierAuthority
0x1800467a6  mov     r9d, [rax]; SubAuthority1
0x1800467a9  mov     [rsp+0B8h+SubAuthority6], r14d; SubAuthority6
0x1800467ae  mov     [rsp+0B8h+SubAuthority5], ebp; SubAuthority5
0x1800467b2  mov     [rsp+0B8h+SubAuthority4], esi; SubAuthority4
0x1800467b6  mov     [rsp+0B8h+SubAuthority3], edi; SubAuthority3
0x1800467ba  mov     [rsp+0B8h+SubAuthority2], ebx; SubAuthority2
0x1800467be  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800467c4  xor     ebx, ebx
0x1800467c6  test    eax, eax
0x1800467c8  jns     short loc_1800467CD
0x1800467ca  mov     r13b, bl
0x1800467cd  lea     rcx, [rsp+0B8h+pSid]
0x1800467d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800467d7  mov     al, r13b
0x1800467da  mov     rcx, [rsp+0B8h+var_40]
0x1800467df  xor     rcx, rsp; StackCookie
0x1800467e2  call    __security_check_cookie
0x1800467e7  mov     rbx, [rsp+0B8h+arg_10]
0x1800467ef  add     rsp, 80h
0x1800467f6  pop     r15
0x1800467f8  pop     r14
0x1800467fa  pop     r13
0x1800467fc  pop     r12
0x1800467fe  pop     rdi
0x1800467ff  pop     rsi
0x180046800  pop     rbp
0x180046801  retn
```
