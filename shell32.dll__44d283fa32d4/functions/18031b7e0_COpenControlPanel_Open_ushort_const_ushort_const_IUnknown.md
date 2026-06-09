# COpenControlPanel::Open(ushort const *,ushort const *,IUnknown *)

- ea: `0x18031b7e0`
- end: `0x18031be97`
- name: `?Open@COpenControlPanel@@UEAAJPEBG0PEAUIUnknown@@@Z`
- size: `1719`
- prototype: `__int64 __fastcall(COpenControlPanel *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18031aa20`
- `0x18031b7e0`

## callees

- `0x180018e4c`
- `0x18001b9a0`
- `0x18003a3e0`
- `0x18005f3b4`
- `0x1800621f0`
- `0x180065190`
- `0x180086710`
- `0x180120904`
- `0x1801c9870`
- `0x1801ef318`
- `0x180235500`
- `0x180249490`
- `0x18024a53c`
- `0x18029131c`
- `0x18031b7e0`
- `0x18031c6f0`
- `0x18031cb70`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031b89f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031b8ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bbf9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bc3c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bc65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031b89f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031b8ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bbf9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bc3c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031bc65`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x18031bc8f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x18031bc8f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18031bb15`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18031bb15`
- `USER32!MonitorFromPoint` at `0x18031ba95`
- `USER32!MonitorFromPoint` at `0x18031bcba`
- `USER32!MonitorFromPoint` at `0x18031ba95`
- `USER32!MonitorFromPoint` at `0x18031bcba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031be32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031be32`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18031b825`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18031b825`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18031b86f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18031b86f`
- `Windows.Storage!ShellExecuteExW` at `0x18031bab0`
- `Windows.Storage!ShellExecuteExW` at `0x18031bcd5`
- `Windows.Storage!ShellExecuteExW` at `0x18031bab0`
- `Windows.Storage!ShellExecuteExW` at `0x18031bcd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COpenControlPanel::Open(
        COpenControlPanel *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4)
{
  HRESULT Error; // edi
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
  const WCHAR *v27; // rcx
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
        v26 = &pszStart;
        v27 = a3;
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
      v14 = &pszStart;
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
                (unsigned int)pszPath,
                (unsigned int)pszPath,
                (int)v16 + (int)v17 + 1,
                fuStyle,
                (__int64)&hWnd);
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
0x18031b7e0  push    rbp
0x18031b7e2  push    rbx
0x18031b7e3  push    rsi
0x18031b7e4  push    rdi
0x18031b7e5  push    r12
0x18031b7e7  push    r13
0x18031b7e9  push    r14
0x18031b7eb  push    r15
0x18031b7ed  lea     rbp, [rsp-818h]
0x18031b7f5  sub     rsp, 918h
0x18031b7fc  mov     rax, cs:__security_cookie
0x18031b803  xor     rax, rsp
0x18031b806  mov     [rbp+850h+var_50], rax
0x18031b80d  mov     r12, r9
0x18031b810  mov     rsi, r8
0x18031b813  mov     rdi, rdx
0x18031b816  mov     [rsp+950h+lpString1], rdx
0x18031b81b  mov     r14, rcx
0x18031b81e  lea     rcx, POLID_NoControlPanel
0x18031b825  call    cs:__imp_SHWindowsPolicy
0x18031b82c  nop     dword ptr [rax+rax+00h]
0x18031b831  xor     r15d, r15d
0x18031b834  test    eax, eax
0x18031b836  jz      short loc_18031B880
0x18031b838  mov     edi, 80004005h
0x18031b83d  mov     [rsp+950h+hWnd], r15
0x18031b842  lea     rdx, [rsp+950h+hWnd]; phwnd
0x18031b847  mov     rcx, r12; punk
0x18031b84a  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x18031b84f  mov     r8d, 2601h; lpcText
0x18031b855  mov     rdx, [rsp+950h+hWnd]; hWnd
0x18031b85a  mov     r9d, 2600h; lpcTitle
0x18031b860  mov     [rsp+950h+fuStyle], 10h; fuStyle
0x18031b868  mov     rcx, cs:g_hinst; hAppInst
0x18031b86f  call    cs:__imp_ShellMessageBoxW
0x18031b876  nop     dword ptr [rax+rax+00h]
0x18031b87b  jmp     loc_18031BE71
0x18031b880  lea     r13, [r14-70h]
0x18031b884  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x18031b88c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18031b890  mov     r9d, ebx; cchCount2
0x18031b893  lea     r8, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x18031b89a  mov     edx, ebx; cchCount1
0x18031b89c  mov     rcx, rdi; lpString1
0x18031b89f  call    cs:__imp_CompareStringOrdinal
0x18031b8a6  nop     dword ptr [rax+rax+00h]
0x18031b8ab  cmp     eax, 2
0x18031b8ae  jnz     short loc_18031B8D3
0x18031b8b0  mov     dword ptr [rsp+950h+var_920], r15d
0x18031b8b5  mov     rax, [r13+8]
0x18031b8b9  mov     [rsp+950h+var_928], rax
0x18031b8be  mov     qword ptr [rsp+950h+fuStyle], r15
0x18031b8c3  xor     edx, edx
0x18031b8c5  mov     ecx, 3512h
0x18031b8ca  lea     r9d, [rbx+3]
0x18031b8ce  call    ?_Fire_CommandHandlerInvokeTelemetry@@YAXW4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_INVOCATION_LOCATION@@W4RIBBON_VISIBILITY@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIShellItem@@PEAUIUnknown@@K@Z; _Fire_CommandHandlerInvokeTelemetry(EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_INVOCATION_LOCATION,RIBBON_VISIBILITY,EXPLORER_COMMAND_SQM_SELECTED_STATE,IShellItem *,IUnknown *,ulong)
0x18031b8d3  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x18031b8db  mov     r9d, ebx; cchCount2
0x18031b8de  lea     r8, aMicrosoftDevic_0; "Microsoft.DevicesAndPrinters"
0x18031b8e5  mov     edx, ebx; cchCount1
0x18031b8e7  mov     rcx, rdi; lpString1
0x18031b8ea  call    cs:__imp_CompareStringOrdinal
0x18031b8f1  nop     dword ptr [rax+rax+00h]
0x18031b8f6  cmp     eax, 2
0x18031b8f9  jnz     short loc_18031B90C
0x18031b8fb  lea     rcx, aMsSettingsDevi; "ms-settings:devices"
0x18031b902  call    ?LaunchRedirectedControlPanelEntryPoint@@YAJPEBGW4CPLENTRYPOINT@@@Z; LaunchRedirectedControlPanelEntryPoint(ushort const *,CPLENTRYPOINT)
0x18031b907  jmp     loc_18031BE73
0x18031b90c  mov     [rsp+950h+var_910], r15b
0x18031b911  mov     [rsp+950h+var_90F], r15b
0x18031b916  test    rsi, rsi
0x18031b919  setnz   al
0x18031b91c  lea     rcx, [rsp+950h+var_90F]
0x18031b921  mov     [rsp+950h+var_920], rcx; bool *
0x18031b926  lea     rcx, [rsp+950h+var_910]
0x18031b92b  mov     [rsp+950h+var_928], rcx; bool *
0x18031b930  mov     byte ptr [rsp+950h+fuStyle], al; bool
0x18031b934  lea     r8, [rbp+850h+var_880]; unsigned __int16 *
0x18031b938  mov     rdx, rdi; unsigned __int16 *
0x18031b93b  mov     rcx, r13; this
0x18031b93e  call    ?_GetPathWithLegacyCheck@COpenControlPanel@@AEAAJPEBGPEAGI_NPEA_N3@Z; COpenControlPanel::_GetPathWithLegacyCheck(ushort const *,ushort *,uint,bool,bool *,bool *)
0x18031b943  mov     edi, eax
0x18031b945  test    eax, eax
0x18031b947  js      loc_18031BBD8
0x18031b94d  mov     eax, 3Ah ; ':'
0x18031b952  cmp     ax, [rbp+850h+var_880]
0x18031b956  jnz     loc_18031BAF7
0x18031b95c  cmp     ax, [rbp+850h+var_87E]
0x18031b960  jnz     loc_18031BAF7
0x18031b966  test    rsi, rsi
0x18031b969  jz      short loc_18031B98B
0x18031b96b  cmp     [rsi], r15w
0x18031b96f  jz      short loc_18031B98B
0x18031b971  lea     edx, [rax+5]
0x18031b974  lea     rcx, asc_180615A18; "\\"
0x18031b97b  lea     rax, pszSrch; ","
0x18031b982  cmp     dx, [rsi]
0x18031b985  cmovnz  rax, rcx
0x18031b989  jmp     short loc_18031B992
0x18031b98b  lea     rax, pszStart
0x18031b992  mov     qword ptr [rsp+950h+fuStyle], rax
0x18031b997  lea     r9, [rbp+850h+var_880]
0x18031b99b  lea     r8, aSS_6; "%s%s"
0x18031b9a2  mov     edx, 30Ch; unsigned __int64
0x18031b9a7  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x18031b9ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18031b9b3  mov     edi, eax
0x18031b9b5  test    eax, eax
0x18031b9b7  js      loc_18031BBD8
0x18031b9bd  mov     rbx, r15
0x18031b9c0  mov     [rsp+950h+hWnd], rbx
0x18031b9c5  test    rsi, rsi
0x18031b9c8  jz      short loc_18031BA2A
0x18031b9ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18031b9ce  mov     rcx, rax
0x18031b9d1  inc     rcx
0x18031b9d4  cmp     [rsi+rcx*2], r15w
0x18031b9d9  jnz     short loc_18031B9D1
0x18031b9db  lea     rdx, [rbp+850h+pszPath]
0x18031b9e2  inc     rax
0x18031b9e5  cmp     [rdx+rax*2], r15w
0x18031b9ea  jnz     short loc_18031B9E2
0x18031b9ec  lea     rbx, [rax+rcx]
0x18031b9f0  lea     rax, [rsp+950h+hWnd]
0x18031b9f5  mov     [rsp+950h+var_928], rax
0x18031b9fa  lea     r9, [rbx+1]
0x18031b9fe  lea     r8, [rbp+850h+pszPath]
0x18031ba05  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18031ba0a  mov     edi, eax
0x18031ba0c  test    eax, eax
0x18031ba0e  js      loc_18031BAE8
0x18031ba14  mov     r8, rsi; unsigned __int16 *
0x18031ba17  lea     rdx, [rbx+1]; unsigned __int64
0x18031ba1b  mov     rbx, [rsp+950h+hWnd]
0x18031ba20  mov     rcx, rbx; unsigned __int16 *
0x18031ba23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18031ba28  mov     edi, eax
0x18031ba2a  test    edi, edi
0x18031ba2c  js      loc_18031BAE8
0x18031ba32  xor     edx, edx; Val
0x18031ba34  lea     r8d, [rdx+6Ch]; Size
0x18031ba38  lea     rcx, [rsp+950h+pExecInfo.fMask]; void *
0x18031ba3d  call    memset_0
0x18031ba42  mov     [rsp+950h+pExecInfo.cbSize], 70h ; 'p'
0x18031ba4a  mov     [rsp+950h+phwnd], r15
0x18031ba4f  lea     rdx, [rsp+950h+phwnd]; phwnd
0x18031ba54  mov     rcx, r12; punk
0x18031ba57  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x18031ba5c  mov     rax, [rsp+950h+phwnd]
0x18031ba61  mov     [rsp+950h+pExecInfo.hwnd], rax
0x18031ba66  mov     [rbp+850h+pExecInfo.nShow], 1
0x18031ba6d  mov     [rsp+950h+pExecInfo.fMask], 4000100h
0x18031ba75  lea     rax, [rbp+850h+pszPath]
0x18031ba7c  test    rsi, rsi
0x18031ba7f  cmovnz  rax, rbx
0x18031ba83  mov     [rsp+950h+pExecInfo.lpFile], rax
0x18031ba88  test    byte ptr [r14-44h], 8
0x18031ba8d  jz      short loc_18031BAAB
0x18031ba8f  xor     edx, edx; dwFlags
0x18031ba91  mov     rcx, [r14-3Ch]; pt
0x18031ba95  call    cs:__imp_MonitorFromPoint
0x18031ba9c  nop     dword ptr [rax+rax+00h]
0x18031baa1  mov     qword ptr [rbp+850h+pExecInfo.60h], rax
0x18031baa5  bts     [rsp+950h+pExecInfo.fMask], 15h
0x18031baab  lea     rcx, [rsp+950h+pExecInfo]; pExecInfo
0x18031bab0  call    cs:__imp_ShellExecuteExW
0x18031bab7  nop     dword ptr [rax+rax+00h]
0x18031babc  test    eax, eax
0x18031babe  jz      short loc_18031BAC5
0x18031bac0  mov     edi, r15d
0x18031bac3  jmp     short loc_18031BAD0
0x18031bac5  call    ResultFromKnownLastError
0x18031baca  mov     edi, eax
0x18031bacc  test    eax, eax
0x18031bace  js      short loc_18031BAE8
0x18031bad0  cmp     [r14+23Ch], r15b
0x18031bad7  jz      short loc_18031BAE8
0x18031bad9  xor     r8d, r8d; bool
0x18031badc  mov     rdx, rsi; unsigned __int16 *
0x18031badf  mov     rcx, r13; this
0x18031bae2  call    ?_AddtoRecentDocs@COpenControlPanel@@AEAAJPEBG_N@Z; COpenControlPanel::_AddtoRecentDocs(ushort const *,bool)
0x18031bae7  nop
0x18031bae8  lea     rcx, [rsp+950h+hWnd]
0x18031baed  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18031baf2  jmp     loc_18031BDB4
0x18031baf7  cmp     [rsp+950h+var_910], r15b
0x18031bafc  jz      loc_18031BD10
0x18031bb02  mov     ebx, 30Ch
0x18031bb07  mov     r8d, ebx
0x18031bb0a  lea     rdx, [rbp+850h+pszPath]
0x18031bb11  lea     rcx, [rbp+850h+var_880]
0x18031bb15  call    cs:__imp_SHExpandEnvironmentStringsW
0x18031bb1c  nop     dword ptr [rax+rax+00h]
0x18031bb21  test    eax, eax
0x18031bb23  jz      short loc_18031BB2A
0x18031bb25  mov     edi, r15d
0x18031bb28  jmp     short loc_18031BB39
0x18031bb2a  call    ResultFromLastError
0x18031bb2f  mov     edi, eax
0x18031bb31  test    eax, eax
0x18031bb33  js      loc_18031BBD8
0x18031bb39  xor     edx, edx; Val
0x18031bb3b  lea     r8d, [rdx+6Ch]; Size
0x18031bb3f  lea     rcx, [rsp+950h+pExecInfo.fMask]; void *
0x18031bb44  call    memset_0
0x18031bb49  mov     [rsp+950h+pExecInfo.cbSize], 70h ; 'p'
0x18031bb51  mov     [rsp+950h+phwnd], r15
0x18031bb56  lea     rdx, [rsp+950h+phwnd]; phwnd
0x18031bb5b  mov     rcx, r12; punk
0x18031bb5e  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x18031bb63  mov     rax, [rsp+950h+phwnd]
0x18031bb68  mov     [rsp+950h+pExecInfo.hwnd], rax
0x18031bb6d  mov     [rbp+850h+pExecInfo.nShow], 1
0x18031bb74  mov     [rsp+950h+pExecInfo.fMask], 4000100h
0x18031bb7c  lea     rax, [rbp+850h+pszPath]
0x18031bb83  mov     [rsp+950h+pExecInfo.lpFile], rax
0x18031bb88  mov     r15b, [rsp+950h+var_90F]
0x18031bb8d  test    r15b, r15b
0x18031bb90  jz      loc_18031BC86
0x18031bb96  test    rsi, rsi
0x18031bb99  jz      short loc_18031BBCB
0x18031bb9b  lea     r8, asc_18061DCA0; " ,"
0x18031bba2  mov     rdx, rbx; unsigned __int64
0x18031bba5  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x18031bbac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18031bbb1  mov     edi, eax
0x18031bbb3  test    eax, eax
0x18031bbb5  js      short loc_18031BBD5
0x18031bbb7  mov     r8, rsi; unsigned __int16 *
0x18031bbba  mov     rdx, rbx; unsigned __int64
0x18031bbbd  lea     rcx, [rbp+850h+pszPath]; unsigned __int16 *
0x18031bbc4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18031bbc9  mov     edi, eax
0x18031bbcb  xor     ebx, ebx
0x18031bbcd  test    edi, edi
0x18031bbcf  jns     loc_18031BC88
0x18031bbd5  xor     r15d, r15d
0x18031bbd8  mov     [rsp+950h+fuStyle], 1; bIgnoreCase
0x18031bbe0  or      r13, 0FFFFFFFFFFFFFFFFh
0x18031bbe4  mov     r9d, r13d; cchCount2
0x18031bbe7  lea     r8, aMicrosoftPerso; "Microsoft.Personalization"
0x18031bbee  mov     edx, r13d; cchCount1
0x18031bbf1  mov     rbx, [rsp+950h+lpString1]
0x18031bbf6  mov     rcx, rbx; lpString1
0x18031bbf9  call    cs:__imp_CompareStringOrdinal
0x18031bc00  nop     dword ptr [rax+rax+00h]
0x18031bc05  cmp     eax, 2
0x18031bc08  jnz     loc_18031BE00
0x18031bc0e  call    ?IsPersonalizationFeatureAvailable@@YA_NXZ; IsPersonalizationFeatureAvailable(void)
0x18031bc13  test    al, al
0x18031bc15  jnz     loc_18031BE00
0x18031bc1b  test    rsi, rsi
0x18031bc1e  jz      loc_18031BDE3
0x18031bc24  lea     ebx, [r13+2]
0x18031bc28  mov     [rsp+950h+fuStyle], ebx; bIgnoreCase
0x18031bc2c  mov     r9d, r13d; cchCount2
0x18031bc2f  lea     r8, aPagecolorizati; "pageColorization"
0x18031bc36  mov     edx, r13d; cchCount1
0x18031bc39  mov     rcx, rsi; lpString1
0x18031bc3c  call    cs:__imp_CompareStringOrdinal
0x18031bc43  nop     dword ptr [rax+rax+00h]
0x18031bc48  cmp     eax, 2
0x18031bc4b  jz      loc_18031BDE3
0x18031bc51  mov     [rsp+950h+fuStyle], ebx; bIgnoreCase
0x18031bc55  mov     r9d, r13d; cchCount2
0x18031bc58  lea     r8, aPagewallpaper; "pageWallpaper"
0x18031bc5f  mov     edx, r13d; cchCount1
0x18031bc62  mov     rcx, rsi; lpString1
0x18031bc65  call    cs:__imp_CompareStringOrdinal
0x18031bc6c  nop     dword ptr [rax+rax+00h]
0x18031bc71  cmp     eax, 2
0x18031bc74  jnz     loc_18031BDC1
0x18031bc7a  lea     r8, aDesktopbackgro; "DesktopBackground"
0x18031bc81  jmp     loc_18031BDEA
0x18031bc86  xor     ebx, ebx
0x18031bc88  lea     rcx, [rbp+850h+pszPath]; pszPath
0x18031bc8f  call    cs:__imp_PathGetArgsW
0x18031bc96  nop     dword ptr [rax+rax+00h]
0x18031bc9b  test    rax, rax
0x18031bc9e  jz      short loc_18031BCAD
0x18031bca0  cmp     [rax], bx
0x18031bca3  jz      short loc_18031BCAD
0x18031bca5  mov     [rbp+850h+pExecInfo.lpParameters], rax
0x18031bca9  mov     [rax-2], bx
0x18031bcad  test    byte ptr [r14-44h], 8
0x18031bcb2  jz      short loc_18031BCD0
0x18031bcb4  xor     edx, edx; dwFlags
0x18031bcb6  mov     rcx, [r14-3Ch]; pt
0x18031bcba  call    cs:__imp_MonitorFromPoint
0x18031bcc1  nop     dword ptr [rax+rax+00h]
0x18031bcc6  mov     qword ptr [rbp+850h+pExecInfo.60h], rax
0x18031bcca  bts     [rsp+950h+pExecInfo.fMask], 15h
0x18031bcd0  lea     rcx, [rsp+950h+pExecInfo]; pExecInfo
0x18031bcd5  call    cs:__imp_ShellExecuteExW
0x18031bcdc  nop     dword ptr [rax+rax+00h]
0x18031bce1  test    eax, eax
0x18031bce3  jz      short loc_18031BCE9
0x18031bce5  mov     edi, ebx
0x18031bce7  jmp     short loc_18031BCF8
0x18031bce9  call    ResultFromKnownLastError
  ... truncated ...
```
