# SNIOpenSync

- ea: `0x100425000`
- end: `0x100425ba7`
- name: `SNIOpenSync`
- size: `2983`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100473340`

## callees

- `0x100421570`
- `0x100422710`
- `0x100422bc0`
- `0x100423130`
- `0x100423310`
- `0x100424650`
- `0x100425000`
- `0x100427e60`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100431f20`
- `0x1004349f0`
- `0x100439390`
- `0x10043b510`
- `0x100453cd0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1004250b8`
- `KERNEL32!GetTickCount` at `0x10042570b`
- `KERNEL32!GetTickCount` at `0x1004250b8`
- `KERNEL32!GetTickCount` at `0x10042570b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100425ab4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100425b0a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100425ab4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100425b0a`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10042528f`
- `api-ms-win-crt-string-l1-1-0!wmemmove_s` at `0x10042528f`
- `USER32!CharNextW` at `0x100425124`
- `USER32!CharNextW` at `0x100425149`
- `USER32!CharNextW` at `0x1004251d3`
- `USER32!CharNextW` at `0x1004251f7`
- `USER32!CharNextW` at `0x100425844`
- `USER32!CharNextW` at `0x100425124`
- `USER32!CharNextW` at `0x100425149`
- `USER32!CharNextW` at `0x1004251d3`
- `USER32!CharNextW` at `0x1004251f7`
- `USER32!CharNextW` at `0x100425844`

## string_xrefs

- `0x100425046`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425257`: `sql\common\dk\sni\src\sni.cpp`
- `0x10042563b`: `sql\common\dk\sni\src\sni.cpp`
- `0x1004256a0`: `sql\common\dk\sni\src\sni.cpp`
- `0x1004256e0`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425744`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425ae3`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425b53`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425b78`: `sql\common\dk\sni\src\sni.cpp`
- `0x100425051`: `SNIOpenSync`
- `0x100425250`: `SNIOpenSync`
- `0x10042536c`: `SNIOpenSync`
- `0x100425634`: `SNIOpenSync`
- `0x100425699`: `SNIOpenSync`
- `0x1004256d9`: `SNIOpenSync`
- `0x10042573d`: `SNIOpenSync`
- `0x100425adc`: `SNIOpenSync`
- `0x100425b4c`: `SNIOpenSync`
- `0x100425b71`: `SNIOpenSync`
- `0x100425327`: `ERR|SNIpOpenInfo is NULL\n`
- `0x10042508e`: `API|SNIpConsumerInfo: %p{SNI_CONSUMER_INFO*}, szConnect: %p{LPSTR}, pOpenInfo: %p, ppConn: %p{SNI_Conn**}, fSync: %d{BOOL}, timeout: %d\n`
- `0x10042595c`: `sql\common\dk\sni\src\smux.cpp`
- `0x100425967`: `Smux::Open`
- `0x1004257a5`: `sql\common\dk\sni\src\sm.cpp`
- `0x1004258a6`: `sql\common\dk\sni\src\sm.cpp`
- `0x1004258cd`: `sql\common\dk\sni\src\sm.cpp`
- `0x100425914`: `sql\common\dk\sni\src\sm.cpp`
- `0x100425937`: `sql\common\dk\sni\src\sm.cpp`
- `0x1004257b0`: `Sm::OpenWithFallback`
- `0x10042589f`: `Sm::OpenWithFallback`
- `0x1004258c6`: `Sm::OpenWithFallback`
- `0x10042590d`: `Sm::OpenWithFallback`
- `0x100425930`: `Sm::OpenWithFallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SNIOpenSync(
        struct Sni_Consumer_Info *a1,
        wchar_t *a2,
        __int64 a3,
        struct SNI_Conn **a4,
        int a5,
        int a6)
{
  __int64 v6; // r14
  struct Sni_Consumer_Info *v8; // rsi
  unsigned int v9; // r12d
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rax
  WCHAR v13; // di
  unsigned int ProtElem; // ebx
  const WCHAR *v15; // r14
  const WCHAR *v16; // rsi
  const WCHAR *v17; // rcx
  int v18; // ebx
  LPWSTR v19; // rax
  __int64 v20; // rax
  rsize_t v21; // r14
  const WCHAR *v22; // rax
  const WCHAR *v23; // rsi
  WCHAR v24; // di
  const WCHAR *v25; // rcx
  int v26; // ebx
  LPWSTR v27; // rax
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  const wchar_t *v30; // r9
  rsize_t v31; // rbx
  __int64 v32; // rcx
  int v33; // edi
  char v34; // al
  int v35; // ebx
  unsigned int v36; // ecx
  unsigned int v37; // edx
  unsigned int v38; // ecx
  __int64 *v39; // rax
  struct SNI_Conn *v40; // rcx
  int v41; // edi
  int v42; // edi
  int v43; // edi
  char v44; // al
  int v45; // ebx
  DWORD v46; // ecx
  struct ProtElem *v47; // rsi
  struct Sni_Consumer_Info *v48; // r15
  char *v49; // rdi
  const WCHAR *v50; // rcx
  int v51; // ebx
  LPWSTR v52; // rax
  __int64 v53; // rax
  unsigned int v54; // eax
  struct SNI_Conn *v55; // rbx
  unsigned int v56; // eax
  struct SNI_Conn *v57; // rdx
  struct SNI_Conn **v58; // rdi
  int v60[2]; // [rsp+20h] [rbp-E0h]
  __int64 v61; // [rsp+28h] [rbp-D8h]
  __int64 v62; // [rsp+30h] [rbp-D0h]
  __int64 v63; // [rsp+40h] [rbp-C0h]
  struct SNI_Conn *v64; // [rsp+50h] [rbp-B0h] BYREF
  char v65; // [rsp+58h] [rbp-A8h] BYREF
  char v66[7]; // [rsp+59h] [rbp-A7h] BYREF
  struct ProtElem *v67; // [rsp+60h] [rbp-A0h] BYREF
  struct SNI_Provider *v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h]
  struct Sni_Consumer_Info *v70; // [rsp+78h] [rbp-88h]
  DWORD TickCount; // [rsp+80h] [rbp-80h]
  struct SNI_Conn **v72; // [rsp+88h] [rbp-78h]
  __int64 v73; // [rsp+90h] [rbp-70h]
  const char *v74; // [rsp+98h] [rbp-68h]
  const char *v75; // [rsp+A0h] [rbp-60h]
  int v76; // [rsp+A8h] [rbp-58h]
  const char *v77; // [rsp+B0h] [rbp-50h]
  const char *v78; // [rsp+B8h] [rbp-48h]
  int v79; // [rsp+C0h] [rbp-40h]
  const char *v80; // [rsp+C8h] [rbp-38h]
  const char *v81; // [rsp+D0h] [rbp-30h]
  int v82; // [rsp+D8h] [rbp-28h]
  __int128 v83; // [rsp+E0h] [rbp-20h] BYREF

  v73 = -2;
  v72 = a4;
  v6 = a3;
  v69 = a3;
  v8 = a1;
  v70 = a1;
  v74 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v75 = "SNIOpenSync";
  v76 = 3559;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIOpenSync",
      3559,
      L"API|SNIpConsumerInfo: %p{SNI_CONSUMER_INFO*}, szConnect: %p{LPSTR}, pOpenInfo: %p, ppConn: %p{SNI_Conn**}, fSync: "
       "%d{BOOL}, timeout: %d\n",
      a1,
      a2,
      a3,
      a4,
      a5,
      a6);
  v9 = 0;
  v67 = 0;
  v64 = 0;
  v68 = 0;
  TickCount = GetTickCount();
  v10 = -1;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = (unsigned int)(v11 + 1);
    *(_QWORD *)&v83 = (unsigned int)v12;
    v13 = *a2;
    if ( *a2 )
    {
      if ( a2[v12 - 1] )
      {
        ProtElem = 87;
LABEL_40:
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v62) = ProtElem;
          LODWORD(v61) = 0;
          v60[0] = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "SNIOpenSync",
            3579,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            *(_QWORD *)v60,
            v61,
            v62);
        }
        SNISetLastError(10, ProtElem, 50100);
        goto LABEL_136;
      }
      v15 = a2;
      v16 = 0;
      do
      {
        v17 = L" \t";
        v18 = 0;
        while ( 1 )
        {
          if ( !*v17 )
          {
LABEL_16:
            v16 = 0;
            goto LABEL_17;
          }
          if ( *v17 == v13 )
            break;
          v19 = CharNextW(v17);
          v17 = v19;
          if ( v19 )
          {
            v20 = v19 - L" \t";
            if ( (int)v20 > v18 )
            {
              v18 = v20;
              if ( (int)v20 < 3 )
                continue;
            }
          }
          goto LABEL_16;
        }
        v22 = v15;
        if ( v16 )
          v22 = v16;
        v16 = v22;
LABEL_17:
        v15 = CharNextW(v15);
        v13 = *v15;
      }
      while ( *v15 );
      if ( v16 )
      {
        v21 = v16 - a2 + 1;
        if ( v21 >= (unsigned __int64)v83 )
        {
LABEL_38:
          ProtElem = 111;
          goto LABEL_39;
        }
        *v16 = 0;
      }
      else
      {
        v21 = v83;
      }
      v23 = a2;
      v24 = *a2;
      if ( *a2 )
      {
        if ( a2[v21 - 1] )
        {
          ProtElem = 87;
LABEL_39:
          v6 = v69;
          goto LABEL_40;
        }
LABEL_28:
        v25 = L" \t";
        v26 = 0;
        while ( *v25 )
        {
          if ( *v25 == v24 )
          {
            v23 = CharNextW(v23);
            v24 = *v23;
            if ( *v23 )
              goto LABEL_28;
            break;
          }
          v27 = CharNextW(v25);
          v25 = v27;
          if ( v27 )
          {
            v28 = v27 - L" \t";
            if ( (int)v28 > v26 )
            {
              v26 = v28;
              if ( (int)v28 < 3 )
                continue;
            }
          }
          break;
        }
        if ( v23 != a2 )
        {
          v29 = v23 - a2;
          if ( v29 >= v21 )
            goto LABEL_38;
          _mm_lfence();
          v31 = v21 - v29;
          wmemmove_s(a2, v21, v23, v21 - v29);
          a2[v31] = 0;
        }
      }
      v6 = v69;
      v8 = v70;
    }
    v10 = -1;
    v32 = -1;
    do
    {
      if ( aSession[v32 + 1] != a2[v32 + 1] )
        break;
      v32 += 2;
      if ( v32 == 9 )
      {
        v33 = 2;
        goto LABEL_60;
      }
    }
    while ( aSession[v32] == a2[v32] );
    if ( v6 )
      goto LABEL_59;
    ProtElem = ProtElem::MakeProtElem(a2, &v67);
    if ( !ProtElem )
    {
      v33 = *(_DWORD *)v67;
      goto LABEL_60;
    }
    goto LABEL_137;
  }
  if ( !v6 )
  {
    v34 = g_XeSniPkg_enabledBitmap;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      SNIXE_SNI_ERROR_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIOpenSync", 3590, L"ERR|SNIpOpenInfo is NULL\n");
      v34 = g_XeSniPkg_enabledBitmap;
    }
    ProtElem = 87;
    if ( (v34 & 2) != 0 )
    {
      LODWORD(v62) = 87;
      LODWORD(v61) = 0;
      v60[0] = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNIOpenSync",
        3592,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        *(_QWORD *)v60,
        v61,
        v62);
    }
    SNISetLastError(10, 87, 50100);
    goto LABEL_137;
  }
LABEL_59:
  v67 = (struct ProtElem *)v6;
  v33 = *(_DWORD *)v6;
LABEL_60:
  ProtElem = SNI_Conn::InitObject(&v64, 0);
  if ( ProtElem )
    goto LABEL_136;
  *((_BYTE *)v64 + 12804) |= 2u;
  *((_BYTE *)v64 + 12804) ^= (*((_BYTE *)v64 + 12804) ^ (4 * *((_BYTE *)v8 + 92))) & 4;
  v35 = a5;
  *((_BYTE *)v64 + 12804) = *((_BYTE *)v64 + 12804) & 0xFE | (a5 != 0);
  if ( v33 != 2 )
  {
    ProtElem = SNI_Conn::SetServerName(v64, (wchar_t *)v67 + 4, (wchar_t *)v67 + 260);
    if ( ProtElem )
      goto LABEL_136;
    v35 = a5;
  }
  SNISetInfo(v64, 1, v8);
  if ( v33 == 2 )
  {
    *((_DWORD *)v64 + 3188) = *(_DWORD *)(v6 + 12752);
    *((_DWORD *)v64 + 3189) = *(_DWORD *)(v6 + 12756);
    *((_DWORD *)v64 + 3190) = *(_DWORD *)(v6 + 12760);
    *((_DWORD *)v64 + 3191) = *(_DWORD *)(v6 + 12764);
    *(_DWORD *)(*((_QWORD *)v64 + 1601) + 20LL) = *(_DWORD *)(*(_QWORD *)(v6 + 12808) + 20LL);
    *((_DWORD *)v64 + 3200) = *(_DWORD *)(v6 + 12800);
    v83 = *(_OWORD *)(v6 + 28);
    SNISetInfo(v64, 10, &v83);
  }
  else
  {
    IncrementConnBufSize(v64, (struct SNI_PROVIDER_INFO *)((char *)&rgProvInfo + 20 * v33));
    v36 = *((_DWORD *)v64 + 3188);
    v37 = v36 + *((_DWORD *)v64 + 3189);
    if ( v37 < v36 || v37 > 0x183E8 )
    {
      ProtElem = -2147024362;
      goto LABEL_136;
    }
    v38 = 0;
    v39 = qword_1004912A0;
    while ( v37 > *(_DWORD *)v39 )
    {
      ++v38;
      v39 = (__int64 *)((char *)v39 + 4);
      if ( v38 > 7 )
      {
        v38 = 7;
        break;
      }
    }
    *((_DWORD *)v64 + 3200) = v38;
  }
  SNISetInfo(v64, 2, *((_QWORD *)v8 + 1));
  v40 = v64;
  *((_DWORD *)v64 + 3156) = *(_DWORD *)v8;
  *((_QWORD *)v40 + 1579) = *((_QWORD *)v8 + 1);
  *((_QWORD *)v40 + 1580) = *((_QWORD *)v8 + 2);
  *((_QWORD *)v40 + 1581) = *((_QWORD *)v8 + 3);
  *((_QWORD *)v40 + 1585) = *((_QWORD *)v8 + 7);
  *((_QWORD *)v40 + 1582) = *((_QWORD *)v8 + 4);
  *((_QWORD *)v40 + 1583) = *((_QWORD *)v8 + 5);
  *((_QWORD *)v40 + 1584) = *((_QWORD *)v8 + 6);
  *((_BYTE *)v40 + 12717) = *((_BYTE *)v8 + 93);
  *((_BYTE *)v40 + 12718) = *((_BYTE *)v8 + 94);
  *((_BYTE *)v40 + 12719) = *((_BYTE *)v8 + 95);
  *((_DWORD *)v40 + 3180) = *((_DWORD *)v8 + 24);
  *((_DWORD *)v40 + 3181) = *((_DWORD *)v8 + 25);
  *((_DWORD *)v40 + 3182) = *((_DWORD *)v8 + 26);
  *((_DWORD *)v40 + 3183) = *((_DWORD *)v8 + 27);
  *((_DWORD *)v40 + 3178) = *((_DWORD *)v8 + 22);
  *((_QWORD *)v40 + 1588) = *((_QWORD *)v8 + 10);
  if ( g_fSandbox && v33 == 4 )
  {
    ProtElem = 50;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v62) = 50;
      LODWORD(v61) = 8;
      v60[0] = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNIOpenSync",
        3717,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        *(_QWORD *)v60,
        v61,
        v62);
    }
    SNISetLastError(10, 50, 50108);
    goto LABEL_136;
  }
  v41 = v33 - 1;
  if ( v41 )
  {
    v42 = v41 - 1;
    if ( v42 )
    {
      v43 = v42 - 2;
      if ( v43 )
      {
        if ( v43 != 3 )
        {
          v44 = g_XeSniPkg_enabledBitmap;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNIOpenSync",
              3809,
              L"ERR|SNIProvNum is unknown\n");
            v44 = g_XeSniPkg_enabledBitmap;
          }
          ProtElem = 87;
          if ( (v44 & 2) != 0 )
          {
            LODWORD(v62) = 87;
            LODWORD(v61) = 0;
            v60[0] = 10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNIOpenSync",
              3811,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              *(_QWORD *)v60,
              v61,
              v62);
          }
          SNISetLastError(10, 87, 50100);
          goto LABEL_136;
        }
        v45 = a6;
        if ( a6 != -1 )
        {
          v46 = a6 + TickCount - GetTickCount();
          v45 = -2;
          if ( v46 != -1 )
            v45 = v46;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            v60[0] = v45;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNIOpenSync",
              3750,
              L"SNItimeout: %d\n",
              *(_QWORD *)v60);
          }
        }
        ProtElem = Tcp::Open(v64, (const WCHAR *)v67, &v68, v45);
        if ( !ProtElem )
        {
          *((_DWORD *)v64 + 3191) = 7;
          goto LABEL_125;
        }
LABEL_136:
        if ( v6 )
        {
LABEL_139:
          if ( v64 )
          {
            v66[0] = 0;
            SNI_Conn::ReleaseUnderForceCloseLock(v64, 0, v66);
          }
          *v72 = 0;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            v60[0] = ProtElem;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNIOpenSync",
              3858,
              L"RET|SNI%d{WINERR}\n",
              *(_QWORD *)v60);
          }
          v9 = ProtElem;
          goto LABEL_144;
        }
LABEL_137:
        if ( v67 )
          operator delete(v67, 0x810u);
        goto LABEL_139;
      }
      v65 = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v64, 0, &v65);
      v64 = 0;
      v47 = v67;
      v77 = "sql\\common\\dk\\sni\\src\\sm.cpp";
      v78 = "Sm::OpenWithFallback";
      v79 = 452;
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      {
        LODWORD(v63) = v35;
        v48 = v70;
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\sm.cpp",
          "Sm::OpenWithFallback",
          452,
          L"API|SNIpConsumerInfo: %p{SNI_CONSUMER_INFO*}, ppConn: %p{SNI_Conn**}, pProtElem: %p{ProtElem*}, ppProv: %p{SNI"
           "_Provider**}, fSync: %d{BOOL}\n",
          v70,
          &v64,
          v67,
          &v68,
          v63);
      }
      else
      {
        v48 = v70;
      }
      v64 = 0;
      v49 = (char *)v47 + 1032;
      do
        ++v10;
      while ( *(_WORD *)&v49[2 * v10] );
      v50 = (const WCHAR *)((char *)v47 + 1032);
      v51 = 0;
      if ( (int)v10 > 0 )
      {
        do
        {
          if ( !*v50 )
            break;
          if ( *v50 == 92 )
            break;
          v52 = CharNextW(v50);
          v50 = v52;
          if ( !v52 )
            break;
          v53 = ((char *)v52 - v49) >> 1;
          if ( (int)v53 <= v51 )
            break;
          v51 = v53;
        }
        while ( (int)v53 < (int)v10 );
      }
      v54 = Sm::OpenNpBasedYukon(v48, &v64, v47, &v68, a5);
      ProtElem = v54;
      if ( v54 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          v60[0] = v54;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sm.cpp",
            "Sm::OpenWithFallback",
            515,
            L"RET|SNI%d{WINERR}\n",
            *(_QWORD *)v60);
        }
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::OpenWithFallback", 452, v30);
        goto LABEL_136;
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v62) = 0;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sm.cpp",
          "Sm::OpenWithFallback",
          510,
          L"RET|SNI*ppConn: %p{SNI_Conn*}, *ppProv: %p{SNI_Provider*}, %d{WINERR}\n",
          v64,
          v68,
          v62);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::OpenWithFallback", 452, v30);
      *((_DWORD *)v64 + 3191) = 4;
    }
    else
    {
      v55 = v64;
      v80 = "sql\\common\\dk\\sni\\src\\smux.cpp";
      v81 = "Smux::Open";
      v82 = 3456;
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::Open",
          3456,
          L"API|SNIpConn: %p{SNI_Conn*}, pParent: %p{SNI_Conn*}, ppProv: %p{SNI_Provider**}\n",
          v64,
          v6,
          &v68);
      *((_BYTE *)v55 + 12804) ^= (*((_BYTE *)v55 + 12804) ^ *(_BYTE *)(v6 + 12804)) & 1;
      v56 = Smux::OpenSession(*(Smux **)(v6 + 12616), v55, &v68);
      ProtElem = v56;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        v60[0] = v56;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::Open",
          3463,
          L"RET|SNI%d{WINERR}\n",
          *(_QWORD *)v60);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Smux::Open", 3456, v30);
      if ( ProtElem )
        goto LABEL_136;
    }
  }
  else
  {
    ProtElem = Np::Open(v64, v67, &v68);
    if ( ProtElem )
      goto LABEL_136;
    *((_DWORD *)v64 + 3191) = 1;
  }
LABEL_125:
  *((_QWORD *)v64 + 1577) = v68;
  v57 = v64;
  if ( (*((_BYTE *)v64 + 12804) & 1) == 0 && *((_QWORD *)v68 + 2) != -1 && !*((_QWORD *)v64 + 1624) )
  {
    ProtElem = SNIRegisterWithIOCQ();
    if ( ProtElem )
      goto LABEL_136;
    v57 = v64;
  }
  v58 = v72;
  *v72 = v57;
  if ( !v6 && v67 )
    operator delete(v67, 0x810u);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIOpenSync", 3840, L"RET|SNIConn: %p\n", *v58);
LABEL_144:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIOpenSync", 3559, v30);
  return v9;
}

```

