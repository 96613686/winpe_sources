# ATL::CAxHostWindow::ReleaseDC(HDC__ *)

- ea: `0x1800190a0`
- end: `0x180019164`
- name: `?ReleaseDC@CAxHostWindow@ATL@@UEAAJPEAUHDC__@@@Z`
- size: `196`
- prototype: `int(ATL::CAxHostWindow *__hidden this, HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002da0`
- `0x1800190a0`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001912c`
- `GDI32!DeleteDC` at `0x18001912c`
- `GDI32!BitBlt` at `0x180019123`
- `GDI32!BitBlt` at `0x180019123`
- `USER32!GetClientRect` at `0x1800190e0`
- `USER32!GetClientRect` at `0x1800190e0`
- `USER32!ReleaseDC` at `0x18001913d`
- `USER32!ReleaseDC` at `0x18001913d`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::ReleaseDC(ATL::CAxHostWindow *this, HDC a2)
{
  bool v2; // zf
  HWND v5; // rcx
  struct tagRECT Rect; // [rsp+50h] [rbp-28h] BYREF

  v2 = *((_QWORD *)this + 11) == 0;
  *((_BYTE *)this + 96) = 1;
  if ( !v2 )
  {
    v5 = (HWND)*((_QWORD *)this - 10);
    Rect = 0;
    GetClientRect(v5, &Rect);
    BitBlt(
      *((HDC *)this + 11),
      Rect.left,
      Rect.top,
      Rect.right - Rect.left,
      Rect.bottom - Rect.top,
      a2,
      0,
      0,
      0xCC0020u);
    DeleteDC(a2);
    a2 = (HDC)*((_QWORD *)this + 11);
  }
  ReleaseDC(*((HWND *)this - 10), a2);
  return 0;
}

```

## disassembly

```asm
0x1800190a0  mov     [rsp+arg_10], rbx
0x1800190a5  mov     [rsp+arg_18], rsi
0x1800190aa  push    rdi
0x1800190ab  sub     rsp, 70h
0x1800190af  mov     rax, cs:__security_cookie
0x1800190b6  xor     rax, rsp
0x1800190b9  mov     [rsp+78h+var_18], rax
0x1800190be  cmp     qword ptr [rcx+58h], 0
0x1800190c3  mov     rsi, rdx
0x1800190c6  mov     rdi, rcx
0x1800190c9  mov     byte ptr [rcx+60h], 1
0x1800190cd  jz      short loc_180019136
0x1800190cf  mov     rcx, [rcx-50h]; hWnd
0x1800190d3  lea     rdx, [rsp+78h+Rect]; lpRect
0x1800190d8  xorps   xmm0, xmm0
0x1800190db  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x1800190e0  call    cs:__imp_GetClientRect
0x1800190e6  mov     eax, [rsp+78h+Rect.bottom]
0x1800190ea  mov     r8d, [rsp+78h+Rect.top]; y
0x1800190ef  sub     eax, r8d
0x1800190f2  mov     r9d, [rsp+78h+Rect.right]
0x1800190f7  mov     edx, [rsp+78h+Rect.left]; x
0x1800190fb  sub     r9d, edx; cx
0x1800190fe  mov     rcx, [rdi+58h]; hdc
0x180019102  mov     [rsp+78h+rop], 0CC0020h; rop
0x18001910a  mov     [rsp+78h+y1], 0; y1
0x180019112  mov     [rsp+78h+x1], 0; x1
0x18001911a  mov     [rsp+78h+hdcSrc], rsi; hdcSrc
0x18001911f  mov     [rsp+78h+cy], eax; cy
0x180019123  call    cs:__imp_BitBlt
0x180019129  mov     rcx, rsi; hdc
0x18001912c  call    cs:__imp_DeleteDC
0x180019132  mov     rsi, [rdi+58h]
0x180019136  mov     rcx, [rdi-50h]; hWnd
0x18001913a  mov     rdx, rsi; hDC
0x18001913d  call    cs:__imp_ReleaseDC
0x180019143  xor     eax, eax
0x180019145  mov     rcx, [rsp+78h+var_18]
0x18001914a  xor     rcx, rsp; StackCookie
0x18001914d  call    __security_check_cookie
0x180019152  lea     r11, [rsp+78h+var_8]
0x180019157  mov     rbx, [r11+20h]
0x18001915b  mov     rsi, [r11+28h]
0x18001915f  mov     rsp, r11
0x180019162  pop     rdi
0x180019163  retn
```
