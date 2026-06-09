# CDigitalClock::_CreateDigitalClock(HWND__ *)

- ea: `0x180021310`
- end: `0x18002149d`
- name: `?_CreateDigitalClock@CDigitalClock@@AEAAHPEAUHWND__@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(CDigitalClock *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023070`

## callees

- `0x180020d38`
- `0x180021310`
- `0x1800214a4`
- `0x180022114`
- `0x1800222a8`
- `0x180022b98`
- `0x180022e80`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002144d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002144d`
- `USER32!GetClientRect` at `0x1800213a7`
- `USER32!GetClientRect` at `0x1800213a7`
- `USER32!CreateWindowExW` at `0x1800213fa`
- `USER32!CreateWindowExW` at `0x1800213fa`
- `USER32!SetWindowLongPtrW` at `0x18002145e`
- `USER32!SetWindowLongPtrW` at `0x18002145e`
- `USER32!GetParent` at `0x18002136f`
- `USER32!GetParent` at `0x18002136f`
- `USER32!GetWindowLongW` at `0x18002133d`
- `USER32!GetWindowLongW` at `0x180021437`
- `USER32!GetWindowLongW` at `0x18002133d`
- `USER32!GetWindowLongW` at `0x180021437`

## pseudocode

```c
__int64 __fastcall CDigitalClock::_CreateDigitalClock(CDigitalClock *this, HWND hWnd)
{
  char WindowLongW; // al
  CDigitalClock *v5; // rcx
  unsigned int EditableDigitalClock; // edi
  HWND Window; // rax
  bool v8; // zf
  struct tagRECT Rect; // [rsp+60h] [rbp-38h] BYREF

  WindowLongW = GetWindowLongW(hWnd, -16);
  *((_QWORD *)this + 11) = 0;
  if ( (WindowLongW & 2) == 0 )
  {
    if ( (WindowLongW & 8) == 0 )
      goto LABEL_5;
    *((_DWORD *)this + 23) = 1;
  }
  *((_DWORD *)this + 22) = 1;
LABEL_5:
  if ( (WindowLongW & 0x10) != 0 )
    *((_DWORD *)this + 25) = 1;
  *(_QWORD *)this = hWnd;
  *((_QWORD *)this + 1) = GetParent(hWnd);
  if ( !CDigitalClock::_s_Settings )
    CDigitalClock::_InitializeCommonSettings(v5);
  CDigitalClock::_SetDefaultFont(this);
  if ( *((_DWORD *)this + 22) )
  {
    EditableDigitalClock = 0;
    Rect = 0;
    if ( !GetClientRect(hWnd, &Rect) )
      return EditableDigitalClock;
    Window = CreateWindowExW(
               0,
               L"STATIC",
               0,
               0x50000001u,
               0,
               0,
               Rect.right,
               Rect.bottom,
               hWnd,
               0,
               CDigitalClock::s_hInst,
               0);
    *((_QWORD *)this + 2) = Window;
    v8 = Window == 0;
  }
  else
  {
    EditableDigitalClock = CDigitalClock::_CreateEditableDigitalClock(this);
    v8 = EditableDigitalClock == 0;
  }
  if ( !v8 )
  {
    CDigitalClock::_SetFont(this, 0);
    CDigitalClock::_InitializeSettings(this);
    if ( !*((_DWORD *)this + 22) && (GetWindowLongW(hWnd, -20) & 0x400000) != 0 )
      CDigitalClock::_AdjustForRTL(this);
    SetLastError(0);
    return SetWindowLongPtrW(hWnd, -21, (LONG_PTR)this) || !GetLastError();
  }
  return EditableDigitalClock;
}