## disassembly

```asm
0x100425000  push    rbp
0x100425002  push    rbx
0x100425003  push    rsi
0x100425004  push    rdi
0x100425005  push    r12
0x100425007  push    r13
0x100425009  push    r14
0x10042500b  push    r15
0x10042500d  lea     rbp, [rsp-8]
0x100425012  sub     rsp, 108h
0x100425019  mov     [rbp+40h+var_B0], 0FFFFFFFFFFFFFFFEh
0x100425021  mov     rax, cs:__security_cookie
0x100425028  xor     rax, rsp
0x10042502b  mov     [rbp+40h+var_50], rax
0x10042502f  mov     [rbp+40h+var_B8], r9
0x100425033  mov     r14, r8
0x100425036  mov     [rsp+140h+var_D0], r8
0x10042503b  mov     r15, rdx
0x10042503e  mov     rsi, rcx
0x100425041  mov     [rsp+140h+var_C8], rcx
0x100425046  lea     rdi, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x10042504d  mov     [rbp+40h+var_A8], rdi
0x100425051  lea     rbx, aSniopensync; "SNIOpenSync"
0x100425058  mov     [rbp+40h+var_A0], rbx
0x10042505c  mov     [rbp+40h+var_98], 0DE7h
0x100425063  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042506a  jz      short loc_1004250A6
0x10042506c  mov     eax, [rbp+40h+arg_28]
0x10042506f  mov     [rsp+140h+var_F8], eax
0x100425073  mov     eax, [rbp+40h+arg_20]
0x100425076  mov     dword ptr [rsp+140h+var_100], eax
0x10042507a  mov     [rsp+140h+var_108], r9
0x10042507f  mov     [rsp+140h+var_110], r8
0x100425084  mov     [rsp+140h+var_118], rdx
0x100425089  mov     qword ptr [rsp+140h+var_120], rcx
0x10042508e  lea     r9, aApiSnipconsume_0; "API|SNIpConsumerInfo: %p{SNI_CONSUMER_I"...
0x100425095  mov     r8d, 0DE7h; int
0x10042509b  mov     rdx, rbx; char *
0x10042509e  mov     rcx, rdi; char *
0x1004250a1  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004250a6  xor     r12d, r12d
0x1004250a9  mov     [rsp+140h+var_E0], r12
0x1004250ae  mov     [rsp+140h+var_F0], r12
0x1004250b3  mov     [rsp+140h+var_D8], r12
0x1004250b8  call    cs:__imp_GetTickCount
0x1004250be  mov     [rbp+40h+var_C0], eax
0x1004250c1  lea     r13, [r12-1]
0x1004250c6  test    r15, r15
0x1004250c9  jz      loc_100425318
0x1004250cf  mov     rax, r13
0x1004250d2  inc     rax
0x1004250d5  cmp     [r15+rax*2], r12w
0x1004250da  jnz     short loc_1004250D2
0x1004250dc  inc     eax
0x1004250de  mov     r13d, eax
0x1004250e1  mov     qword ptr [rbp+40h+var_60], r13
0x1004250e5  movzx   edi, word ptr [r15]
0x1004250e9  test    di, di
0x1004250ec  jz      loc_1004252A4
0x1004250f2  cmp     r12w, [r15+rax*2-2]
0x1004250f8  jz      short loc_100425104
0x1004250fa  mov     ebx, 57h ; 'W'
0x1004250ff  jmp     loc_100425229
0x100425104  mov     r14, r15
0x100425107  mov     rsi, r12
0x10042510a  lea     r13, sz; " \t"
0x100425111  mov     rcx, r13; lpsz
0x100425114  mov     ebx, r12d
0x100425117  movzx   eax, word ptr [rcx]
0x10042511a  test    ax, ax
0x10042511d  jz      short loc_100425143
0x10042511f  cmp     ax, di
0x100425122  jz      short loc_10042517E
0x100425124  call    cs:__imp_CharNextW
0x10042512a  mov     rcx, rax
0x10042512d  test    rax, rax
0x100425130  jz      short loc_100425143
0x100425132  sub     rax, r13
0x100425135  sar     rax, 1
0x100425138  cmp     eax, ebx
0x10042513a  jle     short loc_100425143
0x10042513c  mov     ebx, eax
0x10042513e  cmp     eax, 3
0x100425141  jl      short loc_100425117
0x100425143  mov     rsi, r12
0x100425146  mov     rcx, r14; lpsz
0x100425149  call    cs:__imp_CharNextW
0x10042514f  mov     r14, rax
0x100425152  movzx   edi, word ptr [rax]
0x100425155  test    di, di
0x100425158  jnz     short loc_100425111
0x10042515a  test    rsi, rsi
0x10042515d  mov     r13, qword ptr [rbp+40h+var_60]
0x100425161  jz      short loc_10042518D
0x100425163  mov     r14, rsi
0x100425166  sub     r14, r15
0x100425169  sar     r14, 1
0x10042516c  inc     r14
0x10042516f  cmp     r14, r13
0x100425172  jnb     loc_10042521F
0x100425178  mov     [rsi], r12w
0x10042517c  jmp     short loc_100425190
0x10042517e  mov     rax, r14
0x100425181  test    rsi, rsi
0x100425184  cmovnz  rax, rsi
0x100425188  mov     rsi, rax
0x10042518b  jmp     short loc_100425146
0x10042518d  mov     r14, r13
0x100425190  mov     rsi, r15
0x100425193  movzx   edi, word ptr [r15]
0x100425197  test    di, di
0x10042519a  jz      loc_10042529A
0x1004251a0  cmp     r12w, [r15+r14*2-2]
0x1004251a6  jz      short loc_1004251AF
0x1004251a8  mov     ebx, 57h ; 'W'
0x1004251ad  jmp     short loc_100425224
0x1004251af  lea     r13, sz; " \t"
0x1004251b6  nop     word ptr [rax+rax+00000000h]
0x1004251c0  mov     rcx, r13; lpsz
0x1004251c3  mov     ebx, r12d
0x1004251c6  movzx   eax, word ptr [rcx]
0x1004251c9  test    ax, ax
0x1004251cc  jz      short loc_100425208
0x1004251ce  cmp     ax, di
0x1004251d1  jz      short loc_1004251F4
0x1004251d3  call    cs:__imp_CharNextW
0x1004251d9  mov     rcx, rax
0x1004251dc  test    rax, rax
0x1004251df  jz      short loc_100425208
0x1004251e1  sub     rax, r13
0x1004251e4  sar     rax, 1
0x1004251e7  cmp     eax, ebx
0x1004251e9  jle     short loc_100425208
0x1004251eb  mov     ebx, eax
0x1004251ed  cmp     eax, 3
0x1004251f0  jge     short loc_100425208
0x1004251f2  jmp     short loc_1004251C6
0x1004251f4  mov     rcx, rsi; lpsz
0x1004251f7  call    cs:__imp_CharNextW
0x1004251fd  mov     rsi, rax
0x100425200  movzx   edi, word ptr [rax]
0x100425203  test    di, di
0x100425206  jnz     short loc_1004251C0
0x100425208  cmp     rsi, r15
0x10042520b  jz      loc_10042529A
0x100425211  mov     rax, rsi
0x100425214  sub     rax, r15
0x100425217  sar     rax, 1
0x10042521a  cmp     rax, r14
0x10042521d  jb      short loc_10042527A
0x10042521f  mov     ebx, 6Fh ; 'o'
0x100425224  mov     r14, [rsp+140h+var_D0]
0x100425229  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100425230  jz      short loc_100425263
0x100425232  mov     dword ptr [rsp+140h+var_110], ebx
0x100425236  mov     dword ptr [rsp+140h+var_118], r12d
0x10042523b  mov     [rsp+140h+var_120], 0Ah
0x100425243  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042524a  mov     r8d, 0DFBh; int
0x100425250  lea     rdx, aSniopensync; "SNIOpenSync"
0x100425257  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x10042525e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100425263  mov     r8d, 0C3B4h
0x100425269  mov     edx, ebx
0x10042526b  mov     ecx, 0Ah
0x100425270  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100425275  jmp     loc_100425AF6
0x10042527a  lfence
0x10042527d  mov     rbx, r14
0x100425280  sub     rbx, rax
0x100425283  mov     r9, rbx; N
0x100425286  mov     r8, rsi; S2
0x100425289  mov     rdx, r14; N1
0x10042528c  mov     rcx, r15; S1
0x10042528f  call    cs:__imp_wmemmove_s
0x100425295  mov     [r15+rbx*2], r12w
0x10042529a  mov     r14, [rsp+140h+var_D0]
0x10042529f  mov     rsi, [rsp+140h+var_C8]
0x1004252a4  lea     rdx, aSession; "session:"
0x1004252ab  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1004252b2  mov     rcx, r13
0x1004252b5  nop     word ptr [rax+rax+00000000h]
0x1004252c0  movzx   eax, word ptr [rdx+rcx*2+2]
0x1004252c5  cmp     ax, [r15+rcx*2+2]
0x1004252cb  jnz     short loc_1004252E2
0x1004252cd  add     rcx, 2
0x1004252d1  cmp     rcx, 9
0x1004252d5  jz      short loc_10042530E
0x1004252d7  movzx   eax, word ptr [rdx+rcx*2]
0x1004252db  cmp     ax, [r15+rcx*2]
0x1004252e0  jz      short loc_1004252C0
0x1004252e2  test    r14, r14
0x1004252e5  jnz     loc_100425392
0x1004252eb  lea     rdx, [rsp+140h+var_E0]; struct ProtElem **
0x1004252f0  mov     rcx, r15; wchar_t *
0x1004252f3  call    ?MakeProtElem@ProtElem@@SAKPEA_WPEAPEAV1@@Z; ProtElem::MakeProtElem(wchar_t *,ProtElem * *)
0x1004252f8  mov     ebx, eax
0x1004252fa  test    eax, eax
0x1004252fc  jnz     loc_100425AFB
0x100425302  mov     rax, [rsp+140h+var_E0]
0x100425307  mov     edi, [rax]
0x100425309  jmp     loc_10042539A
0x10042530e  mov     edi, 2
0x100425313  jmp     loc_10042539A
0x100425318  test    r14, r14
0x10042531b  jnz     short loc_100425392
0x10042531d  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100425323  test    al, 2
0x100425325  jz      short loc_100425345
0x100425327  lea     r9, aErrSnipopeninf; "ERR|SNIpOpenInfo is NULL\n"
0x10042532e  mov     r8d, 0E06h; int
0x100425334  mov     rdx, rbx; char *
0x100425337  mov     rcx, rdi; char *
0x10042533a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042533f  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100425345  mov     ebx, 57h ; 'W'
0x10042534a  test    al, 2
0x10042534c  jz      short loc_10042537B
0x10042534e  mov     dword ptr [rsp+140h+var_110], ebx
0x100425352  mov     dword ptr [rsp+140h+var_118], r12d
0x100425357  mov     [rsp+140h+var_120], 0Ah
0x10042535f  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100425366  mov     r8d, 0E08h; int
0x10042536c  lea     rdx, aSniopensync; "SNIOpenSync"
0x100425373  mov     rcx, rdi; char *
0x100425376  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042537b  mov     edx, ebx
0x10042537d  mov     ecx, 0Ah
0x100425382  mov     r8d, 0C3B4h
0x100425388  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042538d  jmp     loc_100425AFB
0x100425392  mov     [rsp+140h+var_E0], r14
0x100425397  mov     edi, [r14]
0x10042539a  xor     edx, edx; int
0x10042539c  lea     rcx, [rsp+140h+var_F0]; struct SNI_Conn **
0x1004253a1  call    ?InitObject@SNI_Conn@@SAKPEAPEAV1@H@Z; SNI_Conn::InitObject(SNI_Conn * *,int)
0x1004253a6  mov     ebx, eax
0x1004253a8  test    eax, eax
0x1004253aa  jnz     loc_100425AF6
0x1004253b0  mov     rax, [rsp+140h+var_F0]
0x1004253b5  or      byte ptr [rax+3204h], 2
0x1004253bc  mov     rcx, [rsp+140h+var_F0]
0x1004253c1  movzx   eax, byte ptr [rsi+5Ch]
0x1004253c5  shl     al, 2
0x1004253c8  xor     al, [rcx+3204h]
0x1004253ce  and     al, 4
0x1004253d0  xor     [rcx+3204h], al
0x1004253d6  mov     rdx, [rsp+140h+var_F0]
0x1004253db  mov     ebx, [rbp+40h+arg_20]
0x1004253de  test    ebx, ebx
0x1004253e0  setnz   cl
0x1004253e3  movzx   eax, byte ptr [rdx+3204h]
0x1004253ea  and     al, 0FEh
0x1004253ec  or      cl, al
0x1004253ee  mov     [rdx+3204h], cl
0x1004253f4  cmp     edi, 2
0x1004253f7  jz      short loc_100425420
0x1004253f9  mov     rdx, [rsp+140h+var_E0]
0x1004253fe  lea     r8, [rdx+208h]; wchar_t *
0x100425405  add     rdx, 8; wchar_t *
0x100425409  mov     rcx, [rsp+140h+var_F0]; this
0x10042540e  call    ?SetServerName@SNI_Conn@@QEAAKPEA_W0@Z; SNI_Conn::SetServerName(wchar_t *,wchar_t *)
0x100425413  mov     ebx, eax
0x100425415  test    eax, eax
0x100425417  jnz     loc_100425AF6
0x10042541d  mov     ebx, [rbp+40h+arg_20]
0x100425420  mov     r8, rsi
0x100425423  mov     edx, 1
0x100425428  mov     rcx, [rsp+140h+var_F0]
0x10042542d  call    SNISetInfo
0x100425432  cmp     edi, 2
0x100425435  jnz     loc_1004254CA
0x10042543b  mov     ecx, [r14+31D0h]
0x100425442  mov     rax, [rsp+140h+var_F0]
0x100425447  mov     [rax+31D0h], ecx
0x10042544d  mov     ecx, [r14+31D4h]
0x100425454  mov     rax, [rsp+140h+var_F0]
0x100425459  mov     [rax+31D4h], ecx
0x10042545f  mov     ecx, [r14+31D8h]
0x100425466  mov     rax, [rsp+140h+var_F0]
0x10042546b  mov     [rax+31D8h], ecx
0x100425471  mov     ecx, [r14+31DCh]
0x100425478  mov     rax, [rsp+140h+var_F0]
0x10042547d  mov     [rax+31DCh], ecx
0x100425483  mov     rdx, [r14+3208h]
0x10042548a  mov     rax, [rsp+140h+var_F0]
0x10042548f  mov     rcx, [rax+3208h]
0x100425496  mov     eax, [rdx+14h]
0x100425499  mov     [rcx+14h], eax
0x10042549c  mov     ecx, [r14+3200h]
0x1004254a3  mov     rax, [rsp+140h+var_F0]
0x1004254a8  mov     [rax+3200h], ecx
0x1004254ae  movups  xmm0, xmmword ptr [r14+1Ch]
0x1004254b3  movups  [rbp+40h+var_60], xmm0
0x1004254b7  lea     r8, [rbp+40h+var_60]
0x1004254bb  lea     edx, [rdi+8]
0x1004254be  mov     rcx, [rsp+140h+var_F0]
0x1004254c3  call    SNISetInfo
0x1004254c8  jmp     short loc_100425536
0x1004254ca  movsxd  rax, edi
  ... truncated ...
```
