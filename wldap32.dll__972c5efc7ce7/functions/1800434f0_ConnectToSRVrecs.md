# ConnectToSRVrecs

- ea: `0x1800434f0`
- end: `0x180043e0f`
- name: `ConnectToSRVrecs`
- size: `2335`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, LPCWSTR DomainName@<rdx>, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002376c`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x18001ce90`
- `0x18001f13c`
- `0x180021454`
- `0x180022a60`
- `0x180022e80`
- `0x18002dd54`
- `0x180034510`
- `0x180034e6c`
- `0x180042484`
- `0x18004294c`
- `0x1800434f0`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043b6e`
- `WS2_32!FreeAddrInfoW` at `0x180043723`
- `WS2_32!FreeAddrInfoW` at `0x180043723`
- `WS2_32!__imp_htons` at `0x18004370b`
- `WS2_32!__imp_htons` at `0x18004370b`
- `logoncli!DsGetDcNextW` at `0x1800438f4`
- `logoncli!DsGetDcNextW` at `0x1800438f4`
- `logoncli!DsGetSiteNameW` at `0x18004386e`
- `logoncli!DsGetSiteNameW` at `0x18004386e`
- `logoncli!DsGetDcOpenW` at `0x18004389c`
- `logoncli!DsGetDcOpenW` at `0x18004389c`
- `netutils!NetApiBufferFree` at `0x18004392b`
- `netutils!NetApiBufferFree` at `0x18004392b`

## pseudocode

```c
__int64 __fastcall ConnectToSRVrecs(
        struct ldap_connection *a1,
        WCHAR *DomainName,
        char a3,
        unsigned __int16 a4,
        _DWORD *a5,
        int a6)
{
  char v6; // di
  __int16 v7; // bx
  char v8; // r13
  WCHAR *v9; // r12
  __int64 v11; // r15
  void *v12; // r14
  int v13; // eax
  const WCHAR *v14; // r14
  __int64 v15; // rax
  _QWORD *v16; // rcx
  __int16 ***v17; // rax
  __int16 **v18; // rcx
  __int16 *v19; // rdi
  __int16 v20; // cx
  const WCHAR *v21; // rbx
  bool v22; // zf
  int v23; // eax
  int v24; // ebx
  DWORD DcOpenW; // ebx
  DWORD DcNextW; // eax
  void *v27; // rcx
  __int64 v28; // rax
  ULONG i; // r13d
  __int64 v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  wchar_t *v38; // r12
  unsigned int v39; // eax
  __int64 v40; // rax
  _QWORD *v41; // r12
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 *v44; // r8
  __int64 v45; // r8
  __int64 v46; // rsi
  __int64 **v47; // rax
  __int64 v48; // rcx
  char v52; // [rsp+54h] [rbp-ACh]
  _BYTE v53[11]; // [rsp+55h] [rbp-ABh] BYREF
  PADDRINFOW pAddrInfo; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+68h] [rbp-98h] BYREF
  ULONG SockAddressCount; // [rsp+70h] [rbp-90h] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h]
  LPWSTR SiteName; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+88h] [rbp-78h]
  PCWSTR pNodeName; // [rsp+90h] [rbp-70h]
  HANDLE GetDcContextHandle; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v63; // [rsp+A8h] [rbp-58h]
  _QWORD v64[100]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = 0;
  v7 = a4;
  v8 = a3;
  Src = DomainName;
  v9 = DomainName;
  v63 = a5;
  GetDcContextHandle = 0;
  SockAddressCount = 0;
  SiteName = 0;
  v52 = 0;
  LODWORD(v11) = 0;
  v55 = 0;
  v12 = 0;
  pNodeName = 0;
  *(_QWORD *)&v53[3] = 0;
  v57 = 0;
  memset_0(v64, 0, sizeof(v64));
  if ( !v9 )
  {
    v9 = (WCHAR *)*((_QWORD *)a1 + 48);
    Src = v9;
  }
  if ( v8 )
  {
LABEL_30:
    v24 = *((_DWORD *)a1 + 114) & 0x10C0;
    SiteName = 0;
    DsGetSiteNameW(0, &SiteName);
    DcOpenW = DsGetDcOpenW(v9, 0, SiteName, 0, 0, v24 | 0x8000, &GetDcContextHandle);
    if ( DcOpenW )
      goto LABEL_94;
    v52 = 1;
LABEL_32:
    if ( (unsigned int)v11 >= 0x63 )
      goto LABEL_71;
    *(_QWORD *)&v53[3] = 0;
    pAddrInfo = 0;
    SockAddressCount = 0;
    v12 = 0;
    DcNextW = DsGetDcNextW(GetDcContextHandle, &SockAddressCount, (LPSOCKET_ADDRESS *)&pAddrInfo, (LPWSTR *)&v53[3]);
    v27 = *(void **)&v53[3];
    DcOpenW = DcNextW;
    if ( *(_QWORD *)&v53[3] )
    {
      if ( !DcNextW )
      {
        v28 = ldap_dup_stringW(*(void **)&v53[3]);
        v27 = *(void **)&v53[3];
        v12 = (void *)v28;
        if ( !v28 )
          DcOpenW = 90;
      }
      NetApiBufferFree(v27);
    }
    if ( DcOpenW )
    {
LABEL_71:
      v22 = g_fTracingOn == 0;
      v38 = (wchar_t *)Src;
      v64[(unsigned int)v11] = 0;
      if ( !v22 && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "Collected a total of %d address records for host '%S'\n", v11, v38);
      if ( !(_DWORD)v11 )
        goto LABEL_108;
      if ( v63 )
      {
        if ( a3 )
          LODWORD(v55) = 1;
        else
          LODWORD(v55) = *v63;
        HIDWORD(v55) = v63[1];
      }
      else
      {
        if ( SiteName )
          v39 = a3 != 0 ? 2 : 10;
        else
          v39 = a3 != 0 ? 2 : 45;
        v55 = v39;
      }
      DcOpenW = LdapParallelConnect(a1, (__int64)&v55);
      if ( DcOpenW )
        goto LABEL_94;
      v40 = ldap_dup_stringW(v38);
      *((_QWORD *)a1 + 54) = v40;
      if ( !v38 || v40 )
      {
        v41 = (_QWORD *)((char *)a1 + 376);
        FreeSocketAddressArr((unsigned int *)a1 + 93, (struct _SOCKET_ADDRESS ***)a1 + 47);
        v42 = ldapMalloc((unsigned int)(8 * v11), 1919177548);
        *((_QWORD *)a1 + 47) = v42;
        if ( v42 )
        {
          v43 = 0;
          do
          {
            *(_QWORD *)(*v41 + 8LL * *((unsigned int *)a1 + 93)) = 0;
            v44 = (__int64 *)v64[v43];
            if ( v44 )
            {
              v45 = *v44;
              if ( v45 )
              {
                *(_QWORD *)(*v41 + 8LL * *((unsigned int *)a1 + 93)) = v45;
                *(_QWORD *)v64[v43] = 0;
                ++*((_DWORD *)a1 + 93);
              }
            }
            v43 = (unsigned int)(v43 + 1);
          }
          while ( (unsigned int)v43 < (unsigned int)v11 );
          goto LABEL_94;
        }
      }
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= SockAddressCount || (unsigned int)v11 >= 0x63 )
        {
          ldapFree(v12, 1953712204);
          v12 = 0;
          LocalFree(pAddrInfo);
          goto LABEL_32;
        }
        v30 = ldapMalloc(16, 1919177548);
        v64[(unsigned int)v11] = v30;
        if ( !v30 )
          goto LABEL_70;
        *(_QWORD *)v64[(unsigned int)v11] = ldapMalloc(16, 1919177548);
        v31 = (_QWORD *)v64[(unsigned int)v11];
        if ( !*v31 )
          break;
        *(_QWORD *)&v53[3] = 16LL * i;
        v32 = *(int *)((char *)&pAddrInfo->ai_socktype + *(_QWORD *)&v53[3]);
        if ( v32 < 0x80 )
          v32 = 128;
        **(_QWORD **)v64[(unsigned int)v11] = ldapMalloc(v32, 1919177548);
        v33 = (_QWORD *)v64[(unsigned int)v11];
        if ( !*(_QWORD *)*v33 )
        {
          ldapFree(*v33, 1919177548);
          v31 = (_QWORD *)v64[(unsigned int)v11];
          break;
        }
        v34 = *(_QWORD *)&v53[3];
        *(_DWORD *)(*v33 + 8LL) = *(int *)((char *)&pAddrInfo->ai_socktype + *(_QWORD *)&v53[3]);
        memcpy_0(
          **(void ***)v64[(unsigned int)v11],
          *(const void **)((char *)&pAddrInfo->ai_flags + v34),
          *(int *)((char *)&pAddrInfo->ai_socktype + v34));
        *(_QWORD *)(v64[(unsigned int)v11] + 8LL) = ldap_dup_stringW(v12);
        if ( v12 && !*(_QWORD *)(v64[(unsigned int)v11] + 8LL) )
          goto LABEL_70;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
          LDAPClientPrint(
            0x2000000,
            "Dns supplied hostname from DsGetDcNext is '%s' totalcount %d intermediatecount %d\n",
            *(const char **)(v64[(unsigned int)v11] + 8LL),
            v11,
            i);
        LODWORD(v11) = v11 + 1;
      }
      ldapFree(v31, 1919177548);
      v64[(unsigned int)v11] = 0;
    }
