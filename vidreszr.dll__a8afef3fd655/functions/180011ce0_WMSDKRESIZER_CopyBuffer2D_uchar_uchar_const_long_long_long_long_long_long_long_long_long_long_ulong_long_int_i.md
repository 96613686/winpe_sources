# WMSDKRESIZER::CopyBuffer2D(uchar *,uchar const *,long,long,long,long,long,long,long,long,long,long,ulong,long,int,int)

- ea: `0x180011ce0`
- end: `0x180012395`
- name: `?CopyBuffer2D@WMSDKRESIZER@@QEAAXPEAEPEBEJJJJJJJJJJKJHH@Z`
- size: `1717`
- prototype: `void __fastcall(WMSDKRESIZER *__hidden this, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int, int, int, int, int, unsigned int, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013b90`

## callees

- `0x180011ce0`
- `0x180015905`

## pseudocode

```c
void __fastcall WMSDKRESIZER::CopyBuffer2D(
        WMSDKRESIZER *this,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        unsigned int a14,
        int a15,
        int a16,
        int a17)
{
  __int64 v20; // rbp
  int v21; // r9d
  int v22; // r11d
  int v23; // r8d
  int v24; // ecx
  int v25; // r13d
  int v26; // r14d
  int v27; // r8d
  int v28; // edi
  int v29; // ebx
  int v30; // esi
  int v31; // r12d
  int v32; // eax
  const unsigned __int8 *v33; // rbx
  int v34; // kr1C_4
  int v35; // eax
  __int64 v36; // r11
  unsigned __int8 *v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  int v42; // esi
  int v43; // r14d
  __int64 v44; // rax
  __int64 v45; // rdx
  const unsigned __int8 *v46; // rdi
  unsigned __int8 *v47; // rsi
  const unsigned __int8 *v48; // rbx
  unsigned __int8 *v49; // rbp
  int v50; // eax
  int v51; // r10d
  int v52; // edx
  int v53; // edx
  int v54; // edx
  int v55; // eax
  int v56; // eax
  int v57; // r8d
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  int v61; // eax
  const unsigned __int8 *v62; // rbx
  unsigned __int8 *v63; // rdi
  int v64; // esi
  __int64 v65; // r15
  __int64 v66; // r12
  int v67; // [rsp+20h] [rbp-78h]
  int v68; // [rsp+24h] [rbp-74h]
  int v69; // [rsp+28h] [rbp-70h]
  int v70; // [rsp+2Ch] [rbp-6Ch]
  __int64 v71; // [rsp+38h] [rbp-60h]
  __int64 v72; // [rsp+40h] [rbp-58h]
  __int64 v73; // [rsp+48h] [rbp-50h]
  __int64 v74; // [rsp+50h] [rbp-48h]
  int v75; // [rsp+A0h] [rbp+8h]
  unsigned int v78; // [rsp+108h] [rbp+70h]
  int v79; // [rsp+118h] [rbp+80h]
  int v80; // [rsp+120h] [rbp+88h]

  v20 = a4;
  if ( a16 || a14 && a14 != 3 )
  {
    v21 = -a5;
    if ( a5 > 0 )
      v21 = a5;
  }
  else
  {
    v21 = a5;
  }
  if ( a17 || a14 && a14 != 3 )
  {
    v22 = -a7;
    if ( a7 > 0 )
      v22 = a7;
  }
  else
  {
    v22 = a7;
  }
  v23 = 0;
  v24 = 0;
  if ( a14 > 0x39555659 )
  {
    if ( a14 > 0x55595659 )
    {
      if ( a14 != 1448433985 )
      {
        if ( a14 == 1448433993 )
          goto LABEL_20;
        if ( a14 != 1498831189 )
          goto LABEL_54;
      }
    }
    else if ( a14 != 1431918169 && a14 != 1345401945 && a14 != 1412510809 && a14 != 1412576345 )
    {
      goto LABEL_54;
    }
    goto LABEL_48;
  }
  if ( a14 == 961893977 )
  {
    v25 = a12;
    v26 = a13;
    v27 = a8;
    v28 = a10;
    v29 = a9;
    v30 = a11;
    v75 = (int)v20 / 4;
    v78 = 17;
    v69 = a6 / 4;
    v70 = a12 / 4;
    v31 = a13 / 4;
    v79 = a8 / 4;
    v67 = a10 / 4;
    v80 = a9 / 4;
    v32 = a11 / 4;
    goto LABEL_21;
  }
  if ( a14 > 0x32315659 )
  {
    if ( a14 == 842150992 )
    {
      v25 = a12;
      v27 = a8;
      v28 = a10;
      v26 = a13;
      v31 = a13;
      v29 = a9;
      v30 = a11;
      v75 = (int)v20 / 2;
      v80 = a9;
      v68 = a11;
      v69 = a6 / 2;
      v78 = 24;
      v70 = a12 / 2;
      v79 = a8 / 2;
      v67 = a10 / 2;
      goto LABEL_22;
    }
    if ( a14 != 844715353 && a14 != 909193814 )
      goto LABEL_54;
LABEL_48:
    v24 = 1;
    v23 = 1;
    if ( a16 && (int)v20 <= 0 )
      v23 = -1;
    if ( !a17 )
      goto LABEL_54;
    goto LABEL_52;
  }
  switch ( a14 )
  {
    case 0x32315659u:
LABEL_20:
      v25 = a12;
      v26 = a13;
      v27 = a8;
      v28 = a10;
      v29 = a9;
      v30 = a11;
      v75 = (int)v20 / 2;
      v78 = 20;
      v69 = a6 / 2;
      v70 = a12 / 2;
      v31 = a13 / 2;
      v79 = a8 / 2;
      v67 = a10 / 2;
      v80 = a9 / 2;
      v32 = a11 / 2;
LABEL_21:
      v68 = v32;
LABEL_22:
      v33 = &a3[v29 * (int)v20 + v27];
      v34 = v78 * v21 * v20;
      v35 = v22 * a6;
      v36 = v34 / 16;
      v37 = &a2[v30 * a6 + v28];
      v38 = v35;
      v39 = v35;
      v40 = (int)(v78 * v35) / 16;
      if ( a14 != 842094169 )
      {
        v39 = v40;
        v40 = v38;
      }
      v73 = v40;
      v41 = v21 * (int)v20;
      if ( a14 != 842094169 )
        v41 = v34 / 16;
      v74 = v39;
      if ( a14 != 842094169 )
        v36 = v21 * (int)v20;
      v72 = v41;
      v42 = 0;
      v71 = v36;
      if ( v26 > 0 )
      {
        do
        {
          memcpy_0(v37, v33, v25);
          v33 += v20;
          v37 += a6;
          ++v42;
        }
        while ( v42 < v26 );
        v36 = v71;
      }
      if ( v31 > 0 )
      {
        v43 = 0;
        v44 = v75 * v80;
        v45 = v69 * v68;
        v46 = &a3[v79 + v44 + v72];
        v47 = &a2[v67 + v45 + v73];
        v48 = &a3[v79 + v36 + v44];
        v49 = &a2[v67 + v45 + v74];
        do
        {
          memcpy_0(v47, v48, v70);
          v48 += v75;
          v47 += v69;
          memcpy_0(v49, v46, v70);
          v46 += v75;
          v49 += v69;
          ++v43;
        }
        while ( v43 < v31 );
      }
      return;
    case 0u:
    case 3u:
      v24 = 1;
      v23 = 1;
      if ( a16 )
      {
        if ( (int)v20 <= 0 )
          v23 = -1;
      }
      else if ( v21 > 0 )
      {
        v23 = -1;
      }
      if ( !a17 )
      {
        if ( v22 > 0 )
          v24 = -1;
        break;
      }
LABEL_52:
      if ( a6 <= 0 )
        v24 = -1;
      break;
    case 0x30323449u:
      goto LABEL_20;
  }
LABEL_54:
  v50 = -(int)v20;
  if ( (int)v20 > 0 )
    v50 = v20;
  v51 = v23 * ((int)((a15 * v50 + 31) & 0xFFFFFFE0) / 8);
  if ( a16 )
  {
    v52 = a9 * v51;
  }
  else if ( v23 == 1 )
  {
    v52 = a9 * v51;
  }
  else
  {
    v53 = -v21;
    if ( v21 > 0 )
      v53 = v21;
    v54 = ~a9 + v53;
    v55 = -v51;
    if ( v51 > 0 )
      v55 = v51;
    v52 = v55 * v54;
  }
  v56 = -a6;
  if ( a6 > 0 )
    v56 = a6;
  v57 = v24 * ((int)((a15 * v56 + 31) & 0xFFFFFFE0) / 8);
  if ( a17 )
  {
    v58 = a11 * v57;
  }
  else if ( v24 == 1 )
  {
    v58 = a11 * v57;
  }
  else
  {
    v59 = -v22;
    if ( v22 > 0 )
      v59 = v22;
    v60 = ~a11 + v59;
    v61 = -v57;
    if ( v57 > 0 )
      v61 = v57;
    v58 = v61 * v60;
  }
  v62 = &a3[v52 + ((a15 * a8) >> 3)];
  v63 = &a2[v58 + ((a15 * a10) >> 3)];
  v64 = 0;
  if ( a13 > 0 )
  {
    v65 = v51;
    v66 = v57;
    do
    {
      memcpy_0(v63, v62, (int)((a15 * a12 + 31) & 0xFFFFFFE0) / 8);
      v62 += v65;
      v63 += v66;
      ++v64;
    }
    while ( v64 < a13 );
  }
}

```

