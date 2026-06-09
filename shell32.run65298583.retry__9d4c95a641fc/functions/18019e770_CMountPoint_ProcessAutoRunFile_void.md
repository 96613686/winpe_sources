# CMountPoint::_ProcessAutoRunFile(void)

- ea: `0x18019e770`
- end: `0x18019f022`
- name: `?_ProcessAutoRunFile@CMountPoint@@QEAAHXZ`
- size: `2226`
- prototype: `__int64 __fastcall(CMountPoint *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802dde5c`
- `0x1802e49a0`
- `0x180545b48`

## callees

- `0x18001bf10`
- `0x18001f630`
- `0x1800be5c0`
- `0x18015a3a4`
- `0x18019e770`
- `0x180233280`
- `0x180270988`
- `0x180427108`
- `0x1805429ac`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e8c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e8e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e978`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e8c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e8e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18019e978`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18019eabd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18019ec89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18019eabd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18019ec89`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18019ebb0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18019ebb0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019e9dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019eb4b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ed1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019edd5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee88`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019e9dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019eb4b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ed1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019edd5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee88`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18019ee9e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18019ef1f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18019ef1f`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18019e8fc`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18019e8fc`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e930`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e96e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e9cd`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e930`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e96e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18019e9cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019ef0f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019ef0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ea4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ea5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019eb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ecfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019edb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019edc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ea4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ea5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019eb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ecfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ed6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019edb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019edc0`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18019e8da`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18019e8da`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ea72`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ec39`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ed89`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ea72`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ec39`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x18019ed89`

## string_xrefs

