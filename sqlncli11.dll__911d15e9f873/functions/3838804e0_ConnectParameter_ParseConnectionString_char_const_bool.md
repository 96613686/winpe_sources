# ConnectParameter::ParseConnectionString(char const *,bool)

- ea: `0x3838804e0`
- end: `0x383880803`
- name: `?ParseConnectionString@ConnectParameter@@QEAAKPEBD_N@Z`
- size: `803`
- prototype: `unsigned int(ConnectParameter *__hidden this, const char *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x383883ac0`
- `0x383ab05e0`

## callees

- `0x383846430`
- `0x38387ca10`
- `0x38387d850`
- `0x3838804e0`
- `0x383881430`
- `0x383884870`
- `0x38388f760`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `MSVCR100!strchr` at `0x3838805f5`
- `MSVCR100!strchr` at `0x383880737`
- `MSVCR100!strchr` at `0x3838f8c5c`
- `MSVCR100!strchr` at `0x3838805f5`
- `MSVCR100!strchr` at `0x383880737`
- `MSVCR100!strchr` at `0x3838f8c5c`
- `KERNEL32!LCMapStringA` at `0x3838805b2`
- `KERNEL32!LCMapStringA` at `0x3838805b2`
- `KERNEL32!CompareStringA` at `0x383880720`
- `KERNEL32!CompareStringA` at `0x3838f8a49`
- `KERNEL32!CompareStringA` at `0x3838f8a86`
- `KERNEL32!CompareStringA` at `0x3838f8aee`
- `KERNEL32!CompareStringA` at `0x383880720`
- `KERNEL32!CompareStringA` at `0x3838f8a49`
- `KERNEL32!CompareStringA` at `0x3838f8a86`
- `KERNEL32!CompareStringA` at `0x3838f8aee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectParameter::ParseConnectionString(ConnectParameter *this, const char *a2, char a3)
{
  __int64 v6; // r13
  int v7; // r14d
  int v8; // r12d
  char v9; // al
  __int64 v10; // rdi
  CHAR *v11; // rax
  __int64 v12; // r15
  unsigned int v13; // eax
  char *v14; // rax
  char *v15; // r14
  __int64 v16; // rbp
  char *v17; // rsi
  __int64 v18; // rdx
  char *v19; // rbx
  _BYTE *v20; // rcx
  char v21; // al
  __int64 v22; // rdx
  char *v23; // r14
  __int64 v24; // rdx
  char *v25; // rax
  __int64 v26; // rdx
  _BYTE *v27; // rax
  ConnectParameter *v28; // r12
  unsigned __int64 v29; // rax
  __int64 v30; // rdx
  _BYTE *v31; // rcx
  char v32; // al
  char *v33; // rcx
  char v34; // al
  char *v35; // rcx
  CHAR v36; // al
  _BYTE *v37; // rbx
  __int64 v38; // rdx
  _BYTE *v39; // rcx
  char v40; // al
  unsigned int v41; // edi
  unsigned int v43; // eax
  char *v44; // rdi
  const char *v45; // rbx
  char v46; // al
  unsigned __int64 v47; // rax
  __int64 v48; // rdx
  _BYTE *v49; // rcx
  char v50; // al
  char *v51; // rdi
  __int64 v52; // rdx
  _BYTE *v53; // rax
  _BYTE *v54; // rbx
  _BYTE *v55; // rdx
  char v56; // cl
  __int64 v57; // rdx
  _BYTE *v58; // rcx
  char v59; // al
  bool v60; // al
  __int64 v61; // rdx
  ConnectParameter *v62; // rcx
  char v63; // al
  int v64; // esi
  __int64 v65; // rdi
  char v66; // al
  const CHAR *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  const CHAR *v70; // rdi
  __int64 v71; // r9
  __int64 v72; // rdx
  __int64 v73; // rax
  _BYTE *v74; // rsi
  const CHAR *v75; // r8
  __int64 v76; // r9
  __int64 v77; // rax
  _BYTE *v78; // rcx
  int v79; // edi
  __int64 v80; // rdx
  char v81; // al
  char *v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // rdx
  _BYTE *v85; // rcx
  char v86; // al
  char *v87; // rax
  __int64 v88; // rdx
  unsigned __int64 v89; // rax
  char *v90; // rcx
  char v91; // al
  __int64 v92; // rdx
  _BYTE *v93; // rax
  __int64 v94; // rdx
  _BYTE *v95; // rcx
  signed __int64 v96; // rbx
  char v97; // al
  char *v98; // rdi
  unsigned __int64 v99; // rax
  char *v100; // rcx
  char v101; // al
  __int64 v102; // rdx
  char *v103; // rcx
  char v104; // al
  bool v105; // zf
  __int64 v106; // rdx
  _BYTE *v107; // rcx
  signed __int64 v108; // rdi
  char v109; // al
  signed __int64 v110; // r14
  char v111; // al
  char v112; // al
  unsigned int v113; // eax
  int v114; // ebp
  const char *v115; // rdx
  __int64 v116; // rcx
  char v117; // al
  unsigned int v118; // eax
  unsigned int v119; // eax
  unsigned int v120; // eax
  int lpDestStr; // [rsp+20h] [rbp-98h]
  int lpDestStra; // [rsp+20h] [rbp-98h]
  int cchDest; // [rsp+28h] [rbp-90h]
  int cchDesta; // [rsp+28h] [rbp-90h]
  char *Str; // [rsp+60h] [rbp-58h]
  __int64 v126; // [rsp+68h] [rbp-50h] BYREF
  char *v127; // [rsp+70h] [rbp-48h]
  __int64 v128; // [rsp+78h] [rbp-40h]
  unsigned int v131; // [rsp+D8h] [rbp+20h]

  v128 = -2;
  v6 = -1;
  v126 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_176[0] )
    bidScopeEnterA(&v126, `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_176[0], a2);
  v7 = 0;
  v8 = 0;
  *((_BYTE *)this + 1549) = a3;
  if ( !*((_BYTE *)this + 1547) || (v9 = 1, a3) )
    v9 = 0;
  *((_BYTE *)this + 1547) = v9;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = (CHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)gpmo + 112LL))(
                  gpmo,
                  (unsigned int)(v10 + 1));
  Str = v11;
  if ( v11 )
  {
    v131 = 87;
    v12 = 256;
    v13 = LCMapStringA(0x800u, 0x100u, a2, -1, v11, v10 + 1);
    if ( !v13 || v13 > (int)v10 + 1 || (Str[(unsigned int)v10] = 0, (unsigned int)StrTrimBoth_Sys(Str)) )
    {
      v28 = this;
      goto LABEL_63;
    }
    v127 = Str;
    v14 = strchr(Str, 58);
    v15 = v14;
    v16 = 11;
    if ( v14 )
    {
      *v14 = 0;
      v17 = Str;
      if ( v14 - Str > 10 )
        goto LABEL_262;
      v18 = 11;
      v19 = (char *)this + 768;
      v20 = (char *)this + 768;
      while ( v18 != -2147483635 )
      {
        v21 = v20[Str - ((char *)this + 768)];
        if ( !v21 )
          break;
        *v20++ = v21;
        if ( !--v18 )
        {
          --v20;
          break;
        }
      }
      *v20 = 0;
      v22 = -1;
      do
        ++v22;
      while ( v19[v22] );
      if ( (unsigned int)StrTrimBoth_Sys(v19) )
      {
LABEL_262:
        v28 = this;
        v7 = 0;
        goto LABEL_64;
      }
      if ( v15 != Str
        && (!strcmp("tcp", (const char *)this + 768)
         || !strcmp("np", (const char *)this + 768)
         || !strcmp("lpc", (const char *)this + 768)
         || !strcmp("admin", (const char *)this + 768)) )
      {
        v23 = v15 + 1;
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        if ( (unsigned int)StrTrimBoth_Sys(v23) )
          goto LABEL_263;
      }
      else
      {
        *v15 = 58;
        *v19 = 0;
        v23 = v127;
      }
    }
    else
    {
      v23 = v127;
    }
    if ( CompareStringA(0x800u, 0, v23, 2, "\\\\", 2) == 2 )
    {
      v28 = this;
      v44 = (char *)this + 768;
      if ( *((_BYTE *)this + 768) )
      {
        if ( strcmp("np", v44) )
          goto LABEL_264;
      }
      else
      {
        v45 = (const char *)("np" - v44);
        while ( v16 != -2147483635 )
        {
          v46 = v45[(_QWORD)v44];
          if ( !v46 )
            break;
          *v44++ = v46;
          if ( !--v16 )
          {
            --v44;
            break;
          }
        }
        *v44 = 0;
      }
      v47 = -1;
      do
        ++v47;
      while ( v23[v47] );
      if ( v47 <= 0xFF )
      {
        v48 = 256;
        v49 = (char *)this + 779;
        while ( v48 != -2147483390 )
        {
          v50 = v49[v23 - ((char *)this + 779)];
          if ( !v50 )
            break;
          *v49++ = v50;
          if ( !--v48 )
          {
            --v49;
            break;
          }
        }
        *v49 = 0;
        v51 = v23 + 2;
        v52 = -1;
        do
          ++v52;
        while ( v51[v52] );
        v53 = (_BYTE *)StrChrA_SYS(v23 + 2);
        v54 = v53;
        if ( v53 )
        {
          *v53 = 0;
          v55 = v23 + 2;
          v56 = *v51;
          if ( *v51 )
          {
            while ( v56 == 32 || v56 == 9 )
            {
              v56 = *++v55;
              if ( !*v55 )
                goto LABEL_264;
            }
          }
          if ( *v55 )
          {
            v57 = 256;
            v58 = (char *)this + 256;
            while ( v57 != -2147483390 )
            {
              v59 = v58[v51 - ((char *)this + 256)];
              if ( !v59 )
                break;
              *v58++ = v59;
              if ( !--v57 )
              {
                --v58;
                break;
              }
            }
            *v58 = 0;
            v60 = IsLocalHost(v23 + 2);
            v61 = 256;
            v62 = this;
            if ( v60 )
            {
              while ( v61 != -2147483390 )
              {
                v63 = *((_BYTE *)v62 + gszComputerName - (CHAR *)this);
                if ( !v63 )
                  break;
                *(_BYTE *)v62 = v63;
                v62 = (ConnectParameter *)((char *)v62 + 1);
                if ( !--v61 )
                {
                  v62 = (ConnectParameter *)((char *)v62 - 1);
                  break;
                }
              }
              *(_BYTE *)v62 = 0;
              v7 = 0;
            }
            else
            {
              v7 = 0;
              v64 = 0;
              v65 = v51 - (char *)this;
              while ( v61 != -2147483390 )
              {
                v66 = *((_BYTE *)v62 + v65);
                if ( !v66 )
                  break;
                *(_BYTE *)v62 = v66;
                v62 = (ConnectParameter *)((char *)v62 + 1);
                if ( !--v61 )
                {
                  v62 = (ConnectParameter *)((char *)v62 - 1);
                  v64 = -2147024774;
                  break;
                }
              }
              *(_BYTE *)v62 = 0;
              if ( v64 < 0 )
                goto LABEL_63;
            }
            v67 = v54 + 1;
            v68 = -1;
            do
              ++v68;
            while ( v67[v68] );
            v69 = StrChrA_SYS(v67);
            if ( v69 )
            {
              v70 = (const CHAR *)(v69 + 1);
              v71 = -1;
              do
                ++v71;
              while ( v70[v71] );
              if ( CompareStringA(0x800u, 0, (PCNZCH)(v69 + 1), v71, "sql\\query", 9) == 2 )
              {
                *((_BYTE *)this + 512) = 0;
              }
              else
              {
                if ( CompareStringA(0x800u, 0, v70, 6, "mssql$", 6) != 2 )
                  goto LABEL_154;
                v72 = -1;
                do
                  ++v72;
                while ( v70[v72] );
                v73 = StrChrA_SYS(v70);
                v74 = (_BYTE *)v73;
                if ( !v73 )
                  goto LABEL_63;
                v75 = (const CHAR *)(v73 + 1);
                v76 = -1;
                do
                  ++v76;
                while ( v75[v76] );
                if ( CompareStringA(0x800u, 0, v75, v76, "sql\\query", 9) == 2 )
                {
                  do
                    ++v6;
                  while ( v70[v6] );
                  v77 = StrChrA_SYS(v70);
                  *v74 = 0;
                  v78 = (char *)this + 512;
                  v79 = 0;
                  v80 = v77 + 1 - ((_QWORD)this + 512);
                  while ( v12 != -2147483390 )
                  {
                    v81 = v78[v80];
                    if ( !v81 )
                      break;
                    *v78++ = v81;
                    if ( !--v12 )
                    {
                      --v78;
                      v79 = -2147024774;
                      break;
                    }
                  }
                  *v78 = 0;
                  if ( v79 < 0 )
                    goto LABEL_63;
                }
                else
                {
LABEL_154:
                  if ( (int)StringCchPrintf_lA((char *)this + 512, 0x100u, "pipe%s", 0, v70) < 0 )
                    goto LABEL_63;
                  *((_BYTE *)this + 1548) = 0;
                }
              }
              *((_BYTE *)this + 1547) = 0;
              v131 = 0;
            }
LABEL_63:
            v17 = Str;
LABEL_64:
            ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v17);
            v41 = v131;
            if ( v131 )
            {
              if ( !v7 )
              {
                if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`225'::_bidPtrSA_030_615[0] )
                {
                  v120 = SniErrorIdFromStringId(0xC3CDu);
                  bidTraceA(
                    `ConnectParameter::ParseConnectionString'::`225'::_bidSrcFileA[0],
                    629760,
                    `ConnectParameter::ParseConnectionString'::`225'::_bidPtrSA_030_615[0],
                    9,
                    v120,
                    v131);
                }
                SNISetLastError(9, v131, 50125);
              }
            }
            else if ( (bidGblFlags & 0x20002) == 0x20002
                   && `ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_637[0] )
            {
              bidTraceA(
                `ConnectParameter::ParseConnectionString'::`234'::_bidSrcFileA[0],
                652288,
                `ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_637[0],
                (char *)v28 + 768,
                (_DWORD)v28,
                (_DWORD)v28 + 512);
              v41 = 0;
            }
            if ( (bidGblFlags & 0x20002) == 0x20002
              && `ConnectParameter::ParseConnectionString'::`241'::_bidPtrSA_030_640[0] )
            {
              bidTraceA(
                `ConnectParameter::ParseConnectionString'::`241'::_bidSrcFileA[0],
                655360,
                `ConnectParameter::ParseConnectionString'::`241'::_bidPtrSA_030_640[0],
                v41,
                lpDestStra,
                cchDesta);
            }
            if ( v126 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
              off_383B15058();
            return v41;
          }
        }
      }
