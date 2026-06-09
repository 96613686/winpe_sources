# OpenLdapServer(ldap_connection *,l_timeval *)

- ea: `0x18002376c`
- end: `0x180024486`
- name: `?OpenLdapServer@@YAHPEAUldap_connection@@PEAUl_timeval@@@Z`
- size: `3354`
- prototype: `__int64 __fastcall(struct ldap_connection *, struct l_timeval *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015bd8`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x18001ef10`
- `0x18001f13c`
- `0x180020228`
- `0x180020970`
- `0x180020990`
- `0x180022a60`
- `0x180022e80`
- `0x18002376c`
- `0x18002448c`
- `0x18002b5fc`
- `0x18002ca68`
- `0x1800314a8`
- `0x180034e6c`
- `0x18004294c`
- `0x1800429f4`
- `0x1800432c4`
- `0x1800434f0`
- `0x180049bf0`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ad8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ad8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023ee7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023ee7`
- `WS2_32!FreeAddrInfoW` at `0x180023d52`
- `WS2_32!FreeAddrInfoW` at `0x180023d52`
- `WS2_32!__imp_htons` at `0x180023bbd`
- `WS2_32!__imp_htons` at `0x180023cb4`
- `WS2_32!__imp_htons` at `0x180023ea2`
- `WS2_32!__imp_htons` at `0x180023bbd`
- `WS2_32!__imp_htons` at `0x180023cb4`
- `WS2_32!__imp_htons` at `0x180023ea2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800240cd`
- `WS2_32!__imp_WSAGetLastError` at `0x180024245`
- `WS2_32!__imp_WSAGetLastError` at `0x1800240cd`
- `WS2_32!__imp_WSAGetLastError` at `0x180024245`

## string_xrefs

- `0x180023f48`: `LDAP connection 0x%x attempting to resolve '%S' using DC locator (DNS only).\n`
- `0x180023f83`: `LDAP connection 0x%x attempting to resolve '%S' using DC locator.\n`
- `0x180024036`: `LDAP connection 0x%x attempting to resolve '%S' using GetHostByName.\n`
- `0x1800241ef`: `LDAP connection 0x%x attempting to resolve '%S' using GetHostByName.\n`
- `0x180024133`: `LDAP connection 0x%x attempting to resolve '%S' using DC locator (NetBIOS only).\n`

## pseudocode

