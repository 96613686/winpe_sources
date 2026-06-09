# CInitialConsentUI::OnCreated(HWND__ *)

- ea: `0x18000d114`
- end: `0x18000d41f`
- name: `?OnCreated@CInitialConsentUI@@AEAAJPEAUHWND__@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(DWORD_PTR dwRefData, HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000de20`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fc4`
- `0x18000c8a0`
- `0x18000d114`
- `0x18000e348`
- `0x180018010`

## import_xrefs

- `wer!WerpSetReportFlags` at `0x18000d402`
- `wer!WerpSetReportFlags` at `0x18000d402`
- `wer!WerpGetReportFlags` at `0x18000d191`
- `wer!WerpGetReportFlags` at `0x18000d191`
- `KERNEL32!LoadLibraryW` at `0x18000d364`
- `KERNEL32!LoadLibraryW` at `0x18000d364`
- `KERNEL32!GetProcAddress` at `0x18000d37d`
- `KERNEL32!GetProcAddress` at `0x18000d37d`
- `COMCTL32!__imp_SetWindowSubclass` at `0x18000d1f6`
- `COMCTL32!__imp_SetWindowSubclass` at `0x18000d1f6`
- `USER32!FlashWindowEx` at `0x18000d334`
- `USER32!FlashWindowEx` at `0x18000d334`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000d20e`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000d20e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000d229`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000d242`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000d229`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000d242`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d144`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d274`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d353`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d3ad`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d144`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d274`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d353`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d3ad`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000d3ef`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000d3ef`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000d30a`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000d30a`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x18000d28c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x18000d28c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongW` at `0x18000d2a2`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongW` at `0x18000d2a2`

## string_xrefs

- `0x18000d35d`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInitialConsentUI::OnCreated(DWORD_PTR dwRefData, HWND hWnd)
{
  int ReportFlags; // ebx
  BOOL v6; // r14d
  HICON IconW; // rbx
  LONG WindowLongW; // eax
  UINT uFlags; // r14d
  unsigned int v10; // eax
  HWND *v11; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  struct $C811A85A3CBAF233E045382DA27E29BF pfwi; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+30h] BYREF
  HMODULE v16; // [rsp+98h] [rbp+38h] BYREF

  memset(&pfwi, 0, sizeof(pfwi));
  v15 = 0;
  if ( !IsWindow(hWnd) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
    return 0;
  }
  ReportFlags = WerpGetReportFlags(*(_QWORD *)(dwRefData + 40), &v15);
  if ( ReportFlags >= 0 )
  {
    v6 = *(_DWORD *)dwRefData == 4;
    *(_QWORD *)(dwRefData + 264) = hWnd;
    *(_DWORD *)(dwRefData + 348) = SetWindowSubclass(
                                     hWnd,
                                     CInitialConsentUI::Static_TaskDialogSubclassProc,
                                     0,
                                     dwRefData);
    IconW = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
    SendMessageW(*(HWND *)(dwRefData + 264), 0x80u, 0, (LPARAM)IconW);
    SendMessageW(*(HWND *)(dwRefData + 264), 0x80u, 1u, (LPARAM)IconW);
    *(_QWORD *)(dwRefData + 248) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(dwRefData + 80) + 360LL))(*(_QWORD *)(dwRefData + 80));
    *(_QWORD *)(*(_QWORD *)(dwRefData + 80) + 352LL) = hWnd;
    if ( IsWindow(*(HWND *)(dwRefData + 248)) )
    {
      WindowLongW = GetWindowLongW(*(HWND *)(dwRefData + 248), -20);
      SetWindowLongW(*(HWND *)(dwRefData + 248), -20, WindowLongW & 0xFFFFFDFF);
      CReportDetails::PopulateDetails(
        dwRefData + 272,
        *(_QWORD *)(dwRefData + 248),
        0,
        *(_QWORD *)(dwRefData + 40),
        v6,
        *(_DWORD *)(dwRefData + 336) == 0);
    }
    CUIDlgBase::UICallback(dwRefData, 0);
    uFlags = 147;
    if ( *(_DWORD *)dwRefData != 3 )
      uFlags = 67;
    v10 = v15;
    if ( (v15 & 0x200) != 0 )
    {
      if ( (v15 & 0x400000) == 0 )
      {
        ShowWindow(hWnd, 2);
        v10 = v15;
        if ( (v15 & 0x40) == 0 )
        {
          pfwi.cbSize = 32;
          pfwi.hwnd = hWnd;
          pfwi.dwFlags = 3;
          pfwi.uCount = 5;
          FlashWindowEx(&pfwi);
          v10 = v15;
        }
      }
      v15 = v10 & 0xFFFFFDFF;
    }
    v11 = (HWND *)(dwRefData + 256);
    if ( *(_DWORD *)dwRefData == 2 && IsWindow(*v11) )
    {
      LibraryW = LoadLibraryW(L"user32.dll");
      v16 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "FrostCrashedWindow");
        if ( ProcAddress )
        {
          if ( !((unsigned int (__fastcall *)(HWND, HWND))ProcAddress)(*v11, hWnd) )
            *(_DWORD *)(dwRefData + 344) = 1;
        }
      }
      tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v16);
    }
    if ( !IsWindow(*v11) && *(_DWORD *)dwRefData == 2 )
      *(_DWORD *)(dwRefData + 344) = 1;
    SetWindowPos(hWnd, (HWND)-(__int64)(*(_DWORD *)(dwRefData + 344) != 0), 0, 0, 0, 0, uFlags);
    v15 |= 0x40u;
    WerpSetReportFlags(*(_QWORD *)(dwRefData + 40));
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids,
      (unsigned int)ReportFlags);
  return (unsigned int)ReportFlags;
}

