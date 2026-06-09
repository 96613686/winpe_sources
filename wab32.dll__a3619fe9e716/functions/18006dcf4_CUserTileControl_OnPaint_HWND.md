# CUserTileControl::_OnPaint(HWND__ *)

- ea: `0x18006dcf4`
- end: `0x18006de8f`
- name: `?_OnPaint@CUserTileControl@@AEAAXPEAUHWND__@@@Z`
- size: `411`
- prototype: `void(CUserTileControl *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006e264`

## callees

- `0x18006dcf4`
- `0x18006de98`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `GDI32!DeleteObject` at `0x18006de4c`
- `GDI32!DeleteObject` at `0x18006de4c`
- `GDI32!CreateDIBSection` at `0x18006ddcf`
- `GDI32!CreateDIBSection` at `0x18006ddcf`
- `GDI32!CreateCompatibleDC` at `0x18006dd5e`
- `GDI32!CreateCompatibleDC` at `0x18006dd5e`
- `GDI32!DeleteDC` at `0x18006de55`
- `GDI32!DeleteDC` at `0x18006de55`
- `GDI32!SelectObject` at `0x18006dde3`
- `GDI32!SelectObject` at `0x18006de43`
- `GDI32!SelectObject` at `0x18006dde3`
- `GDI32!SelectObject` at `0x18006de43`
- `MSIMG32!AlphaBlend` at `0x18006de37`
- `MSIMG32!AlphaBlend` at `0x18006de37`
- `USER32!EndPaint` at `0x18006de62`
- `USER32!EndPaint` at `0x18006de62`
- `USER32!BeginPaint` at `0x18006dd44`
- `USER32!BeginPaint` at `0x18006dd44`
- `USER32!GetClientRect` at `0x18006dd55`
- `USER32!GetClientRect` at `0x18006dd55`

## pseudocode

```c
void __fastcall CUserTileControl::_OnPaint(CUserTileControl *this, HWND a2)
{
  HDC v3; // r12
  HDC CompatibleDC; // rdi
  int hSrc; // r15d
  int wSrc; // r14d
  HBITMAP v7; // rax
  HBITMAP v8; // r13
  HGDIOBJ v9; // rbx
  void *ppvBits; // [rsp+68h] [rbp-98h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-90h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-80h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  Rect = 0;
  v3 = BeginPaint(a2, &Paint);
  GetClientRect(a2, &Rect);
  CompatibleDC = CreateCompatibleDC(v3);
  if ( CompatibleDC )
  {
    hSrc = Rect.bottom - Rect.top;
    wSrc = Rect.right - Rect.left;
    ppvBits = 0;
    pbmi.bmiHeader.biHeight = Rect.top - Rect.bottom;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = Rect.right - Rect.left;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v7 = CreateDIBSection(v3, &pbmi, 0, &ppvBits, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      v9 = SelectObject(CompatibleDC, v7);
      CUserTileControl::_PaintWorker(this, CompatibleDC, &Rect);
      AlphaBlend(v3, 0, 0, wSrc, hSrc, CompatibleDC, 0, 0, wSrc, hSrc, (BLENDFUNCTION)33488896);
      SelectObject(CompatibleDC, v9);
      DeleteObject(v8);
    }
    DeleteDC(CompatibleDC);
  }
  EndPaint(a2, &Paint);
}

```

## disassembly

