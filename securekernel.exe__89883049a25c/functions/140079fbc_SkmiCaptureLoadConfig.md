# SkmiCaptureLoadConfig

- ea: `0x140079fbc`
- end: `0x14007a350`
- name: `SkmiCaptureLoadConfig`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007a358`

## callees

- `0x14000f0f0`
- `0x140079fbc`
- `0x14007b4c0`
- `0x14007c13c`
- `0x14007f020`
- `0x1400dbcfc`
- `0x1400dbe04`
- `0x1400dc054`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCaptureLoadConfig(int a1, int a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int8 v9; // r14
  unsigned __int32 v10; // ebx
  __int32 v11; // eax
  size_t v12; // r12
  unsigned int v13; // r15d
  __int64 Pool; // rax
  __int64 v15; // rdi
  int FunctionOverrideFixupInfo2; // ebx
  void *v17; // rcx
  __m128i v18; // xmm2
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v21; // rax
  size_t v22; // r8
  unsigned int *v23; // rax
  unsigned int *v24; // r14
  const void *v25; // rdx
  void *v26; // rcx
  void *v27; // rax
  unsigned __int64 v28; // rbx
  void *v29; // rax
  unsigned int v30; // r15d
  __int64 v31; // rax
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  _OWORD *v44; // rax
  _QWORD *v45; // r14
  __m256i Src; // [rsp+50h] [rbp-B0h] BYREF
  void *v48[2]; // [rsp+70h] [rbp-90h]
  size_t Size[2]; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+90h] [rbp-70h]
  _OWORD v51[13]; // [rsp+A0h] [rbp-60h] BYREF
  int v52; // [rsp+170h] [rbp+70h]
  char v53[288]; // [rsp+180h] [rbp+80h] BYREF

  memset_0(&Src, 0, 0x48u);
  memset_0(v51, 0, 0xD4u);
  result = SkmiProcessLoadConfigForDriver(a1, a2, a3, a4, 2, &Src);
  if ( (int)result >= 0 )
  {
    v9 = Src.m256i_i8[20];
    v10 = Src.m256i_u32[2];
    if ( Src.m256i_i8[20] )
      v11 = Src.m256i_i32[2];
    else
      v11 = 40 * Src.m256i_i32[2];
    v12 = LODWORD(Size[0]);
    v13 = (v11 + 7) & 0xFFFFFFF8;
    Pool = SkAllocatePool(512, v13 + LODWORD(Size[0]) + 72);
    v15 = Pool;
    if ( !Pool )
      return (unsigned int)-1073741670;
    v17 = (void *)(Pool + 72);
    v18 = *(__m128i *)&Src.m256i_u64[2];
    v19 = *(_OWORD *)Size;
    *(_OWORD *)Pool = *(_OWORD *)Src.m256i_i8;
    v20 = *(_OWORD *)v48;
    *(__m128i *)(Pool + 16) = v18;
    *(_OWORD *)(Pool + 32) = v20;
    *(_QWORD *)&v20 = v50;
    *(_OWORD *)(Pool + 48) = v19;
    *(_QWORD *)(Pool + 64) = v20;
    *(_QWORD *)&v20 = *(__int64 *)((char *)&Src.m256i_i64[2] + 5);
    *(_DWORD *)(Pool + 8) = v10;
    v21 = *(__int64 *)((char *)&Src.m256i_i64[1] + 4);
    *(_QWORD *)(v15 + 21) = v20;
    *(_QWORD *)(v15 + 12) = v21;
    *(_DWORD *)(v15 + 28) = _mm_cvtsi128_si32(_mm_srli_si128(v18, 12));
    *(_BYTE *)(v15 + 20) = v9;
    *(_QWORD *)v15 = v15 + 72;
    if ( v9 )
      v22 = v10;
    else
      v22 = 40LL * v10;
    memmove(v17, (const void *)Src.m256i_i64[0], v22);
    if ( (_DWORD)v12 )
    {
      v23 = (unsigned int *)SkAllocatePool(512, 0x80u);
      v24 = v23;
      if ( !v23 )
        goto LABEL_12;
      memset_0(v23, 0, 0x80u);
      v25 = v48[1];
      *(_QWORD *)(a4 + 200) = v24;
      v26 = (void *)(v15 + v13 + 72LL);
      *(_QWORD *)(v15 + 40) = v26;
      memmove(v26, v25, v12);
      FunctionOverrideFixupInfo2 = SkmiValidateDynamicRelocations(
                                     *(_QWORD *)(v15 + 40),
                                     *(unsigned int *)(a3 + 80),
                                     *(unsigned int *)(a3 + 84),
                                     *(_QWORD *)(a4 + 200));
      if ( FunctionOverrideFixupInfo2 < 0 )
        goto LABEL_13;
      v27 = (void *)SkAllocatePool(512, 9LL * v24[27]);
      *(_QWORD *)(v15 + 56) = v27;
      if ( !v27 )
        goto LABEL_12;
      memset_0(v27, 0, 9LL * v24[27]);
      *(_DWORD *)(v15 + 52) = v24[27];
      if ( (SkmiPatchFlags & 1) != 0 )
      {
        *(_QWORD *)(a4 + 152) = *(_QWORD *)(v15 + 56);
        *(_QWORD *)(a4 + 160) = *(_QWORD *)(v15 + 56) + 8LL * *(unsigned int *)(v15 + 52);
        *(_DWORD *)(a4 + 148) = *(_DWORD *)(v15 + 52);
      }
      v28 = 8LL * v24[27];
      v29 = (void *)SkAllocatePool(512, v28);
      *(_QWORD *)(v15 + 64) = v29;
      if ( !v29 )
      {
LABEL_12:
        FunctionOverrideFixupInfo2 = -1073741670;
LABEL_13:
        SkmiFreeLoadConfig(v15);
        return (unsigned int)FunctionOverrideFixupInfo2;
      }
      memset_0(v29, 0, v28);
      v30 = *(_DWORD *)(a3 + 80);
      if ( a4 == SkmiNtosNar )
      {
        v44 = 0;
      }
      else
      {
        v31 = RtlInitializeImageSystemOverride(v53, v30, 1);
        v32 = *(_OWORD *)(v31 + 16);
        v51[0] = *(_OWORD *)v31;
        v33 = *(_OWORD *)(v31 + 32);
        v51[1] = v32;
        v34 = *(_OWORD *)(v31 + 48);
        v51[2] = v33;
        v35 = *(_OWORD *)(v31 + 64);
        v51[3] = v34;
        v36 = *(_OWORD *)(v31 + 80);
        v51[4] = v35;
        v37 = *(_OWORD *)(v31 + 96);
        v51[5] = v36;
        v38 = *(_OWORD *)(v31 + 112);
        v51[6] = v37;
        v39 = *(_OWORD *)(v31 + 128);
        v51[7] = v38;
        v40 = *(_OWORD *)(v31 + 144);
        v51[8] = v39;
        v41 = *(_OWORD *)(v31 + 160);
        v51[9] = v40;
        v42 = *(_OWORD *)(v31 + 176);
        v51[10] = v41;
        v43 = *(_OWORD *)(v31 + 192);
        v52 = *(_DWORD *)(v31 + 208);
        v44 = v51;
        v51[12] = v43;
        v51[11] = v42;
      }
      v45 = v24 + 30;
      FunctionOverrideFixupInfo2 = RtlCreateFunctionOverrideFixupInfo2(
                                     *(_QWORD *)(v15 + 40),
                                     v12,
                                     *(_DWORD *)(a3 + 80),
                                     *(_DWORD *)(a3 + 84),
                                     (__int64)&xmmword_140156CBC,
                                     (__int64)v45,
                                     (__int64)v44);
      if ( FunctionOverrideFixupInfo2 < 0 )
        goto LABEL_13;
      if ( *v45 )
      {
        if ( a4 != SkmiNtosNar )
          RtlInitializeSystemOverrideDelta(*v45, a2, v30, 0, 0);
      }
    }
    *(_QWORD *)(a4 + 32) = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140079fbc  push    rbp
0x140079fbe  push    rbx
0x140079fbf  push    rsi
0x140079fc0  push    rdi
0x140079fc1  push    r12
0x140079fc3  push    r13
0x140079fc5  push    r14
0x140079fc7  push    r15
0x140079fc9  lea     rbp, [rsp-168h]
0x140079fd1  sub     rsp, 268h
0x140079fd8  mov     rdi, rdx
0x140079fdb  mov     [rsp+2A0h+var_260], rdx
0x140079fe0  xor     edx, edx; Val
0x140079fe2  mov     r13, r8
0x140079fe5  mov     rbx, rcx
0x140079fe8  mov     rsi, r9
0x140079feb  lea     rcx, [rsp+2A0h+Src]; void *
0x140079ff0  lea     r8d, [rdx+48h]; Size
0x140079ff4  call    memset_0
0x140079ff9  xor     edx, edx; Val
0x140079ffb  lea     rcx, [rbp+1A0h+var_200]; void *
0x140079fff  mov     r8d, 0D4h; Size
0x14007a005  call    memset_0
0x14007a00a  lea     rax, [rsp+2A0h+Src]
0x14007a00f  mov     r9, rsi; int
0x14007a012  mov     [rsp+2A0h+var_278], rax; void *
0x14007a017  mov     r8, r13; int
0x14007a01a  mov     rdx, rdi; int
0x14007a01d  mov     dword ptr [rsp+2A0h+var_280], 2; char
0x14007a025  mov     rcx, rbx; int
0x14007a028  call    SkmiProcessLoadConfigForDriver
0x14007a02d  test    eax, eax
0x14007a02f  js      loc_14007A33B
0x14007a035  mov     r14b, [rsp+2A0h+var_23C]
0x14007a03a  mov     ebx, dword ptr [rsp+2A0h+Src+8]
0x14007a03e  test    r14b, r14b
0x14007a041  jz      short loc_14007A047
0x14007a043  mov     eax, ebx
0x14007a045  jmp     short loc_14007A04D
0x14007a047  lea     eax, [rbx+rbx*4]
0x14007a04a  shl     eax, 3
0x14007a04d  mov     r12d, dword ptr [rbp+1A0h+Size]
0x14007a051  lea     r15d, [rax+7]
0x14007a055  and     r15d, 0FFFFFFF8h
0x14007a059  mov     ecx, 200h
0x14007a05e  mov     r8d, 434C6D4Dh
0x14007a064  lea     edx, [r12+48h]
0x14007a069  add     edx, r15d
0x14007a06c  call    SkAllocatePool
0x14007a071  mov     rdi, rax
0x14007a074  test    rax, rax
0x14007a077  jnz     short loc_14007A083
0x14007a079  mov     ebx, 0C000009Ah
0x14007a07e  jmp     loc_14007A339
0x14007a083  movaps  xmm0, xmmword ptr [rsp+2A0h+Src]
0x14007a088  lea     rcx, [rdi+48h]; void *
0x14007a08c  movaps  xmm2, xmmword ptr [rsp+60h]
0x14007a091  movaps  xmm1, xmmword ptr [rbp+1A0h+Size]
0x14007a095  movups  xmmword ptr [rax], xmm0
0x14007a098  movaps  xmm0, xmmword ptr [rsp+2A0h+var_230]
0x14007a09d  movups  xmmword ptr [rax+10h], xmm2
0x14007a0a1  psrldq  xmm2, 0Ch
0x14007a0a6  movups  xmmword ptr [rax+20h], xmm0
0x14007a0aa  movsd   xmm0, [rbp+1A0h+var_210]
0x14007a0af  movups  xmmword ptr [rax+30h], xmm1
0x14007a0b3  movsd   qword ptr [rax+40h], xmm0
0x14007a0b8  movsd   xmm0, [rsp+2A0h+var_23B]
0x14007a0be  mov     [rax+8], ebx
0x14007a0c1  mov     rax, [rsp+2A0h+Src+0Ch]
0x14007a0c6  movsd   qword ptr [rdi+15h], xmm0
0x14007a0cb  mov     [rdi+0Ch], rax
0x14007a0cf  movd    dword ptr [rdi+1Ch], xmm2
0x14007a0d4  mov     [rdi+14h], r14b
0x14007a0d8  mov     [rdi], rcx
0x14007a0db  mov     rdx, [rsp+2A0h+Src]; Src
0x14007a0e0  test    r14b, r14b
0x14007a0e3  jz      short loc_14007A0EA
0x14007a0e5  mov     r8d, ebx
0x14007a0e8  jmp     short loc_14007A0F4
0x14007a0ea  mov     eax, ebx
0x14007a0ec  lea     r8, [rax+rax*4]
0x14007a0f0  shl     r8, 3; Size
0x14007a0f4  call    memmove
0x14007a0f9  test    r12d, r12d
0x14007a0fc  jz      loc_14007A333
0x14007a102  mov     ebx, 80h
0x14007a107  mov     r8d, 434C6D4Dh
0x14007a10d  mov     edx, ebx
0x14007a10f  mov     ecx, 200h
0x14007a114  call    SkAllocatePool
0x14007a119  mov     r14, rax
0x14007a11c  test    rax, rax
0x14007a11f  jnz     short loc_14007A133
0x14007a121  mov     ebx, 0C000009Ah
0x14007a126  mov     rcx, rdi
0x14007a129  call    SkmiFreeLoadConfig
0x14007a12e  jmp     loc_14007A339
0x14007a133  mov     r8, rbx; Size
0x14007a136  xor     edx, edx; Val
0x14007a138  mov     rcx, r14; void *
0x14007a13b  call    memset_0
0x14007a140  mov     rdx, [rsp+2A0h+var_230+8]; Src
0x14007a145  mov     r8, r12; Size
0x14007a148  mov     [rsi+0C8h], r14
0x14007a14f  mov     ecx, r15d
0x14007a152  add     rcx, 48h ; 'H'
0x14007a156  add     rcx, rdi; void *
0x14007a159  mov     [rdi+28h], rcx
0x14007a15d  call    memmove
0x14007a162  mov     r9, [rsi+0C8h]
0x14007a169  mov     r8d, [r13+54h]
0x14007a16d  mov     edx, [r13+50h]
0x14007a171  mov     rcx, [rdi+28h]
0x14007a175  call    SkmiValidateDynamicRelocations
0x14007a17a  mov     ebx, eax
0x14007a17c  test    eax, eax
0x14007a17e  js      short loc_14007A126
0x14007a180  mov     eax, [r14+6Ch]
0x14007a184  mov     r15d, 200h
0x14007a18a  mov     r8d, 5244694Dh
0x14007a190  mov     ecx, r15d
0x14007a193  lea     rdx, [rax+rax*8]
0x14007a197  call    SkAllocatePool
0x14007a19c  mov     [rdi+38h], rax
0x14007a1a0  mov     rcx, rax; void *
0x14007a1a3  test    rax, rax
0x14007a1a6  jz      loc_14007A121
0x14007a1ac  mov     eax, [r14+6Ch]
0x14007a1b0  xor     edx, edx; Val
0x14007a1b2  lea     r8, [rax+rax*8]; Size
0x14007a1b6  call    memset_0
0x14007a1bb  mov     eax, [r14+6Ch]
0x14007a1bf  mov     [rdi+34h], eax
0x14007a1c2  mov     eax, cs:SkmiPatchFlags
0x14007a1c8  test    al, 1
0x14007a1ca  jz      short loc_14007A1F2
0x14007a1cc  mov     rax, [rdi+38h]
0x14007a1d0  mov     [rsi+98h], rax
0x14007a1d7  mov     rax, [rdi+38h]
0x14007a1db  mov     edx, [rdi+34h]
0x14007a1de  lea     rdx, [rax+rdx*8]
0x14007a1e2  mov     [rsi+0A0h], rdx
0x14007a1e9  mov     eax, [rdi+34h]
0x14007a1ec  mov     [rsi+94h], eax
0x14007a1f2  mov     ebx, [r14+6Ch]
0x14007a1f6  mov     r8d, 5244694Dh
0x14007a1fc  shl     rbx, 3
0x14007a200  mov     ecx, r15d
0x14007a203  mov     rdx, rbx
0x14007a206  call    SkAllocatePool
0x14007a20b  mov     [rdi+40h], rax
0x14007a20f  test    rax, rax
0x14007a212  jz      loc_14007A121
0x14007a218  mov     r8, rbx; Size
0x14007a21b  xor     edx, edx; Val
0x14007a21d  mov     rcx, rax; void *
0x14007a220  call    memset_0
0x14007a225  cmp     rsi, cs:SkmiNtosNar
0x14007a22c  mov     r15d, [r13+50h]
0x14007a230  jz      loc_14007A2D0
0x14007a236  mov     r8d, 1
0x14007a23c  lea     rcx, [rbp+1A0h+var_120]
0x14007a243  mov     edx, r15d
0x14007a246  call    RtlInitializeImageSystemOverride
0x14007a24b  movups  xmm0, xmmword ptr [rax]
0x14007a24e  movups  xmm1, xmmword ptr [rax+10h]
0x14007a252  movups  [rbp+1A0h+var_200], xmm0
0x14007a256  movups  xmm0, xmmword ptr [rax+20h]
0x14007a25a  movups  [rbp+1A0h+var_1F0], xmm1
0x14007a25e  movups  xmm1, xmmword ptr [rax+30h]
0x14007a262  movups  [rbp+1A0h+var_1E0], xmm0
0x14007a266  movups  xmm0, xmmword ptr [rax+40h]
0x14007a26a  movups  [rbp+1A0h+var_1D0], xmm1
0x14007a26e  movups  xmm1, xmmword ptr [rax+50h]
0x14007a272  movups  [rbp+1A0h+var_1C0], xmm0
0x14007a276  movups  xmm0, xmmword ptr [rax+60h]
0x14007a27a  movups  [rbp+1A0h+var_1B0], xmm1
0x14007a27e  movups  xmm1, xmmword ptr [rax+70h]
0x14007a282  movups  [rbp+1A0h+var_1A0], xmm0
0x14007a286  movups  xmm0, xmmword ptr [rax+80h]
0x14007a28d  movups  [rbp+1A0h+var_190], xmm1
0x14007a291  movups  xmm1, xmmword ptr [rax+90h]
0x14007a298  movups  [rbp+1A0h+var_180], xmm0
0x14007a29c  movups  xmm0, xmmword ptr [rax+0A0h]
0x14007a2a3  movups  [rbp+1A0h+var_170], xmm1
0x14007a2a7  movups  xmm1, xmmword ptr [rax+0B0h]
0x14007a2ae  movups  [rbp+1A0h+var_160], xmm0
0x14007a2b2  movups  xmm0, xmmword ptr [rax+0C0h]
0x14007a2b9  mov     eax, [rax+0D0h]
0x14007a2bf  mov     [rbp+1A0h+var_130], eax
0x14007a2c2  lea     rax, [rbp+1A0h+var_200]
0x14007a2c6  movups  [rbp+1A0h+var_140], xmm0
0x14007a2ca  movups  [rbp+1A0h+var_150], xmm1
0x14007a2ce  jmp     short loc_14007A2D2
0x14007a2d0  xor     eax, eax
0x14007a2d2  mov     r9d, [r13+54h]
0x14007a2d6  add     r14, 78h ; 'x'
0x14007a2da  mov     r8d, [r13+50h]
0x14007a2de  mov     edx, r12d
0x14007a2e1  mov     rcx, [rdi+28h]
0x14007a2e5  mov     [rsp+2A0h+var_270], rax
0x14007a2ea  lea     rax, xmmword_140156CBC
0x14007a2f1  mov     [rsp+2A0h+var_278], r14
0x14007a2f6  mov     qword ptr [rsp+2A0h+var_280], rax
0x14007a2fb  call    RtlCreateFunctionOverrideFixupInfo2
0x14007a300  mov     ebx, eax
0x14007a302  test    eax, eax
0x14007a304  js      loc_14007A126
0x14007a30a  mov     rcx, [r14]
0x14007a30d  test    rcx, rcx
0x14007a310  jz      short loc_14007A333
0x14007a312  cmp     rsi, cs:SkmiNtosNar
0x14007a319  jz      short loc_14007A333
0x14007a31b  mov     rdx, [rsp+2A0h+var_260]
0x14007a320  xor     r9d, r9d
0x14007a323  mov     r8d, r15d
0x14007a326  mov     dword ptr [rsp+2A0h+var_280], 0
0x14007a32e  call    RtlInitializeSystemOverrideDelta
0x14007a333  mov     [rsi+20h], rdi
0x14007a337  xor     ebx, ebx
0x14007a339  mov     eax, ebx
0x14007a33b  add     rsp, 268h
0x14007a342  pop     r15
0x14007a344  pop     r14
0x14007a346  pop     r13
0x14007a348  pop     r12
0x14007a34a  pop     rdi
0x14007a34b  pop     rsi
0x14007a34c  pop     rbx
0x14007a34d  pop     rbp
0x14007a34e  retn
```
