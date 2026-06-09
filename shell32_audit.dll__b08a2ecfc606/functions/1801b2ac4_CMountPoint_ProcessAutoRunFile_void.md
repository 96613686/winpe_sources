# CMountPoint::_ProcessAutoRunFile(void)

- ea: `0x1801b2ac4`
- end: `0x1801b344a`
- name: `?_ProcessAutoRunFile@CMountPoint@@QEAAHXZ`
- size: `2438`
- prototype: `__int64 __fastcall(CMountPoint *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802fc464`
- `0x180303370`
- `0x1805852d0`

## callees

- `0x18001aae0`
- `0x18001b9a0`
- `0x18009b938`
- `0x18016a154`
- `0x1801b2ac4`
- `0x180249490`
- `0x180289588`
- `0x180457160`
- `0x180581c64`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2c1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2cf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2c1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801b2cf0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801b2e59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801b304f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801b2e59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801b304f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801b2f5e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801b2f5e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b2d61`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b2ef3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b30f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b31d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b326f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b3297`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b32b3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b2d61`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b2ef3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b30f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b31d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b326f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b3297`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801b32b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801b3340`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801b3340`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801b2c62`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801b2c62`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2c9c`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2ce0`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2d4b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2c9c`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2ce0`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801b2d4b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801b332a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801b332a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2dea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2fca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b30c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b30d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b3142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b3153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b31a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b31b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2dea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2fca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b2fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b30c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b30d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b3142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b3153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b31a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b31b6`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1801b2c34`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1801b2c34`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b2e08`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b2ff9`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b3173`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b2e08`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b2ff9`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1801b3173`

## string_xrefs

- `0x1801b3336`: `command`
- `0x1801b2e28`: `shell\AutoRun\command`
- `0x1801b2fa7`: `shell\AutoRun\command`
- `0x1801b2e90`: `SetWorkingDirectoryFromTarget`
- `0x1801b3084`: `SetWorkingDirectoryFromTarget`
- `0x1801b336a`: `SetWorkingDirectoryFromTarget`
- `0x1801b2f57`: `"%windir%\system32\RunDLL32.EXE" Shell32.DLL,ShellExec_RunDLL `

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMountPoint::_ProcessAutoRunFile(CMountPoint *this)
{
  unsigned int v2; // r15d
  int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // r10d
  UINT v7; // esi
  const WCHAR *v8; // r12
  signed int PrivateProfileStringW; // edi
  WCHAR *v10; // rdi
  __int16 v11; // r14
  char v12; // si
  unsigned int v13; // r8d
  void *v14; // rcx
  __int16 v15; // r14
  char v16; // si
  unsigned int v17; // r8d
  unsigned int v18; // r10d
  unsigned int v19; // r10d
  WCHAR *p_pszCmdTemplate; // r9
  const unsigned __int16 *v21; // rdx
  const WCHAR *FileNameW; // rax
  unsigned int v23; // r8d
  __int64 v24; // rax
  PWSTR ppszCommandLine; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR v27; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszApplication; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR v29; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR v30; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszCmdTemplate; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v32[263]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR Buffer[64]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v34[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR v36[272]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR ReturnedString[512]; // [rsp+7A0h] [rbp+6A0h] BYREF
  WCHAR Dst[520]; // [rsp+BA0h] [rbp+AA0h] BYREF

  v2 = 1;
  if ( *((_DWORD *)this + 143) )
    return v2;
  v3 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this);
  v4 = *(_QWORD *)this;
  if ( v3 )
  {
    if ( (*(unsigned int (__fastcall **)(CMountPoint *))(v4 + 488))(this)
      && (!(unsigned int)CMtPtLocal::CanUseVolume(this) || (*(_DWORD *)(*((_QWORD *)this + 72) + 56LL) & 0x101) == 1) )
    {
      goto LABEL_10;
    }
  }
  else if ( (*(unsigned int (__fastcall **)(CMountPoint *))(v4 + 360))(this)
         || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 352LL))(this)
         || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 472LL))(this) )
  {
LABEL_10:
    (*(void (__fastcall **)(CMountPoint *, const WCHAR *))(*(_QWORD *)this + 32LL))(this, L"Shell");
    (*(void (__fastcall **)(CMountPoint *, const wchar_t *))(*(_QWORD *)this + 32LL))(this, L"_Autorun");
    StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)this + 26);
    StringCchCatW(FileName, v5, L"AutoRun.inf");
    if ( !IsPathSafeForAutoplay(FileName) )
    {
LABEL_11:
      *((_DWORD *)this + 143) = 1;
      return 0;
    }
    v7 = SetErrorMode(1u);
    if ( !(unsigned int)PathFileExistsAndAttributesW(FileName, 0) )
    {
      SetErrorMode(v7);
      goto LABEL_11;
    }
    WritePrivateProfileStringW(0, 0, 0, FileName);
    v8 = L"AutoRun.Amd64";
    PrivateProfileStringW = GetPrivateProfileStringW(L"AutoRun.Amd64", 0, &c_szNULL, ReturnedString, 0x200u, FileName);
    if ( !PrivateProfileStringW )
    {
      v8 = L"AutoRun";
      PrivateProfileStringW = GetPrivateProfileStringW(L"AutoRun", 0, &c_szNULL, ReturnedString, 0x200u, FileName);
    }
    SetErrorMode(v7);
    if ( PrivateProfileStringW < 4 )
    {
      v2 = 0;
    }
    else
    {
      v10 = ReturnedString;
      if ( ReturnedString[0] )
      {
        while ( 1 )
        {
          GetPrivateProfileStringW(v8, v10, &c_szNULL, &pszCmdTemplate, 0x104u, FileName);
          if ( !StrCmpICW(v10, L"open") )
          {
            if ( !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this) )
              goto LABEL_58;
            v11 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 232LL))(this);
            v12 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 240LL))(this);
            CMountPoint::_QualifyCommandToDrive(this, &pszCmdTemplate, v13);
            pv = 0;
            ppszCommandLine = 0;
            CoTaskMemFree(0);
            CoTaskMemFree(pv);
            if ( SHEvaluateSystemCommandTemplate(&pszCmdTemplate, (PWSTR *)&pv, &ppszCommandLine, 0) >= 0 )
              CRegSupport::RSSetTextValue(this, L"shell\\AutoRun\\command", 0, ppszCommandLine, 0xFFFFFFFF);
            LoadStringW(g_hinst, ((v12 & 6) != 0) + 17419, Buffer, 64);
            CRegSupport::RSSetTextValue(this, L"shell\\AutoRun", 0, Buffer, 0xFFFFFFFF);
            CRegSupport::RSSetTextValue(
              this,
              L"shell\\AutoRun",
              L"SetWorkingDirectoryFromTarget",
              &pszStart,
              0xFFFFFFFF);
            if ( (v11 & 0xFE0) != 0 )
              CRegSupport::RSSetTextValue(this, L"Shell", 0, L"AutoRun", 0xFFFFFFFF);
            CoTaskMemFree(ppszCommandLine);
            v14 = pv;
            goto LABEL_33;
          }
          if ( !StrCmpICW(v10, L"ShellExecute") )
          {
            if ( !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this) )
              goto LABEL_58;
            v15 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 232LL))(this);
            v16 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 240LL))(this);
            if ( !ExpandEnvironmentStringsW(
                    L"\"%windir%\\system32\\RunDLL32.EXE\" Shell32.DLL,ShellExec_RunDLL ",
                    Dst,
                    0x208u) )
              goto LABEL_58;
            CMountPoint::_QualifyCommandToDrive(this, &pszCmdTemplate, v17);
            StringCchCatW(Dst, 0x208u, &pszCmdTemplate);
            CRegSupport::RSSetTextValue(this, L"shell\\AutoRun\\command", 0, Dst, 0xFFFFFFFF);
            ppszApplication = 0;
            v27 = 0;
            CoTaskMemFree(0);
            CoTaskMemFree(ppszApplication);
            if ( SHEvaluateSystemCommandTemplate(&pszCmdTemplate, &ppszApplication, &v27, 0) >= 0 )
              CRegSupport::RSSetTextValue(this, L"shell\\AutoRun", L"ShellExecute", v27, 0xFFFFFFFF);
            LoadStringW(g_hinst, ((v16 & 6) != 0) + 17419, &pszCmdTemplate, 260);
            CRegSupport::RSSetTextValue(this, L"shell\\AutoRun", 0, &pszCmdTemplate, 0xFFFFFFFF);
            CRegSupport::RSSetTextValue(
              this,
              L"shell\\AutoRun",
              L"SetWorkingDirectoryFromTarget",
              &pszStart,
              0xFFFFFFFF);
            if ( (v15 & 0xFE0) != 0 )
              CRegSupport::RSSetTextValue(this, L"Shell", 0, L"AutoRun", 0xFFFFFFFF);
            CoTaskMemFree(v27);
            v14 = ppszApplication;
LABEL_33:
            CoTaskMemFree(v14);
            goto LABEL_58;
          }
          if ( !StrCmpICW(v10, L"Icon") )
          {
            StringCchCopyW(v36, 0x110u, (const unsigned __int16 *)this + 26);
            StringCchCatW(v36, v18, &pszCmdTemplate);
            v30 = 0;
            v29 = 0;
            CoTaskMemFree(0);
            CoTaskMemFree(v30);
            if ( SHEvaluateSystemCommandTemplate(v36, &v30, &v29, 0) >= 0 )
              CRegSupport::RSSetTextValue(this, L"_Autorun\\DefaultIcon", 0, v29, 0xFFFFFFFF);
            CoTaskMemFree(v29);
            CoTaskMemFree(v30);
            goto LABEL_58;
          }
          if ( StrCmpICW(v10, L"Action") )
          {
            if ( StrCmpICW(v10, L"Label") )
            {
              if ( StrCmpICW(v10, L"shell") || StrCmpICW(&pszCmdTemplate, L"open") )
              {
                if ( !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this)
                  || !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 624LL))(this) )
                {
                  goto LABEL_58;
                }
                FileNameW = PathFindFileNameW(v10);
                if ( lstrcmpiW(FileNameW, L"command") )
                  CRegSupport::RSSetTextValue(this, v10, L"SetWorkingDirectoryFromTarget", &pszStart, 0xFFFFFFFF);
                else
                  CMountPoint::_QualifyCommandToDrive(this, &pszCmdTemplate, v23);
                p_pszCmdTemplate = &pszCmdTemplate;
              }
              else
              {
                if ( !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this) )
                  goto LABEL_58;
                p_pszCmdTemplate = (WCHAR *)L"Autorun";
              }
              v21 = v10;
            }
            else
            {
              p_pszCmdTemplate = &pszCmdTemplate;
              v21 = L"_Autorun\\DefaultLabel";
            }
          }
          else
          {
            if ( !(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)this + 392LL))(this) )
              goto LABEL_58;
            if ( pszCmdTemplate == 64 )
            {
              StringCchCopyW(v36, 0x110u, L"@");
              StringCchCatW(v36, v19, (const unsigned __int16 *)this + 26);
              StringCchCatW(v36, 0x110u, v32);
              p_pszCmdTemplate = v36;
            }
            else
            {
              p_pszCmdTemplate = &pszCmdTemplate;
            }
            v21 = L"_Autorun\\Action";
          }
          CRegSupport::RSSetTextValue(this, v21, 0, p_pszCmdTemplate, 0xFFFFFFFF);
LABEL_58:
          v24 = -1;
          do
            ++v24;
          while ( v10[v24] );
          v10 += v24 + 1;
          if ( !*v10 )
          {
            v2 = 1;
            break;
          }
        }
      }
      LODWORD(ppszCommandLine) = 64;
      if ( (*(unsigned int (__fastcall **)(CMountPoint *, const unsigned __int16 *))(*(_QWORD *)this + 16LL))(
             this,
             L"shell\\AutoRun") )
      {
        if ( (unsigned int)CRegSupport::RSGetTextValue(
                             this,
                             L"_Autorun\\Action",
                             0,
                             v34,
                             (const unsigned int *)&ppszCommandLine) )
          CRegSupport::RSSetTextValue(this, L"shell\\AutoRun", 0, v34, 0xFFFFFFFF);
      }
    }
  }
  *((_DWORD *)this + 143) = 1;
  return v2;
}

```

