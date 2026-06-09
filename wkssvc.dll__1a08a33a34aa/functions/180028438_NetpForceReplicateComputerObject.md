# NetpForceReplicateComputerObject

- ea: `0x180028438`
- end: `0x1800288a1`
- name: `NetpForceReplicateComputerObject`
- size: `1129`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800288a8`

## callees

- `0x1800015c0`
- `0x18001fbd0`
- `0x180028438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180028699`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800286ee`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180028699`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800286ee`
- `netutils!NetApiBufferFree` at `0x180028819`
- `netutils!NetApiBufferFree` at `0x180028819`
- `netutils!NetApiBufferAllocate` at `0x180028750`
- `netutils!NetApiBufferAllocate` at `0x180028750`
- `WLDAP32!__imp_LdapGetLastError` at `0x180028587`
- `WLDAP32!__imp_LdapGetLastError` at `0x180028587`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002855b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002855b`
- `WLDAP32!__imp_ldap_first_entry` at `0x180028576`
- `WLDAP32!__imp_ldap_first_entry` at `0x180028642`
- `WLDAP32!__imp_ldap_first_entry` at `0x180028576`
- `WLDAP32!__imp_ldap_first_entry` at `0x180028642`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800285d3`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002886b`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800285d3`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002886b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002859f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180028664`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800286b9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002859f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180028664`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800286b9`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800287a2`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800287f5`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800287a2`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800287f5`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180028549`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180028626`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180028549`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180028626`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002882d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180028841`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180028855`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002882d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180028841`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180028855`

## string_xrefs

- `0x180028469`: `dsServiceName`

## pseudocode

```c
__int64 __fastcall NetpForceReplicateComputerObject(LDAP *ld, LDAP *a2, WCHAR *a3, int a4)
{
  PWCHAR *v6; // r13
  PWCHAR *v7; // r12
  PWCHAR *v8; // r15
  ULONG LastError; // eax
  ULONG v10; // ebx
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  PWCHAR v13; // r14
  LDAPMessage *v14; // rax
  LDAPMessage *v15; // rdi
  PWCHAR *v16; // rax
  const wchar_t *v17; // rsi
  wchar_t *v18; // rax
  const wchar_t **v19; // rax
  const wchar_t *v20; // rdi
  wchar_t *v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  bool v25; // cc
  const wchar_t *v26; // r8
  __int64 v27; // rcx
  LDAP *v28; // rsi
  PLDAPMessage res; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID Buffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int cchDest; // [rsp+70h] [rbp-90h]
  int cchDest_4; // [rsp+74h] [rbp-8Ch]
  __int128 v34; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v35[3]; // [rsp+88h] [rbp-78h] BYREF
  char v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A1h] [rbp-5Fh]
  __int16 v38; // [rsp+A5h] [rbp-5Bh]
  char v39; // [rsp+A7h] [rbp-59h]
  LDAP *lda; // [rsp+A8h] [rbp-58h]
  PWSTR attr[2]; // [rsp+B0h] [rbp-50h] BYREF
  LDAPModW *mods[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[3]; // [rsp+D0h] [rbp-30h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+E8h] [rbp-18h] BYREF
  PWSTR attrs; // [rsp+F8h] [rbp-8h] BYREF
  PWSTR v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]

  cchDest_4 = a4;
  lda = a2;
  attr[0] = L"dsServiceName";
  attr[1] = 0;
  attrs = L"distinguishedName";
  v47 = 0;
  v46 = L"serverReferenceBL";
  v35[1] = 0;
  v35[0] = L"1.2.840.113556.1.4.529";
  v35[2] = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v6 = 0;
  v36 = 1;
  ServerControls[0] = (PLDAPControlW)v35;
  v7 = 0;
  res = 0;
  v43[1] = L"replicateSingleObject";
  v8 = 0;
  Buffer = 0;
  v43[2] = &v34;
  mods[0] = (LDAPModW *)v43;
  v34 = 0;
  v43[0] = 0;
  ServerControls[1] = 0;
  mods[1] = 0;
  LastError = ldap_search_ext_sW(
                ld,
                (const PWSTR)&base,
                0,
                (const PWSTR)L"(objectClass=*)",
                attr,
                0,
                0,
                0,
                0,
                0xFFFFFFFF,
                &res);
  if ( LastError )
    goto LABEL_2;
  entry = ldap_first_entry(ld, res);
  if ( !entry )
    goto LABEL_4;
  valuesW = ldap_get_valuesW(ld, entry, attr[0]);
  v6 = valuesW;
  if ( !valuesW )
    goto LABEL_4;
  v13 = *valuesW;
  if ( !*valuesW || !*v13 )
    goto LABEL_35;
  if ( res )
  {
    ldap_msgfree(res);
    res = 0;
  }
  LastError = ldap_search_ext_sW(
                ld,
                a3,
                0,
                (const PWSTR)L"(objectClass=*)",
                &attrs,
                0,
                ServerControls,
                0,
                0,
                0xFFFFFFFF,
                &res);
  if ( LastError )
    goto LABEL_2;
  v14 = ldap_first_entry(ld, res);
  v15 = v14;
  if ( !v14 )
    goto LABEL_4;
  v16 = ldap_get_valuesW(ld, v14, attrs);
  v7 = v16;
  if ( !v16 )
    goto LABEL_4;
  v17 = *v16;
  if ( !*v16 || !*v17 )
    goto LABEL_35;
  v18 = wcschr(v17, 0x3Bu);
  if ( v18 )
    *v18 = 0;
  v19 = (const wchar_t **)ldap_get_valuesW(ld, v15, v46);
  v8 = (PWCHAR *)v19;
  if ( !v19 )
  {
LABEL_4:
    LastError = LdapGetLastError();
LABEL_2:
    v10 = LdapMapErrorToWin32(LastError);
    goto LABEL_36;
  }
  v20 = *v19;
  if ( !*v19 || !*v20 )
  {
LABEL_35:
    v10 = 8316;
    goto LABEL_36;
  }
  v21 = wcschr(*v19, 0x3Bu);
  if ( v21 )
    *v21 = 0;
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( v20[v23] );
  v24 = -1;
  do
    ++v24;
  while ( v17[v24] );
  v25 = v24 <= v23;
  v26 = v20;
  v27 = -1;
  if ( !v25 )
    v26 = v17;
  do
    ++v27;
  while ( v26[v27] );
  do
    ++v22;
  while ( v13[v22] );
  cchDest = v27 + 2 + v22;
  v10 = NetApiBufferAllocate(2 * cchDest, &Buffer);
  if ( !v10 )
  {
    StringCchPrintfW((STRSAFE_LPWSTR)Buffer, cchDest, L"%ws:%ws", v13, v17);
    v28 = lda;
    v34 = (unsigned __int64)Buffer;
    LastError = ldap_modify_sW(lda, 0, mods);
    if ( LastError )
      goto LABEL_2;
    if ( cchDest_4 == 3 )
    {
      StringCchPrintfW((STRSAFE_LPWSTR)Buffer, cchDest, L"%ws:%ws", v13, v20);
      v34 = (unsigned __int64)Buffer;
      LastError = ldap_modify_sW(v28, 0, mods);
      if ( LastError )
        goto LABEL_2;
    }
  }
