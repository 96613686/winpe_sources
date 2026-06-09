# CEventUI::OnInitProgressDialog(HWND__ *,int)

- ea: `0x180006bdc`
- end: `0x180006e84`
- name: `?OnInitProgressDialog@CEventUI@@AEAAJPEAUHWND__@@H@Z`
- size: `680`
- prototype: `__int64 __fastcall(DWORD_PTR dwRefData, HWND hWnd, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fc4`
- `0x180006bdc`
- `0x180008ec8`
- `0x18000c8a0`
- `0x180018010`

## import_xrefs

- `wer!WerpSetReportFlags` at `0x180006e6f`
- `wer!WerpSetReportFlags` at `0x180006e6f`
- `wer!WerpGetReportFlags` at `0x180006c57`
- `wer!WerpGetReportFlags` at `0x180006c57`
- `KERNEL32!GetTickCount` at `0x180006cc9`
- `KERNEL32!GetTickCount` at `0x180006cc9`
- `KERNEL32!GetProcAddress` at `0x180006d74`
- `KERNEL32!GetProcAddress` at `0x180006d74`
- `COMCTL32!__imp_SetWindowSubclass` at `0x180006ce5`
- `COMCTL32!__imp_SetWindowSubclass` at `0x180006ce5`
- `USER32!FlashWindowEx` at `0x180006e5b`
- `USER32!FlashWindowEx` at `0x180006e5b`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x180006cfd`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x180006cfd`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006cae`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006d19`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006d2d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006cae`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006d19`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006d2d`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006c0a`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006d44`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006da4`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006c0a`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006d44`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180006da4`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180006e18`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180006e18`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180006e33`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180006e33`

## string_xrefs

- `0x180006d53`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventUI::OnInitProgressDialog(DWORD_PTR dwRefData, HWND hWnd, int a3)
{
  int ReportFlags; // ebx
  HICON IconW; // rbx
  _DWORD *v9; // r14
  HWND *v10; // rbx
  FARPROC ProcAddress; // rax
  UINT uFlags; // eax
  int v13; // ecx
  unsigned int v14; // edx
  HMODULE hModule; // [rsp+40h] [rbp-38h] BYREF
  $C811A85A3CBAF233E045382DA27E29BF pfwi; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v17; // [rsp+C8h] [rbp+50h] BYREF

  memset(&pfwi, 0, sizeof(pfwi));
  v17 = 0;
  if ( !IsWindow(hWnd) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
    return 0;
  }
  ReportFlags = WerpGetReportFlags(*(_QWORD *)(dwRefData + 48), &v17);
  if ( ReportFlags >= 0 )
  {
    *(_QWORD *)(dwRefData + 104) = hWnd;
    SendMessageW(hWnd, 0x46Bu, 1u, 0);
    (*(void (__fastcall **)(DWORD_PTR, _QWORD))(*(_QWORD *)dwRefData + 16LL))(
      dwRefData,
      *(unsigned int *)(dwRefData + 176));
    *(_DWORD *)(dwRefData + 756) = GetTickCount();
    *(_DWORD *)(dwRefData + 932) = SetWindowSubclass(hWnd, CEventUI::Static_ProgressDialogSubclassProc, 0, dwRefData);
    IconW = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
    SendMessageW(*(HWND *)(dwRefData + 104), 0x80u, 0, (LPARAM)IconW);
    SendMessageW(*(HWND *)(dwRefData + 104), 0x80u, 1u, (LPARAM)IconW);
    v9 = (_DWORD *)(dwRefData + 8);
    v10 = (HWND *)(dwRefData + 120);
    if ( *(_DWORD *)(dwRefData + 8) == 2 && IsWindow(*v10) && !a3 )
    {
      UtilLoadModFromSystem(&hModule, (__int64)L"user32.dll");
      if ( hModule )
      {
        ProcAddress = GetProcAddress(hModule, "FrostCrashedWindow");
        if ( ProcAddress )
        {
          if ( !((unsigned int (__fastcall *)(HWND, HWND))ProcAddress)(*v10, hWnd) )
            *(_DWORD *)(dwRefData + 960) = 1;
        }
      }
      tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&hModule);
    }
    if ( !IsWindow(*v10) && *v9 == 2 && (v17 & 0x400000) == 0 )
      *(_DWORD *)(dwRefData + 960) = 1;
    CUIDlgBase::UICallback(dwRefData + 8, 2);
    uFlags = 3;
    v13 = *(_DWORD *)(dwRefData + 960);
    if ( v13 && *v9 == 2 )
      uFlags = 67;
    SetWindowPos(hWnd, (HWND)-(__int64)(v13 != 0), 0, 0, 0, 0, uFlags);
    v14 = v17;
    if ( (v17 & 0x200) != 0 )
    {
      if ( (v17 & 0x400000) == 0 )
      {
        ShowWindow(hWnd, 2);
        v14 = v17;
        if ( (v17 & 0x40) == 0 )
        {
          pfwi.cbSize = 32;
          pfwi.hwnd = hWnd;
          pfwi.dwFlags = 3;
          pfwi.uCount = 5;
          FlashWindowEx(&pfwi);
          v14 = v17;
        }
      }
      v17 = v14 & 0xFFFFFDFF;
      WerpSetReportFlags(*(_QWORD *)(dwRefData + 48));
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
      (unsigned int)ReportFlags);
  return (unsigned int)ReportFlags;
}

```