## disassembly

```asm
0x180011ce0  mov     [rsp+arg_10], r8
0x180011ce5  mov     [rsp+arg_8], rdx
0x180011cea  mov     [rsp+arg_0], rcx
0x180011cef  push    rbx
0x180011cf0  push    rbp
0x180011cf1  push    rdi
0x180011cf2  push    r12
0x180011cf4  push    r14
0x180011cf6  push    r15
0x180011cf8  sub     rsp, 68h
0x180011cfc  mov     ebx, [rsp+98h+arg_78]
0x180011d03  mov     r14, r8
0x180011d06  mov     r10d, [rsp+98h+arg_68]
0x180011d0e  mov     r12, rdx
0x180011d11  movsxd  rbp, r9d
0x180011d14  test    ebx, ebx
0x180011d16  jnz     short loc_180011D2D
0x180011d18  test    r10d, r10d
0x180011d1b  jz      short loc_180011D23
0x180011d1d  cmp     r10d, 3
0x180011d21  jnz     short loc_180011D2D
0x180011d23  mov     r9d, [rsp+98h+arg_20]
0x180011d2b  jmp     short loc_180011D41
0x180011d2d  mov     r9d, [rsp+98h+arg_20]
0x180011d35  neg     r9d
0x180011d38  cmovs   r9d, [rsp+98h+arg_20]
0x180011d41  mov     edi, [rsp+98h+arg_80]
0x180011d48  test    edi, edi
0x180011d4a  jnz     short loc_180011D61
0x180011d4c  test    r10d, r10d
0x180011d4f  jz      short loc_180011D57
0x180011d51  cmp     r10d, 3
0x180011d55  jnz     short loc_180011D61
0x180011d57  mov     r11d, [rsp+98h+arg_30]
0x180011d5f  jmp     short loc_180011D75
0x180011d61  mov     r11d, [rsp+98h+arg_30]
0x180011d69  neg     r11d
0x180011d6c  cmovs   r11d, [rsp+98h+arg_30]
0x180011d75  movsxd  r15, [rsp+98h+arg_28]
0x180011d7d  xor     r8d, r8d
0x180011d80  xor     ecx, ecx
0x180011d82  mov     [rsp+98h+arg_18], rsi
0x180011d8a  mov     [rsp+98h+var_38], r13
0x180011d8f  cmp     r10d, 39555659h
0x180011d96  ja      loc_180012207
0x180011d9c  jz      loc_18001214A
0x180011da2  cmp     r10d, 32315659h
0x180011da9  ja      loc_180012044
0x180011daf  jz      short loc_180011DD1
0x180011db1  test    r10d, r10d
0x180011db4  jz      loc_180012018
0x180011dba  cmp     r10d, 3
0x180011dbe  jz      loc_180012018
0x180011dc4  cmp     r10d, 30323449h
0x180011dcb  jnz     loc_180012080
0x180011dd1  mov     r13d, [rsp+98h+arg_58]
0x180011dd9  mov     eax, ebp
0x180011ddb  mov     r14d, [rsp+98h+arg_60]
0x180011de3  cdq
0x180011de4  mov     r8d, [rsp+98h+arg_38]
0x180011dec  sub     eax, edx
0x180011dee  mov     edi, [rsp+98h+arg_48]
0x180011df5  mov     ebx, [rsp+98h+arg_40]
0x180011dfc  mov     esi, [rsp+98h+arg_50]
0x180011e03  sar     eax, 1
0x180011e05  mov     dword ptr [rsp+98h+arg_0], eax
0x180011e0c  mov     eax, r15d
0x180011e0f  cdq
0x180011e10  mov     [rsp+98h+arg_68], 14h
0x180011e1b  sub     eax, edx
0x180011e1d  sar     eax, 1
0x180011e1f  mov     [rsp+98h+var_70], eax
0x180011e23  mov     eax, r13d
0x180011e26  cdq
0x180011e27  sub     eax, edx
0x180011e29  sar     eax, 1
0x180011e2b  mov     [rsp+98h+var_6C], eax
0x180011e2f  mov     eax, r14d
0x180011e32  cdq
0x180011e33  sub     eax, edx
0x180011e35  sar     eax, 1
0x180011e37  mov     r12d, eax
0x180011e3a  mov     eax, r8d
0x180011e3d  cdq
0x180011e3e  sub     eax, edx
0x180011e40  sar     eax, 1
0x180011e42  mov     [rsp+98h+arg_78], eax
0x180011e49  mov     eax, edi
0x180011e4b  cdq
0x180011e4c  sub     eax, edx
0x180011e4e  sar     eax, 1
0x180011e50  mov     [rsp+98h+var_78], eax
0x180011e54  mov     eax, ebx
0x180011e56  cdq
0x180011e57  sub     eax, edx
0x180011e59  sar     eax, 1
0x180011e5b  mov     [rsp+98h+arg_80], eax
0x180011e62  mov     eax, esi
0x180011e64  cdq
0x180011e65  sub     eax, edx
0x180011e67  sar     eax, 1
0x180011e69  mov     [rsp+98h+var_74], eax
0x180011e6d  mov     eax, ebp
0x180011e6f  movsxd  rdi, edi
0x180011e72  imul    eax, r9d
0x180011e76  mov     ecx, ebp
0x180011e78  imul    ecx, ebx
0x180011e7b  movsxd  rbx, r8d
0x180011e7e  mov     [rsp+98h+var_68], r12d
0x180011e83  movsxd  r8, eax
0x180011e86  imul    eax, [rsp+98h+arg_68]
0x180011e8e  movsxd  rdx, ecx
0x180011e91  mov     rcx, [rsp+98h+arg_10]
0x180011e99  add     rcx, rdx
0x180011e9c  add     rbx, rcx
0x180011e9f  cdq
0x180011ea0  and     edx, 0Fh
0x180011ea3  add     eax, edx
0x180011ea5  sar     eax, 4
0x180011ea8  movsxd  rcx, eax
0x180011eab  mov     eax, r15d
0x180011eae  imul    eax, r11d
0x180011eb2  mov     [rsp+98h+var_60], rcx
0x180011eb7  mov     ecx, r15d
0x180011eba  mov     r11, [rsp+98h+var_60]
0x180011ebf  imul    ecx, esi
0x180011ec2  movsxd  rdx, ecx
0x180011ec5  mov     rcx, [rsp+98h+arg_8]
0x180011ecd  add     rcx, rdx
0x180011ed0  add     rdi, rcx
0x180011ed3  movsxd  rcx, eax
0x180011ed6  imul    eax, [rsp+98h+arg_68]
0x180011ede  cdq
0x180011edf  and     edx, 0Fh
0x180011ee2  add     eax, edx
0x180011ee4  mov     rdx, rcx
0x180011ee7  sar     eax, 4
0x180011eea  cmp     r10d, 32315659h
0x180011ef1  cdqe
0x180011ef3  cmovnz  rdx, rax
0x180011ef7  cmovnz  rax, rcx
0x180011efb  mov     [rsp+98h+var_50], rax
0x180011f00  mov     rax, r8
0x180011f03  cmovnz  rax, r11
0x180011f07  mov     [rsp+98h+var_48], rdx
0x180011f0c  cmovnz  r11, r8
0x180011f10  mov     [rsp+98h+var_58], rax
0x180011f15  xor     esi, esi
0x180011f17  mov     [rsp+98h+var_60], r11
0x180011f1c  test    r14d, r14d
0x180011f1f  jle     short loc_180011F50
0x180011f21  movsxd  r13, r13d
0x180011f24  nop     dword ptr [rax+00h]
0x180011f28  nop     dword ptr [rax+rax+00000000h]
0x180011f30  mov     r8, r13; Size
0x180011f33  mov     rdx, rbx; Src
0x180011f36  mov     rcx, rdi; void *
0x180011f39  call    memcpy_0
0x180011f3e  add     rbx, rbp
0x180011f41  add     rdi, r15
0x180011f44  inc     esi
0x180011f46  cmp     esi, r14d
0x180011f49  jl      short loc_180011F30
0x180011f4b  mov     r11, [rsp+98h+var_60]
0x180011f50  test    r12d, r12d
0x180011f53  jle     loc_18001237A
0x180011f59  mov     eax, [rsp+98h+arg_80]
0x180011f60  xor     r14d, r14d
0x180011f63  movsxd  r9, dword ptr [rsp+98h+arg_0]
0x180011f6b  mov     edx, [rsp+98h+var_74]
0x180011f6f  mov     r12, r9
0x180011f72  movsxd  r10, [rsp+98h+var_70]
0x180011f77  movsxd  rcx, [rsp+98h+arg_78]
0x180011f7f  mov     r13, r10
0x180011f82  movsxd  r8, [rsp+98h+var_78]
0x180011f87  mov     rdi, [rsp+98h+var_58]
0x180011f8c  mov     rsi, [rsp+98h+var_50]
0x180011f91  mov     rbp, [rsp+98h+var_48]
0x180011f96  movsxd  r15, [rsp+98h+var_6C]
0x180011f9b  imul    eax, r9d
0x180011f9f  imul    edx, r10d
0x180011fa3  cdqe
0x180011fa5  add     rdi, rax
0x180011fa8  movsxd  rdx, edx
0x180011fab  add     rsi, rdx
0x180011fae  add     rdi, rcx
0x180011fb1  add     rdi, [rsp+98h+arg_10]
0x180011fb9  add     rsi, r8
0x180011fbc  add     rsi, [rsp+98h+arg_8]
0x180011fc4  lea     rbx, [r11+rax]
0x180011fc8  add     rbx, rcx
0x180011fcb  add     rbp, rdx
0x180011fce  add     rbx, [rsp+98h+arg_10]
0x180011fd6  add     rbp, r8
0x180011fd9  add     rbp, [rsp+98h+arg_8]
0x180011fe1  mov     r8, r15; Size
0x180011fe4  mov     rdx, rbx; Src
0x180011fe7  mov     rcx, rsi; void *
0x180011fea  call    memcpy_0
0x180011fef  mov     r8, r15; Size
0x180011ff2  mov     rdx, rdi; Src
0x180011ff5  mov     rcx, rbp; void *
0x180011ff8  add     rbx, r12
0x180011ffb  add     rsi, r13
0x180011ffe  call    memcpy_0
0x180012003  add     rdi, r12
0x180012006  add     rbp, r13
0x180012009  inc     r14d
0x18001200c  cmp     r14d, [rsp+98h+var_68]
0x180012011  jl      short loc_180011FE1
0x180012013  jmp     loc_18001237A
0x180012018  mov     ecx, 1
0x18001201d  mov     eax, 0FFFFFFFFh
0x180012022  mov     r8d, ecx
0x180012025  test    ebx, ebx
0x180012027  jz      short loc_180012031
0x180012029  test    ebp, ebp
0x18001202b  cmovle  r8d, eax
0x18001202f  jmp     short loc_180012038
0x180012031  test    r9d, r9d
0x180012034  cmovg   r8d, eax
0x180012038  test    edi, edi
0x18001203a  jnz     short loc_18001207A
0x18001203c  test    r11d, r11d
0x18001203f  cmovg   ecx, eax
0x180012042  jmp     short loc_180012080
0x180012044  cmp     r10d, 32323450h
0x18001204b  jz      short loc_1800120BF
0x18001204d  cmp     r10d, 32595559h
0x180012054  jz      short loc_18001205F
0x180012056  cmp     r10d, 36313256h
0x18001205d  jnz     short loc_180012080
0x18001205f  mov     ecx, 1
0x180012064  mov     eax, 0FFFFFFFFh
0x180012069  mov     r8d, ecx
0x18001206c  test    ebx, ebx
0x18001206e  jz      short loc_180012076
0x180012070  test    ebp, ebp
0x180012072  cmovle  r8d, eax
0x180012076  test    edi, edi
0x180012078  jz      short loc_180012080
0x18001207a  test    r15d, r15d
0x18001207d  cmovle  ecx, eax
0x180012080  mov     esi, [rsp+98h+arg_70]
0x180012087  mov     eax, ebp
0x180012089  neg     eax
0x18001208b  cmovs   eax, ebp
0x18001208e  imul    eax, esi
0x180012091  add     eax, 1Fh
0x180012094  and     eax, 0FFFFFFE0h
0x180012097  cdq
0x180012098  and     edx, 7
0x18001209b  lea     r10d, [rdx+rax]
0x18001209f  sar     r10d, 3
0x1800120a3  imul    r10d, r8d
0x1800120a7  test    ebx, ebx
0x1800120a9  jz      loc_180012269
0x1800120af  mov     edx, r10d
0x1800120b2  imul    edx, [rsp+98h+arg_40]
0x1800120ba  jmp     loc_18001229C
0x1800120bf  mov     r13d, [rsp+98h+arg_58]
0x1800120c7  mov     eax, ebp
0x1800120c9  mov     r8d, [rsp+98h+arg_38]
0x1800120d1  cdq
0x1800120d2  mov     edi, [rsp+98h+arg_48]
0x1800120d9  sub     eax, edx
0x1800120db  mov     r14d, [rsp+98h+arg_60]
0x1800120e3  mov     r12d, r14d
0x1800120e6  mov     ebx, [rsp+98h+arg_40]
0x1800120ed  mov     esi, [rsp+98h+arg_50]
0x1800120f4  sar     eax, 1
0x1800120f6  mov     dword ptr [rsp+98h+arg_0], eax
0x1800120fd  mov     eax, r15d
0x180012100  cdq
0x180012101  mov     [rsp+98h+arg_80], ebx
0x180012108  sub     eax, edx
0x18001210a  mov     [rsp+98h+var_74], esi
0x18001210e  sar     eax, 1
0x180012110  mov     [rsp+98h+var_70], eax
0x180012114  mov     eax, r13d
0x180012117  cdq
0x180012118  mov     [rsp+98h+arg_68], 18h
0x180012123  sub     eax, edx
0x180012125  sar     eax, 1
0x180012127  mov     [rsp+98h+var_6C], eax
0x18001212b  mov     eax, r8d
0x18001212e  cdq
0x18001212f  sub     eax, edx
0x180012131  sar     eax, 1
0x180012133  mov     [rsp+98h+arg_78], eax
0x18001213a  mov     eax, edi
0x18001213c  cdq
0x18001213d  sub     eax, edx
0x18001213f  sar     eax, 1
0x180012141  mov     [rsp+98h+var_78], eax
0x180012145  jmp     loc_180011E6D
0x18001214a  mov     r13d, [rsp+98h+arg_58]
0x180012152  mov     eax, ebp
0x180012154  mov     r14d, [rsp+98h+arg_60]
0x18001215c  cdq
  ... truncated ...
```
