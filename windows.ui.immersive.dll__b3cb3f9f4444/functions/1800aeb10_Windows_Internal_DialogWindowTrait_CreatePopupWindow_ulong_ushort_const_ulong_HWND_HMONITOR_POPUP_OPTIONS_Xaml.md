# Windows::Internal::DialogWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS,XamlPopupOptions)

- ea: `0x1800aeb10`
- end: `0x1800aef18`
- name: `?CreatePopupWindow@DialogWindowTrait@Internal@Windows@@UEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@W4XamlPopupOptions@@@Z`
- size: `1032`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002a36c`
- `0x180030d44`
- `0x180051318`
- `0x180054130`
- `0x180054ad4`
- `0x1800aeb10`
- `0x1800af4bc`
- `0x1800af5d4`
- `0x1800b01bc`
- `0x1800e04f0`
- `0x1800ed010`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800aee13`
- `USER32!CreateWindowInBandEx` at `0x1800aee13`
- `USER32!GetWindowBand` at `0x1800aec4f`
- `USER32!GetWindowBand` at `0x1800aec4f`
- `USER32!SetPropW` at `0x1800aeeb8`
- `USER32!SetPropW` at `0x1800aeeb8`
- `USER32!RegisterClassW` at `0x1800aec06`
- `USER32!RegisterClassW` at `0x1800aec06`
- `USER32!GetAncestor` at `0x1800aec71`
- `USER32!GetAncestor` at `0x1800aec71`
- `USER32!LoadCursorW` at `0x1800aebcd`
- `USER32!LoadCursorW` at `0x1800aebcd`
- `USER32!GetWindowRect` at `0x1800aed9a`
- `USER32!GetWindowRect` at `0x1800aed9a`
- `USER32!GetWindow` at `0x1800aece6`
- `USER32!GetWindow` at `0x1800aee98`
- `USER32!GetWindow` at `0x1800aece6`
- `USER32!GetWindow` at `0x1800aee98`
- `USER32!SendMessageW` at `0x1800aeee8`
- `USER32!SendMessageW` at `0x1800aeee8`
- `USER32!DefWindowProcW` at `0x1800aebb0`
- `USER32!__imp_IsShellFrameWindow` at `0x1800aec83`
- `USER32!__imp_IsShellFrameWindow` at `0x1800aec83`
- `USER32!__imp_IsShellManagedWindow` at `0x1800aec15`
- `USER32!__imp_IsShellManagedWindow` at `0x1800aec15`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800aed38`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800aed38`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800aed65`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800aee2e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800aed65`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800aee2e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!AreDpiAwarenessContextsEqual` at `0x1800aed4e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!AreDpiAwarenessContextsEqual` at `0x1800aed4e`

## pseudocode

```c
HWND __fastcall Windows::Internal::DialogWindowTrait::CreatePopupWindow(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        HWND hwnd,
        __int64 a6,
        int a7,
        int a8)
{
  bool *v9; // r8
  HCURSOR CursorW; // rax
  bool v11; // zf
  const wchar_t *v12; // r13
  const WCHAR *v13; // rax
  int v14; // eax
  __int64 v15; // r15
  int v16; // ecx
  int WindowBand; // eax
  HWND Ancestor; // rdi
  int v19; // eax
  HWND WindowInBand; // rdi
  unsigned int v21; // eax
  __int64 v22; // rsi
  unsigned int v23; // edi
  __int64 ThreadDpiAwarenessContext; // rax
  LONG left; // ecx
  LONG top; // r9d
  int v27; // edx
  int v28; // r8d
  HWND v29; // rsi
  bool v31; // [rsp+70h] [rbp-90h]
  CallerIdentity *v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v34; // [rsp+84h] [rbp-7Ch]
  int v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  WNDCLASSW WndClass; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+F0h] [rbp-10h] BYREF

  *(_QWORD *)&Rect.left = a6;
  v36 = a3;
  v34 = a2;
  *(_DWORD *)(a1 + 20) = a8;
  v35 = a4;
  *(_DWORD *)(a1 + 16) = a7;
  v32 = 0;
  if ( (int)CallerIdentity::GetCallingProcessHandle(a1, 0, &v32) >= 0 )
    CallerIdentity::IsProcessAppContainer(v32, (void *)(a1 + 32), v9);
  CAutoHandle<void *>::~CAutoHandle<void *>(&v32);
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = DefWindowProcW;
  WndClass.hInstance = &_ImageBase;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  v11 = *(_BYTE *)(a1 + 60) == 0;
  WndClass.hCursor = CursorW;
  v12 = L"Shell_HostingContainer";
  v13 = L"Shell_HostingContainer";
  WndClass.hbrBackground = (HBRUSH)6;
  if ( v11 )
    v13 = L"Shell_Dialog";
  WndClass.lpszClassName = v13;
  RegisterClassW(&WndClass);
  v14 = IsShellManagedWindow(hwnd);
  v15 = (__int64)hwnd;
  v31 = v14 != 0;
  v16 = 0;
  LODWORD(v32) = 0;
  v33 = 0;
  if ( v14 )
  {
    if ( *(_BYTE *)(a1 + 32) )
    {
      LODWORD(v32) = 1;
      v15 = 0;
      WindowBand = GetWindowBand(hwnd, &v33);
      v16 = (int)v32;
      if ( !WindowBand )
        v33 = 1;
    }
    else
    {
      Ancestor = GetAncestor(hwnd, 1u);
      v19 = IsShellFrameWindow(Ancestor);
      v16 = (int)v32;
      if ( v19 )
      {
        v15 = (__int64)Ancestor;
        v31 = 0;
      }
    }
  }
  if ( (a7 & 8) != 0 )
  {
    if ( !*(_BYTE *)(a1 + 60) )
      v12 = L"Shell_Dialog";
    WindowInBand = (HWND)Windows::Internal::_anonymous_namespace_::CDimmingWindow::CreateOnDesktop(
                           v34,
                           (_DWORD)v12,
                           v36,
                           v35,
                           v15,
                           v16,
                           *(__int64 *)&Rect.left);
    *(_QWORD *)(a1 + 48) = GetWindow(WindowInBand, 4u);
  }
  else
  {
    v21 = 0x80000000;
    if ( !*(_BYTE *)(a1 + 61) && (a7 & 0x200000) == 0 )
    {
      v21 = -2134900736;
      if ( *(_BYTE *)(a1 + 60) )
        v21 = -2134376448;
    }
    v22 = 0;
    v23 = v21 | 0xCA0000;
    if ( (a7 & 0x20000000) == 0 )
      v23 = v21;
    ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
    if ( (unsigned int)AreDpiAwarenessContextsEqual(ThreadDpiAwarenessContext, -3) )
      v22 = SetThreadDpiAwarenessContext(-4);
    left = 0x80000000;
    top = 0x80000000;
    v27 = 0x80000000;
    v28 = 0x80000000;
    if ( hwnd && *(_BYTE *)(a1 + 62) )
    {
      Rect = 0;
      GetWindowRect(hwnd, &Rect);
      left = Rect.left;
      v27 = Rect.right - Rect.left;
      top = Rect.top;
      v28 = Rect.bottom - Rect.top;
    }
    if ( !*(_BYTE *)(a1 + 60) )
      v12 = L"Shell_Dialog";
    WindowInBand = (HWND)CreateWindowInBandEx(
                           v34,
                           v12,
                           v36,
                           v23,
                           left,
                           top,
                           v27,
                           v28,
                           v15,
                           0,
                           &_ImageBase,
                           0,
                           v33,
                           (_DWORD)v32);
    if ( v22 )
      SetThreadDpiAwarenessContext(-3);
    if ( *(_BYTE *)(a1 + 61) )
      Windows::Internal::DialogWindowTrait::_SetWindowVisualPolicy(WindowInBand, 1);
  }
  if ( WindowInBand )
  {
    *(_QWORD *)(a1 + 8) = v15;
    if ( v31 )
    {
      v29 = WindowInBand;
      if ( *(_QWORD *)(a1 + 48) )
        v29 = *(HWND *)(a1 + 48);
      if ( (int)Windows::Internal::DialogWindowTrait::_EnsureBroker((Windows::Internal::DialogWindowTrait *)a1) >= 0
        && (*(int (__fastcall **)(_QWORD, HWND, HWND))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40), v29, hwnd) >= 0 )
      {
        *(_QWORD *)(a1 + 8) = GetWindow(v29, 4u);
      }
    }
    SetPropW(WindowInBand, L"Shell_Dialog_Window_Prop", HANDLE_FLAG_INHERIT);
    if ( (*(_DWORD *)(a1 + 16) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, WindowInBand);
    SendMessageW(WindowInBand, 0x127u, 0x30001u, 0);
  }
  return WindowInBand;
}

