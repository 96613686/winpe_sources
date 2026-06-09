# GetDomainHierarchyIpAddrs(DiscoveryType,ulong,ulong,ushort * *,ushort * *,DiscoveryType *,NtpDiscoveryError *,AuthType *)

- ea: `0x1800136d0`
- end: `0x18001404d`
- name: `?GetDomainHierarchyIpAddrs@@YAJW4DiscoveryType@@KKPEAPEAG1PEAW41@PEAW4NtpDiscoveryError@@PEAW4AuthType@@@Z`
- size: `2429`
- prototype: `__int64 __fastcall(int, __int64, unsigned int, unsigned __int16 **, _QWORD *, _DWORD *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800127f4`

## callees

- `0x18000bde0`
- `0x1800136d0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013af6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fe5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013f1d`
- `logoncli!NetLogonGetTimeServiceParentDomain` at `0x1800138e0`
- `logoncli!NetLogonGetTimeServiceParentDomain` at `0x1800138e0`
- `logoncli!DsGetDcNameW` at `0x180013bec`
- `logoncli!DsGetDcNameW` at `0x180013de6`
- `logoncli!DsGetDcNameW` at `0x180013bec`
- `logoncli!DsGetDcNameW` at `0x180013de6`
- `logoncli!DsGetSiteNameW` at `0x18001385d`
- `logoncli!DsGetSiteNameW` at `0x18001385d`
- `DSROLE!DsRoleFreeMemory` at `0x180013fbb`
- `DSROLE!DsRoleFreeMemory` at `0x180013fbb`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18001380c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18001380c`
- `netutils!NetApiBufferFree` at `0x180013d4e`
- `netutils!NetApiBufferFree` at `0x180013d77`
- `netutils!NetApiBufferFree` at `0x180013fa5`
- `netutils!NetApiBufferFree` at `0x180013fd1`
- `netutils!NetApiBufferFree` at `0x180013ffe`
- `netutils!NetApiBufferFree` at `0x180014014`
- `netutils!NetApiBufferFree` at `0x180013d4e`
- `netutils!NetApiBufferFree` at `0x180013d77`
- `netutils!NetApiBufferFree` at `0x180013fa5`
- `netutils!NetApiBufferFree` at `0x180013fd1`
- `netutils!NetApiBufferFree` at `0x180013ffe`
- `netutils!NetApiBufferFree` at `0x180014014`

## string_xrefs

- `0x180013928`: `NetLogonGetTimeServiceParentDomain dwErr = %d netlogonbits = %d.\n`
- `0x180013c7f`: `Query %d: no DC found (PDC isn't a time service)\n`

## pseudocode

```c
__int64 __fastcall GetDomainHierarchyIpAddrs(
        int a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 **a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7,
        int *a8)
{
  _DWORD *v8; // r15
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rcx
  ULONG v15; // esi
  unsigned __int16 *v16; // r12
  signed int PrimaryDomainInformation; // eax
  DWORD DcNameW; // ebx
  bool v19; // cc
  DWORD TimeServiceParentDomain; // eax
  int v21; // r15d
  unsigned int v22; // esi
  int v23; // ecx
  int v24; // r11d
  bool v25; // r9
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // r15
  __int32 v30; // eax
  __int32 v31; // r9d
  __int32 v32; // r10d
  const WCHAR *v33; // rbx
  const WCHAR *v34; // rdx
  unsigned int v35; // r8d
  __int32 v36; // r13d
  ULONG Flags; // esi
  BOOL v38; // ecx
  int v39; // eax
  bool v40; // zf
  char v41; // al
  int v42; // esi
  ULONG v43; // edx
  unsigned int v44; // ebx
  const WCHAR *v45; // r9
  PDOMAIN_CONTROLLER_INFOW v46; // rcx
  _DWORD *v47; // rax
  int v48; // ecx
  LPWSTR DomainControllerName; // rcx
  __int64 v50; // rbx
  __int64 v51; // rax
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rbx
  unsigned __int16 *v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // r10
  PDOMAIN_CONTROLLER_INFOW *DomainControllerInfo; // [rsp+28h] [rbp-D8h]
  int v59; // [rsp+30h] [rbp-D0h]
  PDOMAIN_CONTROLLER_INFOW v60; // [rsp+38h] [rbp-C8h] BYREF
  PDOMAIN_CONTROLLER_INFOW v61; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v62; // [rsp+48h] [rbp-B8h]
  int v63; // [rsp+4Ch] [rbp-B4h]
  PBYTE Buffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v65; // [rsp+58h] [rbp-A8h]
  LPVOID v66; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR SiteName; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+70h] [rbp-90h] BYREF
  __int32 v69; // [rsp+74h] [rbp-8Ch]
  __int32 v70; // [rsp+78h] [rbp-88h]
  __int32 v71; // [rsp+7Ch] [rbp-84h]
  int v72; // [rsp+80h] [rbp-80h]
  LPCWSTR v73; // [rsp+88h] [rbp-78h]
  _DWORD *v74; // [rsp+90h] [rbp-70h]
  _DWORD *v75; // [rsp+98h] [rbp-68h]
  int *v76; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v77; // [rsp+A8h] [rbp-58h]
  _QWORD *v78; // [rsp+B0h] [rbp-50h]
  __m128i si128; // [rsp+C0h] [rbp-40h]
  LPCWSTR DomainName; // [rsp+D0h] [rbp-30h]
  LPWSTR v81; // [rsp+D8h] [rbp-28h]
  ULONG v82; // [rsp+E0h] [rbp-20h]
  _QWORD v83[2]; // [rsp+E4h] [rbp-1Ch]
  int v84; // [rsp+F4h] [rbp-Ch]
  __int64 v85; // [rsp+F8h] [rbp-8h]
  LPWSTR v86; // [rsp+100h] [rbp+0h]
  int v87; // [rsp+108h] [rbp+8h]
  int v88; // [rsp+10Ch] [rbp+Ch]
  __m128i v89; // [rsp+110h] [rbp+10h]
  __int64 v90; // [rsp+120h] [rbp+20h]
  LPWSTR v91; // [rsp+128h] [rbp+28h]
  int v92; // [rsp+130h] [rbp+30h]
  int v93; // [rsp+134h] [rbp+34h]
  int v94; // [rsp+138h] [rbp+38h]
  BOOL v95; // [rsp+13Ch] [rbp+3Ch]
  int v96; // [rsp+140h] [rbp+40h]
  int v97; // [rsp+144h] [rbp+44h]
  LPVOID v98; // [rsp+148h] [rbp+48h]
  __int64 v99; // [rsp+150h] [rbp+50h]
  int v100; // [rsp+158h] [rbp+58h]
  int v101; // [rsp+15Ch] [rbp+5Ch]
  int v102; // [rsp+160h] [rbp+60h]
  BOOL v103; // [rsp+164h] [rbp+64h]
  int v104; // [rsp+168h] [rbp+68h]
  int v105; // [rsp+16Ch] [rbp+6Ch]
  __int128 v106; // [rsp+170h] [rbp+70h]
  int v107; // [rsp+180h] [rbp+80h]
  int v108; // [rsp+184h] [rbp+84h]
  int v109; // [rsp+188h] [rbp+88h]
  BOOL v110; // [rsp+18Ch] [rbp+8Ch]
  __int64 v111; // [rsp+190h] [rbp+90h]
  __int64 v112; // [rsp+198h] [rbp+98h]
  __int64 v113; // [rsp+1A0h] [rbp+A0h]
  unsigned int v114; // [rsp+1A8h] [rbp+A8h]
  int v115; // [rsp+1ACh] [rbp+ACh]
  unsigned __int16 v116[20]; // [rsp+1B0h] [rbp+B0h] BYREF

  v8 = a7;
  v78 = a5;
  *a7 = 3;
  v77 = a4;
  v74 = a6;
  *a6 = 0;
  *a8 = 0;
  v75 = a7;
  v76 = a8;
  v61 = 0;
  v60 = 0;
  Buffer = 0;
  v66 = 0;
  SiteName = 0;
  if ( a1 == 2 )
  {
    v10 = 2147483646;
    v11 = L"FORCE";
    v12 = 20;
    v13 = v116;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v15 = 18945;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
  }
  else
  {
    if ( a1 == 1 )
    {
      StringCchCopyW(v116, 0x14u, L"FOREGROUND");
    }
    else
    {
      if ( !a1 )
      {
        StringCchCopyW(v116, 0x14u, L"BACKGROUND");
        v15 = 19200;
        goto LABEL_15;
      }
      v116[0] = 0;
    }
    v15 = 18944;
  }
LABEL_15:
  v16 = 0;
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  DcNameW = PrimaryDomainInformation;
  v19 = PrimaryDomainInformation <= 0;
  if ( PrimaryDomainInformation )
  {
LABEL_16:
    if ( v19 )
      goto LABEL_143;
    DcNameW = (unsigned __int16)PrimaryDomainInformation;
    goto LABEL_18;
  }
  if ( *(_DWORD *)Buffer != 1 && (unsigned int)(*(_DWORD *)Buffer - 3) > 2 )
  {
    *a7 = 4;
    DcNameW = -2147023471;
    goto LABEL_143;
  }
  PrimaryDomainInformation = DsGetSiteNameW(0, &SiteName);
  DcNameW = PrimaryDomainInformation;
  if ( PrimaryDomainInformation && PrimaryDomainInformation != 1919 )
  {
LABEL_24:
    v19 = PrimaryDomainInformation <= 0;
    goto LABEL_16;
  }
  if ( ((*(_DWORD *)Buffer - 1) & 0xFFFFFFFD) != 0 )
  {
    v68 = 0;
    v59 = *((_DWORD *)Buffer + 1) & 8;
    if ( v59 && !*((_BYTE *)g_pnpstate + 548) && (a3 & 0x200) != 0 && (unsigned __int8)FileLogAllowEntry(111) )
      FileLogAdd(
        L"Machine is an RODC with chaining enabled and set to be a GTIMESERV. These are mutually exclusive. Please disabling GTIMESERV.\n");
    TimeServiceParentDomain = NetLogonGetTimeServiceParentDomain(0, &v66, &v68);
    DcNameW = TimeServiceParentDomain;
    if ( !TimeServiceParentDomain || TimeServiceParentDomain == 1355 )
    {
      v21 = v15 | 0x2000;
      v22 = v15 & 0xFFFFF77F | 0x80;
      if ( (unsigned __int8)FileLogAllowEntry(111) )
        FileLogAdd(L"NetLogonGetTimeServiceParentDomain dwErr = %d netlogonbits = %d.\n", DcNameW, a3);
      v23 = *((_DWORD *)g_pnpstate + 43);
      v24 = *(_DWORD *)Buffer;
      v63 = *(_DWORD *)Buffer;
      v25 = v23 == 1 && v24 == 5 || v23 == 2;
      v85 = *((_QWORD *)Buffer + 2);
      v90 = v85;
      v72 = a3 & 0x200;
      v92 = v22 | 0x20000;
      v82 = v21 | 0x20000;
      v87 = v21 | 0x20000;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = !v25;
      v26 = 6;
      v89 = _mm_load_si128((const __m128i *)&_xmm);
      if ( !SiteName )
        v26 = 14;
      v100 = v21;
      v101 = v26;
      v107 = v21;
      DomainName = (LPCWSTR)v66;
      v81 = SiteName;
      v83[0] = 14;
      v103 = !v25;
      v27 = 4;
      v83[1] = 1;
      if ( !SiteName )
        v27 = 12;
      v84 = 1;
      v108 = v27;
      v86 = SiteName;
      v88 = 12;
      v91 = SiteName;
      v110 = !v25;
      v28 = 1;
      v93 = 9;
      if ( !SiteName )
        v28 = 9;
      v94 = 1;
      v115 = v28;
      v29 = 0;
      v96 = 1;
      v97 = 1;
      v98 = v66;
      v99 = 0;
      v102 = 0;
      v104 = 0;
      v105 = 1;
      v106 = 0;
      v109 = 0;
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v114 = v22;
      v62 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v29 >= 6 )
        {
          v8 = v75;
          goto LABEL_121;
        }
        v30 = si128.m128i_i32[10 * v29 + 1];
        v31 = si128.m128i_i32[10 * v29 + 2];
        v32 = si128.m128i_i32[10 * v29 + 3];
        v33 = (&DomainName)[5 * v29];
        v34 = (&v81)[5 * v29];
        v35 = v83[5 * v29];
        v36 = si128.m128i_i32[10 * v29];
        Flags = *(&v82 + 10 * v29);
        v38 = 0;
        v69 = v30;
        v70 = v31;
        v71 = v32;
        v73 = v34;
        v65 = v35;
        if ( v33 )
        {
          if ( v66 )
          {
            v39 = _o__wcsicmp(v33, v66);
            v34 = v73;
            v31 = v70;
            v40 = v39 == 0;
            v30 = v69;
            v32 = v71;
            v38 = v40;
            v24 = v63;
          }
          v35 = v65;
        }
        if ( (!v36 || v33)
          && (!v30 || v34)
          && v35 > v62
          && (!v72 && v24 != 5 || v31 && v72 || v32 && v24 == 5)
          && (!v59 || !v38) )
        {
          if ( *((_BYTE *)g_pnpstate + 508) )
          {
            Flags |= 0x1000u;
            if ( !*((_BYTE *)g_pnpstate + 548) )
              Flags |= 0x80000u;
          }
          if ( (unsigned __int8)FileLogAllowEntry(111) )
          {
            LODWORD(DomainControllerInfo) = Flags;
            FileLogAdd(
              L"Query %d (%s): <SITE: %s, DOM: %s, FLAGS: %08X>\n",
              (unsigned int)v29,
              v116,
              v73,
              v33,
              DomainControllerInfo);
          }
          DcNameW = DsGetDcNameW(0, v33, 0, v73, Flags, &v61);
          if ( DcNameW )
          {
            v41 = FileLogAllowEntry(111);
            if ( DcNameW != 1355 )
            {
              if ( v41 )
                FileLogAdd(L"Query %d: error: %08X\n", (unsigned int)v29, DcNameW);
              break;
            }
            if ( v41 )
              FileLogAdd(L"Query %d: no DC found.\n", (unsigned int)v29);
          }
          else if ( (Flags & 0x2000) == 0 || (v61->Flags & 0x200) != 0 || v36 || v59 )
          {
            v42 = Flags & 0x80;
            if ( !v42 || (v61->Flags & 0x40) != 0 )
            {
              if ( v63 == 5 && !v36 && (v61->Flags & 1) != 0 )
              {
                *v74 = 1;
                if ( (unsigned __int8)FileLogAllowEntry(111) )
                  FileLogAdd(L"Query %d: no DC found (found the PDC when we are the PDC)\n", (unsigned int)v29);
              }
              else if ( !v59 || (v61->Flags & 0x1000) != 0 )
              {
                v43 = v61->Flags;
                v44 = (v36 != 0 ? 2 : 0) + ((v43 >> 4) & 8);
                if ( v42 )
                {
                  ++v44;
                }
                else if ( (v43 & 0x200) != 0 )
                {
                  v44 += 4;
                }
                if ( (unsigned __int8)FileLogAllowEntry(111) )
                  FileLogAdd(L"Query %d: %s found.  Score: %u\n", (unsigned int)v29, v61->DomainControllerName, v44);
                if ( v44 > v62 )
                {
                  if ( v60 )
                    NetApiBufferFree(v60);
                  v60 = v61;
                  v61 = 0;
                  v62 = v44;
                }
              }
              else if ( (unsigned __int8)FileLogAllowEntry(111) )
              {
                FileLogAdd(L"Query %d: RODC found non-longhorn DC. Skipping.\n");
              }
            }
            else if ( (unsigned __int8)FileLogAllowEntry(111) )
            {
              FileLogAdd(L"Query %d: no DC found (PDC isn't a time service)\n", (unsigned int)v29);
            }
          }
          else if ( (unsigned __int8)FileLogAllowEntry(111) )
          {
            FileLogAdd(
              L"Query %d: no DC found (asked for reliable timeserv, got regular timeserv)\n",
              (unsigned int)v29);
          }
          if ( v61 )
          {
            NetApiBufferFree(v61);
            v61 = 0;
          }
        }
        v24 = v63;
        v29 = (unsigned int)(v29 + 1);
      }
    }
    if ( (int)DcNameW > 0 )
    {
      DcNameW = (unsigned __int16)DcNameW;
LABEL_18:
      DcNameW |= 0x80070000;
    }
  }
  else
  {
    if ( *((_DWORD *)g_pnpstate + 43) == 2 || (v45 = SiteName) == 0 )
      v45 = 0;
    PrimaryDomainInformation = DsGetDcNameW(0, 0, 0, v45, v15, &v60);
    DcNameW = PrimaryDomainInformation;
    if ( PrimaryDomainInformation )
    {
      if ( PrimaryDomainInformation != 1355 )
        goto LABEL_24;
      if ( (unsigned __int8)FileLogAllowEntry(111) )
        FileLogAdd(L"Domain member query: no DC found.\n");
    }
    else if ( (unsigned __int8)FileLogAllowEntry(111) )
    {
      FileLogAdd(L"Domain member syncing from %s.\n", v60->DomainControllerName);
    }
LABEL_121:
    v46 = v60;
    if ( v60 )
    {
      v47 = v74;
      *v8 = 0;
      *v47 = 1;
      if ( (*((_BYTE *)g_pnpstate + 204) & 1) != 0 )
        v48 = ((v46->Flags & 0x4000) != 0) + 1;
      else
        v48 = 1;
      *v76 = v48;
      DomainControllerName = v60->DomainControllerName;
      if ( *v60->DomainControllerName == 92 && DomainControllerName[1] == 92 )
      {
        v50 = -1;
        v51 = -1;
        do
          ++v51;
        while ( DomainControllerName[v51 + 2] );
        v52 = v51 + 1;
        v16 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v51 + 1));
        if ( !v16 )
          goto LABEL_130;
        StringCchCopyW(v16, v52, (const unsigned __int16 *)v60->DomainControllerName + 2);
        do
          ++v50;
        while ( v60->DomainName[v50] );
        v53 = v50 + 1;
        v54 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v53);
        if ( v54 )
        {
          StringCchCopyW(v54, v53, v60->DomainName);
          DcNameW = 0;
          v55 = v78;
          *v77 = v16;
          v16 = 0;
          *v55 = v56;
        }
        else
        {
LABEL_130:
          DcNameW = -2147024882;
        }
      }
      else
      {
        DcNameW = -2147418113;
      }
    }
    else
    {
      if ( *(_DWORD *)Buffer != 5 || v66 )
      {
        if ( (*((_DWORD *)Buffer + 1) & 0x1000000) != 0 )
          *v8 = 3;
        else
          *v8 = 2;
      }
      else
      {
        *v8 = 1;
      }
      DcNameW = -2147023135;
    }
  }
LABEL_143:
  if ( v61 )
    NetApiBufferFree(v61);
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  if ( v60 )
    NetApiBufferFree(v60);
  if ( v16 )
    LocalFree(v16);
  if ( v66 )
    NetApiBufferFree(v66);
  if ( SiteName )
    NetApiBufferFree(SiteName);
  return DcNameW;
}

```

## disassembly

```asm
0x1800136d0  mov     [rsp-8+arg_0], rbx
0x1800136d5  push    rbp
0x1800136d6  push    rsi
0x1800136d7  push    rdi
0x1800136d8  push    r12
0x1800136da  push    r13
0x1800136dc  push    r14
0x1800136de  push    r15
0x1800136e0  lea     rbp, [rsp-0E0h]
0x1800136e8  sub     rsp, 1E0h
0x1800136ef  mov     rax, cs:__security_cookie
0x1800136f6  xor     rax, rsp
0x1800136f9  mov     [rbp+110h+var_38], rax
0x180013700  mov     rax, [rbp+110h+arg_20]
0x180013707  xor     r14d, r14d
0x18001370a  mov     r15, [rbp+110h+arg_30]
0x180013711  mov     r13d, r8d
0x180013714  mov     rdx, [rbp+110h+arg_38]
0x18001371b  mov     [rbp+110h+var_160], rax
0x18001371f  mov     rax, [rbp+110h+arg_28]
0x180013726  lea     edi, [r14+1]
0x18001372a  mov     dword ptr [r15], 3
0x180013731  mov     [rbp+110h+var_168], r9
0x180013735  mov     [rbp+110h+var_180], rax
0x180013739  mov     [rax], r14d
0x18001373c  mov     [rdx], r14d
0x18001373f  mov     [rbp+110h+var_178], r15
0x180013743  mov     [rbp+110h+var_170], rdx
0x180013747  mov     [rsp+210h+var_1D0], r14
0x18001374c  mov     [rsp+210h+var_1D8], r14
0x180013751  mov     [rsp+210h+Buffer], r14
0x180013756  mov     [rsp+210h+var_1B0], r14
0x18001375b  mov     [rsp+210h+SiteName], r14
0x180013760  cmp     ecx, 2
0x180013763  jnz     short loc_1800137B4
0x180013765  mov     ecx, 7FFFFFFEh
0x18001376a  lea     r8, aForce; "FORCE"
0x180013771  lea     edx, [rdi+13h]
0x180013774  lea     rax, [rbp+110h+var_60]
0x18001377b  test    rcx, rcx
0x18001377e  jz      short loc_18001379E
0x180013780  movzx   r9d, word ptr [r8]
0x180013784  test    r9w, r9w
0x180013788  jz      short loc_18001379E
0x18001378a  mov     [rax], r9w
0x18001378e  add     r8, 2
0x180013792  add     rax, 2
0x180013796  sub     rcx, rdi
0x180013799  sub     rdx, rdi
0x18001379c  jnz     short loc_18001377B
0x18001379e  test    rdx, rdx
0x1800137a1  lea     rcx, [rax-2]
0x1800137a5  mov     esi, 4A01h
0x1800137aa  cmovnz  rcx, rax
0x1800137ae  mov     [rcx], r14w
0x1800137b2  jmp     short loc_180013800
0x1800137b4  cmp     ecx, edi
0x1800137b6  jnz     short loc_1800137D2
0x1800137b8  lea     r8, aForeground; "FOREGROUND"
0x1800137bf  mov     edx, 14h; unsigned __int64
0x1800137c4  lea     rcx, [rbp+110h+var_60]; unsigned __int16 *
0x1800137cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800137d0  jmp     short loc_1800137FB
0x1800137d2  test    ecx, ecx
0x1800137d4  jnz     short loc_1800137F3
0x1800137d6  lea     edx, [rcx+14h]; unsigned __int64
0x1800137d9  lea     rcx, [rbp+110h+var_60]; unsigned __int16 *
0x1800137e0  lea     r8, aBackground; "BACKGROUND"
0x1800137e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800137ec  mov     esi, 4B00h
0x1800137f1  jmp     short loc_180013800
0x1800137f3  mov     [rbp+110h+var_60], r14w
0x1800137fb  mov     esi, 4A00h
0x180013800  lea     r8, [rsp+210h+Buffer]; Buffer
0x180013805  mov     edx, edi; InfoLevel
0x180013807  xor     ecx, ecx; lpServer
0x180013809  mov     r12, r14
0x18001380c  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180013813  nop     dword ptr [rax+rax+00h]
0x180013818  mov     ebx, eax
0x18001381a  test    eax, eax
0x18001381c  jz      short loc_180013832
0x18001381e  jle     loc_180013F9B
0x180013824  movzx   ebx, ax
0x180013827  or      ebx, 80070000h
0x18001382d  jmp     loc_180013F9B
0x180013832  mov     rax, [rsp+210h+Buffer]
0x180013837  mov     eax, [rax]
0x180013839  cmp     eax, edi
0x18001383b  jz      short loc_180013856
0x18001383d  add     eax, 0FFFFFFFDh
0x180013840  cmp     eax, 2
0x180013843  jbe     short loc_180013856
0x180013845  mov     dword ptr [r15], 4
0x18001384c  mov     ebx, 80070591h
0x180013851  jmp     loc_180013F9B
0x180013856  lea     rdx, [rsp+210h+SiteName]; SiteName
0x18001385b  xor     ecx, ecx; ComputerName
0x18001385d  call    cs:__imp_DsGetSiteNameW
0x180013864  nop     dword ptr [rax+rax+00h]
0x180013869  mov     ebx, eax
0x18001386b  test    eax, eax
0x18001386d  jz      short loc_18001387A
0x18001386f  cmp     eax, 77Fh
0x180013874  jz      short loc_18001387A
0x180013876  test    eax, eax
0x180013878  jmp     short loc_18001381E
0x18001387a  mov     rcx, [rsp+210h+Buffer]
0x18001387f  mov     eax, [rcx]
0x180013881  sub     eax, edi
0x180013883  test    eax, 0FFFFFFFDh
0x180013888  jz      loc_180013DB4
0x18001388e  mov     [rsp+210h+var_1A0], r14d
0x180013893  mov     r14d, 6Fh ; 'o'
0x180013899  mov     eax, [rcx+4]
0x18001389c  and     eax, 8
0x18001389f  mov     [rsp+210h+var_1E0], eax
0x1800138a3  jz      short loc_1800138D4
0x1800138a5  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800138ac  cmp     [rax+224h], r12b
0x1800138b3  jnz     short loc_1800138D4
0x1800138b5  bt      r13d, 9
0x1800138ba  jnb     short loc_1800138D4
0x1800138bc  mov     ecx, r14d
0x1800138bf  call    FileLogAllowEntry
0x1800138c4  test    al, al
0x1800138c6  jz      short loc_1800138D4
0x1800138c8  lea     rcx, aMachineIsAnRod; "Machine is an RODC with chaining enable"...
0x1800138cf  call    FileLogAdd
0x1800138d4  lea     r8, [rsp+210h+var_1A0]
0x1800138d9  xor     ecx, ecx
0x1800138db  lea     rdx, [rsp+210h+var_1B0]
0x1800138e0  call    cs:__imp_NetLogonGetTimeServiceParentDomain
0x1800138e7  nop     dword ptr [rax+rax+00h]
0x1800138ec  mov     ebx, eax
0x1800138ee  test    eax, eax
0x1800138f0  jz      short loc_180013909
0x1800138f2  cmp     eax, 54Bh
0x1800138f7  jz      short loc_180013909
0x1800138f9  test    ebx, ebx
0x1800138fb  jle     loc_180013F9B
0x180013901  movzx   ebx, bx
0x180013904  jmp     loc_180013827
0x180013909  mov     r15d, esi
0x18001390c  mov     ecx, r14d
0x18001390f  btr     esi, 0Bh
0x180013913  bts     r15d, 0Dh
0x180013918  bts     esi, 7
0x18001391c  call    FileLogAllowEntry
0x180013921  test    al, al
0x180013923  jz      short loc_180013936
0x180013925  mov     r8d, r13d
0x180013928  lea     rcx, aNetlogongettim; "NetLogonGetTimeServiceParentDomain dwEr"...
0x18001392f  mov     edx, ebx
0x180013931  call    FileLogAdd
0x180013936  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001393d  mov     r10, [rsp+210h+Buffer]
0x180013942  mov     ecx, [rax+0ACh]
0x180013948  mov     r11d, [r10]
0x18001394b  mov     [rsp+210h+var_1C4], r11d
0x180013950  cmp     ecx, edi
0x180013952  jnz     short loc_18001395A
0x180013954  cmp     r11d, 5
0x180013958  jz      short loc_180013964
0x18001395a  cmp     ecx, 2
0x18001395d  jz      short loc_180013964
0x18001395f  xor     r9b, r9b
0x180013962  jmp     short loc_180013967
0x180013964  mov     r9b, dil
0x180013967  mov     rdx, [rsp+210h+SiteName]
0x18001396c  and     r13d, 200h
0x180013973  mov     rax, [r10+10h]
0x180013977  mov     ecx, r15d
0x18001397a  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180013982  mov     ebx, 20000h
0x180013987  mov     r8, [rsp+210h+var_1B0]
0x18001398c  or      ecx, ebx
0x18001398e  mov     [rbp+110h+var_118], rax
0x180013992  mov     [rbp+110h+var_F0], rax
0x180013996  mov     eax, esi
0x180013998  or      eax, ebx
0x18001399a  mov     [rbp+110h+var_190], r13d
0x18001399e  mov     [rbp+110h+var_E0], eax
0x1800139a1  mov     r13d, 0Eh
0x1800139a7  xor     eax, eax
0x1800139a9  mov     [rbp+110h+var_130], ecx
0x1800139ac  test    r9b, r9b
0x1800139af  mov     [rbp+110h+var_108], ecx
0x1800139b2  movups  [rbp+110h+var_150], xmm0
0x1800139b6  lea     ecx, [r13-2]
0x1800139ba  setz    al
0x1800139bd  movdqa  xmm0, cs:__xmm@00000000000000000000000100000000
0x1800139c5  lea     r10d, [r13-5]
0x1800139c9  mov     [rbp+110h+var_D4], eax
0x1800139cc  test    rdx, rdx
0x1800139cf  lea     eax, [rcx-6]
0x1800139d2  movdqa  [rbp+110h+var_100], xmm0
0x1800139d7  cmovz   eax, r13d
0x1800139db  mov     [rbp+110h+var_B8], r15d
0x1800139df  mov     [rbp+110h+var_B4], eax
0x1800139e2  xorps   xmm0, xmm0
0x1800139e5  xor     eax, eax
0x1800139e7  mov     [rbp+110h+var_90], r15d
0x1800139ee  test    r9b, r9b
0x1800139f1  mov     [rbp+110h+DomainName], r8
0x1800139f5  mov     [rbp+110h+var_138], rdx
0x1800139f9  setz    al
0x1800139fc  mov     [rbp+110h+var_12C], r13
0x180013a00  mov     [rbp+110h+var_AC], eax
0x180013a03  test    rdx, rdx
0x180013a06  lea     eax, [rcx-8]
0x180013a09  mov     [rbp+110h+var_124], 1
0x180013a11  cmovz   eax, ecx
0x180013a14  mov     [rbp+110h+var_11C], edi
0x180013a17  mov     [rbp+110h+var_8C], eax
0x180013a1d  xor     eax, eax
0x180013a1f  test    r9b, r9b
0x180013a22  mov     [rbp+110h+var_110], rdx
0x180013a26  mov     [rbp+110h+var_104], ecx
0x180013a29  setz    al
0x180013a2c  mov     [rbp+110h+var_E8], rdx
0x180013a30  mov     [rbp+110h+var_84], eax
0x180013a36  test    rdx, rdx
0x180013a39  mov     eax, edi
0x180013a3b  mov     [rbp+110h+var_DC], r10d
0x180013a3f  cmovz   eax, r10d
0x180013a43  mov     [rbp+110h+var_D8], edi
0x180013a46  mov     [rbp+110h+var_64], eax
0x180013a4c  xor     r15d, r15d
0x180013a4f  mov     [rbp+110h+var_D0], edi
0x180013a52  mov     [rbp+110h+var_CC], edi
0x180013a55  mov     [rbp+110h+var_C8], r8
0x180013a59  mov     [rbp+110h+var_C0], r12
0x180013a5d  mov     [rbp+110h+var_B0], r12d
0x180013a61  mov     [rbp+110h+var_A8], r12d
0x180013a65  mov     [rbp+110h+var_A4], edi
0x180013a68  movdqa  [rbp+110h+var_A0], xmm0
0x180013a6d  mov     [rbp+110h+var_88], r12d
0x180013a74  mov     [rbp+110h+var_80], r12
0x180013a7b  mov     [rbp+110h+var_78], r12
0x180013a82  mov     [rbp+110h+var_70], r12
0x180013a89  mov     [rbp+110h+var_68], esi
0x180013a8f  mov     [rsp+210h+var_1C8], r12d
0x180013a94  cmp     r15d, 6
0x180013a98  jnb     loc_180013E43
0x180013a9e  lea     rcx, [r15+r15*4]
0x180013aa2  mov     eax, dword ptr [rbp+rcx*8+110h+var_150+4]
0x180013aa6  mov     r9d, dword ptr [rbp+rcx*8+110h+var_150+8]
0x180013aab  mov     r10d, dword ptr [rbp+rcx*8+110h+var_150+0Ch]
0x180013ab0  mov     rbx, [rbp+rcx*8+110h+DomainName]
0x180013ab5  mov     rdx, [rbp+rcx*8+110h+var_138]
0x180013aba  mov     r8d, dword ptr [rbp+rcx*8+110h+var_12C]
0x180013abf  mov     r13d, dword ptr [rbp+rcx*8+110h+var_150]
0x180013ac4  mov     esi, [rbp+rcx*8+110h+var_130]
0x180013ac8  xor     ecx, ecx
0x180013aca  mov     [rsp+210h+var_19C], eax
0x180013ace  mov     [rsp+210h+var_198], r9d
0x180013ad3  mov     [rsp+210h+var_194], r10d
0x180013ad8  mov     [rbp+110h+var_188], rdx
0x180013adc  mov     [rsp+210h+var_1B8], r8d
0x180013ae1  test    rbx, rbx
0x180013ae4  jz      short loc_180013B25
0x180013ae6  mov     r8, [rsp+210h+var_1B0]
0x180013aeb  test    r8, r8
0x180013aee  jz      short loc_180013B20
0x180013af0  mov     rdx, r8
0x180013af3  mov     rcx, rbx
0x180013af6  call    cs:__imp__o__wcsicmp
0x180013afd  nop     dword ptr [rax+rax+00h]
0x180013b02  mov     rdx, [rbp+110h+var_188]
0x180013b06  xor     ecx, ecx
0x180013b08  mov     r9d, [rsp+210h+var_198]
0x180013b0d  test    eax, eax
0x180013b0f  mov     eax, [rsp+210h+var_19C]
0x180013b13  mov     r10d, [rsp+210h+var_194]
0x180013b18  setz    cl
0x180013b1b  mov     r11d, [rsp+210h+var_1C4]
0x180013b20  mov     r8d, [rsp+210h+var_1B8]
0x180013b25  test    r13d, r13d
0x180013b28  jz      short loc_180013B33
0x180013b2a  test    rbx, rbx
0x180013b2d  jz      loc_180013D88
0x180013b33  test    eax, eax
0x180013b35  jz      short loc_180013B40
0x180013b37  test    rdx, rdx
0x180013b3a  jz      loc_180013D88
0x180013b40  cmp     r8d, [rsp+210h+var_1C8]
0x180013b45  jbe     loc_180013D88
0x180013b4b  mov     eax, [rbp+110h+var_190]
0x180013b4e  xor     edx, edx
0x180013b50  test    eax, eax
0x180013b52  jnz     short loc_180013B5A
0x180013b54  cmp     r11d, 5
0x180013b58  jnz     short loc_180013B76
0x180013b5a  test    r9d, r9d
0x180013b5d  jz      short loc_180013B63
0x180013b5f  test    eax, eax
0x180013b61  jnz     short loc_180013B76
0x180013b63  test    r10d, r10d
0x180013b66  jz      loc_180013D88
  ... truncated ...
```
