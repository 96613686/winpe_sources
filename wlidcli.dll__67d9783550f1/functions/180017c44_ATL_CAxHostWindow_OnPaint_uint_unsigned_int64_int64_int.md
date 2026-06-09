# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x180017c44`
- end: `0x180017eab`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800184a0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180017c44`
- `0x180063010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180017dee`
- `GDI32!DeleteDC` at `0x180017dee`
- `GDI32!BitBlt` at `0x180017dd9`
- `GDI32!BitBlt` at `0x180017dd9`
- `GDI32!SelectObject` at `0x180017d0e`
- `GDI32!SelectObject` at `0x180017de5`
- `GDI32!SelectObject` at `0x180017d0e`
- `GDI32!SelectObject` at `0x180017de5`
- `GDI32!CreateCompatibleBitmap` at `0x180017ce1`
- `GDI32!CreateCompatibleBitmap` at `0x180017ce1`
- `GDI32!CreateCompatibleDC` at `0x180017cf6`
- `GDI32!CreateCompatibleDC` at `0x180017cf6`
- `GDI32!CreateSolidBrush` at `0x180017d26`
- `GDI32!CreateSolidBrush` at `0x180017e6c`
- `GDI32!CreateSolidBrush` at `0x180017d26`
- `GDI32!CreateSolidBrush` at `0x180017e6c`
- `GDI32!DeleteObject` at `0x180017d4b`
- `GDI32!DeleteObject` at `0x180017e8d`
- `GDI32!DeleteObject` at `0x180017d4b`
- `GDI32!DeleteObject` at `0x180017e8d`
- `USER32!BeginPaint` at `0x180017ca9`
- `USER32!BeginPaint` at `0x180017e43`
- `USER32!BeginPaint` at `0x180017ca9`
- `USER32!BeginPaint` at `0x180017e43`
- `USER32!EndPaint` at `0x180017e9b`
- `USER32!EndPaint` at `0x180017e9b`
- `USER32!FillRect` at `0x180017d42`
- `USER32!FillRect` at `0x180017e84`
- `USER32!FillRect` at `0x180017d42`
- `USER32!FillRect` at `0x180017e84`
- `USER32!GetClientRect` at `0x180017cca`
- `USER32!GetClientRect` at `0x180017e60`
- `USER32!GetClientRect` at `0x180017cca`
- `USER32!GetClientRect` at `0x180017e60`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPaint(ATL::CAxHostWindow *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HDC v6; // rsi
  HWND v7; // rcx
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // r15
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // r12
  HBITMAP v14; // rcx
  HDC v16; // rsi
  HWND v17; // rcx
  HBRUSH v18; // rax
  HBRUSH v19; // rdi
  struct tagRECT Rect; // [rsp+60h] [rbp-41h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+70h] [rbp-31h] BYREF

  if ( *((_QWORD *)this + 28) )
  {
    if ( (*((_BYTE *)this + 280) & 8) != 0 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      v6 = BeginPaint(*((HWND *)this + 1), &Paint);
      if ( v6 )
      {
        v7 = (HWND)*((_QWORD *)this + 1);
        Rect = 0;
        GetClientRect(v7, &Rect);
        CompatibleBitmap = CreateCompatibleBitmap(v6, Rect.right - Rect.left, Rect.bottom - Rect.top);
        if ( CompatibleBitmap )
        {
          CompatibleDC = CreateCompatibleDC(v6);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            v11 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( v11 )
            {
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 85));
              v13 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v13);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  1,
                  0xFFFFFFFFLL);
                BitBlt(v6, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u);
              }
              SelectObject(hdcSrc, v11);
            }
            DeleteDC(hdcSrc);
          }
          v14 = CompatibleBitmap;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 0;
  }
  memset_0(&Paint, 0, sizeof(Paint));
  v16 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( !v16 )
    return 0;
  v17 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  GetClientRect(v17, &Rect);
  v18 = CreateSolidBrush(*((_DWORD *)this + 85));
  v19 = v18;
  if ( v18 )
  {
    FillRect(v16, &Rect, v18);
    v14 = (HBITMAP)v19;
LABEL_17:
    DeleteObject(v14);
  }
LABEL_18:
  EndPaint(*((HWND *)this + 1), &Paint);
  return 1;
}

```

