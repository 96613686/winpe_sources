# ConvertWindowToDifferentClass(HWND__ *,int,wchar_t const *)

- ea: `0x180095ce8`
- end: `0x180095ec8`
- name: `?ConvertWindowToDifferentClass@@YAJPEAUHWND__@@HPEB_W@Z`
- size: `480`
- prototype: `__int64 __fastcall(HWND hWndParent, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180028000`

## callees

- `0x180081a38`
- `0x180095728`
- `0x180095a00`
- `0x180095ce8`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e76`
- `USER32!GetDlgItem` at `0x180095d28`
- `USER32!GetDlgItem` at `0x180095d4d`
- `USER32!GetDlgItem` at `0x180095d28`
- `USER32!GetDlgItem` at `0x180095d4d`
- `USER32!SendMessageW` at `0x180095d6b`
- `USER32!SendMessageW` at `0x180095e2c`
- `USER32!SendMessageW` at `0x180095d6b`
- `USER32!SendMessageW` at `0x180095e2c`
- `USER32!DestroyWindow` at `0x180095e65`
- `USER32!DestroyWindow` at `0x180095e65`
- `USER32!GetWindowLongW` at `0x180095d9a`
- `USER32!GetWindowLongW` at `0x180095da8`
- `USER32!GetWindowLongW` at `0x180095d9a`
- `USER32!GetWindowLongW` at `0x180095da8`
- `USER32!SetWindowPos` at `0x180095e5c`
- `USER32!SetWindowPos` at `0x180095e5c`
- `USER32!CreateWindowExW` at `0x180095e11`
- `USER32!CreateWindowExW` at `0x180095e11`

## string_xrefs

- `0x180095e0a`: `SysLink`

## pseudocode

```c
__int64 __fastcall ConvertWindowToDifferentClass(HWND hWndParent, __int64 a2, const wchar_t *a3)
{
  WCHAR *v3; // rsi
  HWND DlgItem; // rax
  signed int RelativeWindowRect; // ebx
  HWND v7; // rax
  HWND v8; // rdi
  WPARAM v9; // r15
  LONG WindowLongW; // ebx
  LONG v11; // eax
  int v12; // ebp
  HWND Window; // rax
  HWND v14; // rbx
  signed int LastError; // eax
  LPCWSTR lpWindowName; // [rsp+60h] [rbp-38h] BYREF
  struct tagPOINT Points[2]; // [rsp+68h] [rbp-30h] BYREF

  v3 = 0;
  lpWindowName = 0;
  *(_OWORD *)&Points[0].x = 0;
  DlgItem = GetDlgItem(hWndParent, 64407);
  RelativeWindowRect = GetRelativeWindowRect(DlgItem, Points);
  if ( RelativeWindowRect >= 0 )
  {
    v7 = GetDlgItem(hWndParent, 64407);
    v8 = v7;
    if ( !v7 )
      goto LABEL_10;
    v9 = SendMessageW(v7, 0x31u, 0, 0);
    if ( !v9 )
      goto LABEL_10;
    RelativeWindowRect = GetWindowTextAlloc(v8, (wchar_t **)&lpWindowName);
    if ( RelativeWindowRect < 0 )
    {
      v3 = (WCHAR *)lpWindowName;
      goto LABEL_14;
    }
    WindowLongW = GetWindowLongW(v8, -16);
    v11 = GetWindowLongW(v8, -20);
    v12 = WindowLongW & 0x10000000;
    if ( (WindowLongW & 0x10000000) != 0 )
      WindowLongW &= ~0x10000000u;
    v3 = (WCHAR *)lpWindowName;
    Window = CreateWindowExW(
               v11,
               L"SysLink",
               lpWindowName,
               WindowLongW,
               Points[0].x,
               Points[0].y,
               Points[1].x - Points[0].x,
               Points[1].y - Points[0].y,
               hWndParent,
               (HMENU)0xFB97,
               0,
               0);
    v14 = Window;
    if ( Window )
    {
      SendMessageW(Window, 0x30u, v9, 0);
      SetWindowPos(v14, v8, 0, 0, 0, 0, v12 != 0 ? 83 : 19);
      DestroyWindow(v8);
      RelativeWindowRect = 0;
    }
    else
    {
LABEL_10:
      LastError = GetLastError();
      RelativeWindowRect = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        RelativeWindowRect = LastError;
      if ( RelativeWindowRect >= 0 )
        RelativeWindowRect = -2147418113;
    }
  }
LABEL_14:
  SusFree(v3);
  return (unsigned int)RelativeWindowRect;
}

