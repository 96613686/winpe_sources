# CTrayClock::_MoveWnd(HWND__ *)

- ea: `0x18001fae0`
- end: `0x18001fd03`
- name: `?_MoveWnd@CTrayClock@@AEAAJPEAUHWND__@@@Z`
- size: `547`
- prototype: `int(CTrayClock *__hidden this, HWND)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001fd0c`
- `0x18001ff04`
- `0x1800202f0`
- `0x180020410`

## callees

- `0x18001fae0`
- `0x180028f60`

## import_xrefs

- `USER32!InflateRect` at `0x18001fc00`
- `USER32!InflateRect` at `0x18001fc00`
- `USER32!PtInRect` at `0x18001fbaa`
- `USER32!PtInRect` at `0x18001fbaa`
- `USER32!GetCursorPos` at `0x18001fb9c`
- `USER32!GetCursorPos` at `0x18001fb9c`
- `USER32!AdjustWindowRectEx` at `0x18001fb39`
- `USER32!AdjustWindowRectEx` at `0x18001fb39`
- `USER32!FindWindowW` at `0x18001fc37`
- `USER32!FindWindowW` at `0x18001fc37`
- `USER32!SetWindowPos` at `0x18001fccc`
- `USER32!SetWindowPos` at `0x18001fccc`
- `USER32!GetWindowRect` at `0x18001fbe9`
- `USER32!GetWindowRect` at `0x18001fc4c`
- `USER32!GetWindowRect` at `0x18001fbe9`
- `USER32!GetWindowRect` at `0x18001fc4c`
- `USER32!GetWindowBand` at `0x18001fc68`
- `USER32!GetWindowBand` at `0x18001fc68`
- `USER32!CalculatePopupWindowPosition` at `0x18001fc95`
- `USER32!CalculatePopupWindowPosition` at `0x18001fc95`
- `SHELL32!Shell_NotifyIconGetRect` at `0x18001fb80`
- `SHELL32!Shell_NotifyIconGetRect` at `0x18001fb80`

## pseudocode

