# ParseCommandLine(int,ushort * * const,int *,int *,ulong *,APPHOST_CONFIG *)

- ea: `0x140002c58`
- end: `0x140003774`
- name: `?ParseCommandLine@@YAHHQEAPEAGPEAH1PEAKPEAUAPPHOST_CONFIG@@@Z`
- size: `2844`
- prototype: `__int64 __fastcall(int, unsigned __int16 **const, int *, int *, unsigned int *, struct APPHOST_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400027b0`

## callees

- `0x140002c58`
- `0x14000377c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140003029`
- `msvcrt!_wcsicmp` at `0x140003055`
- `msvcrt!_wcsicmp` at `0x1400030a5`
- `msvcrt!_wcsicmp` at `0x140003581`
- `msvcrt!_wcsicmp` at `0x1400035a8`
- `msvcrt!_wcsicmp` at `0x140003029`
- `msvcrt!_wcsicmp` at `0x140003055`
- `msvcrt!_wcsicmp` at `0x1400030a5`
- `msvcrt!_wcsicmp` at `0x140003581`
- `msvcrt!_wcsicmp` at `0x1400035a8`
- `msvcrt!wcstoul` at `0x1400031df`
- `msvcrt!wcstoul` at `0x1400032a8`
- `msvcrt!wcstoul` at `0x140003324`
- `msvcrt!wcstoul` at `0x1400033ba`
- `msvcrt!wcstoul` at `0x140003451`
- `msvcrt!wcstoul` at `0x1400034e8`
- `msvcrt!wcstoul` at `0x1400031df`
- `msvcrt!wcstoul` at `0x1400032a8`
- `msvcrt!wcstoul` at `0x140003324`
- `msvcrt!wcstoul` at `0x1400033ba`
- `msvcrt!wcstoul` at `0x140003451`
- `msvcrt!wcstoul` at `0x1400034e8`
- `iisutil!PuDbgPrint` at `0x140002cbe`
- `iisutil!PuDbgPrint` at `0x140002ea7`
- `iisutil!PuDbgPrint` at `0x140002f11`
- `iisutil!PuDbgPrint` at `0x140002f4a`
- `iisutil!PuDbgPrint` at `0x140002fb8`
- `iisutil!PuDbgPrint` at `0x140003615`
- `iisutil!PuDbgPrint` at `0x140003650`
- `iisutil!PuDbgPrint` at `0x14000368b`
- `iisutil!PuDbgPrint` at `0x1400036c6`
- `iisutil!PuDbgPrint` at `0x140003709`
- `iisutil!PuDbgPrint` at `0x140003748`
- `iisutil!PuDbgPrint` at `0x140002cbe`
- `iisutil!PuDbgPrint` at `0x140002ea7`
- `iisutil!PuDbgPrint` at `0x140002f11`
- `iisutil!PuDbgPrint` at `0x140002f4a`
- `iisutil!PuDbgPrint` at `0x140002fb8`
- `iisutil!PuDbgPrint` at `0x140003615`
- `iisutil!PuDbgPrint` at `0x140003650`
- `iisutil!PuDbgPrint` at `0x14000368b`
- `iisutil!PuDbgPrint` at `0x1400036c6`
- `iisutil!PuDbgPrint` at `0x140003709`
- `iisutil!PuDbgPrint` at `0x140003748`

## string_xrefs

- `0x140002c97`: `ParseCommandLine`
- `0x140002cdc`: `ParseCommandLine`
- `0x140002cb7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\parsecommandline.cxx`
- `0x140002ce8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\parsecommandline.cxx`
- `0x14000323f`: `Root Web Config File, %S\n`
- `0x140003122`: `ClrConfigFile, %S\n`

## pseudocode