```

## disassembly

```asm
0x180021310  mov     [rsp+arg_10], rbx
0x180021315  push    rsi
0x180021316  push    rdi
0x180021317  push    r14
0x180021319  sub     rsp, 80h
0x180021320  mov     rax, cs:__security_cookie
0x180021327  xor     rax, rsp
0x18002132a  mov     [rsp+98h+var_28], rax
0x18002132f  mov     rsi, rdx
0x180021332  mov     rbx, rcx
0x180021335  mov     rcx, rsi; hWnd
0x180021338  mov     edx, 0FFFFFFF0h; nIndex
0x18002133d  call    cs:__imp_GetWindowLongW
0x180021343  mov     qword ptr [rbx+58h], 0
0x18002134b  mov     r14d, 1
0x180021351  test    al, 2
0x180021353  jnz     short loc_18002135D
0x180021355  test    al, 8
0x180021357  jz      short loc_180021361
0x180021359  mov     [rbx+5Ch], r14d
0x18002135d  mov     [rbx+58h], r14d
0x180021361  test    al, 10h
0x180021363  jz      short loc_180021369
0x180021365  mov     [rbx+64h], r14d
0x180021369  mov     rcx, rsi; hWnd
0x18002136c  mov     [rbx], rsi
0x18002136f  call    cs:__imp_GetParent
0x180021375  mov     [rbx+8], rax
0x180021379  cmp     cs:?_s_Settings@CDigitalClock@@0UDIGITALCLOCKCOMMONSETTINGS@@A, 0; DIGITALCLOCKCOMMONSETTINGS CDigitalClock::_s_Settings
0x180021380  jnz     short loc_180021387
0x180021382  call    ?_InitializeCommonSettings@CDigitalClock@@AEAAXXZ; CDigitalClock::_InitializeCommonSettings(void)
0x180021387  mov     rcx, rbx; this
0x18002138a  call    ?_SetDefaultFont@CDigitalClock@@AEAAXXZ; CDigitalClock::_SetDefaultFont(void)
0x18002138f  cmp     dword ptr [rbx+58h], 0
0x180021393  jz      short loc_180021409
0x180021395  xorps   xmm0, xmm0
0x180021398  lea     rdx, [rsp+98h+Rect]; lpRect
0x18002139d  mov     rcx, rsi; hWnd
0x1800213a0  xor     edi, edi
0x1800213a2  movups  xmmword ptr [rsp+98h+Rect.left], xmm0
0x1800213a7  call    cs:__imp_GetClientRect
0x1800213ad  test    eax, eax
0x1800213af  jz      loc_18002147A
0x1800213b5  mov     rax, cs:?s_hInst@CDigitalClock@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * CDigitalClock::s_hInst
0x1800213bc  lea     rdx, aStatic; "STATIC"
0x1800213c3  mov     [rsp+98h+lpParam], rdi; lpParam
0x1800213c8  mov     r9d, 50000001h; dwStyle
0x1800213ce  mov     [rsp+98h+hInstance], rax; hInstance
0x1800213d3  xor     r8d, r8d; lpWindowName
0x1800213d6  mov     eax, [rsp+98h+Rect.bottom]
0x1800213da  xor     ecx, ecx; dwExStyle
0x1800213dc  mov     [rsp+98h+hMenu], rdi; hMenu
0x1800213e1  mov     [rsp+98h+hWndParent], rsi; hWndParent
0x1800213e6  mov     [rsp+98h+nHeight], eax; nHeight
0x1800213ea  mov     eax, [rsp+98h+Rect.right]
0x1800213ee  mov     [rsp+98h+nWidth], eax; nWidth
0x1800213f2  mov     [rsp+98h+Y], edi; Y
0x1800213f6  mov     [rsp+98h+X], edi; X
0x1800213fa  call    cs:__imp_CreateWindowExW
0x180021400  mov     [rbx+10h], rax
0x180021404  test    rax, rax
0x180021407  jmp     short loc_180021415
0x180021409  mov     rcx, rbx; this
0x18002140c  call    ?_CreateEditableDigitalClock@CDigitalClock@@AEAAHXZ; CDigitalClock::_CreateEditableDigitalClock(void)
0x180021411  mov     edi, eax
0x180021413  test    eax, eax
0x180021415  jz      short loc_18002147A
0x180021417  xor     edx, edx; HFONT
0x180021419  mov     rcx, rbx; this
0x18002141c  call    ?_SetFont@CDigitalClock@@AEAAXPEAUHFONT__@@@Z; CDigitalClock::_SetFont(HFONT__ *)
0x180021421  mov     rcx, rbx; this
0x180021424  call    ?_InitializeSettings@CDigitalClock@@AEAAXXZ; CDigitalClock::_InitializeSettings(void)
0x180021429  cmp     dword ptr [rbx+58h], 0
0x18002142d  jnz     short loc_18002144B
0x18002142f  mov     edx, 0FFFFFFECh; nIndex
0x180021434  mov     rcx, rsi; hWnd
0x180021437  call    cs:__imp_GetWindowLongW
0x18002143d  bt      eax, 16h
0x180021441  jnb     short loc_18002144B
0x180021443  mov     rcx, rbx; this
0x180021446  call    ?_AdjustForRTL@CDigitalClock@@AEAAXXZ; CDigitalClock::_AdjustForRTL(void)
0x18002144b  xor     ecx, ecx; dwErrCode
0x18002144d  call    cs:__imp_SetLastError
0x180021453  mov     r8, rbx; dwNewLong
0x180021456  mov     edx, 0FFFFFFEBh; nIndex
0x18002145b  mov     rcx, rsi; hWnd
0x18002145e  call    cs:__imp_SetWindowLongPtrW
0x180021464  test    rax, rax
0x180021467  jnz     short loc_180021477
0x180021469  call    cs:__imp_GetLastError
0x18002146f  test    eax, eax
0x180021471  jz      short loc_180021477
0x180021473  xor     edi, edi
0x180021475  jmp     short loc_18002147A
0x180021477  mov     edi, r14d
0x18002147a  mov     eax, edi
0x18002147c  mov     rcx, [rsp+98h+var_28]
0x180021481  xor     rcx, rsp; StackCookie
0x180021484  call    __security_check_cookie
0x180021489  mov     rbx, [rsp+98h+arg_10]
0x180021491  add     rsp, 80h
0x180021498  pop     r14
0x18002149a  pop     rdi
0x18002149b  pop     rsi
0x18002149c  retn
```
