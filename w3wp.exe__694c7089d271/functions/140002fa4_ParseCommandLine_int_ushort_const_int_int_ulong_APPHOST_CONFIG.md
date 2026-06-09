# ParseCommandLine(int,ushort * * const,int *,int *,ulong *,APPHOST_CONFIG *)

- ea: `0x140002fa4`
- end: `0x140003b45`
- name: `?ParseCommandLine@@YAHHQEAPEAGPEAH1PEAKPEAUAPPHOST_CONFIG@@@Z`
- size: `2977`
- prototype: `__int64 __fastcall(int, unsigned __int16 **const, int *, int *, unsigned int *, struct APPHOST_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x140002fa4`
- `0x140003b4c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140003393`
- `msvcrt!_wcsicmp` at `0x1400033c5`
- `msvcrt!_wcsicmp` at `0x14000341b`
- `msvcrt!_wcsicmp` at `0x140003921`
- `msvcrt!_wcsicmp` at `0x14000394e`
- `msvcrt!_wcsicmp` at `0x140003393`
- `msvcrt!_wcsicmp` at `0x1400033c5`
- `msvcrt!_wcsicmp` at `0x14000341b`
- `msvcrt!_wcsicmp` at `0x140003921`
- `msvcrt!_wcsicmp` at `0x14000394e`
- `msvcrt!wcstoul` at `0x14000355b`
- `msvcrt!wcstoul` at `0x14000362a`
- `msvcrt!wcstoul` at `0x1400036ac`
- `msvcrt!wcstoul` at `0x140003748`
- `msvcrt!wcstoul` at `0x1400037e5`
- `msvcrt!wcstoul` at `0x140003882`
- `msvcrt!wcstoul` at `0x14000355b`
- `msvcrt!wcstoul` at `0x14000362a`
- `msvcrt!wcstoul` at `0x1400036ac`
- `msvcrt!wcstoul` at `0x140003748`
- `msvcrt!wcstoul` at `0x1400037e5`
- `msvcrt!wcstoul` at `0x140003882`
- `iisutil!PuDbgPrint` at `0x14000300a`
- `iisutil!PuDbgPrint` at `0x1400031f9`
- `iisutil!PuDbgPrint` at `0x140003269`
- `iisutil!PuDbgPrint` at `0x1400032a8`
- `iisutil!PuDbgPrint` at `0x14000331c`
- `iisutil!PuDbgPrint` at `0x1400039c1`
- `iisutil!PuDbgPrint` at `0x140003a02`
- `iisutil!PuDbgPrint` at `0x140003a43`
- `iisutil!PuDbgPrint` at `0x140003a84`
- `iisutil!PuDbgPrint` at `0x140003acd`
- `iisutil!PuDbgPrint` at `0x140003b12`
- `iisutil!PuDbgPrint` at `0x14000300a`
- `iisutil!PuDbgPrint` at `0x1400031f9`
- `iisutil!PuDbgPrint` at `0x140003269`
- `iisutil!PuDbgPrint` at `0x1400032a8`
- `iisutil!PuDbgPrint` at `0x14000331c`
- `iisutil!PuDbgPrint` at `0x1400039c1`
- `iisutil!PuDbgPrint` at `0x140003a02`
- `iisutil!PuDbgPrint` at `0x140003a43`
- `iisutil!PuDbgPrint` at `0x140003a84`
- `iisutil!PuDbgPrint` at `0x140003acd`
- `iisutil!PuDbgPrint` at `0x140003b12`

## string_xrefs