```

## disassembly

```asm
0x1800aeb10  push    rbp
0x1800aeb12  push    rbx
0x1800aeb13  push    rsi
0x1800aeb14  push    rdi
0x1800aeb15  push    r12
0x1800aeb17  push    r13
0x1800aeb19  push    r14
0x1800aeb1b  push    r15
0x1800aeb1d  lea     rbp, [rsp-18h]
0x1800aeb22  sub     rsp, 118h
0x1800aeb29  mov     rax, cs:__security_cookie
0x1800aeb30  xor     rax, rsp
0x1800aeb33  mov     [rbp+50h+var_50], rax
0x1800aeb37  mov     rax, [rbp+50h+arg_28]
0x1800aeb3e  mov     rbx, rcx
0x1800aeb41  mov     esi, [rbp+50h+arg_30]
0x1800aeb47  mov     r12d, esi
0x1800aeb4a  mov     r14, [rbp+50h+hwnd]
0x1800aeb51  and     r12d, 8
0x1800aeb55  mov     qword ptr [rbp+50h+Rect.left], rax
0x1800aeb59  mov     eax, [rbp+50h+arg_38]
0x1800aeb5f  mov     [rbp+50h+var_C0], r8
0x1800aeb63  lea     r8, [rsp+150h+var_D8]
0x1800aeb68  mov     [rbp+50h+var_CC], edx
0x1800aeb6b  xor     edx, edx
0x1800aeb6d  mov     [rcx+14h], eax
0x1800aeb70  mov     [rbp+50h+var_C8], r9d
0x1800aeb74  mov     [rcx+10h], esi
0x1800aeb77  mov     [rsp+150h+var_D8], 0
0x1800aeb80  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x1800aeb85  test    eax, eax
0x1800aeb87  js      short loc_1800AEB97
0x1800aeb89  mov     rcx, [rsp+150h+var_D8]; this
0x1800aeb8e  lea     rdx, [rbx+20h]; void *
0x1800aeb92  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x1800aeb97  lea     rcx, [rsp+150h+var_D8]
0x1800aeb9c  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800aeba1  xor     edx, edx; Val
0x1800aeba3  lea     rcx, [rbp+50h+WndClass]; void *
0x1800aeba7  lea     r8d, [rdx+48h]; Size
0x1800aebab  call    memset_0
0x1800aebb0  mov     rax, cs:__imp_DefWindowProcW
0x1800aebb7  mov     edx, 7F00h; lpCursorName
0x1800aebbc  mov     [rbp+50h+WndClass.lpfnWndProc], rax
0x1800aebc0  xor     ecx, ecx; hInstance
0x1800aebc2  lea     rax, __ImageBase
0x1800aebc9  mov     [rbp+50h+WndClass.hInstance], rax
0x1800aebcd  call    cs:__imp_LoadCursorW
0x1800aebd4  nop     dword ptr [rax+rax+00h]
0x1800aebd9  cmp     byte ptr [rbx+3Ch], 0
0x1800aebdd  lea     rcx, aShellDialog; "Shell_Dialog"
0x1800aebe4  mov     [rbp+50h+WndClass.hCursor], rax
0x1800aebe8  lea     r13, aShellHostingco_0; "Shell_HostingContainer"
0x1800aebef  mov     rax, r13
0x1800aebf2  mov     [rbp+50h+WndClass.hbrBackground], 6
0x1800aebfa  cmovz   rax, rcx
0x1800aebfe  lea     rcx, [rbp+50h+WndClass]; lpWndClass
0x1800aec02  mov     [rbp+50h+WndClass.lpszClassName], rax
0x1800aec06  call    cs:__imp_RegisterClassW
0x1800aec0d  nop     dword ptr [rax+rax+00h]
0x1800aec12  mov     rcx, r14
0x1800aec15  call    cs:__imp_IsShellManagedWindow
0x1800aec1c  nop     dword ptr [rax+rax+00h]
0x1800aec21  test    eax, eax
0x1800aec23  mov     r15, r14
0x1800aec26  setnz   [rsp+150h+var_E0]
0x1800aec2b  xor     ecx, ecx
0x1800aec2d  mov     dword ptr [rsp+150h+var_D8], ecx
0x1800aec31  mov     [rbp+50h+var_D0], ecx
0x1800aec34  test    eax, eax
0x1800aec36  jz      short loc_1800AEC9F
0x1800aec38  cmp     [rbx+20h], cl
0x1800aec3b  mov     rcx, r14; hwnd
0x1800aec3e  jz      short loc_1800AEC6C
0x1800aec40  lea     rdx, [rbp+50h+var_D0]
0x1800aec44  mov     dword ptr [rsp+150h+var_D8], 1
0x1800aec4c  xor     r15d, r15d
0x1800aec4f  call    cs:__imp_GetWindowBand
0x1800aec56  nop     dword ptr [rax+rax+00h]
0x1800aec5b  mov     ecx, dword ptr [rsp+150h+var_D8]
0x1800aec5f  test    eax, eax
0x1800aec61  jnz     short loc_1800AEC9F
0x1800aec63  mov     [rbp+50h+var_D0], 1
0x1800aec6a  jmp     short loc_1800AEC9F
0x1800aec6c  mov     edx, 1; gaFlags
0x1800aec71  call    cs:__imp_GetAncestor
0x1800aec78  nop     dword ptr [rax+rax+00h]
0x1800aec7d  mov     rcx, rax
0x1800aec80  mov     rdi, rax
0x1800aec83  call    cs:__imp_IsShellFrameWindow
0x1800aec8a  nop     dword ptr [rax+rax+00h]
0x1800aec8f  mov     ecx, dword ptr [rsp+150h+var_D8]
0x1800aec93  test    eax, eax
0x1800aec95  jz      short loc_1800AEC9F
0x1800aec97  mov     r15, rdi
0x1800aec9a  mov     [rsp+150h+var_E0], 0
0x1800aec9f  test    r12d, r12d
0x1800aeca2  jz      short loc_1800AECFB
0x1800aeca4  mov     rax, qword ptr [rbp+50h+Rect.left]
0x1800aeca8  lea     r10, aShellDialog; "Shell_Dialog"
0x1800aecaf  mov     r9d, [rbp+50h+var_C8]
0x1800aecb3  xor     r12d, r12d
0x1800aecb6  cmp     [rbx+3Ch], r12b
0x1800aecba  mov     r8, [rbp+50h+var_C0]
0x1800aecbe  mov     [rsp+150h+var_120], rax
0x1800aecc3  cmovz   r13, r10
0x1800aecc7  mov     [rsp+150h+var_128], ecx
0x1800aeccb  mov     rdx, r13
0x1800aecce  mov     ecx, [rbp+50h+var_CC]
0x1800aecd1  mov     [rsp+150h+var_130], r15
0x1800aecd6  call    Windows__Internal___anonymous_namespace___CDimmingWindow__CreateOnDesktop
0x1800aecdb  lea     edx, [r12+4]; uCmd
0x1800aece0  mov     rcx, rax; hWnd
0x1800aece3  mov     rdi, rax
0x1800aece6  call    cs:__imp_GetWindow
0x1800aeced  nop     dword ptr [rax+rax+00h]
0x1800aecf2  mov     [rbx+30h], rax
0x1800aecf6  jmp     loc_1800AEE4A
0x1800aecfb  mov     ecx, esi
0x1800aecfd  xor     r12d, r12d
0x1800aed00  and     ecx, 20000000h
0x1800aed06  mov     eax, 80000000h
0x1800aed0b  cmp     [rbx+3Dh], r12b
0x1800aed0f  jnz     short loc_1800AED28
0x1800aed11  bt      esi, 15h
0x1800aed15  jb      short loc_1800AED28
0x1800aed17  cmp     [rbx+3Ch], r12b
0x1800aed1b  mov     eax, 80C00000h
0x1800aed20  mov     edx, 80C80000h
0x1800aed25  cmovnz  eax, edx
0x1800aed28  mov     edi, eax
0x1800aed2a  mov     rsi, r12
0x1800aed2d  or      edi, 0CA0000h
0x1800aed33  test    ecx, ecx
0x1800aed35  cmovz   edi, eax
0x1800aed38  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800aed3f  nop     dword ptr [rax+rax+00h]
0x1800aed44  mov     rcx, rax
0x1800aed47  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x1800aed4e  call    cs:__imp_AreDpiAwarenessContextsEqual
0x1800aed55  nop     dword ptr [rax+rax+00h]
0x1800aed5a  test    eax, eax
0x1800aed5c  jz      short loc_1800AED74
0x1800aed5e  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x1800aed65  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800aed6c  nop     dword ptr [rax+rax+00h]
0x1800aed71  mov     rsi, rax
0x1800aed74  mov     ecx, 80000000h
0x1800aed79  mov     r9d, ecx
0x1800aed7c  mov     edx, ecx
0x1800aed7e  mov     r8d, ecx
0x1800aed81  test    r14, r14
0x1800aed84  jz      short loc_1800AEDB9
0x1800aed86  cmp     [rbx+3Eh], r12b
0x1800aed8a  jz      short loc_1800AEDB9
0x1800aed8c  xorps   xmm0, xmm0
0x1800aed8f  lea     rdx, [rbp+50h+Rect]; lpRect
0x1800aed93  mov     rcx, r14; hWnd
0x1800aed96  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x1800aed9a  call    cs:__imp_GetWindowRect
0x1800aeda1  nop     dword ptr [rax+rax+00h]
0x1800aeda6  mov     edx, [rbp+50h+Rect.right]
0x1800aeda9  mov     ecx, [rbp+50h+Rect.left]
0x1800aedac  sub     edx, ecx
0x1800aedae  mov     r8d, [rbp+50h+Rect.bottom]
0x1800aedb2  mov     r9d, [rbp+50h+Rect.top]
0x1800aedb6  sub     r8d, r9d
0x1800aedb9  mov     eax, [rbp+50h+var_D0]
0x1800aedbc  lea     r10, aShellDialog; "Shell_Dialog"
0x1800aedc3  cmp     [rbx+3Ch], r12b
0x1800aedc7  cmovz   r13, r10
0x1800aedcb  mov     r10d, dword ptr [rsp+150h+var_D8]
0x1800aedd0  mov     [rsp+150h+var_E8], r10d
0x1800aedd5  mov     [rsp+150h+var_F0], eax
0x1800aedd9  lea     rax, __ImageBase
0x1800aede0  mov     [rsp+150h+var_F8], r12
0x1800aede5  mov     [rsp+150h+var_100], rax
0x1800aedea  mov     [rsp+150h+var_108], r12
0x1800aedef  mov     [rsp+150h+var_110], r15
0x1800aedf4  mov     [rsp+150h+var_118], r8d
0x1800aedf9  mov     r8, [rbp+50h+var_C0]
0x1800aedfd  mov     dword ptr [rsp+150h+var_120], edx
0x1800aee01  mov     rdx, r13
0x1800aee04  mov     [rsp+150h+var_128], r9d
0x1800aee09  mov     r9d, edi
0x1800aee0c  mov     dword ptr [rsp+150h+var_130], ecx
0x1800aee10  mov     ecx, [rbp+50h+var_CC]
0x1800aee13  call    cs:__imp_CreateWindowInBandEx
0x1800aee1a  nop     dword ptr [rax+rax+00h]
0x1800aee1f  mov     rdi, rax
0x1800aee22  test    rsi, rsi
0x1800aee25  jz      short loc_1800AEE3A
0x1800aee27  mov     rcx, 0FFFFFFFFFFFFFFFDh
0x1800aee2e  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800aee35  nop     dword ptr [rax+rax+00h]
0x1800aee3a  cmp     [rbx+3Dh], r12b
0x1800aee3e  jz      short loc_1800AEE4A
0x1800aee40  mov     dl, 1; bool
0x1800aee42  mov     rcx, rdi; HWND
0x1800aee45  call    ?_SetWindowVisualPolicy@DialogWindowTrait@Internal@Windows@@CAXPEAUHWND__@@_N@Z; Windows::Internal::DialogWindowTrait::_SetWindowVisualPolicy(HWND__ *,bool)
0x1800aee4a  test    rdi, rdi
0x1800aee4d  jz      loc_1800AEEF4
0x1800aee53  mov     [rbx+8], r15
0x1800aee57  cmp     [rsp+150h+var_E0], r12b
0x1800aee5c  jz      short loc_1800AEEA8
0x1800aee5e  cmp     [rbx+30h], r12
0x1800aee62  mov     rsi, rdi
0x1800aee65  mov     rcx, rbx; this
0x1800aee68  cmovnz  rsi, [rbx+30h]
0x1800aee6d  call    ?_EnsureBroker@DialogWindowTrait@Internal@Windows@@AEAAJXZ; Windows::Internal::DialogWindowTrait::_EnsureBroker(void)
0x1800aee72  test    eax, eax
0x1800aee74  js      short loc_1800AEEA8
0x1800aee76  mov     rcx, [rbx+28h]
0x1800aee7a  mov     r8, r14
0x1800aee7d  mov     rdx, rsi
0x1800aee80  mov     rax, [rcx]
0x1800aee83  mov     rax, [rax+18h]
0x1800aee87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aee8c  test    eax, eax
0x1800aee8e  js      short loc_1800AEEA8
0x1800aee90  mov     edx, 4; uCmd
0x1800aee95  mov     rcx, rsi; hWnd
0x1800aee98  call    cs:__imp_GetWindow
0x1800aee9f  nop     dword ptr [rax+rax+00h]
0x1800aeea4  mov     [rbx+8], rax
0x1800aeea8  mov     r8d, 1; hData
0x1800aeeae  lea     rdx, aShellDialogWin; "Shell_Dialog_Window_Prop"
0x1800aeeb5  mov     rcx, rdi; hWnd
0x1800aeeb8  call    cs:__imp_SetPropW
0x1800aeebf  nop     dword ptr [rax+rax+00h]
0x1800aeec4  test    dword ptr [rbx+10h], 4000h
0x1800aeecb  jz      short loc_1800AEED7
0x1800aeecd  mov     rdx, rdi; HWND
0x1800aeed0  mov     cl, 1; bool
0x1800aeed2  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x1800aeed7  xor     r9d, r9d; lParam
0x1800aeeda  mov     edx, 127h; Msg
0x1800aeedf  mov     r8d, 30001h; wParam
0x1800aeee5  mov     rcx, rdi; hWnd
0x1800aeee8  call    cs:__imp_SendMessageW
0x1800aeeef  nop     dword ptr [rax+rax+00h]
0x1800aeef4  mov     rax, rdi
0x1800aeef7  mov     rcx, [rbp+50h+var_50]
0x1800aeefb  xor     rcx, rsp; StackCookie
0x1800aeefe  call    __security_check_cookie
0x1800aef03  add     rsp, 118h
0x1800aef0a  pop     r15
0x1800aef0c  pop     r14
0x1800aef0e  pop     r13
0x1800aef10  pop     r12
0x1800aef12  pop     rdi
0x1800aef13  pop     rsi
0x1800aef14  pop     rbx
0x1800aef15  pop     rbp
0x1800aef16  retn
```