LABEL_264:
      v7 = 0;
      goto LABEL_63;
    }
    v25 = strchr(v23, 44);
    if ( v25 )
    {
      *v25 = 0;
      v82 = v25 + 1;
      v83 = -1;
      do
        ++v83;
      while ( v82[v83] );
      v28 = this;
      if ( (unsigned int)StrTrimBoth_Sys(v25 + 1) )
        goto LABEL_264;
      if ( !*((_BYTE *)this + 768) )
      {
        v84 = 11;
        v85 = (char *)this + 768;
        while ( v84 != -2147483635 )
        {
          v86 = v85["tcp" - ((const char *)this + 768)];
          if ( !v86 )
            break;
          *v85++ = v86;
          if ( !--v84 )
          {
            --v85;
            break;
          }
        }
        *v85 = 0;
      }
      if ( strcmp("tcp", (const char *)this + 768) )
        goto LABEL_264;
      if ( !strcmp("tcp", (const char *)this + 768) )
      {
        v87 = strchr(v82, 44);
        if ( v87 )
        {
          *v87 = 0;
          v88 = -1;
          do
            ++v88;
          while ( v82[v88] );
          if ( (unsigned int)StrTrimBoth_Sys(v82) )
            goto LABEL_264;
        }
      }
      if ( !*v82 )
        goto LABEL_264;
      if ( *v82 == 92 )
        goto LABEL_264;
      v89 = -1;
      do
        ++v89;
      while ( v82[v89] );
      if ( v89 > 0xFF )
        goto LABEL_264;
      v90 = v23;
      v91 = *v23;
      if ( *v23 )
      {
        while ( v91 == 32 || v91 == 9 )
        {
          v91 = *++v90;
          if ( !*v90 )
            goto LABEL_264;
        }
      }
      if ( !*v90 )
        goto LABEL_264;
      v92 = -1;
      do
        ++v92;
      while ( v82[v92] );
      v93 = (_BYTE *)StrChrA_SYS(v82);
      if ( v93 )
        *v93 = 0;
      v94 = 256;
      v95 = (char *)this + 779;
      v96 = v82 - ((char *)this + 779);
      while ( v94 != -2147483390 )
      {
        v97 = v95[v96];
        if ( !v97 )
          break;
        *v95++ = v97;
        if ( !--v94 )
        {
          --v95;
          break;
        }
      }
      *v95 = 0;
      v8 = 1;
      *((_BYTE *)this + 1547) = 0;
    }
    v26 = -1;
    do
      ++v26;
    while ( v23[v26] );
    v27 = (_BYTE *)StrChrA_SYS(v23);
    if ( !v27 )
      goto LABEL_30;
    *v27 = 0;
    v98 = v27 + 1;
    v99 = -1;
    do
      ++v99;
    while ( v98[v99] );
    if ( v99 <= 0xFF )
    {
      v100 = v23;
      v101 = *v23;
      if ( *v23 )
      {
        while ( v101 == 32 || v101 == 9 )
        {
          v101 = *++v100;
          if ( !*v100 )
            goto LABEL_263;
        }
      }
      if ( *v100 )
      {
        v102 = -1;
        do
          ++v102;
        while ( v98[v102] );
        if ( !(unsigned int)StrTrimBoth_Sys(v98) )
        {
          if ( !*v98 )
          {
LABEL_30:
            v28 = this;
            goto LABEL_31;
          }
          v103 = v98;
          v104 = *v98;
          while ( v104 == 32 || v104 == 9 )
          {
            v104 = *++v103;
            if ( !*v103 )
              goto LABEL_263;
          }
          if ( *v103 )
          {
            v105 = v8 == 0;
            v28 = this;
            if ( v105 )
            {
              v106 = 256;
              v107 = (char *)this + 512;
              v108 = v98 - ((char *)this + 512);
              while ( v106 != -2147483390 )
              {
                v109 = v107[v108];
                if ( !v109 )
                  break;
                *v107++ = v109;
                if ( !--v106 )
                {
                  --v107;
                  break;
                }
              }
              *v107 = 0;
            }
LABEL_31:
            if ( strcmp("mssqlserver", (const char *)v28 + 512) )
            {
              v29 = -1;
              do
                ++v29;
              while ( v23[v29] );
              if ( v29 <= 0xFF )
              {
                do
                  ++v6;
                while ( v23[v6] );
                if ( !(unsigned int)StrTrimBoth_Sys(v23) )
                {
                  v30 = 256;
                  v31 = (char *)v28 + 256;
                  while ( v30 != -2147483390 )
                  {
                    v32 = v31[v23 - ((char *)v28 + 256)];
                    if ( !v32 )
                      break;
                    *v31++ = v32;
                    if ( !--v30 )
                    {
                      --v31;
                      break;
                    }
                  }
                  *v31 = 0;
                  v33 = v23;
                  v34 = *v23;
                  if ( *v23 )
                  {
                    while ( v34 == 32 || v34 == 9 )
                    {
                      v34 = *++v33;
                      if ( !*v33 )
                        goto LABEL_47;
                    }
                  }
                  if ( *v33 && !IsLocalHost(v23) )
                  {
                    v35 = (char *)v28;
                    v110 = v23 - (char *)v28;
                    while ( v12 != -2147483390 )
                    {
                      v111 = v35[v110];
                      if ( !v111 )
                        break;
                      *v35++ = v111;
                      if ( !--v12 )
                      {
LABEL_230:
                        --v35;
                        break;
                      }
                    }
                  }
                  else
                  {
LABEL_47:
                    v35 = (char *)v28;
                    if ( !strcmp("admin", (const char *)v28 + 768) )
                    {
                      while ( v12 != -2147483390 )
                      {
                        v112 = v35["localhost" - (const char *)v28];
                        if ( !v112 )
                          break;
                        *v35++ = v112;
                        if ( !--v12 )
                          goto LABEL_230;
                      }
                    }
                    else
                    {
                      while ( v12 != -2147483390 )
                      {
                        v36 = v35[gszComputerName - (CHAR *)v28];
                        if ( !v36 )
                          break;
                        *v35++ = v36;
                        if ( !--v12 )
                          goto LABEL_230;
                      }
                    }
                  }
                  *v35 = 0;
                  v37 = (char *)v28 + 768;
                  if ( strcmp("lpc", (const char *)v28 + 768) || IsLocalHost((PCNZCH)v28) )
                  {
                    v38 = 512;
                    v39 = (char *)v28 + 1035;
                    while ( v38 != -2147483134 )
                    {
                      v40 = *(v39 - 1035);
                      if ( !v40 )
                        break;
                      *v39++ = v40;
                      if ( !--v38 )
                      {
                        --v39;
                        break;
                      }
                    }
                    *v39 = 0;
                    if ( !*((_BYTE *)v28 + 512)
                      || (StringCchCatA((char *)v28 + 1035, 0x200u, "\\"),
                          StringCchCatA((char *)v28 + 1035, 0x200u, (const char *)v28 + 512),
                          !strcmp("lpc", (const char *)v28 + 768))
                      || !strcmp("admin", (const char *)v28 + 768) )
                    {
                      *((_BYTE *)v28 + 1547) = 0;
                    }
                    if ( a3 )
                    {
                      if ( !strcmp("np", (const char *)v28 + 768)
                        || !strcmp("via", (const char *)v28 + 768)
                        || !strcmp("lpc", (const char *)v28 + 768)
                        || !strcmp("admin", (const char *)v28 + 768) )
                      {
                        v131 = 87;
                        if ( (bidGblFlags & 2) != 0
                          && `ConnectParameter::ParseConnectionString'::`189'::_bidPtrSA_030_582[0] )
                        {
                          v119 = SniErrorIdFromStringId(0xC3E5u);
                          bidTraceA(
                            `ConnectParameter::ParseConnectionString'::`189'::_bidSrcFileA[0],
                            595968,
                            `ConnectParameter::ParseConnectionString'::`189'::_bidPtrSA_030_582[0],
                            9,
                            v119,
                            87);
                        }
                        SNISetLastError(9, 87, 50149);
                        v7 = 1;
                        goto LABEL_63;
                      }
                      v7 = 0;
                      if ( !*v37 )
                      {
                        v114 = 0;
                        v115 = (const char *)("tcp" - v37);
                        v116 = 11;
                        while ( v116 != -2147483635 )
                        {
                          v117 = v37[(_QWORD)v115];
                          if ( !v117 )
                            break;
                          *v37++ = v117;
                          if ( !--v116 )
                          {
                            --v37;
                            v114 = -2147024774;
                            break;
                          }
                        }
                        *v37 = 0;
                        if ( v114 < 0 )
                        {
                          if ( (bidGblFlags & 2) != 0
                            && `ConnectParameter::ParseConnectionString'::`203'::_bidPtrSA_030_594[0] )
                          {
                            bidTraceA(
                              `ConnectParameter::ParseConnectionString'::`203'::_bidSrcFileA[0],
                              608256,
                              `ConnectParameter::ParseConnectionString'::`203'::_bidPtrSA_030_594[0],
                              (unsigned int)v114,
                              lpDestStra,
                              cchDesta);
                          }
                          v131 = 87;
                          if ( (bidGblFlags & 2) != 0
                            && `ConnectParameter::ParseConnectionString'::`211'::_bidPtrSA_030_597[0] )
                          {
                            v118 = SniErrorIdFromStringId(0xC3B4u);
                            bidTraceA(
                              `ConnectParameter::ParseConnectionString'::`211'::_bidSrcFileA[0],
                              611328,
                              `ConnectParameter::ParseConnectionString'::`211'::_bidPtrSA_030_597[0],
                              9,
                              v118,
                              87);
                          }
                          SNISetLastError(9, 87, 50100);
                          v7 = 1;
                          goto LABEL_63;
                        }
                      }
                    }
                    else
                    {
                      v7 = 0;
                    }
                    v131 = 0;
                  }
                  else
                  {
                    if ( (bidGblFlags & 2) != 0
                      && `ConnectParameter::ParseConnectionString'::`168'::_bidPtrSA_030_552[0] )
                    {
                      v113 = SniErrorIdFromStringId(0xC3DDu);
                      bidTraceA(
                        `ConnectParameter::ParseConnectionString'::`168'::_bidSrcFileA[0],
                        565248,
                        `ConnectParameter::ParseConnectionString'::`168'::_bidPtrSA_030_552[0],
                        9,
                        v113,
                        87);
                    }
                    SNISetLastError(9, 87, 50141);
                    v7 = 1;
                  }
                  goto LABEL_63;
                }
              }
            }
            goto LABEL_264;
          }
        }
      }
    }
LABEL_263:
    v28 = this;
    goto LABEL_264;
  }
  if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_196[0] )
  {
    v43 = SniErrorIdFromStringId(0xC3B4u);
    bidTraceA(
      `ConnectParameter::ParseConnectionString'::`20'::_bidSrcFileA[0],
      200704,
      `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_196[0],
      9,
      v43,
      14);
  }
  SNISetLastError(9, 14, 50100);
  if ( (bidGblFlags & 0x20002) == 0x20002 && `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_198[0] )
    bidTraceA(
      `ConnectParameter::ParseConnectionString'::`27'::_bidSrcFileA[0],
      202752,
      `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_198[0],
      14,
      lpDestStr,
      cchDest);
  if ( v126 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 14;
}

```

## disassembly

```asm
0x3838804e0  mov     r11, rsp
0x3838804e3  mov     [r11+18h], r8b
0x3838804e7  mov     [r11+8], rcx
0x3838804eb  push    rbp
0x3838804ec  push    rsi
0x3838804ed  push    rdi
0x3838804ee  push    r12
0x3838804f0  push    r13
0x3838804f2  push    r14
0x3838804f4  push    r15
0x3838804f6  sub     rsp, 80h
0x3838804fd  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x383880505  mov     [r11+10h], rbx
0x383880509  movzx   ebx, r8b
0x38388050d  mov     rsi, rdx
0x383880510  mov     rdi, rcx
0x383880513  or      r13, 0FFFFFFFFFFFFFFFFh
0x383880517  mov     [r11-50h], r13
0x38388051b  mov     eax, cs:_bidGblFlags
0x383880521  and     eax, 20004h
0x383880526  cmp     eax, 20004h
0x38388052b  jz      loc_3838F86A1
0x383880531  xor     r14d, r14d
0x383880534  mov     r12d, r14d
0x383880537  mov     [rdi+60Dh], bl
0x38388053d  cmp     [rdi+60Bh], r12b
0x383880544  jz      loc_3838F86CA
0x38388054a  test    bl, bl
0x38388054c  lea     eax, [r14+1]
0x383880550  jnz     loc_3838F86CA
0x383880556  mov     [rdi+60Bh], al
0x38388055c  mov     rdi, r13
0x38388055f  inc     rdi
0x383880562  cmp     [rsi+rdi], r12b
0x383880566  jnz     short loc_38388055F
0x383880568  lea     ebx, [rdi+1]
0x38388056b  mov     ebp, ebx
0x38388056d  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x383880574  mov     rax, [rcx]
0x383880577  mov     edx, ebx
0x383880579  call    qword ptr [rax+70h]
0x38388057c  mov     [rsp+0B8h+Str], rax
0x383880581  test    rax, rax
0x383880584  jz      loc_3838F86D2
0x38388058a  mov     [rsp+0B8h+arg_18], 57h ; 'W'
0x383880595  mov     [rsp+0B8h+cchDest], ebx; cchDest
0x383880599  mov     [rsp+0B8h+lpDestStr], rax; lpDestStr
0x38388059e  mov     r9d, r13d; cchSrc
0x3838805a1  mov     r8, rsi; lpSrcStr
0x3838805a4  mov     r15d, 100h
0x3838805aa  mov     edx, r15d; dwMapFlags
0x3838805ad  mov     ecx, 800h; Locale
0x3838805b2  call    cs:__imp_LCMapStringA
0x3838805b8  test    eax, eax
0x3838805ba  jz      loc_3838F918C
0x3838805c0  cmp     eax, ebx
0x3838805c2  ja      loc_3838F918C
0x3838805c8  mov     eax, edi
0x3838805ca  mov     rcx, [rsp+0B8h+Str]; Source
0x3838805cf  mov     [rax+rcx], r12b
0x3838805d3  mov     rdx, rbp
0x3838805d6  call    StrTrimBoth_Sys
0x3838805db  test    eax, eax
0x3838805dd  jnz     loc_3838F918C
0x3838805e3  mov     rax, [rsp+0B8h+Str]
0x3838805e8  mov     [rsp+0B8h+var_48], rax
0x3838805ed  mov     edx, 3Ah ; ':'; Val
0x3838805f2  mov     rcx, rax; Str
0x3838805f5  call    cs:__imp_strchr
0x3838805fb  mov     r14, rax
0x3838805fe  mov     ebp, 0Bh
0x383880603  lea     rdi, aTcp; "tcp"
0x38388060a  lea     rbx, aNp; "np"
0x383880611  test    rax, rax
0x383880614  jz      loc_38388EAD4
0x38388061a  mov     [rax], r12b
0x38388061d  mov     rcx, rax
0x383880620  mov     rsi, [rsp+0B8h+Str]
0x383880625  sub     rcx, rsi
0x383880628  cmp     rcx, 0Ah
0x38388062c  jg      loc_3838F9199
0x383880632  mov     edx, ebp
0x383880634  mov     rbx, [rsp+0B8h+lpString2]
0x38388063c  add     rbx, 300h
0x383880643  mov     rcx, rbx
0x383880646  mov     rdi, rsi
0x383880649  sub     rdi, rbx
0x38388064c  nop     dword ptr [rax+00h]
0x383880650  lea     rax, [rdx+7FFFFFF3h]
0x383880657  test    rax, rax
0x38388065a  jz      short loc_383880673
0x38388065c  movzx   eax, byte ptr [rcx+rdi]
0x383880660  test    al, al
0x383880662  jz      short loc_383880673
0x383880664  mov     [rcx], al
0x383880666  inc     rcx
0x383880669  dec     rdx
0x38388066c  jnz     short loc_383880650
0x38388066e  jmp     loc_3838F87A5
0x383880673  test    rdx, rdx
0x383880676  jz      loc_3838F87A7
0x38388067c  mov     [rcx], r12b
0x38388067f  mov     rdx, r13
0x383880682  nop     dword ptr [rax+00000000h]
0x383880689  nop     dword ptr [rax+00000000h]
0x383880690  inc     rdx
0x383880693  cmp     [rbx+rdx], r12b
0x383880697  jnz     short loc_383880690
0x383880699  inc     rdx
0x38388069c  mov     rcx, rbx; Source
0x38388069f  call    StrTrimBoth_Sys
0x3838806a4  test    eax, eax
0x3838806a6  jnz     loc_3838F9199
0x3838806ac  cmp     r14, rsi
0x3838806af  jz      loc_3838F87FB
0x3838806b5  lea     rsi, aTcp; "tcp"
0x3838806bc  mov     rdi, rbx
0x3838806bf  mov     ecx, 4
0x3838806c4  repe cmpsb
0x3838806c6  jnz     loc_3838F87AF
0x3838806cc  inc     r14
0x3838806cf  mov     rdx, r13
0x3838806d2  inc     rdx
0x3838806d5  cmp     [r14+rdx], r12b
0x3838806d9  jnz     short loc_3838806D2
0x3838806db  inc     rdx
0x3838806de  mov     rcx, r14; Source
0x3838806e1  call    StrTrimBoth_Sys
0x3838806e6  test    eax, eax
0x3838806e8  jnz     loc_3838F87F6
0x3838806ee  lea     rbx, aNp; "np"
0x3838806f5  lea     rdi, aTcp; "tcp"
0x3838806fc  mov     [rsp+0B8h+cchDest], 2; cchCount2
0x383880704  lea     rax, Str2; "\\\\"
0x38388070b  mov     [rsp+0B8h+lpDestStr], rax; lpString2
0x383880710  mov     r9d, 2; cchCount1
0x383880716  mov     r8, r14; lpString1
0x383880719  xor     edx, edx; dwCmpFlags
0x38388071b  mov     ecx, 800h; Locale
0x383880720  call    cs:__imp_CompareStringA
0x383880726  cmp     eax, 2
0x383880729  jz      loc_3838F880C
0x38388072f  mov     edx, 2Ch ; ','; Val
0x383880734  mov     rcx, r14; Str
0x383880737  call    cs:__imp_strchr
0x38388073d  test    rax, rax
0x383880740  jnz     loc_3838F8BAD
0x383880746  mov     rdx, r13
0x383880749  inc     rdx
0x38388074c  cmp     byte ptr [r14+rdx], 0
0x383880751  jnz     short loc_383880749
0x383880753  mov     r8b, 5Ch ; '\'
0x383880756  mov     rcx, r14; lpCurrentChar
0x383880759  call    StrChrA_SYS
0x38388075e  test    rax, rax
0x383880761  jnz     loc_3838F8D55
0x383880767  mov     r12, [rsp+0B8h+lpString2]
0x38388076f  lea     rsi, aMssqlserver_1; "mssqlserver"
0x383880776  lea     rdi, [r12+200h]
0x38388077e  mov     ecx, 0Ch
0x383880783  repe cmpsb
0x383880785  jz      loc_3838F91B1
0x38388078b  mov     rax, r13
0x38388078e  inc     rax
0x383880791  cmp     byte ptr [r14+rax], 0
0x383880796  jnz     short loc_38388078E
0x383880798  cmp     rax, 0FFh
0x38388079e  ja      loc_3838F91B1
0x3838807a4  nop     word ptr [rax+rax+00h]
0x3838807aa  nop     word ptr [rax+rax+00h]
0x3838807b0  inc     r13
0x3838807b3  cmp     byte ptr [r14+r13], 0
0x3838807b8  jnz     short loc_3838807B0
0x3838807ba  lea     rdx, [r13+1]
0x3838807be  mov     rcx, r14; Source
0x3838807c1  call    StrTrimBoth_Sys
0x3838807c6  test    eax, eax
0x3838807c8  jnz     loc_3838F91B1
0x3838807ce  mov     rdx, r15
0x3838807d1  lea     rcx, [r12+100h]
0x3838807d9  mov     rdi, r14
0x3838807dc  sub     rdi, rcx
0x3838807df  nop
0x3838807e0  lea     rax, [rdx+7FFFFEFEh]
0x3838807e7  test    rax, rax
0x3838807ea  jz      short loc_383880814
0x3838807ec  movzx   eax, byte ptr [rcx+rdi]
0x3838807f0  test    al, al
0x3838807f2  jz      short loc_383880814
0x3838807f4  mov     [rcx], al
0x3838807f6  inc     rcx
0x3838807f9  dec     rdx
0x3838807fc  jnz     short loc_3838807E0
0x3838807fe  jmp     loc_3838F8E50
0x383880814  test    rdx, rdx
0x383880817  jz      loc_3838F8E52
0x38388081d  mov     byte ptr [rcx], 0
0x383880820  mov     rcx, r14
0x383880823  movzx   eax, byte ptr [r14]
0x383880827  test    al, al
0x383880829  jz      short loc_38388083B
0x38388082b  cmp     al, 20h ; ' '
0x38388082d  jz      loc_3838F8E5A
0x383880833  cmp     al, 9
0x383880835  jz      loc_3838F8E5A
0x38388083b  cmp     byte ptr [rcx], 0
0x38388083e  jz      short loc_383880850
0x383880840  mov     rcx, r14; lpString2
0x383880843  call    ?IsLocalHost@@YA_NPEBD@Z; IsLocalHost(char const *)
0x383880848  test    al, al
0x38388084a  jz      loc_3838F8E6D
0x383880850  lea     rdi, [r12+300h]
0x383880858  lea     rsi, aAdmin; "admin"
0x38388085f  mov     ecx, 6
0x383880864  repe cmpsb
0x383880866  mov     rcx, r12
0x383880869  jz      loc_3838F8EA3
0x38388086f  lea     rdi, ?gszComputerName@@3PADA; char near * gszComputerName
0x383880876  sub     rdi, r12
0x383880879  lea     rax, [r15+7FFFFEFEh]
0x383880880  test    rax, rax
0x383880883  jz      short loc_38388089C
0x383880885  movzx   eax, byte ptr [rcx+rdi]
0x383880889  test    al, al
0x38388088b  jz      short loc_38388089C
0x38388088d  mov     [rcx], al
0x38388088f  inc     rcx
0x383880892  dec     r15
0x383880895  jnz     short loc_383880879
0x383880897  jmp     loc_3838F8EA1
0x38388089c  test    r15, r15
0x38388089f  jz      loc_3838F8ED8
0x3838808a5  mov     byte ptr [rcx], 0
0x3838808a8  lea     rbx, [r12+300h]
0x3838808b0  lea     rsi, aLpc; "lpc"
0x3838808b7  mov     rdi, rbx
0x3838808ba  mov     ecx, 4
0x3838808bf  repe cmpsb
0x3838808c1  jz      loc_3838F8EE0
0x3838808c7  mov     edx, 200h
0x3838808cc  lea     rsi, [r12+40Bh]
0x3838808d4  mov     rcx, rsi
0x3838808d7  mov     rdi, r12
0x3838808da  sub     rdi, rsi
0x3838808dd  nop     dword ptr [rax]
0x3838808e0  lea     rax, [rdx+7FFFFDFEh]
0x3838808e7  test    rax, rax
0x3838808ea  jz      short loc_383880903
0x3838808ec  movzx   eax, byte ptr [rcx+rdi]
0x3838808f0  test    al, al
0x3838808f2  jz      short loc_383880903
0x3838808f4  mov     [rcx], al
0x3838808f6  inc     rcx
0x3838808f9  dec     rdx
0x3838808fc  jnz     short loc_3838808E0
0x3838808fe  jmp     loc_3838F8F57
0x383880903  test    rdx, rdx
0x383880906  jz      loc_3838F8F59
0x38388090c  mov     byte ptr [rcx], 0
0x38388090f  cmp     byte ptr [r12+200h], 0
0x383880918  jnz     loc_3838F8F61
0x38388091e  mov     byte ptr [r12+60Bh], 0
0x383880927  cmp     [rsp+0B8h+arg_10], 0
0x38388092f  jnz     loc_3838F8FBD
0x383880935  xor     r14d, r14d
0x383880938  mov     [rsp+0B8h+arg_18], r14d
0x383880940  jmp     short $+2
0x383880942  mov     rsi, [rsp+0B8h+Str]
0x383880947  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38388094e  mov     rax, [rcx]
0x383880951  mov     rdx, rsi
0x383880954  call    qword ptr [rax+80h]
0x38388095a  mov     edi, [rsp+0B8h+arg_18]
0x383880961  test    edi, edi
0x383880963  jnz     loc_3838F91B9
0x383880969  mov     eax, cs:_bidGblFlags
0x38388096f  and     eax, 20002h
0x383880974  cmp     eax, 20002h
0x383880979  jz      loc_3838F921C
0x38388097f  mov     eax, cs:_bidGblFlags
0x383880985  and     eax, 20002h
0x38388098a  cmp     eax, 20002h
0x38388098f  jz      loc_3838F92AB
0x383880995  cmp     [rsp+0B8h+var_50], 0FFFFFFFFFFFFFFFFh
0x38388099b  jnz     loc_3838F92DC
0x3838809a1  mov     eax, edi
0x3838809a3  mov     rbx, [rsp+0B8h+arg_8]
0x3838809ab  add     rsp, 80h
0x3838809b2  pop     r15
0x3838809b4  pop     r14
0x3838809b6  pop     r13
0x3838809b8  pop     r12
0x3838809ba  pop     rdi
0x3838809bb  pop     rsi
0x3838809bc  pop     rbp
0x3838809bd  retn
0x38388ead4  mov     r14, [rsp+0B8h+var_48]
0x38388ead9  jmp     loc_3838806FC
0x3838f86a1  mov     rax, cs:?_bidPtrSA_040_176@?6??ParseConnectionString@ConnectParameter@@QEAAKPEBD_N@Z@4REBDEB; char const * const `ConnectParameter::ParseConnectionString(char const *,bool)'::`7'::_bidPtrSA_040_176
0x3838f86a8  test    rax, rax
  ... truncated ...
```
