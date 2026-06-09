# CScreenSaverPg::_SaveIni(HWND__ *)

- ea: `0x180048624`
- end: `0x180048919`
- name: `?_SaveIni@CScreenSaverPg@@AEAAJPEAUHWND__@@@Z`
- size: `757`
- prototype: `int(CScreenSaverPg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800473c0`

## callees

- `0x18000ab10`
- `0x180033524`
- `0x1800358c0`
- `0x18003e920`
- `0x180048624`

## import_xrefs

- `SHELL32!__imp_PathGetShortPath` at `0x180048756`
- `SHELL32!__imp_PathGetShortPath` at `0x180048756`
- `SHLWAPI!PathQuoteSpacesW` at `0x180048761`
- `SHLWAPI!PathQuoteSpacesW` at `0x180048761`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004870f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004870f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048827`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180048827`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800487c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800487c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004883d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004883d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048813`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004878b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004878b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048730`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048730`
- `USER32!SendNotifyMessageW` at `0x1800488cc`
- `USER32!SendNotifyMessageW` at `0x1800488e7`
- `USER32!SendNotifyMessageW` at `0x1800488cc`
- `USER32!SendNotifyMessageW` at `0x1800488e7`
- `USER32!SystemParametersInfoW` at `0x18004887c`
- `USER32!SystemParametersInfoW` at `0x18004887c`
- `USER32!SendDlgItemMessageW` at `0x1800486b3`
- `USER32!SendDlgItemMessageW` at `0x1800486d6`
- `USER32!SendDlgItemMessageW` at `0x1800486b3`
- `USER32!SendDlgItemMessageW` at `0x1800486d6`
- `USER32!IsDlgButtonChecked` at `0x180048677`
- `USER32!IsDlgButtonChecked` at `0x180048677`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18004884f`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180048893`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x1800488af`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18004884f`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180048893`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x1800488af`

## pseudocode

```c
__int64 __fastcall CScreenSaverPg::_SaveIni(CScreenSaverPg *this, HWND a2)
{
  unsigned int Error; // esi
  UINT v5; // r12d
  const unsigned __int16 *v6; // r15
  int v7; // r14d
  int v8; // eax
  BOOL v9; // edi
  __int64 v10; // rax
  LSTATUS v11; // eax
  HKEY v12; // rcx
  HKEY phkResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszLongPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( g_bChangedSS )
  {
    phkResult[0] = 0;
    Error = 0;
    v5 = IsDlgButtonChecked(a2, 1320);
    if ( *((_DWORD *)this + 16) )
    {
      v6 = &Default;
      v7 = 0;
      if ( g_wNumMethods )
      {
        v8 = SendDlgItemMessageW(a2, 1300, 0x147u, 0, 0);
        v7 = v8;
        if ( v8 )
          v6 = (const unsigned __int16 *)(&g_aszFiles)[(int)SendDlgItemMessageW(a2, 1300, 0x150u, v8, 0)];
      }
      v9 = v7 != 0;
    }
    else
    {
      LoadStringW(g_hinst, 0x806u, Buffer, 260);
      v6 = (const unsigned __int16 *)&g_szSaverName;
      if ( !*(_WORD *)&g_szSaverName || (v9 = 1, !lstrcmpiW(Buffer, (LPCWSTR)&g_szSaverName)) )
        v9 = 0;
    }
    StringCchCopyW(pszLongPath, 0x104u, v6);
    PathGetShortPath(pszLongPath);
    PathQuoteSpacesW(pszLongPath);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ScreenSavers",
            0,
            0x20006u,
            phkResult)
      || !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", 0, 0, 0, 0x20006u, 0, phkResult, 0) )
    {
      if ( pszLongPath[0] )
      {
        v10 = -1;
        do
          ++v10;
        while ( pszLongPath[v10] );
        v11 = RegSetValueExW(phkResult[0], L"SCRNSAVE.EXE", 0, 1u, (const BYTE *)pszLongPath, 2 * v10 + 2);
      }
      else
      {
        v11 = RegDeleteValueW(phkResult[0], L"SCRNSAVE.EXE");
      }
      if ( v11 )
        Error = ResultFromLastError();
      RegCloseKey(phkResult[0]);
    }
    ClassicSystemParametersInfoW(17, v9, 0, 1);
    if ( v9 )
    {
      SHRegSetBOOL(v12, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", L"SlideshowEnabled", 0);
      SystemParametersInfoW(0xA9u, 0, 0, 1u);
    }
    ClassicSystemParametersInfoW(15, 60 * g_Timeout, 0, 1);
    if ( g_fPasswordDirty )
      ClassicSystemParametersInfoW(119, v5, 0, 1);
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"Windows");
    g_bChangedSS = 0;
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"WindowsThemeElement");
  }
  else
  {
    return 1;
  }
  return Error;
}

