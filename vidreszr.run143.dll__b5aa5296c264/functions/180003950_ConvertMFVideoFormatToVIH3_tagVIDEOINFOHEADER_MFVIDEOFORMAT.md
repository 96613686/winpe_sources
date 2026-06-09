# ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)

- ea: `0x180003950`
- end: `0x180003c6f`
- name: `?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(struct tagVIDEOINFOHEADER *, struct _MFVIDEOFORMAT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003210`
- `0x180004fe0`
- `0x180009170`

## callees

- `0x180003950`
- `0x180004040`
- `0x180015905`

## pseudocode

```c
__int64 __fastcall ConvertMFVideoFormatToVIH3(struct tagVIDEOINFOHEADER *a1, struct _MFVIDEOFORMAT *a2)
{
  signed int Numerator; // eax
  signed int Denominator; // ecx
  double v6; // xmm2_8
  int v7; // eax
  double v8; // xmm2_8
  unsigned __int64 v9; // rcx
  double v10; // xmm0_8
  REFERENCE_TIME v11; // rax
  LONG dwWidth; // r14d
  LONG dwHeight; // esi
  unsigned int Data1; // ecx
  DWORD v15; // r8d
  WORD v16; // ax
  int v17; // ecx
  __int64 v18; // kr08_8
  DWORD v19; // ecx
  int v20; // ecx
  LONG biWidth; // ecx
  int v22; // eax
  DWORD PaletteEntries; // eax
  DWORD Format; // ecx
  DWORD v26; // eax
  unsigned int v27; // eax
  _BYTE v28[16]; // [rsp+30h] [rbp-38h] BYREF
  int v29; // [rsp+70h] [rbp+8h] BYREF
  int v30; // [rsp+80h] [rbp+18h] BYREF
  DWORD v31; // [rsp+88h] [rbp+20h] BYREF

  if ( !a1 || !a2 )
    return 2147500035LL;
  a1->rcTarget.left = 0;
  a1->rcTarget.right = a2->videoInfo.dwWidth;
  a1->rcTarget.top = 0;
  a1->rcTarget.bottom = a2->videoInfo.dwHeight;
  a1->rcSource = a1->rcTarget;
  Numerator = a2->videoInfo.FramesPerSecond.Numerator;
  if ( Numerator && (Denominator = a2->videoInfo.FramesPerSecond.Denominator) != 0 )
  {
    v6 = (double)Numerator;
    v7 = 0;
    v8 = v6 / (double)Denominator;
    do
    {
      if ( v8 >= *(double *)&qword_1800183C0[2 * v7 + 1] - 0.01 && *(double *)&qword_1800183C0[2 * v7 + 1] + 0.01 >= v8 )
      {
        v11 = qword_1800183C0[2 * v7];
        goto LABEL_15;
      }
      ++v7;
    }
    while ( v7 != 9 );
    v9 = 0;
    v10 = 10000000.0 / v8 + 0.5;
    if ( v10 >= 9.223372036854776e18 )
    {
      v10 = v10 - 9.223372036854776e18;
      if ( v10 < 9.223372036854776e18 )
        v9 = 0x8000000000000000uLL;
    }
    v11 = v9 + (unsigned int)(int)v10;
  }
  else
  {
    v11 = 0;
  }
LABEL_15:
  a1->AvgTimePerFrame = v11;
  *(_QWORD *)&a1->bmiHeader.biXPelsPerMeter = 0;
  a1->bmiHeader.biSize = 40;
  dwWidth = a2->videoInfo.dwWidth;
  a1->bmiHeader.biWidth = dwWidth;
  dwHeight = a2->videoInfo.dwHeight;
  a1->bmiHeader.biHeight = dwHeight;
  a1->dwBitRate = a2->compressedInfo.AvgBitrate;
  Data1 = a2->guidFormat.Data1;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  GetCompressionAndBitCount(Data1, (unsigned int)&v31, (unsigned int)&v30, (unsigned int)&v29, (__int64)v28);
  v15 = v31;
  v16 = v30;
  a1->bmiHeader.biPlanes = v29;
  a1->bmiHeader.biBitCount = v16;
  if ( v15 == 961893977
    || v15 == 842094169
    || v15 == 842094158
    || v15 == 825316942
    || v15 == 808596553
    || v15 == 1448433993 )
  {
    v20 = -dwHeight;
    if ( dwHeight > 0 )
      v20 = dwHeight;
    v19 = dwWidth * v20 * v16 / 8;
  }
  else
  {
    v17 = -dwHeight;
    if ( dwHeight > 0 )
      v17 = dwHeight;
    v18 = dwWidth * v16 / 8 + 3;
    v19 = 4 * (((BYTE4(v18) & 3) + (int)v18) >> 2) * v17;
  }
  a1->bmiHeader.biSizeImage = v19;
  if ( v15 == 808530550 )
  {
    biWidth = -a1->bmiHeader.biWidth;
    if ( a1->bmiHeader.biWidth > 0 )
      biWidth = a1->bmiHeader.biWidth;
    v22 = -dwHeight;
    if ( dwHeight > 0 )
      v22 = dwHeight;
    a1->bmiHeader.biSizeImage = (v22 * ((biWidth + 47) / 48)) << 7;
  }
  a1->bmiHeader.biCompression = v15;
  PaletteEntries = a2->surfaceInfo.PaletteEntries;
  a1->bmiHeader.biClrImportant = 0;
  a1->bmiHeader.biClrUsed = PaletteEntries;
  if ( v15 <= 3 && (a2->videoInfo.VideoFlags & 0x80000) == 0 )
    a1->bmiHeader.biHeight = -dwHeight;
  if ( v15 == 3 )
  {
    Format = a2->surfaceInfo.Format;
    if ( Format == 23 || Format == -466162821 )
    {
      a1[1].rcSource.left = 63488;
      a1[1].rcSource.top = 2016;
    }
    else
    {
      if ( Format != 24 && Format != -466162820 )
        return 0;
      a1[1].rcSource.left = 31744;
      a1[1].rcSource.top = 992;
    }
    a1[1].rcSource.right = 31;
    return 0;
  }
  v26 = a2->surfaceInfo.PaletteEntries;
  if ( v26 > 0x100 )
    return 3222091444LL;
  v27 = 4 * v26;
  if ( !v27 )
    return 0;
  memcpy_0(&a1[1], a2->surfaceInfo.Palette, v27);
  return 0;
}

```

