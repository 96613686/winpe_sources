# DrawCircle(Gdiplus::Graphics *,uint,bool)

- ea: `0x18000e558`
- end: `0x18000e80e`
- name: `?DrawCircle@@YAXPEAVGraphics@Gdiplus@@I_N@Z`
- size: `694`
- prototype: `void __fastcall(struct Gdiplus::Graphics *, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012338`

## callees

- `0x180002f7c`
- `0x18000cfd0`
- `0x18000dd10`
- `0x18000e46c`
- `0x18000e814`

## import_xrefs

- `gdiplus!GdipSetPenLineJoin` at `0x18000e609`
- `gdiplus!GdipSetPenLineJoin` at `0x18000e609`
- `gdiplus!GdipDeletePen` at `0x18000e7c9`
- `gdiplus!GdipDeletePen` at `0x18000e7d3`
- `gdiplus!GdipDeletePen` at `0x18000e7c9`
- `gdiplus!GdipDeletePen` at `0x18000e7d3`

## pseudocode

```c
void __fastcall DrawCircle(struct Gdiplus::Graphics *a1, int a2, unsigned __int8 a3)
{
  int v5; // edi
  double v6; // xmm11_8
  double v7; // xmm12_8
  double v8; // xmm10_8
  int v9; // eax
  int v10; // ecx
  int v11; // ebx
  double v12; // xmm6_8
  double v13; // xmm9_8
  double v14; // xmm7_8
  int v15; // ebx
  double v16; // xmm12_8
  __int64 v17; // [rsp+48h] [rbp-79h] BYREF
  int v18; // [rsp+50h] [rbp-71h]
  _QWORD v19[2]; // [rsp+58h] [rbp-69h] BYREF
  _QWORD v20[18]; // [rsp+68h] [rbp-59h] BYREF

  v5 = a3;
  v6 = (double)a2;
  v7 = (double)(a2 + 16);
  v8 = v6 - sqrt(v6 * v6 - 64.0);
  Gdiplus::Pen::Pen((Gdiplus::Pen *)v19, (const struct Gdiplus::Color *)&g_clrStroke, 10.0);
  Gdiplus::Pen::Pen((Gdiplus::Pen *)&v17, (const struct Gdiplus::Color *)&g_clrEdge, 1.0);
  v9 = GdipSetPenLineJoin(v17, 2);
  v10 = v18;
  if ( v9 )
    v10 = v9;
  v11 = 2 * a2;
  v18 = v10;
  Gdiplus::Graphics::DrawEllipse(a1, v19, 16, 16, v11, v11);
  Gdiplus::Graphics::DrawEllipse(a1, &v17, 11, 11, v11 + 10, v11 + 10);
  Gdiplus::Graphics::DrawEllipse(a1, &v17, 21, 21, v11 - 10, v11 - 10);
  memset(v20, 0, 24);
  v12 = v7 - (double)(8 * (2 * v5 - 1));
  v13 = v7 - v6 + v8;
  CalculateTriPoints(v12, v13, 2 * v5 - 1, 1, 0.0, 1, 0, (struct TRI_POINTS *)v20);
  DrawArrow(a1, (struct TRI_POINTS *)v20);
  v14 = v7 + v6 - v8;
  CalculateTriPoints(v14, v12, 1, 2 * v5 - 1, 0.0, 0, 0, (struct TRI_POINTS *)v20);
  DrawArrow(a1, (struct TRI_POINTS *)v20);
  v15 = 2 * (v5 ^ 1) - 1;
  v16 = v7 - (double)(8 * v15);
  CalculateTriPoints(v16, v14, v15, -1, 0.0, 1, 0, (struct TRI_POINTS *)v20);
  DrawArrow(a1, (struct TRI_POINTS *)v20);
  CalculateTriPoints(v13, v16, -1, v15, 0.0, 0, 0, (struct TRI_POINTS *)v20);
  DrawArrow(a1, (struct TRI_POINTS *)v20);
  GdipDeletePen(v17);
  GdipDeletePen(v19[0]);
}

```

## disassembly