```c
__int64 __fastcall ParseCommandLine(
        int a1,
        unsigned __int16 **const a2,
        int *a3,
        int *a4,
        unsigned int *a5,
        struct APPHOST_CONFIG *a6)
{
  int v8; // r15d
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned __int16 *v26; // rcx
  bool v27; // zf
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned __int16 *v34; // rcx
  int *v35; // r14
  __int64 v36; // rax
  __int64 v37; // r8
  unsigned __int16 *v38; // rcx
  const wchar_t *v39; // rcx
  __int64 v40; // r14
  unsigned __int16 *v41; // rcx
  unsigned __int16 *v42; // rcx
  unsigned __int16 *v43; // rcx
  const wchar_t *v44; // rcx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned __int16 *v51; // rcx
  unsigned __int16 v52; // cx
  const wchar_t *v53; // rcx
  __int64 v54; // r14
  signed int v55; // eax
  const wchar_t *v56; // rcx
  __int64 v57; // r14
  unsigned int v58; // eax
  const wchar_t *v59; // rcx
  __int64 v60; // r14
  unsigned int v61; // eax
  const wchar_t *v62; // rcx
  __int64 v63; // r14
  unsigned int v64; // eax
  const wchar_t *v65; // rcx
  __int64 v66; // r14
  unsigned int v67; // eax
  const wchar_t *v68; // rcx
  __int64 v69; // r14
  __int64 v70; // rax
  __int64 v71; // [rsp+28h] [rbp-40h]

  *a3 = 0;
  if ( a1 < 2 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
        131,
        "ParseCommandLine",
        "Invalid number of parameters (%d)\n",
        a1);
    PrintUsage(*a2);
    return 0;
  }
  v8 = 1;
  v9 = 1;
  while ( v9 )
  {
    v10 = a2[v8];
    if ( ((*v10 - 45) & 0xFFFD) != 0 )
      goto LABEL_178;
    v11 = v8;
    v12 = v10[1];
    if ( v12 > 0x57 )
    {
      if ( v12 > 0x6D )
      {
        v45 = v12 - 111;
        if ( v45 )
        {
          v46 = v45 - 3;
          if ( v46 )
          {
            v47 = v46 - 1;
            if ( v47 )
            {
              v48 = v47 - 1;
              if ( v48 )
              {
                v49 = v48 - 1;
                if ( v49 )
                {
                  v50 = v49 - 1;
                  if ( !v50 )
                  {
LABEL_29:
                    v26 = a2[++v8];
                    v27 = (g_dwDebugFlags & 3) == 0;
                    *((_QWORD *)a6 + 5) = v26;
                    if ( !v27 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                        386,
                        "ParseCommandLine",
                        "ClrVersion, %S\n",
                        v26);
                    goto LABEL_42;
                  }
                  if ( v50 == 1 )
                  {
LABEL_100:
                    v51 = a2[++v8];
                    v27 = (g_dwDebugFlags & 3) == 0;
                    *((_QWORD *)a6 + 9) = v51;
                    if ( !v27 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                        373,
                        "ParseCommandLine",
                        "Root Web Config File, %S\n",
                        v51);
                    goto LABEL_42;
                  }
                  goto LABEL_61;
                }
LABEL_102:
                if ( !v10[2] )
                  goto LABEL_75;
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    214,
                    "ParseCommandLine",
                    "invalid argument %S\n",
                    a2[v8]);
                goto LABEL_61;
              }
LABEL_105:
              v52 = v10[2];
              if ( ((v52 - 65) & 0xFFDF) != 0 || v10[3] )
              {
                if ( ((v52 - 84) & 0xFFDF) != 0 || v10[3] )
                {
                  if ( v52 )
                  {
                    if ( (g_dwDebugFlags & 3) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                        334,
                        "ParseCommandLine",
                        "invalid argument %S\n",
                        a2[v8]);
                  }
                  else
                  {
                    v59 = a2[++v8];
                    v60 = v11;
                    v61 = wcstoul(v59, 0, 0);
                    *((_DWORD *)a6 + 3) = v61;
                    if ( v61 )
                    {
                      if ( (g_dwDebugFlags & 3) != 0 )
                      {
                        LODWORD(v71) = v61;
                        PuDbgPrint(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                          348,
                          "ParseCommandLine",
                          "The idle time value is %lu\n",
                          v71);
                      }
                      goto LABEL_42;
                    }
                    if ( (g_dwDebugFlags & 3) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                        343,
                        "ParseCommandLine",
                        "Invalid idle time %ws\n",
                        a2[v60 + 1]);
                  }
                }
                else
                {
                  v56 = a2[++v8];
                  v57 = v11;
                  v58 = wcstoul(v56, 0, 0);
                  g_dwShutDownTimeout = v58;
                  if ( v58 )
                  {
                    if ( (g_dwDebugFlags & 3) != 0 )
                    {
                      LODWORD(v71) = v58;
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                        329,
                        "ParseCommandLine",
                        "The shutdown timeout value is %lu\n",
                        v71);
                    }
                    goto LABEL_42;
                  }
                  if ( (g_dwDebugFlags & 3) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                      324,
                      "ParseCommandLine",
                      "Invalid shutdown timeout value %ws\n",
                      a2[v57 + 1]);
                }
              }
              else
              {
                v53 = a2[++v8];
                v54 = v11;
                v55 = wcstoul(v53, 0, 0);
                *((_DWORD *)a6 + 4) = v55;
                if ( v55 <= 1 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 )
                  {
                    LODWORD(v71) = v55;
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                      311,
                      "ParseCommandLine",
                      "The idle timeout action is %lu\n",
                      v71);
                  }
                  goto LABEL_42;
                }
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    306,
                    "ParseCommandLine",
                    "Invalid idle timeout action %ws\n",
                    a2[v54 + 1]);
              }
              goto LABEL_61;
            }
LABEL_127:
            if ( v10[2] )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                  152,
                  "ParseCommandLine",
                  "invalid argument %S\n",
                  a2[v8]);
            }
            else
            {
              v62 = a2[++v8];
              v63 = v11;
              v64 = wcstoul(v62, 0, 0);
              *((_DWORD *)a6 + 23) = v64;
              if ( v64 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  LODWORD(v71) = v64;
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    166,
                    "ParseCommandLine",
                    "Site Id is %lu\n",
                    v71);
                }
                goto LABEL_42;
              }
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                  161,
                  "ParseCommandLine",
                  "Invalid site id %ws\n",
                  a2[v63 + 1]);
            }
            goto LABEL_61;
          }
LABEL_135:
          if ( v10[2] )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                274,
                "ParseCommandLine",
                "invalid argument %S\n",
                a2[v8]);
          }
          else
          {
            v65 = a2[++v8];
            v66 = v11;
            v67 = wcstoul(v65, 0, 0);
            *((_DWORD *)a6 + 2) = v67;
            if ( v67 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                LODWORD(v71) = v67;
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                  288,
                  "ParseCommandLine",
                  "Maximum requests is %lu\n",
                  v71);
              }
              goto LABEL_42;
            }
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                283,
                "ParseCommandLine",
                "Invalid maximum requests %ws\n",
                a2[v66 + 1]);
          }
          goto LABEL_61;
        }
LABEL_143:
        if ( v10[2] )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              444,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v8]);
        }
        else
        {
          v68 = a2[++v8];
          v69 = v11;
          if ( !_wcsicmp(v68, L"enable") )
          {
            *((_DWORD *)a6 + 24) = 1;
            goto LABEL_42;
          }
          if ( !_wcsicmp(a2[v69 + 1], L"disable") )
          {
            *((_DWORD *)a6 + 24) = 0;
            goto LABEL_42;
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              460,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v69 + 1]);
        }
        goto LABEL_61;
      }
      if ( v12 == 109 )
        goto LABEL_89;
      v28 = v12 - 97;
      if ( !v28 )
      {
LABEL_81:
        if ( ((v10[2] - 80) & 0xFFDF) == 0 && !v10[3] )
        {
          v42 = a2[++v8];
          *((_QWORD *)a6 + 3) = v42;
          goto LABEL_42;
        }
        if ( !v10[2] )
        {
          v43 = a2[++v8];
          v27 = (g_dwDebugFlags & 3) == 0;
          *(_QWORD *)a6 = v43;
          if ( !v27 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              247,
              "ParseCommandLine",
              "NamedPipe Id, %S\n",
              v43);
          goto LABEL_42;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v37 = 237;
LABEL_60:
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
            v37,
            "ParseCommandLine",
            "invalid parameter passed in '%S' \n",
            a2[v8]);
        }
LABEL_61:
        v9 = 0;
        goto LABEL_42;
      }
      v29 = v28 - 2;
      if ( !v29 )
      {
LABEL_79:
        v41 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *((_QWORD *)a6 + 6) = v41;
        if ( !v27 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
            411,
            "ParseCommandLine",
            "ClrConfigFile, %S\n",
            v41);
        goto LABEL_42;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
LABEL_73:
        if ( !_wcsicmp(v10 + 1, L"debug") )
        {
          *a4 = 1;
LABEL_75:
          v35 = a3;
          *a3 = 1;
          goto LABEL_43;
        }
        if ( a2[v8][2] )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              179,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v8]);
          goto LABEL_61;
        }
        goto LABEL_42;
      }
      v31 = v30 - 3;
      if ( !v31 )
      {
LABEL_64:
        if ( v10[2] )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              188,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v8]);
        }
        else
        {
          v39 = a2[++v8];
          v40 = v11;
          if ( !_wcsicmp(v39, L"true") )
          {
            *a4 = 1;
            goto LABEL_42;
          }
          if ( !_wcsicmp(a2[v40 + 1], L"false") )
          {
            *a4 = 0;
            goto LABEL_42;
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              204,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v40 + 1]);
        }
        goto LABEL_61;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
LABEL_62:
        v38 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *((_QWORD *)a6 + 8) = v38;
        if ( !v27 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
            361,
            "ParseCommandLine",
            "Application Host File, %S\n",
            v38);
        goto LABEL_42;
      }
      v33 = v32 - 1;
      if ( v33 )
      {
        if ( v33 == 3 )
        {
LABEL_40:
          v34 = a2[++v8];
          v27 = (g_dwDebugFlags & 3) == 0;
          *((_QWORD *)a6 + 13) = v34;
          if ( !v27 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              399,
              "ParseCommandLine",
              "ClrLoader, %S\n",
              v34);
          goto LABEL_42;
        }
        goto LABEL_61;
      }
    }
    else
    {
      if ( v12 == 87 )
        goto LABEL_100;
      if ( v12 > 0x4C )
      {
        v20 = v12 - 77;
        if ( !v20 )
        {
LABEL_89:
          if ( !v10[2] )
          {
            v44 = a2[++v8];
            *((_DWORD *)a6 + 14) = wcstoul(v44, 0, 0);
            goto LABEL_42;
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              421,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v8]);
          goto LABEL_61;
        }
        v21 = v20 - 2;
        if ( v21 )
        {
          v22 = v21 - 3;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                v25 = v24 - 1;
                if ( v25 )
                {
                  if ( v25 == 1 )
                    goto LABEL_29;
                  goto LABEL_61;
                }
                goto LABEL_102;
              }
              goto LABEL_105;
            }
            goto LABEL_127;
          }
          goto LABEL_135;
        }
        goto LABEL_143;
      }
      if ( v12 == 76 )
        goto LABEL_40;
      v13 = v12 - 63;
      if ( !v13 )
        goto LABEL_61;
      v14 = v13 - 2;
      if ( !v14 )
        goto LABEL_81;
      v15 = v14 - 2;
      if ( !v15 )
        goto LABEL_79;
      v16 = v15 - 1;
      if ( !v16 )
        goto LABEL_73;
      v17 = v16 - 3;
      if ( !v17 )
        goto LABEL_64;
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_62;
      if ( v18 != 1 )
        goto LABEL_61;
    }
    if ( ((v10[2] - 78) & 0xFFDF) != 0 || v10[3] )
    {
      if ( v10[2] )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v37 = 265;
          goto LABEL_60;
        }
        goto LABEL_61;
      }
    }
    else
    {
      v19 = a2[++v8];
      *((_QWORD *)a6 + 10) = v19;
    }
LABEL_42:
    v35 = a3;
LABEL_43:
    if ( ++v8 >= a1 )
    {
      if ( !v9 )
        break;
      v36 = *((_QWORD *)a6 + 3);
      if ( *(_QWORD *)a6 )
      {
        if ( !v36 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              497,
              "ParseCommandLine",
              "No app pool was passed and not in user console mode\n");
          v9 = 0;
        }
        if ( *v35 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              504,
              "ParseCommandLine",
              "Pipeline id cannot be passed when not in user console mode\n");
          v9 = 0;
        }
        if ( *((_DWORD *)a6 + 23) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              509,
              "ParseCommandLine",
              "Site id cannot be passed when not in user console mode\n");
          goto LABEL_172;
        }
      }
      else
      {
        if ( v36 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              519,
              "ParseCommandLine",
              "App pool was passed and in user console mode\n");
          v9 = 0;
        }
        if ( *((_DWORD *)a6 + 14) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              525,
              "ParseCommandLine",
              "Managed pipeline mode can not be passed when in user console mode\n");
          v9 = 0;
        }
        if ( *((_DWORD *)a6 + 2) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              533,
              "ParseCommandLine",
              "Restart count can not be passed when in user console mode\n");
          v9 = 0;
        }
        if ( *((_DWORD *)a6 + 3) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              539,
              "ParseCommandLine",
              "Idle time can not be passed when in user console mode\n");
          v9 = 0;
        }
        v70 = *((_QWORD *)a6 + 8);
        if ( *v35 )
        {
          if ( v70 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                550,
                "ParseCommandLine",
                "App host file cannot be provided when using -debug or -u switch\n");
LABEL_172:
            v9 = 0;
          }
        }
        else if ( !v70 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              558,
              "ParseCommandLine",
              "Missing app host file when in user console mode\n");
LABEL_178:
          v9 = 0;
          break;
        }
      }
      if ( v9 )
        return v9;
      break;
    }
  }
  PrintUsage(*a2);
  return v9;
}

```