```c
unsigned int __fastcall OpenLdapServer(struct ldap_connection *a1, struct l_timeval *a2)
{
  unsigned int v2; // r9d
  struct ldap_connection *v3; // rdi
  int v4; // r15d
  unsigned int v5; // r10d
  void *v6; // rax
  void *v7; // rcx
  unsigned int result; // eax
  void *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int16 *v12; // rcx
  __int16 v13; // ax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rsi
  struct _LDAPHostEnt *v16; // r12
  __int64 v17; // rdx
  int v18; // ecx
  unsigned int CurrentMachineParams; // eax
  __int64 v20; // r8
  char v21; // r14
  unsigned int v22; // r13d
  int v23; // eax
  void *v24; // rcx
  unsigned int v25; // r15d
  void *v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  char v32; // dl
  __int16 v33; // ax
  _WORD *v34; // rdx
  u_short v35; // si
  unsigned int v36; // ebx
  WCHAR *v37; // r13
  char v38; // r15
  WCHAR *v39; // rax
  u_short v40; // ax
  int v41; // r12d
  u_short v42; // r14
  const char *v43; // rdx
  char IsAddressNumeric; // al
  unsigned __int16 *v45; // rbx
  unsigned int AddrInfo; // eax
  PADDRINFOW v47; // rbx
  size_t ai_addrlen; // rax
  unsigned int v49; // eax
  __int64 v50; // rcx
  WCHAR v51; // ax
  unsigned __int16 *v52; // rbx
  _WORD *v53; // rcx
  u_short v54; // ax
  const WCHAR *v55; // r8
  bool v56; // si
  int v57; // eax
  int v58; // eax
  struct _LDAPHostEnt *HostByNameW; // rax
  struct _LDAPHostEnt *v60; // rbx
  int Error; // eax
  int *v62; // r9
  int v63; // ecx
  struct l_timeval *v64; // rsi
  int v65; // eax
  struct _LDAPHostEnt *v66; // rax
  int v67; // eax
  unsigned __int16 *v68; // rsi
  _QWORD *v69; // rsi
  int v70; // r14d
  __int64 v71; // rcx
  __int64 v72; // rcx
  unsigned __int8 v73; // [rsp+50h] [rbp-29h] BYREF
  char v74; // [rsp+51h] [rbp-28h]
  unsigned __int16 *v75; // [rsp+58h] [rbp-21h] BYREF
  u_short v76; // [rsp+60h] [rbp-19h]
  int v77; // [rsp+64h] [rbp-15h]
  struct _LDAPHostEnt *v78; // [rsp+68h] [rbp-11h] BYREF
  unsigned int v79; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v80; // [rsp+78h] [rbp-1h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+80h] [rbp+7h] BYREF
  __int64 v84; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int16 *v85; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  v3 = a1;
  v4 = 0;
  v73 = 0;
  pAddrInfo = 0;
  LOWORD(v5) = 1;
  if ( *((_BYTE *)a1 + 392) && *((_BYTE *)a1 + 393) == 1 )
  {
    v6 = (void *)*((_QWORD *)a1 + 51);
    v7 = (void *)*((_QWORD *)a1 + 48);
    if ( v6 == v7 )
    {
      v6 = (void *)ldap_dup_stringW(v6);
      *((_QWORD *)v3 + 51) = v6;
      if ( !v6 )
        return 90;
      v7 = (void *)*((_QWORD *)v3 + 48);
    }
    v9 = (void *)*((_QWORD *)v3 + 54);
    if ( v9 != v6 && v9 != v7 )
      ldapFree(*((_QWORD *)v3 + 54), 1953712204);
    *((_QWORD *)v3 + 54) = 0;
    FreeSocketAddressArr((unsigned int *)v3 + 93, (struct _SOCKET_ADDRESS ***)v3 + 47);
    ldapFree(*((_QWORD *)v3 + 48), 1953712204);
    v10 = *((_QWORD *)v3 + 52);
    *((_QWORD *)v3 + 48) = 0;
    ldapFree(v10, 1953712204);
    v11 = *((_QWORD *)v3 + 53);
    *((_QWORD *)v3 + 52) = 0;
    ldapFree(v11, 1953712204);
    v2 = 0;
    *((_QWORD *)v3 + 53) = 0;
    *((_BYTE *)v3 + 392) = 0;
    LOWORD(v5) = 1;
    v4 = 1;
  }
  v12 = (__int16 *)*((_QWORD *)v3 + 48);
  v74 = 0;
  if ( !v12 )
  {
    v13 = *((_WORD *)v3 + 253);
    v14 = 0;
    LODWORD(v84) = 1;
    v15 = 0;
    v80 = 0;
    v16 = 0;
    v78 = 0;
    v75 = 0;
    v85 = 0;
    if ( v13 == 389 || (v17 = 636, v18 = 1232, v13 == 636) )
    {
      CurrentMachineParams = GetCurrentMachineParams(&v85, &v75);
      v14 = v85;
      v2 = 0;
      v18 = CurrentMachineParams;
    }
    v20 = *((unsigned __int16 *)v3 + 253);
    if ( (_WORD)v20 == 3268 || (v21 = 0, (_WORD)v20 == 3269) )
      v21 = 1;
    if ( v18 )
    {
      result = GetDefaultLdapServer(
                 0,
                 (__int64)&v84,
                 *((_DWORD *)v3 + 114) | (unsigned int)v4,
                 (__int64)&v73,
                 v20,
                 (__int64)v3 + 468,
                 (unsigned __int64)&v80 & -(__int64)(v21 != 0));
      v2 = 0;
      if ( result )
        return result;
      if ( !v21 )
      {
        result = GetPrimaryDomainName((unsigned __int16 **)&v78);
        v2 = 0;
        if ( result )
          return result;
      }
      v14 = v85;
      v16 = v78;
      v15 = v80;
    }
    if ( v14 )
    {
      v23 = strlenW(v14, v17, v20);
      v5 = 1;
      v22 = v23 + 1;
    }
    else
    {
      v22 = 0;
      v5 = 1;
    }
    v24 = v16;
    if ( v21 )
      v24 = v15;
    if ( v24 )
    {
      v26 = v16;
      if ( v21 )
        v26 = v15;
      v27 = strlenW(v26, v17, v20);
      v25 = v5 + v27;
    }
    else
    {
      v25 = v2;
    }
    if ( v22 > v5 )
    {
      v28 = ldap_dup_stringW(v14);
      *((_QWORD *)v3 + 48) = v28;
      if ( v28 && v25 > 1 )
      {
        v29 = v16;
        if ( v21 )
          v29 = v15;
        v30 = v28 + 2LL * v22;
        *(_WORD *)(v30 - 2) = 32;
        ldap_MoveMemory(v30, v29, 2 * v25);
      }
      ldapFree(v14, 1953712204);
      v2 = 0;
      v14 = 0;
      if ( v15 )
      {
        ldapFree(v15, 1953712204);
        v2 = 0;
      }
      v31 = *((_QWORD *)v3 + 53);
      LOWORD(v5) = 1;
      *((_QWORD *)v3 + 52) = v75;
      v74 = 1;
      if ( v31 )
      {
        ldapFree(v31, 1953712204);
        v2 = 0;
        LOWORD(v5) = 1;
      }
      *((_QWORD *)v3 + 53) = v16;
    }
    v12 = (__int16 *)*((_QWORD *)v3 + 48);
    if ( !v12 )
    {
      ldapFree(v14, 1953712204);
      SetLastError(0x4D9u);
      return 1241;
    }
    *((_BYTE *)v3 + 393) = v5;
  }
  v32 = v2;
  LOBYTE(v85) = v2;
  if ( *((_BYTE *)v3 + 392) == (_BYTE)v2 )
  {
    *((_WORD *)v3 + 252) = v5;
    v33 = *v12;
    if ( *v12 )
    {
      do
      {
        v34 = v12 + 1;
        if ( v33 == 32 )
        {
          *((_WORD *)v3 + 252) += v5;
          *v12++ = v2;
          if ( *v34 == 32 )
          {
            do
              ++v12;
            while ( *v12 == 32 );
          }
        }
        else
        {
          ++v12;
        }
        v33 = *v12;
      }
      while ( *v12 );
      v32 = v2;
    }
    *((_BYTE *)v3 + 392) = v5;
  }
  while ( 1 )
  {
    v35 = *((_WORD *)v3 + 253);
    LOWORD(v36) = v2;
    v37 = (WCHAR *)*((_QWORD *)v3 + 48);
    v38 = v2;
    v77 = v35;
    v79 = v2;
    LOBYTE(v84) = v2;
    if ( !v32 )
    {
      v39 = (WCHAR *)*((_QWORD *)v3 + 51);
      LOBYTE(v84) = v2;
      if ( v39 )
      {
        v37 = v39;
        LOBYTE(v85) = v5;
        v38 = v5;
        LOBYTE(v84) = v5;
      }
    }
    *((_WORD *)v3 + 116) = *((_WORD *)v3 + 184);
    if ( !v35 )
    {
      v35 = 389;
      v77 = 389;
    }
    v40 = htons(v35);
    v2 = 0;
    *((_WORD *)v3 + 117) = v40;
    v41 = 1232;
    LOBYTE(v5) = 1;
    if ( *((_WORD *)v3 + 252) )
      break;
LABEL_202:
    if ( (_BYTE)v84 != 1 )
      return v41;
    v32 = (char)v85;
  }
  while ( v41 )
  {
    v42 = v35;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
    {
      v43 = "LDAP connection 0x%x trying host '%S' using old host resolution order\n";
      if ( !GlobalUseOldHostResolutionOrder )
        v43 = "LDAP connection 0x%x trying host '%S' using new host resolution order\n";
      LDAPClientPrint(0x2000000, v43, v3, v37);
    }
    v76 = 0;
    IsAddressNumeric = LdapIsAddressNumeric(v37);
    v2 = 0;
    if ( !IsAddressNumeric )
    {
      v51 = *v37;
      v52 = v37;
      v75 = v37;
      if ( v51 != 58 )
      {
        do
        {
          if ( !v51 )
            break;
          v51 = *++v52;
        }
        while ( *v52 != 58 );
        v75 = v52;
      }
      if ( *v52 )
      {
        v53 = v52 + 1;
        v42 = 0;
        while ( *v53 )
        {
          if ( (unsigned __int16)(*v53 - 48) > 9u )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
            {
              LDAPClientPrint(0x2000000, "LDAP connection 0x%x invalid port number for '%S'\n", (_DWORD)v3, v37);
              v2 = 0;
            }
            v41 = 1214;
            LOBYTE(v5) = 1;
            goto LABEL_195;
          }
          v42 = *v53++ + 10 * v42 - 48;
        }
        *v52 = 0;
        if ( !v42 )
          v42 = v35;
      }
      else
      {
        v75 = 0;
      }
      v54 = htons(v42);
      v55 = (const WCHAR *)*((_QWORD *)v3 + 48);
      *((_WORD *)v3 + 117) = v54;
      if ( v55 )
        v56 = CompareStringW(0x400u, 1u, v55, -1, L"localhost", -1) == 2;
      else
        v56 = 0;
      if ( !*((_BYTE *)v3 + 394) && !v38 && !v56 )
      {
        if ( GlobalUseOldHostResolutionOrder )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
            LDAPClientPrint(
              0x2000000,
              "LDAP connection 0x%x attempting to resolve '%S' using DC locator (DNS only).\n",
              (_DWORD)v3,
              v37);
          v57 = 0x20000;
        }
        else
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
            LDAPClientPrint(
              0x2000000,
              "LDAP connection 0x%x attempting to resolve '%S' using DC locator.\n",
              (_DWORD)v3,
              v37);
          v57 = 0;
        }
        v58 = ConnectToSRVrecs(v3, v37, (__int64)a2, v57);
        v2 = 0;
        v41 = v58;
        if ( !v58 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
          {
            LDAPClientPrint(
              0x2000000,
              "LDAP connection 0x%x successfully resolved '%S' using DC locator.\n",
              (_DWORD)v3,
              v37);
            v2 = 0;
          }
          v41 = 0;
LABEL_190:
          v35 = v77;
          goto LABEL_191;
        }
      }
      v80 = 0;
      if ( GlobalUseOldHostResolutionOrder )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
          LDAPClientPrint(
            0x2000000,
            "LDAP connection 0x%x attempting to resolve '%S' using GetHostByName.\n",
            (_DWORD)v3,
            v37);
        HostByNameW = GetHostByNameW(v37, v42, *((_BYTE *)v3 + 646));
        v2 = 0;
        v78 = HostByNameW;
        v60 = HostByNameW;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        {
          if ( HostByNameW )
            goto LABEL_142;
LABEL_144:
          if ( !*((_BYTE *)v3 + 394) && !v38 && !v56 )
          {
            Error = WSAGetLastError();
            v63 = g_fTracingOn;
            if ( g_fTracingOn )
            {
              if ( g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
              {
                LDAPClientPrint(0x2000000, "LDAP gethostbyname failed for '%S', 0x%x\n", v37, Error);
                v63 = g_fTracingOn;
              }
              if ( v63 && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
                LDAPClientPrint(
                  0x2000000,
                  "LDAP connection 0x%x attempting to resolve '%S' using DC locator (NetBIOS only).\n",
                  (_DWORD)v3,
                  v37);
            }
            v64 = a2;
            v65 = ResolveHostAsNetbiosDomain(v3, v37, v42, v62, &v78, &v80, a2);
            v60 = v78;
            v2 = 0;
            v41 = v65;
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
            {
              if ( v78 )
              {
                LDAPClientPrint(
                  0x2000000,
                  "LDAP connection 0x%x successfully resolved '%S' using DC Locator.\n",
                  (_DWORD)v3,
                  v37);
                v2 = 0;
                goto LABEL_176;
              }
            }
            else
            {
LABEL_176:
              if ( v60 )
              {
                v41 = ConnectToArecs(v3, (__int64)v64);
                v2 = 0;
              }
            }
            v68 = v80;
            if ( v80 )
            {
              if ( v41 )
              {
                ldapFree(v80, 1953712204);
              }
              else
              {
                ldapFree(*((_QWORD *)v3 + 51), 1953712204);
                *((_QWORD *)v3 + 51) = v68;
              }
              v2 = 0;
            }
            if ( v60 )
            {
              v69 = (_QWORD *)*((_QWORD *)v60 + 3);
              v70 = 0;
              if ( *v69 )
              {
                do
                {
                  v71 = *(_QWORD *)(v69[v70] + 8LL);
                  if ( v71 )
                    ldapFree(v71, 1936605516);
                  ldapFree(v69[v70++], 1936605516);
                }
                while ( v69[v70] );
                v3 = a1;
              }
              ldapFree(v69, 1936605516);
              ldapFree(*(_QWORD *)v60, 1953712204);
              ldapFree(*((_QWORD *)v60 + 1), 1953712204);
              ldapFree(v60, 1936605516);
              v2 = 0;
            }
            goto LABEL_190;
          }
        }
        else if ( !HostByNameW )
        {
          goto LABEL_144;
        }
LABEL_175:
        v64 = a2;
        goto LABEL_176;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(
          0x2000000,
          "LDAP connection 0x%x attempting to resolve '%S' using GetHostByName.\n",
          (_DWORD)v3,
          v37);
      v66 = GetHostByNameW(v37, v42, *((_BYTE *)v3 + 646));
      v2 = 0;
      v60 = v66;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      {
        if ( v66 )
        {
LABEL_142:
          LDAPClientPrint(
            0x2000000,
            "LDAP connection 0x%x successfully resolved '%S' using GetHostByName.\n",
            (_DWORD)v3,
            v37);
          v2 = 0;
          goto LABEL_175;
        }
      }
      else if ( v66 )
      {
        goto LABEL_175;
      }
      v67 = WSAGetLastError();
      v2 = 0;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      {
        LDAPClientPrint(0x2000000, "LDAP gethostbyname failed for '%S', 0x%x\n", v37, v67);
        v2 = 0;
      }
      v41 = 1241;
      goto LABEL_175;
    }
    v75 = 0;
    if ( v76 )
    {
      v45 = v37;
      v42 = v76;
      v75 = v37;
      if ( *v37 )
      {
        do
          ++v45;
        while ( *v45 );
        v75 = v45;
      }
      while ( v45 > v37 )
      {
        if ( *v45 == 58 )
          goto LABEL_79;
        v75 = --v45;
      }
      if ( *v45 == 58 )
      {
LABEL_79:
        *v45 = 0;
        goto LABEL_81;
      }
      v75 = 0;
    }
LABEL_81:
    *((_WORD *)v3 + 117) = htons(v42);
    AddrInfo = LdapGetAddrInfo(v37, v42, &pAddrInfo);
    v2 = 0;
    if ( AddrInfo )
    {
      v41 = 1241;
    }
    else
    {
      v47 = pAddrInfo;
      if ( pAddrInfo )
      {
        ai_addrlen = pAddrInfo->ai_addrlen;
        *((_QWORD *)v3 + 45) = ai_addrlen;
        if ( ai_addrlen > 0x80 )
        {
          *((_QWORD *)v3 + 45) = 0;
          memset_0((char *)v3 + 232, 0, 0x80u);
          v41 = -2147418113;
          *((_DWORD *)v3 + 92) = 0;
        }
        else
        {
          *((_QWORD *)v3 + 45) = v47->ai_addrlen;
          memcpy_0((char *)v3 + 232, v47->ai_addr, v47->ai_addrlen);
          v41 = 0;
        }
      }
      FreeAddrInfoW(v47);
      v2 = 0;
      pAddrInfo = 0;
      if ( !v41 )
      {
        v49 = LdapWinsockConnect(v3, v42, v37, a2, v73);
        v2 = 0;
        v41 = v49;
        if ( !v74 )
        {
          v50 = *((_QWORD *)v3 + 52);
          if ( v50 )
          {
            ldapFree(v50, 1953712204);
            v2 = 0;
            *((_QWORD *)v3 + 52) = 0;
          }
          LOBYTE(v5) = 1;
          *((_BYTE *)v3 + 395) = 1;
          goto LABEL_192;
        }
      }
    }
LABEL_191:
    LOBYTE(v5) = 1;
LABEL_192:
    if ( v75 )
      *v75 = 58;
    if ( v41 )
    {
LABEL_195:
      HIWORD(v36) = HIWORD(v79);
      LOWORD(v36) = v79 + 1;
      v79 = v36;
      while ( *v37 )
        ++v37;
      ++v37;
    }
    else
    {
      LOWORD(v36) = v79;
    }
    v38 = v84;
    if ( (unsigned __int16)v36 >= *((_WORD *)v3 + 252) )
    {
      if ( v41 )
        goto LABEL_202;
      break;
    }
  }
  if ( (_BYTE)v84 == 1 )
  {
    v72 = *((_QWORD *)v3 + 54);
    if ( v72 && v72 != *((_QWORD *)v3 + 48) && v72 != *((_QWORD *)v3 + 51) )
      ldapFree(v72, 1953712204);
    *((_QWORD *)v3 + 54) = *((_QWORD *)v3 + 48);
  }
  if ( (_WORD)v36 )
    *((_QWORD *)v3 + 54) = *((_QWORD *)v3 + 48);
  ldapFree(*((_QWORD *)v3 + 124), 1953712204);
  v41 = FromUnicodeWithAlloc(*((LPCWCH *)v3 + 54));
  if ( !v41 )
  {
    if ( *((_BYTE *)v3 + 646) )
      return LdapSetupSslSession(v3);
  }
  return v41;
}

```