LABEL_70:
    DcOpenW = 90;
    goto LABEL_94;
  }
  v53[0] = 0;
  LODWORD(v62) = 1;
  while ( 1 )
  {
    v13 = a6 | 1;
    if ( !v8 )
      v13 = a6;
    a6 = v13;
    if ( (unsigned int)GetDefaultLdapServer(
                         v9,
                         (__int64)&v62,
                         *((_DWORD *)a1 + 114) | (unsigned int)v13,
                         (__int64)v53,
                         v7,
                         (__int64)a1 + 468,
                         0) )
      goto LABEL_29;
    v14 = pNodeName;
    if ( !pNodeName )
    {
      if ( !v6 )
        goto LABEL_29;
      goto LABEL_19;
    }
    v15 = ldapMalloc(16, 1919177548);
    v64[(unsigned int)v11] = v15;
    if ( !v15 )
      goto LABEL_56;
    *(_QWORD *)v64[(unsigned int)v11] = ldapMalloc(16, 1919177548);
    v16 = (_QWORD *)v64[(unsigned int)v11];
    if ( !*v16 )
      goto LABEL_55;
    **(_QWORD **)v64[(unsigned int)v11] = ldapMalloc(128, 1919177548);
    v17 = (__int16 ***)v64[(unsigned int)v11];
    v18 = *v17;
    v19 = **v17;
    if ( !v19 )
      break;
    *((_DWORD *)v18 + 2) = 128;
    pAddrInfo = 0;
    if ( LdapGetAddrInfo(v14, a4, &pAddrInfo) )
    {
      ldapFree(**(_QWORD **)v64[(unsigned int)v11], 1919177548);
      ldapFree(*(_QWORD *)v64[(unsigned int)v11], 1919177548);
      ldapFree(v64[(unsigned int)v11], 1919177548);
      v64[(unsigned int)v11] = 0;
LABEL_29:
      v12 = *(void **)&v53[3];
      goto LABEL_30;
    }
    memcpy_0(v19, pAddrInfo->ai_addr, pAddrInfo->ai_addrlen);
    *(_DWORD *)(*(_QWORD *)v64[(unsigned int)v11] + 8LL) = pAddrInfo->ai_addrlen;
    v20 = 2;
    if ( pAddrInfo->ai_family == 2 || (v20 = 23, pAddrInfo->ai_family == 23) )
      *v19 = v20;
    else
      *v19 = 0;
    v19[1] = htons(a4);
    v6 = 1;
    FreeAddrInfoW(pAddrInfo);
    pAddrInfo = 0;
LABEL_19:
    v21 = *(const WCHAR **)&v53[3];
    v12 = 0;
    v22 = g_fTracingOn == 0;
    *(_QWORD *)&v53[3] = 0;
    *(_QWORD *)(v64[(unsigned int)v11] + 8LL) = v21;
    if ( !v22 && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      LDAPClientPrint(
        0x2000000,
        "Dns supplied hostname from DsGetDcName is '%s'\n",
        *(const char **)(v64[(unsigned int)v11] + 8LL));
    v23 = 2;
    HIDWORD(v55) = 0;
    v11 = (unsigned int)(v11 + 1);
    if ( v8 )
      v23 = 4;
    v64[v11] = 0;
    LODWORD(v55) = v23;
    if ( !(unsigned int)LdapParallelConnect(a1, (__int64)&v55) )
    {
      v35 = *((_QWORD *)a1 + 54);
      if ( v35 && v35 != *((_QWORD *)a1 + 48) && v35 != *((_QWORD *)a1 + 51) )
        ldapFree(v35, 1953712204);
      v36 = ldap_dup_stringW(v9);
      *((_QWORD *)a1 + 54) = v36;
      if ( !v9 || v36 )
      {
        v37 = *((_QWORD *)a1 + 53);
        if ( v37 )
          ldapFree(v37, 1953712204);
        *((_QWORD *)a1 + 53) = v57;
        v57 = 0;
        DcOpenW = GetSocketAddressesByNameW(v21, a4, (unsigned int *)a1 + 93, (struct _SOCKET_ADDRESS ***)a1 + 47);
      }
      else
      {
        DcOpenW = 90;
      }
      goto LABEL_94;
    }
    ldapFree(v57, 1953712204);
    v57 = 0;
    ldapFree(pNodeName, 1953712204);
    pNodeName = 0;
    if ( v8 )
      goto LABEL_30;
    v7 = a4;
    v8 = 1;
  }
  ldapFree(v18, 1919177548);
  v16 = (_QWORD *)v64[(unsigned int)v11];
LABEL_55:
  ldapFree(v16, 1919177548);
  v64[(unsigned int)v11] = 0;
LABEL_56:
  v12 = *(void **)&v53[3];
  DcOpenW = 90;
LABEL_94:
  v46 = 0;
  do
  {
    v47 = (__int64 **)v64[v46];
    if ( !v47 )
      break;
    if ( *v47 )
    {
      v48 = **v47;
      if ( v48 )
        ldapFree(v48, 1919177548);
      ldapFree(*(_QWORD *)v64[v46], 1919177548);
    }
    ldapFree(*(_QWORD *)(v64[v46] + 8LL), 1953712204);
    ldapFree(v64[v46], 1919177548);
    v64[v46] = 0;
    v46 = (unsigned int)(v46 + 1);
  }
  while ( (unsigned int)v46 < 0x64 );
  if ( pNodeName )
    ldapFree(pNodeName, 1953712204);
  if ( v12 )
    ldapFree(v12, 1953712204);
  if ( v57 )
    ldapFree(v57, 1953712204);
  if ( v52 )
LABEL_108:
    CloseLdapServerFromDomain(GetDcContextHandle, SiteName);
  return DcOpenW;
}