- `0x140002fe3`: `ParseCommandLine`
- `0x14000302e`: `ParseCommandLine`
- `0x140003003`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\parsecommandline.cxx`
- `0x14000303a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\parsecommandline.cxx`
- `0x1400035c1`: `Root Web Config File, %S\n`
- `0x14000349e`: `ClrConfigFile, %S\n`

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
  const char *v28; // rax
  __int64 v29; // r8
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  int *v36; // r14
  __int64 v37; // rax
  const char *v38; // rax
  __int64 v39; // r8
  __int64 v40; // r8
  const wchar_t *v41; // rcx
  __int64 v42; // r14
  unsigned __int16 *v43; // rcx
  const wchar_t *v44; // rcx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned __int16 v51; // cx
  const wchar_t *v52; // rcx
  __int64 v53; // r14
  signed int v54; // eax
  const wchar_t *v55; // rcx
  __int64 v56; // r14
  unsigned int v57; // eax
  const wchar_t *v58; // rcx
  __int64 v59; // r14
  unsigned int v60; // eax
  const wchar_t *v61; // rcx
  __int64 v62; // r14
  unsigned int v63; // eax
  const wchar_t *v64; // rcx
  __int64 v65; // r14
  unsigned int v66; // eax
  const wchar_t *v67; // rcx
  __int64 v68; // r14
  __int64 v69; // rax
  unsigned __int16 *v70; // [rsp+28h] [rbp-40h]

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
      goto LABEL_181;
    v11 = v8;
    v12 = v10[1];
    if ( v12 > 0x57 )
    {
      if ( v12 > 0x6D )
      {
        v45 = v12 - 111;
        if ( !v45 )
          goto LABEL_145;
        v46 = v45 - 3;
        if ( !v46 )
          goto LABEL_137;
        v47 = v46 - 1;
        if ( !v47 )
        {
LABEL_129:
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
            goto LABEL_63;
          }
          v61 = a2[++v8];
          v62 = v11;
          v63 = wcstoul(v61, 0, 0);
          *((_DWORD *)a6 + 23) = v63;
          if ( !v63 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                161,
                "ParseCommandLine",
                "Invalid site id %ws\n",
                a2[v62 + 1]);
            goto LABEL_63;
          }
          if ( (g_dwDebugFlags & 3) == 0 )
            goto LABEL_44;
          LODWORD(v70) = v63;
          v29 = 166;
          v28 = "Site Id is %lu\n";
          goto LABEL_43;
        }
        v48 = v47 - 1;
        if ( !v48 )
          goto LABEL_107;
        v49 = v48 - 1;
        if ( !v49 )
        {
LABEL_104:
          if ( !v10[2] )
            goto LABEL_77;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              214,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v8]);
          goto LABEL_63;
        }
        v50 = v49 - 1;
        if ( v50 )
        {
          if ( v50 != 1 )
            goto LABEL_63;
LABEL_102:
          v26 = a2[++v8];
          v27 = (g_dwDebugFlags & 3) == 0;
          *((_QWORD *)a6 + 9) = v26;
          if ( v27 )
            goto LABEL_44;
          v28 = "Root Web Config File, %S\n";
          v29 = 373;
LABEL_42:
          v70 = v26;
LABEL_43:
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
            v29,
            "ParseCommandLine",
            v28,
            v70);
          goto LABEL_44;
        }
        goto LABEL_29;
      }
      if ( v12 == 109 )
      {
LABEL_91:
        if ( !v10[2] )
        {
          v44 = a2[++v8];
          *((_DWORD *)a6 + 14) = wcstoul(v44, 0, 0);
          goto LABEL_44;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
            421,
            "ParseCommandLine",
            "invalid argument %S\n",
            a2[v8]);
        goto LABEL_63;
      }
      v30 = v12 - 97;
      if ( !v30 )
      {
LABEL_83:
        if ( ((v10[2] - 80) & 0xFFDF) == 0 && !v10[3] )
        {
          v43 = a2[++v8];
          *((_QWORD *)a6 + 3) = v43;
          goto LABEL_44;
        }
        if ( v10[2] )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v40 = 237;
LABEL_62:
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              v40,
              "ParseCommandLine",
              "invalid parameter passed in '%S' \n",
              a2[v8]);
          }
LABEL_63:
          v9 = 0;
          goto LABEL_44;
        }
        v26 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *(_QWORD *)a6 = v26;
        if ( v27 )
          goto LABEL_44;
        v28 = "NamedPipe Id, %S\n";
        v29 = 247;
        goto LABEL_42;
      }
      v31 = v30 - 2;
      if ( !v31 )
      {
LABEL_81:
        v26 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *((_QWORD *)a6 + 6) = v26;
        if ( v27 )
          goto LABEL_44;
        v28 = "ClrConfigFile, %S\n";
        v29 = 411;
        goto LABEL_42;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
LABEL_75:
        if ( !_wcsicmp(v10 + 1, L"debug") )
        {
          *a4 = 1;
LABEL_77:
          v36 = a3;
          *a3 = 1;
          goto LABEL_45;
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
          goto LABEL_63;
        }
        goto LABEL_44;
      }
      v33 = v32 - 3;
      if ( !v33 )
      {
LABEL_66:
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
          v41 = a2[++v8];
          v42 = v11;
          if ( !_wcsicmp(v41, L"true") )
          {
            *a4 = 1;
            goto LABEL_44;
          }
          if ( !_wcsicmp(a2[v42 + 1], L"false") )
          {
            *a4 = 0;
            goto LABEL_44;
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              204,
              "ParseCommandLine",
              "invalid argument %S\n",
              a2[v42 + 1]);
        }
        goto LABEL_63;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
LABEL_64:
        v26 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *((_QWORD *)a6 + 8) = v26;
        if ( v27 )
          goto LABEL_44;
        v28 = "Application Host File, %S\n";
        v29 = 361;
        goto LABEL_42;
      }
      v35 = v34 - 1;
      if ( !v35 )
        goto LABEL_19;
      if ( v35 != 3 )
        goto LABEL_63;
    }
    else
    {
      if ( v12 == 87 )
        goto LABEL_102;
      if ( v12 > 0x4C )
      {
        v20 = v12 - 77;
        if ( !v20 )
          goto LABEL_91;
        v21 = v20 - 2;
        if ( !v21 )
        {
LABEL_145:
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
            v67 = a2[++v8];
            v68 = v11;
            if ( !_wcsicmp(v67, L"enable") )
            {
              *((_DWORD *)a6 + 24) = 1;
              goto LABEL_44;
            }
            if ( !_wcsicmp(a2[v68 + 1], L"disable") )
            {
              *((_DWORD *)a6 + 24) = 0;
              goto LABEL_44;
            }
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                460,
                "ParseCommandLine",
                "invalid argument %S\n",
                a2[v68 + 1]);
          }
          goto LABEL_63;
        }
        v22 = v21 - 3;
        if ( !v22 )
        {
LABEL_137:
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
            goto LABEL_63;
          }
          v64 = a2[++v8];
          v65 = v11;
          v66 = wcstoul(v64, 0, 0);
          *((_DWORD *)a6 + 2) = v66;
          if ( !v66 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                283,
                "ParseCommandLine",
                "Invalid maximum requests %ws\n",
                a2[v65 + 1]);
            goto LABEL_63;
          }
          if ( (g_dwDebugFlags & 3) == 0 )
            goto LABEL_44;
          LODWORD(v70) = v66;
          v29 = 288;
          v28 = "Maximum requests is %lu\n";
          goto LABEL_43;
        }
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_129;
        v24 = v23 - 1;
        if ( !v24 )
        {
LABEL_107:
          v51 = v10[2];
          if ( ((v51 - 65) & 0xFFDF) != 0 || v10[3] )
          {
            if ( ((v51 - 84) & 0xFFDF) != 0 || v10[3] )
            {
              if ( v51 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    334,
                    "ParseCommandLine",
                    "invalid argument %S\n",
                    a2[v8]);
                goto LABEL_63;
              }
              v58 = a2[++v8];
              v59 = v11;
              v60 = wcstoul(v58, 0, 0);
              *((_DWORD *)a6 + 3) = v60;
              if ( !v60 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    343,
                    "ParseCommandLine",
                    "Invalid idle time %ws\n",
                    a2[v59 + 1]);
                goto LABEL_63;
              }
              if ( (g_dwDebugFlags & 3) == 0 )
                goto LABEL_44;
              LODWORD(v70) = v60;
              v29 = 348;
              v28 = "The idle time value is %lu\n";
            }
            else
            {
              v55 = a2[++v8];
              v56 = v11;
              v57 = wcstoul(v55, 0, 0);
              g_dwShutDownTimeout = v57;
              if ( !v57 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                    324,
                    "ParseCommandLine",
                    "Invalid shutdown timeout value %ws\n",
                    a2[v56 + 1]);
                goto LABEL_63;
              }
              if ( (g_dwDebugFlags & 3) == 0 )
                goto LABEL_44;
              LODWORD(v70) = v57;
              v29 = 329;
              v28 = "The shutdown timeout value is %lu\n";
            }
          }
          else
          {
            v52 = a2[++v8];
            v53 = v11;
            v54 = wcstoul(v52, 0, 0);
            *((_DWORD *)a6 + 4) = v54;
            if ( v54 > 1 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                  306,
                  "ParseCommandLine",
                  "Invalid idle timeout action %ws\n",
                  a2[v53 + 1]);
              goto LABEL_63;
            }
            if ( (g_dwDebugFlags & 3) == 0 )
              goto LABEL_44;
            LODWORD(v70) = v54;
            v29 = 311;
            v28 = "The idle timeout action is %lu\n";
          }
          goto LABEL_43;
        }
        v25 = v24 - 1;
        if ( !v25 )
          goto LABEL_104;
        if ( v25 != 1 )
          goto LABEL_63;
LABEL_29:
        v26 = a2[++v8];
        v27 = (g_dwDebugFlags & 3) == 0;
        *((_QWORD *)a6 + 5) = v26;
        if ( !v27 )
        {
          v28 = "ClrVersion, %S\n";
          v29 = 386;
          goto LABEL_42;
        }
        goto LABEL_44;
      }
      if ( v12 != 76 )
      {
        v13 = v12 - 63;
        if ( !v13 )
          goto LABEL_63;
        v14 = v13 - 2;
        if ( !v14 )
          goto LABEL_83;
        v15 = v14 - 2;
        if ( !v15 )
          goto LABEL_81;
        v16 = v15 - 1;
        if ( !v16 )
          goto LABEL_75;
        v17 = v16 - 3;
        if ( !v17 )
          goto LABEL_66;
        v18 = v17 - 1;
        if ( !v18 )
          goto LABEL_64;
        if ( v18 != 1 )
          goto LABEL_63;
LABEL_19:
        if ( ((v10[2] - 78) & 0xFFDF) != 0 || v10[3] )
        {
          if ( v10[2] )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              v40 = 265;
              goto LABEL_62;
            }
            goto LABEL_63;
          }
        }
        else
        {
          v19 = a2[++v8];
          *((_QWORD *)a6 + 10) = v19;
        }
        goto LABEL_44;
      }
    }
    v26 = a2[++v8];
    v27 = (g_dwDebugFlags & 3) == 0;
    *((_QWORD *)a6 + 13) = v26;
    if ( !v27 )
    {
      v28 = "ClrLoader, %S\n";
      v29 = 399;
      goto LABEL_42;
    }
LABEL_44:
    v36 = a3;
LABEL_45:
    if ( ++v8 >= a1 )
    {
      if ( !v9 )
        break;
      v37 = *((_QWORD *)a6 + 3);
      if ( *(_QWORD *)a6 )
      {
        if ( !v37 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              497,
              "ParseCommandLine",
              "No app pool was passed and not in user console mode\n",
              v70);
          v9 = 0;
        }
        if ( *v36 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              504,
              "ParseCommandLine",
              "Pipeline id cannot be passed when not in user console mode\n",
              v70);
          v9 = 0;
        }
        if ( *((_DWORD *)a6 + 23) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v38 = "Site id cannot be passed when not in user console mode\n";
            v39 = 509;
            goto LABEL_174;
          }
          goto LABEL_175;
        }
      }
      else
      {
        if ( v37 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              519,
              "ParseCommandLine",
              "App pool was passed and in user console mode\n",
              v70);
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
              "Managed pipeline mode can not be passed when in user console mode\n",
              v70);
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
              "Restart count can not be passed when in user console mode\n",
              v70);
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
              "Idle time can not be passed when in user console mode\n",
              v70);
          v9 = 0;
        }
        v69 = *((_QWORD *)a6 + 8);
        if ( *v36 )
        {
          if ( v69 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              v38 = "App host file cannot be provided when using -debug or -u switch\n";
              v39 = 550;
LABEL_174:
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
                v39,
                "ParseCommandLine",
                v38,
                v70);
            }
LABEL_175:
            v9 = 0;
          }
        }
        else if ( !v69 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\parsecommandline.cxx",
              558,
              "ParseCommandLine",
              "Missing app host file when in user console mode\n",
              v70);
LABEL_181:
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
0x140002fa4  mov     rax, rsp
0x140002fa7  mov     [rax+10h], rbx
0x140002fab  mov     [rax+20h], r9
0x140002faf  mov     [rax+18h], r8
0x140002fb3  mov     [rax+8], ecx
0x140002fb6  push    rbp
0x140002fb7  push    rsi
0x140002fb8  push    rdi
0x140002fb9  push    r12
0x140002fbb  push    r13
0x140002fbd  push    r14
0x140002fbf  push    r15
0x140002fc1  sub     rsp, 30h
0x140002fc5  xor     r10d, r10d
0x140002fc8  mov     r13, rdx
0x140002fcb  mov     [r8], r10d
0x140002fce  cmp     ecx, 2
0x140002fd1  jge     short loc_140003026
0x140002fd3  lea     edi, [r10+3]
0x140002fd7  test    byte ptr cs:g_dwDebugFlags, dil
0x140002fde  jz      short loc_140003016
0x140002fe0  mov     [rax-40h], ecx
0x140002fe3  lea     r9, aParsecommandli; "ParseCommandLine"
0x140002fea  mov     rcx, cs:g_pDebug
0x140002ff1  lea     rax, aInvalidNumberO; "Invalid number of parameters (%d)\n"
0x140002ff8  mov     r8d, 83h
0x140002ffe  mov     [rsp+68h+var_48], rax
0x140003003  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x14000300a  call    cs:__imp_PuDbgPrint
0x140003011  nop     dword ptr [rax+rax+00h]
0x140003016  mov     rcx, [r13+0]
0x14000301a  call    PrintUsage
0x14000301f  xor     eax, eax
0x140003021  jmp     loc_140003B2F
0x140003026  mov     r12, [rsp+68h+arg_28]
0x14000302e  lea     rsi, aParsecommandli; "ParseCommandLine"
0x140003035  mov     edi, 1
0x14000303a  lea     rbp, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140003041  mov     r15d, edi
0x140003044  lea     r11, aInvalidArgumen; "invalid argument %S\n"
0x14000304b  mov     ebx, edi
0x14000304d  lea     edi, [r15+2]
0x140003051  test    ebx, ebx
0x140003053  jz      loc_140003B24
0x140003059  movsxd  r14, r15d
0x14000305c  mov     ecx, 0FFFDh
0x140003061  mov     rdx, [r13+r14*8+0]
0x140003066  movzx   eax, word ptr [rdx]
0x140003069  sub     ax, 2Dh ; '-'
0x14000306d  test    cx, ax
0x140003070  jnz     loc_140003B21
0x140003076  lea     r8, [rdx+2]
0x14000307a  movsxd  r9, r15d
0x14000307d  movzx   ecx, word ptr [r8]
0x140003081  cmp     ecx, 57h ; 'W'
0x140003084  ja      loc_140003173
0x14000308a  jz      loc_1400035A7
0x140003090  cmp     ecx, 4Ch ; 'L'
0x140003093  ja      short loc_14000310C
0x140003095  jz      loc_1400031BF
0x14000309b  sub     ecx, 3Fh ; '?'
0x14000309e  jz      loc_14000332B
0x1400030a4  sub     ecx, 2
0x1400030a7  jz      loc_1400034B0
0x1400030ad  sub     ecx, 2
0x1400030b0  jz      loc_140003484
0x1400030b6  sub     ecx, 1
0x1400030b9  jz      loc_140003411
0x1400030bf  sub     ecx, edi
0x1400030c1  jz      loc_14000335F
0x1400030c7  sub     ecx, 1
0x1400030ca  jz      loc_140003333
0x1400030d0  cmp     ecx, 1
0x1400030d3  jnz     loc_14000332B
0x1400030d9  movzx   eax, word ptr [rdx+4]
0x1400030dd  mov     ecx, 0FFDFh
0x1400030e2  sub     ax, 4Eh ; 'N'
0x1400030e6  test    cx, ax
0x1400030e9  jnz     loc_1400032E4
0x1400030ef  cmp     r10w, [rdx+6]
0x1400030f4  jnz     loc_1400032E4
0x1400030fa  mov     rcx, [r13+r9*8+8]
0x1400030ff  inc     r15d
0x140003102  mov     [r12+50h], rcx
0x140003107  jmp     loc_140003208
0x14000310c  sub     ecx, 4Dh ; 'M'
0x14000310f  jz      loc_140003525
0x140003115  sub     ecx, 2
0x140003118  jz      loc_1400038E6
0x14000311e  sub     ecx, edi
0x140003120  jz      loc_140003849
0x140003126  sub     ecx, 1
0x140003129  jz      loc_1400037AC
0x14000312f  sub     ecx, 1
0x140003132  jz      loc_140003600
0x140003138  sub     ecx, 1
0x14000313b  jz      loc_1400035D3
0x140003141  cmp     ecx, 1
0x140003144  jnz     loc_14000332B
0x14000314a  mov     rcx, [r13+r9*8+8]
0x14000314f  inc     r15d
0x140003152  test    byte ptr cs:g_dwDebugFlags, dil
0x140003159  mov     [r12+28h], rcx
0x14000315e  jz      loc_140003208
0x140003164  lea     rax, aClrversionS; "ClrVersion, %S\n"
0x14000316b  mov     r8d, 182h
0x140003171  jmp     short loc_1400031E2
0x140003173  cmp     ecx, 6Dh ; 'm'
0x140003176  ja      loc_140003571
0x14000317c  jz      loc_140003525
0x140003182  sub     ecx, 61h ; 'a'
0x140003185  jz      loc_1400034B0
0x14000318b  sub     ecx, 2
0x14000318e  jz      loc_140003484
0x140003194  sub     ecx, 1
0x140003197  jz      loc_140003411
0x14000319d  sub     ecx, edi
0x14000319f  jz      loc_14000335F
0x1400031a5  sub     ecx, 1
0x1400031a8  jz      loc_140003333
0x1400031ae  sub     ecx, 1
0x1400031b1  jz      loc_1400030D9
0x1400031b7  cmp     ecx, edi
0x1400031b9  jnz     loc_14000332B
0x1400031bf  mov     rcx, [r13+r9*8+8]
0x1400031c4  inc     r15d
0x1400031c7  test    byte ptr cs:g_dwDebugFlags, dil
0x1400031ce  mov     [r12+68h], rcx
0x1400031d3  jz      short loc_140003208
0x1400031d5  lea     rax, aClrloaderS; "ClrLoader, %S\n"
0x1400031dc  mov     r8d, 18Fh
0x1400031e2  mov     [rsp+68h+var_40], rcx
0x1400031e7  mov     rcx, cs:g_pDebug
0x1400031ee  mov     r9, rsi
0x1400031f1  mov     rdx, rbp
0x1400031f4  mov     [rsp+68h+var_48], rax
0x1400031f9  call    cs:__imp_PuDbgPrint
0x140003200  nop     dword ptr [rax+rax+00h]
0x140003205  xor     r10d, r10d
0x140003208  mov     r14, [rsp+68h+arg_10]
0x140003210  inc     r15d
0x140003213  lea     r11, aInvalidArgumen; "invalid argument %S\n"
0x14000321a  cmp     r15d, [rsp+68h+arg_0]
0x14000321f  jl      loc_140003051
0x140003225  test    ebx, ebx
0x140003227  jz      loc_140003B24
0x14000322d  mov     rax, [r12+18h]
0x140003232  cmp     [r12], r10
0x140003236  jz      loc_140003994
0x14000323c  test    rax, rax
0x14000323f  jnz     short loc_14000327B
0x140003241  test    byte ptr cs:g_dwDebugFlags, dil
0x140003248  jz      short loc_140003278
0x14000324a  mov     rcx, cs:g_pDebug
0x140003251  lea     rax, aNoAppPoolWasPa; "No app pool was passed and not in user "...
0x140003258  mov     r9, rsi
0x14000325b  mov     [rsp+68h+var_48], rax
0x140003260  mov     r8d, 1F1h
0x140003266  mov     rdx, rbp
0x140003269  call    cs:__imp_PuDbgPrint
0x140003270  nop     dword ptr [rax+rax+00h]
0x140003275  xor     r10d, r10d
0x140003278  mov     ebx, r10d
0x14000327b  cmp     [r14], r10d
0x14000327e  jz      short loc_1400032BA
0x140003280  test    byte ptr cs:g_dwDebugFlags, dil
0x140003287  jz      short loc_1400032B7
0x140003289  mov     rcx, cs:g_pDebug
0x140003290  lea     rax, aPipelineIdCann; "Pipeline id cannot be passed when not i"...
0x140003297  mov     r9, rsi
0x14000329a  mov     [rsp+68h+var_48], rax
0x14000329f  mov     r8d, 1F8h
0x1400032a5  mov     rdx, rbp
0x1400032a8  call    cs:__imp_PuDbgPrint
0x1400032af  nop     dword ptr [rax+rax+00h]
0x1400032b4  xor     r10d, r10d
0x1400032b7  mov     ebx, r10d
0x1400032ba  cmp     [r12+5Ch], r10d
0x1400032bf  jz      loc_140003ADF
0x1400032c5  test    byte ptr cs:g_dwDebugFlags, dil
0x1400032cc  jz      loc_140003ADC
0x1400032d2  lea     rax, aSiteIdCannotBe; "Site id cannot be passed when not in us"...
0x1400032d9  mov     r8d, 1FDh
0x1400032df  jmp     loc_140003ABB
0x1400032e4  cmp     r10w, [rdx+4]
0x1400032e9  jz      loc_140003208
0x1400032ef  test    byte ptr cs:g_dwDebugFlags, dil
0x1400032f6  jz      short loc_14000332B
0x1400032f8  mov     r8d, 109h
0x1400032fe  lea     rax, aInvalidParamet; "invalid parameter passed in '%S' \n"
0x140003305  mov     [rsp+68h+var_40], rdx
0x14000330a  mov     [rsp+68h+var_48], rax
0x14000330f  mov     rcx, cs:g_pDebug
0x140003316  mov     r9, rsi
0x140003319  mov     rdx, rbp
0x14000331c  call    cs:__imp_PuDbgPrint
0x140003323  nop     dword ptr [rax+rax+00h]
0x140003328  xor     r10d, r10d
0x14000332b  mov     ebx, r10d
0x14000332e  jmp     loc_140003208
0x140003333  mov     rcx, [r13+r9*8+8]
0x140003338  inc     r15d
0x14000333b  test    byte ptr cs:g_dwDebugFlags, dil
0x140003342  mov     [r12+40h], rcx
0x140003347  jz      loc_140003208
0x14000334d  lea     rax, aApplicationHos; "Application Host File, %S\n"
0x140003354  mov     r8d, 169h
0x14000335a  jmp     loc_1400031E2
0x14000335f  cmp     [rdx+4], r10w
0x140003364  jz      short loc_140003381
0x140003366  test    byte ptr cs:g_dwDebugFlags, dil
0x14000336d  jz      short loc_14000332B
0x14000336f  mov     [rsp+68h+var_40], rdx
0x140003374  mov     r8d, 0BCh
0x14000337a  mov     [rsp+68h+var_48], r11
0x14000337f  jmp     short loc_14000330F
0x140003381  mov     rcx, [r13+r9*8+8]; String1
0x140003386  lea     rdx, aTrue; "true"
0x14000338d  inc     r15d
0x140003390  mov     r14, r9
0x140003393  call    cs:__imp__wcsicmp
0x14000339a  nop     dword ptr [rax+rax+00h]
0x14000339f  xor     r10d, r10d
0x1400033a2  test    eax, eax
0x1400033a4  jnz     short loc_1400033B9
0x1400033a6  mov     rax, [rsp+68h+arg_18]
0x1400033ae  mov     dword ptr [rax], 1
0x1400033b4  jmp     loc_140003208
0x1400033b9  mov     rcx, [r13+r14*8+8]; String1
0x1400033be  lea     rdx, aFalse; "false"
0x1400033c5  call    cs:__imp__wcsicmp
0x1400033cc  nop     dword ptr [rax+rax+00h]
0x1400033d1  xor     r10d, r10d
0x1400033d4  test    eax, eax
0x1400033d6  jnz     short loc_1400033E8
0x1400033d8  mov     rax, [rsp+68h+arg_18]
0x1400033e0  mov     [rax], r10d
0x1400033e3  jmp     loc_140003208
0x1400033e8  test    byte ptr cs:g_dwDebugFlags, dil
0x1400033ef  jz      loc_14000332B
0x1400033f5  mov     rax, [r13+r14*8+8]
0x1400033fa  mov     r8d, 0CCh
0x140003400  mov     [rsp+68h+var_40], rax
0x140003405  lea     rax, aInvalidArgumen; "invalid argument %S\n"
0x14000340c  jmp     loc_14000330A
0x140003411  lea     rdx, aDebug; "debug"
0x140003418  mov     rcx, r8; String1
0x14000341b  call    cs:__imp__wcsicmp
0x140003422  nop     dword ptr [rax+rax+00h]
0x140003427  xor     r10d, r10d
0x14000342a  test    eax, eax
0x14000342c  jnz     short loc_140003450
0x14000342e  mov     rax, [rsp+68h+arg_18]
0x140003436  mov     dword ptr [rax], 1
0x14000343c  mov     r14, [rsp+68h+arg_10]
0x140003444  mov     dword ptr [r14], 1
0x14000344b  jmp     loc_140003210
0x140003450  mov     rax, [r13+r14*8+0]
0x140003455  cmp     [rax+4], r10w
0x14000345a  jz      loc_140003208
0x140003460  test    byte ptr cs:g_dwDebugFlags, dil
0x140003467  jz      loc_14000332B
0x14000346d  mov     [rsp+68h+var_40], rax
0x140003472  mov     r8d, 0B3h
0x140003478  lea     rax, aInvalidArgumen; "invalid argument %S\n"
0x14000347f  jmp     loc_14000330A
0x140003484  mov     rcx, [r13+r9*8+8]
0x140003489  inc     r15d
0x14000348c  test    byte ptr cs:g_dwDebugFlags, dil
0x140003493  mov     [r12+30h], rcx
0x140003498  jz      loc_140003208
0x14000349e  lea     rax, aClrconfigfileS; "ClrConfigFile, %S\n"
0x1400034a5  mov     r8d, 19Bh
0x1400034ab  jmp     loc_1400031E2
0x1400034b0  movzx   eax, word ptr [rdx+4]
0x1400034b4  mov     ecx, 0FFDFh
0x1400034b9  sub     ax, 50h ; 'P'
0x1400034bd  test    cx, ax
0x1400034c0  jnz     short loc_1400034DB
0x1400034c2  cmp     r10w, [rdx+6]
0x1400034c7  jnz     short loc_1400034DB
0x1400034c9  mov     rcx, [r13+r9*8+8]
0x1400034ce  inc     r15d
0x1400034d1  mov     [r12+18h], rcx
0x1400034d6  jmp     loc_140003208
0x1400034db  cmp     r10w, [rdx+4]
0x1400034e0  jz      short loc_1400034FA
0x1400034e2  test    byte ptr cs:g_dwDebugFlags, dil
0x1400034e9  jz      loc_14000332B
0x1400034ef  mov     r8d, 0EDh
0x1400034f5  jmp     loc_1400032FE
0x1400034fa  mov     rcx, [r13+r9*8+8]
0x1400034ff  inc     r15d
0x140003502  test    byte ptr cs:g_dwDebugFlags, dil
0x140003509  mov     [r12], rcx
0x14000350d  jz      loc_140003208
0x140003513  lea     rax, aNamedpipeIdS; "NamedPipe Id, %S\n"
0x14000351a  mov     r8d, 0F7h
0x140003520  jmp     loc_1400031E2
0x140003525  cmp     [rdx+4], r10w
  ... truncated ...
```