```

## disassembly

```asm
0x18000d114  mov     [rsp-18h+arg_0], rbx
0x18000d119  mov     [rsp-18h+arg_8], rsi
0x18000d11e  push    rbp
0x18000d11f  push    rdi
0x18000d120  push    r14
0x18000d122  mov     rbp, rsp
0x18000d125  sub     rsp, 60h
0x18000d129  mov     rsi, rdx
0x18000d12c  mov     rdi, rcx
0x18000d12f  xorps   xmm0, xmm0
0x18000d132  movups  xmmword ptr [rbp+pfwi.cbSize], xmm0
0x18000d136  movups  xmmword ptr [rbp+pfwi.dwFlags], xmm0
0x18000d13a  mov     [rbp+arg_10], 0
0x18000d141  mov     rcx, rdx; hWnd
0x18000d144  call    cs:__imp_IsWindow
0x18000d14a  test    eax, eax
0x18000d14c  jnz     short loc_18000D189
0x18000d14e  lea     rax, WPP_GLOBAL_Control
0x18000d155  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d15c  cmp     rcx, rax
0x18000d15f  jz      loc_18000D408
0x18000d165  test    byte ptr [rcx+1Ch], 1
0x18000d169  jz      loc_18000D408
0x18000d16f  mov     edx, 0Ah
0x18000d174  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d17b  mov     rcx, [rcx+10h]
0x18000d17f  call    WPP_SF_
0x18000d184  jmp     loc_18000D408
0x18000d189  lea     rdx, [rbp+arg_10]
0x18000d18d  mov     rcx, [rdi+28h]
0x18000d191  call    cs:__imp_WerpGetReportFlags
0x18000d197  mov     ebx, eax
0x18000d199  test    eax, eax
0x18000d19b  jns     short loc_18000D1D5
0x18000d19d  lea     rax, WPP_GLOBAL_Control
0x18000d1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1ab  cmp     rcx, rax
0x18000d1ae  jz      short loc_18000D1CE
0x18000d1b0  test    byte ptr [rcx+1Ch], 1
0x18000d1b4  jz      short loc_18000D1CE
0x18000d1b6  mov     edx, 0Bh
0x18000d1bb  mov     r9d, ebx
0x18000d1be  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d1c5  mov     rcx, [rcx+10h]
0x18000d1c9  call    WPP_SF_d
0x18000d1ce  mov     eax, ebx
0x18000d1d0  jmp     loc_18000D40A
0x18000d1d5  xor     r14d, r14d
0x18000d1d8  cmp     dword ptr [rdi], 4
0x18000d1db  setz    r14b
0x18000d1df  mov     [rdi+108h], rsi
0x18000d1e6  mov     r9, rdi; dwRefData
0x18000d1e9  xor     r8d, r8d; uIdSubclass
0x18000d1ec  lea     rdx, ?Static_TaskDialogSubclassProc@CInitialConsentUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000d1f3  mov     rcx, rsi; hWnd
0x18000d1f6  call    cs:__imp_SetWindowSubclass
0x18000d1fc  mov     [rdi+15Ch], eax
0x18000d202  mov     edx, 194h; lpIconName
0x18000d207  lea     rcx, __ImageBase; hInstance
0x18000d20e  call    cs:__imp_LoadIconW
0x18000d214  mov     rbx, rax
0x18000d217  mov     r9, rax; lParam
0x18000d21a  xor     r8d, r8d; wParam
0x18000d21d  mov     edx, 80h; Msg
0x18000d222  mov     rcx, [rdi+108h]; hWnd
0x18000d229  call    cs:__imp_SendMessageW
0x18000d22f  mov     r9, rbx; lParam
0x18000d232  mov     edx, 80h; Msg
0x18000d237  lea     r8d, [rdx-7Fh]; wParam
0x18000d23b  mov     rcx, [rdi+108h]; hWnd
0x18000d242  call    cs:__imp_SendMessageW
0x18000d248  mov     rcx, [rdi+50h]
0x18000d24c  mov     rax, [rcx]
0x18000d24f  mov     rax, [rax+168h]
0x18000d256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d25b  mov     [rdi+0F8h], rax
0x18000d262  mov     rax, [rdi+50h]
0x18000d266  mov     [rax+160h], rsi
0x18000d26d  mov     rcx, [rdi+0F8h]; hWnd
0x18000d274  call    cs:__imp_IsWindow
0x18000d27a  test    eax, eax
0x18000d27c  jz      short loc_18000D2D6
0x18000d27e  mov     ebx, 0FFFFFFECh
0x18000d283  mov     edx, ebx; nIndex
0x18000d285  mov     rcx, [rdi+0F8h]; hWnd
0x18000d28c  call    cs:__imp_GetWindowLongW
0x18000d292  btr     eax, 9
0x18000d296  mov     r8d, eax; dwNewLong
0x18000d299  mov     edx, ebx; nIndex
0x18000d29b  mov     rcx, [rdi+0F8h]; hWnd
0x18000d2a2  call    cs:__imp_SetWindowLongW
0x18000d2a8  xor     eax, eax
0x18000d2aa  cmp     [rdi+150h], eax
0x18000d2b0  setz    al
0x18000d2b3  lea     rcx, [rdi+110h]
0x18000d2ba  mov     [rsp+60h+cy], eax
0x18000d2be  mov     [rsp+60h+var_40], r14d
0x18000d2c3  mov     r9, [rdi+28h]
0x18000d2c7  xor     r8d, r8d
0x18000d2ca  mov     rdx, [rdi+0F8h]
0x18000d2d1  call    ?PopulateDetails@CReportDetails@@QEAAJPEAUHWND__@@W4CONSENTDLG_TYPE@@PEAXHH@Z; CReportDetails::PopulateDetails(HWND__ *,CONSENTDLG_TYPE,void *,int,int)
0x18000d2d6  mov     r8, rsi
0x18000d2d9  xor     edx, edx
0x18000d2db  mov     rcx, rdi
0x18000d2de  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000d2e3  mov     eax, 43h ; 'C'
0x18000d2e8  lea     r14d, [rax+50h]
0x18000d2ec  cmp     dword ptr [rdi], 3
0x18000d2ef  cmovnz  r14d, eax
0x18000d2f3  mov     eax, [rbp+arg_10]
0x18000d2f6  bt      eax, 9
0x18000d2fa  jnb     short loc_18000D344
0x18000d2fc  bt      eax, 16h
0x18000d300  jb      short loc_18000D33D
0x18000d302  mov     edx, 2; nCmdShow
0x18000d307  mov     rcx, rsi; hWnd
0x18000d30a  call    cs:__imp_ShowWindow
0x18000d310  mov     eax, [rbp+arg_10]
0x18000d313  test    al, 40h
0x18000d315  jnz     short loc_18000D33D
0x18000d317  mov     [rbp+pfwi.cbSize], 20h ; ' '
0x18000d31e  mov     [rbp+pfwi.hwnd], rsi
0x18000d322  mov     [rbp+pfwi.dwFlags], 3
0x18000d329  mov     [rbp+pfwi.uCount], 5
0x18000d330  lea     rcx, [rbp+pfwi]; pfwi
0x18000d334  call    cs:__imp_FlashWindowEx
0x18000d33a  mov     eax, [rbp+arg_10]
0x18000d33d  btr     eax, 9
0x18000d341  mov     [rbp+arg_10], eax
0x18000d344  lea     rbx, [rdi+100h]
0x18000d34b  cmp     dword ptr [rdi], 2
0x18000d34e  jnz     short loc_18000D3AA
0x18000d350  mov     rcx, [rbx]; hWnd
0x18000d353  call    cs:__imp_IsWindow
0x18000d359  test    eax, eax
0x18000d35b  jz      short loc_18000D3AA
0x18000d35d  lea     rcx, aUser32Dll_0; "user32.dll"
0x18000d364  call    cs:__imp_LoadLibraryW
0x18000d36a  mov     [rbp+arg_18], rax
0x18000d36e  test    rax, rax
0x18000d371  jz      short loc_18000D3A1
0x18000d373  lea     rdx, aFrostcrashedwi; "FrostCrashedWindow"
0x18000d37a  mov     rcx, rax; hModule
0x18000d37d  call    cs:__imp_GetProcAddress
0x18000d383  test    rax, rax
0x18000d386  jz      short loc_18000D3A1
0x18000d388  mov     rdx, rsi
0x18000d38b  mov     rcx, [rbx]
0x18000d38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d393  test    eax, eax
0x18000d395  jnz     short loc_18000D3A1
0x18000d397  mov     dword ptr [rdi+158h], 1
0x18000d3a1  lea     rcx, [rbp+arg_18]
0x18000d3a5  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18000d3aa  mov     rcx, [rbx]; hWnd
0x18000d3ad  call    cs:__imp_IsWindow
0x18000d3b3  test    eax, eax
0x18000d3b5  jnz     short loc_18000D3C6
0x18000d3b7  cmp     dword ptr [rdi], 2
0x18000d3ba  jnz     short loc_18000D3C6
0x18000d3bc  mov     dword ptr [rdi+158h], 1
0x18000d3c6  mov     eax, [rdi+158h]
0x18000d3cc  neg     eax
0x18000d3ce  sbb     rdx, rdx; hWndInsertAfter
0x18000d3d1  mov     [rsp+60h+uFlags], r14d; uFlags
0x18000d3d6  mov     [rsp+60h+cy], 0; cy
0x18000d3de  mov     [rsp+60h+var_40], 0; cx
0x18000d3e6  xor     r9d, r9d; Y
0x18000d3e9  xor     r8d, r8d; X
0x18000d3ec  mov     rcx, rsi; hWnd
0x18000d3ef  call    cs:__imp_SetWindowPos
0x18000d3f5  mov     edx, [rbp+arg_10]
0x18000d3f8  or      edx, 40h
0x18000d3fb  mov     [rbp+arg_10], edx
0x18000d3fe  mov     rcx, [rdi+28h]
0x18000d402  call    cs:__imp_WerpSetReportFlags
0x18000d408  xor     eax, eax
0x18000d40a  lea     r11, [rsp+60h+var_s0]
0x18000d40f  mov     rbx, [r11+20h]
0x18000d413  mov     rsi, [r11+28h]
0x18000d417  mov     rsp, r11
0x18000d41a  pop     r14
0x18000d41c  pop     rdi
0x18000d41d  pop     rbp
0x18000d41e  retn
```