```c
__int64 __fastcall CTrayClock::_MoveWnd(const RECT *this, HWND a2)
{
  int v2; // ebx
  unsigned int v5; // esi
  UINT v6; // edi
  struct tagRECT *v7; // r12
  HWND WindowW; // rax
  HWND v9; // r14
  int v11; // [rsp+40h] [rbp-49h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-41h] BYREF
  RECT iconLocation; // [rsp+50h] [rbp-39h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-29h] BYREF
  struct tagRECT rc; // [rsp+70h] [rbp-19h] BYREF
  struct tagRECT v16; // [rsp+80h] [rbp-9h] BYREF
  NOTIFYICONIDENTIFIER identifier; // [rsp+90h] [rbp+7h] BYREF

  v2 = 0;
  if ( a2 == *(HWND *)&this[1].left )
  {
    if ( this[5].left )
    {
      Rect = 0;
      if ( AdjustWindowRectEx(&Rect, 0x40000u, 0, 0) )
      {
        *((_DWORD *)&identifier.guidItem + 4) = 0;
        *(_OWORD *)(&identifier.cbSize + 1) = 0;
        v2 = (Rect.right - Rect.left) / 2;
        identifier.cbSize = 40;
        identifier.guidItem = GUID_ShellNotifyTaskbarOffset;
        iconLocation = 0;
        if ( Shell_NotifyIconGetRect(&identifier, &iconLocation) >= 0 )
          v2 = iconLocation.bottom + v2 - iconLocation.top;
      }
    }
  }
  Point = 0;
  GetCursorPos(&Point);
  if ( !PtInRect(this + 3, Point) )
  {
    Point.x = this[3].right - (this[3].right - this[3].left) / 2;
    Point.y = this[3].bottom - (this[3].bottom - this[3].top) / 2;
  }
  v5 = -2147467259;
  rc = 0;
  if ( GetWindowRect(a2, &rc) )
  {
    InflateRect(&rc, v2, v2);
    Rect.left = rc.right - rc.left;
    v6 = 65556;
    Rect.top = rc.bottom - rc.top;
    v7 = 0;
    iconLocation = 0;
    v16 = 0;
    WindowW = FindWindowW(L"Shell_TrayWnd", 0);
    v9 = WindowW;
    if ( WindowW )
    {
      if ( GetWindowRect(WindowW, &v16) )
      {
        v11 = 0;
        v7 = &v16;
        if ( (unsigned int)GetWindowBand(v9, &v11) )
        {
          if ( v11 != 1 )
            v6 = 20;
        }
      }
    }
    if ( CalculatePopupWindowPosition(&Point, (const SIZE *)&Rect, v6, v7, &iconLocation)
      && SetWindowPos(a2, HWND_MESSAGE|0x2LL, v2 + iconLocation.left, v2 + iconLocation.top, 0, 0, 0x11u) )
    {
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001fae0  mov     [rsp-8+arg_10], rbx
0x18001fae5  mov     [rsp-8+arg_18], rsi
0x18001faea  push    rbp
0x18001faeb  push    rdi
0x18001faec  push    r12
0x18001faee  push    r14
0x18001faf0  push    r15
0x18001faf2  lea     rbp, [rsp-37h]
0x18001faf7  sub     rsp, 0C0h
0x18001fafe  mov     rax, cs:__security_cookie
0x18001fb05  xor     rax, rsp
0x18001fb08  mov     [rbp+57h+var_28], rax
0x18001fb0c  xor     ebx, ebx
0x18001fb0e  mov     r15, rdx
0x18001fb11  mov     rdi, rcx
0x18001fb14  lea     r14d, [rbx+2]
0x18001fb18  cmp     rdx, [rcx+10h]
0x18001fb1c  jnz     short loc_18001FB90
0x18001fb1e  cmp     [rcx+50h], ebx
0x18001fb21  jz      short loc_18001FB90
0x18001fb23  xorps   xmm0, xmm0
0x18001fb26  lea     rcx, [rbp+57h+Rect]; lpRect
0x18001fb2a  xor     r9d, r9d; dwExStyle
0x18001fb2d  xor     r8d, r8d; bMenu
0x18001fb30  mov     edx, 40000h; dwStyle
0x18001fb35  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18001fb39  call    cs:__imp_AdjustWindowRectEx
0x18001fb3f  test    eax, eax
0x18001fb41  jz      short loc_18001FB90
0x18001fb43  mov     eax, [rbp+57h+Rect.right]
0x18001fb46  lea     rcx, [rbp+57h+identifier]; identifier
0x18001fb4a  sub     eax, [rbp+57h+Rect.left]
0x18001fb4d  xorps   xmm0, xmm0
0x18001fb50  cdq
0x18001fb51  mov     dword ptr [rbp+57h+identifier+24h], 0
0x18001fb58  idiv    r14d
0x18001fb5b  movdqu  xmmword ptr [rbp+57h+identifier+4], xmm0
0x18001fb60  lea     rdx, [rbp+57h+iconLocation]; iconLocation
0x18001fb64  mov     ebx, eax
0x18001fb66  movups  xmm0, xmmword ptr cs:GUID_ShellNotifyTaskbarOffset.Data1
0x18001fb6d  mov     [rbp+57h+identifier.cbSize], 28h ; '('
0x18001fb74  movdqu  xmmword ptr [rbp+57h+identifier.guidItem.Data1], xmm0
0x18001fb79  xorps   xmm0, xmm0
0x18001fb7c  movups  xmmword ptr [rbp+57h+iconLocation.left], xmm0
0x18001fb80  call    cs:__imp_Shell_NotifyIconGetRect
0x18001fb86  test    eax, eax
0x18001fb88  js      short loc_18001FB90
0x18001fb8a  sub     ebx, [rbp+57h+iconLocation.top]
0x18001fb8d  add     ebx, [rbp+57h+iconLocation.bottom]
0x18001fb90  lea     rcx, [rbp+57h+Point]; lpPoint
0x18001fb94  mov     qword ptr [rbp+57h+Point.x], 0
0x18001fb9c  call    cs:__imp_GetCursorPos
0x18001fba2  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x18001fba6  lea     rcx, [rdi+30h]; lprc
0x18001fbaa  call    cs:__imp_PtInRect
0x18001fbb0  test    eax, eax
0x18001fbb2  jnz     short loc_18001FBD6
0x18001fbb4  mov     ecx, [rdi+38h]
0x18001fbb7  mov     eax, ecx
0x18001fbb9  sub     eax, [rdi+30h]
0x18001fbbc  cdq
0x18001fbbd  idiv    r14d
0x18001fbc0  sub     ecx, eax
0x18001fbc2  mov     [rbp+57h+Point.x], ecx
0x18001fbc5  mov     ecx, [rdi+3Ch]
0x18001fbc8  mov     eax, ecx
0x18001fbca  sub     eax, [rdi+34h]
0x18001fbcd  cdq
0x18001fbce  idiv    r14d
0x18001fbd1  sub     ecx, eax
0x18001fbd3  mov     [rbp+57h+Point.y], ecx
0x18001fbd6  xorps   xmm0, xmm0
0x18001fbd9  lea     rdx, [rbp+57h+rc]; lpRect
0x18001fbdd  mov     rcx, r15; hWnd
0x18001fbe0  mov     esi, 80004005h
0x18001fbe5  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18001fbe9  call    cs:__imp_GetWindowRect
0x18001fbef  test    eax, eax
0x18001fbf1  jz      loc_18001FCD9
0x18001fbf7  mov     r8d, ebx; dy
0x18001fbfa  lea     rcx, [rbp+57h+rc]; lprc
0x18001fbfe  mov     edx, ebx; dx
0x18001fc00  call    cs:__imp_InflateRect
0x18001fc06  mov     eax, [rbp+57h+rc.right]
0x18001fc09  lea     rcx, ClassName; "Shell_TrayWnd"
0x18001fc10  sub     eax, [rbp+57h+rc.left]
0x18001fc13  xorps   xmm0, xmm0
0x18001fc16  mov     [rbp+57h+Rect.left], eax
0x18001fc19  xorps   xmm1, xmm1
0x18001fc1c  mov     eax, [rbp+57h+rc.bottom]
0x18001fc1f  xor     edx, edx; lpWindowName
0x18001fc21  sub     eax, [rbp+57h+rc.top]
0x18001fc24  mov     edi, 10014h
0x18001fc29  mov     [rbp+57h+Rect.top], eax
0x18001fc2c  xor     r12d, r12d
0x18001fc2f  movups  xmmword ptr [rbp+57h+iconLocation.left], xmm0
0x18001fc33  movups  xmmword ptr [rbp+57h+var_60.left], xmm1
0x18001fc37  call    cs:__imp_FindWindowW
0x18001fc3d  mov     r14, rax
0x18001fc40  test    rax, rax
0x18001fc43  jz      short loc_18001FC7E
0x18001fc45  lea     rdx, [rbp+57h+var_60]; lpRect
0x18001fc49  mov     rcx, rax; hWnd
0x18001fc4c  call    cs:__imp_GetWindowRect
0x18001fc52  test    eax, eax
0x18001fc54  jz      short loc_18001FC7E
0x18001fc56  lea     rdx, [rbp+57h+var_A0]
0x18001fc5a  mov     [rbp+57h+var_A0], 0
0x18001fc61  mov     rcx, r14
0x18001fc64  lea     r12, [rbp+57h+var_60]
0x18001fc68  call    cs:__imp_GetWindowBand
0x18001fc6e  test    eax, eax
0x18001fc70  jz      short loc_18001FC7E
0x18001fc72  cmp     [rbp+57h+var_A0], 1
0x18001fc76  mov     eax, 14h
0x18001fc7b  cmovnz  edi, eax
0x18001fc7e  lea     rax, [rbp+57h+iconLocation]
0x18001fc82  mov     r9, r12; excludeRect
0x18001fc85  mov     r8d, edi; flags
0x18001fc88  mov     [rsp+0E0h+popupWindowPosition], rax; popupWindowPosition
0x18001fc8d  lea     rdx, [rbp+57h+Rect]; windowSize
0x18001fc91  lea     rcx, [rbp+57h+Point]; anchorPoint
0x18001fc95  call    cs:__imp_CalculatePopupWindowPosition
0x18001fc9b  test    eax, eax
0x18001fc9d  jz      short loc_18001FCD9
0x18001fc9f  mov     r9d, [rbp+57h+iconLocation.top]
0x18001fca3  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18001fca7  mov     r8d, [rbp+57h+iconLocation.left]
0x18001fcab  add     r9d, ebx; Y
0x18001fcae  mov     [rsp+0E0h+uFlags], 11h; uFlags
0x18001fcb6  add     r8d, ebx; X
0x18001fcb9  mov     [rsp+0E0h+cy], 0; cy
0x18001fcc1  mov     rcx, r15; hWnd
0x18001fcc4  mov     dword ptr [rsp+0E0h+popupWindowPosition], 0; cx
0x18001fccc  call    cs:__imp_SetWindowPos
0x18001fcd2  xor     ecx, ecx
0x18001fcd4  test    eax, eax
0x18001fcd6  cmovnz  esi, ecx
0x18001fcd9  mov     eax, esi
0x18001fcdb  mov     rcx, [rbp+57h+var_28]
0x18001fcdf  xor     rcx, rsp; StackCookie
0x18001fce2  call    __security_check_cookie
0x18001fce7  lea     r11, [rsp+0E0h+var_20]
0x18001fcef  mov     rbx, [r11+40h]
0x18001fcf3  mov     rsi, [r11+48h]
0x18001fcf7  mov     rsp, r11
0x18001fcfa  pop     r15
0x18001fcfc  pop     r14
0x18001fcfe  pop     r12
0x18001fd00  pop     rdi
0x18001fd01  pop     rbp
0x18001fd02  retn
```
