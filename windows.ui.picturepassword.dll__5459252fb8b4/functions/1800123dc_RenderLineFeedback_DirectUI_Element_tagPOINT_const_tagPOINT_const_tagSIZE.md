# _RenderLineFeedback(DirectUI::Element *,tagPOINT const &,tagPOINT const &,tagSIZE *)

- ea: `0x1800123dc`
- end: `0x180012a8d`
- name: `?_RenderLineFeedback@@YAJPEAVElement@DirectUI@@AEBUtagPOINT@@1PEAUtagSIZE@@@Z`
- size: `1713`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, const struct tagPOINT *, const struct tagPOINT *, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180010d70`

## callees

- `0x180002610`
- `0x180002f7c`
- `0x1800092b8`
- `0x18000cc68`
- `0x18000cfd0`
- `0x18000dab8`
- `0x18000dd10`
- `0x18000e46c`
- `0x18000e8a0`
- `0x180011220`
- `0x1800123dc`
- `0x180012bd0`

## import_xrefs

- `gdiplus!GdipDrawPolygonI` at `0x1800127b7`
- `gdiplus!GdipDrawPolygonI` at `0x1800127b7`
- `gdiplus!GdipDeletePen` at `0x180012a1a`
- `gdiplus!GdipDeletePen` at `0x180012a24`
- `gdiplus!GdipDeletePen` at `0x180012a1a`
- `gdiplus!GdipDeletePen` at `0x180012a24`
- `gdiplus!GdipDrawLineI` at `0x180012799`
- `gdiplus!GdipDrawLineI` at `0x180012799`
- `gdiplus!GdipDisposeImage` at `0x180012a2e`
- `gdiplus!GdipDisposeImage` at `0x180012a2e`

## pseudocode

```c
__int64 __fastcall _RenderLineFeedback(
        struct DirectUI::Element *a1,
        const struct tagPOINT *a2,
        const struct tagPOINT *a3,
        struct tagSIZE *a4)
{
  LONG x; // ebx
  struct tagSIZE *v5; // r13
  LONG y; // esi
  int v7; // eax
  double v9; // xmm9_8
  double v10; // xmm8_8
  bool v11; // r14
  double v12; // xmm7_8
  __m128i v13; // xmm1
  __m128i v14; // xmm0
  int v15; // r9d
  int v16; // r8d
  double v17; // xmm1_8
  double v18; // xmm0_8
  int v19; // r9d
  int v20; // r8d
  __m128i v21; // xmm1
  __m128i v22; // xmm0
  double v23; // xmm1_8
  int v24; // r9d
  int v25; // r15d
  int v26; // r10d
  int v27; // r12d
  unsigned int v28; // r11d
  int v29; // r8d
  int v30; // eax
  int v31; // edx
  int v32; // eax
  struct Gdiplus::Graphics *v33; // rsi
  int Error; // ebx
  unsigned int v35; // ecx
  __m128i v36; // xmm11
  int v37; // edi
  int v38; // ebx
  int v39; // r9d
  int v40; // r8d
  double v41; // xmm10_8
  double v42; // xmm11_8
  int v43; // r9d
  int v44; // r8d
  double v45; // xmm12_8
  double v46; // xmm13_8
  int v47; // r15d
  unsigned int v48; // ebx
  int v49; // eax
  int v50; // eax
  int v51; // r9d
  int v52; // r8d
  int v53; // r9d
  int v54; // r8d
  double v55; // xmm10_8
  int v56; // edi
  __m128i v57; // xmm0
  int v58; // ebx
  double v59; // xmm10_8
  double v60; // xmm15_8
  int v61; // eax
  double v62; // xmm0_8
  double v63; // xmm2_8
  double v64; // xmm12_8
  double v65; // xmm2_8
  double v66; // xmm1_8
  int v67; // r9d
  int v68; // r8d
  __m128i v69; // xmm0
  int v71; // [rsp+30h] [rbp-D8h]
  __int64 v72; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+50h] [rbp-B8h]
  __int64 v74; // [rsp+58h] [rbp-B0h]
  __int64 v75; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+68h] [rbp-A0h]
  __int64 v77; // [rsp+70h] [rbp-98h]
  __int64 v78; // [rsp+78h] [rbp-90h] BYREF
  __int64 v79; // [rsp+80h] [rbp-88h]
  __int64 v80; // [rsp+88h] [rbp-80h]
  int v81; // [rsp+90h] [rbp-78h]
  unsigned int v82; // [rsp+94h] [rbp-74h]
  const struct tagPOINT *v83; // [rsp+98h] [rbp-70h]
  __int64 v84; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-60h]
  struct tagSIZE *v86; // [rsp+B8h] [rbp-50h]
  struct DirectUI::Element *v87; // [rsp+C0h] [rbp-48h]
  __int64 v88; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v89; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v90[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-18h]
  __int128 v92; // [rsp+100h] [rbp-8h] BYREF
  __int64 v93; // [rsp+110h] [rbp+8h]
  __int64 v94; // [rsp+118h] [rbp+10h]
  __int64 v95; // [rsp+120h] [rbp+18h]

  v86 = a4;
  *a4 = 0;
  x = a3->x;
  v5 = a4;
  y = a3->y;
  v7 = a3->x - a2->x;
  v83 = a3;
  v87 = a1;
  v9 = (double)v7;
  v10 = (double)(y - a2->y);
  if ( v10 == 0.0 )
  {
    v11 = 1;
    v12 = 0.0;
  }
  else
  {
    v11 = 0;
    v12 = v9 / v10;
  }
  v13 = _mm_cvtsi32_si128(a2->y);
  v14 = _mm_cvtsi32_si128(a2->x);
  v15 = 1;
  v16 = 1;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  *(_QWORD *)&v17 = *(_OWORD *)&_mm_cvtepi32_pd(v13);
  if ( v10 < 0.0 )
    v15 = -1;
  *(_QWORD *)&v18 = *(_OWORD *)&_mm_cvtepi32_pd(v14);
  if ( v9 < 0.0 )
    v16 = -1;
  CalculateTriPoints(v18, v17, v16, v15, v12, v11, 0, (struct TRI_POINTS *)&v78);
  v19 = 1;
  v20 = 1;
  v21 = _mm_cvtsi32_si128(y);
  v22 = _mm_cvtsi32_si128(x);
  if ( v10 < 0.0 )
    v19 = -1;
  *(_QWORD *)&v23 = *(_OWORD *)&_mm_cvtepi32_pd(v21);
  if ( v9 < 0.0 )
    v20 = -1;
  CalculateTriPoints(_mm_cvtepi32_pd(v22).m128d_f64[0], v23, v20, v19, v12, v11, 0, (struct TRI_POINTS *)&v75);
  v24 = 0;
  v25 = v78;
  v26 = 0;
  v27 = HIDWORD(v78);
  v28 = 0;
  HIDWORD(v92) = HIDWORD(v79);
  v93 = v75;
  v94 = v76;
  v95 = v77;
  LODWORD(v92) = v78;
  *(_QWORD *)((char *)&v92 + 4) = __PAIR64__(v79, HIDWORD(v78));
  do
  {
    v29 = *((_DWORD *)&v92 + 2 * (int)v28);
    v30 = v29;
    v31 = *((_DWORD *)&v92 + 2 * (int)v28 + 1);
    if ( v29 >= v25 )
      v30 = v25;
    v25 = v30;
    v32 = *((_DWORD *)&v92 + 2 * (int)v28 + 1);
    if ( v31 >= v27 )
      v32 = v27;
    v27 = v32;
    if ( v29 <= v24 )
      v29 = v24;
    v24 = v29;
    if ( v31 <= v26 )
      v31 = v26;
    ++v28;
    v26 = v31;
  }
  while ( v28 < 5 );
  Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v90, v29 - v25 + 1, v31 - v32 + 1);
  v33 = Gdiplus::Graphics::FromImage((struct Image *)v90);
  if ( v33 )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  if ( Error >= 0 )
  {
    Gdiplus::Graphics::SetSmoothingMode(v33);
    Gdiplus::Pen::Pen((Gdiplus::Pen *)&v89, (const struct Gdiplus::Color *)&g_clrStroke, 10.0);
    Gdiplus::Pen::Pen((Gdiplus::Pen *)&v88, (const struct Gdiplus::Color *)&g_clrEdge, 1.0);
    v35 = a2->x - v25;
    v81 = a2->y - v27;
    v82 = v35;
    v36 = _mm_cvtsi32_si128(v35);
    v37 = v83->x - v25;
    v38 = v83->y - v27;
    v72 = 0;
    v73 = 0;
    v39 = 1;
    v40 = 1;
    v84 = 0;
    v85 = 0;
    v41 = (double)v81;
    if ( v10 < 0.0 )
      v39 = -1;
    *(_QWORD *)&v42 = *(_OWORD *)&_mm_cvtepi32_pd(v36);
    if ( v9 < 0.0 )
      v40 = -1;
    CalculateTriPoints(v42, v41, v40, v39, v12, v11, 1, (struct TRI_POINTS *)&v72);
    v43 = 1;
    v44 = 1;
    v45 = (double)v38;
    if ( v10 < 0.0 )
      v43 = -1;
    v46 = (double)v37;
    if ( v9 < 0.0 )
      v44 = -1;
    CalculateTriPoints(v46, v45, v44, v43, v12, v11, 1, (struct TRI_POINTS *)&v84);
    *(_QWORD *)&v92 = v72;
    *((_QWORD *)&v92 + 1) = v84;
    v93 = v85;
    v94 = v73;
    v47 = v81;
    v71 = v38;
    v48 = v82;
    v49 = GdipDrawLineI(*(_QWORD *)v33, v89, v82, (unsigned int)v81, v37, v71);
    if ( v49 )
      *((_DWORD *)v33 + 2) = v49;
    v50 = GdipDrawPolygonI(*(_QWORD *)v33, v88, &v92, 4);
    if ( v50 )
      *((_DWORD *)v33 + 2) = v50;
    v51 = 1;
    v52 = 1;
    if ( v10 < 0.0 )
      v51 = -1;
    if ( v9 < 0.0 )
      v52 = -1;
    CalculateTriPoints(v42, v41, v52, v51, v12, v11, 0, (struct TRI_POINTS *)&v78);
    v53 = 1;
    v54 = 1;
    if ( v10 < 0.0 )
      v53 = -1;
    if ( v9 < 0.0 )
      v54 = -1;
    CalculateTriPoints(v46, v45, v54, v53, v12, v11, 0, (struct TRI_POINTS *)&v75);
    DrawArrow(v33, (struct TRI_POINTS *)&v78);
    DrawArrow(v33, (struct TRI_POINTS *)&v75);
    v55 = sqrt(v10 * v10 + v9 * v9);
    v56 = (int)(v55 / 250.0);
    if ( v56 > 0 )
    {
      v57 = _mm_cvtsi32_si128(v48);
      v58 = 1;
      v83 = (const struct tagPOINT *)*(_OWORD *)&_mm_cvtepi32_pd(v57);
      v59 = v55 / (double)v56;
      v60 = (double)v47;
      if ( v56 > 1 )
      {
        do
        {
          if ( v11 )
          {
            v61 = v47;
            if ( v9 >= 0.0 )
              v62 = DOUBLE_1_0;
            else
              v62 = DOUBLE_N1_0;
            v63 = (double)v58 * v59 * v62;
          }
          else
          {
            if ( v10 >= 0.0 )
              v64 = DOUBLE_1_0;
            else
              v64 = DOUBLE_N1_0;
            v65 = sqrt((double)v58 * v59 * ((double)v58 * v59) / (v12 * v12 + 1.0)) * v64 + v60;
            v66 = v65 + 0.49;
            v63 = (v65 - v60) * v12;
            v61 = (int)v66;
          }
          v67 = 1;
          v68 = 1;
          v72 = 0;
          v73 = 0;
          v74 = 0;
          if ( v10 < 0.0 )
            v67 = -1;
          v69 = _mm_cvtsi32_si128((int)(*(double *)&v83 + v63 + 0.49));
          if ( v9 < 0.0 )
            v68 = -1;
          CalculateTriPoints(
            _mm_cvtepi32_pd(v69).m128d_f64[0],
            (double)v61,
            v68,
            v67,
            v12,
            v11,
            0,
            (struct TRI_POINTS *)&v72);
          DrawArrow(v33, (struct TRI_POINTS *)&v72);
          ++v58;
        }
        while ( v58 < v56 );
        v5 = v86;
      }
    }
    Error = _SetFeedBackDUIElement(v87, (struct Gdiplus::Bitmap *)v90, v5);
    if ( v33 )
      Gdiplus::Graphics::`scalar deleting destructor'(v33);
    GdipDeletePen(v88);
    GdipDeletePen(v89);
  }
  GdipDisposeImage(v91);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800123dc  mov     rax, rsp
0x1800123df  push    rbp
0x1800123e0  push    rbx
0x1800123e1  push    rsi
0x1800123e2  push    rdi
0x1800123e3  push    r12
0x1800123e5  push    r13
0x1800123e7  push    r14
0x1800123e9  push    r15
0x1800123eb  lea     rbp, [rax-108h]
0x1800123f2  sub     rsp, 1C8h
0x1800123f9  movaps  xmmword ptr [rax-58h], xmm6
0x1800123fd  movaps  xmmword ptr [rax-68h], xmm7
0x180012401  movaps  xmmword ptr [rax-78h], xmm8
0x180012406  movaps  xmmword ptr [rax-88h], xmm9
0x18001240e  movaps  xmmword ptr [rax-98h], xmm10
0x180012416  movaps  xmmword ptr [rax-0A8h], xmm11
0x18001241e  movaps  xmmword ptr [rax-0B8h], xmm12
0x180012426  movaps  xmmword ptr [rax-0C8h], xmm13
0x18001242e  movaps  xmmword ptr [rax-0D8h], xmm15
0x180012436  mov     rax, cs:__security_cookie
0x18001243d  xor     rax, rsp
0x180012440  mov     [rbp+100h+var_E0], rax
0x180012444  xor     r15d, r15d
0x180012447  mov     [rbp+100h+var_150], r9
0x18001244b  mov     [r9], r15
0x18001244e  xorps   xmm6, xmm6
0x180012451  mov     ebx, [r8]
0x180012454  mov     r13, r9
0x180012457  mov     esi, [r8+4]
0x18001245b  mov     eax, ebx
0x18001245d  sub     eax, [rdx]
0x18001245f  lea     r12d, [r15+1]
0x180012463  mov     [rbp+100h+var_170], r8
0x180012467  mov     rdi, rdx
0x18001246a  mov     [rbp+100h+var_148], rcx
0x18001246e  movd    xmm9, eax
0x180012473  mov     eax, esi
0x180012475  sub     eax, [rdx+4]
0x180012478  cvtdq2pd xmm9, xmm9
0x18001247d  movd    xmm8, eax
0x180012482  cvtdq2pd xmm8, xmm8
0x180012487  ucomisd xmm8, xmm6
0x18001248c  jp      short loc_180012498
0x18001248e  jnz     short loc_180012498
0x180012490  mov     r14b, r12b
0x180012493  xorps   xmm7, xmm7
0x180012496  jmp     short loc_1800124A4
0x180012498  movaps  xmm7, xmm9
0x18001249c  mov     r14b, r15b
0x18001249f  divsd   xmm7, xmm8
0x1800124a4  movd    xmm1, dword ptr [rdx+4]
0x1800124a9  or      eax, 0FFFFFFFFh
0x1800124ac  movd    xmm0, dword ptr [rdx]
0x1800124b0  mov     r9d, r12d
0x1800124b3  comisd  xmm6, xmm8
0x1800124b8  mov     r8d, r12d
0x1800124bb  mov     [rsp+200h+var_190], r15
0x1800124c0  mov     [rsp+200h+var_188], r15
0x1800124c5  mov     [rbp+100h+var_180], r15
0x1800124c9  mov     [rsp+200h+var_1A8], r15
0x1800124ce  mov     [rsp+200h+var_1A0], r15
0x1800124d3  mov     [rsp+200h+var_198], r15
0x1800124d8  cvtdq2pd xmm1, xmm1; double
0x1800124dc  cmova   r9d, eax; int
0x1800124e0  comisd  xmm6, xmm9
0x1800124e5  cvtdq2pd xmm0, xmm0; double
0x1800124e9  cmova   r8d, eax; int
0x1800124ed  lea     rax, [rsp+200h+var_190]
0x1800124f2  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x1800124f7  mov     [rsp+200h+var_1D0], r15b; bool
0x1800124fc  mov     [rsp+200h+var_1D8], r14b; bool
0x180012501  movsd   [rsp+200h+var_1E0], xmm7; double
0x180012507  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18001250c  comisd  xmm6, xmm8
0x180012511  mov     eax, 0FFFFFFFFh
0x180012516  mov     r9d, r12d
0x180012519  mov     r8d, r12d
0x18001251c  movd    xmm1, esi
0x180012520  movd    xmm0, ebx
0x180012524  cmova   r9d, eax; int
0x180012528  comisd  xmm6, xmm9
0x18001252d  cvtdq2pd xmm1, xmm1; double
0x180012531  cmova   r8d, eax; int
0x180012535  lea     rax, [rsp+200h+var_1A8]
0x18001253a  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x18001253f  mov     [rsp+200h+var_1D0], r15b; bool
0x180012544  mov     [rsp+200h+var_1D8], r14b; bool
0x180012549  cvtdq2pd xmm0, xmm0; double
0x18001254d  movsd   [rsp+200h+var_1E0], xmm7; double
0x180012553  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x180012558  mov     eax, dword ptr [rsp+200h+var_188]
0x18001255c  xor     r9d, r9d
0x18001255f  mov     r15d, dword ptr [rsp+200h+var_190]
0x180012564  xor     r10d, r10d
0x180012567  mov     r12d, dword ptr [rsp+200h+var_190+4]
0x18001256c  xor     r11d, r11d
0x18001256f  mov     dword ptr [rbp+100h+var_104+4], eax
0x180012572  mov     eax, dword ptr [rsp+200h+var_188+4]
0x180012576  mov     dword ptr [rbp+100h+var_104+8], eax
0x180012579  mov     eax, dword ptr [rsp+200h+var_1A8]
0x18001257d  mov     dword ptr [rbp+100h+var_F8], eax
0x180012580  mov     eax, dword ptr [rsp+200h+var_1A8+4]
0x180012584  mov     dword ptr [rbp+100h+var_F8+4], eax
0x180012587  mov     eax, dword ptr [rsp+200h+var_1A0]
0x18001258b  mov     dword ptr [rbp+100h+var_F0], eax
0x18001258e  mov     eax, dword ptr [rsp+200h+var_1A0+4]
0x180012592  mov     dword ptr [rbp+100h+var_F0+4], eax
0x180012595  mov     eax, dword ptr [rsp+200h+var_198]
0x180012599  mov     dword ptr [rbp+100h+var_E8], eax
0x18001259c  mov     eax, dword ptr [rsp+200h+var_198+4]
0x1800125a0  mov     dword ptr [rbp+100h+var_E8+4], eax
0x1800125a3  mov     [rbp+100h+var_108], r15d
0x1800125a7  mov     dword ptr [rbp+100h+var_104], r12d
0x1800125ab  movsxd  rcx, r11d
0x1800125ae  mov     r8d, [rbp+rcx*8+100h+var_108]
0x1800125b3  mov     eax, r8d
0x1800125b6  mov     edx, dword ptr [rbp+rcx*8+100h+var_104]
0x1800125ba  cmp     r8d, r15d
0x1800125bd  cmovge  eax, r15d
0x1800125c1  cmp     edx, r12d
0x1800125c4  mov     r15d, eax
0x1800125c7  mov     eax, edx
0x1800125c9  cmovge  eax, r12d
0x1800125cd  cmp     r8d, r9d
0x1800125d0  mov     r12d, eax
0x1800125d3  cmovle  r8d, r9d
0x1800125d7  cmp     edx, r10d
0x1800125da  mov     r9d, r8d
0x1800125dd  cmovle  edx, r10d
0x1800125e1  inc     r11d
0x1800125e4  mov     r10d, edx
0x1800125e7  cmp     r11d, 5
0x1800125eb  jb      short loc_1800125AB
0x1800125ed  sub     r10d, eax
0x1800125f0  lea     rcx, [rbp+100h+var_120]; this
0x1800125f4  sub     r9d, r15d; int
0x1800125f7  lea     r8d, [r10+1]; int
0x1800125fb  lea     edx, [r9+1]; int
0x1800125ff  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x180012604  lea     rcx, [rbp+100h+var_120]; struct Image *
0x180012608  call    ?FromImage@Graphics@Gdiplus@@SAPEAV12@PEAVImage@2@@Z; Gdiplus::Graphics::FromImage(Gdiplus::Image *)
0x18001260d  mov     rsi, rax
0x180012610  test    rax, rax
0x180012613  jnz     short loc_18001261E
0x180012615  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001261a  mov     ebx, eax
0x18001261c  jmp     short loc_180012620
0x18001261e  xor     ebx, ebx
0x180012620  test    ebx, ebx
0x180012622  js      loc_180012A2A
0x180012628  mov     rcx, rsi
0x18001262b  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180012630  movss   xmm2, cs:__real@41200000; float
0x180012638  lea     rdx, ?g_clrStroke@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x18001263f  lea     rcx, [rbp+100h+var_130]; this
0x180012643  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180012648  movss   xmm2, cs:__real@3f800000; float
0x180012650  lea     rdx, ?g_clrEdge@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x180012657  lea     rcx, [rbp+100h+var_140]; this
0x18001265b  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180012660  mov     ecx, [rdi]
0x180012662  mov     eax, [rdi+4]
0x180012665  sub     ecx, r15d
0x180012668  mov     rbx, [rbp+100h+var_170]
0x18001266c  sub     eax, r12d
0x18001266f  mov     [rbp+100h+var_178], eax
0x180012672  mov     [rbp+100h+var_174], ecx
0x180012675  movd    xmm11, ecx
0x18001267a  mov     edi, [rbx]
0x18001267c  mov     ebx, [rbx+4]
0x18001267f  sub     edi, r15d
0x180012682  sub     ebx, r12d
0x180012685  movd    xmm10, eax
0x18001268a  xor     r12d, r12d
0x18001268d  lea     rax, [rsp+200h+var_1C0]
0x180012692  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x180012697  comisd  xmm6, xmm8
0x18001269c  mov     [rsp+200h+var_1C0], r12
0x1800126a1  lea     r15d, [r12+1]
0x1800126a6  mov     [rsp+200h+var_1B8], r12
0x1800126ab  lea     edx, [r12-1]
0x1800126b0  mov     [rsp+200h+var_1D0], r15b; bool
0x1800126b5  mov     r9d, r15d
0x1800126b8  mov     [rsp+200h+var_1D8], r14b; bool
0x1800126bd  mov     r8d, r15d
0x1800126c0  mov     [rbp+100h+var_168], r12
0x1800126c4  mov     [rbp+100h+var_160], r12
0x1800126c8  cvtdq2pd xmm10, xmm10
0x1800126cd  cmova   r9d, edx; int
0x1800126d1  movsd   [rsp+200h+var_1E0], xmm7; double
0x1800126d7  comisd  xmm6, xmm9
0x1800126dc  cvtdq2pd xmm11, xmm11
0x1800126e1  cmova   r8d, edx; int
0x1800126e5  movaps  xmm1, xmm10; double
0x1800126e9  movaps  xmm0, xmm11; double
0x1800126ed  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x1800126f2  comisd  xmm6, xmm8
0x1800126f7  lea     eax, [r12-1]
0x1800126fc  mov     r9d, r15d
0x1800126ff  mov     r8d, r15d
0x180012702  movd    xmm12, ebx
0x180012707  cvtdq2pd xmm12, xmm12
0x18001270c  cmova   r9d, eax; int
0x180012710  movd    xmm13, edi
0x180012715  comisd  xmm6, xmm9
0x18001271a  cvtdq2pd xmm13, xmm13
0x18001271f  cmova   r8d, eax; int
0x180012723  lea     rax, [rbp+100h+var_168]
0x180012727  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x18001272c  mov     [rsp+200h+var_1D0], r15b; bool
0x180012731  mov     [rsp+200h+var_1D8], r14b; bool
0x180012736  movaps  xmm1, xmm12; double
0x18001273a  movsd   [rsp+200h+var_1E0], xmm7; double
0x180012740  movaps  xmm0, xmm13; double
0x180012744  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x180012749  mov     eax, dword ptr [rsp+200h+var_1C0]
0x18001274d  mov     [rbp+100h+var_108], eax
0x180012750  mov     eax, dword ptr [rsp+200h+var_1C0+4]
0x180012754  mov     dword ptr [rbp+100h+var_104], eax
0x180012757  mov     eax, dword ptr [rbp+100h+var_168]
0x18001275a  mov     dword ptr [rbp+100h+var_104+4], eax
0x18001275d  mov     eax, dword ptr [rbp+100h+var_168+4]
0x180012760  mov     dword ptr [rbp+100h+var_104+8], eax
0x180012763  mov     eax, dword ptr [rbp+100h+var_160]
0x180012766  mov     dword ptr [rbp+100h+var_F8], eax
0x180012769  mov     eax, dword ptr [rbp+100h+var_160+4]
0x18001276c  mov     dword ptr [rbp+100h+var_F8+4], eax
0x18001276f  mov     eax, dword ptr [rsp+200h+var_1B8]
0x180012773  mov     dword ptr [rbp+100h+var_F0], eax
0x180012776  mov     eax, dword ptr [rsp+200h+var_1B8+4]
0x18001277a  mov     dword ptr [rbp+100h+var_F0+4], eax
0x18001277d  mov     r15d, [rbp+100h+var_178]
0x180012781  mov     r9d, r15d
0x180012784  mov     rdx, [rbp+100h+var_130]
0x180012788  mov     rcx, [rsi]
0x18001278b  mov     dword ptr [rsp+200h+var_1D8], ebx
0x18001278f  mov     ebx, [rbp+100h+var_174]
0x180012792  mov     r8d, ebx
0x180012795  mov     dword ptr [rsp+200h+var_1E0], edi
0x180012799  call    cs:__imp_GdipDrawLineI
0x18001279f  test    eax, eax
0x1800127a1  jz      short loc_1800127A6
0x1800127a3  mov     [rsi+8], eax
0x1800127a6  mov     rdx, [rbp+100h+var_140]
0x1800127aa  lea     r8, [rbp+100h+var_108]
0x1800127ae  mov     rcx, [rsi]
0x1800127b1  mov     r9d, 4
0x1800127b7  call    cs:__imp_GdipDrawPolygonI
0x1800127bd  test    eax, eax
0x1800127bf  jz      short loc_1800127C4
0x1800127c1  mov     [rsi+8], eax
0x1800127c4  comisd  xmm6, xmm8
0x1800127c9  mov     edi, 1
0x1800127ce  mov     r9d, edi
0x1800127d1  mov     r8d, edi
0x1800127d4  lea     eax, [rdi-2]
0x1800127d7  movaps  xmm1, xmm10; double
0x1800127db  movaps  xmm0, xmm11; double
0x1800127df  cmova   r9d, eax; int
0x1800127e3  comisd  xmm6, xmm9
0x1800127e8  cmova   r8d, eax; int
0x1800127ec  lea     rax, [rsp+200h+var_190]
0x1800127f1  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x1800127f6  mov     [rsp+200h+var_1D0], r12b; bool
0x1800127fb  mov     [rsp+200h+var_1D8], r14b; bool
0x180012800  movsd   [rsp+200h+var_1E0], xmm7; double
0x180012806  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18001280b  comisd  xmm6, xmm8
0x180012810  lea     eax, [rdi-2]
0x180012813  mov     r9d, edi
0x180012816  mov     r8d, edi
0x180012819  movaps  xmm1, xmm12; double
0x18001281d  movaps  xmm0, xmm13; double
0x180012821  cmova   r9d, eax; int
0x180012825  comisd  xmm6, xmm9
0x18001282a  cmova   r8d, eax; int
0x18001282e  lea     rax, [rsp+200h+var_1A8]
0x180012833  mov     [rsp+200h+var_1C8], rax; struct TRI_POINTS *
0x180012838  mov     [rsp+200h+var_1D0], r12b; bool
0x18001283d  mov     [rsp+200h+var_1D8], r14b; bool
0x180012842  movsd   [rsp+200h+var_1E0], xmm7; double
0x180012848  call    ?CalculateTriPoints@@YAXNNHHN_N0PEAUTRI_POINTS@@@Z; CalculateTriPoints(double,double,int,int,double,bool,bool,TRI_POINTS *)
0x18001284d  lea     rdx, [rsp+200h+var_190]; struct TRI_POINTS *
0x180012852  mov     rcx, rsi; struct Gdiplus::Graphics *
0x180012855  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x18001285a  lea     rdx, [rsp+200h+var_1A8]; struct TRI_POINTS *
0x18001285f  mov     rcx, rsi; struct Gdiplus::Graphics *
0x180012862  call    ?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z; DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)
0x180012867  movaps  xmm0, xmm8
0x18001286b  movaps  xmm1, xmm9
0x18001286f  mulsd   xmm0, xmm8
0x180012874  mulsd   xmm1, xmm9
0x180012879  addsd   xmm0, xmm1; X
0x18001287d  call    sqrt
0x180012882  movaps  xmm1, xmm0
0x180012885  movaps  xmm10, xmm0
0x180012889  divsd   xmm1, cs:__real@406f400000000000
0x180012891  cvttsd2si edi, xmm1
0x180012895  test    edi, edi
  ... truncated ...
```
