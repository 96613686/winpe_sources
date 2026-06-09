# _CreateMirroredBitmap(HBITMAP__ *,int,int,uint const *,uint)

- ea: `0x1803faa70`
- end: `0x1803fad2b`
- name: `?_CreateMirroredBitmap@@YAPEAUHBITMAP__@@PEAU1@HHPEBII@Z`
- size: `699`
- prototype: `HBITMAP __fastcall(HBITMAP h, int, int, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1803f9b5c`

## callees

- `0x180018e4c`
- `0x180249490`
- `0x1803fa814`
- `0x1803faa70`

## import_xrefs

- `USER32!ReleaseDC` at `0x1803facdf`
- `USER32!ReleaseDC` at `0x1803facdf`
- `USER32!GetDC` at `0x1803faae5`
- `USER32!GetDC` at `0x1803faae5`
- `GDI32!CreateDIBSection` at `0x1803fab9e`
- `GDI32!CreateDIBSection` at `0x1803fab9e`
- `GDI32!CreateCompatibleDC` at `0x1803fab04`
- `GDI32!CreateCompatibleDC` at `0x1803fab2c`
- `GDI32!CreateCompatibleDC` at `0x1803fab04`
- `GDI32!CreateCompatibleDC` at `0x1803fab2c`
- `GDI32!SelectObject` at `0x1803fabd2`
- `GDI32!SelectObject` at `0x1803fabe7`
- `GDI32!SelectObject` at `0x1803faca7`
- `GDI32!SelectObject` at `0x1803facb9`
- `GDI32!SelectObject` at `0x1803fabd2`
- `GDI32!SelectObject` at `0x1803fabe7`
- `GDI32!SelectObject` at `0x1803faca7`
- `GDI32!SelectObject` at `0x1803facb9`
- `GDI32!DeleteDC` at `0x1803facce`
- `GDI32!DeleteDC` at `0x1803facf4`
- `GDI32!DeleteDC` at `0x1803facce`
- `GDI32!DeleteDC` at `0x1803facf4`
- `GDI32!BitBlt` at `0x1803fac3e`
- `GDI32!BitBlt` at `0x1803fac3e`
- `GDI32!GetObjectW` at `0x1803faac6`
- `GDI32!GetObjectW` at `0x1803faac6`
- `GDI32!StretchBlt` at `0x1803fac95`
- `GDI32!StretchBlt` at `0x1803fac95`

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
0x1803faa70  mov     [rsp-8+arg_8], rbx
0x1803faa75  push    rbp
0x1803faa76  push    rsi
0x1803faa77  push    rdi
0x1803faa78  push    r12
0x1803faa7a  push    r13
0x1803faa7c  push    r14
0x1803faa7e  push    r15
0x1803faa80  lea     rbp, [rsp-1Fh]
0x1803faa85  sub     rsp, 0E0h
0x1803faa8c  mov     rax, cs:__security_cookie
0x1803faa93  xor     rax, rsp
0x1803faa96  mov     [rbp+4Fh+var_38], rax
0x1803faa9a  mov     [rbp+4Fh+var_AC], r8d
0x1803faa9e  mov     [rbp+4Fh+var_B0], edx
0x1803faaa1  mov     r15, rcx
0x1803faaa4  xor     r14d, r14d
0x1803faaa7  xorps   xmm0, xmm0
0x1803faaaa  movups  [rbp+4Fh+pv], xmm0
0x1803faaae  movups  [rbp+4Fh+var_80], xmm0
0x1803faab2  test    rcx, rcx
0x1803faab5  jz      loc_1803FAD00
0x1803faabb  lea     r8, [rbp+4Fh+pv]; pv
0x1803faabf  lea     r12d, [r14+20h]
0x1803faac3  mov     edx, r12d; c
0x1803faac6  call    cs:__imp_GetObjectW
0x1803faacd  nop     dword ptr [rax+rax+00h]
0x1803faad2  test    eax, eax
0x1803faad4  jnz     short loc_1803FAAE3
0x1803faad6  call    ResultFromKnownLastError
0x1803faadb  test    eax, eax
0x1803faadd  js      loc_1803FAD00
0x1803faae3  xor     ecx, ecx; hWnd
0x1803faae5  call    cs:__imp_GetDC
0x1803faaec  nop     dword ptr [rax+rax+00h]
0x1803faaf1  mov     rsi, rax
0x1803faaf4  mov     [rbp+4Fh+var_A8], rax
0x1803faaf8  test    rax, rax
0x1803faafb  jz      loc_1803FAD00
0x1803fab01  mov     rcx, rax; hdc
0x1803fab04  call    cs:__imp_CreateCompatibleDC
0x1803fab0b  nop     dword ptr [rax+rax+00h]
0x1803fab10  mov     rbx, rax
0x1803fab13  mov     [rbp+4Fh+var_A0], rax
0x1803fab17  test    rax, rax
0x1803fab1a  jnz     short loc_1803FAB29
0x1803fab1c  call    ResultFromKnownLastError
0x1803fab21  test    eax, eax
0x1803fab23  js      loc_1803FACDA
0x1803fab29  mov     rcx, rsi; hdc
0x1803fab2c  call    cs:__imp_CreateCompatibleDC
0x1803fab33  nop     dword ptr [rax+rax+00h]
0x1803fab38  mov     rdi, rax
0x1803fab3b  mov     [rbp+4Fh+var_98], rax
0x1803fab3f  test    rax, rax
0x1803fab42  jnz     short loc_1803FAB51
0x1803fab44  call    ResultFromKnownLastError
0x1803fab49  test    eax, eax
0x1803fab4b  js      loc_1803FACC6
0x1803fab51  cmp     word ptr [rbp+4Fh+var_80+2], r12w
0x1803fab56  jnz     short loc_1803FABAC
0x1803fab58  mov     [rbp+4Fh+ppvBits], 0
0x1803fab60  mov     [rbp+4Fh+pbmi.bmiHeader.biSize], 28h ; '('
0x1803fab67  mov     eax, dword ptr [rbp+4Fh+pv+4]
0x1803fab6a  mov     [rbp+4Fh+pbmi.bmiHeader.biWidth], eax
0x1803fab6d  mov     eax, dword ptr [rbp+4Fh+pv+8]
0x1803fab70  mov     [rbp+4Fh+pbmi.bmiHeader.biHeight], eax
0x1803fab73  mov     dword ptr [rbp+4Fh+pbmi.bmiHeader.biPlanes], 200001h
0x1803fab7a  xorps   xmm0, xmm0
0x1803fab7d  xor     eax, eax
0x1803fab7f  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biCompression], xmm0
0x1803fab83  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x1803fab87  mov     [rsp+110h+offset], eax; offset
0x1803fab8b  mov     [rsp+110h+hSection], rax; hSection
0x1803fab90  lea     r9, [rbp+4Fh+ppvBits]; ppvBits
0x1803fab94  xor     r8d, r8d; usage
0x1803fab97  lea     rdx, [rbp+4Fh+pbmi]; pbmi
0x1803fab9b  mov     rcx, rsi; hdc
0x1803fab9e  call    cs:__imp_CreateDIBSection
0x1803faba5  nop     dword ptr [rax+rax+00h]
0x1803fabaa  jmp     short loc_1803FABB7
0x1803fabac  mov     edx, dword ptr [rbp+4Fh+pv+8]; cy
0x1803fabaf  mov     ecx, dword ptr [rbp+4Fh+pv+4]; cx
0x1803fabb2  call    ?_CreateColorBitmap@@YAPEAUHBITMAP__@@HH@Z; _CreateColorBitmap(int,int)
0x1803fabb7  mov     r14, rax
0x1803fabba  test    rax, rax
0x1803fabbd  jnz     short loc_1803FABCC
0x1803fabbf  call    ResultFromKnownLastError
0x1803fabc4  test    eax, eax
0x1803fabc6  js      loc_1803FACC6
0x1803fabcc  mov     rdx, r15; h
0x1803fabcf  mov     rcx, rbx; hdc
0x1803fabd2  call    cs:__imp_SelectObject
0x1803fabd9  nop     dword ptr [rax+rax+00h]
0x1803fabde  mov     r12, rax
0x1803fabe1  mov     rdx, r14; h
0x1803fabe4  mov     rcx, rdi; hdc
0x1803fabe7  call    cs:__imp_SelectObject
0x1803fabee  nop     dword ptr [rax+rax+00h]
0x1803fabf3  mov     r13, rax
0x1803fabf6  cmp     [rbp+4Fh+var_B0], 0
0x1803fabfa  jz      short loc_1803FAC5B
0x1803fabfc  xor     r15d, r15d
0x1803fabff  mov     ecx, dword ptr [rbp+4Fh+pv+4]
0x1803fac02  test    ecx, ecx
0x1803fac04  jle     loc_1803FACA1
0x1803fac0a  mov     esi, [rbp+4Fh+var_AC]
0x1803fac0d  sub     ecx, esi
0x1803fac0f  sub     ecx, r15d
0x1803fac12  mov     [rsp+110h+rop], 0CC0020h; rop
0x1803fac1a  mov     [rsp+110h+y1], 0; y1
0x1803fac22  mov     [rsp+110h+x1], r15d; x1
0x1803fac27  mov     qword ptr [rsp+110h+offset], rbx; hdcSrc
0x1803fac2c  mov     eax, dword ptr [rbp+4Fh+pv+8]
0x1803fac2f  mov     dword ptr [rsp+110h+hSection], eax; cy
0x1803fac33  mov     r9d, esi; cx
0x1803fac36  xor     r8d, r8d; y
0x1803fac39  mov     edx, ecx; x
0x1803fac3b  mov     rcx, rdi; hdc
0x1803fac3e  call    cs:__imp_BitBlt
0x1803fac45  nop     dword ptr [rax+rax+00h]
0x1803fac4a  add     r15d, esi
0x1803fac4d  mov     ecx, dword ptr [rbp+4Fh+pv+4]
0x1803fac50  cmp     r15d, ecx
0x1803fac53  jl      short loc_1803FAC0D
0x1803fac55  mov     rsi, [rbp+4Fh+var_A8]
0x1803fac59  jmp     short loc_1803FACA1
0x1803fac5b  mov     r9d, dword ptr [rbp+4Fh+pv+4]; wDest
0x1803fac5f  mov     eax, r9d
0x1803fac62  neg     eax
0x1803fac64  mov     [rsp+110h+var_C0], 0CC0020h; rop
0x1803fac6c  mov     ecx, dword ptr [rbp+4Fh+pv+8]
0x1803fac6f  mov     [rsp+110h+hSrc], ecx; hSrc
0x1803fac73  mov     [rsp+110h+rop], eax; wSrc
0x1803fac77  mov     [rsp+110h+y1], 0; ySrc
0x1803fac7f  mov     [rsp+110h+x1], r9d; xSrc
0x1803fac84  mov     qword ptr [rsp+110h+offset], rbx; hdcSrc
0x1803fac89  mov     dword ptr [rsp+110h+hSection], ecx; hDest
0x1803fac8d  xor     r8d, r8d; yDest
0x1803fac90  xor     edx, edx; xDest
0x1803fac92  mov     rcx, rdi; hdcDest
0x1803fac95  call    cs:__imp_StretchBlt
0x1803fac9c  nop     dword ptr [rax+rax+00h]
0x1803faca1  mov     rdx, r12; h
0x1803faca4  mov     rcx, rbx; hdc
0x1803faca7  call    cs:__imp_SelectObject
0x1803facae  nop     dword ptr [rax+rax+00h]
0x1803facb3  mov     rdx, r13; h
0x1803facb6  mov     rcx, rdi; hdc
0x1803facb9  call    cs:__imp_SelectObject
0x1803facc0  nop     dword ptr [rax+rax+00h]
0x1803facc5  nop
0x1803facc6  test    rdi, rdi
0x1803facc9  jz      short loc_1803FACDA
0x1803faccb  mov     rcx, rdi; hdc
0x1803facce  call    cs:__imp_DeleteDC
0x1803facd5  nop     dword ptr [rax+rax+00h]
0x1803facda  mov     rdx, rsi; hDC
0x1803facdd  xor     ecx, ecx; hWnd
0x1803facdf  call    cs:__imp_ReleaseDC
0x1803face6  nop     dword ptr [rax+rax+00h]
0x1803faceb  nop
0x1803facec  test    rbx, rbx
0x1803facef  jz      short loc_1803FAD00
0x1803facf1  mov     rcx, rbx; hdc
0x1803facf4  call    cs:__imp_DeleteDC
0x1803facfb  nop     dword ptr [rax+rax+00h]
0x1803fad00  mov     rax, r14
0x1803fad03  mov     rcx, [rbp+4Fh+var_38]
0x1803fad07  xor     rcx, rsp; StackCookie
0x1803fad0a  call    __security_check_cookie
0x1803fad0f  mov     rbx, [rsp+110h+arg_8]
0x1803fad17  add     rsp, 0E0h
0x1803fad1e  pop     r15
0x1803fad20  pop     r14
0x1803fad22  pop     r13
0x1803fad24  pop     r12
0x1803fad26  pop     rdi
0x1803fad27  pop     rsi
0x1803fad28  pop     rbp
0x1803fad29  retn
```