```

## disassembly

```asm
0x1800434f0  mov     [rsp-8+arg_10], rbx
0x1800434f5  push    rbp
0x1800434f6  push    rsi
0x1800434f7  push    rdi
0x1800434f8  push    r12
0x1800434fa  push    r13
0x1800434fc  push    r14
0x1800434fe  push    r15
0x180043500  lea     rbp, [rsp-2E0h]
0x180043508  sub     rsp, 3E0h
0x18004350f  mov     rax, cs:__security_cookie
0x180043516  xor     rax, rsp
0x180043519  mov     [rbp+310h+var_40], rax
0x180043520  mov     rax, [rbp+310h+arg_20]
0x180043527  xor     edi, edi
0x180043529  movzx   ebx, r9w
0x18004352d  mov     [rsp+410h+var_3C0], r8b
0x180043532  mov     r13b, r8b
0x180043535  mov     [rbp+310h+Src], rdx
0x180043539  mov     r12, rdx
0x18004353c  mov     [rsp+410h+var_3BE], bx
0x180043541  mov     rsi, rcx
0x180043544  mov     [rbp+310h+var_368], rax
0x180043548  xor     edx, edx; Val
0x18004354a  mov     [rbp+310h+GetDcContextHandle], rdi
0x18004354e  mov     r8d, 320h; Size
0x180043554  mov     [rsp+410h+SockAddressCount], edi
0x180043558  lea     rcx, [rbp+310h+var_360]; void *
0x18004355c  mov     [rbp+310h+SiteName], rdi
0x180043560  mov     [rsp+410h+var_3BC], dil
0x180043565  mov     r15d, edi
0x180043568  mov     [rsp+410h+var_3A8], rdi
0x18004356d  mov     r14d, edi
0x180043570  mov     [rbp+310h+pNodeName], rdi
0x180043574  mov     qword ptr [rsp+410h+var_3BB+3], rdi
0x180043579  mov     [rsp+410h+var_398], rdi
0x18004357e  call    memset_0
0x180043583  test    r12, r12
0x180043586  jnz     short loc_180043593
0x180043588  mov     r12, [rsi+180h]
0x18004358f  mov     [rbp+310h+Src], r12
0x180043593  test    r13b, r13b
0x180043596  jnz     loc_180043850
0x18004359c  mov     [rsp+410h+var_3BB], dil
0x1800435a1  mov     dword ptr [rbp+310h+var_370], 1
0x1800435a8  lea     rdx, [rsi+1D4h]
0x1800435af  mov     eax, [rbp+310h+arg_28]
0x1800435b5  lea     rcx, [rsp+410h+var_3BB]
0x1800435ba  or      eax, 1
0x1800435bd  mov     [rsp+410h+var_3C8], 0; __int64
0x1800435c6  mov     [rsp+410h+var_3D0], rdx; __int64
0x1800435cb  lea     r9, [rsp+410h+var_398]
0x1800435d0  mov     [rsp+410h+var_3D8], bx; __int16
0x1800435d5  lea     r8, [rsp+410h+var_3BB+3]
0x1800435da  mov     [rsp+410h+RetGetDcContext], rcx; __int64
0x1800435df  lea     rdx, [rbp+310h+pNodeName]
0x1800435e3  test    r13b, r13b
0x1800435e6  mov     rcx, r12; DomainName
0x1800435e9  cmovz   eax, [rbp+310h+arg_28]
0x1800435f0  mov     [rbp+310h+arg_28], eax
0x1800435f6  or      eax, [rsi+1C8h]
0x1800435fc  mov     [rsp+410h+DcFlags], eax; int
0x180043600  lea     rax, [rbp+310h+var_370]
0x180043604  mov     [rsp+410h+DnsForestName], rax; __int64
0x180043609  call    GetDefaultLdapServer
0x18004360e  test    eax, eax
0x180043610  jnz     loc_18004384B
0x180043616  mov     r14, [rbp+310h+pNodeName]
0x18004361a  test    r14, r14
0x18004361d  jz      loc_18004373A
0x180043623  mov     edi, 7264534Ch
0x180043628  lea     ecx, [rax+10h]
0x18004362b  mov     edx, edi
0x18004362d  call    ldapMalloc
0x180043632  mov     ebx, r15d
0x180043635  mov     [rbp+rbx*8+310h+var_360], rax
0x18004363a  test    rax, rax
0x18004363d  jz      loc_180043AB0
0x180043643  mov     edx, edi
0x180043645  mov     ecx, 10h
0x18004364a  call    ldapMalloc
0x18004364f  mov     rcx, [rbp+rbx*8+310h+var_360]
0x180043654  mov     edx, edi
0x180043656  mov     [rcx], rax
0x180043659  mov     rcx, [rbp+rbx*8+310h+var_360]
0x18004365e  cmp     qword ptr [rcx], 0
0x180043662  jz      loc_180043AA2
0x180043668  mov     ecx, 80h
0x18004366d  call    ldapMalloc
0x180043672  mov     rcx, [rbp+rbx*8+310h+var_360]
0x180043677  mov     rdx, [rcx]
0x18004367a  mov     [rdx], rax
0x18004367d  mov     rax, [rbp+rbx*8+310h+var_360]
0x180043682  mov     rcx, [rax]
0x180043685  mov     rdi, [rcx]
0x180043688  test    rdi, rdi
0x18004368b  jz      loc_180043A8E
0x180043691  movzx   edx, [rsp+410h+var_3BE]; unsigned __int16
0x180043696  lea     r8, [rsp+410h+pAddrInfo]; struct addrinfoW **
0x18004369b  mov     dword ptr [rcx+8], 80h
0x1800436a2  mov     rcx, r14; pNodeName
0x1800436a5  mov     [rsp+410h+pAddrInfo], 0
0x1800436ae  call    ?LdapGetAddrInfo@@YAKPEAGGPEAPEAUaddrinfoW@@@Z; LdapGetAddrInfo(ushort *,ushort,addrinfoW * *)
0x1800436b3  test    eax, eax
0x1800436b5  jnz     loc_180043810
0x1800436bb  mov     rdx, [rsp+410h+pAddrInfo]
0x1800436c0  mov     rcx, rdi; void *
0x1800436c3  mov     r8, [rdx+10h]; Size
0x1800436c7  mov     rdx, [rdx+20h]; Src
0x1800436cb  call    memcpy_0
0x1800436d0  mov     rax, [rbp+rbx*8+310h+var_360]
0x1800436d5  mov     rdx, [rax]
0x1800436d8  mov     rax, [rsp+410h+pAddrInfo]
0x1800436dd  mov     ecx, [rax+10h]
0x1800436e0  mov     [rdx+8], ecx
0x1800436e3  mov     ecx, 2
0x1800436e8  mov     rax, [rsp+410h+pAddrInfo]
0x1800436ed  cmp     [rax+4], ecx
0x1800436f0  jz      short loc_180043703
0x1800436f2  mov     ecx, 17h
0x1800436f7  cmp     [rax+4], ecx
0x1800436fa  jz      short loc_180043703
0x1800436fc  xor     eax, eax
0x1800436fe  mov     [rdi], ax
0x180043701  jmp     short loc_180043706
0x180043703  mov     [rdi], cx
0x180043706  movzx   ecx, [rsp+410h+var_3BE]; hostshort
0x18004370b  call    cs:__imp_htons
0x180043712  nop     dword ptr [rax+rax+00h]
0x180043717  mov     [rdi+2], ax
0x18004371b  mov     dil, 1
0x18004371e  mov     rcx, [rsp+410h+pAddrInfo]; pAddrInfo
0x180043723  call    cs:__imp_FreeAddrInfoW
0x18004372a  nop     dword ptr [rax+rax+00h]
0x18004372f  mov     [rsp+410h+pAddrInfo], 0
0x180043738  jmp     short loc_180043743
0x18004373a  test    dil, dil
0x18004373d  jz      loc_18004384B
0x180043743  mov     rbx, qword ptr [rsp+410h+var_3BB+3]
0x180043748  xor     r14d, r14d
0x18004374b  cmp     cs:g_fTracingOn, r14d
0x180043752  mov     r8d, r15d
0x180043755  mov     qword ptr [rsp+410h+var_3BB+3], r14
0x18004375a  mov     rax, [rbp+r8*8+310h+var_360]
0x18004375f  mov     [rax+8], rbx
0x180043763  jz      short loc_180043793
0x180043765  cmp     cs:g_fProviderEnabled, r14d
0x18004376c  jz      short loc_180043793
0x18004376e  mov     eax, 2000000h
0x180043773  test    cs:g_ulTraceFlags, rax
0x18004377a  jz      short loc_180043793
0x18004377c  mov     r8, [rbp+r8*8+310h+var_360]
0x180043781  lea     rdx, aDnsSuppliedHos; "Dns supplied hostname from DsGetDcName "...
0x180043788  mov     ecx, eax
0x18004378a  mov     r8, [r8+8]
0x18004378e  call    LDAPClientPrint
0x180043793  movzx   r8d, [rsp+410h+var_3BE]
0x180043799  lea     rdx, [rbp+310h+var_360]
0x18004379d  mov     eax, 2
0x1800437a2  mov     dword ptr [rsp+410h+var_3A8+4], r14d
0x1800437a7  inc     r15d
0x1800437aa  test    r13b, r13b
0x1800437ad  mov     r9d, r15d
0x1800437b0  lea     ecx, [rax+2]
0x1800437b3  cmovnz  eax, ecx
0x1800437b6  mov     [rbp+r15*8+310h+var_360], r14
0x1800437bb  mov     dword ptr [rsp+410h+var_3A8], eax
0x1800437bf  mov     rcx, rsi; struct ldap_connection *
0x1800437c2  lea     rax, [rsp+410h+var_3A8]
0x1800437c7  mov     [rsp+410h+DnsForestName], rax; __int64
0x1800437cc  call    LdapParallelConnect
0x1800437d1  test    eax, eax
0x1800437d3  jz      loc_180043ABF
0x1800437d9  mov     rcx, [rsp+410h+var_398]
0x1800437de  mov     ebx, 7473484Ch
0x1800437e3  mov     edx, ebx
0x1800437e5  call    ldapFree
0x1800437ea  mov     rcx, [rbp+310h+pNodeName]
0x1800437ee  mov     edx, ebx
0x1800437f0  mov     [rsp+410h+var_398], r14
0x1800437f5  call    ldapFree
0x1800437fa  mov     [rbp+310h+pNodeName], r14
0x1800437fe  test    r13b, r13b
0x180043801  jnz     short loc_180043850
0x180043803  movzx   ebx, [rsp+410h+var_3BE]
0x180043808  mov     r13b, 1
0x18004380b  jmp     loc_1800435A8
0x180043810  mov     rax, [rbp+rbx*8+310h+var_360]
0x180043815  mov     edi, 7264534Ch
0x18004381a  mov     edx, edi
0x18004381c  mov     rcx, [rax]
0x18004381f  mov     rcx, [rcx]
0x180043822  call    ldapFree
0x180043827  mov     rcx, [rbp+rbx*8+310h+var_360]
0x18004382c  mov     edx, edi
0x18004382e  mov     rcx, [rcx]
0x180043831  call    ldapFree
0x180043836  mov     rcx, [rbp+rbx*8+310h+var_360]
0x18004383b  mov     edx, edi
0x18004383d  call    ldapFree
0x180043842  mov     [rbp+rbx*8+310h+var_360], 0
0x18004384b  mov     r14, qword ptr [rsp+410h+var_3BB+3]
0x180043850  mov     ebx, [rsi+1C8h]
0x180043856  lea     rdx, [rbp+310h+SiteName]; SiteName
0x18004385a  and     ebx, 10C0h
0x180043860  mov     [rbp+310h+SiteName], 0
0x180043868  xor     ecx, ecx; ComputerName
0x18004386a  bts     ebx, 0Fh
0x18004386e  call    cs:__imp_DsGetSiteNameW
0x180043875  nop     dword ptr [rax+rax+00h]
0x18004387a  mov     r8, [rbp+310h+SiteName]; SiteName
0x18004387e  lea     rax, [rbp+310h+GetDcContextHandle]
0x180043882  mov     [rsp+410h+RetGetDcContext], rax; RetGetDcContext
0x180043887  xor     r9d, r9d; DomainGuid
0x18004388a  mov     [rsp+410h+DcFlags], ebx; DcFlags
0x18004388e  xor     edx, edx; OptionFlags
0x180043890  mov     rcx, r12; DnsName
0x180043893  mov     [rsp+410h+DnsForestName], 0; DnsForestName
0x18004389c  call    cs:__imp_DsGetDcOpenW
0x1800438a3  nop     dword ptr [rax+rax+00h]
0x1800438a8  mov     ebx, eax
0x1800438aa  test    eax, eax
0x1800438ac  jnz     loc_180043D28
0x1800438b2  mov     [rsp+410h+var_3BC], 1
0x1800438b7  lea     edi, [rax+5Ah]
0x1800438ba  cmp     r15d, 63h ; 'c'
0x1800438be  jnb     loc_180043BAB
0x1800438c4  mov     rcx, [rbp+310h+GetDcContextHandle]; GetDcContextHandle
0x1800438c8  lea     r9, [rsp+410h+var_3BB+3]; DnsHostName
0x1800438cd  lea     r8, [rsp+410h+pAddrInfo]; SockAddresses
0x1800438d2  mov     qword ptr [rsp+410h+var_3BB+3], 0
0x1800438db  lea     rdx, [rsp+410h+SockAddressCount]; SockAddressCount
0x1800438e0  mov     [rsp+410h+pAddrInfo], 0
0x1800438e9  mov     [rsp+410h+SockAddressCount], 0
0x1800438f1  xor     r14d, r14d
0x1800438f4  call    cs:__imp_DsGetDcNextW
0x1800438fb  nop     dword ptr [rax+rax+00h]
0x180043900  mov     rcx, qword ptr [rsp+410h+var_3BB+3]; Src
0x180043905  mov     ebx, eax
0x180043907  test    rcx, rcx
0x18004390a  jz      short loc_180043937
0x18004390c  test    eax, eax
0x18004390e  jnz     short loc_18004392B
0x180043910  xor     edx, edx
0x180043912  mov     r8d, 7473484Ch
0x180043918  call    ldap_dup_stringW
0x18004391d  mov     rcx, qword ptr [rsp+410h+var_3BB+3]; Buffer
0x180043922  test    rax, rax
0x180043925  mov     r14, rax
0x180043928  cmovz   ebx, edi
0x18004392b  call    cs:__imp_NetApiBufferFree
0x180043932  nop     dword ptr [rax+rax+00h]
0x180043937  test    ebx, ebx
0x180043939  jnz     loc_180043BAB
0x18004393f  xor     r13d, r13d
0x180043942  cmp     r13d, [rsp+410h+SockAddressCount]
0x180043947  jnb     loc_180043B59
0x18004394d  cmp     r15d, 63h ; 'c'
0x180043951  jnb     loc_180043B59
0x180043957  mov     edx, 7264534Ch
0x18004395c  mov     ecx, 10h
0x180043961  call    ldapMalloc
0x180043966  mov     r12d, r15d
0x180043969  mov     [rbp+r12*8+310h+var_360], rax
0x18004396e  test    rax, rax
0x180043971  jz      loc_180043BA4
0x180043977  mov     edx, 7264534Ch
0x18004397c  mov     ecx, 10h
0x180043981  call    ldapMalloc
0x180043986  mov     rcx, [rbp+r12*8+310h+var_360]
0x18004398b  mov     edx, 7264534Ch
0x180043990  mov     [rcx], rax
0x180043993  mov     rcx, [rbp+r12*8+310h+var_360]
0x180043998  cmp     qword ptr [rcx], 0
0x18004399c  jz      loc_180043B96
0x1800439a2  mov     rax, [rsp+410h+pAddrInfo]
0x1800439a7  mov     ecx, r13d
0x1800439aa  shl     rcx, 4
0x1800439ae  mov     qword ptr [rsp+410h+var_3BB+3], rcx
0x1800439b3  movsxd  rcx, dword ptr [rcx+rax+8]
0x1800439b8  mov     eax, 80h
0x1800439bd  cmp     rcx, rax
0x1800439c0  cmovb   rcx, rax
0x1800439c4  call    ldapMalloc
0x1800439c9  mov     rcx, [rbp+r12*8+310h+var_360]
0x1800439ce  mov     rdx, [rcx]
0x1800439d1  mov     [rdx], rax
0x1800439d4  mov     rax, [rbp+r12*8+310h+var_360]
0x1800439d9  mov     r8, [rax]
0x1800439dc  cmp     qword ptr [r8], 0
0x1800439e0  jz      loc_180043B7F
0x1800439e6  mov     rax, [rsp+410h+pAddrInfo]
0x1800439eb  mov     r9, qword ptr [rsp+410h+var_3BB+3]
0x1800439f0  mov     ecx, [r9+rax+8]
0x1800439f5  mov     [r8+8], ecx
0x1800439f9  mov     rdx, [rsp+410h+pAddrInfo]
0x1800439fe  mov     rax, [rbp+r12*8+310h+var_360]
0x180043a03  movsxd  r8, dword ptr [r9+rdx+8]; Size
0x180043a08  mov     rcx, [rax]
0x180043a0b  mov     rdx, [r9+rdx]; Src
  ... truncated ...
```
