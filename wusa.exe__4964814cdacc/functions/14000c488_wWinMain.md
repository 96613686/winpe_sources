# wWinMain

- ea: `0x14000c488`
- end: `0x14000c9e3`
- name: `wWinMain`
- size: `1371`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400013e0`

## callees

- `0x140006554`
- `0x140006fb8`
- `0x140008ff8`
- `0x14000c488`
- `0x14000e280`
- `0x14000ec58`
- `0x14000f8f0`
- `0x1400108dc`
- `0x140011b08`
- `0x140011c10`
- `0x1400131a8`
- `0x14001331c`
- `0x140013490`
- `0x1400144e0`
- `0x1400145b4`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000c61a`
- `ADVAPI32!EventWrite` at `0x14000c69b`
- `ADVAPI32!EventWrite` at `0x14000c719`
- `ADVAPI32!EventWrite` at `0x14000c78f`
- `ADVAPI32!EventWrite` at `0x14000c61a`
- `ADVAPI32!EventWrite` at `0x14000c69b`
- `ADVAPI32!EventWrite` at `0x14000c719`
- `ADVAPI32!EventWrite` at `0x14000c78f`
- `KERNEL32!GetCommandLineW` at `0x14000c4ba`
- `KERNEL32!GetCommandLineW` at `0x14000c5b3`
- `KERNEL32!GetCommandLineW` at `0x14000c620`
- `KERNEL32!GetCommandLineW` at `0x14000c634`
- `KERNEL32!GetCommandLineW` at `0x14000c6a1`
- `KERNEL32!GetCommandLineW` at `0x14000c6de`
- `KERNEL32!GetCommandLineW` at `0x14000c71f`
- `KERNEL32!GetCommandLineW` at `0x14000c754`
- `KERNEL32!GetCommandLineW` at `0x14000c795`
- `KERNEL32!GetCommandLineW` at `0x14000c7e1`
- `KERNEL32!GetCommandLineW` at `0x14000c7ff`
- `KERNEL32!GetCommandLineW` at `0x14000c813`
- `KERNEL32!GetCommandLineW` at `0x14000c831`
- `KERNEL32!GetCommandLineW` at `0x14000c8a4`
- `KERNEL32!GetCommandLineW` at `0x14000c8c5`
- `KERNEL32!GetCommandLineW` at `0x14000c8d9`
- `KERNEL32!GetCommandLineW` at `0x14000c8fa`
- `KERNEL32!GetCommandLineW` at `0x14000c4ba`
- `KERNEL32!GetCommandLineW` at `0x14000c5b3`
- `KERNEL32!GetCommandLineW` at `0x14000c620`
- `KERNEL32!GetCommandLineW` at `0x14000c634`
- `KERNEL32!GetCommandLineW` at `0x14000c6a1`
- `KERNEL32!GetCommandLineW` at `0x14000c6de`
- `KERNEL32!GetCommandLineW` at `0x14000c71f`
- `KERNEL32!GetCommandLineW` at `0x14000c754`
- `KERNEL32!GetCommandLineW` at `0x14000c795`
- `KERNEL32!GetCommandLineW` at `0x14000c7e1`
- `KERNEL32!GetCommandLineW` at `0x14000c7ff`
- `KERNEL32!GetCommandLineW` at `0x14000c813`
- `KERNEL32!GetCommandLineW` at `0x14000c831`
- `KERNEL32!GetCommandLineW` at `0x14000c8a4`
- `KERNEL32!GetCommandLineW` at `0x14000c8c5`
- `KERNEL32!GetCommandLineW` at `0x14000c8d9`
- `KERNEL32!GetCommandLineW` at `0x14000c8fa`
- `KERNEL32!LocalFree` at `0x14000c890`
- `KERNEL32!LocalFree` at `0x14000c991`
- `KERNEL32!LocalFree` at `0x14000c890`
- `KERNEL32!LocalFree` at `0x14000c991`
- `ntdll!WinSqmSetDWORD` at `0x14000c57a`
- `ntdll!WinSqmSetDWORD` at `0x14000c58f`
- `ntdll!WinSqmSetDWORD` at `0x14000c57a`
- `ntdll!WinSqmSetDWORD` at `0x14000c58f`
- `ntdll!WinSqmSetString` at `0x14000c569`
- `ntdll!WinSqmSetString` at `0x14000c569`
- `ntdll!WinSqmStartSession` at `0x14000c540`
- `ntdll!WinSqmStartSession` at `0x14000c540`
- `ntdll!WinSqmEndSession` at `0x14000c598`
- `ntdll!WinSqmEndSession` at `0x14000c598`