## disassembly

```asm
0x1801b2ac4  push    rbp
0x1801b2ac6  push    rbx
0x1801b2ac7  push    rsi
0x1801b2ac8  push    rdi
0x1801b2ac9  push    r12
0x1801b2acb  push    r13
0x1801b2acd  push    r14
0x1801b2acf  push    r15
0x1801b2ad1  lea     rbp, [rsp-0EC8h]
0x1801b2ad9  sub     rsp, 0FC8h
0x1801b2ae0  mov     rax, cs:__security_cookie
0x1801b2ae7  xor     rax, rsp
0x1801b2aea  mov     [rbp+0F00h+var_50], rax
0x1801b2af1  mov     rbx, rcx
0x1801b2af4  mov     r15d, 1
0x1801b2afa  xor     r14d, r14d
0x1801b2afd  cmp     [rcx+23Ch], r14d
0x1801b2b04  jnz     loc_1801B3423
0x1801b2b0a  mov     rax, [rcx]
0x1801b2b0d  mov     rax, [rax+188h]
0x1801b2b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2b19  mov     rdx, [rbx]
0x1801b2b1c  mov     rcx, rbx
0x1801b2b1f  test    eax, eax
0x1801b2b21  jz      short loc_1801B2B5E
0x1801b2b23  mov     rax, [rdx+1E8h]
0x1801b2b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2b2f  test    eax, eax
0x1801b2b31  jz      loc_1801B3419
0x1801b2b37  mov     rcx, rbx; this
0x1801b2b3a  call    ?CanUseVolume@CMtPtLocal@@QEBAHXZ; CMtPtLocal::CanUseVolume(void)
0x1801b2b3f  test    eax, eax
0x1801b2b41  jz      short loc_1801B2B9E
0x1801b2b43  mov     rax, [rbx+240h]
0x1801b2b4a  mov     ecx, [rax+38h]
0x1801b2b4d  and     ecx, 101h
0x1801b2b53  cmp     ecx, r15d
0x1801b2b56  jnz     loc_1801B3419
0x1801b2b5c  jmp     short loc_1801B2B9E
0x1801b2b5e  mov     rax, [rdx+168h]
0x1801b2b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2b6a  test    eax, eax
0x1801b2b6c  jnz     short loc_1801B2B9E
0x1801b2b6e  mov     rax, [rbx]
0x1801b2b71  mov     rcx, rbx
0x1801b2b74  mov     rax, [rax+160h]
0x1801b2b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2b80  test    eax, eax
0x1801b2b82  jnz     short loc_1801B2B9E
0x1801b2b84  mov     rax, [rbx]
0x1801b2b87  mov     rcx, rbx
0x1801b2b8a  mov     rax, [rax+1D8h]
0x1801b2b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2b96  test    eax, eax
0x1801b2b98  jz      loc_1801B3419
0x1801b2b9e  mov     rax, [rbx]
0x1801b2ba1  lea     rdx, pszBagName; "Shell"
0x1801b2ba8  mov     rcx, rbx
0x1801b2bab  mov     rax, [rax+20h]
0x1801b2baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2bb4  mov     rax, [rbx]
0x1801b2bb7  lea     rdx, aAutorun; "_Autorun"
0x1801b2bbe  mov     rcx, rbx
0x1801b2bc1  mov     rax, [rax+20h]
0x1801b2bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2bca  lea     r13, [rbx+34h]
0x1801b2bce  mov     r8, r13; unsigned __int16 *
0x1801b2bd1  mov     r10d, 104h
0x1801b2bd7  mov     edx, r10d; unsigned __int64
0x1801b2bda  lea     rcx, [rbp+0F00h+FileName]; unsigned __int16 *
0x1801b2be1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b2be6  lea     r8, aAutorunInf_0; "AutoRun.inf"
0x1801b2bed  mov     edx, r10d; unsigned __int64
0x1801b2bf0  lea     rcx, [rbp+0F00h+FileName]; unsigned __int16 *
0x1801b2bf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b2bfc  lea     rcx, [rbp+0F00h+FileName]; lpFileName
0x1801b2c03  call    IsPathSafeForAutoplay
0x1801b2c08  test    eax, eax
0x1801b2c0a  jnz     short loc_1801B2C1A
0x1801b2c0c  mov     [rbx+23Ch], r15d
0x1801b2c13  xor     eax, eax
0x1801b2c15  jmp     loc_1801B3426
0x1801b2c1a  mov     ecx, r15d; uMode
0x1801b2c1d  call    cs:__imp_SetErrorMode
0x1801b2c24  nop     dword ptr [rax+rax+00h]
0x1801b2c29  mov     esi, eax
0x1801b2c2b  xor     edx, edx
0x1801b2c2d  lea     rcx, [rbp+0F00h+FileName]
0x1801b2c34  call    cs:__imp_PathFileExistsAndAttributesW
0x1801b2c3b  nop     dword ptr [rax+rax+00h]
0x1801b2c40  test    eax, eax
0x1801b2c42  jnz     short loc_1801B2C54
0x1801b2c44  mov     ecx, esi; uMode
0x1801b2c46  call    cs:__imp_SetErrorMode
0x1801b2c4d  nop     dword ptr [rax+rax+00h]
0x1801b2c52  jmp     short loc_1801B2C0C
0x1801b2c54  lea     r9, [rbp+0F00h+FileName]; lpFileName
0x1801b2c5b  xor     r8d, r8d; lpString
0x1801b2c5e  xor     edx, edx; lpKeyName
0x1801b2c60  xor     ecx, ecx; lpAppName
0x1801b2c62  call    cs:__imp_WritePrivateProfileStringW
0x1801b2c69  nop     dword ptr [rax+rax+00h]
0x1801b2c6e  lea     rax, [rbp+0F00h+FileName]
0x1801b2c75  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x1801b2c7a  mov     [rsp+1000h+nSize], 200h; nSize
0x1801b2c82  lea     r9, [rbp+0F00h+ReturnedString]; lpReturnedString
0x1801b2c89  lea     r8, c_szNULL; lpDefault
0x1801b2c90  xor     edx, edx; lpKeyName
0x1801b2c92  lea     r12, aAutorunAmd64; "AutoRun.Amd64"
0x1801b2c99  mov     rcx, r12; lpAppName
0x1801b2c9c  call    cs:__imp_GetPrivateProfileStringW
0x1801b2ca3  nop     dword ptr [rax+rax+00h]
0x1801b2ca8  mov     edi, eax
0x1801b2caa  test    eax, eax
0x1801b2cac  jnz     short loc_1801B2CEE
0x1801b2cae  lea     r12, aAutorun_0; "AutoRun"
0x1801b2cb5  lea     rax, [rbp+0F00h+FileName]
0x1801b2cbc  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x1801b2cc1  mov     [rsp+1000h+nSize], 200h; nSize
0x1801b2cc9  lea     r9, [rbp+0F00h+ReturnedString]; lpReturnedString
0x1801b2cd0  lea     r8, c_szNULL; lpDefault
0x1801b2cd7  xor     edx, edx; lpKeyName
0x1801b2cd9  lea     rcx, aAutorun_0; "AutoRun"
0x1801b2ce0  call    cs:__imp_GetPrivateProfileStringW
0x1801b2ce7  nop     dword ptr [rax+rax+00h]
0x1801b2cec  mov     edi, eax
0x1801b2cee  mov     ecx, esi; uMode
0x1801b2cf0  call    cs:__imp_SetErrorMode
0x1801b2cf7  nop     dword ptr [rax+rax+00h]
0x1801b2cfc  cmp     edi, 4
0x1801b2cff  jl      loc_1801B3416
0x1801b2d05  lea     rdi, [rbp+0F00h+ReturnedString]
0x1801b2d0c  or      esi, 0FFFFFFFFh
0x1801b2d0f  mov     eax, 40h ; '@'
0x1801b2d14  cmp     [rbp+0F00h+ReturnedString], r14w
0x1801b2d1c  jz      loc_1801B33B2
0x1801b2d22  mov     r15d, eax
0x1801b2d25  lea     rax, [rbp+0F00h+FileName]
0x1801b2d2c  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x1801b2d31  mov     [rsp+1000h+nSize], 104h; nSize
0x1801b2d39  lea     r9, [rsp+1000h+pszCmdTemplate]; lpReturnedString
0x1801b2d3e  lea     r8, c_szNULL; lpDefault
0x1801b2d45  mov     rdx, rdi; lpKeyName
0x1801b2d48  mov     rcx, r12; lpAppName
0x1801b2d4b  call    cs:__imp_GetPrivateProfileStringW
0x1801b2d52  nop     dword ptr [rax+rax+00h]
0x1801b2d57  lea     rdx, Operation; "open"
0x1801b2d5e  mov     rcx, rdi; pszStr1
0x1801b2d61  call    cs:__imp_StrCmpICW
0x1801b2d68  nop     dword ptr [rax+rax+00h]
0x1801b2d6d  test    eax, eax
0x1801b2d6f  jnz     loc_1801B2EE9
0x1801b2d75  mov     rax, [rbx]
0x1801b2d78  mov     rcx, rbx
0x1801b2d7b  mov     rax, [rax+188h]
0x1801b2d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2d87  test    eax, eax
0x1801b2d89  jz      loc_1801B3389
0x1801b2d8f  mov     rax, [rbx]
0x1801b2d92  mov     rcx, rbx
0x1801b2d95  mov     rax, [rax+0E8h]
0x1801b2d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2da1  mov     r14d, eax
0x1801b2da4  mov     rax, [rbx]
0x1801b2da7  mov     rcx, rbx
0x1801b2daa  mov     rax, [rax+0F0h]
0x1801b2db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2db6  mov     esi, eax
0x1801b2db8  lea     rdx, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x1801b2dbd  mov     rcx, rbx; this
0x1801b2dc0  call    ?_QualifyCommandToDrive@CMountPoint@@IEAAXPEAGK@Z; CMountPoint::_QualifyCommandToDrive(ushort *,ulong)
0x1801b2dc5  mov     [rsp+1000h+pv], 0
0x1801b2dce  mov     [rsp+1000h+ppszCommandLine], 0
0x1801b2dd7  xor     ecx, ecx; pv
0x1801b2dd9  call    cs:__imp_CoTaskMemFree
0x1801b2de0  nop     dword ptr [rax+rax+00h]
0x1801b2de5  mov     rcx, [rsp+1000h+pv]; pv
0x1801b2dea  call    cs:__imp_CoTaskMemFree
0x1801b2df1  nop     dword ptr [rax+rax+00h]
0x1801b2df6  xor     r9d, r9d; ppszParameters
0x1801b2df9  lea     r8, [rsp+1000h+ppszCommandLine]; ppszCommandLine
0x1801b2dfe  lea     rdx, [rsp+1000h+pv]; ppszApplication
0x1801b2e03  lea     rcx, [rsp+1000h+pszCmdTemplate]; pszCmdTemplate
0x1801b2e08  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1801b2e0f  nop     dword ptr [rax+rax+00h]
0x1801b2e14  test    eax, eax
0x1801b2e16  js      short loc_1801B2E37
0x1801b2e18  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x1801b2e20  mov     r9, [rsp+1000h+ppszCommandLine]; unsigned __int16 *
0x1801b2e25  xor     r8d, r8d; unsigned __int16 *
0x1801b2e28  lea     rdx, aShellAutorunCo; "shell\\AutoRun\\command"
0x1801b2e2f  mov     rcx, rbx; this
0x1801b2e32  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b2e37  and     sil, 6
0x1801b2e3b  neg     sil
0x1801b2e3e  sbb     edx, edx
0x1801b2e40  neg     edx
0x1801b2e42  add     edx, 440Bh; uID
0x1801b2e48  mov     r9d, r15d; cchBufferMax
0x1801b2e4b  lea     r8, [rbp+0F00h+Buffer]; lpBuffer
0x1801b2e52  mov     rcx, cs:g_hinst; hInstance
0x1801b2e59  call    cs:__imp_LoadStringW
0x1801b2e60  nop     dword ptr [rax+rax+00h]
0x1801b2e65  or      esi, 0FFFFFFFFh
0x1801b2e68  mov     [rsp+1000h+nSize], esi; unsigned int
0x1801b2e6c  lea     r9, [rbp+0F00h+Buffer]; unsigned __int16 *
0x1801b2e73  xor     r8d, r8d; unsigned __int16 *
0x1801b2e76  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x1801b2e7d  mov     rcx, rbx; this
0x1801b2e80  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b2e85  mov     [rsp+1000h+nSize], esi; unsigned int
0x1801b2e89  lea     r9, pszStart; unsigned __int16 *
0x1801b2e90  lea     r8, aSetworkingdire; "SetWorkingDirectoryFromTarget"
0x1801b2e97  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x1801b2e9e  mov     rcx, rbx; this
0x1801b2ea1  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b2ea6  test    r14d, 0FE0h
0x1801b2ead  jz      short loc_1801B2ECD
0x1801b2eaf  mov     [rsp+1000h+nSize], esi; unsigned int
0x1801b2eb3  lea     r9, aAutorun_0; "AutoRun"
0x1801b2eba  xor     r8d, r8d; unsigned __int16 *
0x1801b2ebd  lea     rdx, c_szShell; "Shell"
0x1801b2ec4  mov     rcx, rbx; this
0x1801b2ec7  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b2ecc  nop
0x1801b2ecd  mov     rcx, [rsp+1000h+ppszCommandLine]; pv
0x1801b2ed2  call    cs:__imp_CoTaskMemFree
0x1801b2ed9  nop     dword ptr [rax+rax+00h]
0x1801b2ede  nop
0x1801b2edf  mov     rcx, [rsp+1000h+pv]
0x1801b2ee4  jmp     loc_1801B30D8
0x1801b2ee9  lea     rdx, aShellexecute; "ShellExecute"
0x1801b2ef0  mov     rcx, rdi; pszStr1
0x1801b2ef3  call    cs:__imp_StrCmpICW
0x1801b2efa  nop     dword ptr [rax+rax+00h]
0x1801b2eff  test    eax, eax
0x1801b2f01  jnz     loc_1801B30EC
0x1801b2f07  mov     rax, [rbx]
0x1801b2f0a  mov     rcx, rbx
0x1801b2f0d  mov     rax, [rax+188h]
0x1801b2f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2f19  test    eax, eax
0x1801b2f1b  jz      loc_1801B3389
0x1801b2f21  mov     rax, [rbx]
0x1801b2f24  mov     rcx, rbx
0x1801b2f27  mov     rax, [rax+0E8h]
0x1801b2f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2f33  mov     r14d, eax
0x1801b2f36  mov     rax, [rbx]
0x1801b2f39  mov     rcx, rbx
0x1801b2f3c  mov     rax, [rax+0F0h]
0x1801b2f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2f48  mov     esi, eax
0x1801b2f4a  mov     r8d, 208h; nSize
0x1801b2f50  lea     rdx, [rbp+0F00h+Dst]; lpDst
0x1801b2f57  lea     rcx, aWindirSystem32_2; "\"%windir%\\system32\\RunDLL32.EXE\" Sh"...
0x1801b2f5e  call    cs:__imp_ExpandEnvironmentStringsW
0x1801b2f65  nop     dword ptr [rax+rax+00h]
0x1801b2f6a  test    eax, eax
0x1801b2f6c  jz      loc_1801B3383
0x1801b2f72  lea     rdx, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x1801b2f77  mov     rcx, rbx; this
0x1801b2f7a  call    ?_QualifyCommandToDrive@CMountPoint@@IEAAXPEAGK@Z; CMountPoint::_QualifyCommandToDrive(ushort *,ulong)
0x1801b2f7f  lea     r8, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x1801b2f84  mov     edx, 208h; unsigned __int64
0x1801b2f89  lea     rcx, [rbp+0F00h+Dst]; unsigned __int16 *
0x1801b2f90  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b2f95  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x1801b2f9d  lea     r9, [rbp+0F00h+Dst]; unsigned __int16 *
0x1801b2fa4  xor     r8d, r8d; unsigned __int16 *
0x1801b2fa7  lea     rdx, aShellAutorunCo; "shell\\AutoRun\\command"
0x1801b2fae  mov     rcx, rbx; this
0x1801b2fb1  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b2fb6  mov     [rsp+1000h+ppszApplication], 0
0x1801b2fbf  mov     [rsp+1000h+var_FC0], 0
0x1801b2fc8  xor     ecx, ecx; pv
0x1801b2fca  call    cs:__imp_CoTaskMemFree
0x1801b2fd1  nop     dword ptr [rax+rax+00h]
0x1801b2fd6  mov     rcx, [rsp+1000h+ppszApplication]; pv
0x1801b2fdb  call    cs:__imp_CoTaskMemFree
0x1801b2fe2  nop     dword ptr [rax+rax+00h]
0x1801b2fe7  xor     r9d, r9d; ppszParameters
0x1801b2fea  lea     r8, [rsp+1000h+var_FC0]; ppszCommandLine
0x1801b2fef  lea     rdx, [rsp+1000h+ppszApplication]; ppszApplication
0x1801b2ff4  lea     rcx, [rsp+1000h+pszCmdTemplate]; pszCmdTemplate
0x1801b2ff9  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1801b3000  nop     dword ptr [rax+rax+00h]
0x1801b3005  test    eax, eax
0x1801b3007  js      short loc_1801B302C
0x1801b3009  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x1801b3011  mov     r9, [rsp+1000h+var_FC0]; unsigned __int16 *
0x1801b3016  lea     r8, aShellexecute; "ShellExecute"
0x1801b301d  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x1801b3024  mov     rcx, rbx; this
0x1801b3027  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x1801b302c  and     sil, 6
0x1801b3030  neg     sil
0x1801b3033  sbb     edx, edx
0x1801b3035  neg     edx
0x1801b3037  add     edx, 440Bh; uID
  ... truncated ...
```
