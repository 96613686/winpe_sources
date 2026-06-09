# CLdap::Search2(ushort const *,ulong,ushort const *,ushort const * *,int)

- ea: `0x1800142f0`
- end: `0x18001456d`
- name: `?Search2@CLdap@@QEAAPEAXPEBGK0PEAPEBGH@Z`
- size: `637`
- prototype: `void *__fastcall(CLdap *__hidden this, PWSTR DistinguishedName, ULONG ScopeOfSearch, PWSTR SearchFilter, PZPWSTR, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x1800017a8`
- `0x1800139d0`
- `0x1800142f0`
- `0x180014800`
- `0x18002e468`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014390`
- `msvcrt!_wcsicmp` at `0x180014390`
- `KERNEL32!SetLastError` at `0x18001453d`
- `KERNEL32!SetLastError` at `0x18001453d`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001446a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001446a`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800144dc`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800144dc`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800144f8`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800144f8`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x1800144a2`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x1800144a2`
- `WLDAP32!__imp_ldap_search_abandon_page` at `0x180014513`
- `WLDAP32!__imp_ldap_search_abandon_page` at `0x180014513`
- `WLDAP32!__imp_ldap_search_init_pageW` at `0x18001444e`
- `WLDAP32!__imp_ldap_search_init_pageW` at `0x18001444e`

## string_xrefs

- `0x180014386`: `ntSecurityDescriptor`

## pseudocode

```c
PLDAP **__fastcall CLdap::Search2(
        PLDAP *this,
        PWSTR DistinguishedName,
        ULONG ScopeOfSearch,
        PWSTR SearchFilter,
        const wchar_t **AttributeList,
        ULONG AttributesOnly)
{
  int v6; // edi
  const wchar_t *v11; // rax
  __int64 v12; // rbx
  const wchar_t *v13; // rdx
  const wchar_t *v14; // r8
  PLDAP **v15; // rax
  PLDAP **v16; // rbx
  struct ldapsearch *inited; // rax
  LDAPMessage **v18; // rsi
  unsigned int LastError; // eax
  ULONG next_page_s; // edi
  ULONG *v21; // r12
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  struct ldapsearch *v26; // rdx
  struct l_timeval timeout; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v29[3]; // [rsp+70h] [rbp-39h] BYREF
  char v30; // [rsp+88h] [rbp-21h]
  int v31; // [rsp+89h] [rbp-20h]
  __int16 v32; // [rsp+8Dh] [rbp-1Ch]
  char v33; // [rsp+8Fh] [rbp-1Ah]
  _QWORD v34[2]; // [rsp+90h] [rbp-19h] BYREF
  int v35; // [rsp+A0h] [rbp-9h] BYREF
  char v36; // [rsp+A4h] [rbp-5h]

  v6 = 0;
  timeout = 0;
  v34[1] = 0;
  v29[1] = 5;
  v29[0] = L"1.2.840.113556.1.4.801";
  v29[2] = &v35;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34[0] = v29;
  v11 = *AttributeList;
  v30 = 1;
  v35 = 16909104;
  v36 = 7;
  timeout.tv_sec = 58;
  if ( v11 )
  {
    LODWORD(v12) = 0;
    while ( _wcsicmp(v11, L"ntSecurityDescriptor") )
    {
      v12 = (unsigned int)(v12 + 1);
      v11 = AttributeList[v12];
      if ( !v11 )
        goto LABEL_7;
    }
  }
  v6 = 1;
LABEL_7:
  if ( g_ErrLibTraceFunction )
  {
    v13 = &psz;
    v14 = &psz;
    if ( SearchFilter )
      v14 = SearchFilter;
    if ( DistinguishedName )
      v13 = DistinguishedName;
    g_ErrLibTraceFunction(L"CLdap::Search2: BaseDN=%s, Filter=%s, Scope=%u\n", v13, v14, ScopeOfSearch);
  }
  v15 = (PLDAP **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v16 = 0;
    next_page_s = 8;
    goto LABEL_28;
  }
  v15[1] = 0;
  v15[2] = 0;
  *((_DWORD *)v15 + 6) = 0;
  *v15 = this;
  inited = ldap_search_init_pageW(
             *this,
             DistinguishedName,
             ScopeOfSearch,
             SearchFilter,
             (PZPWSTR)AttributeList,
             AttributesOnly,
             (PLDAPControlW *)((unsigned __int64)v34 & -(__int64)(v6 != 0)),
             0,
             0,
             0xFFFFFFFF,
             0);
  v16[1] = (PLDAP *)inited;
  v18 = (LDAPMessage **)(v16 + 2);
  if ( inited )
  {
    v21 = (ULONG *)(v16 + 3);
    next_page_s = ldap_get_next_page_s(*this, inited, &timeout, 0x9C4u, (ULONG *)v16 + 6, (LDAPMessage **)v16 + 2);
    if ( !(unsigned int)ElValidateWin32_5(next_page_s, v22, v23, 0x25Fu) )
    {
      if ( !*v21 )
        *v21 = ldap_count_entries(*this, *v18);
      goto LABEL_21;
    }
    LastError = ElValidateWin32_5(next_page_s, v24, v25, 0x261u);
  }
  else
  {
    LastError = LdapGetLastError();
  }
  next_page_s = CLdap::GetLdapErrorCode((CLdap *)this, LastError);
LABEL_21:
  if ( next_page_s )
  {
    if ( *v18 )
      ldap_msgfree(*v18);
    v26 = (struct ldapsearch *)v16[1];
    if ( v26 )
      ldap_search_abandon_page(**v16, v26);
    *v18 = 0;
    v16[1] = 0;
    operator delete(v16);
    v16 = 0;
  }
LABEL_28:
  SetLastError(next_page_s);
  return v16;
}

```

