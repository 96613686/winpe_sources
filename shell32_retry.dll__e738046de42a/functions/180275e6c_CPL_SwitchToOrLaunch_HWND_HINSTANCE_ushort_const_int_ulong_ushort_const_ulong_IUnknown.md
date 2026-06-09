# CPL_SwitchToOrLaunch(HWND__ *,HINSTANCE__ *,ushort const *,int,ulong,ushort const *,ulong *,IUnknown *)

- ea: `0x180275e6c`
- end: `0x1802763d3`
- name: `?CPL_SwitchToOrLaunch@@YAHPEAUHWND__@@PEAUHINSTANCE__@@PEBGHK2PEAKPEAUIUnknown@@@Z`
- size: `1383`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, HINSTANCE@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, const unsigned __int16 *, unsigned int *, struct IUnknown *)`
- caller_count: `4`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180277854`
- `0x1802779b0`
- `0x1802779e0`
- `0x180277a10`

## callees

- `0x18001bf10`
- `0x18001df70`
- `0x180043380`
- `0x18009b608`
- `0x180166dd4`
- `0x180179358`
- `0x180233280`
- `0x1802342fc`
- `0x180275a54`
- `0x180275bbc`
- `0x180275de8`
- `0x180275e6c`
- `0x1802763dc`
- `0x180276534`
- `0x180276700`
- `0x180276f00`
- `0x180276f4c`
- `0x1802772e0`
- `0x180277344`
- `0x180277520`
- `0x180277590`
- `0x18036cc80`
- `0x1804d5274`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802762f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802762f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180276352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180276352`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180275fa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180275fa1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1802762e6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180276329`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1802762e6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180276329`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180275fc9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180275feb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180275fc9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180275feb`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1802761b7`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1802761b7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180275fb6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180275fb6`
- `USER32!RemovePropW` at `0x180276393`
- `USER32!RemovePropW` at `0x1802763a3`
- `USER32!RemovePropW` at `0x1802763b3`
- `USER32!RemovePropW` at `0x180276393`
- `USER32!RemovePropW` at `0x1802763a3`
- `USER32!RemovePropW` at `0x1802763b3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180276039`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180276039`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180275ed9`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180275ed9`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x180276183`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x180276183`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180275f09`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180276259`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180275f09`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180276259`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x180275ee3`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x180276215`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x180275ee3`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x180276215`

## string_xrefs

- `0x180275fbf`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall CPL_SwitchToOrLaunch(
        HWND a1,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        int a4,
        char a5,
        const unsigned __int16 *a6,
        unsigned int *a7,
        struct IUnknown *a8)
{
  BOOL v10; // r13d
  __int64 v13; // rdx
  unsigned int v14; // ebx
  const WCHAR *FileNameW; // rsi
  int v16; // r15d
  enum ACTCTX_REQUESTED_RUN_LEVEL RunLevelForCPL; // eax
  struct CPLMODULE *v18; // r14
  __int64 v19; // r12
  const WCHAR *v20; // r8
  __int64 v21; // rax
  int cbMultiByte; // ebx
  CHAR *v23; // rax
  CHAR *v24; // r15
  const unsigned __int16 *fuStyle; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  struct CPLMODULE *ItemPtr; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  _BYTE v31[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v32[260]; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v33[524]; // [rsp+26Ch] [rbp+16Ch] BYREF
  LPCWCH lpWideCharStr; // [rsp+478h] [rbp+378h]
  __int128 v35; // [rsp+480h] [rbp+380h] BYREF
  __int64 v36; // [rsp+490h] [rbp+390h]
  WCHAR pszMenu[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR Filename[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v28 = a4;
  v10 = 0;
  v36 = 0;
  ItemPtr = 0;
  v35 = 0;
  if ( (unsigned int)SHWindowsPolicy(&POLID_NoControlPanel) )
  {
    if ( (unsigned int)SHIsCurrentThreadOnUserDesktop() )
      ShellMessageBoxW(g_hinst, a1, (LPCWSTR)0x2601, (LPCWSTR)0x2600, 0x10u);
    return 0;
  }
  v30 = SHCoInitialize();
  memset_0(v31, 0, 0x420u);
  CPL_ParseCommandLine(v32, v13, v31, v33);
  v26 = 0;
  v14 = _VerifyAndLaunchControlPanelAppletIfLegacy(a1, (struct CPLEXECINFO *)v31, a4, &v26, fuStyle, a7, a8);
  v27 = v14;
  if ( v26 )
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v14 = 0;
      goto LABEL_14;
    }
    FileNameW = PathFindFileNameW(Filename);
    if ( StrCmpICW(FileNameW, L"rundll32.exe") )
    {
      v16 = 0;
      v10 = StrCmpICW(FileNameW, L"RunLegacyCplElevated.exe") == 0;
    }
    else
    {
      v16 = 1;
    }
    if ( (a5 & 4) != 0
      && GetModuleTargetArchitecture(v32) == 332
      && (unsigned int)CPL_RelaunchOppositeArchitecture(a3, v28, v16) )
    {
      v14 = 1;
      goto LABEL_14;
    }
    if ( !(unsigned int)CPL_Identify((struct CPLAPPLETID *)&v35, (const struct CPLEXECINFO *)v31, a1) )
      goto LABEL_14;
    if ( (a5 & 2) != 0 && (unsigned int)_SwitchToControlPanelWindowAlreadyShowing(a1, (struct CPLAPPLETID *)&v35) )
    {
      v14 = 1;
LABEL_21:
      CPL_UnIdentify((struct CPLAPPLETID *)&v35);
      goto LABEL_14;
    }
    if ( (a5 & 1) == 0 )
      goto LABEL_21;
    v26 = 0;
    if ( (int)SHIsCurrentAppElevated(&v26) < 0 )
      goto LABEL_21;
    if ( !v26 )
    {
      if ( !v16 )
      {
LABEL_28:
        v14 = 0;
        goto LABEL_21;
      }
      RunLevelForCPL = _GetRunLevelForCPL(v32);
      if ( RunLevelForCPL )
      {
        if ( RunLevelForCPL != ACTCTX_RUN_LEVEL_AS_INVOKER )
          goto LABEL_28;
      }
      else
      {
        if ( !(unsigned int)_HandleUnmarkedLegacyCPL(a1, (const struct CPLEXECINFO *)v31, a3, v28, &v27) )
        {
          v14 = v27;
          goto LABEL_21;
        }
        v14 = 0;
      }
    }
    v27 = 0;
    if ( !(unsigned int)LoadAndFindApplet(&ItemPtr, 0, &v27, (const struct CPLEXECINFO *)v31, 1) )
      goto LABEL_21;
    v18 = ItemPtr;
    v19 = v27;
    ItemPtr = (struct CPLMODULE *)DSA_GetItemPtr(*((HDSA *)ItemPtr + 70), v27);
    if ( (int)StringCchCopyW(pszMenu, 0x104u, *(const unsigned __int16 **)ItemPtr) >= 0 )
    {
      SHStripMneumonicW(pszMenu);
      if ( WORD1(v35) )
      {
        if ( !(_DWORD)v19 )
          LODWORD(v36) = v36 | 1;
      }
      else
      {
        LODWORD(v36) = v36 | 1;
        WORD1(v35) = GlobalAddAtomW(pszMenu);
        if ( !WORD1(v35) )
          goto LABEL_59;
      }
      if ( (unsigned int)CPL_SetWindowProps(a1, (struct CPLAPPLETID *)&v35) )
      {
        if ( a1 )
          _SetIconToCPLStubWindow(a1, v18, ItemPtr, pszMenu);
        if ( v16 && !(unsigned int)SHInitLUAVirtualizationFromActCtx(*((HANDLE *)v18 + 72)) )
        {
          if ( (unsigned int)SHIsCurrentThreadOnUserDesktop() )
            ShellMessageBoxW(
              g_hinst,
              a1,
              (LPCWSTR)0x2453,
              (LPCWSTR)0x1041,
              0x30u,
              (char *)v18 + 32,
              L"requestedRunLevel");
          goto LABEL_56;
        }
        v20 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          v21 = CPL_CallEntry(v18, a1, 0xAu, v19, (__int64)lpWideCharStr);
          v20 = lpWideCharStr;
          v14 = v21 != 0;
        }
        if ( v16 || v10 )
        {
          _ResetWindowsVersionOnProcessBlock(v18);
          v20 = lpWideCharStr;
        }
        if ( v20 )
        {
          if ( v14 )
            goto LABEL_56;
          cbMultiByte = WideCharToMultiByte(0, 0x400u, v20, -1, 0, 0, 0, 0);
          v23 = (CHAR *)LocalAlloc(0x40u, cbMultiByte);
          v24 = v23;
          if ( !v23 )
          {
LABEL_55:
            CPL_CallEntry(v18, a1, 5u, v19, *((_QWORD *)ItemPtr + 3));
            v14 = 1;
            goto LABEL_56;
          }
          WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, v23, cbMultiByte, 0, 0);
          v14 = CPL_CallEntry(v18, a1, 9u, v19, (__int64)v24) != 0;
          LocalFree(v24);
        }
        if ( !v14 )
          goto LABEL_55;
LABEL_56:
        if ( (_DWORD)v36 )
          RemovePropW(a1, L"CPLFlags");
        RemovePropW(a1, L"AppletName");
        RemovePropW(a1, L"CPLName");
      }
    }
LABEL_59:
    CPL_ReleaseModuleReference(v18);
    goto LABEL_21;
  }
LABEL_14:
  if ( !v30 )
    CoUninitialize();
  return v14;
}

```