## disassembly

```asm
0x180003950  push    rbx
0x180003952  push    rdi
0x180003953  sub     rsp, 58h
0x180003957  mov     rdi, rdx
0x18000395a  mov     rbx, rcx
0x18000395d  test    rcx, rcx
0x180003960  jz      loc_180003C63
0x180003966  test    rdx, rdx
0x180003969  jz      loc_180003C63
0x18000396f  mov     [rsp+68h+arg_8], rbp
0x180003974  mov     [rsp+68h+var_18], rsi
0x180003979  mov     [rsp+68h+var_20], r14
0x18000397e  mov     [rsp+68h+var_28], r15
0x180003983  xor     r15d, r15d
0x180003986  mov     [rcx+10h], r15d
0x18000398a  mov     ebp, r15d
0x18000398d  mov     eax, [rdx+8]
0x180003990  mov     [rcx+18h], eax
0x180003993  mov     [rcx+14h], r15d
0x180003997  mov     eax, [rdx+0Ch]
0x18000399a  mov     [rcx+1Ch], eax
0x18000399d  movups  xmm0, xmmword ptr [rcx+10h]
0x1800039a1  movups  xmmword ptr [rcx], xmm0
0x1800039a4  mov     eax, [rdx+30h]
0x1800039a7  test    eax, eax
0x1800039a9  jz      loc_180003A55
0x1800039af  mov     ecx, [rdx+34h]
0x1800039b2  test    ecx, ecx
0x1800039b4  jz      loc_180003A55
0x1800039ba  movsd   xmm3, cs:__real@3f847ae147ae147b
0x1800039c2  lea     rdx, qword_1800183C0
0x1800039c9  xorps   xmm2, xmm2
0x1800039cc  xorps   xmm0, xmm0
0x1800039cf  cvtsi2sd xmm2, rax
0x1800039d4  mov     eax, r15d
0x1800039d7  cvtsi2sd xmm0, rcx
0x1800039dc  divsd   xmm2, xmm0
0x1800039e0  movsxd  rcx, eax
0x1800039e3  add     rcx, rcx
0x1800039e6  movsd   xmm1, qword ptr [rdx+rcx*8+8]
0x1800039ec  movaps  xmm0, xmm1
0x1800039ef  subsd   xmm0, xmm3
0x1800039f3  comisd  xmm2, xmm0
0x1800039f7  jb      short loc_180003A03
0x1800039f9  addsd   xmm1, xmm3
0x1800039fd  comisd  xmm1, xmm2
0x180003a01  jnb     short loc_180003A4F
0x180003a03  inc     eax
0x180003a05  cmp     eax, 9
0x180003a08  jnz     short loc_1800039E0
0x180003a0a  movsd   xmm0, cs:__real@416312d000000000
0x180003a12  xor     ecx, ecx
0x180003a14  movsd   xmm1, cs:__real@43e0000000000000
0x180003a1c  divsd   xmm0, xmm2
0x180003a20  addsd   xmm0, cs:__real@3fe0000000000000
0x180003a28  comisd  xmm0, xmm1
0x180003a2c  jb      short loc_180003A45
0x180003a2e  subsd   xmm0, xmm1
0x180003a32  comisd  xmm0, xmm1
0x180003a36  jnb     short loc_180003A45
0x180003a38  mov     rax, 8000000000000000h
0x180003a42  mov     rcx, rax
0x180003a45  cvttsd2si rax, xmm0
0x180003a4a  add     rax, rcx
0x180003a4d  jmp     short loc_180003A58
0x180003a4f  mov     rax, [rdx+rcx*8]
0x180003a53  jmp     short loc_180003A58
0x180003a55  mov     rax, r15
0x180003a58  mov     [rbx+28h], rax
0x180003a5c  lea     r9, [rsp+68h+arg_0]
0x180003a61  mov     [rbx+48h], r15
0x180003a65  lea     r8, [rsp+68h+arg_10]
0x180003a6d  mov     dword ptr [rbx+30h], 28h ; '('
0x180003a74  lea     rdx, [rsp+68h+arg_18]
0x180003a7c  mov     r14d, [rdi+8]
0x180003a80  mov     [rbx+34h], r14d
0x180003a84  mov     esi, [rdi+0Ch]
0x180003a87  mov     [rbx+38h], esi
0x180003a8a  mov     eax, [rdi+88h]
0x180003a90  mov     [rbx+20h], eax
0x180003a93  lea     rax, [rsp+68h+var_38]
0x180003a98  mov     ecx, [rdi+78h]
0x180003a9b  mov     [rsp+68h+var_48], rax
0x180003aa0  mov     [rsp+68h+arg_18], r15d
0x180003aa8  mov     [rsp+68h+arg_10], r15d
0x180003ab0  mov     [rsp+68h+arg_0], r15d
0x180003ab5  call    GetCompressionAndBitCount
0x180003aba  movzx   ecx, word ptr [rsp+68h+arg_0]
0x180003abf  mov     r8d, [rsp+68h+arg_18]
0x180003ac7  mov     eax, [rsp+68h+arg_10]
0x180003ace  mov     [rbx+3Ch], cx
0x180003ad2  mov     [rbx+3Eh], ax
0x180003ad6  cmp     r8d, 39555659h
0x180003add  jz      short loc_180003B37
0x180003adf  cmp     r8d, 32315659h
0x180003ae6  jz      short loc_180003B37
0x180003ae8  cmp     r8d, 3231564Eh
0x180003aef  jz      short loc_180003B37
0x180003af1  cmp     r8d, 3131564Eh
0x180003af8  jz      short loc_180003B37
0x180003afa  cmp     r8d, 30323449h
0x180003b01  jz      short loc_180003B37
0x180003b03  cmp     r8d, 56555949h
0x180003b0a  jz      short loc_180003B37
0x180003b0c  movzx   eax, ax
0x180003b0f  mov     ecx, esi
0x180003b11  neg     ecx
0x180003b13  cmovs   ecx, esi
0x180003b16  imul    eax, r14d
0x180003b1a  cdq
0x180003b1b  and     edx, 7
0x180003b1e  add     eax, edx
0x180003b20  sar     eax, 3
0x180003b23  add     eax, 3
0x180003b26  cdq
0x180003b27  and     edx, 3
0x180003b2a  add     eax, edx
0x180003b2c  sar     eax, 2
0x180003b2f  imul    ecx, eax
0x180003b32  shl     ecx, 2
0x180003b35  jmp     short loc_180003B52
0x180003b37  movzx   eax, ax
0x180003b3a  mov     ecx, esi
0x180003b3c  neg     ecx
0x180003b3e  cmovs   ecx, esi
0x180003b41  imul    eax, ecx
0x180003b44  imul    eax, r14d
0x180003b48  cdq
0x180003b49  and     edx, 7
0x180003b4c  lea     ecx, [rdx+rax]
0x180003b4f  sar     ecx, 3
0x180003b52  mov     [rbx+44h], ecx
0x180003b55  mov     r14, [rsp+68h+var_20]
0x180003b5a  cmp     r8d, 30313276h
0x180003b61  jnz     short loc_180003B90
0x180003b63  mov     ecx, [rbx+34h]
0x180003b66  mov     eax, 2AAAAAABh
0x180003b6b  neg     ecx
0x180003b6d  cmovs   ecx, [rbx+34h]
0x180003b71  add     ecx, 2Fh ; '/'
0x180003b74  imul    ecx
0x180003b76  sar     edx, 3
0x180003b79  mov     eax, edx
0x180003b7b  shr     eax, 1Fh
0x180003b7e  add     edx, eax
0x180003b80  mov     eax, esi
0x180003b82  neg     eax
0x180003b84  cmovs   eax, esi
0x180003b87  imul    edx, eax
0x180003b8a  shl     edx, 7
0x180003b8d  mov     [rbx+44h], edx
0x180003b90  mov     [rbx+40h], r8d
0x180003b94  mov     eax, [rdi+0A4h]
0x180003b9a  mov     [rbx+54h], r15d
0x180003b9e  mov     r15, [rsp+68h+var_28]
0x180003ba3  mov     [rbx+50h], eax
0x180003ba6  cmp     r8d, 3
0x180003baa  ja      short loc_180003BBB
0x180003bac  mov     eax, [rdi+70h]
0x180003baf  bt      rax, 13h
0x180003bb4  jb      short loc_180003BBB
0x180003bb6  neg     esi
0x180003bb8  mov     [rbx+38h], esi
0x180003bbb  mov     rsi, [rsp+68h+var_18]
0x180003bc0  cmp     r8d, 3
0x180003bc4  jnz     short loc_180003C19
0x180003bc6  mov     ecx, [rdi+0A0h]
0x180003bcc  cmp     ecx, 17h
0x180003bcf  jz      short loc_180003C09
0x180003bd1  cmp     ecx, 0E436EB7Bh
0x180003bd7  jz      short loc_180003C09
0x180003bd9  cmp     ecx, 18h
0x180003bdc  jz      short loc_180003BE6
0x180003bde  cmp     ecx, 0E436EB7Ch
0x180003be4  jnz     short loc_180003BFB
0x180003be6  mov     dword ptr [rbx+58h], 7C00h
0x180003bed  mov     dword ptr [rbx+5Ch], 3E0h
0x180003bf4  mov     dword ptr [rbx+60h], 1Fh
0x180003bfb  mov     eax, ebp
0x180003bfd  mov     rbp, [rsp+68h+arg_8]
0x180003c02  add     rsp, 58h
0x180003c06  pop     rdi
0x180003c07  pop     rbx
0x180003c08  retn
0x180003c09  mov     dword ptr [rbx+58h], 0F800h
0x180003c10  mov     dword ptr [rbx+5Ch], 7E0h
0x180003c17  jmp     short loc_180003BF4
0x180003c19  mov     eax, [rdi+0A4h]
0x180003c1f  cmp     eax, 100h
0x180003c24  ja      short loc_180003C52
0x180003c26  lea     eax, ds:0[rax*4]
0x180003c2d  test    eax, eax
0x180003c2f  jz      short loc_180003BFB
0x180003c31  mov     r8d, eax; Size
0x180003c34  lea     rdx, [rdi+0A8h]; Src
0x180003c3b  lea     rcx, [rbx+58h]; void *
0x180003c3f  call    memcpy_0
0x180003c44  mov     eax, ebp
0x180003c46  mov     rbp, [rsp+68h+arg_8]
0x180003c4b  add     rsp, 58h
0x180003c4f  pop     rdi
0x180003c50  pop     rbx
0x180003c51  retn
0x180003c52  mov     rbp, [rsp+68h+arg_8]
0x180003c57  mov     eax, 0C00D36B4h
0x180003c5c  add     rsp, 58h
0x180003c60  pop     rdi
0x180003c61  pop     rbx
0x180003c62  retn
0x180003c63  mov     eax, 80004003h
0x180003c68  add     rsp, 58h
0x180003c6c  pop     rdi
0x180003c6d  pop     rbx
0x180003c6e  retn
```