## disassembly

```asm
0x180017c44  mov     [rsp-8+arg_8], rbx
0x180017c49  mov     [rsp-8+arg_10], rsi
0x180017c4e  push    rbp
0x180017c4f  push    rdi
0x180017c50  push    r12
0x180017c52  push    r14
0x180017c54  push    r15
0x180017c56  lea     rbp, [rsp-2Fh]
0x180017c5b  sub     rsp, 0D0h
0x180017c62  mov     rax, cs:__security_cookie
0x180017c69  xor     rax, rsp
0x180017c6c  mov     [rbp+4Fh+var_30], rax
0x180017c70  cmp     qword ptr [rcx+0E0h], 0
0x180017c78  mov     rbx, rcx
0x180017c7b  mov     rax, [rbp+4Fh+arg_20]
0x180017c7f  jz      loc_180017E2C
0x180017c85  test    byte ptr [rcx+118h], 8
0x180017c8c  jz      loc_180017DFC
0x180017c92  xor     edx, edx; Val
0x180017c94  lea     rcx, [rbp+4Fh+Paint]; void *
0x180017c98  lea     r8d, [rdx+48h]; Size
0x180017c9c  call    memset_0
0x180017ca1  mov     rcx, [rbx+8]; hWnd
0x180017ca5  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180017ca9  call    cs:__imp_BeginPaint
0x180017caf  mov     rsi, rax
0x180017cb2  test    rax, rax
0x180017cb5  jz      loc_180017E02
0x180017cbb  mov     rcx, [rbx+8]; hWnd
0x180017cbf  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x180017cc3  xorps   xmm0, xmm0
0x180017cc6  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180017cca  call    cs:__imp_GetClientRect
0x180017cd0  mov     r8d, [rbp+4Fh+Rect.bottom]
0x180017cd4  mov     rcx, rsi; hdc
0x180017cd7  mov     edx, [rbp+4Fh+Rect.right]
0x180017cda  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x180017cde  sub     edx, [rbp+4Fh+Rect.left]; cx
0x180017ce1  call    cs:__imp_CreateCompatibleBitmap
0x180017ce7  mov     r14, rax
0x180017cea  test    rax, rax
0x180017ced  jz      loc_180017E93
0x180017cf3  mov     rcx, rsi; hdc
0x180017cf6  call    cs:__imp_CreateCompatibleDC
0x180017cfc  mov     rdi, rax
0x180017cff  test    rax, rax
0x180017d02  jz      loc_180017DF4
0x180017d08  mov     rdx, r14; h
0x180017d0b  mov     rcx, rax; hdc
0x180017d0e  call    cs:__imp_SelectObject
0x180017d14  mov     r15, rax
0x180017d17  test    rax, rax
0x180017d1a  jz      loc_180017DEB
0x180017d20  mov     ecx, [rbx+154h]; color
0x180017d26  call    cs:__imp_CreateSolidBrush
0x180017d2c  mov     r12, rax
0x180017d2f  test    rax, rax
0x180017d32  jz      loc_180017DDF
0x180017d38  mov     r8, rax; hbr
0x180017d3b  lea     rdx, [rbp+4Fh+Rect]; lprc
0x180017d3f  mov     rcx, rdi; hDC
0x180017d42  call    cs:__imp_FillRect
0x180017d48  mov     rcx, r12; ho
0x180017d4b  call    cs:__imp_DeleteObject
0x180017d51  mov     rcx, [rbx+0E0h]
0x180017d58  lea     rdx, [rbx+134h]
0x180017d5f  mov     [rsp+0F0h+var_A0], 0
0x180017d68  xor     r9d, r9d
0x180017d6b  mov     [rsp+0F0h+var_A8], 0
0x180017d74  or      r8d, 0FFFFFFFFh
0x180017d78  mov     qword ptr [rsp+0F0h+rop], rdx
0x180017d7d  mov     rax, [rcx]
0x180017d80  mov     qword ptr [rsp+0F0h+y1], rdx
0x180017d85  lea     edx, [r9+1]
0x180017d89  mov     qword ptr [rsp+0F0h+x1], rdi
0x180017d8e  mov     [rsp+0F0h+hdcSrc], 0
0x180017d97  mov     rax, [rax+18h]
0x180017d9b  mov     qword ptr [rsp+0F0h+cy], 0
0x180017da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017da9  mov     eax, [rbp+4Fh+Rect.bottom]
0x180017dac  xor     r8d, r8d; y
0x180017daf  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x180017db3  xor     edx, edx; x
0x180017db5  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x180017dbd  mov     rcx, rsi; hdc
0x180017dc0  mov     [rsp+0F0h+y1], 0; y1
0x180017dc8  mov     [rsp+0F0h+x1], 0; x1
0x180017dd0  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x180017dd5  mov     [rsp+0F0h+cy], eax; cy
0x180017dd9  call    cs:__imp_BitBlt
0x180017ddf  mov     rdx, r15; h
0x180017de2  mov     rcx, rdi; hdc
0x180017de5  call    cs:__imp_SelectObject
0x180017deb  mov     rcx, rdi; hdc
0x180017dee  call    cs:__imp_DeleteDC
0x180017df4  mov     rcx, r14
0x180017df7  jmp     loc_180017E8D
0x180017dfc  mov     dword ptr [rax], 0
0x180017e02  xor     eax, eax
0x180017e04  mov     rcx, [rbp+4Fh+var_30]
0x180017e08  xor     rcx, rsp; StackCookie
0x180017e0b  call    __security_check_cookie
0x180017e10  lea     r11, [rsp+0F0h+var_20]
0x180017e18  mov     rbx, [r11+38h]
0x180017e1c  mov     rsi, [r11+40h]
0x180017e20  mov     rsp, r11
0x180017e23  pop     r15
0x180017e25  pop     r14
0x180017e27  pop     r12
0x180017e29  pop     rdi
0x180017e2a  pop     rbp
0x180017e2b  retn
0x180017e2c  xor     edx, edx; Val
0x180017e2e  lea     rcx, [rbp+4Fh+Paint]; void *
0x180017e32  lea     r8d, [rdx+48h]; Size
0x180017e36  call    memset_0
0x180017e3b  mov     rcx, [rbx+8]; hWnd
0x180017e3f  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180017e43  call    cs:__imp_BeginPaint
0x180017e49  mov     rsi, rax
0x180017e4c  test    rax, rax
0x180017e4f  jz      short loc_180017E02
0x180017e51  mov     rcx, [rbx+8]; hWnd
0x180017e55  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x180017e59  xorps   xmm0, xmm0
0x180017e5c  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180017e60  call    cs:__imp_GetClientRect
0x180017e66  mov     ecx, [rbx+154h]; color
0x180017e6c  call    cs:__imp_CreateSolidBrush
0x180017e72  mov     rdi, rax
0x180017e75  test    rax, rax
0x180017e78  jz      short loc_180017E93
0x180017e7a  mov     r8, rax; hbr
0x180017e7d  lea     rdx, [rbp+4Fh+Rect]; lprc
0x180017e81  mov     rcx, rsi; hDC
0x180017e84  call    cs:__imp_FillRect
0x180017e8a  mov     rcx, rdi; ho
0x180017e8d  call    cs:__imp_DeleteObject
0x180017e93  mov     rcx, [rbx+8]; hWnd
0x180017e97  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180017e9b  call    cs:__imp_EndPaint
0x180017ea1  mov     eax, 1
0x180017ea6  jmp     loc_180017E04
```