## string_xrefs

- `0x14000c62b`: `Succeeded to uninstall update %ls. Command line: %ls`
- `0x14000c6ac`: `Succeeded to install update %ls. Command line: %ls`
- `0x14000c728`: `Failed to install package because servicing stack must be updated; Error: 0X%x, Command line: %ls`
- `0x14000c79e`: `Failed to install package because baseline update is required; Error: 0X%x, Command line: %ls`
- `0x14000c805`: `Failed to uninstall update %ls; Error: 0X%x, %ls. Command line: %ls`
- `0x14000c837`: `Failed to install update %ls; Error: 0X%x, %ls. Command line: %ls`
- `0x14000c8d0`: `Failed to uninstall update %ls; Error: 0X%x. Command line: %ls`
- `0x14000c905`: `Failed to install update %ls; Error: 0X%x. Command line: %ls`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // esi
  int v5; // r14d
  const unsigned __int16 *CommandLineW; // rax
  int v7; // eax
  DWORD started; // ebx
  __int64 v9; // rax
  __int64 v10; // rdi
  LPWSTR v11; // rax
  __int64 v12; // rcx
  LPWSTR v13; // r8
  __int64 v14; // rax
  LPWSTR v15; // rax
  LPWSTR v16; // rax
  __int64 v17; // rcx
  LPWSTR v18; // r8
  __int64 v19; // rax
  LPWSTR v20; // rax
  LPWSTR v21; // rax
  __int64 v22; // rcx
  const wchar_t *v23; // rax
  LPWSTR v24; // rax
  __int64 v25; // rcx
  const wchar_t *v26; // rax
  LPWSTR v27; // rax
  void *Ptr; // rdi
  LPWSTR v29; // rax
  const char *v30; // r8
  __int64 v31; // rdx
  LPWSTR v32; // rax
  LPWSTR v33; // rax
  LPWSTR v34; // rax
  __int64 v35; // rdx
  const char *v36; // r8
  LPWSTR v37; // rax
  void *v38; // rdi
  int v39; // ecx
  __int64 v41; // [rsp+28h] [rbp-50h]
  __int64 v42; // [rsp+28h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-38h] BYREF
  LPWSTR v44; // [rsp+50h] [rbp-28h]
  int v45; // [rsp+58h] [rbp-20h]
  int v46; // [rsp+5Ch] [rbp-1Ch]

  _Module = hInstance;
  v4 = 0;
  v5 = 0;
  CommandLineW = GetCommandLineW();
  v7 = AppModule::Init((AppModule *)&_Module, CommandLineW);
  started = v7;
  if ( v7 < 0 )
  {
    WusaLogDebugEventA(L"wWinMain", 2115, "Failed to initialize the application");
    goto LABEL_10;
  }
  if ( v7 != 1 )
  {
    if ( qword_1400201F8 )
    {
      started = StartLogs(qword_1400201F8);
      if ( (started & 0x80000000) != 0 )
      {
        WusaLogDebugEventA(L"wWinMain", 2126, "Failed to initialize tracing");
        goto LABEL_10;
      }
      v5 = 1;
    }
    started = DoInstall();
    v4 = RebootIfRequested();
  }