## disassembly

```asm
0x180275e6c  mov     [rsp-8+arg_8], rbx
0x180275e71  push    rbp
0x180275e72  push    rsi
0x180275e73  push    rdi
0x180275e74  push    r12
0x180275e76  push    r13
0x180275e78  push    r14
0x180275e7a  push    r15
0x180275e7c  lea     rbp, [rsp-7D0h]
0x180275e84  sub     rsp, 8D0h
0x180275e8b  mov     rax, cs:__security_cookie
0x180275e92  xor     rax, rsp
0x180275e95  mov     [rbp+800h+var_40], rax
0x180275e9c  mov     rsi, [rbp+800h+arg_30]
0x180275ea3  mov     ebx, r9d
0x180275ea6  mov     r14, [rbp+800h+arg_38]
0x180275ead  mov     rdi, rcx
0x180275eb0  xorps   xmm0, xmm0
0x180275eb3  mov     [rsp+900h+var_8B8], ebx
0x180275eb7  xor     eax, eax
0x180275eb9  lea     rcx, POLID_NoControlPanel
0x180275ec0  xor     r13d, r13d
0x180275ec3  mov     [rbp+800h+var_470], rax
0x180275eca  mov     [rsp+900h+var_8B0], r13
0x180275ecf  mov     r12, r8
0x180275ed2  movups  [rbp+800h+var_480], xmm0
0x180275ed9  call    cs:__imp_SHWindowsPolicy
0x180275edf  test    eax, eax
0x180275ee1  jz      short loc_180275F16
0x180275ee3  call    cs:__imp_SHIsCurrentThreadOnUserDesktop
0x180275ee9  test    eax, eax
0x180275eeb  jz      short loc_180275F0F
0x180275eed  mov     rcx, cs:g_hinst; hAppInst
0x180275ef4  mov     r9d, 2600h; lpcTitle
0x180275efa  mov     rdx, rdi; hWnd
0x180275efd  mov     [rsp+900h+fuStyle], 10h; fuStyle
0x180275f05  lea     r8d, [r9+1]; lpcText
0x180275f09  call    cs:__imp_ShellMessageBoxW
0x180275f0f  xor     eax, eax
0x180275f11  jmp     loc_180276041
0x180275f16  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180275f1b  xor     edx, edx; Val
0x180275f1d  mov     [rsp+900h+var_8A8], eax
0x180275f21  mov     r8d, 420h; Size
0x180275f27  lea     rcx, [rsp+900h+var_8A0]; void *
0x180275f2c  call    memset_0
0x180275f31  lea     rax, [rbp+800h+lpWideCharStr]
0x180275f38  mov     dword ptr [rsp+900h+lpUsedDefaultChar], r13d
0x180275f3d  mov     [rsp+900h+lpDefaultChar], r12
0x180275f42  lea     r9, [rbp+800h+var_694]
0x180275f49  lea     r8, [rsp+900h+var_8A0]
0x180275f4e  mov     qword ptr [rsp+900h+cbMultiByte], rax
0x180275f53  lea     rcx, [rsp+900h+var_89C]
0x180275f58  call    CPL_ParseCommandLine
0x180275f5d  mov     [rsp+900h+var_8C0], r13d
0x180275f62  mov     [rsp+900h+lpDefaultChar], r14; struct IUnknown *
0x180275f67  lea     r9, [rsp+900h+var_8C0]; int *
0x180275f6c  mov     r8d, ebx; int
0x180275f6f  mov     qword ptr [rsp+900h+cbMultiByte], rsi; unsigned int *
0x180275f74  lea     rdx, [rsp+900h+var_8A0]; struct CPLEXECINFO *
0x180275f79  mov     rcx, rdi; HWND
0x180275f7c  call    ?_VerifyAndLaunchControlPanelAppletIfLegacy@@YAHPEAUHWND__@@PEAUCPLEXECINFO@@HPEAHPEBGPEAKPEAUIUnknown@@@Z; _VerifyAndLaunchControlPanelAppletIfLegacy(HWND__ *,CPLEXECINFO *,int,int *,ushort const *,ulong *,IUnknown *)
0x180275f81  mov     ebx, eax
0x180275f83  mov     [rsp+900h+var_8BC], eax
0x180275f87  cmp     [rsp+900h+var_8C0], r13d
0x180275f8c  jz      loc_180276032
0x180275f92  mov     r8d, 104h; nSize
0x180275f98  lea     rdx, [rbp+800h+Filename]; lpFilename
0x180275f9f  xor     ecx, ecx; hModule
0x180275fa1  call    cs:__imp_GetModuleFileNameW
0x180275fa7  test    eax, eax
0x180275fa9  jz      loc_1802763CB
0x180275faf  lea     rcx, [rbp+800h+Filename]; pszPath
0x180275fb6  call    cs:__imp_PathFindFileNameW
0x180275fbc  mov     rcx, rax; pszStr1
0x180275fbf  lea     rdx, aRundll32Exe; "rundll32.exe"
0x180275fc6  mov     rsi, rax
0x180275fc9  call    cs:__imp_StrCmpICW
0x180275fcf  xor     r14d, r14d
0x180275fd2  test    eax, eax
0x180275fd4  jnz     short loc_180275FDE
0x180275fd6  lea     esi, [rax+1]
0x180275fd9  mov     r15d, esi
0x180275fdc  jmp     short loc_180275FFC
0x180275fde  lea     rdx, aRunlegacycplel; "RunLegacyCplElevated.exe"
0x180275fe5  mov     rcx, rsi; pszStr1
0x180275fe8  mov     r15d, r14d
0x180275feb  call    cs:__imp_StrCmpICW
0x180275ff1  test    eax, eax
0x180275ff3  mov     esi, 1
0x180275ff8  cmovz   r13d, esi
0x180275ffc  mov     r14d, dword ptr [rbp+800h+arg_20]
0x180276003  test    r14b, 4
0x180276007  jz      short loc_18027606B
0x180276009  lea     rcx, [rsp+900h+var_89C]; unsigned __int16 *
0x18027600e  call    ?GetModuleTargetArchitecture@@YAKPEBG@Z; GetModuleTargetArchitecture(ushort const *)
0x180276013  cmp     eax, 14Ch
0x180276018  jnz     short loc_18027606B
0x18027601a  mov     edx, [rsp+900h+var_8B8]; int
0x18027601e  mov     r8d, r15d; int
0x180276021  mov     rcx, r12; unsigned __int16 *
0x180276024  call    ?CPL_RelaunchOppositeArchitecture@@YAHPEBGHH@Z; CPL_RelaunchOppositeArchitecture(ushort const *,int,int)
0x180276029  test    eax, eax
0x18027602b  jz      short loc_18027606B
0x18027602d  mov     ebx, esi
0x18027602f  xor     r13d, r13d
0x180276032  cmp     [rsp+900h+var_8A8], r13d
0x180276037  jnz     short loc_18027603F
0x180276039  call    cs:__imp_CoUninitialize
0x18027603f  mov     eax, ebx
0x180276041  mov     rcx, [rbp+800h+var_40]
0x180276048  xor     rcx, rsp; StackCookie
0x18027604b  call    __security_check_cookie
0x180276050  mov     rbx, [rsp+900h+arg_8]
0x180276058  add     rsp, 8D0h
0x18027605f  pop     r15
0x180276061  pop     r14
0x180276063  pop     r13
0x180276065  pop     r12
0x180276067  pop     rdi
0x180276068  pop     rsi
0x180276069  pop     rbp
0x18027606a  retn
0x18027606b  mov     r8, rdi; HWND
0x18027606e  lea     rdx, [rsp+900h+var_8A0]; struct CPLEXECINFO *
0x180276073  lea     rcx, [rbp+800h+var_480]; struct CPLAPPLETID *
0x18027607a  call    ?CPL_Identify@@YAHPEAUCPLAPPLETID@@PEBUCPLEXECINFO@@PEAUHWND__@@@Z; CPL_Identify(CPLAPPLETID *,CPLEXECINFO const *,HWND__ *)
0x18027607f  test    eax, eax
0x180276081  jz      short loc_18027602F
0x180276083  test    r14b, 2
0x180276087  jz      short loc_1802760AF
0x180276089  lea     rdx, [rbp+800h+var_480]; struct CPLAPPLETID *
0x180276090  mov     rcx, rdi; HWND
0x180276093  call    ?_SwitchToControlPanelWindowAlreadyShowing@@YAHPEAUHWND__@@PEAUCPLAPPLETID@@@Z; _SwitchToControlPanelWindowAlreadyShowing(HWND__ *,CPLAPPLETID *)
0x180276098  test    eax, eax
0x18027609a  jz      short loc_1802760AF
0x18027609c  mov     ebx, esi
0x18027609e  xor     r13d, r13d
0x1802760a1  lea     rcx, [rbp+800h+var_480]; struct CPLAPPLETID *
0x1802760a8  call    ?CPL_UnIdentify@@YAXPEAUCPLAPPLETID@@@Z; CPL_UnIdentify(CPLAPPLETID *)
0x1802760ad  jmp     short loc_180276032
0x1802760af  test    sil, r14b
0x1802760b2  jz      short loc_18027609E
0x1802760b4  xor     r14d, r14d
0x1802760b7  lea     rcx, [rsp+900h+var_8C0]
0x1802760bc  mov     [rsp+900h+var_8C0], r14d
0x1802760c1  call    SHIsCurrentAppElevated
0x1802760c6  test    eax, eax
0x1802760c8  js      short loc_18027609E
0x1802760ca  cmp     [rsp+900h+var_8C0], r14d
0x1802760cf  jnz     short loc_18027611B
0x1802760d1  test    r15d, r15d
0x1802760d4  jz      short loc_1802760E9
0x1802760d6  lea     rcx, [rsp+900h+var_89C]; unsigned __int16 *
0x1802760db  call    ?_GetRunLevelForCPL@@YA?AW4ACTCTX_REQUESTED_RUN_LEVEL@@PEBG@Z; _GetRunLevelForCPL(ushort const *)
0x1802760e0  test    eax, eax
0x1802760e2  jz      short loc_1802760F1
0x1802760e4  sub     eax, 1
0x1802760e7  jz      short loc_18027611B
0x1802760e9  xor     r13d, r13d
0x1802760ec  mov     ebx, r13d
0x1802760ef  jmp     short loc_1802760A1
0x1802760f1  mov     r9d, [rsp+900h+var_8B8]; int
0x1802760f6  lea     rax, [rsp+900h+var_8BC]
0x1802760fb  mov     r8, r12; unsigned __int16 *
0x1802760fe  mov     qword ptr [rsp+900h+fuStyle], rax; int *
0x180276103  lea     rdx, [rsp+900h+var_8A0]; struct CPLEXECINFO *
0x180276108  mov     rcx, rdi; HWND
0x18027610b  call    ?_HandleUnmarkedLegacyCPL@@YAHPEAUHWND__@@PEBUCPLEXECINFO@@PEBGHPEAH@Z; _HandleUnmarkedLegacyCPL(HWND__ *,CPLEXECINFO const *,ushort const *,int,int *)
0x180276110  test    eax, eax
0x180276112  jz      loc_1802761A1
0x180276118  mov     ebx, r14d
0x18027611b  lea     r9, [rsp+900h+var_8A0]; struct CPLEXECINFO *
0x180276120  mov     [rsp+900h+var_8BC], r14d
0x180276125  lea     r8, [rsp+900h+var_8BC]; int *
0x18027612a  mov     [rsp+900h+fuStyle], esi; int
0x18027612e  xor     edx, edx; HICON *
0x180276130  lea     rcx, [rsp+900h+var_8B0]; struct CPLMODULE **
0x180276135  call    ?LoadAndFindApplet@@YAHPEAPEAUCPLMODULE@@PEAPEAUHICON__@@PEAHPEBUCPLEXECINFO@@H@Z; LoadAndFindApplet(CPLMODULE * *,HICON__ * *,int *,CPLEXECINFO const *,int)
0x18027613a  test    eax, eax
0x18027613c  jz      loc_18027609E
0x180276142  mov     r14, [rsp+900h+var_8B0]
0x180276147  movsxd  r12, [rsp+900h+var_8BC]
0x18027614c  mov     edx, r12d; i
0x18027614f  mov     rcx, [r14+230h]; hdsa
0x180276156  call    DSA_GetItemPtr
0x18027615b  mov     edx, 104h; unsigned __int64
0x180276160  mov     [rsp+900h+var_8B0], rax
0x180276165  lea     rcx, [rbp+800h+pszMenu]; unsigned __int16 *
0x18027616c  mov     r8, [rax]; unsigned __int16 *
0x18027616f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180276174  test    eax, eax
0x180276176  js      loc_1802763BB
0x18027617c  lea     rcx, [rbp+800h+pszMenu]; pszMenu
0x180276183  call    cs:__imp_SHStripMneumonicW
0x180276189  xor     eax, eax
0x18027618b  cmp     word ptr [rbp+800h+var_480+2], ax
0x180276192  jz      short loc_1802761AA
0x180276194  test    r12d, r12d
0x180276197  jnz     short loc_1802761CD
0x180276199  or      dword ptr [rbp+800h+var_470], esi
0x18027619f  jmp     short loc_1802761CD
0x1802761a1  mov     ebx, [rsp+900h+var_8BC]
0x1802761a5  jmp     loc_18027609E
0x1802761aa  or      dword ptr [rbp+800h+var_470], esi
0x1802761b0  lea     rcx, [rbp+800h+pszMenu]; lpString
0x1802761b7  call    cs:__imp_GlobalAddAtomW
0x1802761bd  mov     word ptr [rbp+800h+var_480+2], ax
0x1802761c4  test    ax, ax
0x1802761c7  jz      loc_1802763BB
0x1802761cd  lea     rdx, [rbp+800h+var_480]; struct CPLAPPLETID *
0x1802761d4  mov     rcx, rdi; hWnd
0x1802761d7  call    ?CPL_SetWindowProps@@YAHPEAUHWND__@@PEAUCPLAPPLETID@@@Z; CPL_SetWindowProps(HWND__ *,CPLAPPLETID *)
0x1802761dc  test    eax, eax
0x1802761de  jz      loc_1802763BB
0x1802761e4  test    rdi, rdi
0x1802761e7  jz      short loc_180276200
0x1802761e9  mov     r8, [rsp+900h+var_8B0]; struct CPLITEM *
0x1802761ee  lea     r9, [rbp+800h+pszMenu]; unsigned __int16 *
0x1802761f5  mov     rdx, r14; struct CPLMODULE *
0x1802761f8  mov     rcx, rdi; HWND
0x1802761fb  call    ?_SetIconToCPLStubWindow@@YAHPEAUHWND__@@PEAUCPLMODULE@@PEAUCPLITEM@@PEBG@Z; _SetIconToCPLStubWindow(HWND__ *,CPLMODULE *,CPLITEM *,ushort const *)
0x180276200  test    r15d, r15d
0x180276203  jz      short loc_180276264
0x180276205  mov     rcx, [r14+240h]; hActCtx
0x18027620c  call    SHInitLUAVirtualizationFromActCtx
0x180276211  test    eax, eax
0x180276213  jnz     short loc_180276264
0x180276215  call    cs:__imp_SHIsCurrentThreadOnUserDesktop
0x18027621b  xor     r13d, r13d
0x18027621e  test    eax, eax
0x180276220  jz      loc_180276380
0x180276226  lea     rcx, aRequestedrunle; "requestedRunLevel"
0x18027622d  mov     r9d, 1041h; lpcTitle
0x180276233  mov     [rsp+900h+lpDefaultChar], rcx
0x180276238  lea     rax, [r14+20h]
0x18027623c  mov     rcx, cs:g_hinst; hAppInst
0x180276243  mov     r8d, 2453h; lpcText
0x180276249  mov     qword ptr [rsp+900h+cbMultiByte], rax
0x18027624e  mov     rdx, rdi; hWnd
0x180276251  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x180276259  call    cs:__imp_ShellMessageBoxW
0x18027625f  jmp     loc_180276380
0x180276264  mov     r8, [rbp+800h+lpWideCharStr]
0x18027626b  test    r8, r8
0x18027626e  jz      short loc_18027629A
0x180276270  mov     qword ptr [rsp+900h+fuStyle], r8; __int64
0x180276275  mov     r9, r12; __int64
0x180276278  mov     r8d, 0Ah; unsigned int
0x18027627e  mov     rdx, rdi; HWND
0x180276281  mov     rcx, r14; struct CPLMODULE *
0x180276284  call    ?CPL_CallEntry@@YA_JPEBUCPLMODULE@@PEAUHWND__@@I_J2@Z; CPL_CallEntry(CPLMODULE const *,HWND__ *,uint,__int64,__int64)
0x180276289  mov     r8, [rbp+800h+lpWideCharStr]
0x180276290  xor     ecx, ecx
0x180276292  test    rax, rax
0x180276295  mov     ebx, ecx
0x180276297  setnz   bl
0x18027629a  test    r15d, r15d
0x18027629d  jnz     short loc_1802762A4
0x18027629f  test    r13d, r13d
0x1802762a2  jz      short loc_1802762B3
0x1802762a4  mov     rcx, r14; struct CPLMODULE *
0x1802762a7  call    ?_ResetWindowsVersionOnProcessBlock@@YAXPEAUCPLMODULE@@@Z; _ResetWindowsVersionOnProcessBlock(CPLMODULE *)
0x1802762ac  mov     r8, [rbp+800h+lpWideCharStr]; lpWideCharStr
0x1802762b3  xor     r13d, r13d
0x1802762b6  test    r8, r8
0x1802762b9  jz      loc_180276358
0x1802762bf  test    ebx, ebx
0x1802762c1  jnz     loc_180276380
0x1802762c7  mov     [rsp+900h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1802762cc  or      r9d, 0FFFFFFFFh; cchWideChar
0x1802762d0  mov     [rsp+900h+lpDefaultChar], r13; lpDefaultChar
0x1802762d5  mov     edx, 400h; dwFlags
0x1802762da  mov     [rsp+900h+cbMultiByte], r13d; cbMultiByte
0x1802762df  xor     ecx, ecx; CodePage
0x1802762e1  mov     qword ptr [rsp+900h+fuStyle], r13; lpMultiByteStr
0x1802762e6  call    cs:__imp_WideCharToMultiByte
0x1802762ec  movsxd  rbx, eax
0x1802762ef  lea     ecx, [r13+40h]; uFlags
0x1802762f3  mov     rdx, rbx; uBytes
0x1802762f6  call    cs:__imp_LocalAlloc
0x1802762fc  mov     r15, rax
0x1802762ff  test    rax, rax
0x180276302  jz      short loc_18027635C
0x180276304  mov     r8, [rbp+800h+lpWideCharStr]; lpWideCharStr
0x18027630b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18027630f  mov     [rsp+900h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180276314  mov     edx, 400h; dwFlags
0x180276319  mov     [rsp+900h+lpDefaultChar], r13; lpDefaultChar
0x18027631e  xor     ecx, ecx; CodePage
0x180276320  mov     [rsp+900h+cbMultiByte], ebx; cbMultiByte
0x180276324  mov     qword ptr [rsp+900h+fuStyle], rax; lpMultiByteStr
0x180276329  call    cs:__imp_WideCharToMultiByte
0x18027632f  mov     r9, r12; __int64
0x180276332  mov     qword ptr [rsp+900h+fuStyle], r15; __int64
0x180276337  lea     r8d, [r13+9]; unsigned int
0x18027633b  mov     rdx, rdi; HWND
0x18027633e  mov     rcx, r14; struct CPLMODULE *
0x180276341  call    ?CPL_CallEntry@@YA_JPEBUCPLMODULE@@PEAUHWND__@@I_J2@Z; CPL_CallEntry(CPLMODULE const *,HWND__ *,uint,__int64,__int64)
0x180276346  test    rax, rax
  ... truncated ...
```