LABEL_36:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v6 )
    ldap_value_freeW(v6);
  if ( v7 )
    ldap_value_freeW(v7);
  if ( v8 )
    ldap_value_freeW(v8);
  if ( res )
    ldap_msgfree(res);
  return v10;
}

```

## disassembly

```asm
0x180028438  mov     [rsp-8+arg_18], rbx
0x18002843d  push    rbp
0x18002843e  push    rsi
0x18002843f  push    rdi
0x180028440  push    r12
0x180028442  push    r13
0x180028444  push    r14
0x180028446  push    r15
0x180028448  lea     rbp, [rsp-20h]
0x18002844d  sub     rsp, 120h
0x180028454  mov     rax, cs:__security_cookie
0x18002845b  xor     rax, rsp
0x18002845e  mov     [rbp+50h+var_40], rax
0x180028462  xor     esi, esi
0x180028464  mov     dword ptr [rsp+150h+cchDest+4], r9d
0x180028469  lea     rax, aDsservicename; "dsServiceName"
0x180028470  mov     [rbp+50h+ld], rdx
0x180028474  mov     [rbp+50h+attr], rax
0x180028478  lea     r9, filter; "(objectClass=*)"
0x18002847f  lea     rax, aDistinguishedn; "distinguishedName"
0x180028486  mov     [rbp+50h+var_98], rsi
0x18002848a  mov     [rbp+50h+var_58], rax
0x18002848e  lea     rdx, base; base
0x180028495  lea     rax, aServerreferenc; "serverReferenceBL"
0x18002849c  mov     [rbp+50h+var_48], rsi
0x1800284a0  mov     [rbp+50h+var_50], rax
0x1800284a4  mov     rdi, r8
0x1800284a7  lea     rax, a12840113556145; "1.2.840.113556.1.4.529"
0x1800284ae  mov     [rbp+50h+var_C0], rsi
0x1800284b2  mov     [rbp+50h+var_C8], rax
0x1800284b6  xorps   xmm0, xmm0
0x1800284b9  xor     eax, eax
0x1800284bb  mov     [rbp+50h+var_B8], rsi
0x1800284bf  mov     [rbp+50h+var_AF], eax
0x1800284c2  xor     r8d, r8d; scope
0x1800284c5  mov     [rbp+50h+var_AB], ax
0x1800284c9  mov     rbx, rcx
0x1800284cc  mov     [rbp+50h+var_A9], al
0x1800284cf  mov     r13d, esi
0x1800284d2  lea     rax, [rbp+50h+var_C8]
0x1800284d6  mov     [rbp+50h+var_B0], 1
0x1800284da  mov     [rbp+50h+var_68], rax
0x1800284de  mov     r12d, esi
0x1800284e1  lea     rax, aReplicatesingl; "replicateSingleObject"
0x1800284e8  mov     [rsp+150h+var_F0], rsi
0x1800284ed  mov     [rbp+50h+var_78], rax
0x1800284f1  mov     r15d, esi
0x1800284f4  lea     rax, [rsp+150h+var_D8]
0x1800284f9  mov     [rsp+150h+Buffer], rsi
0x1800284fe  mov     [rbp+50h+var_70], rax
0x180028502  lea     rax, [rbp+50h+var_80]
0x180028506  mov     [rbp+50h+mods], rax
0x18002850a  lea     rax, [rsp+150h+var_F0]
0x18002850f  mov     [rsp+150h+res], rax; res
0x180028514  lea     rax, [rbp+50h+attr]
0x180028518  mov     [rsp+150h+SizeLimit], 0FFFFFFFFh; SizeLimit
0x180028520  mov     [rsp+150h+timeout], rsi; timeout
0x180028525  mov     [rsp+150h+ClientControls], rsi; ClientControls
0x18002852a  mov     [rsp+150h+ServerControls], rsi; ServerControls
0x18002852f  mov     [rsp+150h+attrsonly], esi; attrsonly
0x180028533  mov     [rsp+150h+attrs], rax; attrs
0x180028538  movups  [rsp+150h+var_D8], xmm0
0x18002853d  mov     [rbp+50h+var_80], rsi
0x180028541  mov     [rbp+50h+var_60], rsi
0x180028545  mov     [rbp+50h+var_88], rsi
0x180028549  call    cs:__imp_ldap_search_ext_sW
0x180028550  nop     dword ptr [rax+rax+00h]
0x180028555  test    eax, eax
0x180028557  jz      short loc_18002856E
0x180028559  mov     ecx, eax; LdapError
0x18002855b  call    cs:__imp_LdapMapErrorToWin32
0x180028562  nop     dword ptr [rax+rax+00h]
0x180028567  mov     ebx, eax
0x180028569  jmp     loc_18002880F
0x18002856e  mov     rdx, [rsp+150h+var_F0]; res
0x180028573  mov     rcx, rbx; ld
0x180028576  call    cs:__imp_ldap_first_entry
0x18002857d  nop     dword ptr [rax+rax+00h]
0x180028582  test    rax, rax
0x180028585  jnz     short loc_180028595
0x180028587  call    cs:__imp_LdapGetLastError
0x18002858e  nop     dword ptr [rax+rax+00h]
0x180028593  jmp     short loc_180028559
0x180028595  mov     r8, [rbp+50h+attr]; attr
0x180028599  mov     rdx, rax; entry
0x18002859c  mov     rcx, rbx; ld
0x18002859f  call    cs:__imp_ldap_get_valuesW
0x1800285a6  nop     dword ptr [rax+rax+00h]
0x1800285ab  mov     r13, rax
0x1800285ae  test    rax, rax
0x1800285b1  jz      short loc_180028587
0x1800285b3  mov     r14, [rax]
0x1800285b6  test    r14, r14
0x1800285b9  jz      loc_18002880A
0x1800285bf  cmp     [r14], si
0x1800285c3  jz      loc_18002880A
0x1800285c9  mov     rcx, [rsp+150h+var_F0]; res
0x1800285ce  test    rcx, rcx
0x1800285d1  jz      short loc_1800285E4
0x1800285d3  call    cs:__imp_ldap_msgfree
0x1800285da  nop     dword ptr [rax+rax+00h]
0x1800285df  mov     [rsp+150h+var_F0], rsi
0x1800285e4  lea     rax, [rsp+150h+var_F0]
0x1800285e9  xor     r8d, r8d; scope
0x1800285ec  mov     [rsp+150h+res], rax; res
0x1800285f1  lea     r9, filter; "(objectClass=*)"
0x1800285f8  mov     [rsp+150h+SizeLimit], 0FFFFFFFFh; SizeLimit
0x180028600  lea     rax, [rbp+50h+var_68]
0x180028604  mov     [rsp+150h+timeout], rsi; timeout
0x180028609  mov     rdx, rdi; base
0x18002860c  mov     [rsp+150h+ClientControls], rsi; ClientControls
0x180028611  mov     rcx, rbx; ld
0x180028614  mov     [rsp+150h+ServerControls], rax; ServerControls
0x180028619  lea     rax, [rbp+50h+var_58]
0x18002861d  mov     [rsp+150h+attrsonly], esi; attrsonly
0x180028621  mov     [rsp+150h+attrs], rax; attrs
0x180028626  call    cs:__imp_ldap_search_ext_sW
0x18002862d  nop     dword ptr [rax+rax+00h]
0x180028632  test    eax, eax
0x180028634  jnz     loc_180028559
0x18002863a  mov     rdx, [rsp+150h+var_F0]; res
0x18002863f  mov     rcx, rbx; ld
0x180028642  call    cs:__imp_ldap_first_entry
0x180028649  nop     dword ptr [rax+rax+00h]
0x18002864e  mov     rdi, rax
0x180028651  test    rax, rax
0x180028654  jz      loc_180028587
0x18002865a  mov     r8, [rbp+50h+var_58]; attr
0x18002865e  mov     rdx, rax; entry
0x180028661  mov     rcx, rbx; ld
0x180028664  call    cs:__imp_ldap_get_valuesW
0x18002866b  nop     dword ptr [rax+rax+00h]
0x180028670  mov     r12, rax
0x180028673  test    rax, rax
0x180028676  jz      loc_180028587
0x18002867c  mov     rsi, [rax]
0x18002867f  xor     eax, eax
0x180028681  test    rsi, rsi
0x180028684  jz      loc_18002880A
0x18002868a  cmp     [rsi], ax
0x18002868d  jz      loc_18002880A
0x180028693  lea     edx, [rax+3Bh]; Ch
0x180028696  mov     rcx, rsi; Str
0x180028699  call    cs:__imp_wcschr
0x1800286a0  nop     dword ptr [rax+rax+00h]
0x1800286a5  xor     ecx, ecx
0x1800286a7  test    rax, rax
0x1800286aa  jz      short loc_1800286AF
0x1800286ac  mov     [rax], cx
0x1800286af  mov     r8, [rbp+50h+var_50]; attr
0x1800286b3  mov     rdx, rdi; entry
0x1800286b6  mov     rcx, rbx; ld
0x1800286b9  call    cs:__imp_ldap_get_valuesW
0x1800286c0  nop     dword ptr [rax+rax+00h]
0x1800286c5  xor     ebx, ebx
0x1800286c7  mov     r15, rax
0x1800286ca  test    rax, rax
0x1800286cd  jz      loc_180028587
0x1800286d3  mov     rdi, [rax]
0x1800286d6  test    rdi, rdi
0x1800286d9  jz      loc_18002880A
0x1800286df  cmp     [rdi], bx
0x1800286e2  jz      loc_18002880A
0x1800286e8  lea     edx, [rbx+3Bh]; Ch
0x1800286eb  mov     rcx, rdi; Str
0x1800286ee  call    cs:__imp_wcschr
0x1800286f5  nop     dword ptr [rax+rax+00h]
0x1800286fa  test    rax, rax
0x1800286fd  jz      short loc_180028702
0x1800286ff  mov     [rax], bx
0x180028702  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028706  mov     rdx, rax
0x180028709  inc     rdx
0x18002870c  cmp     [rdi+rdx*2], bx
0x180028710  jnz     short loc_180028709
0x180028712  mov     rcx, rax
0x180028715  inc     rcx
0x180028718  cmp     [rsi+rcx*2], bx
0x18002871c  jnz     short loc_180028715
0x18002871e  cmp     rcx, rdx
0x180028721  mov     r8, rdi
0x180028724  mov     rcx, rax
0x180028727  cmova   r8, rsi
0x18002872b  inc     rcx
0x18002872e  cmp     [r8+rcx*2], bx
0x180028733  jnz     short loc_18002872B
0x180028735  inc     rax
0x180028738  cmp     [r14+rax*2], bx
0x18002873d  jnz     short loc_180028735
0x18002873f  add     ecx, 2
0x180028742  lea     rdx, [rsp+150h+Buffer]; Buffer
0x180028747  add     eax, ecx
0x180028749  mov     dword ptr [rsp+150h+cchDest], eax
0x18002874d  lea     ecx, [rax+rax]; ByteCount
0x180028750  call    cs:__imp_NetApiBufferAllocate
0x180028757  nop     dword ptr [rax+rax+00h]
0x18002875c  mov     ebx, eax
0x18002875e  test    eax, eax
0x180028760  jnz     loc_18002880F
0x180028766  mov     edx, dword ptr [rsp+150h+cchDest]; cchDest
0x18002876a  lea     r8, aWsWs; "%ws:%ws"
0x180028771  mov     rcx, [rsp+150h+Buffer]; pszDest
0x180028776  mov     r9, r14
0x180028779  mov     [rsp+150h+attrs], rsi
0x18002877e  call    StringCchPrintfW
0x180028783  mov     rax, [rsp+150h+Buffer]
0x180028788  lea     r8, [rbp+50h+mods]; mods
0x18002878c  mov     rsi, [rbp+50h+ld]
0x180028790  xor     edx, edx; dn
0x180028792  mov     rcx, rsi; ld
0x180028795  mov     qword ptr [rsp+150h+var_D8], rax
0x18002879a  mov     qword ptr [rbp+50h+var_D8+8], 0
0x1800287a2  call    cs:__imp_ldap_modify_sW
0x1800287a9  nop     dword ptr [rax+rax+00h]
0x1800287ae  test    eax, eax
0x1800287b0  jnz     loc_180028559
0x1800287b6  cmp     dword ptr [rsp+150h+cchDest+4], 3
0x1800287bb  jnz     short loc_18002880F
0x1800287bd  mov     edx, dword ptr [rsp+150h+cchDest]; cchDest
0x1800287c1  lea     r8, aWsWs; "%ws:%ws"
0x1800287c8  mov     rcx, [rsp+150h+Buffer]; pszDest
0x1800287cd  mov     r9, r14
0x1800287d0  mov     [rsp+150h+attrs], rdi
0x1800287d5  call    StringCchPrintfW
0x1800287da  mov     rax, [rsp+150h+Buffer]
0x1800287df  lea     r8, [rbp+50h+mods]; mods
0x1800287e3  xor     edx, edx; dn
0x1800287e5  mov     qword ptr [rsp+150h+var_D8], rax
0x1800287ea  mov     rcx, rsi; ld
0x1800287ed  mov     qword ptr [rbp+50h+var_D8+8], 0
0x1800287f5  call    cs:__imp_ldap_modify_sW
0x1800287fc  nop     dword ptr [rax+rax+00h]
0x180028801  test    eax, eax
0x180028803  jz      short loc_18002880F
0x180028805  jmp     loc_180028559
0x18002880a  mov     ebx, 207Ch
0x18002880f  mov     rcx, [rsp+150h+Buffer]; Buffer
0x180028814  test    rcx, rcx
0x180028817  jz      short loc_180028825
0x180028819  call    cs:__imp_NetApiBufferFree
0x180028820  nop     dword ptr [rax+rax+00h]
0x180028825  test    r13, r13
0x180028828  jz      short loc_180028839
0x18002882a  mov     rcx, r13; vals
0x18002882d  call    cs:__imp_ldap_value_freeW
0x180028834  nop     dword ptr [rax+rax+00h]
0x180028839  test    r12, r12
0x18002883c  jz      short loc_18002884D
0x18002883e  mov     rcx, r12; vals
0x180028841  call    cs:__imp_ldap_value_freeW
0x180028848  nop     dword ptr [rax+rax+00h]
0x18002884d  test    r15, r15
0x180028850  jz      short loc_180028861
0x180028852  mov     rcx, r15; vals
0x180028855  call    cs:__imp_ldap_value_freeW
0x18002885c  nop     dword ptr [rax+rax+00h]
0x180028861  mov     rcx, [rsp+150h+var_F0]; res
0x180028866  test    rcx, rcx
0x180028869  jz      short loc_180028877
0x18002886b  call    cs:__imp_ldap_msgfree
0x180028872  nop     dword ptr [rax+rax+00h]
0x180028877  mov     eax, ebx
0x180028879  mov     rcx, [rbp+50h+var_40]
0x18002887d  xor     rcx, rsp; StackCookie
0x180028880  call    __security_check_cookie
0x180028885  mov     rbx, [rsp+150h+arg_18]
0x18002888d  add     rsp, 120h
0x180028894  pop     r15
0x180028896  pop     r14
0x180028898  pop     r13
0x18002889a  pop     r12
0x18002889c  pop     rdi
0x18002889d  pop     rsi
0x18002889e  pop     rbp
0x18002889f  retn
```