```

## disassembly

```asm
0x180048624  push    rbp
0x180048626  push    rbx
0x180048627  push    rsi
0x180048628  push    rdi
0x180048629  push    r12
0x18004862b  push    r13
0x18004862d  push    r14
0x18004862f  push    r15
0x180048631  lea     rbp, [rsp-398h]
0x180048639  sub     rsp, 498h
0x180048640  mov     rax, cs:__security_cookie
0x180048647  xor     rax, rsp
0x18004864a  mov     [rbp+3D0h+var_50], rax
0x180048651  xor     r13d, r13d
0x180048654  mov     rdi, rdx
0x180048657  cmp     cs:?g_bChangedSS@@3HA, r13d; int g_bChangedSS
0x18004865e  mov     r14, rcx
0x180048661  jz      loc_1800488EF
0x180048667  mov     edx, 528h; nIDButton
0x18004866c  mov     [rsp+4D0h+phkResult], r13
0x180048671  mov     rcx, rdi; hDlg
0x180048674  mov     esi, r13d
0x180048677  call    cs:__imp_IsDlgButtonChecked
0x18004867d  lea     ebx, [r13+1]
0x180048681  mov     r12d, eax
0x180048684  cmp     [r14+40h], r13d
0x180048688  jz      short loc_1800486F6
0x18004868a  cmp     cs:?g_wNumMethods@@3IA, r13d; uint g_wNumMethods
0x180048691  lea     r15, Default
0x180048698  mov     r14d, r13d
0x18004869b  jz      short loc_1800486EA
0x18004869d  xor     r9d, r9d; wParam
0x1800486a0  mov     [rsp+4D0h+lParam], r13; lParam
0x1800486a5  mov     edx, 514h; nIDDlgItem
0x1800486aa  mov     r8d, 147h; Msg
0x1800486b0  mov     rcx, rdi; hDlg
0x1800486b3  call    cs:__imp_SendDlgItemMessageW
0x1800486b9  mov     r14, rax
0x1800486bc  test    eax, eax
0x1800486be  jz      short loc_1800486EA
0x1800486c0  movsxd  r9, eax; wParam
0x1800486c3  mov     edx, 514h; nIDDlgItem
0x1800486c8  mov     r8d, 150h; Msg
0x1800486ce  mov     [rsp+4D0h+lParam], r13; lParam
0x1800486d3  mov     rcx, rdi; hDlg
0x1800486d6  call    cs:__imp_SendDlgItemMessageW
0x1800486dc  movsxd  rcx, eax
0x1800486df  lea     r15, ?g_aszFiles@@3PAPEAGA; ushort * near * g_aszFiles
0x1800486e6  mov     r15, [r15+rcx*8]
0x1800486ea  test    r14d, r14d
0x1800486ed  mov     edi, r13d
0x1800486f0  setnz   dil
0x1800486f4  jmp     short loc_18004873F
0x1800486f6  mov     rcx, cs:g_hinst; hInstance
0x1800486fd  lea     r8, [rbp+3D0h+Buffer]; lpBuffer
0x180048704  mov     r9d, 104h; cchBufferMax
0x18004870a  mov     edx, 806h; uID
0x18004870f  call    cs:__imp_LoadStringW
0x180048715  cmp     cs:?g_szSaverName@@3PAGA, r13w; ushort near * g_szSaverName
0x18004871d  lea     r15, ?g_szSaverName@@3PAGA; ushort near * g_szSaverName
0x180048724  jz      short loc_18004873C
0x180048726  mov     rdx, r15; lpString2
0x180048729  lea     rcx, [rbp+3D0h+Buffer]; lpString1
0x180048730  call    cs:__imp_lstrcmpiW
0x180048736  mov     edi, ebx
0x180048738  test    eax, eax
0x18004873a  jnz     short loc_18004873F
0x18004873c  mov     edi, r13d
0x18004873f  mov     r8, r15; unsigned __int16 *
0x180048742  lea     rcx, [rsp+4D0h+pszLongPath]; unsigned __int16 *
0x180048747  mov     edx, 104h; unsigned __int64
0x18004874c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180048751  lea     rcx, [rsp+4D0h+pszLongPath]; pszLongPath
0x180048756  call    cs:__imp_PathGetShortPath
0x18004875c  lea     rcx, [rsp+4D0h+pszLongPath]; lpsz
0x180048761  call    cs:__imp_PathQuoteSpacesW
0x180048767  lea     rax, [rsp+4D0h+phkResult]
0x18004876c  mov     r14d, 20006h
0x180048772  mov     r9d, r14d; samDesired
0x180048775  mov     [rsp+4D0h+lParam], rax; phkResult
0x18004877a  xor     r8d, r8d; ulOptions
0x18004877d  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\Windows NT\\Curren"...
0x180048784  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004878b  call    cs:__imp_RegOpenKeyExW
0x180048791  test    eax, eax
0x180048793  jz      short loc_1800487D1
0x180048795  mov     [rsp+4D0h+lpdwDisposition], r13; lpdwDisposition
0x18004879a  lea     rax, [rsp+4D0h+phkResult]
0x18004879f  mov     [rsp+4D0h+var_498], rax; phkResult
0x1800487a4  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x1800487ab  mov     [rsp+4D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800487b0  xor     r9d, r9d; lpClass
0x1800487b3  mov     [rsp+4D0h+samDesired], r14d; samDesired
0x1800487b8  xor     r8d, r8d; Reserved
0x1800487bb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800487c2  mov     dword ptr [rsp+4D0h+lParam], r13d; dwOptions
0x1800487c7  call    cs:__imp_RegCreateKeyExW
0x1800487cd  test    eax, eax
0x1800487cf  jnz     short loc_180048843
0x1800487d1  cmp     [rsp+4D0h+pszLongPath], r13w
0x1800487d7  jz      short loc_18004881B
0x1800487d9  lea     rcx, [rsp+4D0h+pszLongPath]
0x1800487de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800487e2  inc     rax
0x1800487e5  cmp     [rcx+rax*2], r13w
0x1800487ea  jnz     short loc_1800487E2
0x1800487ec  mov     rcx, [rsp+4D0h+phkResult]; hKey
0x1800487f1  lea     eax, ds:2[rax*2]
0x1800487f8  mov     [rsp+4D0h+samDesired], eax; cbData
0x1800487fc  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x180048803  lea     rax, [rsp+4D0h+pszLongPath]
0x180048808  mov     r9d, ebx; dwType
0x18004880b  xor     r8d, r8d; Reserved
0x18004880e  mov     [rsp+4D0h+lParam], rax; lpData
0x180048813  call    cs:__imp_RegSetValueExW
0x180048819  jmp     short loc_18004882D
0x18004881b  mov     rcx, [rsp+4D0h+phkResult]; hKey
0x180048820  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x180048827  call    cs:__imp_RegDeleteValueW
0x18004882d  test    eax, eax
0x18004882f  jz      short loc_180048838
0x180048831  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180048836  mov     esi, eax
0x180048838  mov     rcx, [rsp+4D0h+phkResult]; hKey
0x18004883d  call    cs:__imp_RegCloseKey
0x180048843  xor     r8d, r8d
0x180048846  mov     r9d, ebx
0x180048849  mov     edx, edi
0x18004884b  lea     ecx, [r8+11h]
0x18004884f  call    cs:__imp_ClassicSystemParametersInfoW
0x180048855  test    edi, edi
0x180048857  jz      short loc_180048882
0x180048859  xor     r9d, r9d; int
0x18004885c  lea     r8, aSlideshowenabl; "SlideshowEnabled"
0x180048863  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004886a  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18004886f  mov     r9d, ebx; fWinIni
0x180048872  xor     r8d, r8d; pvParam
0x180048875  xor     edx, edx; uiParam
0x180048877  mov     ecx, 0A9h; uiAction
0x18004887c  call    cs:__imp_SystemParametersInfoW
0x180048882  imul    edx, cs:?g_Timeout@@3PAHA, 3Ch ; '<'; int near * g_Timeout
0x180048889  xor     r8d, r8d
0x18004888c  mov     r9d, ebx
0x18004888f  lea     ecx, [r8+0Fh]
0x180048893  call    cs:__imp_ClassicSystemParametersInfoW
0x180048899  cmp     cs:?g_fPasswordDirty@@3HA, r13d; int g_fPasswordDirty
0x1800488a0  jz      short loc_1800488B5
0x1800488a2  xor     r8d, r8d
0x1800488a5  mov     r9d, ebx
0x1800488a8  mov     edx, r12d
0x1800488ab  lea     ecx, [r8+77h]
0x1800488af  call    cs:__imp_ClassicSystemParametersInfoW
0x1800488b5  xor     r8d, r8d; wParam
0x1800488b8  lea     r9, aWindows; "Windows"
0x1800488bf  mov     ebx, 0FFFFh
0x1800488c4  mov     ecx, ebx; hWnd
0x1800488c6  lea     edi, [r8+1Ah]
0x1800488ca  mov     edx, edi; Msg
0x1800488cc  call    cs:__imp_SendNotifyMessageW
0x1800488d2  lea     r9, lParam; "WindowsThemeElement"
0x1800488d9  mov     cs:?g_bChangedSS@@3HA, r13d; int g_bChangedSS
0x1800488e0  xor     r8d, r8d; wParam
0x1800488e3  mov     edx, edi; Msg
0x1800488e5  mov     ecx, ebx; hWnd
0x1800488e7  call    cs:__imp_SendNotifyMessageW
0x1800488ed  jmp     short loc_1800488F4
0x1800488ef  mov     esi, 1
0x1800488f4  mov     eax, esi
0x1800488f6  mov     rcx, [rbp+3D0h+var_50]
0x1800488fd  xor     rcx, rsp; StackCookie
0x180048900  call    __security_check_cookie
0x180048905  add     rsp, 498h
0x18004890c  pop     r15
0x18004890e  pop     r14
0x180048910  pop     r13
0x180048912  pop     r12
0x180048914  pop     rdi
0x180048915  pop     rsi
0x180048916  pop     rbx
0x180048917  pop     rbp
0x180048918  retn
```
