# COpenControlPanel::Open(ushort const *,ushort const *,IUnknown *)

- ea: `0x1802fb4d0`
- end: `0x1802fbb32`
- name: `?Open@COpenControlPanel@@UEAAJPEBG0PEAUIUnknown@@@Z`
- size: `1634`
- prototype: `__int64 __fastcall(COpenControlPanel *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802fa7c0`
- `0x1802fb4d0`

## callees

- `0x180015ad8`
- `0x18001f630`
- `0x1800208d8`
- `0x1800247bc`
- `0x18003eab0`
- `0x180073848`
- `0x180091458`
- `0x1801143b4`
- `0x1801b44ec`
- `0x1801d7e88`
- `0x18021f1a8`
- `0x180233280`
- `0x1802342fc`
- `0x180277854`
- `0x1802fb4d0`
- `0x1802fc338`
- `0x1802fc780`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb583`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb5c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb8bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb8fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb91f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb583`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb5c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb8bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb8fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802fb91f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802fb943`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802fb943`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802fb7e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802fb7e1`
- `USER32!MonitorFromPoint` at `0x1802fb76d`
- `USER32!MonitorFromPoint` at `0x1802fb968`
- `USER32!MonitorFromPoint` at `0x1802fb76d`
- `USER32!MonitorFromPoint` at `0x1802fb968`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802fbad4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802fbad4`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1802fb515`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1802fb515`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1802fb559`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1802fb559`
- `Windows.Storage!ShellExecuteExW` at `0x1802fb782`
- `Windows.Storage!ShellExecuteExW` at `0x1802fb97d`
- `Windows.Storage!ShellExecuteExW` at `0x1802fb782`
- `Windows.Storage!ShellExecuteExW` at `0x1802fb97d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COpenControlPanel::Open(
        COpenControlPanel *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4)
{
  signed int Error; // edi
  __int64 v9; // r8
  HWND v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // r9d
  const WCHAR *v14; // rax
  HWND v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  WCHAR *v20; // rax
  bool v21; // r15
  LPCWCH v22; // rbx
  const unsigned __int16 *v23; // r8
  const WCHAR *ArgsW; // rax
  bool v25; // zf
  const WCHAR *v26; // rax
  const size_t *v27; // rcx
  int v28; // eax
  int fuStyle; // [rsp+20h] [rbp-E0h]
  bool v30; // [rsp+40h] [rbp-C0h] BYREF
  bool v31; // [rsp+41h] [rbp-BFh] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-B8h]
  HWND phwnd; // [rsp+50h] [rbp-B0h] BYREF
  HWND hWnd; // [rsp+58h] [rbp-A8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[784]; // [rsp+2E0h] [rbp+1E0h] BYREF

  lpString1 = a2;
  if ( !(unsigned int)SHWindowsPolicy(POLID_NoControlPanel) )
  {
    if ( CompareStringOrdinal(a2, -1, L"Microsoft.NetworkAndSharingCenter", -1, 1) == 2 )
      _Fire_CommandHandlerInvokeTelemetry(13586, 0, v11, 2, 0, *((_QWORD *)this - 13), 0);
    if ( CompareStringOrdinal(a2, -1, L"Microsoft.DevicesAndPrinters", -1, 1) == 2 )
      return LaunchRedirectedControlPanelEntryPoint(L"ms-settings:devices");
    v30 = 0;
    v31 = 0;
    Error = COpenControlPanel::_GetPathWithLegacyCheck(
              (COpenControlPanel *)((char *)this - 112),
              a2,
              v36,
              v12,
              a3 != 0,
              &v30,
              &v31);
    if ( Error < 0 )
      goto LABEL_44;
    if ( v36[0] != 58 || v36[1] != 58 )
    {
      if ( v30 )
      {
        if ( (unsigned int)SHExpandEnvironmentStringsW(v36, pszPath, 780) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromLastError();
          if ( Error < 0 )
            goto LABEL_44;
        }
        memset_0(&pExecInfo.fMask, 0, 0x6Cu);
        pExecInfo.cbSize = 112;
        phwnd = 0;
        GetWindowFromSite(a4, &phwnd);
        pExecInfo.hwnd = phwnd;
        pExecInfo.nShow = 1;
        pExecInfo.fMask = 67109120;
        pExecInfo.lpFile = pszPath;
        v21 = v31;
        if ( v31 )
        {
          if ( a3 )
          {
            Error = StringCchCatW(pszPath, 0x30Cu, L" ,");
            if ( Error < 0 )
              goto LABEL_44;
            Error = StringCchCatW(pszPath, 0x30Cu, a3);
          }
          if ( Error < 0 )
            goto LABEL_44;
        }
        ArgsW = PathGetArgsW(pszPath);
        if ( ArgsW && *ArgsW )
        {
          pExecInfo.lpParameters = ArgsW;
          *((_WORD *)ArgsW - 1) = 0;
        }
        if ( (*((_BYTE *)this - 68) & 8) != 0 )
        {
          pExecInfo.hIcon = MonitorFromPoint(*(POINT *)((char *)this - 60), 0);
          pExecInfo.fMask |= 0x200000u;
        }
        if ( ShellExecuteExW(&pExecInfo) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            goto LABEL_44;
        }
        if ( !v21 )
          return (unsigned int)Error;
        v25 = *((_BYTE *)this + 572) == 0;
      }
      else
      {
        v26 = (const WCHAR *)&pszStart;
        v27 = (const size_t *)a3;
        if ( a3 )
        {
          if ( *a3 )
            v26 = L",";
        }
        else
        {
          v27 = &pszStart;
        }
        Error = StringCchPrintfW(pszPath, 0x30Cu, L"%s%s%s", v36, v26, v27);
        if ( Error < 0 )
          goto LABEL_44;
        phwnd = 0;
        GetWindowFromSite(a4, &phwnd);
        v28 = CPL_Open(pszPath, 0);
        Error = v28 == 0 ? 0x80004005 : 0;
        if ( !*((_BYTE *)this + 572) )
          goto LABEL_69;
        v25 = v28 == 0;
      }
      if ( !v25 )
        COpenControlPanel::_AddtoRecentDocs((COpenControlPanel *)((char *)this - 112), 0, 1);
LABEL_69:
      if ( Error >= 0 )
        return (unsigned int)Error;
LABEL_44:
      v22 = lpString1;
      if ( CompareStringOrdinal(lpString1, -1, L"Microsoft.Personalization", -1, 1) != 2
        || IsPersonalizationFeatureAvailable() )
      {
        if ( (unsigned int)IsOS_OS_WOW6432() )
        {
          hWnd = 0;
          Error = CoCreateInstance(
                    &CLSID_OpenControlPanel,
                    0,
                    0x80004u,
                    &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
                    (LPVOID *)&hWnd);
          if ( Error >= 0 )
          {
            Error = (*(__int64 (__fastcall **)(HWND, LPCWCH, const unsigned __int16 *, _QWORD))(*(_QWORD *)hWnd + 24LL))(
                      hWnd,
                      v22,
                      a3,
                      0);
            (*(void (__fastcall **)(HWND))(*(_QWORD *)hWnd + 16LL))(hWnd);
          }
        }
        return (unsigned int)Error;
      }
      if ( !a3 || CompareStringOrdinal(a3, -1, L"pageColorization", -1, 1) == 2 )
      {
        v23 = L"WindowColor";
      }
      else
      {
        if ( CompareStringOrdinal(a3, -1, L"pageWallpaper", -1, 1) != 2 )
        {
          phwnd = 0;
          GetWindowFromSite(a4, &phwnd);
          v9 = 9737;
          v10 = phwnd;
          goto LABEL_3;
        }
        v23 = L"DesktopBackground";
      }
      return (unsigned int)COpenControlPanel::Open(this, L"Microsoft.Display", v23, a4);
    }
    if ( a3 && *a3 )
    {
      v14 = L",";
      if ( *a3 != 63 )
        v14 = L"\\";
    }
    else
    {
      v14 = (const WCHAR *)&pszStart;
    }
    Error = StringCchPrintfW(pszPath, 0x30Cu, L"%s%s", v36, v14);
    if ( Error < 0 )
      goto LABEL_44;
    v15 = 0;
    hWnd = 0;
    if ( a3 )
    {
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
      do
        ++v16;
      while ( pszPath[v16] );
      v18 = v16 + v17;
      Error = _AllocStringWorker<CTCoAllocPolicy>(
                v17,
                (__int64)pszPath,
                (const size_t *)pszPath,
                v16 + v17 + 1,
                fuStyle,
                &hWnd);
      if ( Error < 0 )
        goto LABEL_34;
      v19 = v18 + 1;
      v15 = hWnd;
      Error = StringCchCatW((unsigned __int16 *)hWnd, v19, a3);
    }
    if ( Error >= 0 )
    {
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.cbSize = 112;
      phwnd = 0;
      GetWindowFromSite(a4, &phwnd);
      pExecInfo.hwnd = phwnd;
      pExecInfo.nShow = 1;
      pExecInfo.fMask = 67109120;
      v20 = pszPath;
      if ( a3 )
        v20 = (WCHAR *)v15;
      pExecInfo.lpFile = v20;
      if ( (*((_BYTE *)this - 68) & 8) != 0 )
      {
        pExecInfo.hIcon = MonitorFromPoint(*(POINT *)((char *)this - 60), 0);
        pExecInfo.fMask |= 0x200000u;
      }
      if ( ShellExecuteExW(&pExecInfo) )
      {
        Error = 0;
        goto LABEL_32;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
      {
LABEL_32:
        if ( *((_BYTE *)this + 572) )
          COpenControlPanel::_AddtoRecentDocs((COpenControlPanel *)((char *)this - 112), a3, 0);
      }
    }
LABEL_34:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&hWnd);
    goto LABEL_69;
  }
  Error = -2147467259;
  hWnd = 0;
  GetWindowFromSite(a4, &hWnd);
  v9 = 9729;
  v10 = hWnd;
LABEL_3:
  ShellMessageBoxW(g_hinst, v10, (LPCWSTR)v9, (LPCWSTR)0x2600, 0x10u);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802fb4d0  push    rbp
0x1802fb4d2  push    rbx
0x1802fb4d3  push    rsi
0x1802fb4d4  push    rdi
0x1802fb4d5  push    r12
0x1802fb4d7  push    r13
0x1802fb4d9  push    r14
0x1802fb4db  push    r15
0x1802fb4dd  lea     rbp, [rsp-818h]
0x1802fb4e5  sub     rsp, 918h
0x1802fb4ec  mov     rax, cs:__security_cookie
0x1802fb4f3  xor     rax, rsp
0x1802fb4f6  mov     [rbp+850h+var_50], rax
0x1802fb4fd  mov     r12, r9
0x1802fb500  mov     rsi, r8
0x1802fb503  mov     rdi, rdx
0x1802fb506  mov     [rsp+950h+lpString1], rdx
0x1802fb50b  mov     r14, rcx
0x1802fb50e  lea     rcx, POLID_NoControlPanel
0x1802fb515  call    cs:__imp_SHWindowsPolicy
0x1802fb51b  xor     r15d, r15d
0x1802fb51e  test    eax, eax
0x1802fb520  jz      short loc_1802FB564
0x1802fb522  mov     edi, 80004005h
0x1802fb527  mov     [rsp+950h+hWnd], r15
0x1802fb52c  lea     rdx, [rsp+950h+hWnd]; phwnd
0x1802fb531  mov     rcx, r12; punk
0x1802fb534  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x1802fb539  mov     r8d, 2601h; lpcText
0x1802fb53f  mov     rdx, [rsp+950h+hWnd]; hWnd
0x1802fb544  mov     r9d, 2600h; lpcTitle
0x1802fb54a  mov     [rsp+950h+fuStyle], 10h; fuStyle
0x1802fb552  mov     rcx, cs:g_hinst; hAppInst
0x1802fb559  call    cs:__imp_ShellMessageBoxW
0x1802fb55f  jmp     loc_1802FBB0D
0x1802fb564  lea     r13, [r14-70h]
0x1802fb568  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x1802fb570  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802fb574  mov     r9d, ebx; cchCount2
0x1802fb577  lea     r8, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x1802fb57e  mov     edx, ebx; cchCount1
0x1802fb580  mov     rcx, rdi; lpString1
0x1802fb583  call    cs:__imp_CompareStringOrdinal
0x1802fb589  cmp     eax, 2
0x1802fb58c  jnz     short loc_1802FB5B1
0x1802fb58e  mov     dword ptr [rsp+950h+var_920], r15d
0x1802fb593  mov     rax, [r13+8]
0x1802fb597  mov     [rsp+950h+var_928], rax
0x1802fb59c  mov     qword ptr [rsp+950h+fuStyle], r15
0x1802fb5a1  xor     edx, edx
0x1802fb5a3  mov     ecx, 3512h
0x1802fb5a8  lea     r9d, [rbx+3]
0x1802fb5ac  call    ?_Fire_CommandHandlerInvokeTelemetry@@YAXW4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_INVOCATION_LOCATION@@W4RIBBON_VISIBILITY@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIShellItem@@PEAUIUnknown@@K@Z; _Fire_CommandHandlerInvokeTelemetry(EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_INVOCATION_LOCATION,RIBBON_VISIBILITY,EXPLORER_COMMAND_SQM_SELECTED_STATE,IShellItem *,IUnknown *,ulong)
0x1802fb5b1  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x1802fb5b9  mov     r9d, ebx; cchCount2
0x1802fb5bc  lea     r8, aMicrosoftDevic_0; "Microsoft.DevicesAndPrinters"
0x1802fb5c3  mov     edx, ebx; cchCount1
0x1802fb5c5  mov     rcx, rdi; lpString1
0x1802fb5c8  call    cs:__imp_CompareStringOrdinal
0x1802fb5ce  cmp     eax, 2
0x1802fb5d1  jnz     short loc_1802FB5E4
0x1802fb5d3  lea     rcx, aMsSettingsDevi; "ms-settings:devices"
0x1802fb5da  call    ?LaunchRedirectedControlPanelEntryPoint@@YAJPEBGW4CPLENTRYPOINT@@@Z; LaunchRedirectedControlPanelEntryPoint(ushort const *,CPLENTRYPOINT)
0x1802fb5df  jmp     loc_1802FBB0F
0x1802fb5e4  mov     [rsp+950h+var_910], r15b
0x1802fb5e9  mov     [rsp+950h+var_90F], r15b
0x1802fb5ee  test    rsi, rsi
0x1802fb5f1  setnz   al
0x1802fb5f4  lea     rcx, [rsp+950h+var_90F]
0x1802fb5f9  mov     [rsp+950h+var_920], rcx; bool *
0x1802fb5fe  lea     rcx, [rsp+950h+var_910]
0x1802fb603  mov     [rsp+950h+var_928], rcx; bool *
0x1802fb608  mov     byte ptr [rsp+950h+fuStyle], al; bool
0x1802fb60c  lea     r8, [rbp+850h+var_880]; unsigned __int16 *
0x1802fb610  mov     rdx, rdi; unsigned __int16 *
0x1802fb613  mov     rcx, r13; this
0x1802fb616  call    ?_GetPathWithLegacyCheck@COpenControlPanel@@AEAAJPEBGPEAGI_NPEA_N3@Z; COpenControlPanel::_GetPathWithLegacyCheck(ushort const *,ushort *,uint,bool,bool *,bool *)
0x1802fb61b  mov     edi, eax
0x1802fb61d  test    eax, eax
0x1802fb61f  js      loc_1802FB89E
0x1802fb625  mov     eax, 3Ah ; ':'
0x1802fb62a  cmp     ax, [rbp+850h+var_880]
0x1802fb62e  jnz     loc_1802FB7C3
0x1802fb634  cmp     ax, [rbp+850h+var_87E]
0x1802fb638  jnz     loc_1802FB7C3
0x1802fb63e  test    rsi, rsi
0x1802fb641  jz      short loc_1802FB663
0x1802fb643  cmp     [rsi], r15w
0x1802fb647  jz      short loc_1802FB663
0x1802fb649  lea     edx, [rax+5]
0x1802fb64c  lea     rcx, asc_1805D5234; "\\"
0x1802fb653  lea     rax, asc_1805DD41C; ","
0x1802fb65a  cmp     dx, [rsi]
0x1802fb65d  cmovnz  rax, rcx
0x1802fb661  jmp     short loc_1802FB66A
0x1802fb663  lea     rax, pszStart
0x1802fb66a  mov     qword ptr [rsp+950h+fuStyle], rax
0x1802fb66f  lea     r9, [rbp+850h+var_880]
0x1802fb673  lea     r8, aSS_6; "%s%s"
0x1802fb67a  mov     edx, 30Ch; unsigned __int64
0x1802fb67f  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x1802fb686  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802fb68b  mov     edi, eax
0x1802fb68d  test    eax, eax
0x1802fb68f  js      loc_1802FB89E
0x1802fb695  mov     rbx, r15
0x1802fb698  mov     [rsp+950h+hWnd], rbx
0x1802fb69d  test    rsi, rsi
0x1802fb6a0  jz      short loc_1802FB702
0x1802fb6a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802fb6a6  mov     rcx, rax
0x1802fb6a9  inc     rcx
0x1802fb6ac  cmp     [rsi+rcx*2], r15w
0x1802fb6b1  jnz     short loc_1802FB6A9
0x1802fb6b3  lea     rdx, [rbp+850h+pszPath]
0x1802fb6ba  inc     rax
0x1802fb6bd  cmp     [rdx+rax*2], r15w
0x1802fb6c2  jnz     short loc_1802FB6BA
0x1802fb6c4  lea     rbx, [rax+rcx]
0x1802fb6c8  lea     rax, [rsp+950h+hWnd]
0x1802fb6cd  mov     [rsp+950h+var_928], rax
0x1802fb6d2  lea     r9, [rbx+1]
0x1802fb6d6  lea     r8, [rbp+850h+pszPath]
0x1802fb6dd  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1802fb6e2  mov     edi, eax
0x1802fb6e4  test    eax, eax
0x1802fb6e6  js      loc_1802FB7B4
0x1802fb6ec  mov     r8, rsi; unsigned __int16 *
0x1802fb6ef  lea     rdx, [rbx+1]; unsigned __int64
0x1802fb6f3  mov     rbx, [rsp+950h+hWnd]
0x1802fb6f8  mov     rcx, rbx; unsigned __int16 *
0x1802fb6fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802fb700  mov     edi, eax
0x1802fb702  test    edi, edi
0x1802fb704  js      loc_1802FB7B4
0x1802fb70a  xor     edx, edx; Val
0x1802fb70c  lea     r8d, [rdx+6Ch]; Size
0x1802fb710  lea     rcx, [rsp+950h+pExecInfo.fMask]; void *
0x1802fb715  call    memset_0
0x1802fb71a  mov     [rsp+950h+pExecInfo.cbSize], 70h ; 'p'
0x1802fb722  mov     [rsp+950h+phwnd], r15
0x1802fb727  lea     rdx, [rsp+950h+phwnd]; phwnd
0x1802fb72c  mov     rcx, r12; punk
0x1802fb72f  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x1802fb734  mov     rax, [rsp+950h+phwnd]
0x1802fb739  mov     [rsp+950h+pExecInfo.hwnd], rax
0x1802fb73e  mov     [rbp+850h+pExecInfo.nShow], 1
0x1802fb745  mov     [rsp+950h+pExecInfo.fMask], 4000100h
0x1802fb74d  lea     rax, [rbp+850h+pszPath]
0x1802fb754  test    rsi, rsi
0x1802fb757  cmovnz  rax, rbx
0x1802fb75b  mov     [rsp+950h+pExecInfo.lpFile], rax
0x1802fb760  test    byte ptr [r14-44h], 8
0x1802fb765  jz      short loc_1802FB77D
0x1802fb767  xor     edx, edx; dwFlags
0x1802fb769  mov     rcx, [r14-3Ch]; pt
0x1802fb76d  call    cs:__imp_MonitorFromPoint
0x1802fb773  mov     qword ptr [rbp+850h+pExecInfo.60h], rax
0x1802fb777  bts     [rsp+950h+pExecInfo.fMask], 15h
0x1802fb77d  lea     rcx, [rsp+950h+pExecInfo]; pExecInfo
0x1802fb782  call    cs:__imp_ShellExecuteExW
0x1802fb788  test    eax, eax
0x1802fb78a  jz      short loc_1802FB791
0x1802fb78c  mov     edi, r15d
0x1802fb78f  jmp     short loc_1802FB79C
0x1802fb791  call    ResultFromKnownLastError
0x1802fb796  mov     edi, eax
0x1802fb798  test    eax, eax
0x1802fb79a  js      short loc_1802FB7B4
0x1802fb79c  cmp     [r14+23Ch], r15b
0x1802fb7a3  jz      short loc_1802FB7B4
0x1802fb7a5  xor     r8d, r8d; bool
0x1802fb7a8  mov     rdx, rsi; unsigned __int16 *
0x1802fb7ab  mov     rcx, r13; this
0x1802fb7ae  call    ?_AddtoRecentDocs@COpenControlPanel@@AEAAJPEBG_N@Z; COpenControlPanel::_AddtoRecentDocs(ushort const *,bool)
0x1802fb7b3  nop
0x1802fb7b4  lea     rcx, [rsp+950h+hWnd]
0x1802fb7b9  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1802fb7be  jmp     loc_1802FBA56
0x1802fb7c3  cmp     [rsp+950h+var_910], r15b
0x1802fb7c8  jz      loc_1802FB9B2
0x1802fb7ce  mov     ebx, 30Ch
0x1802fb7d3  mov     r8d, ebx
0x1802fb7d6  lea     rdx, [rbp+850h+pszPath]
0x1802fb7dd  lea     rcx, [rbp+850h+var_880]
0x1802fb7e1  call    cs:__imp_SHExpandEnvironmentStringsW
0x1802fb7e7  test    eax, eax
0x1802fb7e9  jz      short loc_1802FB7F0
0x1802fb7eb  mov     edi, r15d
0x1802fb7ee  jmp     short loc_1802FB7FF
0x1802fb7f0  call    ResultFromLastError
0x1802fb7f5  mov     edi, eax
0x1802fb7f7  test    eax, eax
0x1802fb7f9  js      loc_1802FB89E
0x1802fb7ff  xor     edx, edx; Val
0x1802fb801  lea     r8d, [rdx+6Ch]; Size
0x1802fb805  lea     rcx, [rsp+950h+pExecInfo.fMask]; void *
0x1802fb80a  call    memset_0
0x1802fb80f  mov     [rsp+950h+pExecInfo.cbSize], 70h ; 'p'
0x1802fb817  mov     [rsp+950h+phwnd], r15
0x1802fb81c  lea     rdx, [rsp+950h+phwnd]; phwnd
0x1802fb821  mov     rcx, r12; punk
0x1802fb824  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x1802fb829  mov     rax, [rsp+950h+phwnd]
0x1802fb82e  mov     [rsp+950h+pExecInfo.hwnd], rax
0x1802fb833  mov     [rbp+850h+pExecInfo.nShow], 1
0x1802fb83a  mov     [rsp+950h+pExecInfo.fMask], 4000100h
0x1802fb842  lea     rax, [rbp+850h+pszPath]
0x1802fb849  mov     [rsp+950h+pExecInfo.lpFile], rax
0x1802fb84e  mov     r15b, [rsp+950h+var_90F]
0x1802fb853  test    r15b, r15b
0x1802fb856  jz      loc_1802FB93A
0x1802fb85c  test    rsi, rsi
0x1802fb85f  jz      short loc_1802FB891
0x1802fb861  lea     r8, asc_1805DD5B0; " ,"
0x1802fb868  mov     rdx, rbx; unsigned __int64
0x1802fb86b  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x1802fb872  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802fb877  mov     edi, eax
0x1802fb879  test    eax, eax
0x1802fb87b  js      short loc_1802FB89B
0x1802fb87d  mov     r8, rsi; unsigned __int16 *
0x1802fb880  mov     rdx, rbx; unsigned __int64
0x1802fb883  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x1802fb88a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802fb88f  mov     edi, eax
0x1802fb891  xor     ebx, ebx
0x1802fb893  test    edi, edi
0x1802fb895  jns     loc_1802FB93C
0x1802fb89b  xor     r15d, r15d
0x1802fb89e  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x1802fb8a6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1802fb8aa  mov     r9d, r13d; cchCount2
0x1802fb8ad  lea     r8, aMicrosoftPerso; "Microsoft.Personalization"
0x1802fb8b4  mov     edx, r13d; cchCount1
0x1802fb8b7  mov     rbx, [rsp+950h+lpString1]
0x1802fb8bc  mov     rcx, rbx; lpString1
0x1802fb8bf  call    cs:__imp_CompareStringOrdinal
0x1802fb8c5  cmp     eax, 2
0x1802fb8c8  jnz     loc_1802FBAA2
0x1802fb8ce  call    ?IsPersonalizationFeatureAvailable@@YA_NXZ; IsPersonalizationFeatureAvailable(void)
0x1802fb8d3  test    al, al
0x1802fb8d5  jnz     loc_1802FBAA2
0x1802fb8db  test    rsi, rsi
0x1802fb8de  jz      loc_1802FBA85
0x1802fb8e4  lea     ebx, [r13+2]
0x1802fb8e8  mov     [rsp+950h+fuStyle], ebx; bIgnoreCase
0x1802fb8ec  mov     r9d, r13d; cchCount2
0x1802fb8ef  lea     r8, aPagecolorizati; "pageColorization"
0x1802fb8f6  mov     edx, r13d; cchCount1
0x1802fb8f9  mov     rcx, rsi; lpString1
0x1802fb8fc  call    cs:__imp_CompareStringOrdinal
0x1802fb902  cmp     eax, 2
0x1802fb905  jz      loc_1802FBA85
0x1802fb90b  mov     [rsp+950h+fuStyle], ebx; bIgnoreCase
0x1802fb90f  mov     r9d, r13d; cchCount2
0x1802fb912  lea     r8, aPagewallpaper; "pageWallpaper"
0x1802fb919  mov     edx, r13d; cchCount1
0x1802fb91c  mov     rcx, rsi; lpString1
0x1802fb91f  call    cs:__imp_CompareStringOrdinal
0x1802fb925  cmp     eax, 2
0x1802fb928  jnz     loc_1802FBA63
0x1802fb92e  lea     r8, aDesktopbackgro; "DesktopBackground"
0x1802fb935  jmp     loc_1802FBA8C
0x1802fb93a  xor     ebx, ebx
0x1802fb93c  lea     rcx, [rbp+850h+pszPath]; pszPath
0x1802fb943  call    cs:__imp_PathGetArgsW
0x1802fb949  test    rax, rax
0x1802fb94c  jz      short loc_1802FB95B
0x1802fb94e  cmp     [rax], bx
0x1802fb951  jz      short loc_1802FB95B
0x1802fb953  mov     [rbp+850h+pExecInfo.lpParameters], rax
0x1802fb957  mov     [rax-2], bx
0x1802fb95b  test    byte ptr [r14-44h], 8
0x1802fb960  jz      short loc_1802FB978
0x1802fb962  xor     edx, edx; dwFlags
0x1802fb964  mov     rcx, [r14-3Ch]; pt
0x1802fb968  call    cs:__imp_MonitorFromPoint
0x1802fb96e  mov     qword ptr [rbp+850h+pExecInfo.60h], rax
0x1802fb972  bts     [rsp+950h+pExecInfo.fMask], 15h
0x1802fb978  lea     rcx, [rsp+950h+pExecInfo]; pExecInfo
0x1802fb97d  call    cs:__imp_ShellExecuteExW
0x1802fb983  test    eax, eax
0x1802fb985  jz      short loc_1802FB98B
0x1802fb987  mov     edi, ebx
0x1802fb989  jmp     short loc_1802FB99A
0x1802fb98b  call    ResultFromKnownLastError
0x1802fb990  mov     edi, eax
0x1802fb992  test    eax, eax
0x1802fb994  js      loc_1802FB89B
0x1802fb99a  test    r15b, r15b
0x1802fb99d  jz      loc_1802FBB0D
0x1802fb9a3  xor     r15d, r15d
0x1802fb9a6  cmp     [r14+23Ch], r15b
0x1802fb9ad  jmp     loc_1802FBA47
0x1802fb9b2  lea     rax, pszStart
0x1802fb9b9  mov     rcx, rsi
0x1802fb9bc  test    rsi, rsi
0x1802fb9bf  cmovz   rcx, rax
0x1802fb9c3  jz      short loc_1802FB9D2
  ... truncated ...
```