## disassembly

```asm
0x140002c58  mov     rax, rsp
0x140002c5b  mov     [rax+10h], rbx
0x140002c5f  mov     [rax+20h], r9
0x140002c63  mov     [rax+18h], r8
0x140002c67  mov     [rax+8], ecx
0x140002c6a  push    rbp
0x140002c6b  push    rsi
0x140002c6c  push    rdi
0x140002c6d  push    r12
0x140002c6f  push    r13
0x140002c71  push    r14
0x140002c73  push    r15
0x140002c75  sub     rsp, 30h
0x140002c79  xor     r10d, r10d
0x140002c7c  mov     r13, rdx
0x140002c7f  mov     [r8], r10d
0x140002c82  cmp     ecx, 2
0x140002c85  jge     short loc_140002CD4
0x140002c87  lea     edi, [r10+3]
0x140002c8b  test    byte ptr cs:g_dwDebugFlags, dil
0x140002c92  jz      short loc_140002CC4
0x140002c94  mov     [rax-40h], ecx
0x140002c97  lea     r9, aParsecommandli; "ParseCommandLine"
0x140002c9e  mov     rcx, cs:g_pDebug
0x140002ca5  lea     rax, aInvalidNumberO; "Invalid number of parameters (%d)\n"
0x140002cac  mov     r8d, 83h
0x140002cb2  mov     [rsp+68h+var_48], rax
0x140002cb7  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140002cbe  call    cs:__imp_PuDbgPrint
0x140002cc4  mov     rcx, [r13+0]
0x140002cc8  call    PrintUsage
0x140002ccd  xor     eax, eax
0x140002ccf  jmp     loc_14000375F
0x140002cd4  mov     r12, [rsp+68h+arg_28]
0x140002cdc  lea     rsi, aParsecommandli; "ParseCommandLine"
0x140002ce3  mov     edi, 1
0x140002ce8  lea     rbp, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140002cef  mov     r15d, edi
0x140002cf2  lea     r11, aInvalidArgumen; "invalid argument %S\n"
0x140002cf9  mov     ebx, edi
0x140002cfb  lea     edi, [r15+2]
0x140002cff  test    ebx, ebx
0x140002d01  jz      loc_140003754
0x140002d07  movsxd  r14, r15d
0x140002d0a  mov     ecx, 0FFFDh
0x140002d0f  mov     rdx, [r13+r14*8+0]
0x140002d14  movzx   eax, word ptr [rdx]
0x140002d17  sub     ax, 2Dh ; '-'
0x140002d1b  test    cx, ax
0x140002d1e  jnz     loc_140003751
0x140002d24  lea     r8, [rdx+2]
0x140002d28  movsxd  r9, r15d
0x140002d2b  movzx   ecx, word ptr [r8]
0x140002d2f  cmp     ecx, 57h ; 'W'
0x140002d32  ja      loc_140002E21
0x140002d38  jz      loc_140003225
0x140002d3e  cmp     ecx, 4Ch ; 'L'
0x140002d41  ja      short loc_140002DBA
0x140002d43  jz      loc_140002E6D
0x140002d49  sub     ecx, 3Fh ; '?'
0x140002d4c  jz      loc_140002FC1
0x140002d52  sub     ecx, 2
0x140002d55  jz      loc_140003134
0x140002d5b  sub     ecx, 2
0x140002d5e  jz      loc_140003108
0x140002d64  sub     ecx, 1
0x140002d67  jz      loc_14000309B
0x140002d6d  sub     ecx, edi
0x140002d6f  jz      loc_140002FF5
0x140002d75  sub     ecx, 1
0x140002d78  jz      loc_140002FC9
0x140002d7e  cmp     ecx, 1
0x140002d81  jnz     loc_140002FC1
0x140002d87  movzx   eax, word ptr [rdx+4]
0x140002d8b  mov     ecx, 0FFDFh
0x140002d90  sub     ax, 4Eh ; 'N'
0x140002d94  test    cx, ax
0x140002d97  jnz     loc_140002F80
0x140002d9d  cmp     r10w, [rdx+6]
0x140002da2  jnz     loc_140002F80
0x140002da8  mov     rcx, [r13+r9*8+8]
0x140002dad  inc     r15d
0x140002db0  mov     [r12+50h], rcx
0x140002db5  jmp     loc_140002EB0
0x140002dba  sub     ecx, 4Dh ; 'M'
0x140002dbd  jz      loc_1400031A9
0x140002dc3  sub     ecx, 2
0x140002dc6  jz      loc_140003546
0x140002dcc  sub     ecx, edi
0x140002dce  jz      loc_1400034AF
0x140002dd4  sub     ecx, 1
0x140002dd7  jz      loc_140003418
0x140002ddd  sub     ecx, 1
0x140002de0  jz      loc_14000327E
0x140002de6  sub     ecx, 1
0x140002de9  jz      loc_140003251
0x140002def  cmp     ecx, 1
0x140002df2  jnz     loc_140002FC1
0x140002df8  mov     rcx, [r13+r9*8+8]
0x140002dfd  inc     r15d
0x140002e00  test    byte ptr cs:g_dwDebugFlags, dil
0x140002e07  mov     [r12+28h], rcx
0x140002e0c  jz      loc_140002EB0
0x140002e12  lea     rax, aClrversionS; "ClrVersion, %S\n"
0x140002e19  mov     r8d, 182h
0x140002e1f  jmp     short loc_140002E90
0x140002e21  cmp     ecx, 6Dh ; 'm'
0x140002e24  ja      loc_1400031EF
0x140002e2a  jz      loc_1400031A9
0x140002e30  sub     ecx, 61h ; 'a'
0x140002e33  jz      loc_140003134
0x140002e39  sub     ecx, 2
0x140002e3c  jz      loc_140003108
0x140002e42  sub     ecx, 1
0x140002e45  jz      loc_14000309B
0x140002e4b  sub     ecx, edi
0x140002e4d  jz      loc_140002FF5
0x140002e53  sub     ecx, 1
0x140002e56  jz      loc_140002FC9
0x140002e5c  sub     ecx, 1
0x140002e5f  jz      loc_140002D87
0x140002e65  cmp     ecx, edi
0x140002e67  jnz     loc_140002FC1
0x140002e6d  mov     rcx, [r13+r9*8+8]
0x140002e72  inc     r15d
0x140002e75  test    byte ptr cs:g_dwDebugFlags, dil
0x140002e7c  mov     [r12+68h], rcx
0x140002e81  jz      short loc_140002EB0
0x140002e83  lea     rax, aClrloaderS; "ClrLoader, %S\n"
0x140002e8a  mov     r8d, 18Fh
0x140002e90  mov     [rsp+68h+var_40], rcx
0x140002e95  mov     rcx, cs:g_pDebug
0x140002e9c  mov     r9, rsi
0x140002e9f  mov     rdx, rbp
0x140002ea2  mov     [rsp+68h+var_48], rax
0x140002ea7  call    cs:__imp_PuDbgPrint
0x140002ead  xor     r10d, r10d
0x140002eb0  mov     r14, [rsp+68h+arg_10]
0x140002eb8  inc     r15d
0x140002ebb  lea     r11, aInvalidArgumen; "invalid argument %S\n"
0x140002ec2  cmp     r15d, [rsp+68h+arg_0]
0x140002ec7  jl      loc_140002CFF
0x140002ecd  test    ebx, ebx
0x140002ecf  jz      loc_140003754
0x140002ed5  mov     rax, [r12+18h]
0x140002eda  cmp     [r12], r10
0x140002ede  jz      loc_1400035E8
0x140002ee4  test    rax, rax
0x140002ee7  jnz     short loc_140002F1D
0x140002ee9  test    byte ptr cs:g_dwDebugFlags, dil
0x140002ef0  jz      short loc_140002F1A
0x140002ef2  mov     rcx, cs:g_pDebug
0x140002ef9  lea     rax, aNoAppPoolWasPa; "No app pool was passed and not in user "...
0x140002f00  mov     r9, rsi
0x140002f03  mov     [rsp+68h+var_48], rax
0x140002f08  mov     r8d, 1F1h
0x140002f0e  mov     rdx, rbp
0x140002f11  call    cs:__imp_PuDbgPrint
0x140002f17  xor     r10d, r10d
0x140002f1a  mov     ebx, r10d
0x140002f1d  cmp     [r14], r10d
0x140002f20  jz      short loc_140002F56
0x140002f22  test    byte ptr cs:g_dwDebugFlags, dil
0x140002f29  jz      short loc_140002F53
0x140002f2b  mov     rcx, cs:g_pDebug
0x140002f32  lea     rax, aPipelineIdCann; "Pipeline id cannot be passed when not i"...
0x140002f39  mov     r9, rsi
0x140002f3c  mov     [rsp+68h+var_48], rax
0x140002f41  mov     r8d, 1F8h
0x140002f47  mov     rdx, rbp
0x140002f4a  call    cs:__imp_PuDbgPrint
0x140002f50  xor     r10d, r10d
0x140002f53  mov     ebx, r10d
0x140002f56  cmp     [r12+5Ch], r10d
0x140002f5b  jz      loc_140003715
0x140002f61  test    byte ptr cs:g_dwDebugFlags, dil
0x140002f68  jz      loc_140003712
0x140002f6e  lea     rax, aSiteIdCannotBe; "Site id cannot be passed when not in us"...
0x140002f75  mov     r8d, 1FDh
0x140002f7b  jmp     loc_1400036F7
0x140002f80  cmp     r10w, [rdx+4]
0x140002f85  jz      loc_140002EB0
0x140002f8b  test    byte ptr cs:g_dwDebugFlags, dil
0x140002f92  jz      short loc_140002FC1
0x140002f94  mov     r8d, 109h
0x140002f9a  lea     rax, aInvalidParamet; "invalid parameter passed in '%S' \n"
0x140002fa1  mov     [rsp+68h+var_40], rdx
0x140002fa6  mov     [rsp+68h+var_48], rax
0x140002fab  mov     rcx, cs:g_pDebug
0x140002fb2  mov     r9, rsi
0x140002fb5  mov     rdx, rbp
0x140002fb8  call    cs:__imp_PuDbgPrint
0x140002fbe  xor     r10d, r10d
0x140002fc1  mov     ebx, r10d
0x140002fc4  jmp     loc_140002EB0
0x140002fc9  mov     rcx, [r13+r9*8+8]
0x140002fce  inc     r15d
0x140002fd1  test    byte ptr cs:g_dwDebugFlags, dil
0x140002fd8  mov     [r12+40h], rcx
0x140002fdd  jz      loc_140002EB0
0x140002fe3  lea     rax, aApplicationHos; "Application Host File, %S\n"
0x140002fea  mov     r8d, 169h
0x140002ff0  jmp     loc_140002E90
0x140002ff5  cmp     [rdx+4], r10w
0x140002ffa  jz      short loc_140003017
0x140002ffc  test    byte ptr cs:g_dwDebugFlags, dil
0x140003003  jz      short loc_140002FC1
0x140003005  mov     [rsp+68h+var_40], rdx
0x14000300a  mov     r8d, 0BCh
0x140003010  mov     [rsp+68h+var_48], r11
0x140003015  jmp     short loc_140002FAB
0x140003017  mov     rcx, [r13+r9*8+8]; String1
0x14000301c  lea     rdx, aTrue; "true"
0x140003023  inc     r15d
0x140003026  mov     r14, r9
0x140003029  call    cs:__imp__wcsicmp
0x14000302f  xor     r10d, r10d
0x140003032  test    eax, eax
0x140003034  jnz     short loc_140003049
0x140003036  mov     rax, [rsp+68h+arg_18]
0x14000303e  mov     dword ptr [rax], 1
0x140003044  jmp     loc_140002EB0
0x140003049  mov     rcx, [r13+r14*8+8]; String1
0x14000304e  lea     rdx, aFalse; "false"
0x140003055  call    cs:__imp__wcsicmp
0x14000305b  xor     r10d, r10d
0x14000305e  test    eax, eax
0x140003060  jnz     short loc_140003072
0x140003062  mov     rax, [rsp+68h+arg_18]
0x14000306a  mov     [rax], r10d
0x14000306d  jmp     loc_140002EB0
0x140003072  test    byte ptr cs:g_dwDebugFlags, dil
0x140003079  jz      loc_140002FC1
0x14000307f  mov     rax, [r13+r14*8+8]
0x140003084  mov     r8d, 0CCh
0x14000308a  mov     [rsp+68h+var_40], rax
0x14000308f  lea     rax, aInvalidArgumen; "invalid argument %S\n"
0x140003096  jmp     loc_140002FA6
0x14000309b  lea     rdx, aDebug; "debug"
0x1400030a2  mov     rcx, r8; String1
0x1400030a5  call    cs:__imp__wcsicmp
0x1400030ab  xor     r10d, r10d
0x1400030ae  test    eax, eax
0x1400030b0  jnz     short loc_1400030D4
0x1400030b2  mov     rax, [rsp+68h+arg_18]
0x1400030ba  mov     dword ptr [rax], 1
0x1400030c0  mov     r14, [rsp+68h+arg_10]
0x1400030c8  mov     dword ptr [r14], 1
0x1400030cf  jmp     loc_140002EB8
0x1400030d4  mov     rax, [r13+r14*8+0]
0x1400030d9  cmp     [rax+4], r10w
0x1400030de  jz      loc_140002EB0
0x1400030e4  test    byte ptr cs:g_dwDebugFlags, dil
0x1400030eb  jz      loc_140002FC1
0x1400030f1  mov     [rsp+68h+var_40], rax
0x1400030f6  mov     r8d, 0B3h
0x1400030fc  lea     rax, aInvalidArgumen; "invalid argument %S\n"
0x140003103  jmp     loc_140002FA6
0x140003108  mov     rcx, [r13+r9*8+8]
0x14000310d  inc     r15d
0x140003110  test    byte ptr cs:g_dwDebugFlags, dil
0x140003117  mov     [r12+30h], rcx
0x14000311c  jz      loc_140002EB0
0x140003122  lea     rax, aClrconfigfileS; "ClrConfigFile, %S\n"
0x140003129  mov     r8d, 19Bh
0x14000312f  jmp     loc_140002E90
0x140003134  movzx   eax, word ptr [rdx+4]
0x140003138  mov     ecx, 0FFDFh
0x14000313d  sub     ax, 50h ; 'P'
0x140003141  test    cx, ax
0x140003144  jnz     short loc_14000315F
0x140003146  cmp     r10w, [rdx+6]
0x14000314b  jnz     short loc_14000315F
0x14000314d  mov     rcx, [r13+r9*8+8]
0x140003152  inc     r15d
0x140003155  mov     [r12+18h], rcx
0x14000315a  jmp     loc_140002EB0
0x14000315f  cmp     r10w, [rdx+4]
0x140003164  jz      short loc_14000317E
0x140003166  test    byte ptr cs:g_dwDebugFlags, dil
0x14000316d  jz      loc_140002FC1
0x140003173  mov     r8d, 0EDh
0x140003179  jmp     loc_140002F9A
0x14000317e  mov     rcx, [r13+r9*8+8]
0x140003183  inc     r15d
0x140003186  test    byte ptr cs:g_dwDebugFlags, dil
0x14000318d  mov     [r12], rcx
0x140003191  jz      loc_140002EB0
0x140003197  lea     rax, aNamedpipeIdS; "NamedPipe Id, %S\n"
0x14000319e  mov     r8d, 0F7h
0x1400031a4  jmp     loc_140002E90
0x1400031a9  cmp     [rdx+4], r10w
0x1400031ae  jz      short loc_1400031D2
0x1400031b0  test    byte ptr cs:g_dwDebugFlags, dil
0x1400031b7  jz      loc_140002FC1
0x1400031bd  mov     [rsp+68h+var_40], rdx
0x1400031c2  mov     r8d, 1A5h
0x1400031c8  mov     [rsp+68h+var_48], r11
0x1400031cd  jmp     loc_140002FAB
0x1400031d2  mov     rcx, [r13+r9*8+8]; String
  ... truncated ...
```