## disassembly

```asm
0x18002376c  mov     [rsp-8+arg_8], rdx
0x180023771  mov     [rsp-8+arg_0], rcx
0x180023776  push    rbp
0x180023777  push    rbx
0x180023778  push    rsi
0x180023779  push    rdi
0x18002377a  push    r12
0x18002377c  push    r13
0x18002377e  push    r14
0x180023780  push    r15
0x180023782  lea     rbp, [rsp-1Fh]
0x180023787  sub     rsp, 98h
0x18002378e  xor     r9d, r9d
0x180023791  mov     rdi, rcx
0x180023794  mov     r15d, r9d
0x180023797  mov     [rbp+57h+var_80], r9b
0x18002379b  mov     r14d, 7473484Ch
0x1800237a1  mov     [rbp+57h+pAddrInfo], r9
0x1800237a5  lea     r10d, [r9+1]
0x1800237a9  cmp     [rcx+188h], r9b
0x1800237b0  jz      loc_18002388D
0x1800237b6  cmp     [rcx+189h], r10b
0x1800237bd  jnz     loc_18002388D
0x1800237c3  mov     rax, [rcx+198h]
0x1800237ca  mov     rcx, [rcx+180h]
0x1800237d1  cmp     rax, rcx
0x1800237d4  jnz     short loc_180023802
0x1800237d6  mov     r8d, r14d
0x1800237d9  xor     edx, edx
0x1800237db  mov     rcx, rax; Src
0x1800237de  call    ldap_dup_stringW
0x1800237e3  xor     ebx, ebx
0x1800237e5  mov     [rdi+198h], rax
0x1800237ec  test    rax, rax
0x1800237ef  jnz     short loc_1800237F9
0x1800237f1  lea     eax, [rbx+5Ah]
0x1800237f4  jmp     loc_180024471
0x1800237f9  mov     rcx, [rdi+180h]
0x180023800  jmp     short loc_180023804
0x180023802  xor     ebx, ebx
0x180023804  mov     r8, [rdi+1B0h]
0x18002380b  cmp     r8, rax
0x18002380e  jz      short loc_180023820
0x180023810  cmp     r8, rcx
0x180023813  jz      short loc_180023820
0x180023815  mov     edx, r14d
0x180023818  mov     rcx, r8
0x18002381b  call    ldapFree
0x180023820  lea     rdx, [rdi+178h]; struct _SOCKET_ADDRESS ***
0x180023827  mov     [rdi+1B0h], rbx
0x18002382e  lea     rcx, [rdi+174h]; unsigned int *
0x180023835  call    ?FreeSocketAddressArr@@YAXPEAKPEAPEAPEAU_SOCKET_ADDRESS@@@Z; FreeSocketAddressArr(ulong *,_SOCKET_ADDRESS * * *)
0x18002383a  mov     rcx, [rdi+180h]
0x180023841  mov     edx, r14d
0x180023844  call    ldapFree
0x180023849  mov     rcx, [rdi+1A0h]
0x180023850  mov     edx, r14d
0x180023853  mov     [rdi+180h], rbx
0x18002385a  call    ldapFree
0x18002385f  mov     rcx, [rdi+1A8h]
0x180023866  mov     edx, r14d
0x180023869  mov     [rdi+1A0h], rbx
0x180023870  call    ldapFree
0x180023875  xor     r9d, r9d
0x180023878  mov     [rdi+1A8h], r9
0x18002387f  mov     [rdi+188h], r9b
0x180023886  lea     r10d, [r9+1]
0x18002388a  mov     r15d, r10d
0x18002388d  mov     rcx, [rdi+180h]
0x180023894  mov     r11d, 185h
0x18002389a  mov     [rbp+57h+var_7F], r9b
0x18002389e  mov     r8d, 20h ; ' '
0x1800238a4  test    rcx, rcx
0x1800238a7  jnz     loc_180023AFE
0x1800238ad  movzx   eax, word ptr [rdi+1FAh]
0x1800238b4  mov     rbx, r9
0x1800238b7  mov     dword ptr [rbp+57h+arg_10], r10d
0x1800238bb  mov     rsi, r9
0x1800238be  mov     [rbp+57h+var_58], r9
0x1800238c2  mov     r12, r9
0x1800238c5  mov     [rbp+57h+var_68], r9
0x1800238c9  mov     [rbp+57h+var_78], r9
0x1800238cd  mov     [rbp+57h+arg_18], rbx
0x1800238d1  cmp     ax, r11w
0x1800238d5  jz      short loc_1800238E6
0x1800238d7  mov     edx, 27Ch
0x1800238dc  mov     ecx, 4D0h
0x1800238e1  cmp     ax, dx
0x1800238e4  jnz     short loc_180023900
0x1800238e6  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x1800238ea  lea     rcx, [rbp+57h+arg_18]; unsigned __int16 **
0x1800238ee  call    ?GetCurrentMachineParams@@YAKPEAPEAG0@Z; GetCurrentMachineParams(ushort * *,ushort * *)
0x1800238f3  mov     rbx, [rbp+57h+arg_18]
0x1800238f7  xor     r9d, r9d
0x1800238fa  mov     ecx, eax
0x1800238fc  lea     r10d, [r9+1]
0x180023900  movzx   r8d, word ptr [rdi+1FAh]
0x180023908  mov     eax, 0CC4h
0x18002390d  cmp     r8w, ax
0x180023911  jz      short loc_180023921
0x180023913  mov     eax, 0CC5h
0x180023918  mov     r14b, r9b
0x18002391b  cmp     r8w, ax
0x18002391f  jnz     short loc_180023924
0x180023921  mov     r14b, r10b
0x180023924  test    ecx, ecx
0x180023926  jz      loc_1800239BE
0x18002392c  mov     al, r14b
0x18002392f  lea     rcx, [rdi+1D4h]
0x180023936  neg     al
0x180023938  lea     rax, [rbp+57h+var_58]
0x18002393c  sbb     rdx, rdx
0x18002393f  or      r15d, [rdi+1C8h]
0x180023946  and     rdx, rax
0x180023949  mov     al, r14b
0x18002394c  mov     [rsp+0D0h+var_88], rdx; __int64
0x180023951  neg     al
0x180023953  mov     [rsp+0D0h+var_90], rcx; __int64
0x180023958  lea     rax, [rbp+57h+var_68]
0x18002395c  mov     [rsp+0D0h+var_98], r8w; __int16
0x180023962  lea     rdx, [rbp+57h+arg_18]
0x180023966  sbb     r9, r9
0x180023969  lea     r8, [rbp+57h+var_78]
0x18002396d  and     r9, rax
0x180023970  xor     ecx, ecx; DomainName
0x180023972  lea     rax, [rbp+57h+var_80]
0x180023976  mov     [rsp+0D0h+var_A0], rax; __int64
0x18002397b  lea     rax, [rbp+57h+arg_10]
0x18002397f  mov     [rsp+0D0h+cchCount2], r15d; int
0x180023984  mov     [rsp+0D0h+lpString2], rax; __int64
0x180023989  call    GetDefaultLdapServer
0x18002398e  xor     r9d, r9d
0x180023991  test    eax, eax
0x180023993  jnz     loc_180024471
0x180023999  test    r14b, r14b
0x18002399c  jnz     short loc_1800239B2
0x18002399e  lea     rcx, [rbp+57h+var_68]; unsigned __int16 **
0x1800239a2  call    ?GetPrimaryDomainName@@YAKPEAPEAG@Z; GetPrimaryDomainName(ushort * *)
0x1800239a7  xor     r9d, r9d
0x1800239aa  test    eax, eax
0x1800239ac  jnz     loc_180024471
0x1800239b2  mov     rbx, [rbp+57h+arg_18]
0x1800239b6  mov     r12, [rbp+57h+var_68]
0x1800239ba  mov     rsi, [rbp+57h+var_58]
0x1800239be  test    rbx, rbx
0x1800239c1  jnz     short loc_1800239CC
0x1800239c3  mov     r13d, r9d
0x1800239c6  lea     r10d, [rbx+1]
0x1800239ca  jmp     short loc_1800239DE
0x1800239cc  mov     rcx, rbx
0x1800239cf  call    strlenW
0x1800239d4  mov     r10d, 1
0x1800239da  lea     r13d, [r10+rax]
0x1800239de  test    r14b, r14b
0x1800239e1  mov     rcx, r12
0x1800239e4  cmovnz  rcx, rsi
0x1800239e8  test    rcx, rcx
0x1800239eb  jnz     short loc_1800239F2
0x1800239ed  mov     r15d, r9d
0x1800239f0  jmp     short loc_180023A05
0x1800239f2  test    r14b, r14b
0x1800239f5  mov     rcx, r12
0x1800239f8  cmovnz  rcx, rsi
0x1800239fc  call    strlenW
0x180023a01  lea     r15d, [r10+rax]
0x180023a05  cmp     r13d, r10d
0x180023a08  jbe     loc_180023AB4
0x180023a0e  mov     r8d, 7473484Ch
0x180023a14  mov     edx, r15d
0x180023a17  mov     rcx, rbx; Src
0x180023a1a  call    ldap_dup_stringW
0x180023a1f  mov     [rdi+180h], rax
0x180023a26  test    rax, rax
0x180023a29  jz      short loc_180023A51
0x180023a2b  cmp     r15d, 1
0x180023a2f  jbe     short loc_180023A51
0x180023a31  test    r14b, r14b
0x180023a34  mov     ecx, r13d
0x180023a37  mov     rdx, r12
0x180023a3a  lea     r8d, [r15+r15]
0x180023a3e  cmovnz  rdx, rsi
0x180023a42  lea     rcx, [rax+rcx*2]
0x180023a46  mov     word ptr [rcx-2], 20h ; ' '
0x180023a4c  call    ldap_MoveMemory
0x180023a51  mov     r14d, 7473484Ch
0x180023a57  mov     rcx, rbx
0x180023a5a  mov     edx, r14d
0x180023a5d  call    ldapFree
0x180023a62  xor     r9d, r9d
0x180023a65  mov     ebx, r9d
0x180023a68  test    rsi, rsi
0x180023a6b  jz      short loc_180023A7B
0x180023a6d  mov     edx, r14d
0x180023a70  mov     rcx, rsi
0x180023a73  call    ldapFree
0x180023a78  xor     r9d, r9d
0x180023a7b  mov     rcx, [rdi+1A8h]
0x180023a82  mov     r10d, 1
0x180023a88  mov     rax, [rbp+57h+var_78]
0x180023a8c  mov     [rdi+1A0h], rax
0x180023a93  mov     [rbp+57h+var_7F], r10b
0x180023a97  test    rcx, rcx
0x180023a9a  jz      short loc_180023AAB
0x180023a9c  mov     edx, r14d
0x180023a9f  call    ldapFree
0x180023aa4  xor     r9d, r9d
0x180023aa7  lea     r10d, [r9+1]
0x180023aab  mov     [rdi+1A8h], r12
0x180023ab2  jmp     short loc_180023ABA
0x180023ab4  mov     r14d, 7473484Ch
0x180023aba  mov     rcx, [rdi+180h]
0x180023ac1  test    rcx, rcx
0x180023ac4  jnz     short loc_180023AEB
0x180023ac6  mov     edx, r14d
0x180023ac9  mov     rcx, rbx
0x180023acc  call    ldapFree
0x180023ad1  mov     ebx, 4D9h
0x180023ad6  mov     ecx, ebx; dwErrCode
0x180023ad8  call    cs:__imp_SetLastError
0x180023adf  nop     dword ptr [rax+rax+00h]
0x180023ae4  mov     eax, ebx
0x180023ae6  jmp     loc_180024471
0x180023aeb  mov     [rdi+189h], r10b
0x180023af2  mov     r8d, 20h ; ' '
0x180023af8  mov     r11d, 185h
0x180023afe  mov     dl, r9b
0x180023b01  mov     byte ptr [rbp+57h+arg_18], dl
0x180023b04  cmp     [rdi+188h], r9b
0x180023b0b  jnz     short loc_180023B5D
0x180023b0d  mov     [rdi+1F8h], r10w
0x180023b15  movzx   eax, word ptr [rcx]
0x180023b18  test    ax, ax
0x180023b1b  jz      short loc_180023B56
0x180023b1d  lea     rdx, [rcx+2]
0x180023b21  cmp     ax, r8w
0x180023b25  jnz     short loc_180023B48
0x180023b27  add     [rdi+1F8h], r10w
0x180023b2f  mov     [rcx], r9w
0x180023b33  mov     rcx, rdx
0x180023b36  cmp     [rdx], r8w
0x180023b3a  jnz     short loc_180023B4B
0x180023b3c  add     rcx, 2
0x180023b40  cmp     [rcx], r8w
0x180023b44  jz      short loc_180023B3C
0x180023b46  jmp     short loc_180023B4B
0x180023b48  mov     rcx, rdx
0x180023b4b  movzx   eax, word ptr [rcx]
0x180023b4e  test    ax, ax
0x180023b51  jnz     short loc_180023B1D
0x180023b53  mov     dl, r9b
0x180023b56  mov     [rdi+188h], r10b
0x180023b5d  lea     rcx, [rdi+0E8h]
0x180023b64  movzx   esi, word ptr [rdi+1FAh]
0x180023b6b  mov     ebx, r9d
0x180023b6e  mov     r13, [rdi+180h]
0x180023b75  mov     r15b, r9b
0x180023b78  mov     [rbp+57h+var_6C], esi
0x180023b7b  mov     [rbp+57h+var_60], ebx
0x180023b7e  mov     byte ptr [rbp+57h+arg_10], r9b
0x180023b82  test    dl, dl
0x180023b84  jnz     short loc_180023BA4
0x180023b86  mov     rax, [rdi+198h]
0x180023b8d  mov     byte ptr [rbp+57h+arg_10], r9b
0x180023b91  test    rax, rax
0x180023b94  jz      short loc_180023BA4
0x180023b96  mov     r13, rax
0x180023b99  mov     byte ptr [rbp+57h+arg_18], r10b
0x180023b9d  mov     r15b, r10b
0x180023ba0  mov     byte ptr [rbp+57h+arg_10], r10b
0x180023ba4  movzx   eax, word ptr [rdi+170h]
0x180023bab  mov     [rcx], ax
0x180023bae  test    si, si
0x180023bb1  jnz     short loc_180023BBA
0x180023bb3  mov     esi, r11d
0x180023bb6  mov     [rbp+57h+var_6C], r11d
0x180023bba  movzx   ecx, si; hostshort
0x180023bbd  call    cs:__imp_htons
0x180023bc4  nop     dword ptr [rax+rax+00h]
0x180023bc9  xor     r9d, r9d
0x180023bcc  mov     [rdi+0EAh], ax
0x180023bd3  mov     r12d, 4D0h
0x180023bd9  lea     r10d, [r9+1]
0x180023bdd  cmp     r9w, [rdi+1F8h]
0x180023be5  jnb     loc_1800243BC
0x180023beb  test    r12d, r12d
0x180023bee  jz      loc_1800243D4
0x180023bf4  cmp     cs:g_fTracingOn, r9d
0x180023bfb  movzx   r14d, si
0x180023bff  jz      short loc_180023C3F
0x180023c01  cmp     cs:g_fProviderEnabled, r9d
0x180023c08  jz      short loc_180023C3F
0x180023c0a  mov     eax, 2000000h
0x180023c0f  test    cs:g_ulTraceFlags, rax
0x180023c16  jz      short loc_180023C3F
0x180023c18  cmp     cs:GlobalUseOldHostResolutionOrder, r9b
0x180023c1f  lea     rdx, aLdapConnection_9; "LDAP connection 0x%x trying host '%S' u"...
0x180023c26  mov     r9, r13
0x180023c29  mov     r8, rdi
0x180023c2c  mov     ecx, eax
0x180023c2e  jnz     short loc_180023C37
  ... truncated ...
```
