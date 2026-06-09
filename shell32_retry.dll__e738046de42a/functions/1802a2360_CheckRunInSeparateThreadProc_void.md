# CheckRunInSeparateThreadProc(void *)

- ea: `0x1802a2360`
- end: `0x1802a25c8`
- name: `?CheckRunInSeparateThreadProc@@YAKPEAX@Z`
- size: `616`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001df70`
- `0x1800bb328`
- `0x180233280`
- `0x1802a2360`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802a256e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802a256e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802a23df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802a23df`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802a23ec`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802a23ec`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1802a24e3`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1802a24e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802a2466`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802a2466`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1802a2430`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1802a2430`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802a247c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802a247c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802a24a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802a24a0`
- `api-ms-win-core-kernel32-legacy-l1-1-2!GetBinaryTypeW` at `0x1802a24fe`
- `api-ms-win-core-kernel32-legacy-l1-1-2!GetBinaryTypeW` at `0x1802a24fe`
- `USER32!EnableWindow` at `0x1802a253a`
- `USER32!EnableWindow` at `0x1802a253a`
- `USER32!CheckDlgButton` at `0x1802a2521`
- `USER32!CheckDlgButton` at `0x1802a2521`
- `USER32!GetWindowLongPtrW` at `0x1802a2548`
- `USER32!GetWindowLongPtrW` at `0x1802a2548`
- `USER32!GetWindowTextW` at `0x1802a2425`
- `USER32!GetWindowTextW` at `0x1802a2425`
- `USER32!GetDlgItem` at `0x1802a2411`
- `USER32!GetDlgItem` at `0x1802a252f`
- `USER32!GetDlgItem` at `0x1802a2411`
- `USER32!GetDlgItem` at `0x1802a252f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802a257f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802a257f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a243b`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a24ad`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a243b`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a24ad`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802a2457`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802a2457`

## pseudocode

```c
__int64 __fastcall CheckRunInSeparateThreadProc(HWND Parameter, __int64 a2, int a3)
{
  int v4; // esi
  HWND DlgItem; // rax
  UINT v6; // r8d
  BOOL v7; // ebx
  LPWSTR ArgsW; // rax
  HWND v9; // rax
  LONG_PTR WindowLongPtrW; // rax
  int v11; // ecx
  unsigned int v12; // ecx
  int v13; // ecx
  int v14; // r8d
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  DWORD BinaryType; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)Parameter,
      (unsigned int)&ShellTask_RunDialog_CheckRunInSeparateThread_Start,
      a3,
      1,
      (__int64)v18);
  BinaryType = 0;
  FilePart = 0;
  v4 = SHCoInitialize();
  while ( g_bCheckRunInSep )
  {
    WaitForSingleObject(g_hCheckNow, 0xFFFFFFFF);
    ResetEvent(g_hCheckNow);
    if ( g_bCheckRunInSep )
    {
      String[0] = 0;
      Buffer[0] = 0;
      DlgItem = GetDlgItem(Parameter, 12298);
      GetWindowTextW(DlgItem, String, 261);
      PathRemoveBlanksW(String);
      if ( PathIsNetworkPathW(String) )
        goto LABEL_7;
      if ( !(unsigned int)PathFileExistsAndAttributesW(String, 0) )
      {
        ArgsW = PathGetArgsW(String);
        if ( *ArgsW )
          *(ArgsW - 1) = 0;
        PathUnquoteSpacesW(String);
      }
      if ( String[0]
        && ((SHExpandEnvironmentStringsW(String, pszPath, 261), PathIsNetworkPathW(pszPath))
         || SearchPathW(0, pszPath, L".EXE", 0x105u, Buffer, &FilePart) - 1 <= 0x103
         && GetBinaryTypeW(Buffer, &BinaryType)
         && BinaryType == 2) )
      {
LABEL_7:
        v6 = 0;
        v7 = 1;
      }
      else
      {
        v7 = 0;
        v6 = 1;
      }
      CheckDlgButton(Parameter, 12306, v6);
      v9 = GetDlgItem(Parameter, 12306);
      EnableWindow(v9, v7);
      WindowLongPtrW = GetWindowLongPtrW(Parameter, 16);
      if ( WindowLongPtrW )
      {
        v11 = *(_DWORD *)(WindowLongPtrW + 56);
        if ( v7 )
          v12 = v11 | 0x10;
        else
          v12 = v11 & 0xFFFFFFEF;
        *(_DWORD *)(WindowLongPtrW + 56) = v12;
      }
    }
  }
  CloseHandle(g_hCheckNow);
  g_hCheckNow = 0;
  if ( !v4 )
    CoUninitialize();
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v13,
      (unsigned int)&ShellTask_RunDialog_CheckRunInSeparateThread_Stop,
      v14,
      1,
      (__int64)v18);
  return 0;
}

