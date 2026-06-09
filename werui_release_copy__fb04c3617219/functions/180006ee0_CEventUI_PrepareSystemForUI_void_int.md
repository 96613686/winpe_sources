# CEventUI::PrepareSystemForUI(void *,int *)

- ea: `0x180006ee0`
- end: `0x18000738a`
- name: `?PrepareSystemForUI@CEventUI@@AEAAJPEAXPEAH@Z`
- size: `1194`
- prototype: `int(CEventUI *__hidden this, void *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006550`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x18000438c`
- `0x180004488`
- `0x180005c58`
- `0x180005ddc`
- `0x180006ee0`
- `0x1800098b8`
- `0x18000c8a0`
- `0x180016c50`

## import_xrefs

- `wer!WerpSetReportFlags` at `0x1800072d9`
- `wer!WerpSetReportFlags` at `0x1800072f7`
- `wer!WerpSetReportFlags` at `0x1800072d9`
- `wer!WerpSetReportFlags` at `0x1800072f7`
- `wer!WerpGetReportFlags` at `0x180006f99`
- `wer!WerpGetReportFlags` at `0x180006f99`
- `KERNEL32!GetCurrentProcess` at `0x1800071e2`
- `KERNEL32!GetCurrentProcess` at `0x1800071eb`
- `KERNEL32!GetCurrentProcess` at `0x1800071e2`
- `KERNEL32!GetCurrentProcess` at `0x1800071eb`
- `KERNEL32!GetLastError` at `0x18000703a`
- `KERNEL32!GetLastError` at `0x18000703a`
- `KERNEL32!GetProcessId` at `0x18000700d`
- `KERNEL32!GetProcessId` at `0x1800070b4`
- `KERNEL32!GetProcessId` at `0x18000700d`
- `KERNEL32!GetProcessId` at `0x1800070b4`
- `KERNEL32!AttachConsole` at `0x1800070bc`
- `KERNEL32!AttachConsole` at `0x1800070bc`
- `KERNEL32!GetConsoleWindow` at `0x1800070c6`
- `KERNEL32!GetConsoleWindow` at `0x1800070c6`
- `KERNEL32!FreeConsole` at `0x1800070d7`
- `KERNEL32!FreeConsole` at `0x1800070d7`
- `KERNEL32!DuplicateHandle` at `0x180007219`
- `KERNEL32!DuplicateHandle` at `0x180007219`
- `USER32!ChangeWindowMessageFilter` at `0x180007001`
- `USER32!ChangeWindowMessageFilter` at `0x180007001`
- `USER32!GetMonitorInfoW` at `0x18000714d`
- `USER32!GetMonitorInfoW` at `0x18000714d`
- `USER32!MonitorFromRect` at `0x180007139`
- `USER32!MonitorFromRect` at `0x180007139`
- `ntdll!NtSuspendProcess` at `0x180007233`
- `ntdll!NtSuspendProcess` at `0x180007233`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180006fed`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180006fed`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800070cf`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000711a`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800071aa`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800072b6`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800070cf`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000711a`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800071aa`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800072b6`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x180007030`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x180007030`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventUI::PrepareSystemForUI(CEventUI *this, void *a2, int *a3)
{
  int v6; // r12d
  int v7; // ebx
  int ReportFlags; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  UINT v12; // eax
  DWORD LastError; // eax
  LPARAM v14; // rcx
  _DWORD *v15; // rbx
  DWORD ProcessId; // eax
  HWND ConsoleWindow; // rax
  BOOL v18; // ebx
  int v19; // r13d
  int v20; // eax
  HMONITOR v21; // rax
  HANDLE *v22; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v24; // rax
  void *v25; // r8
  HANDLE v26; // rbx
  HANDLE v27; // rax
  int v29; // [rsp+40h] [rbp-59h] BYREF
  HANDLE ProcessHandle; // [rsp+48h] [rbp-51h] BYREF
  HANDLE hSourceHandle; // [rsp+50h] [rbp-49h]
  int *v32; // [rsp+58h] [rbp-41h]
  LPARAM lParam[2]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v34[24]; // [rsp+70h] [rbp-29h] BYREF
  struct tagMONITORINFO mi; // [rsp+88h] [rbp-11h] BYREF

  v32 = a3;
  hSourceHandle = a2;
  *(_OWORD *)lParam = 0;
  memset(v34, 0, sizeof(v34));
  memset(&mi, 0, sizeof(mi));
  v6 = 0;
  ProcessHandle = 0;
  v29 = 0;
  if ( !a2 )
  {
    v7 = 0;
    goto LABEL_76;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
    v7 = -2147024809;
    goto LABEL_76;
  }
  ReportFlags = WerpGetReportFlags(*((_QWORD *)this + 6), &v29);
  v7 = ReportFlags;
  if ( ReportFlags < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_76;
    v10 = 14;
LABEL_12:
    v11 = (unsigned int)ReportFlags;
    goto LABEL_75;
  }
  if ( (unsigned int)(*((_DWORD *)this + 2) - 2) <= 1 )
  {
    v12 = RegisterWindowMessageW(L"WerHangRepMessage");
    g_uHangrepMsg = v12;
    if ( v12 )
      ChangeWindowMessageFilter(v12, 1u);
  }
  *a3 = 0;
  LODWORD(lParam[0]) = GetProcessId(a2);
  if ( !LODWORD(lParam[0]) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_da26f2d1156739261f61a97d8df66789_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147024809;
    goto LABEL_72;
  }
  if ( EnumWindows(EnumWindowProcForProperties, (LPARAM)lParam) )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(LastError);
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( v7 < 0 )
  {
LABEL_72:
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_76;
    v10 = 15;
    v11 = (unsigned int)v7;
LABEL_75:
    WPP_SF_d(v9[2], v10, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, v11);
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, lParam[1]);
  v14 = lParam[1];
  *((_QWORD *)this + 15) = lParam[1];
  *((_OWORD *)this + 8) = *(_OWORD *)&v34[4];
  v15 = (_DWORD *)((char *)this + 8);
  if ( !v14 && *v15 == 2 )
  {
    ProcessId = GetProcessId(a2);
    if ( AttachConsole(ProcessId) )
    {
      ConsoleWindow = GetConsoleWindow();
      v18 = IsWindow(ConsoleWindow);
      FreeConsole();
      if ( v18 )
        v6 = 1;
      v15 = (_DWORD *)((char *)this + 8);
    }
  }
  v19 = v29 & 0x1000000;
  *((_DWORD *)this + 240) = v6 | v29 & 0x1000000;
  if ( v19 )
    goto LABEL_34;
  if ( v6 )
    goto LABEL_49;
  if ( *v15 != 2 )
  {
    if ( *v15 == 3 )
      goto LABEL_34;
LABEL_49:
    v20 = 1;
    goto LABEL_35;
  }
  if ( !IsWindow(*((HWND *)this + 15)) )
    goto LABEL_49;
LABEL_34:
  v20 = 0;
LABEL_35:
  *((_DWORD *)this + 241) = v20;
  v21 = MonitorFromRect((LPCRECT)this + 8, 2u);
  mi.cbSize = 40;
  GetMonitorInfoW(v21, &mi);
  if ( mi.rcMonitor.bottom == *((_DWORD *)this + 35)
    && mi.rcMonitor.top == *((_DWORD *)this + 33)
    && mi.rcMonitor.left == *((_DWORD *)this + 32)
    && mi.rcMonitor.right == *((_DWORD *)this + 34) )
  {
    *((_DWORD *)this + 240) = 1;
  }
  if ( !(unsigned int)IsDirectXRunningFullScreen() )
    goto LABEL_59;
  if ( *(_QWORD *)&v34[4] || !IsWindow((HWND)lParam[1]) )
  {
    *v32 = 1;
    goto LABEL_59;
  }
  *((_DWORD *)this + 240) = 1;
  if ( (unsigned int)CUIDlgBase::UICallback(v15, 6) )
  {
    v26 = hSourceHandle;
  }
  else
  {
    v22 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&ProcessHandle);
    CurrentProcess = GetCurrentProcess();
    v24 = GetCurrentProcess();
    v25 = CurrentProcess;
    v26 = hSourceHandle;
    if ( DuplicateHandle(v24, hSourceHandle, v25, v22, 0xA00u, 0, 0) )
    {
      v27 = ProcessHandle;
      if ( (unsigned __int64)ProcessHandle + 1 <= 1 )
        goto LABEL_52;
      if ( NtSuspendProcess(ProcessHandle) >= 0 )
        *((_DWORD *)this + 236) = 1;
    }
  }
  v27 = ProcessHandle;
LABEL_52:
  if ( (unsigned __int64)v27 + 1 > 1 )
    v26 = v27;
  ReportFlags = RestoreFromDirectXRunningFullScreen(v26);
  v7 = ReportFlags;
  if ( ReportFlags < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_76;
    v10 = 17;
    goto LABEL_12;
  }
LABEL_59:
  if ( !v19 && *((_DWORD *)this + 2) == 2 && !v6 && !IsWindow(*((HWND *)this + 15)) && *((_DWORD *)this + 44) )
  {
    v29 |= 0x400040u;
    WerpSetReportFlags(*((_QWORD *)this + 6));
  }
  if ( *((_DWORD *)this + 240) )
  {
    v29 &= ~0x400000u;
    WerpSetReportFlags(*((_QWORD *)this + 6));
  }
  v7 = 0;
LABEL_76:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&ProcessHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006ee0  mov     [rsp-8+arg_18], rbx
0x180006ee5  push    rbp
0x180006ee6  push    rsi
0x180006ee7  push    rdi
0x180006ee8  push    r12
0x180006eea  push    r13
0x180006eec  push    r14
0x180006eee  push    r15
0x180006ef0  lea     rbp, [rsp-27h]
0x180006ef5  sub     rsp, 0C0h
0x180006efc  mov     rax, cs:__security_cookie
0x180006f03  xor     rax, rsp
0x180006f06  mov     [rbp+57h+var_40], rax
0x180006f0a  mov     rdi, r8
0x180006f0d  mov     [rbp+57h+var_98], r8
0x180006f11  mov     r13, rdx
0x180006f14  mov     [rbp+57h+hSourceHandle], rdx
0x180006f18  mov     r14, rcx
0x180006f1b  xorps   xmm0, xmm0
0x180006f1e  xor     eax, eax
0x180006f20  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x180006f24  movups  [rbp+57h+var_80], xmm0
0x180006f28  mov     [rbp+57h+var_70], rax
0x180006f2c  xorps   xmm1, xmm1
0x180006f2f  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm1
0x180006f33  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm1
0x180006f37  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x180006f3b  xor     r12d, r12d
0x180006f3e  mov     [rbp+57h+ProcessHandle], r12
0x180006f42  mov     [rbp+57h+var_B0], r12d
0x180006f46  test    rdx, rdx
0x180006f49  jnz     short loc_180006F53
0x180006f4b  mov     ebx, r12d
0x180006f4e  jmp     loc_180007358
0x180006f53  test    rdi, rdi
0x180006f56  jnz     short loc_180006F91
0x180006f58  lea     r15, WPP_GLOBAL_Control
0x180006f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f66  cmp     rcx, r15
0x180006f69  jz      short loc_180006F87
0x180006f6b  lea     esi, [rdi+1]
0x180006f6e  test    [rcx+1Ch], sil
0x180006f72  jz      short loc_180006F87
0x180006f74  lea     edx, [rdi+0Dh]
0x180006f77  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006f7e  mov     rcx, [rcx+10h]
0x180006f82  call    WPP_SF_
0x180006f87  mov     ebx, 80070057h
0x180006f8c  jmp     loc_180007358
0x180006f91  lea     rdx, [rbp+57h+var_B0]
0x180006f95  mov     rcx, [rcx+30h]
0x180006f99  call    cs:__imp_WerpGetReportFlags
0x180006f9f  mov     ebx, eax
0x180006fa1  test    eax, eax
0x180006fa3  jns     short loc_180006FD6
0x180006fa5  lea     r15, WPP_GLOBAL_Control
0x180006fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fb3  cmp     rcx, r15
0x180006fb6  jz      loc_180007358
0x180006fbc  mov     esi, 1
0x180006fc1  test    [rcx+1Ch], sil
0x180006fc5  jz      loc_180007358
0x180006fcb  lea     edx, [rsi+0Dh]
0x180006fce  mov     r9d, eax
0x180006fd1  jmp     loc_180007347
0x180006fd6  mov     eax, [r14+8]
0x180006fda  sub     eax, 2
0x180006fdd  mov     esi, 1
0x180006fe2  cmp     eax, esi
0x180006fe4  ja      short loc_180007007
0x180006fe6  lea     rcx, String; "WerHangRepMessage"
0x180006fed  call    cs:__imp_RegisterWindowMessageW
0x180006ff3  mov     cs:?g_uHangrepMsg@@3IA, eax; uint g_uHangrepMsg
0x180006ff9  test    eax, eax
0x180006ffb  jz      short loc_180007007
0x180006ffd  mov     edx, esi; dwFlag
0x180006fff  mov     ecx, eax; message
0x180007001  call    cs:__imp_ChangeWindowMessageFilter
0x180007007  mov     [rdi], r12d
0x18000700a  mov     rcx, r13; Process
0x18000700d  call    cs:__imp_GetProcessId
0x180007013  mov     dword ptr [rbp+57h+lParam], eax
0x180007016  lea     r15, WPP_GLOBAL_Control
0x18000701d  test    eax, eax
0x18000701f  jz      loc_180007301
0x180007025  lea     rdx, [rbp+57h+lParam]; lParam
0x180007029  lea     rcx, ?EnumWindowProcForProperties@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180007030  call    cs:__imp_EnumWindows
0x180007036  test    eax, eax
0x180007038  jnz     short loc_18000704B
0x18000703a  call    cs:__imp_GetLastError
0x180007040  mov     ecx, eax; unsigned int
0x180007042  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180007047  mov     ebx, eax
0x180007049  jmp     short loc_18000704E
0x18000704b  mov     ebx, r12d
0x18000704e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007055  test    ebx, ebx
0x180007057  js      loc_180007334
0x18000705d  cmp     rcx, r15
0x180007060  jz      short loc_180007081
0x180007062  test    byte ptr [rcx+1Ch], 4
0x180007066  jz      short loc_180007081
0x180007068  mov     edx, 10h
0x18000706d  mov     r9, [rbp+57h+lParam+8]
0x180007071  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180007078  mov     rcx, [rcx+10h]
0x18000707c  call    WPP_SF_q
0x180007081  mov     rcx, [rbp+57h+lParam+8]
0x180007085  mov     [r14+78h], rcx
0x180007089  lea     rdi, [r14+80h]
0x180007090  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180007093  mov     [rdi], eax
0x180007095  mov     eax, dword ptr [rbp+57h+var_80+8]
0x180007098  mov     [rdi+4], eax
0x18000709b  mov     rax, qword ptr [rbp+57h+var_80+0Ch]
0x18000709f  mov     [rdi+8], rax
0x1800070a3  lea     rbx, [r14+8]
0x1800070a7  test    rcx, rcx
0x1800070aa  jnz     short loc_1800070E7
0x1800070ac  cmp     dword ptr [rbx], 2
0x1800070af  jnz     short loc_1800070E7
0x1800070b1  mov     rcx, r13; Process
0x1800070b4  call    cs:__imp_GetProcessId
0x1800070ba  mov     ecx, eax; dwProcessId
0x1800070bc  call    cs:__imp_AttachConsole
0x1800070c2  test    eax, eax
0x1800070c4  jz      short loc_1800070E7
0x1800070c6  call    cs:__imp_GetConsoleWindow
0x1800070cc  mov     rcx, rax; hWnd
0x1800070cf  call    cs:__imp_IsWindow
0x1800070d5  mov     ebx, eax
0x1800070d7  call    cs:__imp_FreeConsole
0x1800070dd  test    ebx, ebx
0x1800070df  cmovnz  r12d, esi
0x1800070e3  lea     rbx, [r14+8]
0x1800070e7  mov     r13d, [rbp+57h+var_B0]
0x1800070eb  and     r13d, 1000000h
0x1800070f2  mov     eax, r13d
0x1800070f5  or      eax, r12d
0x1800070f8  mov     [r14+3C0h], eax
0x1800070ff  test    r13d, r13d
0x180007102  jnz     short loc_180007128
0x180007104  test    r12d, r12d
0x180007107  jnz     loc_18000724F
0x18000710d  cmp     dword ptr [rbx], 2
0x180007110  jnz     loc_180007246
0x180007116  mov     rcx, [r14+78h]; hWnd
0x18000711a  call    cs:__imp_IsWindow
0x180007120  test    eax, eax
0x180007122  jz      loc_18000724F
0x180007128  xor     eax, eax
0x18000712a  mov     [r14+3C4h], eax
0x180007131  mov     edx, 2; dwFlags
0x180007136  mov     rcx, rdi; lprc
0x180007139  call    cs:__imp_MonitorFromRect
0x18000713f  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180007146  lea     rdx, [rbp+57h+mi]; lpmi
0x18000714a  mov     rcx, rax; hMonitor
0x18000714d  call    cs:__imp_GetMonitorInfoW
0x180007153  mov     eax, [r14+8Ch]
0x18000715a  cmp     [rbp+57h+mi.rcMonitor.bottom], eax
0x18000715d  jnz     short loc_180007185
0x18000715f  mov     eax, [r14+84h]
0x180007166  cmp     [rbp+57h+mi.rcMonitor.top], eax
0x180007169  jnz     short loc_180007185
0x18000716b  mov     eax, [rdi]
0x18000716d  cmp     [rbp+57h+mi.rcMonitor.left], eax
0x180007170  jnz     short loc_180007185
0x180007172  mov     eax, [r14+88h]
0x180007179  cmp     [rbp+57h+mi.rcMonitor.right], eax
0x18000717c  jnz     short loc_180007185
0x18000717e  mov     [r14+3C0h], esi
0x180007185  call    ?IsDirectXRunningFullScreen@@YAHXZ; IsDirectXRunningFullScreen(void)
0x18000718a  test    eax, eax
0x18000718c  jz      loc_1800072A1
0x180007192  cmp     dword ptr [rbp+57h+var_80+8], 0
0x180007196  jnz     loc_18000729B
0x18000719c  cmp     dword ptr [rbp+57h+var_80+4], 0
0x1800071a0  jnz     loc_18000729B
0x1800071a6  mov     rcx, [rbp+57h+lParam+8]; hWnd
0x1800071aa  call    cs:__imp_IsWindow
0x1800071b0  test    eax, eax
0x1800071b2  jz      loc_18000729B
0x1800071b8  mov     [r14+3C0h], esi
0x1800071bf  xor     r8d, r8d
0x1800071c2  lea     edx, [r8+6]
0x1800071c6  mov     rcx, rbx
0x1800071c9  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x1800071ce  test    eax, eax
0x1800071d0  jnz     loc_180007256
0x1800071d6  lea     rcx, [rbp+57h+ProcessHandle]
0x1800071da  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800071df  mov     rdi, rax
0x1800071e2  call    cs:__imp_GetCurrentProcess
0x1800071e8  mov     rbx, rax
0x1800071eb  call    cs:__imp_GetCurrentProcess
0x1800071f1  mov     [rsp+0F0h+dwOptions], 0; dwOptions
0x1800071f9  mov     [rsp+0F0h+bInheritHandle], 0; bInheritHandle
0x180007201  mov     [rsp+0F0h+dwDesiredAccess], 0A00h; dwDesiredAccess
0x180007209  mov     r9, rdi; lpTargetHandle
0x18000720c  mov     r8, rbx; hTargetProcessHandle
0x18000720f  mov     rbx, [rbp+57h+hSourceHandle]
0x180007213  mov     rdx, rbx; hSourceHandle
0x180007216  mov     rcx, rax; hSourceProcessHandle
0x180007219  call    cs:__imp_DuplicateHandle
0x18000721f  test    eax, eax
0x180007221  jz      short loc_18000725A
0x180007223  mov     rax, [rbp+57h+ProcessHandle]
0x180007227  lea     rcx, [rax+1]
0x18000722b  cmp     rcx, rsi
0x18000722e  jbe     short loc_18000725E
0x180007230  mov     rcx, rax; ProcessHandle
0x180007233  call    cs:__imp_NtSuspendProcess
0x180007239  test    eax, eax
0x18000723b  js      short loc_18000725A
0x18000723d  mov     [r14+3B0h], esi
0x180007244  jmp     short loc_18000725A
0x180007246  cmp     dword ptr [rbx], 3
0x180007249  jz      loc_180007128
0x18000724f  mov     eax, esi
0x180007251  jmp     loc_18000712A
0x180007256  mov     rbx, [rbp+57h+hSourceHandle]
0x18000725a  mov     rax, [rbp+57h+ProcessHandle]
0x18000725e  lea     rcx, [rax+1]
0x180007262  cmp     rcx, rsi
0x180007265  cmova   rbx, rax
0x180007269  mov     rcx, rbx; void *
0x18000726c  call    ?RestoreFromDirectXRunningFullScreen@@YAJPEAX@Z; RestoreFromDirectXRunningFullScreen(void *)
0x180007271  mov     ebx, eax
0x180007273  test    eax, eax
0x180007275  jns     short loc_1800072A1
0x180007277  mov     rcx, cs:WPP_GLOBAL_Control
0x18000727e  cmp     rcx, r15
0x180007281  jz      loc_180007358
0x180007287  test    [rcx+1Ch], sil
0x18000728b  jz      loc_180007358
0x180007291  mov     edx, 11h
0x180007296  jmp     loc_180006FCE
0x18000729b  mov     rax, [rbp+57h+var_98]
0x18000729f  mov     [rax], esi
0x1800072a1  test    r13d, r13d
0x1800072a4  jnz     short loc_1800072DF
0x1800072a6  cmp     dword ptr [r14+8], 2
0x1800072ab  jnz     short loc_1800072DF
0x1800072ad  test    r12d, r12d
0x1800072b0  jnz     short loc_1800072DF
0x1800072b2  mov     rcx, [r14+78h]; hWnd
0x1800072b6  call    cs:__imp_IsWindow
0x1800072bc  test    eax, eax
0x1800072be  jnz     short loc_1800072DF
0x1800072c0  cmp     [r14+0B0h], eax
0x1800072c7  jz      short loc_1800072DF
0x1800072c9  mov     edx, [rbp+57h+var_B0]
0x1800072cc  or      edx, 400040h
0x1800072d2  mov     [rbp+57h+var_B0], edx
0x1800072d5  mov     rcx, [r14+30h]
0x1800072d9  call    cs:__imp_WerpSetReportFlags
0x1800072df  cmp     dword ptr [r14+3C0h], 0
0x1800072e7  jz      short loc_1800072FD
0x1800072e9  mov     edx, [rbp+57h+var_B0]
0x1800072ec  btr     edx, 16h
0x1800072f0  mov     [rbp+57h+var_B0], edx
0x1800072f3  mov     rcx, [r14+30h]
0x1800072f7  call    cs:__imp_WerpSetReportFlags
0x1800072fd  xor     ebx, ebx
0x1800072ff  jmp     short loc_180007358
0x180007301  mov     rcx, cs:WPP_GLOBAL_Control
0x180007308  cmp     rcx, r15
0x18000730b  jz      short loc_18000732F
0x18000730d  test    [rcx+1Ch], sil
0x180007311  jz      short loc_18000732F
0x180007313  mov     edx, 0Ah
0x180007318  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x18000731f  mov     rcx, [rcx+10h]
0x180007323  call    WPP_SF_
0x180007328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000732f  mov     ebx, 80070057h
0x180007334  cmp     rcx, r15
0x180007337  jz      short loc_180007358
0x180007339  test    [rcx+1Ch], sil
0x18000733d  jz      short loc_180007358
0x18000733f  mov     edx, 0Fh
0x180007344  mov     r9d, ebx
0x180007347  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x18000734e  mov     rcx, [rcx+10h]
0x180007352  call    WPP_SF_d
0x180007357  nop
0x180007358  lea     rcx, [rbp+57h+ProcessHandle]
0x18000735c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007361  mov     eax, ebx
0x180007363  mov     rcx, [rbp+57h+var_40]
0x180007367  xor     rcx, rsp; StackCookie
0x18000736a  call    __security_check_cookie
0x18000736f  mov     rbx, [rsp+0F0h+arg_18]
0x180007377  add     rsp, 0C0h
0x18000737e  pop     r15
0x180007380  pop     r14
0x180007382  pop     r13
0x180007384  pop     r12
  ... truncated ...
```