- `0x18019ef15`: `command`
- `0x18019ea8c`: `shell\AutoRun\command`
- `0x18019ebf3`: `shell\AutoRun\command`
- `0x18019eaee`: `SetWorkingDirectoryFromTarget`
- `0x18019ecb8`: `SetWorkingDirectoryFromTarget`
- `0x18019ef43`: `SetWorkingDirectoryFromTarget`
- `0x18019eba9`: `"%windir%\system32\RunDLL32.EXE" Shell32.DLL,ShellExec_RunDLL `

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
    if ( !(unsigned int)IsPathSafeForAutoplay(FileName) )
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
              (const unsigned __int16 *)&pszStart,
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
              (const unsigned __int16 *)&pszStart,
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
                  CRegSupport::RSSetTextValue(
                    this,
                    v10,
                    L"SetWorkingDirectoryFromTarget",
                    (const unsigned __int16 *)&pszStart,
                    0xFFFFFFFF);
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
0x18019e770  push    rbp
0x18019e772  push    rbx
0x18019e773  push    rsi
0x18019e774  push    rdi
0x18019e775  push    r12
0x18019e777  push    r13
0x18019e779  push    r14
0x18019e77b  push    r15
0x18019e77d  lea     rbp, [rsp-0EC8h]
0x18019e785  sub     rsp, 0FC8h
0x18019e78c  mov     rax, cs:__security_cookie
0x18019e793  xor     rax, rsp
0x18019e796  mov     [rbp+0F00h+var_50], rax
0x18019e79d  mov     rbx, rcx
0x18019e7a0  mov     r15d, 1
0x18019e7a6  xor     r14d, r14d
0x18019e7a9  cmp     [rcx+23Ch], r14d
0x18019e7b0  jnz     loc_18019EFFC
0x18019e7b6  mov     rax, [rcx]
0x18019e7b9  mov     rax, [rax+188h]
0x18019e7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e7c5  mov     rdx, [rbx]
0x18019e7c8  mov     rcx, rbx
0x18019e7cb  test    eax, eax
0x18019e7cd  jz      short loc_18019E80A
0x18019e7cf  mov     rax, [rdx+1E8h]
0x18019e7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e7db  test    eax, eax
0x18019e7dd  jz      loc_18019EFF2
0x18019e7e3  mov     rcx, rbx; this
0x18019e7e6  call    ?CanUseVolume@CMtPtLocal@@QEBAHXZ; CMtPtLocal::CanUseVolume(void)
0x18019e7eb  test    eax, eax
0x18019e7ed  jz      short loc_18019E84A
0x18019e7ef  mov     rax, [rbx+240h]
0x18019e7f6  mov     ecx, [rax+38h]
0x18019e7f9  and     ecx, 101h
0x18019e7ff  cmp     ecx, r15d
0x18019e802  jnz     loc_18019EFF2
0x18019e808  jmp     short loc_18019E84A
0x18019e80a  mov     rax, [rdx+168h]
0x18019e811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e816  test    eax, eax
0x18019e818  jnz     short loc_18019E84A
0x18019e81a  mov     rax, [rbx]
0x18019e81d  mov     rcx, rbx
0x18019e820  mov     rax, [rax+160h]
0x18019e827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e82c  test    eax, eax
0x18019e82e  jnz     short loc_18019E84A
0x18019e830  mov     rax, [rbx]
0x18019e833  mov     rcx, rbx
0x18019e836  mov     rax, [rax+1D8h]
0x18019e83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e842  test    eax, eax
0x18019e844  jz      loc_18019EFF2
0x18019e84a  mov     rax, [rbx]
0x18019e84d  lea     rdx, pszBagName; "Shell"
0x18019e854  mov     rcx, rbx
0x18019e857  mov     rax, [rax+20h]
0x18019e85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e860  mov     rax, [rbx]
0x18019e863  lea     rdx, aAutorun; "_Autorun"
0x18019e86a  mov     rcx, rbx
0x18019e86d  mov     rax, [rax+20h]
0x18019e871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e876  lea     r13, [rbx+34h]
0x18019e87a  mov     r8, r13; unsigned __int16 *
0x18019e87d  mov     r10d, 104h
0x18019e883  mov     edx, r10d; unsigned __int64
0x18019e886  lea     rcx, [rbp+0F00h+FileName]; unsigned __int16 *
0x18019e88d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18019e892  lea     r8, aAutorunInf_0; "AutoRun.inf"
0x18019e899  mov     edx, r10d; unsigned __int64
0x18019e89c  lea     rcx, [rbp+0F00h+FileName]; unsigned __int16 *
0x18019e8a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18019e8a8  lea     rcx, [rbp+0F00h+FileName]; lpFileName
0x18019e8af  call    IsPathSafeForAutoplay
0x18019e8b4  test    eax, eax
0x18019e8b6  jnz     short loc_18019E8C6
0x18019e8b8  mov     [rbx+23Ch], r15d
0x18019e8bf  xor     eax, eax
0x18019e8c1  jmp     loc_18019EFFF
0x18019e8c6  mov     ecx, r15d; uMode
0x18019e8c9  call    cs:__imp_SetErrorMode
0x18019e8cf  mov     esi, eax
0x18019e8d1  xor     edx, edx
0x18019e8d3  lea     rcx, [rbp+0F00h+FileName]
0x18019e8da  call    cs:__imp_PathFileExistsAndAttributesW
0x18019e8e0  test    eax, eax
0x18019e8e2  jnz     short loc_18019E8EE
0x18019e8e4  mov     ecx, esi; uMode
0x18019e8e6  call    cs:__imp_SetErrorMode
0x18019e8ec  jmp     short loc_18019E8B8
0x18019e8ee  lea     r9, [rbp+0F00h+FileName]; lpFileName
0x18019e8f5  xor     r8d, r8d; lpString
0x18019e8f8  xor     edx, edx; lpKeyName
0x18019e8fa  xor     ecx, ecx; lpAppName
0x18019e8fc  call    cs:__imp_WritePrivateProfileStringW
0x18019e902  lea     rax, [rbp+0F00h+FileName]
0x18019e909  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x18019e90e  mov     [rsp+1000h+nSize], 200h; nSize
0x18019e916  lea     r9, [rbp+0F00h+ReturnedString]; lpReturnedString
0x18019e91d  lea     r8, c_szNULL; lpDefault
0x18019e924  xor     edx, edx; lpKeyName
0x18019e926  lea     r12, aAutorunAmd64; "AutoRun.Amd64"
0x18019e92d  mov     rcx, r12; lpAppName
0x18019e930  call    cs:__imp_GetPrivateProfileStringW
0x18019e936  mov     edi, eax
0x18019e938  test    eax, eax
0x18019e93a  jnz     short loc_18019E976
0x18019e93c  lea     r12, aAutorun_0; "AutoRun"
0x18019e943  lea     rax, [rbp+0F00h+FileName]
0x18019e94a  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x18019e94f  mov     [rsp+1000h+nSize], 200h; nSize
0x18019e957  lea     r9, [rbp+0F00h+ReturnedString]; lpReturnedString
0x18019e95e  lea     r8, c_szNULL; lpDefault
0x18019e965  xor     edx, edx; lpKeyName
0x18019e967  lea     rcx, aAutorun_0; "AutoRun"
0x18019e96e  call    cs:__imp_GetPrivateProfileStringW
0x18019e974  mov     edi, eax
0x18019e976  mov     ecx, esi; uMode
0x18019e978  call    cs:__imp_SetErrorMode
0x18019e97e  cmp     edi, 4
0x18019e981  jl      loc_18019EFEF
0x18019e987  lea     rdi, [rbp+0F00h+ReturnedString]
0x18019e98e  or      esi, 0FFFFFFFFh
0x18019e991  mov     eax, 40h ; '@'
0x18019e996  cmp     [rbp+0F00h+ReturnedString], r14w
0x18019e99e  jz      loc_18019EF8B
0x18019e9a4  mov     r15d, eax
0x18019e9a7  lea     rax, [rbp+0F00h+FileName]
0x18019e9ae  mov     [rsp+1000h+lpFileName], rax; lpFileName
0x18019e9b3  mov     [rsp+1000h+nSize], 104h; nSize
0x18019e9bb  lea     r9, [rsp+1000h+pszCmdTemplate]; lpReturnedString
0x18019e9c0  lea     r8, c_szNULL; lpDefault
0x18019e9c7  mov     rdx, rdi; lpKeyName
0x18019e9ca  mov     rcx, r12; lpAppName
0x18019e9cd  call    cs:__imp_GetPrivateProfileStringW
0x18019e9d3  lea     rdx, Operation; "open"
0x18019e9da  mov     rcx, rdi; pszStr1
0x18019e9dd  call    cs:__imp_StrCmpICW
0x18019e9e3  test    eax, eax
0x18019e9e5  jnz     loc_18019EB41
0x18019e9eb  mov     rax, [rbx]
0x18019e9ee  mov     rcx, rbx
0x18019e9f1  mov     rax, [rax+188h]
0x18019e9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e9fd  test    eax, eax
0x18019e9ff  jz      loc_18019EF62
0x18019ea05  mov     rax, [rbx]
0x18019ea08  mov     rcx, rbx
0x18019ea0b  mov     rax, [rax+0E8h]
0x18019ea12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea17  mov     r14d, eax
0x18019ea1a  mov     rax, [rbx]
0x18019ea1d  mov     rcx, rbx
0x18019ea20  mov     rax, [rax+0F0h]
0x18019ea27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ea2c  mov     esi, eax
0x18019ea2e  lea     rdx, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x18019ea33  mov     rcx, rbx; this
0x18019ea36  call    ?_QualifyCommandToDrive@CMountPoint@@IEAAXPEAGK@Z; CMountPoint::_QualifyCommandToDrive(ushort *,ulong)
0x18019ea3b  mov     [rsp+1000h+pv], 0
0x18019ea44  mov     [rsp+1000h+ppszCommandLine], 0
0x18019ea4d  xor     ecx, ecx; pv
0x18019ea4f  call    cs:__imp_CoTaskMemFree
0x18019ea55  mov     rcx, [rsp+1000h+pv]; pv
0x18019ea5a  call    cs:__imp_CoTaskMemFree
0x18019ea60  xor     r9d, r9d; ppszParameters
0x18019ea63  lea     r8, [rsp+1000h+ppszCommandLine]; ppszCommandLine
0x18019ea68  lea     rdx, [rsp+1000h+pv]; ppszApplication
0x18019ea6d  lea     rcx, [rsp+1000h+pszCmdTemplate]; pszCmdTemplate
0x18019ea72  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18019ea78  test    eax, eax
0x18019ea7a  js      short loc_18019EA9B
0x18019ea7c  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x18019ea84  mov     r9, [rsp+1000h+ppszCommandLine]; unsigned __int16 *
0x18019ea89  xor     r8d, r8d; unsigned __int16 *
0x18019ea8c  lea     rdx, aShellAutorunCo; "shell\\AutoRun\\command"
0x18019ea93  mov     rcx, rbx; this
0x18019ea96  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019ea9b  and     sil, 6
0x18019ea9f  neg     sil
0x18019eaa2  sbb     edx, edx
0x18019eaa4  neg     edx
0x18019eaa6  add     edx, 440Bh; uID
0x18019eaac  mov     r9d, r15d; cchBufferMax
0x18019eaaf  lea     r8, [rbp+0F00h+Buffer]; lpBuffer
0x18019eab6  mov     rcx, cs:g_hinst; hInstance
0x18019eabd  call    cs:__imp_LoadStringW
0x18019eac3  or      esi, 0FFFFFFFFh
0x18019eac6  mov     [rsp+1000h+nSize], esi; unsigned int
0x18019eaca  lea     r9, [rbp+0F00h+Buffer]; unsigned __int16 *
0x18019ead1  xor     r8d, r8d; unsigned __int16 *
0x18019ead4  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x18019eadb  mov     rcx, rbx; this
0x18019eade  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019eae3  mov     [rsp+1000h+nSize], esi; unsigned int
0x18019eae7  lea     r9, pszStart; unsigned __int16 *
0x18019eaee  lea     r8, aSetworkingdire; "SetWorkingDirectoryFromTarget"
0x18019eaf5  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x18019eafc  mov     rcx, rbx; this
0x18019eaff  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019eb04  test    r14d, 0FE0h
0x18019eb0b  jz      short loc_18019EB2B
0x18019eb0d  mov     [rsp+1000h+nSize], esi; unsigned int
0x18019eb11  lea     r9, aAutorun_0; "AutoRun"
0x18019eb18  xor     r8d, r8d; unsigned __int16 *
0x18019eb1b  lea     rdx, c_szShell; "Shell"
0x18019eb22  mov     rcx, rbx; this
0x18019eb25  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019eb2a  nop
0x18019eb2b  mov     rcx, [rsp+1000h+ppszCommandLine]; pv
0x18019eb30  call    cs:__imp_CoTaskMemFree
0x18019eb36  nop
0x18019eb37  mov     rcx, [rsp+1000h+pv]
0x18019eb3c  jmp     loc_18019ED06
0x18019eb41  lea     rdx, aShellexecute; "ShellExecute"
0x18019eb48  mov     rcx, rdi; pszStr1
0x18019eb4b  call    cs:__imp_StrCmpICW
0x18019eb51  test    eax, eax
0x18019eb53  jnz     loc_18019ED14
0x18019eb59  mov     rax, [rbx]
0x18019eb5c  mov     rcx, rbx
0x18019eb5f  mov     rax, [rax+188h]
0x18019eb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb6b  test    eax, eax
0x18019eb6d  jz      loc_18019EF62
0x18019eb73  mov     rax, [rbx]
0x18019eb76  mov     rcx, rbx
0x18019eb79  mov     rax, [rax+0E8h]
0x18019eb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb85  mov     r14d, eax
0x18019eb88  mov     rax, [rbx]
0x18019eb8b  mov     rcx, rbx
0x18019eb8e  mov     rax, [rax+0F0h]
0x18019eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb9a  mov     esi, eax
0x18019eb9c  mov     r8d, 208h; nSize
0x18019eba2  lea     rdx, [rbp+0F00h+Dst]; lpDst
0x18019eba9  lea     rcx, aWindirSystem32_2; "\"%windir%\\system32\\RunDLL32.EXE\" Sh"...
0x18019ebb0  call    cs:__imp_ExpandEnvironmentStringsW
0x18019ebb6  test    eax, eax
0x18019ebb8  jz      loc_18019EF5C
0x18019ebbe  lea     rdx, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x18019ebc3  mov     rcx, rbx; this
0x18019ebc6  call    ?_QualifyCommandToDrive@CMountPoint@@IEAAXPEAGK@Z; CMountPoint::_QualifyCommandToDrive(ushort *,ulong)
0x18019ebcb  lea     r8, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x18019ebd0  mov     edx, 208h; unsigned __int64
0x18019ebd5  lea     rcx, [rbp+0F00h+Dst]; unsigned __int16 *
0x18019ebdc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18019ebe1  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x18019ebe9  lea     r9, [rbp+0F00h+Dst]; unsigned __int16 *
0x18019ebf0  xor     r8d, r8d; unsigned __int16 *
0x18019ebf3  lea     rdx, aShellAutorunCo; "shell\\AutoRun\\command"
0x18019ebfa  mov     rcx, rbx; this
0x18019ebfd  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019ec02  mov     [rsp+1000h+ppszApplication], 0
0x18019ec0b  mov     [rsp+1000h+var_FC0], 0
0x18019ec14  xor     ecx, ecx; pv
0x18019ec16  call    cs:__imp_CoTaskMemFree
0x18019ec1c  mov     rcx, [rsp+1000h+ppszApplication]; pv
0x18019ec21  call    cs:__imp_CoTaskMemFree
0x18019ec27  xor     r9d, r9d; ppszParameters
0x18019ec2a  lea     r8, [rsp+1000h+var_FC0]; ppszCommandLine
0x18019ec2f  lea     rdx, [rsp+1000h+ppszApplication]; ppszApplication
0x18019ec34  lea     rcx, [rsp+1000h+pszCmdTemplate]; pszCmdTemplate
0x18019ec39  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18019ec3f  test    eax, eax
0x18019ec41  js      short loc_18019EC66
0x18019ec43  mov     [rsp+1000h+nSize], 0FFFFFFFFh; unsigned int
0x18019ec4b  mov     r9, [rsp+1000h+var_FC0]; unsigned __int16 *
0x18019ec50  lea     r8, aShellexecute; "ShellExecute"
0x18019ec57  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x18019ec5e  mov     rcx, rbx; this
0x18019ec61  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019ec66  and     sil, 6
0x18019ec6a  neg     sil
0x18019ec6d  sbb     edx, edx
0x18019ec6f  neg     edx
0x18019ec71  add     edx, 440Bh; uID
0x18019ec77  mov     r9d, 104h; cchBufferMax
0x18019ec7d  lea     r8, [rsp+1000h+pszCmdTemplate]; lpBuffer
0x18019ec82  mov     rcx, cs:g_hinst; hInstance
0x18019ec89  call    cs:__imp_LoadStringW
0x18019ec8f  or      esi, 0FFFFFFFFh
0x18019ec92  mov     [rsp+1000h+nSize], esi; unsigned int
0x18019ec96  lea     r9, [rsp+1000h+pszCmdTemplate]; unsigned __int16 *
0x18019ec9b  xor     r8d, r8d; unsigned __int16 *
0x18019ec9e  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x18019eca5  mov     rcx, rbx; this
0x18019eca8  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019ecad  mov     [rsp+1000h+nSize], esi; unsigned int
0x18019ecb1  lea     r9, pszStart; unsigned __int16 *
0x18019ecb8  lea     r8, aSetworkingdire; "SetWorkingDirectoryFromTarget"
0x18019ecbf  lea     rdx, aShellAutorun; "shell\\AutoRun"
0x18019ecc6  mov     rcx, rbx; this
0x18019ecc9  call    ?RSSetTextValue@CRegSupport@@QEAAHPEBG00K@Z; CRegSupport::RSSetTextValue(ushort const *,ushort const *,ushort const *,ulong)
0x18019ecce  test    r14d, 0FE0h
0x18019ecd5  jz      short loc_18019ECF5
  ... truncated ...
```
