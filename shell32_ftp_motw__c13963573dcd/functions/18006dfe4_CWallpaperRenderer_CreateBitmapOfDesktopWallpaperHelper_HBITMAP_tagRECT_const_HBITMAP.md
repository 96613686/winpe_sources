# CWallpaperRenderer::_CreateBitmapOfDesktopWallpaperHelper(HBITMAP__ *,tagRECT const &,HBITMAP__ * *)

- ea: `0x18006dfe4`
- end: `0x18006e3d6`
- name: `?_CreateBitmapOfDesktopWallpaperHelper@CWallpaperRenderer@@AEBA_NPEAUHBITMAP__@@AEBUtagRECT@@PEAPEAU2@@Z`
- size: `1010`
- prototype: `bool __fastcall(CWallpaperRenderer *__hidden this, HBITMAP, const struct tagRECT *, HBITMAP *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006d4b8`
- `0x1804cf7a0`

## callees

- `0x18006dfe4`
- `0x18006e3dc`
- `0x180249490`

## import_xrefs

- `USER32!FillRect` at `0x18006e156`
- `USER32!FillRect` at `0x18006e156`
- `USER32!GetSystemMetrics` at `0x18006e18e`
- `USER32!GetSystemMetrics` at `0x18006e1a4`
- `USER32!GetSystemMetrics` at `0x18006e18e`
- `USER32!GetSystemMetrics` at `0x18006e1a4`
- `GDI32!DeleteObject` at `0x18006e2f9`
- `GDI32!DeleteObject` at `0x18006e2f9`
- `GDI32!CreateCompatibleDC` at `0x18006e043`
- `GDI32!CreateCompatibleDC` at `0x18006e0da`
- `GDI32!CreateCompatibleDC` at `0x18006e043`
- `GDI32!CreateCompatibleDC` at `0x18006e0da`
- `GDI32!SelectObject` at `0x18006e062`
- `GDI32!SelectObject` at `0x18006e122`
- `GDI32!SelectObject` at `0x18006e2ea`
- `GDI32!SelectObject` at `0x18006e30c`
- `GDI32!SelectObject` at `0x18006e062`
- `GDI32!SelectObject` at `0x18006e122`
- `GDI32!SelectObject` at `0x18006e2ea`
- `GDI32!SelectObject` at `0x18006e30c`
- `GDI32!DeleteDC` at `0x18006e31b`
- `GDI32!DeleteDC` at `0x18006e31b`
- `GDI32!BitBlt` at `0x18006e20f`
- `GDI32!BitBlt` at `0x18006e2c8`
- `GDI32!BitBlt` at `0x18006e39d`
- `GDI32!BitBlt` at `0x18006e20f`
- `GDI32!BitBlt` at `0x18006e2c8`
- `GDI32!BitBlt` at `0x18006e39d`
- `GDI32!GetObjectW` at `0x18006e093`
- `GDI32!GetObjectW` at `0x18006e093`
- `GDI32!CreateCompatibleBitmap` at `0x18006e100`
- `GDI32!CreateCompatibleBitmap` at `0x18006e100`

## pseudocode

