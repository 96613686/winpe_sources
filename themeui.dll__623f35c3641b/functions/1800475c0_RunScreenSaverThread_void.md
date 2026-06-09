# RunScreenSaverThread(void *)

- ea: `0x1800475c0`
- end: `0x1800477fa`
- name: `?RunScreenSaverThread@@YAKPEAX@Z`
- size: `570`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c608`
- `0x1800358c0`
- `0x18003633c`
- `0x1800475c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800477d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800477d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800475fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800475fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800476d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800476d5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800476c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800476c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800476e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800476eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800476e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800476eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800477c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800477c2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180047607`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180047607`
- `USER32!PostMessageW` at `0x180047732`
- `USER32!PostMessageW` at `0x180047757`
- `USER32!PostMessageW` at `0x18004776b`
- `USER32!PostMessageW` at `0x180047732`
- `USER32!PostMessageW` at `0x180047757`
- `USER32!PostMessageW` at `0x18004776b`
- `USER32!EnableWindow` at `0x1800477ad`
- `USER32!EnableWindow` at `0x1800477b9`
- `USER32!EnableWindow` at `0x1800477ad`
- `USER32!EnableWindow` at `0x1800477b9`
- `USER32!GetDlgItem` at `0x180047618`
- `USER32!GetDlgItem` at `0x180047629`
- `USER32!GetDlgItem` at `0x180047740`
- `USER32!GetDlgItem` at `0x180047618`
- `USER32!GetDlgItem` at `0x180047629`
- `USER32!GetDlgItem` at `0x180047740`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180047706`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18004771e`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180047706`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18004771e`

## pseudocode

```c
__int64 __fastcall RunScreenSaverThread(PVOID Parameter)
{
  HMODULE LibraryW; // rdi
  HWND DlgItem; // rsi
  HWND v4; // r14
  HWND v5; // rax
  unsigned int v6; // ecx
  int v7; // eax
  BOOL v8; // edx
  unsigned int v10; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+E0h] [rbp-20h] BYREF

  GetModuleFileNameW(g_hinst, Filename, 0x104u);
  LibraryW = LoadLibraryW(Filename);
  DlgItem = GetDlgItem(*(HWND *)Parameter, 1303);
  v4 = GetDlgItem(*(HWND *)Parameter, 1304);
  if ( dword_18008B23C )
    SetNewSSDemo(*(HWND *)Parameter, -1);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 1;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(
         (LPCWSTR)Parameter + 4,
         (LPWSTR)Parameter + 264,
         0,
         0,
         0,
         0,
         0,
         0,
         &StartupInfo,
         &ProcessInformation) )
  {
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  v10 = 0;
  ClassicSystemParametersInfoW(16, 0, &v10, 0);
  if ( v10 )
    ClassicSystemParametersInfoW(17, v10, 0, 0);
  PostMessageW(*(HWND *)Parameter, 0x401u, 0, 1);
  v5 = GetDlgItem(*(HWND *)Parameter, 1300);
  PostMessageW(*(HWND *)Parameter, 0x111u, 0x10514u, (LPARAM)v5);
  PostMessageW(*(HWND *)Parameter, 0x401u, 0, 0);
  v8 = 0;
  if ( !g_fSettingsButtonOffByPolicy )
  {
    v6 = *(unsigned __int16 *)(&g_aszMethods)[dword_18008B238];
    LOWORD(v6) = v6 - 67;
    if ( (unsigned __int16)v6 <= 0xDu )
    {
      v7 = 8257;
      if ( _bittest(&v7, v6) )
        v8 = 1;
    }
  }
  EnableWindow(DlgItem, v8);
  EnableWindow(v4, 1);
  LocalFree(Parameter);
  if ( LibraryW )
    FreeLibraryAndExitThread(LibraryW, 0);
  return 0;
}

```

## disassembly

