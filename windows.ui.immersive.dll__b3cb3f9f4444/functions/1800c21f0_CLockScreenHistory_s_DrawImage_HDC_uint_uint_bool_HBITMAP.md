# CLockScreenHistory::_s_DrawImage(HDC__ *,uint,uint,bool,HBITMAP__ *)

- ea: `0x1800c21f0`
- end: `0x1800c2401`
- name: `?_s_DrawImage@CLockScreenHistory@@KAXPEAUHDC__@@II_NPEAUHBITMAP__@@@Z`
- size: `529`
- prototype: `void __usercall(HDC hdcDest@<rcx>, unsigned int wDest@<edx>, unsigned int hSrc@<r8d>, bool@<r9b>, HBITMAP)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800c20e0`

## callees

- `0x180054130`
- `0x180054ad4`
- `0x1800c21f0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800c222f`
- `GDI32!CreateCompatibleDC` at `0x1800c222f`
- `GDI32!DeleteDC` at `0x1800c23ca`
- `GDI32!DeleteDC` at `0x1800c23ca`
- `GDI32!SelectObject` at `0x1800c224d`
- `GDI32!SelectObject` at `0x1800c23bb`
- `GDI32!SelectObject` at `0x1800c224d`
- `GDI32!SelectObject` at `0x1800c23bb`
- `GDI32!GetObjectW` at `0x1800c2279`
- `GDI32!GetObjectW` at `0x1800c2279`
- `GDI32!StretchBlt` at `0x1800c23a9`
- `GDI32!StretchBlt` at `0x1800c23a9`

## pseudocode

```c
void __fastcall CLockScreenHistory::_s_DrawImage(HDC hdcDest, int wDest, int hSrc, unsigned __int8 a4, HGDIOBJ h)
{
  int v6; // r12d
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // rbp
  float v12; // xmm6_4
  int v13; // eax
  float v14; // xmm4_4
  int v15; // ebx
  signed int v16; // r9d
  int v17; // ecx
  int ySrc; // r11d
  int v19; // r10d
  int xSrc; // eax
  _BYTE pv[4]; // [rsp+60h] [rbp-C8h] BYREF
  int v22; // [rsp+64h] [rbp-C4h]
  int v23; // [rsp+68h] [rbp-C0h]

  v6 = a4;
  CompatibleDC = CreateCompatibleDC(hdcDest);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v11 = SelectObject(CompatibleDC, h);
    memset_0(pv, 0, 0x68u);
    if ( GetObjectW(h, 104, pv) )
    {
      v12 = (float)hSrc;
      v13 = v23;
      if ( v22 > v23 )
        v13 = v22;
      v14 = fmaxf(
              fmaxf(
                fmaxf(
                  v12 * (float)((float)v22 / (float)v23),
                  (float)(1.0 / (float)((float)v22 / (float)v23)) * (float)wDest),
                v12),
              (float)wDest)
          / (float)v13;
      v15 = (int)(float)((float)((float)wDest - (float)(v14 * (float)v22)) / (float)(v14 + v14));
      v16 = v22 + 2 * v15;
      v17 = (int)(float)((float)(v12 - (float)(v14 * (float)v23)) / (float)(v14 * 3.0));
      ySrc = -v17;
      if ( v17 >= 0 )
        ySrc = 0;
      if ( wDest < v16 )
        v16 = wDest;
      v19 = v17 + v23 + 2 * v17;
      if ( hSrc < v19 )
        v19 = hSrc;
      xSrc = ((_BYTE)v6 != 0 ? v16 - 1 : 0) - v15;
      if ( v15 >= 0 )
        xSrc = (_BYTE)v6 != 0 ? v16 - 1 : 0;
      StretchBlt(hdcDest, 0, 0, wDest, hSrc, hdcSrc, xSrc, ySrc, v16 * (2 * (v6 ^ 1) - 1), v19, 0xCC0020u);
    }
    SelectObject(hdcSrc, v11);
    DeleteDC(hdcSrc);
  }
}

```

## disassembly