```c
bool __fastcall CWallpaperRenderer::_CreateBitmapOfDesktopWallpaperHelper(
        CWallpaperRenderer *this,
        HBITMAP a2,
        const struct tagRECT *a3,
        HBITMAP *a4)
{
  bool v4; // r13
  LONG right; // ebx
  LONG bottom; // esi
  unsigned int v9; // r12d
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r15
  HDC v12; // r14
  int v13; // ebx
  int v14; // esi
  HBITMAP CompatibleBitmap; // rax
  int y1; // r11d
  LONG v17; // ebx
  int SystemMetrics; // eax
  LONG v19; // esi
  int v20; // ebx
  int v21; // eax
  LONG v22; // r9d
  LONG cy; // ecx
  int v24; // r12d
  int i; // esi
  int j; // ebx
  BOOL v27; // eax
  int x1; // edi
  int v29; // edx
  int v30; // eax
  int v31; // eax
  int v32; // esi
  int v33; // edx
  int v34; // eax
  int v35; // eax
  int v36; // ebx
  int v37; // r8d
  int v38; // edx
  int v40; // eax
  int v41; // eax
  int y; // [rsp+50h] [rbp-49h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-41h] BYREF
  LONG left; // [rsp+60h] [rbp-39h]
  LONG top; // [rsp+64h] [rbp-35h]
  HGDIOBJ v46; // [rsp+68h] [rbp-31h]
  HGDIOBJ v47; // [rsp+70h] [rbp-29h]
  RECT pv[2]; // [rsp+78h] [rbp-21h] BYREF
  RECT rc; // [rsp+98h] [rbp-1h] BYREF

  v4 = 0;
  right = a3->right;
  bottom = a3->bottom;
  v9 = 5;
  left = a3->left;
  top = a3->top;
  v46 = a4;
  h = a2;
  if ( !*((_BYTE *)this + 48) )
    v9 = *((_DWORD *)this + 6);
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v47 = SelectObject(CompatibleDC, h);
    if ( v47 )
    {
      memset(pv, 0, sizeof(pv));
      if ( GetObjectW(h, 32, pv) == 32 )
      {
        LODWORD(h) = 0;
        y = 0;
        CWallpaperRenderer::_GetOffsetAndTileMode(this, a3, pv, v9, 0, &h, &y);
        v12 = CreateCompatibleDC(0);
        if ( v12 )
        {
          v13 = right - left;
          v14 = bottom - top;
          CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, v13, v14);
          *(_QWORD *)v46 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v46 = SelectObject(v12, CompatibleBitmap);
            if ( v46 )
            {
              *(_QWORD *)&rc.left = 0;
              rc.right = v13;
              rc.bottom = v14;
              FillRect(v12, &rc, (HBRUSH)2);
              if ( v9 == 1 )
              {
                v17 = a3->left;
                SystemMetrics = GetSystemMetrics(76);
                v19 = a3->top;
                v20 = v17 - SystemMetrics;
                v21 = GetSystemMetrics(77);
                v22 = pv[0].top;
                cy = pv[0].right;
                v24 = a3->left - v20 % pv[0].top;
                for ( i = v19 - (v19 - v21) % pv[0].right; i < a3->bottom; i += cy )
                {
                  for ( j = v24; j < a3->right; j += pv[0].top )
                  {
                    v27 = BitBlt(v12, j - a3->left, i - a3->top, v22, cy, hdcSrc, 0, 0, 0xCC0020u);
                    v22 = pv[0].top;
                    cy = pv[0].right;
                    v4 = v27;
                  }
                }
              }
              else if ( v9 == 5 )
              {
                v4 = BitBlt(v12, (_DWORD)h - a3->left, y - a3->top, pv[0].top, pv[0].right, hdcSrc, 0, 0, 0xCC0020u);
              }
              else
              {
                if ( y < 0 )
                  y1 = -y;
                else
                  y1 = 0;
                if ( (int)h < 0 )
                  x1 = -(int)h;
                else
                  x1 = 0;
                v29 = 0;
                if ( y > 0 )
                  v29 = y;
                v30 = 0;
                if ( y < 0 )
                  v30 = y;
                if ( v14 - v29 >= pv[0].right + v30 )
                {
                  v40 = 0;
                  if ( y < 0 )
                    v40 = y;
                  v32 = v40 + pv[0].right;
                }
                else
                {
                  v31 = 0;
                  if ( y > 0 )
                    v31 = y;
                  v32 = v14 - v31;
                }
                v33 = 0;
                if ( (int)h > 0 )
                  v33 = (int)h;
                v34 = 0;
                if ( (int)h < 0 )
                  v34 = (int)h;
                if ( v13 - v33 >= pv[0].top + v34 )
                {
                  v41 = 0;
                  if ( (int)h < 0 )
                    v41 = (int)h;
                  v36 = v41 + pv[0].top;
                }
                else
                {
                  v35 = 0;
                  if ( (int)h > 0 )
                    v35 = (int)h;
                  v36 = v13 - v35;
                }
                v37 = 0;
                if ( y > 0 )
                  v37 = y;
                v38 = 0;
                if ( (int)h > 0 )
                  v38 = (int)h;
                v4 = BitBlt(v12, v38, v37, v36, v32, hdcSrc, x1, y1, 0xCC0020u);
              }
              SelectObject(v12, v46);
            }
          }
          DeleteObject(v12);
        }
      }
      SelectObject(hdcSrc, v47);
    }
    DeleteDC(hdcSrc);
  }
  return v4;
}

```

