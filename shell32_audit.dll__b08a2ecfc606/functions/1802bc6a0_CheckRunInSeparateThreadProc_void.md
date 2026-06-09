# CheckRunInSeparateThreadProc(void *)

- ea: `0x1802bc6a0`
- end: `0x1802bc97f`
- name: `?CheckRunInSeparateThreadProc@@YAKPEAX@Z`
- size: `735`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180016364`
- `0x180055afc`
- `0x180249490`
- `0x1802bc6a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bc918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802bc918`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802bc732`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802bc732`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802bc71f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802bc71f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1802bc869`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1802bc869`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802bc7d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1802bc7d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1802bc788`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1802bc788`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bc7ec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bc7ec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802bc816`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1802bc816`
- `api-ms-win-core-kernel32-legacy-l1-1-2!GetBinaryTypeW` at `0x1802bc88a`
- `api-ms-win-core-kernel32-legacy-l1-1-2!GetBinaryTypeW` at `0x1802bc88a`
- `USER32!EnableWindow` at `0x1802bc8d8`
- `USER32!EnableWindow` at `0x1802bc8d8`
- `USER32!CheckDlgButton` at `0x1802bc8b3`
- `USER32!CheckDlgButton` at `0x1802bc8b3`
- `USER32!GetWindowLongPtrW` at `0x1802bc8ec`
- `USER32!GetWindowLongPtrW` at `0x1802bc8ec`
- `USER32!GetWindowTextW` at `0x1802bc777`
- `USER32!GetWindowTextW` at `0x1802bc777`
- `USER32!GetDlgItem` at `0x1802bc75d`
- `USER32!GetDlgItem` at `0x1802bc8c7`
- `USER32!GetDlgItem` at `0x1802bc75d`
- `USER32!GetDlgItem` at `0x1802bc8c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802bc92f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802bc92f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802bc799`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802bc829`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802bc799`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802bc829`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802bc7bb`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802bc7bb`

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
0x1802bc6a0  push    rbp
0x1802bc6a2  push    rbx
0x1802bc6a3  push    rsi
0x1802bc6a4  push    rdi
0x1802bc6a5  push    r14
0x1802bc6a7  push    r15
0x1802bc6a9  lea     rbp, [rsp-598h]
0x1802bc6b1  sub     rsp, 698h
0x1802bc6b8  mov     rax, cs:__security_cookie
0x1802bc6bf  xor     rax, rsp
0x1802bc6c2  mov     [rbp+5C0h+var_40], rax
0x1802bc6c9  mov     r15d, 1
0x1802bc6cf  mov     rdi, rcx
0x1802bc6d2  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802bc6d9  jz      short loc_1802BC6F4
0x1802bc6db  lea     rax, [rsp+6C0h+var_680]
0x1802bc6e0  mov     r9d, r15d
0x1802bc6e3  lea     rdx, ShellTask_RunDialog_CheckRunInSeparateThread_Start
0x1802bc6ea  mov     [rsp+6C0h+lpBuffer], rax
0x1802bc6ef  call    McGenEventWrite_EtwEventWriteTransfer
0x1802bc6f4  xor     r14d, r14d
0x1802bc6f7  mov     [rsp+6C0h+BinaryType], r14d
0x1802bc6fc  mov     [rsp+6C0h+FilePart], r14
0x1802bc701  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1802bc706  mov     esi, eax
0x1802bc708  cmp     cs:?g_bCheckRunInSep@@3HA, r14d; int g_bCheckRunInSep
0x1802bc70f  mov     rcx, cs:?g_hCheckNow@@3PEAXEA; hObject
0x1802bc716  jz      loc_1802BC918
0x1802bc71c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1802bc71f  call    cs:__imp_WaitForSingleObject
0x1802bc726  nop     dword ptr [rax+rax+00h]
0x1802bc72b  mov     rcx, cs:?g_hCheckNow@@3PEAXEA; hEvent
0x1802bc732  call    cs:__imp_ResetEvent
0x1802bc739  nop     dword ptr [rax+rax+00h]
0x1802bc73e  cmp     cs:?g_bCheckRunInSep@@3HA, r14d; int g_bCheckRunInSep
0x1802bc745  jz      short loc_1802BC708
0x1802bc747  mov     edx, 300Ah; nIDDlgItem
0x1802bc74c  mov     [rsp+6C0h+String], r14w
0x1802bc752  mov     rcx, rdi; hDlg
0x1802bc755  mov     [rbp+5C0h+Buffer], r14w
0x1802bc75d  call    cs:__imp_GetDlgItem
0x1802bc764  nop     dword ptr [rax+rax+00h]
0x1802bc769  mov     r8d, 105h; nMaxCount
0x1802bc76f  lea     rdx, [rsp+6C0h+String]; lpString
0x1802bc774  mov     rcx, rax; hWnd
0x1802bc777  call    cs:__imp_GetWindowTextW
0x1802bc77e  nop     dword ptr [rax+rax+00h]
0x1802bc783  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802bc788  call    cs:__imp_PathRemoveBlanksW
0x1802bc78f  nop     dword ptr [rax+rax+00h]
0x1802bc794  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802bc799  call    cs:__imp_PathIsNetworkPathW
0x1802bc7a0  nop     dword ptr [rax+rax+00h]
0x1802bc7a5  test    eax, eax
0x1802bc7a7  jz      short loc_1802BC7B4
0x1802bc7a9  mov     r8d, r14d
0x1802bc7ac  mov     ebx, r15d
0x1802bc7af  jmp     loc_1802BC8AB
0x1802bc7b4  xor     edx, edx
0x1802bc7b6  lea     rcx, [rsp+6C0h+String]
0x1802bc7bb  call    cs:__imp_PathFileExistsAndAttributesW
0x1802bc7c2  nop     dword ptr [rax+rax+00h]
0x1802bc7c7  test    eax, eax
0x1802bc7c9  jnz     short loc_1802BC7F8
0x1802bc7cb  lea     rcx, [rsp+6C0h+String]; pszPath
0x1802bc7d0  call    cs:__imp_PathGetArgsW
0x1802bc7d7  nop     dword ptr [rax+rax+00h]
0x1802bc7dc  cmp     [rax], r14w
0x1802bc7e0  jz      short loc_1802BC7E7
0x1802bc7e2  mov     [rax-2], r14w
0x1802bc7e7  lea     rcx, [rsp+6C0h+String]; lpsz
0x1802bc7ec  call    cs:__imp_PathUnquoteSpacesW
0x1802bc7f3  nop     dword ptr [rax+rax+00h]
0x1802bc7f8  cmp     [rsp+6C0h+String], r14w
0x1802bc7fe  jz      loc_1802BC8A5
0x1802bc804  mov     r8d, 105h
0x1802bc80a  lea     rdx, [rbp+5C0h+pszPath]
0x1802bc811  lea     rcx, [rsp+6C0h+String]
0x1802bc816  call    cs:__imp_SHExpandEnvironmentStringsW
0x1802bc81d  nop     dword ptr [rax+rax+00h]
0x1802bc822  lea     rcx, [rbp+5C0h+pszPath]; pszPath
0x1802bc829  call    cs:__imp_PathIsNetworkPathW
0x1802bc830  nop     dword ptr [rax+rax+00h]
0x1802bc835  test    eax, eax
0x1802bc837  jnz     loc_1802BC7A9
0x1802bc83d  lea     rax, [rsp+6C0h+FilePart]
0x1802bc842  mov     r9d, 105h; nBufferLength
0x1802bc848  mov     [rsp+6C0h+lpFilePart], rax; lpFilePart
0x1802bc84d  lea     r8, Extension; ".EXE"
0x1802bc854  lea     rax, [rbp+5C0h+Buffer]
0x1802bc85b  xor     ecx, ecx; lpPath
0x1802bc85d  lea     rdx, [rbp+5C0h+pszPath]; lpFileName
0x1802bc864  mov     [rsp+6C0h+lpBuffer], rax; lpBuffer
0x1802bc869  call    cs:__imp_SearchPathW
0x1802bc870  nop     dword ptr [rax+rax+00h]
0x1802bc875  dec     eax
0x1802bc877  cmp     eax, 103h
0x1802bc87c  ja      short loc_1802BC8A5
0x1802bc87e  lea     rdx, [rsp+6C0h+BinaryType]; lpBinaryType
0x1802bc883  lea     rcx, [rbp+5C0h+Buffer]; lpApplicationName
0x1802bc88a  call    cs:__imp_GetBinaryTypeW
0x1802bc891  nop     dword ptr [rax+rax+00h]
0x1802bc896  test    eax, eax
0x1802bc898  jz      short loc_1802BC8A5
0x1802bc89a  cmp     [rsp+6C0h+BinaryType], 2
0x1802bc89f  jz      loc_1802BC7A9
0x1802bc8a5  mov     ebx, r14d
0x1802bc8a8  mov     r8d, r15d; uCheck
0x1802bc8ab  mov     edx, 3012h; nIDButton
0x1802bc8b0  mov     rcx, rdi; hDlg
0x1802bc8b3  call    cs:__imp_CheckDlgButton
0x1802bc8ba  nop     dword ptr [rax+rax+00h]
0x1802bc8bf  mov     edx, 3012h; nIDDlgItem
0x1802bc8c4  mov     rcx, rdi; hDlg
0x1802bc8c7  call    cs:__imp_GetDlgItem
0x1802bc8ce  nop     dword ptr [rax+rax+00h]
0x1802bc8d3  mov     rcx, rax; hWnd
0x1802bc8d6  mov     edx, ebx; bEnable
0x1802bc8d8  call    cs:__imp_EnableWindow
0x1802bc8df  nop     dword ptr [rax+rax+00h]
0x1802bc8e4  mov     edx, 10h; nIndex
0x1802bc8e9  mov     rcx, rdi; hWnd
0x1802bc8ec  call    cs:__imp_GetWindowLongPtrW
0x1802bc8f3  nop     dword ptr [rax+rax+00h]
0x1802bc8f8  test    rax, rax
0x1802bc8fb  jz      loc_1802BC708
0x1802bc901  mov     ecx, [rax+38h]
0x1802bc904  test    ebx, ebx
0x1802bc906  jz      short loc_1802BC90D
0x1802bc908  or      ecx, 10h
0x1802bc90b  jmp     short loc_1802BC910
0x1802bc90d  and     ecx, 0FFFFFFEFh
0x1802bc910  mov     [rax+38h], ecx
0x1802bc913  jmp     loc_1802BC708
0x1802bc918  call    cs:__imp_CloseHandle
0x1802bc91f  nop     dword ptr [rax+rax+00h]
0x1802bc924  mov     cs:?g_hCheckNow@@3PEAXEA, r14; void * g_hCheckNow
0x1802bc92b  test    esi, esi
0x1802bc92d  jnz     short loc_1802BC93B
0x1802bc92f  call    cs:__imp_CoUninitialize
0x1802bc936  nop     dword ptr [rax+rax+00h]
0x1802bc93b  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1802bc942  jz      short loc_1802BC95D
0x1802bc944  lea     rax, [rsp+6C0h+var_680]
0x1802bc949  mov     r9d, r15d
0x1802bc94c  lea     rdx, ShellTask_RunDialog_CheckRunInSeparateThread_Stop
0x1802bc953  mov     [rsp+6C0h+lpBuffer], rax
0x1802bc958  call    McGenEventWrite_EtwEventWriteTransfer
0x1802bc95d  xor     eax, eax
0x1802bc95f  mov     rcx, [rbp+5C0h+var_40]
0x1802bc966  xor     rcx, rsp; StackCookie
0x1802bc969  call    __security_check_cookie
0x1802bc96e  add     rsp, 698h
0x1802bc975  pop     r15
0x1802bc977  pop     r14
0x1802bc979  pop     rdi
0x1802bc97a  pop     rsi
0x1802bc97b  pop     rbx
0x1802bc97c  pop     rbp
0x1802bc97d  retn
```
