# CLdap::Search2(ushort const *,ulong,ushort const *,ushort const * *,int)

- ea: `0x180014fc0`
- end: `0x180015244`
- name: `?Search2@CLdap@@QEAAPEAXPEBGK0PEAPEBGH@Z`
- size: `644`
- prototype: `void *__fastcall(CLdap *__hidden this, PWSTR DistinguishedName, ULONG ScopeOfSearch, PWSTR SearchFilter, PZPWSTR, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180015250`

## callees

- `0x180002158`
- `0x180014690`
- `0x180014fc0`
- `0x1800154f8`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015060`
- `msvcrt!_wcsicmp` at `0x180015060`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800151f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800151f9`
- `KERNEL32!SetLastError` at `0x180015214`
- `KERNEL32!SetLastError` at `0x180015214`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001513a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001513a`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800151ac`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800151ac`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800151c8`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800151c8`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x180015172`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x180015172`
- `WLDAP32!__imp_ldap_search_abandon_page` at `0x1800151e3`
- `WLDAP32!__imp_ldap_search_abandon_page` at `0x1800151e3`
- `WLDAP32!__imp_ldap_search_init_pageW` at `0x18001511e`
- `WLDAP32!__imp_ldap_search_init_pageW` at `0x18001511e`

## string_xrefs

- `0x180015056`: `ntSecurityDescriptor`

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
0x180014fc0  push    rbp
0x180014fc2  push    rbx
0x180014fc3  push    rsi
0x180014fc4  push    rdi
0x180014fc5  push    r12
0x180014fc7  push    r13
0x180014fc9  push    r14
0x180014fcb  push    r15
0x180014fcd  lea     rbp, [rsp-0Fh]
0x180014fd2  sub     rsp, 0B8h
0x180014fd9  mov     rax, cs:__security_cookie
0x180014fe0  xor     rax, rsp
0x180014fe3  mov     [rbp+47h+var_48], rax
0x180014fe7  mov     eax, [rbp+47h+arg_28]
0x180014fea  xor     edi, edi
0x180014fec  and     qword ptr [rbp+47h+timeout.tv_sec], rdi
0x180014ff0  mov     r12, r9
0x180014ff3  mov     rsi, [rbp+47h+arg_20]
0x180014ff7  mov     r13d, r8d
0x180014ffa  and     [rbp+47h+var_58], rdi
0x180014ffe  mov     r14, rdx
0x180015001  mov     [rbp+47h+var_90], eax
0x180015004  mov     r15, rcx
0x180015007  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18001500e  mov     [rbp+47h+var_78], 5
0x180015016  mov     [rbp+47h+var_80], rax
0x18001501a  lea     rax, [rbp+47h+var_50]
0x18001501e  mov     [rbp+47h+var_70], rax
0x180015022  xor     eax, eax
0x180015024  mov     [rbp+47h+var_67], eax
0x180015027  mov     [rbp+47h+var_63], ax
0x18001502b  mov     [rbp+47h+var_61], al
0x18001502e  lea     rax, [rbp+47h+var_80]
0x180015032  mov     [rbp+47h+var_60], rax
0x180015036  mov     rax, [rsi]
0x180015039  mov     [rbp+47h+var_68], 1
0x18001503d  mov     [rbp+47h+var_50], 1020330h
0x180015044  mov     [rbp+47h+var_4C], 7
0x180015048  mov     [rbp+47h+timeout.tv_sec], 3Ah ; ':'
0x18001504f  test    rax, rax
0x180015052  jz      short loc_18001507D
0x180015054  xor     ebx, ebx
0x180015056  lea     rdx, aNtsecuritydesc; "ntSecurityDescriptor"
0x18001505d  mov     rcx, rax; String1
0x180015060  call    cs:__imp__wcsicmp
0x180015067  nop     dword ptr [rax+rax+00h]
0x18001506c  test    eax, eax
0x18001506e  jz      short loc_18001507D
0x180015070  inc     ebx
0x180015072  mov     rax, [rsi+rbx*8]
0x180015076  test    rax, rax
0x180015079  jnz     short loc_180015056
0x18001507b  jmp     short loc_180015082
0x18001507d  mov     edi, 1
0x180015082  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015089  test    rax, rax
0x18001508c  jz      short loc_1800150B5
0x18001508e  test    r12, r12
0x180015091  lea     rdx, psz
0x180015098  mov     r8, rdx
0x18001509b  lea     rcx, aCldapSearch2Ba; "CLdap::Search2: BaseDN=%s, Filter=%s, S"...
0x1800150a2  cmovnz  r8, r12
0x1800150a6  mov     r9d, r13d
0x1800150a9  test    r14, r14
0x1800150ac  cmovnz  rdx, r14
0x1800150b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800150bc  mov     ecx, 20h ; ' '; unsigned __int64
0x1800150c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800150c6  xor     edx, edx
0x1800150c8  mov     rbx, rax
0x1800150cb  test    rax, rax
0x1800150ce  jz      loc_18001520A
0x1800150d4  mov     [rsp+0F0h+SortKeys], rdx; SortKeys
0x1800150d9  lea     rcx, [rbp+47h+var_60]
0x1800150dd  mov     [rax+8], rdx
0x1800150e1  neg     edi
0x1800150e3  mov     [rax+10h], rdx
0x1800150e7  mov     r9, r12; SearchFilter
0x1800150ea  mov     [rax+18h], edx
0x1800150ed  mov     r8d, r13d; ScopeOfSearch
0x1800150f0  mov     [rax], r15
0x1800150f3  sbb     rax, rax
0x1800150f6  or      [rsp+0F0h+var_A8], 0FFFFFFFFh
0x1800150fb  and     rax, rcx
0x1800150fe  mov     rcx, [r15]; ExternalHandle
0x180015101  mov     [rsp+0F0h+PageTimeLimit], edx; PageTimeLimit
0x180015105  mov     [rsp+0F0h+ClientControls], rdx; ClientControls
0x18001510a  mov     rdx, r14; DistinguishedName
0x18001510d  mov     [rsp+0F0h+ServerControls], rax; ServerControls
0x180015112  mov     eax, [rbp+47h+var_90]
0x180015115  mov     [rsp+0F0h+AttributesOnly], eax; AttributesOnly
0x180015119  mov     [rsp+0F0h+AttributeList], rsi; AttributeList
0x18001511e  call    cs:__imp_ldap_search_init_pageW
0x180015125  nop     dword ptr [rax+rax+00h]
0x18001512a  xor     r13d, r13d
0x18001512d  mov     [rbx+8], rax
0x180015131  lea     rsi, [rbx+10h]
0x180015135  test    rax, rax
0x180015138  jnz     short loc_180015154
0x18001513a  call    cs:__imp_LdapGetLastError
0x180015141  nop     dword ptr [rax+rax+00h]
0x180015146  mov     edx, eax; unsigned int
0x180015148  mov     rcx, r15; this
0x18001514b  call    ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
0x180015150  mov     edi, eax
0x180015152  jmp     short loc_1800151BC
0x180015154  mov     rcx, [r15]; ExternalHandle
0x180015157  lea     r12, [rbx+18h]
0x18001515b  mov     qword ptr [rsp+0F0h+AttributesOnly], rsi; Results
0x180015160  lea     r8, [rbp+47h+timeout]; timeout
0x180015164  mov     r9d, 9C4h; PageSize
0x18001516a  mov     [rsp+0F0h+AttributeList], r12; TotalCount
0x18001516f  mov     rdx, rax; SearchHandle
0x180015172  call    cs:__imp_ldap_get_next_page_s
0x180015179  nop     dword ptr [rax+rax+00h]
0x18001517e  mov     ecx, eax
0x180015180  mov     r9d, 25Fh
0x180015186  mov     edi, eax
0x180015188  call    ElValidateWin32_5
0x18001518d  test    eax, eax
0x18001518f  jz      short loc_1800151A0
0x180015191  mov     r9d, 261h
0x180015197  mov     ecx, edi
0x180015199  call    ElValidateWin32_5
0x18001519e  jmp     short loc_180015146
0x1800151a0  cmp     [r12], r13d
0x1800151a4  jnz     short loc_1800151BC
0x1800151a6  mov     rdx, [rsi]; res
0x1800151a9  mov     rcx, [r15]; ld
0x1800151ac  call    cs:__imp_ldap_count_entries
0x1800151b3  nop     dword ptr [rax+rax+00h]
0x1800151b8  mov     [r12], eax
0x1800151bc  test    edi, edi
0x1800151be  jz      short loc_180015212
0x1800151c0  mov     rcx, [rsi]; res
0x1800151c3  test    rcx, rcx
0x1800151c6  jz      short loc_1800151D4
0x1800151c8  call    cs:__imp_ldap_msgfree
0x1800151cf  nop     dword ptr [rax+rax+00h]
0x1800151d4  mov     rdx, [rbx+8]; SearchBlock
0x1800151d8  test    rdx, rdx
0x1800151db  jz      short loc_1800151EF
0x1800151dd  mov     rcx, [rbx]
0x1800151e0  mov     rcx, [rcx]; ExternalHandle
0x1800151e3  call    cs:__imp_ldap_search_abandon_page
0x1800151ea  nop     dword ptr [rax+rax+00h]
0x1800151ef  mov     rcx, rbx
0x1800151f2  mov     [rsi], r13
0x1800151f5  mov     [rbx+8], r13
0x1800151f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015200  nop     dword ptr [rax+rax+00h]
0x180015205  mov     rbx, r13
0x180015208  jmp     short loc_180015212
0x18001520a  mov     rbx, rdx
0x18001520d  mov     edi, 8
0x180015212  mov     ecx, edi; dwErrCode
0x180015214  call    cs:__imp_SetLastError
0x18001521b  nop     dword ptr [rax+rax+00h]
0x180015220  mov     rax, rbx
0x180015223  mov     rcx, [rbp+47h+var_48]
0x180015227  xor     rcx, rsp; StackCookie
0x18001522a  call    __security_check_cookie
0x18001522f  add     rsp, 0B8h
0x180015236  pop     r15
0x180015238  pop     r14
0x18001523a  pop     r13
0x18001523c  pop     r12
0x18001523e  pop     rdi
0x18001523f  pop     rsi
0x180015240  pop     rbx
0x180015241  pop     rbp
0x180015242  retn
```
