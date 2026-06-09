# _DrawPieActual(Gdiplus::Graphics *,tagRECT const *,uint,uint,float,ulong const *)

- ea: `0x1800334a0`
- end: `0x1800338ac`
- name: `?_DrawPieActual@@YAXPEAVGraphics@Gdiplus@@PEBUtagRECT@@IIMPEBK@Z`
- size: `1036`
- prototype: `void __fastcall(struct Gdiplus::Graphics *, const struct tagRECT *, unsigned int, unsigned int, float, const unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180032a58`

## callees

- `0x180030b9c`
- `0x1800334a0`
- `0x1800338b4`
- `0x180068760`
- `0x1800687bc`
- `0x1800687f8`
- `0x180068838`
- `0x18006887c`

## import_xrefs

- `gdiplus!GdipGetPathLastPoint` at `0x180033630`
- `gdiplus!GdipGetPathLastPoint` at `0x180033630`
- `gdiplus!GdipAddPathArcI` at `0x18003360f`
- `gdiplus!GdipAddPathArcI` at `0x18003360f`
- `gdiplus!GdipDeletePath` at `0x180033706`
- `gdiplus!GdipDeletePath` at `0x180033706`
- `gdiplus!GdipCreatePath` at `0x1800335e5`
- `gdiplus!GdipCreatePath` at `0x1800335e5`
- `gdiplus!GdipDeletePen` at `0x18003386c`
- `gdiplus!GdipDeletePen` at `0x18003386c`
- `gdiplus!GdipCreatePen1` at `0x180033507`
- `gdiplus!GdipCreatePen1` at `0x180033507`
- `gdiplus!GdipDeleteBrush` at `0x180033876`
- `gdiplus!GdipDeleteBrush` at `0x180033876`
- `gdiplus!GdipDrawPieI` at `0x18003380d`
- `gdiplus!GdipDrawPieI` at `0x18003380d`
- `gdiplus!GdipFillPieI` at `0x1800337dc`
- `gdiplus!GdipFillPieI` at `0x1800337dc`

## pseudocode