```

## disassembly

```asm
0x180095ce8  mov     r11, rsp
0x180095ceb  mov     [r11+10h], rbx
0x180095cef  mov     [r11+18h], rbp
0x180095cf3  mov     [r11+20h], rsi
0x180095cf7  push    rdi
0x180095cf8  push    r14
0x180095cfa  push    r15
0x180095cfc  sub     rsp, 80h
0x180095d03  mov     rax, cs:__security_cookie
0x180095d0a  xor     rax, rsp
0x180095d0d  mov     [rsp+98h+var_20], rax
0x180095d12  xorps   xmm0, xmm0
0x180095d15  xor     esi, esi
0x180095d17  mov     edx, 0FB97h; nIDDlgItem
0x180095d1c  mov     [r11-38h], rsi
0x180095d20  movups  xmmword ptr [rsp+98h+Points.x], xmm0
0x180095d25  mov     r14, rcx
0x180095d28  call    cs:__imp_GetDlgItem
0x180095d2e  mov     rcx, rax; hWnd
0x180095d31  lea     rdx, [rsp+98h+Points]; lpPoints
0x180095d36  call    ?GetRelativeWindowRect@@YAJPEAUHWND__@@PEAUtagRECT@@@Z; GetRelativeWindowRect(HWND__ *,tagRECT *)
0x180095d3b  mov     ebx, eax
0x180095d3d  test    eax, eax
0x180095d3f  js      loc_180095E94
0x180095d45  mov     edx, 0FB97h; nIDDlgItem
0x180095d4a  mov     rcx, r14; hDlg
0x180095d4d  call    cs:__imp_GetDlgItem
0x180095d53  mov     rdi, rax
0x180095d56  test    rax, rax
0x180095d59  jz      loc_180095E76
0x180095d5f  xor     r9d, r9d; lParam
0x180095d62  lea     edx, [rsi+31h]; Msg
0x180095d65  xor     r8d, r8d; wParam
0x180095d68  mov     rcx, rax; hWnd
0x180095d6b  call    cs:__imp_SendMessageW
0x180095d71  mov     r15, rax
0x180095d74  test    rax, rax
0x180095d77  jz      loc_180095E76
0x180095d7d  lea     rdx, [rsp+98h+lpWindowName]; wchar_t **
0x180095d82  mov     rcx, rdi; hWnd
0x180095d85  call    ?GetWindowTextAlloc@@YAJPEAUHWND__@@PEAPEA_W@Z; GetWindowTextAlloc(HWND__ *,wchar_t * *)
0x180095d8a  mov     ebx, eax
0x180095d8c  test    eax, eax
0x180095d8e  js      loc_180095E6F
0x180095d94  lea     edx, [rsi-10h]; nIndex
0x180095d97  mov     rcx, rdi; hWnd
0x180095d9a  call    cs:__imp_GetWindowLongW
0x180095da0  lea     edx, [rsi-14h]; nIndex
0x180095da3  mov     rcx, rdi; hWnd
0x180095da6  mov     ebx, eax
0x180095da8  call    cs:__imp_GetWindowLongW
0x180095dae  mov     ebp, ebx
0x180095db0  and     ebp, 10000000h
0x180095db6  jz      short loc_180095DBC
0x180095db8  btr     ebx, 1Ch
0x180095dbc  mov     r9d, [rsp+98h+Points.y]
0x180095dc1  mov     edx, [rsp+98h+Points.x]
0x180095dc5  mov     r8d, [rsp+98h+Points.y+8]
0x180095dca  mov     ecx, [rsp+98h+Points.x+8]
0x180095dce  sub     r8d, r9d
0x180095dd1  mov     [rsp+98h+lpParam], rsi; lpParam
0x180095dd6  sub     ecx, edx
0x180095dd8  mov     [rsp+98h+hInstance], rsi; hInstance
0x180095ddd  mov     rsi, [rsp+98h+lpWindowName]
0x180095de2  mov     [rsp+98h+hMenu], 0FB97h; hMenu
0x180095deb  mov     [rsp+98h+hWndParent], r14; hWndParent
0x180095df0  mov     [rsp+98h+nHeight], r8d; nHeight
0x180095df5  mov     r8, rsi; lpWindowName
0x180095df8  mov     [rsp+98h+nWidth], ecx; nWidth
0x180095dfc  mov     ecx, eax; dwExStyle
0x180095dfe  mov     [rsp+98h+Y], r9d; Y
0x180095e03  mov     r9d, ebx; dwStyle
0x180095e06  mov     [rsp+98h+X], edx; X
0x180095e0a  lea     rdx, ClassName; "SysLink"
0x180095e11  call    cs:__imp_CreateWindowExW
0x180095e17  mov     rbx, rax
0x180095e1a  test    rax, rax
0x180095e1d  jz      short loc_180095E76
0x180095e1f  xor     r9d, r9d; lParam
0x180095e22  mov     r8, r15; wParam
0x180095e25  mov     rcx, rax; hWnd
0x180095e28  lea     edx, [r9+30h]; Msg
0x180095e2c  call    cs:__imp_SendMessageW
0x180095e32  neg     ebp
0x180095e34  mov     rdx, rdi; hWndInsertAfter
0x180095e37  sbb     ecx, ecx
0x180095e39  xor     r9d, r9d; Y
0x180095e3c  and     ecx, 40h
0x180095e3f  xor     r8d, r8d; X
0x180095e42  add     ecx, 13h
0x180095e45  mov     [rsp+98h+nWidth], ecx; uFlags
0x180095e49  mov     rcx, rbx; hWnd
0x180095e4c  mov     [rsp+98h+Y], 0; cy
0x180095e54  mov     [rsp+98h+X], 0; cx
0x180095e5c  call    cs:__imp_SetWindowPos
0x180095e62  mov     rcx, rdi; hWnd
0x180095e65  call    cs:__imp_DestroyWindow
0x180095e6b  xor     ebx, ebx
0x180095e6d  jmp     short loc_180095E94
0x180095e6f  mov     rsi, [rsp+98h+lpWindowName]
0x180095e74  jmp     short loc_180095E94
0x180095e76  call    cs:__imp_GetLastError
0x180095e7c  movzx   ebx, ax
0x180095e7f  or      ebx, 80070000h
0x180095e85  test    eax, eax
0x180095e87  cmovle  ebx, eax
0x180095e8a  mov     eax, 8000FFFFh
0x180095e8f  test    ebx, ebx
0x180095e91  cmovns  ebx, eax
0x180095e94  mov     rcx, rsi; lpMem
0x180095e97  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180095e9c  mov     eax, ebx
0x180095e9e  mov     rcx, [rsp+98h+var_20]
0x180095ea3  xor     rcx, rsp; StackCookie
0x180095ea6  call    __security_check_cookie
0x180095eab  lea     r11, [rsp+98h+var_18]
0x180095eb3  mov     rbx, [r11+28h]
0x180095eb7  mov     rbp, [r11+30h]
0x180095ebb  mov     rsi, [r11+38h]
0x180095ebf  mov     rsp, r11
0x180095ec2  pop     r15
0x180095ec4  pop     r14
0x180095ec6  pop     rdi
0x180095ec7  retn
```