## disassembly

```asm
0x18006dfe4  push    rbp
0x18006dfe6  push    rbx
0x18006dfe7  push    rsi
0x18006dfe8  push    rdi
0x18006dfe9  push    r12
0x18006dfeb  push    r13
0x18006dfed  push    r14
0x18006dfef  push    r15
0x18006dff1  lea     rbp, [rsp-1Fh]
0x18006dff6  sub     rsp, 0B8h
0x18006dffd  mov     rax, cs:__security_cookie
0x18006e004  xor     rax, rsp
0x18006e007  mov     [rbp+57h+var_48], rax
0x18006e00b  mov     eax, [r8]
0x18006e00e  xor     r13b, r13b
0x18006e011  mov     rdi, r8
0x18006e014  mov     ebx, [r8+8]
0x18006e018  mov     r14, rcx
0x18006e01b  mov     esi, [r8+0Ch]
0x18006e01f  mov     r12d, 5
0x18006e025  mov     [rbp+57h+var_90], eax
0x18006e028  mov     eax, [r8+4]
0x18006e02c  mov     [rbp+57h+var_8C], eax
0x18006e02f  mov     [rbp+57h+var_88], r9
0x18006e033  mov     [rbp+57h+h], rdx
0x18006e037  cmp     [rcx+30h], r13b
0x18006e03b  jnz     short loc_18006E041
0x18006e03d  mov     r12d, [rcx+18h]
0x18006e041  xor     ecx, ecx; hdc
0x18006e043  call    cs:__imp_CreateCompatibleDC
0x18006e04a  nop     dword ptr [rax+rax+00h]
0x18006e04f  mov     r15, rax
0x18006e052  test    rax, rax
0x18006e055  jz      loc_18006E327
0x18006e05b  mov     rdx, [rbp+57h+h]; h
0x18006e05f  mov     rcx, rax; hdc
0x18006e062  call    cs:__imp_SelectObject
0x18006e069  nop     dword ptr [rax+rax+00h]
0x18006e06e  mov     [rbp+57h+var_80], rax
0x18006e072  test    rax, rax
0x18006e075  jz      loc_18006E318
0x18006e07b  mov     rcx, [rbp+57h+h]; h
0x18006e07f  lea     r8, [rbp+57h+pv]; pv
0x18006e083  xorps   xmm0, xmm0
0x18006e086  mov     edx, 20h ; ' '; c
0x18006e08b  movups  [rbp+57h+pv], xmm0
0x18006e08f  movups  [rbp+57h+var_68], xmm0
0x18006e093  call    cs:__imp_GetObjectW
0x18006e09a  nop     dword ptr [rax+rax+00h]
0x18006e09f  cmp     eax, 20h ; ' '
0x18006e0a2  jnz     loc_18006E305
0x18006e0a8  xor     ecx, ecx
0x18006e0aa  lea     rax, [rbp+57h+y]
0x18006e0ae  mov     qword ptr [rsp+0F0h+x1], rax
0x18006e0b3  lea     r8, [rbp+57h+pv]
0x18006e0b7  lea     rax, [rbp+57h+h]
0x18006e0bb  mov     dword ptr [rbp+57h+h], ecx
0x18006e0be  mov     [rsp+0F0h+hdcSrc], rax
0x18006e0c3  mov     r9d, r12d
0x18006e0c6  mov     byte ptr [rsp+0F0h+cy], cl
0x18006e0ca  mov     rdx, rdi
0x18006e0cd  mov     [rbp+57h+y], ecx
0x18006e0d0  mov     rcx, r14
0x18006e0d3  call    ?_GetOffsetAndTileMode@CWallpaperRenderer@@AEBAXPEBUtagRECT@@PEBUtagBITMAP@@W4DESKTOP_WALLPAPER_POSITION@@_NPEAH4@Z; CWallpaperRenderer::_GetOffsetAndTileMode(tagRECT const *,tagBITMAP const *,DESKTOP_WALLPAPER_POSITION,bool,int *,int *)
0x18006e0d8  xor     ecx, ecx; hdc
0x18006e0da  call    cs:__imp_CreateCompatibleDC
0x18006e0e1  nop     dword ptr [rax+rax+00h]
0x18006e0e6  mov     r14, rax
0x18006e0e9  test    rax, rax
0x18006e0ec  jz      loc_18006E305
0x18006e0f2  sub     ebx, [rbp+57h+var_90]
0x18006e0f5  mov     rcx, r15; hdc
0x18006e0f8  sub     esi, [rbp+57h+var_8C]
0x18006e0fb  mov     edx, ebx; cx
0x18006e0fd  mov     r8d, esi; cy
0x18006e100  call    cs:__imp_CreateCompatibleBitmap
0x18006e107  nop     dword ptr [rax+rax+00h]
0x18006e10c  mov     rcx, [rbp+57h+var_88]
0x18006e110  mov     [rcx], rax
0x18006e113  test    rax, rax
0x18006e116  jz      loc_18006E2F6
0x18006e11c  mov     rdx, rax; h
0x18006e11f  mov     rcx, r14; hdc
0x18006e122  call    cs:__imp_SelectObject
0x18006e129  nop     dword ptr [rax+rax+00h]
0x18006e12e  mov     [rbp+57h+var_88], rax
0x18006e132  test    rax, rax
0x18006e135  jz      loc_18006E2F6
0x18006e13b  mov     r8d, 2; hbr
0x18006e141  mov     qword ptr [rbp+57h+rc.left], 0
0x18006e149  lea     rdx, [rbp+57h+rc]; lprc
0x18006e14d  mov     [rbp+57h+rc.right], ebx
0x18006e150  mov     rcx, r14; hDC
0x18006e153  mov     [rbp+57h+rc.bottom], esi
0x18006e156  call    cs:__imp_FillRect
0x18006e15d  nop     dword ptr [rax+rax+00h]
0x18006e162  cmp     r12d, 1
0x18006e166  jz      short loc_18006E187
0x18006e168  cmp     r12d, 5
0x18006e16c  jz      loc_18006E365
0x18006e172  mov     r10d, [rbp+57h+y]
0x18006e176  test    r10d, r10d
0x18006e179  js      loc_18006E34B
0x18006e17f  xor     r11d, r11d
0x18006e182  jmp     loc_18006E351
0x18006e187  mov     ebx, [rdi]
0x18006e189  mov     ecx, 4Ch ; 'L'; nIndex
0x18006e18e  call    cs:__imp_GetSystemMetrics
0x18006e195  nop     dword ptr [rax+rax+00h]
0x18006e19a  mov     esi, [rdi+4]
0x18006e19d  mov     ecx, 4Dh ; 'M'; nIndex
0x18006e1a2  sub     ebx, eax
0x18006e1a4  call    cs:__imp_GetSystemMetrics
0x18006e1ab  nop     dword ptr [rax+rax+00h]
0x18006e1b0  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x18006e1b4  mov     ecx, esi
0x18006e1b6  mov     r12d, [rdi]
0x18006e1b9  sub     ecx, eax
0x18006e1bb  mov     eax, ebx
0x18006e1bd  cdq
0x18006e1be  idiv    r9d
0x18006e1c1  mov     eax, ecx
0x18006e1c3  mov     ecx, dword ptr [rbp+57h+pv+8]
0x18006e1c6  sub     r12d, edx
0x18006e1c9  cdq
0x18006e1ca  idiv    ecx
0x18006e1cc  sub     esi, edx
0x18006e1ce  cmp     esi, [rdi+0Ch]
0x18006e1d1  jge     loc_18006E2E3
0x18006e1d7  mov     ebx, r12d
0x18006e1da  cmp     r12d, [rdi+8]
0x18006e1de  jge     short loc_18006E230
0x18006e1e0  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18006e1e8  mov     r8d, esi
0x18006e1eb  sub     r8d, [rdi+4]; y
0x18006e1ef  mov     edx, ebx
0x18006e1f1  sub     edx, [rdi]; x
0x18006e1f3  mov     [rsp+0F0h+y1], 0; y1
0x18006e1fb  mov     [rsp+0F0h+x1], 0; x1
0x18006e203  mov     [rsp+0F0h+hdcSrc], r15; hdcSrc
0x18006e208  mov     [rsp+0F0h+cy], ecx; cy
0x18006e20c  mov     rcx, r14; hdc
0x18006e20f  call    cs:__imp_BitBlt
0x18006e216  nop     dword ptr [rax+rax+00h]
0x18006e21b  mov     r9d, dword ptr [rbp+57h+pv+4]
0x18006e21f  test    eax, eax
0x18006e221  mov     ecx, dword ptr [rbp+57h+pv+8]
0x18006e224  setnz   r13b
0x18006e228  add     ebx, r9d
0x18006e22b  cmp     ebx, [rdi+8]
0x18006e22e  jl      short loc_18006E1E0
0x18006e230  add     esi, ecx
0x18006e232  jmp     short loc_18006E1CE
0x18006e234  mov     edi, r9d
0x18006e237  neg     edi
0x18006e239  xor     edx, edx
0x18006e23b  mov     ecx, esi
0x18006e23d  test    r10d, r10d
0x18006e240  cmovg   edx, r10d
0x18006e244  xor     eax, eax
0x18006e246  test    r10d, r10d
0x18006e249  cmovs   eax, r10d
0x18006e24d  sub     ecx, edx
0x18006e24f  mov     edx, dword ptr [rbp+57h+pv+8]
0x18006e252  add     eax, edx
0x18006e254  cmp     ecx, eax
0x18006e256  jge     loc_18006E3B4
0x18006e25c  xor     eax, eax
0x18006e25e  test    r10d, r10d
0x18006e261  cmovg   eax, r10d
0x18006e265  sub     esi, eax
0x18006e267  xor     edx, edx
0x18006e269  mov     ecx, ebx
0x18006e26b  test    r9d, r9d
0x18006e26e  cmovg   edx, r9d
0x18006e272  xor     eax, eax
0x18006e274  test    r9d, r9d
0x18006e277  cmovs   eax, r9d
0x18006e27b  sub     ecx, edx
0x18006e27d  mov     edx, dword ptr [rbp+57h+pv+4]
0x18006e280  add     eax, edx
0x18006e282  cmp     ecx, eax
0x18006e284  jge     loc_18006E3C5
0x18006e28a  xor     eax, eax
0x18006e28c  test    r9d, r9d
0x18006e28f  cmovg   eax, r9d
0x18006e293  sub     ebx, eax
0x18006e295  xor     r8d, r8d
0x18006e298  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18006e2a0  mov     [rsp+0F0h+y1], r11d; y1
0x18006e2a5  test    r10d, r10d
0x18006e2a8  mov     [rsp+0F0h+x1], edi; x1
0x18006e2ac  mov     rcx, r14; hdc
0x18006e2af  cmovg   r8d, r10d; y
0x18006e2b3  mov     [rsp+0F0h+hdcSrc], r15; hdcSrc
0x18006e2b8  xor     edx, edx
0x18006e2ba  mov     [rsp+0F0h+cy], esi; cy
0x18006e2be  test    r9d, r9d
0x18006e2c1  cmovg   edx, r9d; x
0x18006e2c5  mov     r9d, ebx; cx
0x18006e2c8  call    cs:__imp_BitBlt
0x18006e2cf  nop     dword ptr [rax+rax+00h]
0x18006e2d4  test    eax, eax
0x18006e2d6  movzx   r13d, r13b
0x18006e2da  mov     eax, 1
0x18006e2df  cmovnz  r13d, eax
0x18006e2e3  mov     rdx, [rbp+57h+var_88]; h
0x18006e2e7  mov     rcx, r14; hdc
0x18006e2ea  call    cs:__imp_SelectObject
0x18006e2f1  nop     dword ptr [rax+rax+00h]
0x18006e2f6  mov     rcx, r14; ho
0x18006e2f9  call    cs:__imp_DeleteObject
0x18006e300  nop     dword ptr [rax+rax+00h]
0x18006e305  mov     rdx, [rbp+57h+var_80]; h
0x18006e309  mov     rcx, r15; hdc
0x18006e30c  call    cs:__imp_SelectObject
0x18006e313  nop     dword ptr [rax+rax+00h]
0x18006e318  mov     rcx, r15; hdc
0x18006e31b  call    cs:__imp_DeleteDC
0x18006e322  nop     dword ptr [rax+rax+00h]
0x18006e327  mov     al, r13b
0x18006e32a  mov     rcx, [rbp+57h+var_48]
0x18006e32e  xor     rcx, rsp; StackCookie
0x18006e331  call    __security_check_cookie
0x18006e336  add     rsp, 0B8h
0x18006e33d  pop     r15
0x18006e33f  pop     r14
0x18006e341  pop     r13
0x18006e343  pop     r12
0x18006e345  pop     rdi
0x18006e346  pop     rsi
0x18006e347  pop     rbx
0x18006e348  pop     rbp
0x18006e349  retn
0x18006e34b  mov     r11d, r10d
0x18006e34e  neg     r11d
0x18006e351  mov     r9d, dword ptr [rbp+57h+h]
0x18006e355  test    r9d, r9d
0x18006e358  js      loc_18006E234
0x18006e35e  xor     edi, edi
0x18006e360  jmp     loc_18006E239
0x18006e365  mov     r8d, [rbp+57h+y]
0x18006e369  mov     rcx, r14; hdc
0x18006e36c  mov     edx, dword ptr [rbp+57h+h]
0x18006e36f  mov     eax, dword ptr [rbp+57h+pv+8]
0x18006e372  sub     r8d, [rdi+4]; y
0x18006e376  sub     edx, [rdi]; x
0x18006e378  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x18006e37c  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18006e384  mov     [rsp+0F0h+y1], 0; y1
0x18006e38c  mov     [rsp+0F0h+x1], 0; x1
0x18006e394  mov     [rsp+0F0h+hdcSrc], r15; hdcSrc
0x18006e399  mov     [rsp+0F0h+cy], eax; cy
0x18006e39d  call    cs:__imp_BitBlt
0x18006e3a4  nop     dword ptr [rax+rax+00h]
0x18006e3a9  test    eax, eax
0x18006e3ab  setnz   r13b
0x18006e3af  jmp     loc_18006E2E3
0x18006e3b4  xor     eax, eax
0x18006e3b6  test    r10d, r10d
0x18006e3b9  cmovs   eax, r10d
0x18006e3bd  lea     esi, [rax+rdx]
0x18006e3c0  jmp     loc_18006E267
0x18006e3c5  xor     eax, eax
0x18006e3c7  test    r9d, r9d
0x18006e3ca  cmovs   eax, r9d
0x18006e3ce  lea     ebx, [rax+rdx]
0x18006e3d1  jmp     loc_18006E295
```