LABEL_10:
  v9 = WinSqmStartSession(qword_140020358, 14024704, 0);
  v10 = v9;
  if ( pszPath || qword_1400201F0 )
    WinSqmSetString(v9, 4286);
  WinSqmSetDWORD(v10, 4287, started);
  WinSqmSetDWORD(v10, 4285, (unsigned int)dword_140020198);
  WinSqmEndSession(v10);
  if ( started )
  {
    if ( started != 1 )
    {
      if ( started == -2145116137 )
      {
        v21 = GetCommandLineW();
        UserData.Ptr = (ULONGLONG)v21;
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        UserData.Reserved = 0;
        UserData.Size = 2 * v22 + 2;
        EventWrite(RegHandle, &WUSA_EVENT_STACKUPDATEREQUIRED, 1u, &UserData);
        v23 = GetCommandLineW();
        WusaLogDebugEventA(
          L"wWinMain",
          2180,
          "Failed to install package because servicing stack must be updated; Error: 0X%x, Command line: %ls",
          -2145116137,
          v23);
        ShowStackUpdateDialog();
      }
      else if ( started == -2145116122 )
      {
        v24 = GetCommandLineW();
        UserData.Ptr = (ULONGLONG)v24;
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        UserData.Reserved = 0;
        UserData.Size = 2 * v25 + 2;
        EventWrite(RegHandle, &WUSA_EVENT_REBASEUPDATEREQUIRED, 1u, &UserData);
        v26 = GetCommandLineW();
        WusaLogDebugEventA(
          L"wWinMain",
          2186,
          "Failed to install package because baseline update is required; Error: 0X%x, Command line: %ls",
          -2145116122,
          v26);
        ShowRebaseUpdateDialog();
      }
      else
      {
        UserData.Ptr = 0;
        if ( (int)WusaGetErrorMessage(started, (unsigned __int16 **)&UserData) < 0 )
        {
          if ( dword_14002017C )
          {
            v33 = GetCommandLineW();
            WusaEventUninstallFailure(off_1400201D8, started, &pwszReason, v33);
            v34 = GetCommandLineW();
            v35 = 2215;
            v36 = "Failed to uninstall update %ls; Error: 0X%x. Command line: %ls";
          }
          else
          {
            v37 = GetCommandLineW();
            WusaEventInstallFailure(off_1400201D8, started, &pwszReason, v37);
            v34 = GetCommandLineW();
            v35 = 2220;
            v36 = "Failed to install update %ls; Error: 0X%x. Command line: %ls";
          }
          WusaLogDebugEventA(L"wWinMain", v35, v36, off_1400201D8, started, v34);
          LODWORD(v42) = started;
          WusaMessageBox(0xEA62u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0, v42, &pwszReason);
        }
        else
        {
          if ( dword_14002017C )
          {
            v27 = GetCommandLineW();
            Ptr = (void *)UserData.Ptr;
            WusaEventUninstallFailure(off_1400201D8, started, UserData.Ptr, v27);
            v29 = GetCommandLineW();
            v30 = "Failed to uninstall update %ls; Error: 0X%x, %ls. Command line: %ls";
            v31 = 2200;
          }
          else
          {
            v32 = GetCommandLineW();
            Ptr = (void *)UserData.Ptr;
            WusaEventInstallFailure(off_1400201D8, started, UserData.Ptr, v32);
            v29 = GetCommandLineW();
            v30 = "Failed to install update %ls; Error: 0X%x, %ls. Command line: %ls";
            v31 = 2205;
          }
          WusaLogDebugEventA(L"wWinMain", v31, v30, off_1400201D8, started, Ptr, v29);
          LODWORD(v41) = started;
          WusaMessageBox(0xEA62u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0, v41, Ptr);
          if ( Ptr )
            LocalFree(Ptr);
        }
      }
      if ( dword_14002018C )
        GpModeCleanup();
      if ( (started & 0x80000000) != 0 )
      {
        UserData.Ptr = 0;
        WusaGetErrorMessage(started, (unsigned __int16 **)&UserData);
        v38 = (void *)UserData.Ptr;
        WusaLogDebugEventA(L"wWinMain", 2235, "Exit with error code 0X%x (%ls)", started, (const wchar_t *)UserData.Ptr);
        if ( v38 )
          LocalFree(v38);
      }
    }
  }
  else if ( dword_14002017C )
  {
    v11 = GetCommandLineW();
    v12 = -1;
    v13 = v11;
    UserData.Ptr = (ULONGLONG)off_1400201D8;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)off_1400201D8 + v14) );
    UserData.Reserved = 0;
    UserData.Size = 2 * v14 + 2;
    v44 = v13;
    do
      ++v12;
    while ( v13[v12] );
    v46 = 0;
    v45 = 2 * v12 + 2;
    EventWrite(RegHandle, &WUSA_EVENT_UNINSTALLSUCCESS, 2u, &UserData);
    v15 = GetCommandLineW();
    WusaLogDebugEventA(L"wWinMain", 2154, "Succeeded to uninstall update %ls. Command line: %ls", off_1400201D8, v15);
  }
  else
  {
    v16 = GetCommandLineW();
    v17 = -1;
    v18 = v16;
    UserData.Ptr = (ULONGLONG)off_1400201D8;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)off_1400201D8 + v19) );
    UserData.Reserved = 0;
    UserData.Size = 2 * v19 + 2;
    v44 = v18;
    do
      ++v17;
    while ( v18[v17] );
    v46 = 0;
    v45 = 2 * v17 + 2;
    EventWrite(RegHandle, &WUSA_EVENT_INSTALLSUCCESS, 2u, &UserData);
    v20 = GetCommandLineW();
    WusaLogDebugEventA(L"wWinMain", 2159, "Succeeded to install update %ls. Command line: %ls", off_1400201D8, v20);
  }
  if ( v5 )
    StopLogs();
  AppModule::Uninit((AppModule *)&_Module);
  v39 = (unsigned __int16)started;
  if ( (started & 0x1FFF0000) != 0x70000 )
    v39 = started;
  if ( !v4 )
    return v39;
  return v4;
}