```c
void __fastcall _DrawPieActual(struct Gdiplus::Graphics *a1, const struct tagRECT *a2, int a3, int a4)
{
  __int64 v8; // rdx
  int v9; // eax
  LONG left; // edi
  int v11; // ebx
  unsigned int v12; // edi
  float v13; // xmm7_4
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  int v18; // ecx
  int PathLastPoint; // eax
  int v20; // ecx
  LONG top; // edx
  LONG right; // eax
  LONG v23; // edx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // [rsp+48h] [rbp-69h] BYREF
  int v29; // [rsp+50h] [rbp-61h]
  __int64 v30; // [rsp+58h] [rbp-59h] BYREF
  int v31; // [rsp+60h] [rbp-51h]
  LONG v32; // [rsp+68h] [rbp-49h] BYREF
  LONG v33; // [rsp+6Ch] [rbp-45h]
  int v34; // [rsp+70h] [rbp-41h]
  int v35; // [rsp+74h] [rbp-3Dh]
  _BYTE v36[8]; // [rsp+78h] [rbp-39h] BYREF
  __int64 v37; // [rsp+80h] [rbp-31h]
  __int64 v38; // [rsp+110h] [rbp+5Fh] BYREF
  int v39; // [rsp+118h] [rbp+67h] BYREF

  v39 = -16777216;
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v36, (const struct Gdiplus::Color *)&v39);
  v28 = 0;
  v9 = GdipCreatePen1(4278190080LL, v8, 0, &v28);
  left = a2->left;
  v29 = v9;
  v11 = a2->bottom + ~a4 - a2->top;
  v12 = a2->right + ~left;
  v13 = (float)((float)a3 * 360.0) / 1000.0;
  if ( (unsigned int)a3 < 0x3E8 )
  {
    v39 = -8388480;
    Gdiplus::SolidBrush::SetColor(v36, &v39);
    Gdiplus::Graphics::FillEllipse(a1, v36, (unsigned int)a2->left, (unsigned int)(a4 + a2->top), v12, v11);
    Gdiplus::Graphics::DrawArc(
      a1,
      &v28,
      (unsigned int)a2->left,
      (unsigned int)(a4 + a2->top),
      v12,
      v11,
      0,
      LODWORD(FLOAT_180_0));
  }
  if ( (unsigned int)a3 > 0x1F4 )
  {
    v39 = -16777088;
    Gdiplus::SolidBrush::SetColor(v36, &v39);
    v30 = 0;
    v14 = GdipCreatePath(0, &v30);
    v15 = (unsigned int)a2->left;
    v16 = (unsigned int)(a4 + a2->top);
    v31 = v14;
    v17 = GdipAddPathArcI(v30, v15, v16, v12, v11, 0, v13 - 180.0);
    v18 = v31;
    v38 = 0;
    if ( v17 )
      v18 = v17;
    v31 = v18;
    PathLastPoint = GdipGetPathLastPoint(v30, &v38);
    v20 = v31;
    top = a2->top;
    if ( PathLastPoint )
      v20 = PathLastPoint;
    v33 = a2->top;
    right = a2->right;
    v31 = v20;
    v32 = (int)*(float *)&v38;
    v34 = right - (int)*(float *)&v38;
    v35 = a2->bottom - top;
    Gdiplus::Graphics::SetClip(a1, &v32);
    Gdiplus::Graphics::FillEllipse(a1, v36, (unsigned int)a2->left, (unsigned int)(a4 + a2->top), v12, v11);
    v23 = a2->top;
    v24 = a2->right - a2->left;
    v32 = a2->left;
    v34 = v24;
    v25 = a2->bottom - v23;
    v33 = v23;
    v35 = v25;
    Gdiplus::Graphics::SetClip(a1, &v32);
    Gdiplus::Graphics::DrawArc(a1, &v28, (unsigned int)a2->left, (unsigned int)(a4 + a2->top), v12, v11, 0, v13 - 180.0);
    Gdiplus::Graphics::DrawLine(a1, &v28);
    GdipDeletePath(v30);
  }
  if ( (unsigned int)a3 < 0x3E8 )
  {
    v39 = -65281;
    Gdiplus::SolidBrush::SetColor(v36, &v39);
    Gdiplus::Graphics::FillEllipse(a1, v36, (unsigned int)a2->left, (unsigned int)a2->top, v12, v11);
    Gdiplus::Graphics::DrawEllipse(a1, &v28, (unsigned int)a2->left, (unsigned int)a2->top, v12, v11);
  }
  v39 = -16776961;
  Gdiplus::SolidBrush::SetColor(v36, &v39);
  if ( a3 == 1000 )
  {
    Gdiplus::Graphics::FillEllipse(a1, v36, (unsigned int)a2->left, (unsigned int)a2->top, v12, v11);
    Gdiplus::Graphics::DrawEllipse(a1, &v28, (unsigned int)a2->left, (unsigned int)a2->top, v12, v11);
  }
  else if ( a3 )
  {
    v26 = GdipFillPieI(
            *(_QWORD *)a1,
            v37,
            (unsigned int)a2->left,
            (unsigned int)a2->top,
            v12,
            v11,
            LODWORD(FLOAT_180_0),
            (float)((float)a3 * 360.0) / 1000.0);
    if ( v26 )
      *((_DWORD *)a1 + 2) = v26;
    v27 = GdipDrawPieI(
            *(_QWORD *)a1,
            v28,
            (unsigned int)a2->left,
            (unsigned int)a2->top,
            v12,
            v11,
            LODWORD(FLOAT_180_0),
            (float)((float)a3 * 360.0) / 1000.0);
    if ( v27 )
      *((_DWORD *)a1 + 2) = v27;
  }
  Gdiplus::Graphics::DrawLine(a1, &v28);
  Gdiplus::Graphics::DrawLine(a1, &v28);
  GdipDeletePen(v28);
  GdipDeleteBrush(v37);
}

```

## disassembly