```

## disassembly

```asm
0x1802a2360  push    rbp
0x1802a2362  push    rbx
0x1802a2363  push    rsi
0x1802a2364  push    rdi
0x1802a2365  push    r14
0x1802a2367  push    r15
0x1802a2369  lea     rbp, [rsp-598h]
0x1802a2371  sub     rsp, 698h
0x1802a2378  mov     rax, cs:__security_cookie
0x1802a237f  xor     rax, rsp
0x1802a2382  mov     [rbp+5C0h+var_40], rax
0x1802a2389  mov     r15d, 1
0x1802a238f  mov     rdi, rcx
0x1802a2392  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802a2399  jz      short loc_1802A23B4
0x1802a239b  lea     rax, [rsp+6C0h+var_680]
0x1802a23a0  mov     r9d, r15d
0x1802a23a3  lea     rdx, ShellTask_RunDialog_CheckRunInSeparateThread_Start
0x1802a23aa  mov     [rsp+6C0h+lpBuffer], rax
0x1802a23af  call    McGenEventWrite_EtwEventWriteTransfer
0x1802a23b4  xor     r14d, r14d
0x1802a23b7  mov     [rsp+6C0h+BinaryType], r14d
0x1802a23bc  mov     [rsp+6C0h+FilePart], r14
0x1802a23c1  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1802a23c6  mov     esi, eax
0x1802a23c8  cmp     cs:?g_bCheckRunInSep@@3HA, r14d; int g_bCheckRunInSep
0x1802a23cf  mov     rcx, cs:?g_hCheckNow@@3PEAXEA; hObject
0x1802a23d6  jz      loc_1802A256E
0x1802a23dc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1802a23df  call    cs:__imp_WaitForSingleObject
0x1802a23e5  mov     rcx, cs:?g_hCheckNow@@3PEAXEA; hEvent
0x1802a23ec  call    cs:__imp_ResetEvent
0x1802a23f2  cmp     cs:?g_bCheckRunInSep@@3HA, r14d; int g_bCheckRunInSep
0x1802a23f9  jz      short loc_1802A23C8
0x1802a23fb  mov     edx, 300Ah; nIDDlgItem
0x1802a2400  mov     [rsp+6C0h+String], r14w
0x1802a2406  mov     rcx, rdi; hDlg
0x1802a2409  mov     [rbp+5C0h+Buffer], r14w
0x1802a2411  call    cs:__imp_GetDlgItem
0x1802a2417  mov     r8d, 105h; nMaxCount
0x1802a241d  lea     rdx, [rsp+6C0h+String]; lpString
0x1802a2422  mov     rcx, rax; hWnd
0x1802a2425  call    cs:__imp_GetWindowTextW
0x1802a242b  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802a2430  call    cs:__imp_PathRemoveBlanksW
0x1802a2436  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802a243b  call    cs:__imp_PathIsNetworkPathW
0x1802a2441  test    eax, eax
0x1802a2443  jz      short loc_1802A2450
0x1802a2445  mov     r8d, r14d
0x1802a2448  mov     ebx, r15d
0x1802a244b  jmp     loc_1802A2519
0x1802a2450  xor     edx, edx
0x1802a2452  lea     rcx, [rsp+6C0h+String]
0x1802a2457  call    cs:__imp_PathFileExistsAndAttributesW
0x1802a245d  test    eax, eax
0x1802a245f  jnz     short loc_1802A2482
0x1802a2461  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802a2466  call    cs:__imp_PathGetArgsW
0x1802a246c  cmp     [rax], r14w
0x1802a2470  jz      short loc_1802A2477
0x1802a2472  mov     [rax-2], r14w
0x1802a2477  lea     rcx, [rsp+6C0h+String]; lpsz
0x1802a247c  call    cs:__imp_PathUnquoteSpacesW
0x1802a2482  cmp     [rsp+6C0h+String], r14w
0x1802a2488  jz      loc_1802A2513
0x1802a248e  mov     r8d, 105h
0x1802a2494  lea     rdx, [rbp+5C0h+pszPath]
0x1802a249b  lea     rcx, [rsp+6C0h+String]
0x1802a24a0  call    cs:__imp_SHExpandEnvironmentStringsW
0x1802a24a6  lea     rcx, [rbp+5C0h+pszPath]; pszPath
0x1802a24ad  call    cs:__imp_PathIsNetworkPathW
0x1802a24b3  test    eax, eax
0x1802a24b5  jnz     short loc_1802A2445
0x1802a24b7  lea     rax, [rsp+6C0h+FilePart]
0x1802a24bc  mov     r9d, 105h; nBufferLength
0x1802a24c2  mov     [rsp+6C0h+lpFilePart], rax; lpFilePart
0x1802a24c7  lea     r8, Extension; ".EXE"
0x1802a24ce  lea     rax, [rbp+5C0h+Buffer]
0x1802a24d5  xor     ecx, ecx; lpPath
0x1802a24d7  lea     rdx, [rbp+5C0h+pszPath]; lpFileName
0x1802a24de  mov     [rsp+6C0h+lpBuffer], rax; lpBuffer
0x1802a24e3  call    cs:__imp_SearchPathW
0x1802a24e9  dec     eax
0x1802a24eb  cmp     eax, 103h
0x1802a24f0  ja      short loc_1802A2513
0x1802a24f2  lea     rdx, [rsp+6C0h+BinaryType]; lpBinaryType
0x1802a24f7  lea     rcx, [rbp+5C0h+Buffer]; lpApplicationName
0x1802a24fe  call    cs:__imp_GetBinaryTypeW
0x1802a2504  test    eax, eax
0x1802a2506  jz      short loc_1802A2513
0x1802a2508  cmp     [rsp+6C0h+BinaryType], 2
0x1802a250d  jz      loc_1802A2445
0x1802a2513  mov     ebx, r14d
0x1802a2516  mov     r8d, r15d; uCheck
0x1802a2519  mov     edx, 3012h; nIDButton
0x1802a251e  mov     rcx, rdi; hDlg
0x1802a2521  call    cs:__imp_CheckDlgButton
0x1802a2527  mov     edx, 3012h; nIDDlgItem
0x1802a252c  mov     rcx, rdi; hDlg
0x1802a252f  call    cs:__imp_GetDlgItem
0x1802a2535  mov     rcx, rax; hWnd
0x1802a2538  mov     edx, ebx; bEnable
0x1802a253a  call    cs:__imp_EnableWindow
0x1802a2540  mov     edx, 10h; nIndex
0x1802a2545  mov     rcx, rdi; hWnd
0x1802a2548  call    cs:__imp_GetWindowLongPtrW
0x1802a254e  test    rax, rax
0x1802a2551  jz      loc_1802A23C8
0x1802a2557  mov     ecx, [rax+38h]
0x1802a255a  test    ebx, ebx
0x1802a255c  jz      short loc_1802A2563
0x1802a255e  or      ecx, 10h
0x1802a2561  jmp     short loc_1802A2566
0x1802a2563  and     ecx, 0FFFFFFEFh
0x1802a2566  mov     [rax+38h], ecx
0x1802a2569  jmp     loc_1802A23C8
0x1802a256e  call    cs:__imp_CloseHandle
0x1802a2574  mov     cs:?g_hCheckNow@@3PEAXEA, r14; void * g_hCheckNow
0x1802a257b  test    esi, esi
0x1802a257d  jnz     short loc_1802A2585
0x1802a257f  call    cs:__imp_CoUninitialize
0x1802a2585  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802a258c  jz      short loc_1802A25A7
0x1802a258e  lea     rax, [rsp+6C0h+var_680]
0x1802a2593  mov     r9d, r15d
0x1802a2596  lea     rdx, ShellTask_RunDialog_CheckRunInSeparateThread_Stop
0x1802a259d  mov     [rsp+6C0h+lpBuffer], rax
0x1802a25a2  call    McGenEventWrite_EtwEventWriteTransfer
0x1802a25a7  xor     eax, eax
0x1802a25a9  mov     rcx, [rbp+5C0h+var_40]
0x1802a25b0  xor     rcx, rsp; StackCookie
0x1802a25b3  call    __security_check_cookie
0x1802a25b8  add     rsp, 698h
0x1802a25bf  pop     r15
0x1802a25c1  pop     r14
0x1802a25c3  pop     rdi
0x1802a25c4  pop     rsi
0x1802a25c5  pop     rbx
0x1802a25c6  pop     rbp
0x1802a25c7  retn
```