```asm
0x18006dcf4  mov     [rsp-8+arg_10], rbx
0x18006dcf9  push    rbp
0x18006dcfa  push    rsi
0x18006dcfb  push    rdi
0x18006dcfc  push    r12
0x18006dcfe  push    r13
0x18006dd00  push    r14
0x18006dd02  push    r15
0x18006dd04  lea     rbp, [rsp-10h]
0x18006dd09  sub     rsp, 110h
0x18006dd10  mov     rax, cs:__security_cookie
0x18006dd17  xor     rax, rsp
0x18006dd1a  mov     [rbp+40h+var_40], rax
0x18006dd1e  mov     rsi, rdx
0x18006dd21  mov     qword ptr [rsp+140h+var_E0.BlendOp], rcx
0x18006dd26  xor     edx, edx; Val
0x18006dd28  lea     rcx, [rbp+40h+Paint]; void *
0x18006dd2c  lea     r8d, [rdx+48h]; Size
0x18006dd30  call    memset_0
0x18006dd35  xorps   xmm0, xmm0
0x18006dd38  lea     rdx, [rbp+40h+Paint]; lpPaint
0x18006dd3c  mov     rcx, rsi; hWnd
0x18006dd3f  movups  xmmword ptr [rsp+140h+Rect.left], xmm0
0x18006dd44  call    cs:__imp_BeginPaint
0x18006dd4a  lea     rdx, [rsp+140h+Rect]; lpRect
0x18006dd4f  mov     rcx, rsi; hWnd
0x18006dd52  mov     r12, rax
0x18006dd55  call    cs:__imp_GetClientRect
0x18006dd5b  mov     rcx, r12; hdc
0x18006dd5e  call    cs:__imp_CreateCompatibleDC
0x18006dd64  xor     ebx, ebx
0x18006dd66  mov     rdi, rax
0x18006dd69  test    rax, rax
0x18006dd6c  jz      loc_18006DE5B
0x18006dd72  mov     r15d, [rsp+140h+Rect.bottom]
0x18006dd77  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x18006dd7c  sub     r15d, [rsp+140h+Rect.top]
0x18006dd81  lea     rdx, [rbp+40h+pbmi]; pbmi
0x18006dd85  mov     r14d, [rsp+140h+Rect.right]
0x18006dd8a  xor     eax, eax
0x18006dd8c  sub     r14d, [rsp+140h+Rect.left]
0x18006dd91  xorps   xmm0, xmm0
0x18006dd94  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biWidth], xmm0
0x18006dd98  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biClrImportant], rax
0x18006dd9c  xor     r8d, r8d; usage
0x18006dd9f  mov     eax, r15d
0x18006dda2  mov     [rsp+140h+offset], ebx; offset
0x18006dda6  neg     eax
0x18006dda8  mov     [rsp+140h+ppvBits], rbx
0x18006ddad  mov     rcx, r12; hdc
0x18006ddb0  mov     [rbp+40h+pbmi.bmiHeader.biHeight], eax
0x18006ddb3  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biSizeImage], xmm0
0x18006ddb7  mov     [rbp+40h+pbmi.bmiHeader.biSize], 28h ; '('
0x18006ddbe  mov     [rbp+40h+pbmi.bmiHeader.biWidth], r14d
0x18006ddc2  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biPlanes], 200001h
0x18006ddca  mov     [rsp+140h+hSection], rbx; hSection
0x18006ddcf  call    cs:__imp_CreateDIBSection
0x18006ddd5  mov     r13, rax
0x18006ddd8  test    rax, rax
0x18006dddb  jz      short loc_18006DE52
0x18006dddd  mov     rdx, rax; h
0x18006dde0  mov     rcx, rdi; hdc
0x18006dde3  call    cs:__imp_SelectObject
0x18006dde9  mov     rcx, qword ptr [rsp+140h+var_E0.BlendOp]; this
0x18006ddee  lea     r8, [rsp+140h+Rect]; struct tagRECT *
0x18006ddf3  mov     rdx, rdi; HDC
0x18006ddf6  mov     rbx, rax
0x18006ddf9  call    ?_PaintWorker@CUserTileControl@@AEAAXPEAUHDC__@@AEBUtagRECT@@@Z; CUserTileControl::_PaintWorker(HDC__ *,tagRECT const &)
0x18006ddfe  xor     eax, eax
0x18006de00  mov     dword ptr [rsp+140h+var_E0.BlendOp], 1FF0000h
0x18006de08  mov     ecx, dword ptr [rsp+140h+var_E0.BlendOp]
0x18006de0c  mov     r9d, r14d; wDest
0x18006de0f  mov     dword ptr [rsp+140h+ftn.BlendOp], ecx; ftn
0x18006de13  xor     r8d, r8d; yoriginDest
0x18006de16  mov     [rsp+140h+hSrc], r15d; hSrc
0x18006de1b  xor     edx, edx; xoriginDest
0x18006de1d  mov     [rsp+140h+wSrc], r14d; wSrc
0x18006de22  mov     rcx, r12; hdcDest
0x18006de25  mov     [rsp+140h+yoriginSrc], eax; yoriginSrc
0x18006de29  mov     [rsp+140h+xoriginSrc], eax; xoriginSrc
0x18006de2d  mov     qword ptr [rsp+140h+offset], rdi; hdcSrc
0x18006de32  mov     dword ptr [rsp+140h+hSection], r15d; hDest
0x18006de37  call    cs:__imp_AlphaBlend
0x18006de3d  mov     rdx, rbx; h
0x18006de40  mov     rcx, rdi; hdc
0x18006de43  call    cs:__imp_SelectObject
0x18006de49  mov     rcx, r13; ho
0x18006de4c  call    cs:__imp_DeleteObject
0x18006de52  mov     rcx, rdi; hdc
0x18006de55  call    cs:__imp_DeleteDC
0x18006de5b  lea     rdx, [rbp+40h+Paint]; lpPaint
0x18006de5f  mov     rcx, rsi; hWnd
0x18006de62  call    cs:__imp_EndPaint
0x18006de68  mov     rcx, [rbp+40h+var_40]
0x18006de6c  xor     rcx, rsp; StackCookie
0x18006de6f  call    __security_check_cookie
0x18006de74  mov     rbx, [rsp+140h+arg_10]
0x18006de7c  add     rsp, 110h
0x18006de83  pop     r15
0x18006de85  pop     r14
0x18006de87  pop     r13
0x18006de89  pop     r12
0x18006de8b  pop     rdi
0x18006de8c  pop     rsi
0x18006de8d  pop     rbp
0x18006de8e  retn
```
