# Names::GetInterestingFileNames(void)

- ea: `0x180016fd8`
- end: `0x1800179e9`
- name: `?GetInterestingFileNames@Names@@SAJXZ`
- size: `2577`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180016c18`

## callees

- `0x180007824`
- `0x180016fd8`
- `0x180017c68`
- `0x180017d90`
- `0x18004d030`
- `0x18004d350`
- `0x18004dbcc`
- `0x18004dc64`
- `0x18004dddc`
- `0x1800653e6`
- `0x1800653f8`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180017538`
- `KERNEL32!WideCharToMultiByte` at `0x180017538`
- `KERNEL32!GetModuleFileNameW` at `0x180017021`
- `KERNEL32!GetModuleFileNameW` at `0x180017021`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017100`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017100`
- `KERNEL32!FindClose` at `0x18001768a`
- `KERNEL32!FindClose` at `0x18001768a`
- `KERNEL32!FindFirstFileW` at `0x18001767b`
- `KERNEL32!FindFirstFileW` at `0x18001767b`

## string_xrefs

- `0x18001789c`: `aspnet_filter.dll`
- `0x18001792b`: `aspnet_filter.dll`
- `0x1800175f8`: `machine.config`
- `0x180017353`: `aspnet_isapi.dll`
- `0x1800173e2`: `aspnet_isapi.dll`
- `0x18001746d`: `System.Web.dll`
- `0x1800174f8`: `config`
- `0x180017560`: `machine.config`
- `0x1800179a7`: `aspnet_perf.dll`

## pseudocode