```

## disassembly

```asm
0x14000c488  push    rbp
0x14000c48a  push    rbx
0x14000c48b  push    rsi
0x14000c48c  push    rdi
0x14000c48d  push    r12
0x14000c48f  push    r13
0x14000c491  push    r14
0x14000c493  push    r15
0x14000c495  mov     rbp, rsp
0x14000c498  sub     rsp, 78h
0x14000c49c  mov     rax, cs:__security_cookie
0x14000c4a3  xor     rax, rsp
0x14000c4a6  mov     [rbp+var_18], rax
0x14000c4aa  xor     r15d, r15d
0x14000c4ad  mov     cs:?_Module@@3VAppModule@@A, rcx; AppModule _Module
0x14000c4b4  mov     esi, r15d
0x14000c4b7  mov     r14d, r15d
0x14000c4ba  call    cs:__imp_GetCommandLineW
0x14000c4c0  mov     rdx, rax; unsigned __int16 *
0x14000c4c3  lea     rcx, ?_Module@@3VAppModule@@A; this
0x14000c4ca  call    ?Init@AppModule@@QEAAJPEBG@Z; AppModule::Init(ushort const *)
0x14000c4cf  lea     r12d, [r15+1]
0x14000c4d3  mov     ebx, eax
0x14000c4d5  lea     r13, aWwinmain; "wWinMain"
0x14000c4dc  test    eax, eax
0x14000c4de  jns     short loc_14000C4F6
0x14000c4e0  lea     r8, aFailedToInitia_5; "Failed to initialize the application"
0x14000c4e7  mov     edx, 843h
0x14000c4ec  mov     rcx, r13
0x14000c4ef  call    WusaLogDebugEventA
0x14000c4f4  jmp     short loc_14000C531
0x14000c4f6  cmp     eax, r12d
0x14000c4f9  jz      short loc_14000C531
0x14000c4fb  mov     rcx, cs:qword_1400201F8; unsigned __int16 *
0x14000c502  test    rcx, rcx
0x14000c505  jz      short loc_14000C523
0x14000c507  call    ?StartLogs@@YAJPEBG@Z; StartLogs(ushort const *)
0x14000c50c  mov     ebx, eax
0x14000c50e  test    eax, eax
0x14000c510  jns     short loc_14000C520
0x14000c512  lea     r8, aFailedToInitia_1; "Failed to initialize tracing"
0x14000c519  mov     edx, 84Eh
0x14000c51e  jmp     short loc_14000C4EC
0x14000c520  mov     r14d, r12d
0x14000c523  call    ?DoInstall@@YAJXZ; DoInstall(void)
0x14000c528  mov     ebx, eax
0x14000c52a  call    ?RebootIfRequested@@YAKXZ; RebootIfRequested(void)
0x14000c52f  mov     esi, eax
0x14000c531  xor     r8d, r8d
0x14000c534  lea     rcx, qword_140020358
0x14000c53b  mov     edx, 0D60000h
0x14000c540  call    cs:__imp_WinSqmStartSession
0x14000c546  mov     r8, cs:pszPath
0x14000c54d  mov     rdi, rax
0x14000c550  test    r8, r8
0x14000c553  jnz     short loc_14000C561
0x14000c555  mov     r8, cs:qword_1400201F0
0x14000c55c  test    r8, r8
0x14000c55f  jz      short loc_14000C56F
0x14000c561  mov     edx, 10BEh
0x14000c566  mov     rcx, rdi
0x14000c569  call    cs:__imp_WinSqmSetString
0x14000c56f  mov     r8d, ebx
0x14000c572  mov     edx, 10BFh
0x14000c577  mov     rcx, rdi
0x14000c57a  call    cs:__imp_WinSqmSetDWORD
0x14000c580  mov     r8d, cs:dword_140020198
0x14000c587  mov     edx, 10BDh
0x14000c58c  mov     rcx, rdi
0x14000c58f  call    cs:__imp_WinSqmSetDWORD
0x14000c595  mov     rcx, rdi
0x14000c598  call    cs:__imp_WinSqmEndSession
0x14000c59e  test    ebx, ebx
0x14000c5a0  jnz     loc_14000C6CC
0x14000c5a6  cmp     cs:dword_14002017C, r15d
0x14000c5ad  jz      loc_14000C634
0x14000c5b3  call    cs:__imp_GetCommandLineW
0x14000c5b9  mov     rdx, cs:off_1400201D8
0x14000c5c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000c5c4  mov     r8, rax
0x14000c5c7  mov     [rbp+UserData.Ptr], rdx
0x14000c5cb  mov     rax, rcx
0x14000c5ce  inc     rax
0x14000c5d1  cmp     [rdx+rax*2], r15w
0x14000c5d6  jnz     short loc_14000C5CE
0x14000c5d8  lea     eax, ds:2[rax*2]
0x14000c5df  mov     dword ptr [rbp+UserData.0Ch], r15d
0x14000c5e3  mov     [rbp+UserData.Size], eax
0x14000c5e6  mov     [rbp+var_28], r8
0x14000c5ea  inc     rcx
0x14000c5ed  cmp     [r8+rcx*2], r15w
0x14000c5f2  jnz     short loc_14000C5EA
0x14000c5f4  lea     eax, ds:2[rcx*2]
0x14000c5fb  mov     [rbp+var_1C], r15d
0x14000c5ff  mov     rcx, cs:RegHandle; RegHandle
0x14000c606  lea     r9, [rbp+UserData]; UserData
0x14000c60a  mov     r8d, 2; UserDataCount
0x14000c610  mov     [rbp+var_20], eax
0x14000c613  lea     rdx, WUSA_EVENT_UNINSTALLSUCCESS; EventDescriptor
0x14000c61a  call    cs:__imp_EventWrite
0x14000c620  call    cs:__imp_GetCommandLineW
0x14000c626  mov     edx, 86Ah
0x14000c62b  lea     r8, aSucceededToUni_0; "Succeeded to uninstall update %ls. Comm"...
0x14000c632  jmp     short loc_14000C6B3
0x14000c634  call    cs:__imp_GetCommandLineW
0x14000c63a  mov     rdx, cs:off_1400201D8
0x14000c641  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000c645  mov     r8, rax
0x14000c648  mov     [rbp+UserData.Ptr], rdx
0x14000c64c  mov     rax, rcx
0x14000c64f  inc     rax
0x14000c652  cmp     [rdx+rax*2], r15w
0x14000c657  jnz     short loc_14000C64F
0x14000c659  lea     eax, ds:2[rax*2]
0x14000c660  mov     dword ptr [rbp+UserData.0Ch], r15d
0x14000c664  mov     [rbp+UserData.Size], eax
0x14000c667  mov     [rbp+var_28], r8
0x14000c66b  inc     rcx
0x14000c66e  cmp     [r8+rcx*2], r15w
0x14000c673  jnz     short loc_14000C66B
0x14000c675  lea     eax, ds:2[rcx*2]
0x14000c67c  mov     [rbp+var_1C], r15d
0x14000c680  mov     rcx, cs:RegHandle; RegHandle
0x14000c687  lea     r9, [rbp+UserData]; UserData
0x14000c68b  mov     r8d, 2; UserDataCount
0x14000c691  mov     [rbp+var_20], eax
0x14000c694  lea     rdx, WUSA_EVENT_INSTALLSUCCESS; EventDescriptor
0x14000c69b  call    cs:__imp_EventWrite
0x14000c6a1  call    cs:__imp_GetCommandLineW
0x14000c6a7  mov     edx, 86Fh
0x14000c6ac  lea     r8, aSucceededToIns; "Succeeded to install update %ls. Comman"...
0x14000c6b3  mov     r9, cs:off_1400201D8
0x14000c6ba  mov     rcx, r13
0x14000c6bd  mov     [rsp+78h+var_58], rax
0x14000c6c2  call    WusaLogDebugEventA
0x14000c6c7  jmp     loc_14000C997
0x14000c6cc  cmp     ebx, r12d
0x14000c6cf  jz      loc_14000C997
0x14000c6d5  mov     edi, 80242017h
0x14000c6da  cmp     ebx, edi
0x14000c6dc  jnz     short loc_14000C74B
0x14000c6de  call    cs:__imp_GetCommandLineW
0x14000c6e4  mov     [rbp+UserData.Ptr], rax
0x14000c6e8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000c6ec  inc     rcx
0x14000c6ef  cmp     [rax+rcx*2], r15w
0x14000c6f4  jnz     short loc_14000C6EC
0x14000c6f6  lea     eax, ds:2[rcx*2]
0x14000c6fd  mov     dword ptr [rbp+UserData.0Ch], r15d
0x14000c701  mov     rcx, cs:RegHandle; RegHandle
0x14000c708  lea     r9, [rbp+UserData]; UserData
0x14000c70c  mov     r8d, r12d; UserDataCount
0x14000c70f  mov     [rbp+UserData.Size], eax
0x14000c712  lea     rdx, WUSA_EVENT_STACKUPDATEREQUIRED; EventDescriptor
0x14000c719  call    cs:__imp_EventWrite
0x14000c71f  call    cs:__imp_GetCommandLineW
0x14000c725  mov     r9d, edi
0x14000c728  lea     r8, aFailedToInstal_0; "Failed to install package because servi"...
0x14000c72f  mov     edx, 884h
0x14000c734  mov     [rsp+78h+var_58], rax
0x14000c739  mov     rcx, r13
0x14000c73c  call    WusaLogDebugEventA
0x14000c741  call    ?ShowStackUpdateDialog@@YAJXZ; ShowStackUpdateDialog(void)
0x14000c746  jmp     loc_14000C948
0x14000c74b  mov     edi, 80242026h
0x14000c750  cmp     ebx, edi
0x14000c752  jnz     short loc_14000C7C1
0x14000c754  call    cs:__imp_GetCommandLineW
0x14000c75a  mov     [rbp+UserData.Ptr], rax
0x14000c75e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000c762  inc     rcx
0x14000c765  cmp     [rax+rcx*2], r15w
0x14000c76a  jnz     short loc_14000C762
0x14000c76c  lea     eax, ds:2[rcx*2]
0x14000c773  mov     dword ptr [rbp+UserData.0Ch], r15d
0x14000c777  mov     rcx, cs:RegHandle; RegHandle
0x14000c77e  lea     r9, [rbp+UserData]; UserData
0x14000c782  mov     r8d, r12d; UserDataCount
0x14000c785  mov     [rbp+UserData.Size], eax
0x14000c788  lea     rdx, WUSA_EVENT_REBASEUPDATEREQUIRED; EventDescriptor
0x14000c78f  call    cs:__imp_EventWrite
0x14000c795  call    cs:__imp_GetCommandLineW
0x14000c79b  mov     r9d, edi
0x14000c79e  lea     r8, aFailedToInstal_3; "Failed to install package because basel"...
0x14000c7a5  mov     edx, 88Ah
0x14000c7aa  mov     [rsp+78h+var_58], rax
0x14000c7af  mov     rcx, r13
0x14000c7b2  call    WusaLogDebugEventA
0x14000c7b7  call    ?ShowRebaseUpdateDialog@@YAJXZ; ShowRebaseUpdateDialog(void)
0x14000c7bc  jmp     loc_14000C948
0x14000c7c1  lea     rdx, [rbp+UserData]; unsigned __int16 **
0x14000c7c5  mov     [rbp+UserData.Ptr], r15
0x14000c7c9  mov     ecx, ebx; dwMessageId
0x14000c7cb  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000c7d0  test    eax, eax
0x14000c7d2  js      loc_14000C89B
0x14000c7d8  cmp     cs:dword_14002017C, r15d
0x14000c7df  jz      short loc_14000C813
0x14000c7e1  call    cs:__imp_GetCommandLineW
0x14000c7e7  mov     rdi, [rbp+UserData.Ptr]
0x14000c7eb  mov     edx, ebx
0x14000c7ed  mov     rcx, cs:off_1400201D8
0x14000c7f4  mov     r9, rax
0x14000c7f7  mov     r8, rdi
0x14000c7fa  call    WusaEventUninstallFailure
0x14000c7ff  call    cs:__imp_GetCommandLineW
0x14000c805  lea     r8, aFailedToUninst_2; "Failed to uninstall update %ls; Error: "...
0x14000c80c  mov     edx, 898h
0x14000c811  jmp     short loc_14000C843
0x14000c813  call    cs:__imp_GetCommandLineW
0x14000c819  mov     rdi, [rbp+UserData.Ptr]
0x14000c81d  mov     edx, ebx
0x14000c81f  mov     rcx, cs:off_1400201D8
0x14000c826  mov     r9, rax
0x14000c829  mov     r8, rdi
0x14000c82c  call    WusaEventInstallFailure
0x14000c831  call    cs:__imp_GetCommandLineW
0x14000c837  lea     r8, aFailedToInstal_1; "Failed to install update %ls; Error: 0X"...
0x14000c83e  mov     edx, 89Dh
0x14000c843  mov     r9, cs:off_1400201D8
0x14000c84a  mov     rcx, r13
0x14000c84d  mov     [rsp+78h+var_48], rax
0x14000c852  mov     [rsp+78h+var_50], rdi
0x14000c857  mov     dword ptr [rsp+78h+var_58], ebx
0x14000c85b  call    WusaLogDebugEventA
0x14000c860  mov     edx, 0EA60h; DWORD
0x14000c865  mov     [rsp+78h+var_48], rdi
0x14000c86a  mov     dword ptr [rsp+78h+var_50], ebx
0x14000c86e  mov     r9d, 0FFFEh; pszIcon
0x14000c874  mov     r8d, r12d; dwCommonButtons
0x14000c877  mov     [rsp+78h+var_58], r15; int *
0x14000c87c  lea     ecx, [rdx+2]; dwMessageId
0x14000c87f  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000c884  test    rdi, rdi
0x14000c887  jz      loc_14000C948
0x14000c88d  mov     rcx, rdi; hMem
0x14000c890  call    cs:__imp_LocalFree
0x14000c896  jmp     loc_14000C948
0x14000c89b  cmp     cs:dword_14002017C, r15d
0x14000c8a2  jz      short loc_14000C8D9
0x14000c8a4  call    cs:__imp_GetCommandLineW
0x14000c8aa  mov     rcx, cs:off_1400201D8
0x14000c8b1  lea     rdi, pwszReason
0x14000c8b8  mov     r9, rax
0x14000c8bb  mov     r8, rdi
0x14000c8be  mov     edx, ebx
0x14000c8c0  call    WusaEventUninstallFailure
0x14000c8c5  call    cs:__imp_GetCommandLineW
0x14000c8cb  mov     edx, 8A7h
0x14000c8d0  lea     r8, aFailedToUninst_0; "Failed to uninstall update %ls; Error: "...
0x14000c8d7  jmp     short loc_14000C90C
0x14000c8d9  call    cs:__imp_GetCommandLineW
0x14000c8df  mov     rcx, cs:off_1400201D8
0x14000c8e6  lea     rdi, pwszReason
0x14000c8ed  mov     r9, rax
0x14000c8f0  mov     r8, rdi
0x14000c8f3  mov     edx, ebx
0x14000c8f5  call    WusaEventInstallFailure
0x14000c8fa  call    cs:__imp_GetCommandLineW
0x14000c900  mov     edx, 8ACh
0x14000c905  lea     r8, aFailedToInstal_2; "Failed to install update %ls; Error: 0X"...
0x14000c90c  mov     r9, cs:off_1400201D8
0x14000c913  mov     rcx, r13
0x14000c916  mov     [rsp+78h+var_50], rax
0x14000c91b  mov     dword ptr [rsp+78h+var_58], ebx
0x14000c91f  call    WusaLogDebugEventA
0x14000c924  mov     edx, 0EA60h; DWORD
0x14000c929  mov     [rsp+78h+var_48], rdi
0x14000c92e  mov     dword ptr [rsp+78h+var_50], ebx
0x14000c932  mov     r9d, 0FFFEh; pszIcon
0x14000c938  mov     r8d, r12d; dwCommonButtons
0x14000c93b  mov     [rsp+78h+var_58], r15; int *
0x14000c940  lea     ecx, [rdx+2]; dwMessageId
0x14000c943  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000c948  cmp     cs:dword_14002018C, r15d
0x14000c94f  jz      short loc_14000C956
0x14000c951  call    ?GpModeCleanup@@YAJXZ; GpModeCleanup(void)
0x14000c956  test    ebx, ebx
0x14000c958  jns     short loc_14000C997
0x14000c95a  lea     rdx, [rbp+UserData]; unsigned __int16 **
0x14000c95e  mov     [rbp+UserData.Ptr], r15
0x14000c962  mov     ecx, ebx; dwMessageId
0x14000c964  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000c969  mov     rdi, [rbp+UserData.Ptr]
0x14000c96d  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000c974  mov     r9d, ebx
0x14000c977  mov     [rsp+78h+var_58], rdi
0x14000c97c  mov     edx, 8BBh
0x14000c981  mov     rcx, r13
0x14000c984  call    WusaLogDebugEventA
0x14000c989  test    rdi, rdi
0x14000c98c  jz      short loc_14000C997
0x14000c98e  mov     rcx, rdi; hMem
0x14000c991  call    cs:__imp_LocalFree
0x14000c997  test    r14d, r14d
0x14000c99a  jz      short loc_14000C9A1
0x14000c99c  call    ?StopLogs@@YAXXZ; StopLogs(void)
0x14000c9a1  lea     rcx, ?_Module@@3VAppModule@@A; this
0x14000c9a8  call    ?Uninit@AppModule@@QEAAXXZ; AppModule::Uninit(void)
0x14000c9ad  mov     eax, ebx
  ... truncated ...
```
