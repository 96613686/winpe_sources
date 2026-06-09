# CDigitalClock::_MoveClockItem(HWND__ *,int)

- ea: `0x1800224a4`
- end: `0x18002253b`
- name: `?_MoveClockItem@CDigitalClock@@AEAAXPEAUHWND__@@H@Z`
- size: `151`
- prototype: `void(CDigitalClock *__hidden this, HWND, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180020d38`
- `0x180020dd4`
- `0x180022544`

## callees

- `0x1800224a4`
- `0x180028f60`

## import_xrefs

- `USER32!MoveWindow` at `0x180022520`
- `USER32!MoveWindow` at `0x180022520`
- `USER32!MapWindowPoints` at `0x1800224ee`
- `USER32!MapWindowPoints` at `0x1800224ee`
- `USER32!GetWindowRect` at `0x1800224d4`
- `USER32!GetWindowRect` at `0x1800224d4`

## pseudocode

```c
void __fastcall CDigitalClock::_MoveClockItem(HWND *this, HWND a2, int a3)
{
  struct tagRECT Rect; // [rsp+30h] [rbp-38h] BYREF

  Rect = 0;
  if ( GetWindowRect(a2, &Rect) )
  {
    MapWindowPoints(0, *this, (LPPOINT)&Rect, 2u);
    MoveWindow(a2, a3 + Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
  }
}

```

## disassembly

```asm
0x1800224a4  push    rbx
0x1800224a6  push    rsi
0x1800224a7  push    rdi
0x1800224a8  sub     rsp, 50h
0x1800224ac  mov     rax, cs:__security_cookie
0x1800224b3  xor     rax, rsp
0x1800224b6  mov     [rsp+68h+var_28], rax
0x1800224bb  mov     rbx, rdx
0x1800224be  mov     rdi, rcx
0x1800224c1  xorps   xmm0, xmm0
0x1800224c4  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800224c9  mov     rcx, rbx; hWnd
0x1800224cc  mov     esi, r8d
0x1800224cf  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800224d4  call    cs:__imp_GetWindowRect
0x1800224da  test    eax, eax
0x1800224dc  jz      short loc_180022526
0x1800224de  mov     rdx, [rdi]; hWndTo
0x1800224e1  lea     r8, [rsp+68h+Rect]; lpPoints
0x1800224e6  mov     r9d, 2; cPoints
0x1800224ec  xor     ecx, ecx; hWndFrom
0x1800224ee  call    cs:__imp_MapWindowPoints
0x1800224f4  mov     eax, [rsp+68h+Rect.left]
0x1800224f8  mov     rcx, rbx; hWnd
0x1800224fb  mov     r10d, [rsp+68h+Rect.bottom]
0x180022500  mov     r8d, [rsp+68h+Rect.top]; Y
0x180022505  sub     r10d, r8d
0x180022508  mov     r9d, [rsp+68h+Rect.right]
0x18002250d  lea     edx, [rsi+rax]; X
0x180022510  mov     [rsp+68h+bRepaint], 1; bRepaint
0x180022518  sub     r9d, eax; nWidth
0x18002251b  mov     [rsp+68h+nHeight], r10d; nHeight
0x180022520  call    cs:__imp_MoveWindow
0x180022526  mov     rcx, [rsp+68h+var_28]
0x18002252b  xor     rcx, rsp; StackCookie
0x18002252e  call    __security_check_cookie
0x180022533  add     rsp, 50h
0x180022537  pop     rdi
0x180022538  pop     rsi
0x180022539  pop     rbx
0x18002253a  retn
```