```asm
0x1800c21f0  mov     rax, rsp
0x1800c21f3  push    rbx
0x1800c21f4  push    rbp
0x1800c21f5  push    rsi
0x1800c21f6  push    rdi
0x1800c21f7  push    r12
0x1800c21f9  push    r14
0x1800c21fb  push    r15
0x1800c21fd  sub     rsp, 0F0h
0x1800c2204  movaps  xmmword ptr [rax-48h], xmm6
0x1800c2208  mov     rax, cs:__security_cookie
0x1800c220f  xor     rax, rsp
0x1800c2212  mov     [rsp+128h+var_58], rax
0x1800c221a  mov     rbx, [rsp+128h+h]
0x1800c2222  mov     rsi, rcx
0x1800c2225  movzx   r12d, r9b
0x1800c2229  mov     r15d, r8d
0x1800c222c  mov     r14d, edx
0x1800c222f  call    cs:__imp_CreateCompatibleDC
0x1800c2236  nop     dword ptr [rax+rax+00h]
0x1800c223b  mov     rdi, rax
0x1800c223e  test    rax, rax
0x1800c2241  jz      loc_1800C23D6
0x1800c2247  mov     rdx, rbx; h
0x1800c224a  mov     rcx, rax; hdc
0x1800c224d  call    cs:__imp_SelectObject
0x1800c2254  nop     dword ptr [rax+rax+00h]
0x1800c2259  xor     edx, edx; Val
0x1800c225b  lea     rcx, [rsp+128h+pv]; void *
0x1800c2260  mov     rbp, rax
0x1800c2263  lea     r8d, [rdx+68h]; Size
0x1800c2267  call    memset_0
0x1800c226c  lea     r8, [rsp+128h+pv]; pv
0x1800c2271  mov     edx, 68h ; 'h'; c
0x1800c2276  mov     rcx, rbx; h
0x1800c2279  call    cs:__imp_GetObjectW
0x1800c2280  nop     dword ptr [rax+rax+00h]
0x1800c2285  test    eax, eax
0x1800c2287  jz      loc_1800C23B5
0x1800c228d  mov     edx, [rsp+128h+var_C4]
0x1800c2291  xorps   xmm6, xmm6
0x1800c2294  mov     r8d, [rsp+128h+var_C0]
0x1800c2299  xorps   xmm3, xmm3
0x1800c229c  movss   xmm0, cs:__real@3f800000
0x1800c22a4  cmp     edx, r8d
0x1800c22a7  cvtsi2ss xmm6, r15
0x1800c22ac  mov     eax, r8d
0x1800c22af  mov     [rsp+128h+rop], 0CC0020h; rop
0x1800c22b7  cmovg   eax, edx
0x1800c22ba  movd    xmm2, edx
0x1800c22be  movd    xmm5, r8d
0x1800c22c3  movaps  xmm4, xmm6
0x1800c22c6  cvtdq2ps xmm2, xmm2
0x1800c22c9  cvtdq2ps xmm5, xmm5
0x1800c22cc  movaps  xmm1, xmm2
0x1800c22cf  divss   xmm1, xmm5
0x1800c22d3  cvtsi2ss xmm3, r14
0x1800c22d8  divss   xmm0, xmm1
0x1800c22dc  mulss   xmm4, xmm1
0x1800c22e0  mulss   xmm0, xmm3
0x1800c22e4  maxss   xmm4, xmm0
0x1800c22e8  movd    xmm0, eax
0x1800c22ec  xor     eax, eax
0x1800c22ee  cvtdq2ps xmm0, xmm0
0x1800c22f1  maxss   xmm4, xmm6
0x1800c22f5  maxss   xmm4, xmm3
0x1800c22f9  divss   xmm4, xmm0
0x1800c22fd  movaps  xmm1, xmm4
0x1800c2300  movaps  xmm0, xmm4
0x1800c2303  mulss   xmm1, xmm2
0x1800c2307  addss   xmm0, xmm4
0x1800c230b  subss   xmm3, xmm1
0x1800c230f  movaps  xmm1, xmm4
0x1800c2312  mulss   xmm4, cs:__real@40400000
0x1800c231a  mulss   xmm1, xmm5
0x1800c231e  divss   xmm3, xmm0
0x1800c2322  subss   xmm6, xmm1
0x1800c2326  cvttss2si ebx, xmm3
0x1800c232a  divss   xmm6, xmm4
0x1800c232e  lea     r9d, [rdx+rbx*2]
0x1800c2332  cvttss2si ecx, xmm6
0x1800c2336  mov     r11d, ecx
0x1800c2339  neg     r11d
0x1800c233c  test    ecx, ecx
0x1800c233e  lea     r10d, [r8+rcx*2]
0x1800c2342  cmovns  r11d, eax
0x1800c2346  cmp     r14d, r9d
0x1800c2349  mov     al, r12b
0x1800c234c  cmovl   r9d, r14d
0x1800c2350  add     r10d, ecx
0x1800c2353  cmp     r15d, r10d
0x1800c2356  cmovl   r10d, r15d
0x1800c235a  neg     al
0x1800c235c  mov     [rsp+128h+hSrc], r10d; hSrc
0x1800c2361  lea     ecx, [r9-1]
0x1800c2365  sbb     r8d, r8d
0x1800c2368  mov     eax, r12d
0x1800c236b  xor     eax, 1
0x1800c236e  and     r8d, ecx
0x1800c2371  mov     rcx, rsi; hdcDest
0x1800c2374  lea     edx, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x1800c237b  mov     eax, r8d
0x1800c237e  imul    edx, r9d
0x1800c2382  sub     eax, ebx
0x1800c2384  test    ebx, ebx
0x1800c2386  mov     r9d, r14d; wDest
0x1800c2389  cmovns  eax, r8d
0x1800c238d  xor     r8d, r8d; yDest
0x1800c2390  mov     [rsp+128h+wSrc], edx; wSrc
0x1800c2394  xor     edx, edx; xDest
0x1800c2396  mov     [rsp+128h+ySrc], r11d; ySrc
0x1800c239b  mov     [rsp+128h+xSrc], eax; xSrc
0x1800c239f  mov     [rsp+128h+hdcSrc], rdi; hdcSrc
0x1800c23a4  mov     [rsp+128h+hDest], r15d; hDest
0x1800c23a9  call    cs:__imp_StretchBlt
0x1800c23b0  nop     dword ptr [rax+rax+00h]
0x1800c23b5  mov     rdx, rbp; h
0x1800c23b8  mov     rcx, rdi; hdc
0x1800c23bb  call    cs:__imp_SelectObject
0x1800c23c2  nop     dword ptr [rax+rax+00h]
0x1800c23c7  mov     rcx, rdi; hdc
0x1800c23ca  call    cs:__imp_DeleteDC
0x1800c23d1  nop     dword ptr [rax+rax+00h]
0x1800c23d6  mov     rcx, [rsp+128h+var_58]
0x1800c23de  xor     rcx, rsp; StackCookie
0x1800c23e1  call    __security_check_cookie
0x1800c23e6  movaps  xmm6, [rsp+128h+var_48]
0x1800c23ee  add     rsp, 0F0h
0x1800c23f5  pop     r15
0x1800c23f7  pop     r14
0x1800c23f9  pop     r12
0x1800c23fb  pop     rdi
0x1800c23fc  pop     rsi
0x1800c23fd  pop     rbp
0x1800c23fe  pop     rbx
0x1800c23ff  retn
```