## disassembly

```asm
0x180006bdc  push    rbp
0x180006bde  push    rbx
0x180006bdf  push    rsi
0x180006be0  push    rdi
0x180006be1  push    r14
0x180006be3  push    r15
0x180006be5  mov     rbp, rsp
0x180006be8  sub     rsp, 78h
0x180006bec  mov     r15d, r8d
0x180006bef  mov     rsi, rdx
0x180006bf2  mov     rdi, rcx
0x180006bf5  xorps   xmm0, xmm0
0x180006bf8  movups  xmmword ptr [rbp+pfwi.cbSize], xmm0
0x180006bfc  movups  xmmword ptr [rbp+pfwi.dwFlags], xmm0
0x180006c00  mov     [rbp+arg_18], 0
0x180006c07  mov     rcx, rdx; hWnd
0x180006c0a  call    cs:__imp_IsWindow
0x180006c10  test    eax, eax
0x180006c12  jnz     short loc_180006C4F
0x180006c14  lea     rax, WPP_GLOBAL_Control
0x180006c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c22  cmp     rcx, rax
0x180006c25  jz      loc_180006E75
0x180006c2b  test    byte ptr [rcx+1Ch], 1
0x180006c2f  jz      loc_180006E75
0x180006c35  mov     edx, 21h ; '!'
0x180006c3a  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006c41  mov     rcx, [rcx+10h]
0x180006c45  call    WPP_SF_
0x180006c4a  jmp     loc_180006E75
0x180006c4f  lea     rdx, [rbp+arg_18]
0x180006c53  mov     rcx, [rdi+30h]
0x180006c57  call    cs:__imp_WerpGetReportFlags
0x180006c5d  mov     ebx, eax
0x180006c5f  test    eax, eax
0x180006c61  jns     short loc_180006C9B
0x180006c63  lea     rax, WPP_GLOBAL_Control
0x180006c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c71  cmp     rcx, rax
0x180006c74  jz      short loc_180006C94
0x180006c76  test    byte ptr [rcx+1Ch], 1
0x180006c7a  jz      short loc_180006C94
0x180006c7c  mov     edx, 22h ; '"'
0x180006c81  mov     r9d, ebx
0x180006c84  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006c8b  mov     rcx, [rcx+10h]
0x180006c8f  call    WPP_SF_d
0x180006c94  mov     eax, ebx
0x180006c96  jmp     loc_180006E77
0x180006c9b  mov     [rdi+68h], rsi
0x180006c9f  xor     r9d, r9d; lParam
0x180006ca2  mov     edx, 46Bh; Msg
0x180006ca7  lea     r8d, [r9+1]; wParam
0x180006cab  mov     rcx, rsi; hWnd
0x180006cae  call    cs:__imp_SendMessageW
0x180006cb4  mov     rax, [rdi]
0x180006cb7  mov     edx, [rdi+0B0h]
0x180006cbd  mov     rcx, rdi
0x180006cc0  mov     rax, [rax+10h]
0x180006cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc9  call    cs:__imp_GetTickCount
0x180006ccf  mov     [rdi+2F4h], eax
0x180006cd5  mov     r9, rdi; dwRefData
0x180006cd8  xor     r8d, r8d; uIdSubclass
0x180006cdb  lea     rdx, ?Static_ProgressDialogSubclassProc@CEventUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x180006ce2  mov     rcx, rsi; hWnd
0x180006ce5  call    cs:__imp_SetWindowSubclass
0x180006ceb  mov     [rdi+3A4h], eax
0x180006cf1  mov     edx, 194h; lpIconName
0x180006cf6  lea     rcx, __ImageBase; hInstance
0x180006cfd  call    cs:__imp_LoadIconW
0x180006d03  mov     rbx, rax
0x180006d06  mov     r9, rax; lParam
0x180006d09  xor     r8d, r8d; wParam
0x180006d0c  mov     r14d, 80h
0x180006d12  mov     edx, r14d; Msg
0x180006d15  mov     rcx, [rdi+68h]; hWnd
0x180006d19  call    cs:__imp_SendMessageW
0x180006d1f  mov     r9, rbx; lParam
0x180006d22  lea     r8d, [r14-7Fh]; wParam
0x180006d26  mov     edx, r14d; Msg
0x180006d29  mov     rcx, [rdi+68h]; hWnd
0x180006d2d  call    cs:__imp_SendMessageW
0x180006d33  lea     r14, [rdi+8]
0x180006d37  lea     rbx, [rdi+78h]
0x180006d3b  cmp     dword ptr [r14], 2
0x180006d3f  jnz     short loc_180006DA1
0x180006d41  mov     rcx, [rbx]; hWnd
0x180006d44  call    cs:__imp_IsWindow
0x180006d4a  test    eax, eax
0x180006d4c  jz      short loc_180006DA1
0x180006d4e  test    r15d, r15d
0x180006d51  jnz     short loc_180006DA1
0x180006d53  lea     rdx, aUser32Dll_0; "user32.dll"
0x180006d5a  lea     rcx, [rbp+hModule]
0x180006d5e  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEBG@Z; UtilLoadModFromSystem(ushort const *)
0x180006d63  nop
0x180006d64  mov     rcx, [rbp+hModule]; hModule
0x180006d68  test    rcx, rcx
0x180006d6b  jz      short loc_180006D98
0x180006d6d  lea     rdx, aFrostcrashedwi; "FrostCrashedWindow"
0x180006d74  call    cs:__imp_GetProcAddress
0x180006d7a  test    rax, rax
0x180006d7d  jz      short loc_180006D98
0x180006d7f  mov     rdx, rsi
0x180006d82  mov     rcx, [rbx]
0x180006d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d8a  test    eax, eax
0x180006d8c  jnz     short loc_180006D98
0x180006d8e  mov     dword ptr [rdi+3C0h], 1
0x180006d98  lea     rcx, [rbp+hModule]
0x180006d9c  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180006da1  mov     rcx, [rbx]; hWnd
0x180006da4  call    cs:__imp_IsWindow
0x180006daa  mov     ebx, 400000h
0x180006daf  test    eax, eax
0x180006db1  jnz     short loc_180006DC8
0x180006db3  cmp     dword ptr [r14], 2
0x180006db7  jnz     short loc_180006DC8
0x180006db9  test    [rbp+arg_18], ebx
0x180006dbc  jnz     short loc_180006DC8
0x180006dbe  mov     dword ptr [rdi+3C0h], 1
0x180006dc8  mov     r8, rsi
0x180006dcb  mov     edx, 2
0x180006dd0  mov     rcx, r14
0x180006dd3  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180006dd8  mov     r15d, 3
0x180006dde  mov     eax, r15d
0x180006de1  mov     ecx, [rdi+3C0h]
0x180006de7  test    ecx, ecx
0x180006de9  jz      short loc_180006DF6
0x180006deb  lea     edx, [r15+40h]
0x180006def  cmp     dword ptr [r14], 2
0x180006df3  cmovz   eax, edx
0x180006df6  neg     ecx
0x180006df8  sbb     rdx, rdx; hWndInsertAfter
0x180006dfb  mov     [rsp+78h+uFlags], eax; uFlags
0x180006dff  mov     [rsp+78h+cy], 0; cy
0x180006e07  mov     [rsp+78h+var_58], 0; cx
0x180006e0f  xor     r9d, r9d; Y
0x180006e12  xor     r8d, r8d; X
0x180006e15  mov     rcx, rsi; hWnd
0x180006e18  call    cs:__imp_SetWindowPos
0x180006e1e  mov     edx, [rbp+arg_18]
0x180006e21  bt      edx, 9
0x180006e25  jnb     short loc_180006E75
0x180006e27  test    ebx, edx
0x180006e29  jnz     short loc_180006E64
0x180006e2b  mov     edx, 2; nCmdShow
0x180006e30  mov     rcx, rsi; hWnd
0x180006e33  call    cs:__imp_ShowWindow
0x180006e39  mov     edx, [rbp+arg_18]
0x180006e3c  test    dl, 40h
0x180006e3f  jnz     short loc_180006E64
0x180006e41  mov     [rbp+pfwi.cbSize], 20h ; ' '
0x180006e48  mov     [rbp+pfwi.hwnd], rsi
0x180006e4c  mov     [rbp+pfwi.dwFlags], r15d
0x180006e50  mov     [rbp+pfwi.uCount], 5
0x180006e57  lea     rcx, [rbp+pfwi]; pfwi
0x180006e5b  call    cs:__imp_FlashWindowEx
0x180006e61  mov     edx, [rbp+arg_18]
0x180006e64  btr     edx, 9
0x180006e68  mov     [rbp+arg_18], edx
0x180006e6b  mov     rcx, [rdi+30h]
0x180006e6f  call    cs:__imp_WerpSetReportFlags
0x180006e75  xor     eax, eax
0x180006e77  add     rsp, 78h
0x180006e7b  pop     r15
0x180006e7d  pop     r14
0x180006e7f  pop     rdi
0x180006e80  pop     rsi
0x180006e81  pop     rbx
0x180006e82  pop     rbp
0x180006e83  retn
```