```c
__int64 Names::GetInterestingFileNames(void)
{
  __int64 result; // rax
  wchar_t *v1; // rax
  wchar_t *v2; // rcx
  __int64 v3; // rdx
  signed __int64 v4; // r8
  wchar_t v5; // ax
  wchar_t *v6; // rax
  __int64 v7; // rsi
  wchar_t *v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 v11; // ax
  unsigned __int16 *v12; // rax
  unsigned __int16 v13; // ax
  unsigned __int16 *v14; // rax
  WCHAR *v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // r8
  unsigned __int16 *v18; // rdx
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned __int16 v22; // ax
  unsigned __int16 *v23; // rax
  wchar_t *v24; // rcx
  __int64 v25; // rdx
  wchar_t v26; // ax
  wchar_t *v27; // rax
  __int64 v28; // rdx
  unsigned __int16 *v29; // rcx
  unsigned __int16 v30; // ax
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rcx
  __int64 v33; // rdx
  unsigned __int16 v34; // ax
  unsigned __int16 *v35; // rax
  WCHAR *v36; // rcx
  __int64 v37; // rdx
  WCHAR v38; // ax
  WCHAR *v39; // rax
  __int64 v40; // rdx
  WCHAR *v41; // rcx
  WCHAR v42; // ax
  WCHAR *v43; // rax
  WCHAR *v44; // rcx
  __int64 v45; // rdx
  WCHAR v46; // ax
  WCHAR *v47; // rax
  HANDLE FirstFileW; // rax
  wchar_t *v49; // rcx
  __int64 v50; // rdx
  wchar_t v51; // ax
  wchar_t *v52; // rax
  unsigned __int16 *v53; // rcx
  __int64 v54; // rdx
  unsigned __int16 v55; // ax
  unsigned __int16 *v56; // rax
  unsigned __int16 *v57; // rcx
  __int64 v58; // rdx
  unsigned __int16 v59; // ax
  unsigned __int16 *v60; // rax
  OLECHAR *v61; // rcx
  __int64 v62; // rdx
  OLECHAR v63; // ax
  OLECHAR *v64; // rax
  __int64 v65; // rdx
  unsigned __int16 *v66; // rcx
  unsigned __int16 v67; // ax
  unsigned __int16 *v68; // rax
  __int64 v69; // r9
  unsigned __int16 *v70; // rcx
  unsigned __int16 v71; // ax
  unsigned __int16 *v72; // rax
  _WIN32_FIND_DATAW FindFileData; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 v74[264]; // [rsp+298h] [rbp+190h] BYREF
  WCHAR FileName[264]; // [rsp+4A8h] [rbp+3A0h] BYREF
  WCHAR Dst[264]; // [rsp+6B8h] [rbp+5B0h] BYREF

  if ( !GetModuleFileNameW(0, &Names::s_wszExeFullPath, 0x104u) )
    return GetLastWin32Error();
  v1 = wcsrchr_0(&Names::s_wszExeFullPath, 0x5Cu);
  if ( !v1 )
    return 2147549183LL;
  v2 = &Names::s_wszExeFileName;
  v3 = 260;
  v4 = (char *)v1 - (char *)&Names::s_wszExeFileName;
  do
  {
    if ( v3 == -2147483386 )
      break;
    v5 = *(wchar_t *)((char *)v2 + v4 + 2);
    if ( !v5 )
      break;
    *v2++ = v5;
    --v3;
  }
  while ( v3 );
  v6 = v2 - 1;
  if ( v3 )
    v6 = v2;
  *v6 = 0;
  result = v3 == 0 ? 0x8007007A : 0;
  if ( v3 )
  {
    result = GetEngineFullPath(&Names::s_wszEngineFullPath, 0x104u);
    if ( !(_DWORD)result )
    {
      result = GetInstallDirectory(&Names::s_wszInstallDirectory, 0x104u);
      if ( !(_DWORD)result )
      {
        v7 = ExpandEnvironmentStringsW(L"%windir%", Dst, 0x104u);
        v8 = wcsstr_0(&Names::s_wszInstallDirectory, Dst);
        v9 = v74;
        v10 = 260;
        if ( v8 == &Names::s_wszInstallDirectory )
        {
          do
          {
            if ( v10 == -2147483386 )
              break;
            v11 = *(unsigned __int16 *)((char *)v9 + (char *)L"%windir%" - (char *)v74);
            if ( !v11 )
              break;
            *v9++ = v11;
            --v10;
          }
          while ( v10 );
          v12 = v9 - 1;
          if ( v10 )
            v12 = v9;
          *v12 = 0;
          result = v10 == 0 ? 0x8007007A : 0;
          if ( !v10 )
            return result;
          result = StringCchCatW(v74, 0x104u, &Names::s_wszInstallDirectory + v7 - 1);
          if ( (_DWORD)result )
            return result;
        }
        else
        {
          do
          {
            if ( v10 == -2147483386 )
              break;
            v13 = *(unsigned __int16 *)((char *)v9 + (char *)&Names::s_wszInstallDirectory - (char *)v74);
            if ( !v13 )
              break;
            *v9++ = v13;
            --v10;
          }
          while ( v10 );
          v14 = v9 - 1;
          if ( v10 )
            v14 = v9;
          *v14 = 0;
          result = v10 == 0 ? 0x8007007A : 0;
          if ( !v10 )
            return result;
        }
        v15 = wcsstr_0(&Names::s_wszEngineFullPath, Dst);
        v16 = &Names::s_wszEngineFullPathWithWindir;
        if ( v15 == &Names::s_wszEngineFullPath )
        {
          v17 = 260;
          v18 = &Names::s_wszEngineFullPathWithWindir;
          do
          {
            if ( v17 == -2147483386 )
              break;
            v19 = *(unsigned __int16 *)((char *)v18 + (char *)L"%windir%"
                                                    - (char *)&Names::s_wszEngineFullPathWithWindir);
            if ( !v19 )
              break;
            *v18++ = v19;
            --v17;
          }
          while ( v17 );
          v20 = v18 - 1;
          if ( v17 )
            v20 = v18;
          *v20 = 0;
          result = v17 == 0 ? 0x8007007A : 0;
          if ( !v17 )
            return result;
          result = StringCchCatW(&Names::s_wszEngineFullPathWithWindir, 0x104u, &Names::s_wszEngineFullPath + v7 - 1);
          if ( (_DWORD)result )
            return result;
        }
        else
        {
          v21 = 260;
          do
          {
            if ( v21 == -2147483386 )
              break;
            v22 = *(unsigned __int16 *)((char *)v16
                                      + (char *)&Names::s_wszEngineFullPath
                                      - (char *)&Names::s_wszEngineFullPathWithWindir);
            if ( !v22 )
              break;
            *v16++ = v22;
            --v21;
          }
          while ( v21 );
          v23 = v16 - 1;
          if ( v21 )
            v23 = v16;
          *v23 = 0;
          result = v21 == 0 ? 0x8007007A : 0;
          if ( !v21 )
            return result;
        }
        result = GetInstallDirectory64(&Names::s_wszInstallDirectory64, 0x104u);
        if ( !(_DWORD)result )
        {
          v24 = &Names::s_wszIsapiFullPath;
          v25 = 260;
          do
          {
            if ( v25 == -2147483386 )
              break;
            v26 = *(wchar_t *)((char *)v24 + (char *)&Names::s_wszInstallDirectory - (char *)&Names::s_wszIsapiFullPath);
            if ( !v26 )
              break;
            *v24++ = v26;
            --v25;
          }
          while ( v25 );
          v27 = v24 - 1;
          if ( v25 )
            v27 = v24;
          *v27 = 0;
          result = v25 == 0 ? 0x8007007A : 0;
          if ( v25 )
          {
            result = StringCchCatW(&Names::s_wszIsapiFullPath, 0x104u, L"\\");
            if ( !(_DWORD)result )
            {
              result = StringCchCatW(&Names::s_wszIsapiFullPath, 0x104u, L"aspnet_isapi.dll");
              if ( !(_DWORD)result )
              {
                v28 = 260;
                v29 = &Names::s_wszIsapiFullPathWithWindir;
                do
                {
                  if ( v28 == -2147483386 )
                    break;
                  v30 = *(unsigned __int16 *)((char *)v29 + (char *)v74 - (char *)&Names::s_wszIsapiFullPathWithWindir);
                  if ( !v30 )
                    break;
                  *v29++ = v30;
                  --v28;
                }
                while ( v28 );
                v31 = v29 - 1;
                if ( v28 )
                  v31 = v29;
                *v31 = 0;
                result = v28 == 0 ? 0x8007007A : 0;
                if ( v28 )
                {
                  result = StringCchCatW(&Names::s_wszIsapiFullPathWithWindir, 0x104u, L"\\");
                  if ( !(_DWORD)result )
                  {
                    result = StringCchCatW(&Names::s_wszIsapiFullPathWithWindir, 0x104u, L"aspnet_isapi.dll");
                    if ( !(_DWORD)result )
                    {
                      v32 = &Names::s_wszWebFullPath;
                      v33 = 260;
                      do
                      {
                        if ( v33 == -2147483386 )
                          break;
                        v34 = *(unsigned __int16 *)((char *)v32
                                                  + (char *)&Names::s_wszInstallDirectory
                                                  - (char *)&Names::s_wszWebFullPath);
                        if ( !v34 )
                          break;
                        *v32++ = v34;
                        --v33;
                      }
                      while ( v33 );
                      v35 = v32 - 1;
                      if ( v33 )
                        v35 = v32;
                      *v35 = 0;
                      result = v33 == 0 ? 0x8007007A : 0;
                      if ( v33 )
                      {
                        result = StringCchCatW(&Names::s_wszWebFullPath, 0x104u, L"\\");
                        if ( !(_DWORD)result )
                        {
                          result = StringCchCatW(&Names::s_wszWebFullPath, 0x104u, L"System.Web.dll");
                          if ( !(_DWORD)result )
                          {
                            v36 = &Names::s_wszGlobalConfigDirectory;
                            v37 = 260;
                            do
                            {
                              if ( v37 == -2147483386 )
                                break;
                              v38 = *(WCHAR *)((char *)v36
                                             + (char *)&Names::s_wszInstallDirectory
                                             - (char *)&Names::s_wszGlobalConfigDirectory);
                              if ( !v38 )
                                break;
                              *v36++ = v38;
                              --v37;
                            }
                            while ( v37 );
                            v39 = v36 - 1;
                            if ( v37 )
                              v39 = v36;
                            *v39 = 0;
                            result = v37 == 0 ? 0x8007007A : 0;
                            if ( v37 )
                            {
                              result = StringCchCatW(&Names::s_wszGlobalConfigDirectory, 0x104u, L"\\");
                              if ( !(_DWORD)result )
                              {
                                result = StringCchCatW(&Names::s_wszGlobalConfigDirectory, 0x104u, L"config");
                                if ( !(_DWORD)result )
                                {
                                  if ( !WideCharToMultiByte(
                                          0,
                                          0,
                                          &Names::s_wszGlobalConfigDirectory,
                                          -1,
                                          Names::s_szGlobalConfigFullPath,
                                          260,
                                          0,
                                          0) )
                                    return GetLastWin32Error();
                                  result = StringCchCatA(Names::s_szGlobalConfigFullPath, 0x104u, "\\");
                                  if ( !(_DWORD)result )
                                  {
                                    result = StringCchCatA(Names::s_szGlobalConfigFullPath, 0x104u, "machine.config");
                                    if ( !(_DWORD)result )
                                    {
                                      v40 = 260;
                                      v41 = FileName;
                                      do
                                      {
                                        if ( v40 == -2147483386 )
                                          break;
                                        v42 = *(WCHAR *)((char *)v41
                                                       + (char *)&Names::s_wszGlobalConfigDirectory
                                                       - (char *)FileName);
                                        if ( !v42 )
                                          break;
                                        *v41++ = v42;
                                        --v40;
                                      }
                                      while ( v40 );
                                      v43 = v41 - 1;
                                      if ( v40 )
                                        v43 = v41;
                                      *v43 = 0;
                                      result = v40 == 0 ? 0x8007007A : 0;
                                      if ( v40 )
                                      {
                                        result = StringCchCatW(FileName, 0x104u, L"\\");
                                        if ( !(_DWORD)result )
                                        {
                                          result = StringCchCatW(FileName, 0x104u, L"machine.config");
                                          if ( !(_DWORD)result )
                                          {
                                            v44 = &Names::s_wszGlobalConfigFullPath;
                                            v45 = 260;
                                            do
                                            {
                                              if ( v45 == -2147483386 )
                                                break;
                                              v46 = *(WCHAR *)((char *)v44
                                                             + (char *)FileName
                                                             - (char *)&Names::s_wszGlobalConfigFullPath);
                                              if ( !v46 )
                                                break;
                                              *v44++ = v46;
                                              --v45;
                                            }
                                            while ( v45 );
                                            v47 = v44 - 1;
                                            if ( v45 )
                                              v47 = v44;
                                            *v47 = 0;
                                            result = v45 == 0 ? 0x8007007A : 0;
                                            if ( v45 )
                                            {
                                              FirstFileW = FindFirstFileW(FileName, &FindFileData);
                                              if ( FirstFileW == (HANDLE)-1LL )
                                                goto LABEL_110;
                                              FindClose(FirstFileW);
                                              v49 = &Names::s_wszGlobalConfigShortFileName;
                                              v50 = 14;
                                              do
                                              {
                                                if ( v50 == -2147483632 )
                                                  break;
                                                v51 = *(wchar_t *)((char *)v49
                                                                 + (char *)FindFileData.cAlternateFileName
                                                                 - (char *)&Names::s_wszGlobalConfigShortFileName);
                                                if ( !v51 )
                                                  break;
                                                *v49++ = v51;
                                                --v50;
                                              }
                                              while ( v50 );
                                              v52 = v49 - 1;
                                              if ( v50 )
                                                v52 = v49;
                                              *v52 = 0;
                                              result = v50 == 0 ? 0x8007007A : 0;
                                              if ( v50 )
                                              {
LABEL_110:
                                                result = Names::LoadResourceDLL(
                                                           &Names::s_langid,
                                                           &Names::s_wszRcFullPath,
                                                           260,
                                                           &g_rcDllInstance,
                                                           2);
                                                if ( !(_DWORD)result )
                                                {
                                                  v53 = &Names::s_wszClientScriptSrcDir;
                                                  v54 = 260;
                                                  do
                                                  {
                                                    if ( v54 == -2147483386 )
                                                      break;
                                                    v55 = *(unsigned __int16 *)((char *)v53
                                                                              + (char *)&Names::s_wszInstallDirectory
                                                                              - (char *)&Names::s_wszClientScriptSrcDir);
                                                    if ( !v55 )
                                                      break;
                                                    *v53++ = v55;
                                                    --v54;
                                                  }
                                                  while ( v54 );
                                                  v56 = v53 - 1;
                                                  if ( v54 )
                                                    v56 = v53;
                                                  *v56 = 0;
                                                  result = v54 == 0 ? 0x8007007A : 0;
                                                  if ( v54 )
                                                  {
                                                    result = StringCchCatW(
                                                               &Names::s_wszClientScriptSrcDir,
                                                               0x104u,
                                                               L"\\");
                                                    if ( !(_DWORD)result )
                                                    {
                                                      result = StringCchCatW(
                                                                 &Names::s_wszClientScriptSrcDir,
                                                                 0x104u,
                                                                 L"asp.netclientfiles");
                                                      if ( !(_DWORD)result )
                                                      {
                                                        v57 = &Names::s_wszWebAdminSrcDir;
                                                        v58 = 260;
                                                        do
                                                        {
                                                          if ( v58 == -2147483386 )
                                                            break;
                                                          v59 = *(unsigned __int16 *)((char *)v57
                                                                                    + (char *)&Names::s_wszInstallDirectory
                                                                                    - (char *)&Names::s_wszWebAdminSrcDir);
                                                          if ( !v59 )
                                                            break;
                                                          *v57++ = v59;
                                                          --v58;
                                                        }
                                                        while ( v58 );
                                                        v60 = v57 - 1;
                                                        if ( v58 )
                                                          v60 = v57;
                                                        *v60 = 0;
                                                        result = v58 == 0 ? 0x8007007A : 0;
                                                        if ( v58 )
                                                        {
                                                          result = StringCchCatW(
                                                                     &Names::s_wszWebAdminSrcDir,
                                                                     0x104u,
                                                                     L"\\");
                                                          if ( !(_DWORD)result )
                                                          {
                                                            result = StringCchCatW(
                                                                       &Names::s_wszWebAdminSrcDir,
                                                                       0x104u,
                                                                       L"asp.netwebadminfiles");
                                                            if ( !(_DWORD)result )
                                                            {
                                                              v61 = &Names::s_wszFilterFullPath;
                                                              v62 = 260;
                                                              do
                                                              {
                                                                if ( v62 == -2147483386 )
                                                                  break;
                                                                v63 = *(OLECHAR *)((char *)v61
                                                                                 + (char *)&Names::s_wszInstallDirectory
                                                                                 - (char *)&Names::s_wszFilterFullPath);
                                                                if ( !v63 )
                                                                  break;
                                                                *v61++ = v63;
                                                                --v62;
                                                              }
                                                              while ( v62 );
                                                              v64 = v61 - 1;
                                                              if ( v62 )
                                                                v64 = v61;
                                                              *v64 = 0;
                                                              result = v62 == 0 ? 0x8007007A : 0;
                                                              if ( v62 )
                                                              {
                                                                result = StringCchCatW(
                                                                           &Names::s_wszFilterFullPath,
                                                                           0x104u,
                                                                           L"\\");
                                                                if ( !(_DWORD)result )
                                                                {
                                                                  result = StringCchCatW(
                                                                             &Names::s_wszFilterFullPath,
                                                                             0x104u,
                                                                             L"aspnet_filter.dll");
                                                                  if ( !(_DWORD)result )
                                                                  {
                                                                    v65 = 260;
                                                                    v66 = &Names::s_wszFilterFullPathWithWindir;
                                                                    do
                                                                    {
                                                                      if ( v65 == -2147483386 )
                                                                        break;
                                                                      v67 = *(unsigned __int16 *)((char *)v66
                                                                                                + (char *)v74
                                                                                                - (char *)&Names::s_wszFilterFullPathWithWindir);
                                                                      if ( !v67 )
                                                                        break;
                                                                      *v66++ = v67;
                                                                      --v65;
                                                                    }
                                                                    while ( v65 );
                                                                    v68 = v66 - 1;
                                                                    if ( v65 )
                                                                      v68 = v66;
                                                                    *v68 = 0;
                                                                    result = v65 == 0 ? 0x8007007A : 0;
                                                                    if ( v65 )
                                                                    {
                                                                      result = StringCchCatW(
                                                                                 &Names::s_wszFilterFullPathWithWindir,
                                                                                 0x104u,
                                                                                 L"\\");
                                                                      if ( !(_DWORD)result )
                                                                      {
                                                                        result = StringCchCatW(
                                                                                   &Names::s_wszFilterFullPathWithWindir,
                                                                                   0x104u,
                                                                                   L"aspnet_filter.dll");
                                                                        if ( !(_DWORD)result )
                                                                        {
                                                                          v69 = 260;
                                                                          v70 = &Names::s_wszPerfFullPath;
                                                                          do
                                                                          {
                                                                            if ( v69 == -2147483386 )
                                                                              break;
                                                                            v71 = *(unsigned __int16 *)((char *)v70 + (char *)&Names::s_wszInstallDirectory - (char *)&Names::s_wszPerfFullPath);
                                                                            if ( !v71 )
                                                                              break;
                                                                            *v70++ = v71;
                                                                            --v69;
                                                                          }
                                                                          while ( v69 );
                                                                          v72 = v70 - 1;
                                                                          if ( v69 )
                                                                            v72 = v70;
                                                                          *v72 = 0;
                                                                          result = v69 == 0 ? 0x8007007A : 0;
                                                                          if ( v69 )
                                                                          {
                                                                            result = StringCchCatW(
                                                                                       &Names::s_wszPerfFullPath,
                                                                                       0x104u,
                                                                                       L"\\");
                                                                            if ( !(_DWORD)result )
                                                                              return StringCchCatW(
                                                                                       &Names::s_wszPerfFullPath,
                                                                                       0x104u,
                                                                                       L"aspnet_perf.dll");
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016fd8  mov     rax, rsp
0x180016fdb  mov     [rax+8], rbx
0x180016fdf  mov     [rax+10h], rsi
0x180016fe3  mov     [rax+18h], rdi
0x180016fe7  push    rbp
0x180016fe8  push    r12
0x180016fea  push    r13
0x180016fec  push    r14
0x180016fee  push    r15
0x180016ff0  lea     rbp, [rax-7F8h]
0x180016ff7  sub     rsp, 8D0h
0x180016ffe  mov     rax, cs:__security_cookie
0x180017005  xor     rax, rsp
0x180017008  mov     [rbp+7F0h+var_30], rax
0x18001700f  mov     r12d, 104h
0x180017015  lea     rdx, ?s_wszExeFullPath@Names@@0PAGA; lpFilename
0x18001701c  mov     r8d, r12d; nSize
0x18001701f  xor     ecx, ecx; hModule
0x180017021  call    cs:__imp_GetModuleFileNameW
0x180017027  xor     r15d, r15d
0x18001702a  test    eax, eax
0x18001702c  jnz     short loc_180017038
0x18001702e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180017033  jmp     loc_1800179B9
0x180017038  mov     edx, 5Ch ; '\'; Ch
0x18001703d  lea     rcx, ?s_wszExeFullPath@Names@@0PAGA; Str
0x180017044  call    wcsrchr_0
0x180017049  mov     r8, rax
0x18001704c  test    rax, rax
0x18001704f  jnz     short loc_18001705B
0x180017051  mov     eax, 8000FFFFh
0x180017056  jmp     loc_1800179B9
0x18001705b  lea     rcx, ?s_wszExeFileName@Names@@0PAGA; ushort near * Names::s_wszExeFileName
0x180017062  mov     rdx, r12
0x180017065  sub     r8, rcx
0x180017068  mov     r13d, 2
0x18001706e  lea     rax, [rdx+7FFFFEFAh]
0x180017075  test    rax, rax
0x180017078  jz      short loc_180017091
0x18001707a  movzx   eax, word ptr [r8+rcx+2]
0x180017080  test    ax, ax
0x180017083  jz      short loc_180017091
0x180017085  mov     [rcx], ax
0x180017088  add     rcx, r13
0x18001708b  sub     rdx, 1
0x18001708f  jnz     short loc_18001706E
0x180017091  test    rdx, rdx
0x180017094  lea     rax, [rcx-2]
0x180017098  cmovnz  rax, rcx
0x18001709c  mov     [rax], r15w
0x1800170a0  mov     rax, rdx
0x1800170a3  neg     rax
0x1800170a6  sbb     eax, eax
0x1800170a8  not     eax
0x1800170aa  and     eax, 8007007Ah
0x1800170af  test    rdx, rdx
0x1800170b2  jz      loc_1800179B9
0x1800170b8  lea     rbx, ?s_wszEngineFullPath@Names@@0PAGA; ushort near * Names::s_wszEngineFullPath
0x1800170bf  mov     rdx, r12; unsigned __int64
0x1800170c2  mov     rcx, rbx; unsigned __int16 *
0x1800170c5  call    ?GetEngineFullPath@@YAJPEAG_K@Z; GetEngineFullPath(ushort *,unsigned __int64)
0x1800170ca  test    eax, eax
0x1800170cc  jnz     loc_1800179B9
0x1800170d2  lea     r14, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x1800170d9  mov     rdx, r12; unsigned __int64
0x1800170dc  mov     rcx, r14; unsigned __int16 *
0x1800170df  call    ?GetInstallDirectory@@YAJPEAG_K@Z; GetInstallDirectory(ushort *,unsigned __int64)
0x1800170e4  test    eax, eax
0x1800170e6  jnz     loc_1800179B9
0x1800170ec  lea     rdi, Src; "%windir%"
0x1800170f3  mov     r8d, r12d; nSize
0x1800170f6  mov     rcx, rdi; lpSrc
0x1800170f9  lea     rdx, [rbp+7F0h+Dst]; lpDst
0x180017100  call    cs:__imp_ExpandEnvironmentStringsW
0x180017106  lea     rdx, [rbp+7F0h+Dst]; SubStr
0x18001710d  mov     rcx, r14; Str
0x180017110  mov     esi, eax
0x180017112  call    wcsstr_0
0x180017117  cmp     rax, r14
0x18001711a  lea     rcx, [rbp+7F0h+var_660]
0x180017121  lea     rax, [rbp+7F0h+var_660]
0x180017128  mov     rdx, r12
0x18001712b  jnz     short loc_18001719D
0x18001712d  mov     r8, rdi
0x180017130  sub     r8, rax
0x180017133  lea     rax, [rdx+7FFFFEFAh]
0x18001713a  test    rax, rax
0x18001713d  jz      short loc_180017155
0x18001713f  movzx   eax, word ptr [r8+rcx]
0x180017144  test    ax, ax
0x180017147  jz      short loc_180017155
0x180017149  mov     [rcx], ax
0x18001714c  add     rcx, r13
0x18001714f  sub     rdx, 1
0x180017153  jnz     short loc_180017133
0x180017155  test    rdx, rdx
0x180017158  lea     rax, [rcx-2]
0x18001715c  cmovnz  rax, rcx
0x180017160  mov     [rax], r15w
0x180017164  mov     rax, rdx
0x180017167  neg     rax
0x18001716a  sbb     eax, eax
0x18001716c  not     eax
0x18001716e  and     eax, 8007007Ah
0x180017173  test    rdx, rdx
0x180017176  jz      loc_1800179B9
0x18001717c  lea     rax, [r14-2]
0x180017180  mov     rdx, r12; unsigned __int64
0x180017183  lea     r8, [rax+rsi*2]; unsigned __int16 *
0x180017187  lea     rcx, [rbp+7F0h+var_660]; unsigned __int16 *
0x18001718e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017193  test    eax, eax
0x180017195  jnz     loc_1800179B9
0x18001719b  jmp     short loc_1800171EC
0x18001719d  mov     r8, r14
0x1800171a0  sub     r8, rax
0x1800171a3  lea     rax, [rdx+7FFFFEFAh]
0x1800171aa  test    rax, rax
0x1800171ad  jz      short loc_1800171C5
0x1800171af  movzx   eax, word ptr [rcx+r8]
0x1800171b4  test    ax, ax
0x1800171b7  jz      short loc_1800171C5
0x1800171b9  mov     [rcx], ax
0x1800171bc  add     rcx, r13
0x1800171bf  sub     rdx, 1
0x1800171c3  jnz     short loc_1800171A3
0x1800171c5  test    rdx, rdx
0x1800171c8  lea     rax, [rcx-2]
0x1800171cc  cmovnz  rax, rcx
0x1800171d0  mov     [rax], r15w
0x1800171d4  mov     rax, rdx
0x1800171d7  neg     rax
0x1800171da  sbb     eax, eax
0x1800171dc  not     eax
0x1800171de  and     eax, 8007007Ah
0x1800171e3  test    rdx, rdx
0x1800171e6  jz      loc_1800179B9
0x1800171ec  lea     rdx, [rbp+7F0h+Dst]; SubStr
0x1800171f3  mov     rcx, rbx; Str
0x1800171f6  call    wcsstr_0
0x1800171fb  lea     rcx, ?s_wszEngineFullPathWithWindir@Names@@0PAGA; unsigned __int16 *
0x180017202  cmp     rax, rbx
0x180017205  jnz     short loc_180017274
0x180017207  mov     r8, r12
0x18001720a  mov     rdx, rcx
0x18001720d  sub     rdi, rcx
0x180017210  lea     rax, [r8+7FFFFEFAh]
0x180017217  test    rax, rax
0x18001721a  jz      short loc_180017231
0x18001721c  movzx   eax, word ptr [rdx+rdi]
0x180017220  test    ax, ax
0x180017223  jz      short loc_180017231
0x180017225  mov     [rdx], ax
0x180017228  add     rdx, r13
0x18001722b  sub     r8, 1
0x18001722f  jnz     short loc_180017210
0x180017231  test    r8, r8
0x180017234  lea     rax, [rdx-2]
0x180017238  mov     edi, 8007007Ah
0x18001723d  cmovnz  rax, rdx
0x180017241  mov     [rax], r15w
0x180017245  mov     rax, r8
0x180017248  neg     rax
0x18001724b  sbb     eax, eax
0x18001724d  not     eax
0x18001724f  and     eax, edi
0x180017251  test    r8, r8
0x180017254  jz      loc_1800179B9
0x18001725a  lea     rax, [rbx-2]
0x18001725e  mov     rdx, r12; unsigned __int64
0x180017261  lea     r8, [rax+rsi*2]; unsigned __int16 *
0x180017265  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001726a  test    eax, eax
0x18001726c  jnz     loc_1800179B9
0x180017272  jmp     short loc_1800172C4
0x180017274  mov     rdx, r12
0x180017277  sub     rbx, rcx
0x18001727a  lea     rax, [rdx+7FFFFEFAh]
0x180017281  test    rax, rax
0x180017284  jz      short loc_18001729B
0x180017286  movzx   eax, word ptr [rcx+rbx]
0x18001728a  test    ax, ax
0x18001728d  jz      short loc_18001729B
0x18001728f  mov     [rcx], ax
0x180017292  add     rcx, r13
0x180017295  sub     rdx, 1
0x180017299  jnz     short loc_18001727A
0x18001729b  test    rdx, rdx
0x18001729e  lea     rax, [rcx-2]
0x1800172a2  mov     edi, 8007007Ah
0x1800172a7  cmovnz  rax, rcx
0x1800172ab  mov     [rax], r15w
0x1800172af  mov     rax, rdx
0x1800172b2  neg     rax
0x1800172b5  sbb     eax, eax
0x1800172b7  not     eax
0x1800172b9  and     eax, edi
0x1800172bb  test    rdx, rdx
0x1800172be  jz      loc_1800179B9
0x1800172c4  mov     rdx, r12; unsigned __int64
0x1800172c7  lea     rcx, ?s_wszInstallDirectory64@Names@@0PAGA; unsigned __int16 *
0x1800172ce  call    ?GetInstallDirectory64@@YAJPEAG_K@Z; GetInstallDirectory64(ushort *,unsigned __int64)
0x1800172d3  test    eax, eax
0x1800172d5  jnz     loc_1800179B9
0x1800172db  lea     rbx, ?s_wszIsapiFullPath@Names@@0PAGA; ushort near * Names::s_wszIsapiFullPath
0x1800172e2  mov     r8, r14
0x1800172e5  mov     rcx, rbx
0x1800172e8  lea     esi, [rax+1]
0x1800172eb  sub     r8, rbx
0x1800172ee  mov     rdx, r12
0x1800172f1  lea     rax, [rdx+7FFFFEFAh]
0x1800172f8  test    rax, rax
0x1800172fb  jz      short loc_180017312
0x1800172fd  movzx   eax, word ptr [rcx+r8]
0x180017302  test    ax, ax
0x180017305  jz      short loc_180017312
0x180017307  mov     [rcx], ax
0x18001730a  add     rcx, r13
0x18001730d  sub     rdx, rsi
0x180017310  jnz     short loc_1800172F1
0x180017312  test    rdx, rdx
0x180017315  lea     rax, [rcx-2]
0x180017319  cmovnz  rax, rcx
0x18001731d  mov     [rax], r15w
0x180017321  mov     rax, rdx
0x180017324  neg     rax
0x180017327  sbb     eax, eax
0x180017329  not     eax
0x18001732b  and     eax, edi
0x18001732d  test    rdx, rdx
0x180017330  jz      loc_1800179B9
0x180017336  lea     rdi, SubBlock; "\\"
0x18001733d  mov     rdx, r12; unsigned __int64
0x180017340  mov     r8, rdi; unsigned __int16 *
0x180017343  mov     rcx, rbx; unsigned __int16 *
0x180017346  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001734b  test    eax, eax
0x18001734d  jnz     loc_1800179B9
0x180017353  lea     r8, aAspnetIsapiDll_0; "aspnet_isapi.dll"
0x18001735a  mov     rdx, r12; unsigned __int64
0x18001735d  mov     rcx, rbx; unsigned __int16 *
0x180017360  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017365  test    eax, eax
0x180017367  jnz     loc_1800179B9
0x18001736d  lea     rbx, ?s_wszIsapiFullPathWithWindir@Names@@0PAGA; ushort near * Names::s_wszIsapiFullPathWithWindir
0x180017374  mov     rdx, r12
0x180017377  lea     r8, [rbp+7F0h+var_660]
0x18001737e  mov     rcx, rbx
0x180017381  sub     r8, rbx
0x180017384  lea     rax, [rdx+7FFFFEFAh]
0x18001738b  test    rax, rax
0x18001738e  jz      short loc_1800173A5
0x180017390  movzx   eax, word ptr [rcx+r8]
0x180017395  test    ax, ax
0x180017398  jz      short loc_1800173A5
0x18001739a  mov     [rcx], ax
0x18001739d  add     rcx, r13
0x1800173a0  sub     rdx, rsi
0x1800173a3  jnz     short loc_180017384
0x1800173a5  test    rdx, rdx
0x1800173a8  lea     rax, [rcx-2]
0x1800173ac  cmovnz  rax, rcx
0x1800173b0  mov     [rax], r15w
0x1800173b4  mov     rax, rdx
0x1800173b7  neg     rax
0x1800173ba  sbb     eax, eax
0x1800173bc  not     eax
0x1800173be  and     eax, 8007007Ah
0x1800173c3  test    rdx, rdx
0x1800173c6  jz      loc_1800179B9
0x1800173cc  mov     r8, rdi; unsigned __int16 *
0x1800173cf  mov     rdx, r12; unsigned __int64
0x1800173d2  mov     rcx, rbx; unsigned __int16 *
0x1800173d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800173da  test    eax, eax
0x1800173dc  jnz     loc_1800179B9
0x1800173e2  lea     r8, aAspnetIsapiDll_0; "aspnet_isapi.dll"
0x1800173e9  mov     rdx, r12; unsigned __int64
0x1800173ec  mov     rcx, rbx; unsigned __int16 *
0x1800173ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800173f4  test    eax, eax
0x1800173f6  jnz     loc_1800179B9
0x1800173fc  lea     rbx, ?s_wszWebFullPath@Names@@0PAGA; ushort near * Names::s_wszWebFullPath
0x180017403  mov     r8, r14
0x180017406  mov     rcx, rbx
0x180017409  sub     r8, rbx
0x18001740c  mov     rdx, r12
0x18001740f  lea     rax, [rdx+7FFFFEFAh]
0x180017416  test    rax, rax
0x180017419  jz      short loc_180017430
0x18001741b  movzx   eax, word ptr [rcx+r8]
0x180017420  test    ax, ax
0x180017423  jz      short loc_180017430
0x180017425  mov     [rcx], ax
0x180017428  add     rcx, r13
0x18001742b  sub     rdx, rsi
0x18001742e  jnz     short loc_18001740F
0x180017430  test    rdx, rdx
0x180017433  lea     rax, [rcx-2]
0x180017437  cmovnz  rax, rcx
  ... truncated ...
```