## disassembly

```asm
0x1800142f0  push    rbp
0x1800142f2  push    rbx
0x1800142f3  push    rsi
0x1800142f4  push    rdi
0x1800142f5  push    r12
0x1800142f7  push    r13
0x1800142f9  push    r14
0x1800142fb  push    r15
0x1800142fd  lea     rbp, [rsp-0Fh]
0x180014302  sub     rsp, 0B8h
0x180014309  mov     rax, cs:__security_cookie
0x180014310  xor     rax, rsp
0x180014313  mov     [rbp+47h+var_48], rax
0x180014317  mov     eax, [rbp+47h+arg_28]
0x18001431a  xor     edi, edi
0x18001431c  and     qword ptr [rbp+47h+timeout.tv_sec], rdi
0x180014320  mov     r12, r9
0x180014323  mov     rsi, [rbp+47h+arg_20]
0x180014327  mov     r13d, r8d
0x18001432a  and     [rbp+47h+var_58], rdi
0x18001432e  mov     r14, rdx
0x180014331  mov     [rbp+47h+var_90], eax
0x180014334  mov     r15, rcx
0x180014337  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18001433e  mov     [rbp+47h+var_78], 5
0x180014346  mov     [rbp+47h+var_80], rax
0x18001434a  lea     rax, [rbp+47h+var_50]
0x18001434e  mov     [rbp+47h+var_70], rax
0x180014352  xor     eax, eax
0x180014354  mov     [rbp+47h+var_67], eax
0x180014357  mov     [rbp+47h+var_63], ax
0x18001435b  mov     [rbp+47h+var_61], al
0x18001435e  lea     rax, [rbp+47h+var_80]
0x180014362  mov     [rbp+47h+var_60], rax
0x180014366  mov     rax, [rsi]
0x180014369  mov     [rbp+47h+var_68], 1
0x18001436d  mov     [rbp+47h+var_50], 1020330h
0x180014374  mov     [rbp+47h+var_4C], 7
0x180014378  mov     [rbp+47h+timeout.tv_sec], 3Ah ; ':'
0x18001437f  test    rax, rax
0x180014382  jz      short loc_1800143AD
0x180014384  xor     ebx, ebx
0x180014386  lea     rdx, aNtsecuritydesc; "ntSecurityDescriptor"
0x18001438d  mov     rcx, rax; String1
0x180014390  call    cs:__imp__wcsicmp
0x180014397  nop     dword ptr [rax+rax+00h]
0x18001439c  test    eax, eax
0x18001439e  jz      short loc_1800143AD
0x1800143a0  inc     ebx
0x1800143a2  mov     rax, [rsi+rbx*8]
0x1800143a6  test    rax, rax
0x1800143a9  jnz     short loc_180014386
0x1800143ab  jmp     short loc_1800143B2
0x1800143ad  mov     edi, 1
0x1800143b2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800143b9  test    rax, rax
0x1800143bc  jz      short loc_1800143E5
0x1800143be  test    r12, r12
0x1800143c1  lea     rdx, psz
0x1800143c8  mov     r8, rdx
0x1800143cb  lea     rcx, aCldapSearch2Ba; "CLdap::Search2: BaseDN=%s, Filter=%s, S"...
0x1800143d2  cmovnz  r8, r12
0x1800143d6  mov     r9d, r13d
0x1800143d9  test    r14, r14
0x1800143dc  cmovnz  rdx, r14
0x1800143e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800143ec  mov     ecx, 20h ; ' '; unsigned __int64
0x1800143f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800143f6  xor     edx, edx
0x1800143f8  mov     rbx, rax
0x1800143fb  test    rax, rax
0x1800143fe  jz      loc_180014533
0x180014404  mov     [rsp+0F0h+SortKeys], rdx; SortKeys
0x180014409  lea     rcx, [rbp+47h+var_60]
0x18001440d  mov     [rax+8], rdx
0x180014411  neg     edi
0x180014413  mov     [rax+10h], rdx
0x180014417  mov     r9, r12; SearchFilter
0x18001441a  mov     [rax+18h], edx
0x18001441d  mov     r8d, r13d; ScopeOfSearch
0x180014420  mov     [rax], r15
0x180014423  sbb     rax, rax
0x180014426  or      [rsp+0F0h+var_A8], 0FFFFFFFFh
0x18001442b  and     rax, rcx
0x18001442e  mov     rcx, [r15]; ExternalHandle
0x180014431  mov     [rsp+0F0h+PageTimeLimit], edx; PageTimeLimit
0x180014435  mov     [rsp+0F0h+ClientControls], rdx; ClientControls
0x18001443a  mov     rdx, r14; DistinguishedName
0x18001443d  mov     [rsp+0F0h+ServerControls], rax; ServerControls
0x180014442  mov     eax, [rbp+47h+var_90]
0x180014445  mov     [rsp+0F0h+AttributesOnly], eax; AttributesOnly
0x180014449  mov     [rsp+0F0h+AttributeList], rsi; AttributeList
0x18001444e  call    cs:__imp_ldap_search_init_pageW
0x180014455  nop     dword ptr [rax+rax+00h]
0x18001445a  xor     r13d, r13d
0x18001445d  mov     [rbx+8], rax
0x180014461  lea     rsi, [rbx+10h]
0x180014465  test    rax, rax
0x180014468  jnz     short loc_180014484
0x18001446a  call    cs:__imp_LdapGetLastError
0x180014471  nop     dword ptr [rax+rax+00h]
0x180014476  mov     edx, eax; unsigned int
0x180014478  mov     rcx, r15; this
0x18001447b  call    ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
0x180014480  mov     edi, eax
0x180014482  jmp     short loc_1800144EC
0x180014484  mov     rcx, [r15]; ExternalHandle
0x180014487  lea     r12, [rbx+18h]
0x18001448b  mov     qword ptr [rsp+0F0h+AttributesOnly], rsi; Results
0x180014490  lea     r8, [rbp+47h+timeout]; timeout
0x180014494  mov     r9d, 9C4h; PageSize
0x18001449a  mov     [rsp+0F0h+AttributeList], r12; TotalCount
0x18001449f  mov     rdx, rax; SearchHandle
0x1800144a2  call    cs:__imp_ldap_get_next_page_s
0x1800144a9  nop     dword ptr [rax+rax+00h]
0x1800144ae  mov     ecx, eax
0x1800144b0  mov     r9d, 25Fh
0x1800144b6  mov     edi, eax
0x1800144b8  call    ElValidateWin32_5
0x1800144bd  test    eax, eax
0x1800144bf  jz      short loc_1800144D0
0x1800144c1  mov     r9d, 261h
0x1800144c7  mov     ecx, edi
0x1800144c9  call    ElValidateWin32_5
0x1800144ce  jmp     short loc_180014476
0x1800144d0  cmp     [r12], r13d
0x1800144d4  jnz     short loc_1800144EC
0x1800144d6  mov     rdx, [rsi]; res
0x1800144d9  mov     rcx, [r15]; ld
0x1800144dc  call    cs:__imp_ldap_count_entries
0x1800144e3  nop     dword ptr [rax+rax+00h]
0x1800144e8  mov     [r12], eax
0x1800144ec  test    edi, edi
0x1800144ee  jz      short loc_18001453B
0x1800144f0  mov     rcx, [rsi]; res
0x1800144f3  test    rcx, rcx
0x1800144f6  jz      short loc_180014504
0x1800144f8  call    cs:__imp_ldap_msgfree
0x1800144ff  nop     dword ptr [rax+rax+00h]
0x180014504  mov     rdx, [rbx+8]; SearchBlock
0x180014508  test    rdx, rdx
0x18001450b  jz      short loc_18001451F
0x18001450d  mov     rcx, [rbx]
0x180014510  mov     rcx, [rcx]; ExternalHandle
0x180014513  call    cs:__imp_ldap_search_abandon_page
0x18001451a  nop     dword ptr [rax+rax+00h]
0x18001451f  mov     rcx, rbx; lpMem
0x180014522  mov     [rsi], r13
0x180014525  mov     [rbx+8], r13
0x180014529  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001452e  mov     rbx, r13
0x180014531  jmp     short loc_18001453B
0x180014533  mov     rbx, rdx
0x180014536  mov     edi, 8
0x18001453b  mov     ecx, edi; dwErrCode
0x18001453d  call    cs:__imp_SetLastError
0x180014544  nop     dword ptr [rax+rax+00h]
0x180014549  mov     rax, rbx
0x18001454c  mov     rcx, [rbp+47h+var_48]
0x180014550  xor     rcx, rsp; StackCookie
0x180014553  call    __security_check_cookie
0x180014558  add     rsp, 0B8h
0x18001455f  pop     r15
0x180014561  pop     r14
0x180014563  pop     r13
0x180014565  pop     r12
0x180014567  pop     rdi
0x180014568  pop     rsi
0x180014569  pop     rbx
0x18001456a  pop     rbp
0x18001456b  retn
```