```asm
0x1800334a0  mov     rax, rsp
0x1800334a3  mov     [rax+8], rbx
0x1800334a7  mov     [rax+20h], rsi
0x1800334ab  push    rbp
0x1800334ac  push    rdi
0x1800334ad  push    r12
0x1800334af  push    r14
0x1800334b1  push    r15
0x1800334b3  lea     rbp, [rax-4Fh]
0x1800334b7  sub     rsp, 0D0h
0x1800334be  movaps  xmmword ptr [rax-38h], xmm6
0x1800334c2  mov     rsi, rdx
0x1800334c5  movaps  xmmword ptr [rax-48h], xmm7
0x1800334c9  lea     rdx, [rbp+47h+arg_10]; struct Gdiplus::Color *
0x1800334cd  mov     r14, rcx
0x1800334d0  movaps  xmmword ptr [rax-58h], xmm8
0x1800334d5  mov     ebx, 0FF000000h
0x1800334da  movaps  xmmword ptr [rax-68h], xmm9
0x1800334df  lea     rcx, [rbp+47h+var_80]; this
0x1800334e3  mov     r15d, r8d
0x1800334e6  mov     r12d, r9d
0x1800334e9  mov     [rbp+47h+arg_10], ebx
0x1800334ec  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1800334f1  movss   xmm1, [rbp+47h+arg_20]
0x1800334f6  lea     r9, [rbp+47h+var_B0]
0x1800334fa  xor     r8d, r8d
0x1800334fd  mov     [rbp+47h+var_B0], 0
0x180033505  mov     ecx, ebx
0x180033507  call    cs:__imp_GdipCreatePen1
0x18003350d  mov     edi, [rsi]
0x18003350f  xorps   xmm7, xmm7
0x180033512  movss   xmm8, cs:__real@43340000
0x18003351b  mov     ebx, r12d
0x18003351e  cvtsi2ss xmm7, r15
0x180033523  not     ebx
0x180033525  mov     [rbp+47h+var_A8], eax
0x180033528  sub     ebx, [rsi+4]
0x18003352b  not     edi
0x18003352d  add     ebx, [rsi+0Ch]
0x180033530  add     edi, [rsi+8]
0x180033533  xorps   xmm9, xmm9
0x180033537  mulss   xmm7, cs:__real@43b40000
0x18003353f  divss   xmm7, cs:__real@447a0000
0x180033547  cmp     r15d, 3E8h
0x18003354e  jnb     short loc_1800335AE
0x180033550  lea     rdx, [rbp+47h+arg_10]
0x180033554  mov     [rbp+47h+arg_10], 0FF800080h
0x18003355b  lea     rcx, [rbp+47h+var_80]
0x18003355f  call    ?SetColor@SolidBrush@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@@Z; Gdiplus::SolidBrush::SetColor(Gdiplus::Color const &)
0x180033564  mov     r9d, [rsi+4]
0x180033568  lea     rdx, [rbp+47h+var_80]
0x18003356c  mov     r8d, [rsi]
0x18003356f  add     r9d, r12d
0x180033572  mov     [rsp+0F0h+var_C8], ebx
0x180033576  mov     rcx, r14
0x180033579  mov     [rsp+0F0h+var_D0], edi
0x18003357d  call    ?FillEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillEllipse(Gdiplus::Brush const *,int,int,int,int)
0x180033582  mov     r9d, [rsi+4]
0x180033586  lea     rdx, [rbp+47h+var_B0]
0x18003358a  mov     r8d, [rsi]
0x18003358d  add     r9d, r12d
0x180033590  movss   [rsp+0F0h+var_B8], xmm8
0x180033597  mov     rcx, r14
0x18003359a  movss   [rsp+0F0h+var_C0], xmm9
0x1800335a1  mov     [rsp+0F0h+var_C8], ebx
0x1800335a5  mov     [rsp+0F0h+var_D0], edi
0x1800335a9  call    ?DrawArc@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHHMM@Z; Gdiplus::Graphics::DrawArc(Gdiplus::Pen const *,int,int,int,int,float,float)
0x1800335ae  cmp     r15d, 1F4h
0x1800335b5  jbe     loc_18003370C
0x1800335bb  lea     rdx, [rbp+47h+arg_10]
0x1800335bf  mov     [rbp+47h+arg_10], 0FF000080h
0x1800335c6  lea     rcx, [rbp+47h+var_80]
0x1800335ca  call    ?SetColor@SolidBrush@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@@Z; Gdiplus::SolidBrush::SetColor(Gdiplus::Color const &)
0x1800335cf  movaps  xmm6, xmm7
0x1800335d2  mov     [rbp+47h+var_A0], 0
0x1800335da  lea     rdx, [rbp+47h+var_A0]
0x1800335de  xor     ecx, ecx
0x1800335e0  subss   xmm6, xmm8
0x1800335e5  call    cs:__imp_GdipCreatePath
0x1800335eb  mov     r8d, [rsi+4]
0x1800335ef  mov     r9d, edi
0x1800335f2  mov     edx, [rsi]
0x1800335f4  add     r8d, r12d
0x1800335f7  mov     rcx, [rbp+47h+var_A0]
0x1800335fb  movss   [rsp+0F0h+var_C0], xmm6
0x180033601  movss   [rsp+0F0h+var_C8], xmm9
0x180033608  mov     [rbp+47h+var_98], eax
0x18003360b  mov     [rsp+0F0h+var_D0], ebx
0x18003360f  call    cs:__imp_GdipAddPathArcI
0x180033615  mov     ecx, [rbp+47h+var_98]
0x180033618  lea     rdx, [rbp+47h+arg_8]
0x18003361c  test    eax, eax
0x18003361e  mov     [rbp+47h+arg_8], 0
0x180033626  cmovnz  ecx, eax
0x180033629  mov     [rbp+47h+var_98], ecx
0x18003362c  mov     rcx, [rbp+47h+var_A0]
0x180033630  call    cs:__imp_GdipGetPathLastPoint
0x180033636  mov     ecx, [rbp+47h+var_98]
0x180033639  test    eax, eax
0x18003363b  mov     edx, [rsi+4]
0x18003363e  cmovnz  ecx, eax
0x180033641  mov     [rbp+47h+var_8C], edx
0x180033644  mov     eax, [rsi+8]
0x180033647  mov     [rbp+47h+var_98], ecx
0x18003364a  cvttss2si ecx, dword ptr [rbp+47h+arg_8]
0x18003364f  sub     eax, ecx
0x180033651  mov     [rbp+47h+var_90], ecx
0x180033654  mov     [rbp+47h+var_88], eax
0x180033657  mov     rcx, r14
0x18003365a  mov     eax, [rsi+0Ch]
0x18003365d  sub     eax, edx
0x18003365f  lea     rdx, [rbp+47h+var_90]
0x180033663  mov     [rbp+47h+var_84], eax
0x180033666  call    ?SetClip@Graphics@Gdiplus@@QEAA?AW4Status@2@AEBVRect@2@W4CombineMode@2@@Z; Gdiplus::Graphics::SetClip(Gdiplus::Rect const &,Gdiplus::CombineMode)
0x18003366b  mov     r9d, [rsi+4]
0x18003366f  lea     rdx, [rbp+47h+var_80]
0x180033673  mov     r8d, [rsi]
0x180033676  add     r9d, r12d
0x180033679  mov     [rsp+0F0h+var_C8], ebx
0x18003367d  mov     rcx, r14
0x180033680  mov     [rsp+0F0h+var_D0], edi
0x180033684  call    ?FillEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillEllipse(Gdiplus::Brush const *,int,int,int,int)
0x180033689  mov     ecx, [rsi]
0x18003368b  mov     edx, [rsi+4]
0x18003368e  mov     eax, [rsi+8]
0x180033691  sub     eax, ecx
0x180033693  mov     [rbp+47h+var_90], ecx
0x180033696  mov     [rbp+47h+var_88], eax
0x180033699  mov     rcx, r14
0x18003369c  mov     eax, [rsi+0Ch]
0x18003369f  sub     eax, edx
0x1800336a1  mov     [rbp+47h+var_8C], edx
0x1800336a4  lea     rdx, [rbp+47h+var_90]
0x1800336a8  mov     [rbp+47h+var_84], eax
0x1800336ab  call    ?SetClip@Graphics@Gdiplus@@QEAA?AW4Status@2@AEBVRect@2@W4CombineMode@2@@Z; Gdiplus::Graphics::SetClip(Gdiplus::Rect const &,Gdiplus::CombineMode)
0x1800336b0  mov     r9d, [rsi+4]
0x1800336b4  lea     rdx, [rbp+47h+var_B0]
0x1800336b8  mov     r8d, [rsi]
0x1800336bb  add     r9d, r12d
0x1800336be  movss   [rsp+0F0h+var_B8], xmm6
0x1800336c4  mov     rcx, r14
0x1800336c7  movss   [rsp+0F0h+var_C0], xmm9
0x1800336ce  mov     [rsp+0F0h+var_C8], ebx
0x1800336d2  mov     [rsp+0F0h+var_D0], edi
0x1800336d6  call    ?DrawArc@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHHMM@Z; Gdiplus::Graphics::DrawArc(Gdiplus::Pen const *,int,int,int,int,float,float)
0x1800336db  cvttss2si r9d, dword ptr [rbp+47h+arg_8+4]
0x1800336e1  cvttss2si r8d, dword ptr [rbp+47h+arg_8]
0x1800336e7  mov     eax, r9d
0x1800336ea  sub     eax, r12d
0x1800336ed  mov     [rsp+0F0h+var_C8], eax
0x1800336f1  lea     rdx, [rbp+47h+var_B0]
0x1800336f5  mov     [rsp+0F0h+var_D0], r8d
0x1800336fa  mov     rcx, r14
0x1800336fd  call    ?DrawLine@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawLine(Gdiplus::Pen const *,int,int,int,int)
0x180033702  mov     rcx, [rbp+47h+var_A0]
0x180033706  call    cs:__imp_GdipDeletePath
0x18003370c  cmp     r15d, 3E8h
0x180033713  jnb     short loc_18003375F
0x180033715  lea     rdx, [rbp+47h+arg_10]
0x180033719  mov     [rbp+47h+arg_10], 0FFFF00FFh
0x180033720  lea     rcx, [rbp+47h+var_80]
0x180033724  call    ?SetColor@SolidBrush@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@@Z; Gdiplus::SolidBrush::SetColor(Gdiplus::Color const &)
0x180033729  mov     r9d, [rsi+4]
0x18003372d  lea     rdx, [rbp+47h+var_80]
0x180033731  mov     r8d, [rsi]
0x180033734  mov     rcx, r14
0x180033737  mov     [rsp+0F0h+var_C8], ebx
0x18003373b  mov     [rsp+0F0h+var_D0], edi
0x18003373f  call    ?FillEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillEllipse(Gdiplus::Brush const *,int,int,int,int)
0x180033744  mov     r9d, [rsi+4]
0x180033748  lea     rdx, [rbp+47h+var_B0]
0x18003374c  mov     r8d, [rsi]
0x18003374f  mov     rcx, r14
0x180033752  mov     [rsp+0F0h+var_C8], ebx
0x180033756  mov     [rsp+0F0h+var_D0], edi
0x18003375a  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x18003375f  lea     rdx, [rbp+47h+arg_10]
0x180033763  mov     [rbp+47h+arg_10], 0FF0000FFh
0x18003376a  lea     rcx, [rbp+47h+var_80]
0x18003376e  call    ?SetColor@SolidBrush@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@@Z; Gdiplus::SolidBrush::SetColor(Gdiplus::Color const &)
0x180033773  cmp     r15d, 3E8h
0x18003377a  jnz     short loc_1800337B4
0x18003377c  mov     r9d, [rsi+4]
0x180033780  lea     rdx, [rbp+47h+var_80]
0x180033784  mov     r8d, [rsi]
0x180033787  mov     rcx, r14
0x18003378a  mov     [rsp+0F0h+var_C8], ebx
0x18003378e  mov     [rsp+0F0h+var_D0], edi
0x180033792  call    ?FillEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillEllipse(Gdiplus::Brush const *,int,int,int,int)
0x180033797  mov     r9d, [rsi+4]
0x18003379b  lea     rdx, [rbp+47h+var_B0]
0x18003379f  mov     r8d, [rsi]
0x1800337a2  mov     rcx, r14
0x1800337a5  mov     [rsp+0F0h+var_C8], ebx
0x1800337a9  mov     [rsp+0F0h+var_D0], edi
0x1800337ad  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x1800337b2  jmp     short loc_18003381B
0x1800337b4  test    r15d, r15d
0x1800337b7  jz      short loc_18003381B
0x1800337b9  mov     r9d, [rsi+4]
0x1800337bd  mov     r8d, [rsi]
0x1800337c0  mov     rdx, [rbp+47h+var_78]
0x1800337c4  mov     rcx, [r14]
0x1800337c7  movss   [rsp+0F0h+var_B8], xmm7
0x1800337cd  movss   [rsp+0F0h+var_C0], xmm8
0x1800337d4  mov     [rsp+0F0h+var_C8], ebx
0x1800337d8  mov     [rsp+0F0h+var_D0], edi
0x1800337dc  call    cs:__imp_GdipFillPieI
0x1800337e2  test    eax, eax
0x1800337e4  jz      short loc_1800337EA
0x1800337e6  mov     [r14+8], eax
0x1800337ea  mov     r9d, [rsi+4]
0x1800337ee  mov     r8d, [rsi]
0x1800337f1  mov     rdx, [rbp+47h+var_B0]
0x1800337f5  mov     rcx, [r14]
0x1800337f8  movss   [rsp+0F0h+var_B8], xmm7
0x1800337fe  movss   [rsp+0F0h+var_C0], xmm8
0x180033805  mov     [rsp+0F0h+var_C8], ebx
0x180033809  mov     [rsp+0F0h+var_D0], edi
0x18003380d  call    cs:__imp_GdipDrawPieI
0x180033813  test    eax, eax
0x180033815  jz      short loc_18003381B
0x180033817  mov     [r14+8], eax
0x18003381b  mov     edi, [rsi+4]
0x18003381e  mov     eax, ebx
0x180033820  mov     r8d, [rsi]
0x180033823  cdq
0x180033824  mov     ecx, 2
0x180033829  idiv    ecx
0x18003382b  lea     rdx, [rbp+47h+var_B0]
0x18003382f  mov     rcx, r14
0x180033832  add     edi, eax
0x180033834  mov     r9d, edi
0x180033837  lea     ebx, [rdi+r12]
0x18003383b  mov     [rsp+0F0h+var_C8], ebx
0x18003383f  mov     [rsp+0F0h+var_D0], r8d
0x180033844  call    ?DrawLine@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawLine(Gdiplus::Pen const *,int,int,int,int)
0x180033849  mov     r8d, [rsi+8]
0x18003384d  lea     rdx, [rbp+47h+var_B0]
0x180033851  dec     r8d
0x180033854  mov     [rsp+0F0h+var_C8], ebx
0x180033858  mov     r9d, edi
0x18003385b  mov     [rsp+0F0h+var_D0], r8d
0x180033860  mov     rcx, r14
0x180033863  call    ?DrawLine@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawLine(Gdiplus::Pen const *,int,int,int,int)
0x180033868  mov     rcx, [rbp+47h+var_B0]
0x18003386c  call    cs:__imp_GdipDeletePen
0x180033872  mov     rcx, [rbp+47h+var_78]
0x180033876  call    cs:__imp_GdipDeleteBrush
0x18003387c  lea     r11, [rsp+0F0h+var_20]
0x180033884  mov     rbx, [r11+30h]
0x180033888  mov     rsi, [r11+48h]
0x18003388c  movaps  xmm6, xmmword ptr [r11-10h]
0x180033891  movaps  xmm7, xmmword ptr [r11-20h]
0x180033896  movaps  xmm8, xmmword ptr [r11-30h]
0x18003389b  movaps  xmm9, xmmword ptr [r11-40h]
0x1800338a0  mov     rsp, r11
0x1800338a3  pop     r15
0x1800338a5  pop     r14
0x1800338a7  pop     r12
0x1800338a9  pop     rdi
0x1800338aa  pop     rbp
0x1800338ab  retn
```
