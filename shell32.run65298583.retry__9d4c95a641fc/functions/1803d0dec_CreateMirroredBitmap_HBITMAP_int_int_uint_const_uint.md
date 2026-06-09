# _CreateMirroredBitmap(HBITMAP__ *,int,int,uint const *,uint)

- ea: `0x1803d0dec`
- end: `0x1803d1052`
- name: `?_CreateMirroredBitmap@@YAPEAUHBITMAP__@@PEAU1@HHPEBII@Z`
- size: `614`
- prototype: `HBITMAP __fastcall(HBITMAP h, int, int, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1803cffa0`

## callees

- `0x1800208d8`
- `0x180233280`
- `0x1803d0bd0`
- `0x1803d0dec`

## import_xrefs

- `USER32!ReleaseDC` at `0x1803d1013`
- `USER32!ReleaseDC` at `0x1803d1013`
- `USER32!GetDC` at `0x1803d0e5b`
- `USER32!GetDC` at `0x1803d0e5b`
- `GDI32!CreateDIBSection` at `0x1803d0f02`
- `GDI32!CreateDIBSection` at `0x1803d0f02`
- `GDI32!CreateCompatibleDC` at `0x1803d0e74`
- `GDI32!CreateCompatibleDC` at `0x1803d0e96`
- `GDI32!CreateCompatibleDC` at `0x1803d0e74`
- `GDI32!CreateCompatibleDC` at `0x1803d0e96`
- `GDI32!SelectObject` at `0x1803d0f30`
- `GDI32!SelectObject` at `0x1803d0f3f`
- `GDI32!SelectObject` at `0x1803d0fed`
- `GDI32!SelectObject` at `0x1803d0ff9`
- `GDI32!SelectObject` at `0x1803d0f30`
- `GDI32!SelectObject` at `0x1803d0f3f`
- `GDI32!SelectObject` at `0x1803d0fed`
- `GDI32!SelectObject` at `0x1803d0ff9`
- `GDI32!DeleteDC` at `0x1803d1008`
- `GDI32!DeleteDC` at `0x1803d1022`
- `GDI32!DeleteDC` at `0x1803d1008`
- `GDI32!DeleteDC` at `0x1803d1022`
- `GDI32!BitBlt` at `0x1803d0f90`
- `GDI32!BitBlt` at `0x1803d0f90`
- `GDI32!GetObjectW` at `0x1803d0e42`
- `GDI32!GetObjectW` at `0x1803d0e42`
- `GDI32!StretchBlt` at `0x1803d0fe1`
- `GDI32!StretchBlt` at `0x1803d0fe1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HBITMAP __fastcall _CreateMirroredBitmap(HBITMAP h, int a2, int a3, const unsigned int *a4)
{
  HBITMAP v5; // r14
  HDC DC; // rax
  HDC v7; // rsi
  HDC CompatibleDC; // rbx
  HDC v9; // rdi
  HBITMAP ColorBitmap; // rax
  HGDIOBJ v11; // r12
  HGDIOBJ v12; // r13
  int x1; // r15d
  int v14; // ecx
  HDC v18; // [rsp+68h] [rbp-59h]
  __int128 pv; // [rsp+80h] [rbp-41h] BYREF
  __int128 v20; // [rsp+90h] [rbp-31h]
  void *ppvBits; // [rsp+A0h] [rbp-21h] BYREF
  BITMAPINFO pbmi; // [rsp+A8h] [rbp-19h] BYREF

  v5 = 0;
  pv = 0;
  v20 = 0;
  if ( h && (GetObjectW(h, 32, &pv) || (int)ResultFromKnownLastError() >= 0) )
  {
    DC = GetDC(0);
    v7 = DC;
    v18 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      if ( CompatibleDC || (int)ResultFromKnownLastError() >= 0 )
      {
        v9 = CreateCompatibleDC(v7);
        if ( v9 || (int)ResultFromKnownLastError() >= 0 )
        {
          if ( WORD1(v20) == 32 )
          {
            ppvBits = 0;
            pbmi.bmiHeader.biSize = 40;
            *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)&pv + 4);
            *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
            memset(&pbmi.bmiHeader.biCompression, 0, 28);
            ColorBitmap = CreateDIBSection(v7, &pbmi, 0, &ppvBits, 0, 0);
          }
          else
          {
            ColorBitmap = _CreateColorBitmap(SDWORD1(pv), SDWORD2(pv));
          }
          v5 = ColorBitmap;
          if ( ColorBitmap || (int)ResultFromKnownLastError() >= 0 )
          {
            v11 = SelectObject(CompatibleDC, h);
            v12 = SelectObject(v9, v5);
            if ( a2 )
            {
              x1 = 0;
              v14 = DWORD1(pv);
              if ( SDWORD1(pv) > 0 )
              {
                do
                {
                  BitBlt(v9, v14 - a3 - x1, 0, a3, SDWORD2(pv), CompatibleDC, x1, 0, 0xCC0020u);
                  x1 += a3;
                  v14 = DWORD1(pv);
                }
                while ( x1 < SDWORD1(pv) );
                v7 = v18;
              }
            }
            else
            {
              StretchBlt(
                v9,
                0,
                0,
                SDWORD1(pv),
                SDWORD2(pv),
                CompatibleDC,
                SDWORD1(pv),
                0,
                -DWORD1(pv),
                SDWORD2(pv),
                0xCC0020u);
            }
            SelectObject(CompatibleDC, v11);
            SelectObject(v9, v12);
          }
        }
        if ( v9 )
          DeleteDC(v9);
      }
      ReleaseDC(0, v7);
      if ( CompatibleDC )
        DeleteDC(CompatibleDC);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1803d0dec  mov     [rsp-8+arg_8], rbx
0x1803d0df1  push    rbp
0x1803d0df2  push    rsi
0x1803d0df3  push    rdi
0x1803d0df4  push    r12
0x1803d0df6  push    r13
0x1803d0df8  push    r14
0x1803d0dfa  push    r15
0x1803d0dfc  lea     rbp, [rsp-1Fh]
0x1803d0e01  sub     rsp, 0E0h
0x1803d0e08  mov     rax, cs:__security_cookie
0x1803d0e0f  xor     rax, rsp
0x1803d0e12  mov     [rbp+4Fh+var_38], rax
0x1803d0e16  mov     [rbp+4Fh+var_AC], r8d
0x1803d0e1a  mov     [rbp+4Fh+var_B0], edx
0x1803d0e1d  mov     r15, rcx
0x1803d0e20  xor     r14d, r14d
0x1803d0e23  xorps   xmm0, xmm0
0x1803d0e26  movups  [rbp+4Fh+pv], xmm0
0x1803d0e2a  movups  [rbp+4Fh+var_80], xmm0
0x1803d0e2e  test    rcx, rcx
0x1803d0e31  jz      loc_1803D1028
0x1803d0e37  lea     r8, [rbp+4Fh+pv]; pv
0x1803d0e3b  lea     r12d, [r14+20h]
0x1803d0e3f  mov     edx, r12d; c
0x1803d0e42  call    cs:__imp_GetObjectW
0x1803d0e48  test    eax, eax
0x1803d0e4a  jnz     short loc_1803D0E59
0x1803d0e4c  call    ResultFromKnownLastError
0x1803d0e51  test    eax, eax
0x1803d0e53  js      loc_1803D1028
0x1803d0e59  xor     ecx, ecx; hWnd
0x1803d0e5b  call    cs:__imp_GetDC
0x1803d0e61  mov     rsi, rax
0x1803d0e64  mov     [rbp+4Fh+var_A8], rax
0x1803d0e68  test    rax, rax
0x1803d0e6b  jz      loc_1803D1028
0x1803d0e71  mov     rcx, rax; hdc
0x1803d0e74  call    cs:__imp_CreateCompatibleDC
0x1803d0e7a  mov     rbx, rax
0x1803d0e7d  mov     [rbp+4Fh+var_A0], rax
0x1803d0e81  test    rax, rax
0x1803d0e84  jnz     short loc_1803D0E93
0x1803d0e86  call    ResultFromKnownLastError
0x1803d0e8b  test    eax, eax
0x1803d0e8d  js      loc_1803D100E
0x1803d0e93  mov     rcx, rsi; hdc
0x1803d0e96  call    cs:__imp_CreateCompatibleDC
0x1803d0e9c  mov     rdi, rax
0x1803d0e9f  mov     [rbp+4Fh+var_98], rax
0x1803d0ea3  test    rax, rax
0x1803d0ea6  jnz     short loc_1803D0EB5
0x1803d0ea8  call    ResultFromKnownLastError
0x1803d0ead  test    eax, eax
0x1803d0eaf  js      loc_1803D1000
0x1803d0eb5  cmp     word ptr [rbp+4Fh+var_80+2], r12w
0x1803d0eba  jnz     short loc_1803D0F0A
0x1803d0ebc  mov     [rbp+4Fh+ppvBits], 0
0x1803d0ec4  mov     [rbp+4Fh+pbmi.bmiHeader.biSize], 28h ; '('
0x1803d0ecb  mov     eax, dword ptr [rbp+4Fh+pv+4]
0x1803d0ece  mov     [rbp+4Fh+pbmi.bmiHeader.biWidth], eax
0x1803d0ed1  mov     eax, dword ptr [rbp+4Fh+pv+8]
0x1803d0ed4  mov     [rbp+4Fh+pbmi.bmiHeader.biHeight], eax
0x1803d0ed7  mov     dword ptr [rbp+4Fh+pbmi.bmiHeader.biPlanes], 200001h
0x1803d0ede  xorps   xmm0, xmm0
0x1803d0ee1  xor     eax, eax
0x1803d0ee3  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biCompression], xmm0
0x1803d0ee7  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x1803d0eeb  mov     [rsp+110h+offset], eax; offset
0x1803d0eef  mov     [rsp+110h+hSection], rax; hSection
0x1803d0ef4  lea     r9, [rbp+4Fh+ppvBits]; ppvBits
0x1803d0ef8  xor     r8d, r8d; usage
0x1803d0efb  lea     rdx, [rbp+4Fh+pbmi]; pbmi
0x1803d0eff  mov     rcx, rsi; hdc
0x1803d0f02  call    cs:__imp_CreateDIBSection
0x1803d0f08  jmp     short loc_1803D0F15
0x1803d0f0a  mov     edx, dword ptr [rbp+4Fh+pv+8]; cy
0x1803d0f0d  mov     ecx, dword ptr [rbp+4Fh+pv+4]; cx
0x1803d0f10  call    ?_CreateColorBitmap@@YAPEAUHBITMAP__@@HH@Z; _CreateColorBitmap(int,int)
0x1803d0f15  mov     r14, rax
0x1803d0f18  test    rax, rax
0x1803d0f1b  jnz     short loc_1803D0F2A
0x1803d0f1d  call    ResultFromKnownLastError
0x1803d0f22  test    eax, eax
0x1803d0f24  js      loc_1803D1000
0x1803d0f2a  mov     rdx, r15; h
0x1803d0f2d  mov     rcx, rbx; hdc
0x1803d0f30  call    cs:__imp_SelectObject
0x1803d0f36  mov     r12, rax
0x1803d0f39  mov     rdx, r14; h
0x1803d0f3c  mov     rcx, rdi; hdc
0x1803d0f3f  call    cs:__imp_SelectObject
0x1803d0f45  mov     r13, rax
0x1803d0f48  cmp     [rbp+4Fh+var_B0], 0
0x1803d0f4c  jz      short loc_1803D0FA7
0x1803d0f4e  xor     r15d, r15d
0x1803d0f51  mov     ecx, dword ptr [rbp+4Fh+pv+4]
0x1803d0f54  test    ecx, ecx
0x1803d0f56  jle     loc_1803D0FE7
0x1803d0f5c  mov     esi, [rbp+4Fh+var_AC]
0x1803d0f5f  sub     ecx, esi
0x1803d0f61  sub     ecx, r15d
0x1803d0f64  mov     [rsp+110h+rop], 0CC0020h; rop
0x1803d0f6c  mov     [rsp+110h+y1], 0; y1
0x1803d0f74  mov     [rsp+110h+x1], r15d; x1
0x1803d0f79  mov     qword ptr [rsp+110h+offset], rbx; hdcSrc
0x1803d0f7e  mov     eax, dword ptr [rbp+4Fh+pv+8]
0x1803d0f81  mov     dword ptr [rsp+110h+hSection], eax; cy
0x1803d0f85  mov     r9d, esi; cx
0x1803d0f88  xor     r8d, r8d; y
0x1803d0f8b  mov     edx, ecx; x
0x1803d0f8d  mov     rcx, rdi; hdc
0x1803d0f90  call    cs:__imp_BitBlt
0x1803d0f96  add     r15d, esi
0x1803d0f99  mov     ecx, dword ptr [rbp+4Fh+pv+4]
0x1803d0f9c  cmp     r15d, ecx
0x1803d0f9f  jl      short loc_1803D0F5F
0x1803d0fa1  mov     rsi, [rbp+4Fh+var_A8]
0x1803d0fa5  jmp     short loc_1803D0FE7
0x1803d0fa7  mov     r9d, dword ptr [rbp+4Fh+pv+4]; wDest
0x1803d0fab  mov     eax, r9d
0x1803d0fae  neg     eax
0x1803d0fb0  mov     [rsp+110h+var_C0], 0CC0020h; rop
0x1803d0fb8  mov     ecx, dword ptr [rbp+4Fh+pv+8]
0x1803d0fbb  mov     [rsp+110h+hSrc], ecx; hSrc
0x1803d0fbf  mov     [rsp+110h+rop], eax; wSrc
0x1803d0fc3  mov     [rsp+110h+y1], 0; ySrc
0x1803d0fcb  mov     [rsp+110h+x1], r9d; xSrc
0x1803d0fd0  mov     qword ptr [rsp+110h+offset], rbx; hdcSrc
0x1803d0fd5  mov     dword ptr [rsp+110h+hSection], ecx; hDest
0x1803d0fd9  xor     r8d, r8d; yDest
0x1803d0fdc  xor     edx, edx; xDest
0x1803d0fde  mov     rcx, rdi; hdcDest
0x1803d0fe1  call    cs:__imp_StretchBlt
0x1803d0fe7  mov     rdx, r12; h
0x1803d0fea  mov     rcx, rbx; hdc
0x1803d0fed  call    cs:__imp_SelectObject
0x1803d0ff3  mov     rdx, r13; h
0x1803d0ff6  mov     rcx, rdi; hdc
0x1803d0ff9  call    cs:__imp_SelectObject
0x1803d0fff  nop
0x1803d1000  test    rdi, rdi
0x1803d1003  jz      short loc_1803D100E
0x1803d1005  mov     rcx, rdi; hdc
0x1803d1008  call    cs:__imp_DeleteDC
0x1803d100e  mov     rdx, rsi; hDC
0x1803d1011  xor     ecx, ecx; hWnd
0x1803d1013  call    cs:__imp_ReleaseDC
0x1803d1019  nop
0x1803d101a  test    rbx, rbx
0x1803d101d  jz      short loc_1803D1028
0x1803d101f  mov     rcx, rbx; hdc
0x1803d1022  call    cs:__imp_DeleteDC
0x1803d1028  mov     rax, r14
0x1803d102b  mov     rcx, [rbp+4Fh+var_38]
0x1803d102f  xor     rcx, rsp; StackCookie
0x1803d1032  call    __security_check_cookie
0x1803d1037  mov     rbx, [rsp+110h+arg_8]
0x1803d103f  add     rsp, 0E0h
0x1803d1046  pop     r15
0x1803d1048  pop     r14
0x1803d104a  pop     r13
0x1803d104c  pop     r12
0x1803d104e  pop     rdi
0x1803d104f  pop     rsi
0x1803d1050  pop     rbp
0x1803d1051  retn
```