```asm
0x1800475c0  push    rbp
0x1800475c2  push    rbx
0x1800475c3  push    rsi
0x1800475c4  push    rdi
0x1800475c5  push    r13
0x1800475c7  push    r14
0x1800475c9  lea     rbp, [rsp-208h]
0x1800475d1  sub     rsp, 308h
0x1800475d8  mov     rax, cs:__security_cookie
0x1800475df  xor     rax, rsp
0x1800475e2  mov     [rbp+230h+var_40], rax
0x1800475e9  mov     rbx, rcx
0x1800475ec  lea     rdx, [rbp+230h+Filename]; lpFilename
0x1800475f0  mov     rcx, cs:g_hinst; hModule
0x1800475f7  mov     r8d, 104h; nSize
0x1800475fd  call    cs:__imp_GetModuleFileNameW
0x180047603  lea     rcx, [rbp+230h+Filename]; lpLibFileName
0x180047607  call    cs:__imp_LoadLibraryW
0x18004760d  mov     rcx, [rbx]; hDlg
0x180047610  mov     edx, 517h; nIDDlgItem
0x180047615  mov     rdi, rax
0x180047618  call    cs:__imp_GetDlgItem
0x18004761e  mov     rcx, [rbx]; hDlg
0x180047621  mov     edx, 518h; nIDDlgItem
0x180047626  mov     rsi, rax
0x180047629  call    cs:__imp_GetDlgItem
0x18004762f  cmp     cs:dword_18008B23C, 0
0x180047636  mov     r14, rax
0x180047639  jz      short loc_180047646
0x18004763b  mov     rcx, [rbx]; hDlg
0x18004763e  or      edx, 0FFFFFFFFh; int
0x180047641  call    ?SetNewSSDemo@@YAXPEAUHWND__@@H@Z; SetNewSSDemo(HWND__ *,int)
0x180047646  xor     edx, edx; Val
0x180047648  lea     rcx, [rsp+330h+StartupInfo]; void *
0x18004764d  lea     r8d, [rdx+68h]; Size
0x180047651  call    memset_0
0x180047656  xor     eax, eax
0x180047658  mov     [rsp+330h+StartupInfo.cb], 68h ; 'h'
0x180047660  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x180047665  lea     rdx, [rbx+210h]; lpCommandLine
0x18004766c  lea     rax, [rsp+330h+ProcessInformation]
0x180047671  mov     r13d, 1
0x180047677  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x18004767c  lea     rcx, [rbx+8]; lpApplicationName
0x180047680  lea     rax, [rsp+330h+StartupInfo]
0x180047685  mov     [rbp+230h+StartupInfo.dwFlags], r13d
0x180047689  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18004768e  xorps   xmm0, xmm0
0x180047691  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18004769a  xor     r9d, r9d; lpThreadAttributes
0x18004769d  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x1800476a6  xor     r8d, r8d; lpProcessAttributes
0x1800476a9  mov     [rsp+330h+dwCreationFlags], 0; dwCreationFlags
0x1800476b1  mov     [rsp+330h+bInheritHandles], 0; bInheritHandles
0x1800476b9  mov     [rbp+230h+StartupInfo.wShowWindow], r13w
0x1800476be  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x1800476c3  call    cs:__imp_CreateProcessW
0x1800476c9  test    eax, eax
0x1800476cb  jz      short loc_1800476F1
0x1800476cd  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hHandle
0x1800476d2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800476d5  call    cs:__imp_WaitForSingleObject
0x1800476db  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x1800476e0  call    cs:__imp_CloseHandle
0x1800476e6  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x1800476eb  call    cs:__imp_CloseHandle
0x1800476f1  xor     edx, edx
0x1800476f3  mov     [rsp+330h+var_2E0], 0
0x1800476fb  xor     r9d, r9d
0x1800476fe  lea     r8, [rsp+330h+var_2E0]
0x180047703  lea     ecx, [rdx+10h]
0x180047706  call    cs:__imp_ClassicSystemParametersInfoW
0x18004770c  mov     edx, [rsp+330h+var_2E0]
0x180047710  test    edx, edx
0x180047712  jz      short loc_180047724
0x180047714  xor     r9d, r9d
0x180047717  xor     r8d, r8d
0x18004771a  lea     ecx, [r9+11h]
0x18004771e  call    cs:__imp_ClassicSystemParametersInfoW
0x180047724  mov     rcx, [rbx]; hWnd
0x180047727  mov     r9, r13; lParam
0x18004772a  xor     r8d, r8d; wParam
0x18004772d  mov     edx, 401h; Msg
0x180047732  call    cs:__imp_PostMessageW
0x180047738  mov     rcx, [rbx]; hDlg
0x18004773b  mov     edx, 514h; nIDDlgItem
0x180047740  call    cs:__imp_GetDlgItem
0x180047746  mov     rcx, [rbx]; hWnd
0x180047749  mov     edx, 111h; Msg
0x18004774e  mov     r9, rax; lParam
0x180047751  mov     r8d, 10514h; wParam
0x180047757  call    cs:__imp_PostMessageW
0x18004775d  mov     rcx, [rbx]; hWnd
0x180047760  xor     r9d, r9d; lParam
0x180047763  xor     r8d, r8d; wParam
0x180047766  mov     edx, 401h; Msg
0x18004776b  call    cs:__imp_PostMessageW
0x180047771  cmp     cs:?g_fSettingsButtonOffByPolicy@@3HA, 0; int g_fSettingsButtonOffByPolicy
0x180047778  jnz     short loc_1800477A8
0x18004777a  movsxd  rax, cs:dword_18008B238
0x180047781  lea     rcx, ?g_aszMethods@@3PAPEAGA; ushort * near * g_aszMethods
0x180047788  mov     rax, [rcx+rax*8]
0x18004778c  movzx   ecx, word ptr [rax]
0x18004778f  sub     cx, 43h ; 'C'
0x180047793  cmp     cx, 0Dh
0x180047797  ja      short loc_1800477A8
0x180047799  mov     eax, 2041h
0x18004779e  bt      eax, ecx
0x1800477a1  jnb     short loc_1800477A8
0x1800477a3  mov     edx, r13d
0x1800477a6  jmp     short loc_1800477AA
0x1800477a8  xor     edx, edx; bEnable
0x1800477aa  mov     rcx, rsi; hWnd
0x1800477ad  call    cs:__imp_EnableWindow
0x1800477b3  mov     edx, r13d; bEnable
0x1800477b6  mov     rcx, r14; hWnd
0x1800477b9  call    cs:__imp_EnableWindow
0x1800477bf  mov     rcx, rbx; hMem
0x1800477c2  call    cs:__imp_LocalFree
0x1800477c8  test    rdi, rdi
0x1800477cb  jz      short loc_1800477D9
0x1800477cd  xor     edx, edx; dwExitCode
0x1800477cf  mov     rcx, rdi; hLibModule
0x1800477d2  call    cs:__imp_FreeLibraryAndExitThread
0x1800477d8  int     3; Trap to Debugger
0x1800477d9  xor     eax, eax
0x1800477db  mov     rcx, [rbp+230h+var_40]
0x1800477e2  xor     rcx, rsp; StackCookie
0x1800477e5  call    __security_check_cookie
0x1800477ea  add     rsp, 308h
0x1800477f1  pop     r14
0x1800477f3  pop     r13
0x1800477f5  pop     rdi
0x1800477f6  pop     rsi
0x1800477f7  pop     rbx
0x1800477f8  pop     rbp
0x1800477f9  retn
```