```asm
0x18000e558  mov     rax, rsp
0x18000e55b  push    rbp
0x18000e55c  push    rbx
0x18000e55d  push    rsi
0x18000e55e  push    rdi
0x18000e55f  push    r15
0x18000e561  lea     rbp, [rax-5Fh]
0x18000e565  sub     rsp, 0F0h
0x18000e56c  movaps  xmmword ptr [rax-38h], xmm6
0x18000e570  mov     rsi, rcx
0x18000e573  movaps  xmmword ptr [rax-48h], xmm7
0x18000e577  movaps  xmmword ptr [rax-58h], xmm8
0x18000e57c  movaps  xmmword ptr [rax-68h], xmm9
0x18000e581  movaps  xmmword ptr [rax-78h], xmm10
0x18000e586  movaps  xmmword ptr [rax-88h], xmm11
0x18000e58e  xorps   xmm11, xmm11
0x18000e592  mov     ebx, edx
0x18000e594  movaps  xmmword ptr [rax-98h], xmm12
0x18000e59c  movzx   edi, r8b
0x18000e5a0  cvtsi2sd xmm11, rbx
0x18000e5a5  movaps  xmm0, xmm11
0x18000e5a9  mulsd   xmm0, xmm11
0x18000e5ae  subsd   xmm0, cs:__real@4050000000000000; X
0x18000e5b6  call    sqrt
0x18000e5bb  movss   xmm2, cs:__real@41200000; float
0x18000e5c3  lea     ecx, [rbx+10h]
0x18000e5c6  xorps   xmm12, xmm12
0x18000e5ca  lea     rdx, ?g_clrStroke@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x18000e5d1  movaps  xmm10, xmm11
0x18000e5d5  cvtsi2sd xmm12, rcx
0x18000e5da  lea     rcx, [rbp+57h+var_C0]; this
0x18000e5de  subsd   xmm10, xmm0
0x18000e5e3  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18000e5e8  movss   xmm2, cs:__real@3f800000; float
0x18000e5f0  lea     rdx, ?g_clrEdge@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x18000e5f7  lea     rcx, [rbp+57h+var_D0]; this
0x18000e5fb  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18000e600  mov     rcx, [rbp+57h+var_D0]
0x18000e604  mov     edx, 2
0x18000e609  call    cs:__imp_GdipSetPenLineJoin
0x18000e60f  mov     ecx, [rbp+57h+var_C8]
0x18000e612  lea     rdx, [rbp+57h+var_C0]
0x18000e616  xor     r15d, r15d
0x18000e619  test    eax, eax
0x18000e61b  cmovnz  ecx, eax
0x18000e61e  add     ebx, ebx
0x18000e620  lea     r8d, [r15+10h]
0x18000e624  mov     [rbp+57h+var_C8], ecx
0x18000e627  mov     dword ptr [rsp+110h+var_E8], ebx
0x18000e62b  mov     rcx, rsi
0x18000e62e  mov     r9d, r8d
0x18000e631  mov     dword ptr [rsp+110h+var_F0], ebx
0x18000e635  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x18000e63a  lea     eax, [rbx+0Ah]
0x18000e63d  mov     rcx, rsi
0x18000e640  lea     r8d, [r15+0Bh]
0x18000e644  mov     dword ptr [rsp+110h+var_E8], eax
0x18000e648  mov     r9d, r8d
0x18000e64b  mov     dword ptr [rsp+110h+var_F0], eax
0x18000e64f  lea     rdx, [rbp+57h+var_D0]
0x18000e653  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x18000e658  lea     eax, [rbx-0Ah]
0x18000e65b  mov     rcx, rsi
0x18000e65e  lea     r8d, [r15+15h]
0x18000e662  mov     dword ptr [rsp+110h+var_E8], eax
0x18000e666  mov     r9d, r8d
0x18000e669  mov     dword ptr [rsp+110h+var_F0], eax
0x18000e66d  lea     rdx, [rbp+57h+var_D0]
0x18000e671  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x18000e676  lea     ebx, ds:0FFFFFFFFFFFFFFFFh[rdi*2]
0x18000e67d  mov     [rbp+57h+var_B0], r15
0x18000e681  lea     eax, ds:0[rbx*8]
0x18000e688  mov     [rbp+57h+var_A8], r15
0x18000e68c  movd    xmm0, eax
0x18000e690  lea     r9d, [r15+1]; int
0x18000e694  cvtdq2pd xmm0, xmm0
0x18000e698  mov     [rbp+57h+var_A0], r15
0x18000e69c  lea     rax, [rbp+57h+var_B0]
0x18000e6a0  mov     [rsp+110h+var_D8], rax; struct TRI_POINTS *
0x18000e6a5  mov     r8d, ebx; int
0x18000e6a8  mov     [rsp+110h+var_E0], r15b; bool
0x18000e6ad  mov     [rsp+110h+var_E8], 1; bool
0x18000e6b2  movaps  xmm9, xmm12
0x18000e6b6  movaps  xmm6, xmm12
0x18000e6ba  subsd   xmm9, xmm11
0x18000e6bf  xorps   xmm8, xmm8
0x18000e6c3  subsd   xmm6, xmm0
0x18000e6c7  movsd   [rsp+110h+var_F0], xmm8; double
0x18000e6ce  addsd   xmm9, xmm10
0x18000e6d3  movaps  xmm1, xmm9; double
0x18000e6d7  movaps  xmm0, xmm6; double
0x18000e6da  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18000e6df  lea     rdx, [rbp+57h+var_B0]; struct TRI_POINTS *
0x18000e6e3  mov     rcx, rsi; struct Gdiplus::Graphics *
0x18000e6e6  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x18000e6eb  movaps  xmm7, xmm12
0x18000e6ef  lea     rax, [rbp+57h+var_B0]
0x18000e6f3  mov     [rsp+110h+var_D8], rax; struct TRI_POINTS *
0x18000e6f8  addsd   xmm7, xmm11
0x18000e6fd  mov     [rsp+110h+var_E0], r15b; bool
0x18000e702  lea     r8d, [r15+1]; int
0x18000e706  mov     [rsp+110h+var_E8], r15b; bool
0x18000e70b  mov     r9d, ebx; int
0x18000e70e  movaps  xmm1, xmm6; double
0x18000e711  movsd   [rsp+110h+var_F0], xmm8; double
0x18000e718  subsd   xmm7, xmm10
0x18000e71d  movaps  xmm0, xmm7; double
0x18000e720  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18000e725  lea     rdx, [rbp+57h+var_B0]; struct TRI_POINTS *
0x18000e729  mov     rcx, rsi; struct Gdiplus::Graphics *
0x18000e72c  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x18000e731  mov     eax, edi
0x18000e733  movaps  xmm1, xmm7; double
0x18000e736  xor     eax, 1
0x18000e739  or      edi, 0FFFFFFFFh
0x18000e73c  mov     r9d, edi; int
0x18000e73f  lea     ebx, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x18000e746  lea     eax, ds:0[rbx*8]
0x18000e74d  mov     r8d, ebx; int
0x18000e750  movd    xmm0, eax
0x18000e754  lea     rax, [rbp+57h+var_B0]
0x18000e758  mov     [rsp+110h+var_D8], rax; struct TRI_POINTS *
0x18000e75d  cvtdq2pd xmm0, xmm0
0x18000e761  mov     [rsp+110h+var_E0], r15b; bool
0x18000e766  mov     [rsp+110h+var_E8], 1; bool
0x18000e76b  movsd   [rsp+110h+var_F0], xmm8; double
0x18000e772  subsd   xmm12, xmm0
0x18000e777  movaps  xmm0, xmm12; double
0x18000e77b  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18000e780  lea     rdx, [rbp+57h+var_B0]; struct TRI_POINTS *
0x18000e784  mov     rcx, rsi; struct Gdiplus::Graphics *
0x18000e787  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x18000e78c  lea     rax, [rbp+57h+var_B0]
0x18000e790  mov     r9d, ebx; int
0x18000e793  mov     [rsp+110h+var_D8], rax; struct TRI_POINTS *
0x18000e798  mov     r8d, edi; int
0x18000e79b  mov     [rsp+110h+var_E0], r15b; bool
0x18000e7a0  movaps  xmm1, xmm12; double
0x18000e7a4  mov     [rsp+110h+var_E8], r15b; bool
0x18000e7a9  movaps  xmm0, xmm9; double
0x18000e7ad  movsd   [rsp+110h+var_F0], xmm8; double
0x18000e7b4  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18000e7b9  lea     rdx, [rbp+57h+var_B0]; struct TRI_POINTS *
0x18000e7bd  mov     rcx, rsi; struct Gdiplus::Graphics *
0x18000e7c0  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x18000e7c5  mov     rcx, [rbp+57h+var_D0]
0x18000e7c9  call    cs:__imp_GdipDeletePen
0x18000e7cf  mov     rcx, [rbp+57h+var_C0]
0x18000e7d3  call    cs:__imp_GdipDeletePen
0x18000e7d9  lea     r11, [rsp+110h+var_20]
0x18000e7e1  movaps  xmm6, xmmword ptr [r11-10h]
0x18000e7e6  movaps  xmm7, xmmword ptr [r11-20h]
0x18000e7eb  movaps  xmm8, xmmword ptr [r11-30h]
0x18000e7f0  movaps  xmm9, xmmword ptr [r11-40h]
0x18000e7f5  movaps  xmm10, xmmword ptr [r11-50h]
0x18000e7fa  movaps  xmm11, xmmword ptr [r11-60h]
0x18000e7ff  movaps  xmm12, xmmword ptr [r11-70h]
0x18000e804  mov     rsp, r11
0x18000e807  pop     r15
0x18000e809  pop     rdi
0x18000e80a  pop     rsi
0x18000e80b  pop     rbx
0x18000e80c  pop     rbp
0x18000e80d  retn
```
