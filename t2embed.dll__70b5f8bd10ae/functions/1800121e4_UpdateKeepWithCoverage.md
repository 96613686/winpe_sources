# UpdateKeepWithCoverage

- ea: `0x1800121e4`
- end: `0x180012a11`
- name: `UpdateKeepWithCoverage`
- size: `2093`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001400c`

## callees

- `0x18000ee40`
- `0x1800121e4`
- `0x1800134a0`
- `0x180015190`
- `0x1800164a0`
- `0x1800164e0`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall UpdateKeepWithCoverage(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        __int16 a4,
        int a5,
        int a6,
        _WORD *a7,
        unsigned __int16 a8,
        __int16 a9,
        __int16 a10)
{
  __int64 v10; // r13
  __int64 v11; // r12
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 result; // rax
  unsigned __int16 v15; // r14
  unsigned __int16 v16; // si
  __int64 v17; // r15
  unsigned __int16 Word; // bx
  __int16 v19; // r11
  int v20; // ecx
  int v21; // r9d
  int v22; // r10d
  unsigned __int16 v23; // dx
  __int64 v24; // rcx
  char v25; // al
  __int64 v26; // rcx
  __int64 v27; // r14
  __int64 v28; // rcx
  unsigned int v29; // ebx
  unsigned __int16 v30; // si
  __int64 v31; // rax
  __int64 v32; // rdi
  int v33; // eax
  int v34; // r14d
  __int64 v35; // rsi
  int v36; // edx
  unsigned __int16 j; // cx
  unsigned __int16 GenericRepeat; // ax
  __int64 v39; // rcx
  unsigned int v40; // r14d
  unsigned __int16 v41; // di
  __int64 v42; // rax
  __int64 v43; // rsi
  unsigned __int16 v44; // cx
  __int64 v45; // r12
  unsigned __int16 v46; // r9
  char v47; // r13
  __int64 v48; // rdx
  unsigned int v49; // r14d
  unsigned __int16 v50; // di
  __int64 v51; // rax
  unsigned __int16 v52; // cx
  __int64 v53; // r12
  unsigned __int16 v54; // r9
  char v55; // r13
  __int64 v56; // rdx
  unsigned __int16 v57; // dx
  int v58; // [rsp+40h] [rbp-79h]
  unsigned __int16 v59; // [rsp+44h] [rbp-75h]
  unsigned __int16 v60; // [rsp+46h] [rbp-73h]
  _WORD v61[2]; // [rsp+48h] [rbp-71h] BYREF
  _WORD v62[2]; // [rsp+4Ch] [rbp-6Dh] BYREF
  unsigned __int16 v63; // [rsp+50h] [rbp-69h]
  __int16 v64; // [rsp+52h] [rbp-67h]
  int i; // [rsp+54h] [rbp-65h]
  int v66; // [rsp+58h] [rbp-61h] BYREF
  __int64 v67; // [rsp+60h] [rbp-59h]
  int v68; // [rsp+68h] [rbp-51h]
  _WORD *v69; // [rsp+70h] [rbp-49h]
  int v70; // [rsp+78h] [rbp-41h]
  unsigned int v71; // [rsp+7Ch] [rbp-3Dh]
  __int64 v72; // [rsp+80h] [rbp-39h]
  __int64 v73; // [rsp+88h] [rbp-31h]
  __int64 v74; // [rsp+90h] [rbp-29h]
  int v75; // [rsp+98h] [rbp-21h] BYREF
  __int16 v76; // [rsp+9Ch] [rbp-1Dh]
  __int64 v77; // [rsp+A0h] [rbp-19h] BYREF
  int v78; // [rsp+A8h] [rbp-11h]

  v74 = a1;
  v10 = 0;
  v75 = 0;
  v76 = 0;
  v11 = a1;
  v12 = a2;
  v77 = 0;
  v78 = 0;
  v64 = a4;
  v63 = a3;
  v67 = a2;
  v69 = a7;
  v62[0] = 0;
  v66 = 0;
  if ( !a6 || !a7 )
    return 0;
  if ( !*(_QWORD *)a1 )
    return 1001;
  v13 = (unsigned int)(a6 + a5);
  if ( (int)v13 + 2 < (unsigned int)v13 || (unsigned int)(v13 + 2) > *(_DWORD *)(a1 + 8) )
    return 1001;
  v15 = _byteswap_ushort(*(_WORD *)(v13 + *(_QWORD *)a1));
  v59 = v15;
  if ( v15 == 1 )
  {
    result = ReadGeneric((__int64 *)a1, (__int64)&v75, 4u, (unsigned __int8 *)&GSUBCOVERAGEFORMAT1_CONTROL, v13, v62);
    if ( (_WORD)result )
      return result;
    v16 = HIWORD(v75);
    v60 = HIWORD(v75);
    v73 = Mem_Alloc(2LL * HIWORD(v75));
    v10 = v73;
    if ( v73 )
    {
      v17 = 0;
      v72 = 0;
      GenericRepeat = ReadGenericRepeat(
                        v11,
                        v73,
                        (unsigned int)WORD_CONTROL,
                        (unsigned int)v13 + v62[0],
                        (__int64)&v66,
                        v16,
                        2);
      v19 = 0;
      Word = GenericRepeat;
      if ( GenericRepeat )
      {
        v26 = v10;
        goto LABEL_40;
      }
      goto LABEL_15;
    }
    return 1005;
  }
  if ( v15 != 2 )
    return 1080;
  result = ReadGeneric((__int64 *)a1, (__int64)&v77, 4u, (unsigned __int8 *)&GSUBCOVERAGEFORMAT2_CONTROL, v13, v62);
  if ( !(_WORD)result )
  {
    v16 = WORD1(v77);
    v60 = WORD1(v77);
    v72 = Mem_Alloc(8LL * WORD1(v77));
    v17 = v72;
    if ( v72 )
    {
      Word = ReadGenericRepeat(
               v11,
               v72,
               (unsigned int)&GSUBRANGERECORD_CONTROL,
               (unsigned int)v13 + v62[0],
               (__int64)&v66,
               v16,
               8);
      if ( Word )
        goto LABEL_39;
      v73 = 0;
      v19 = 0;
LABEL_15:
      v20 = 0;
      v68 = 0;
      v58 = 0;
      v21 = 0;
      v22 = 0;
      for ( i = 0; ; i = v22 )
      {
        if ( (unsigned __int16)v20 >= v16 || Word )
        {
LABEL_38:
          Mem_Free(v10);
LABEL_39:
          v26 = v17;
LABEL_40:
          Mem_Free(v26);
          return Word;
        }
        if ( v15 == 1 )
        {
          v23 = *(_WORD *)(v10 + 2LL * (unsigned __int16)v20);
        }
        else
        {
          v23 = *(_WORD *)(v17 + 8LL * (unsigned __int16)v20) + v21;
          if ( v23 < *(_WORD *)(v17 + 8LL * (unsigned __int16)v20 + 2) )
          {
            LOWORD(v21) = v21 + 1;
            v68 = v21;
            goto LABEL_21;
          }
          LOWORD(v68) = v19;
        }
        LOWORD(v20) = v20 + 1;
        v58 = v20;
LABEL_21:
        if ( v23 >= v63 )
          goto LABEL_24;
        if ( *(unsigned __int8 *)(v23 + v12) != v64 )
          goto LABEL_23;
        switch ( a9 )
        {
          case 1:
            if ( a10 == 1 )
            {
              v57 = *v69 + v23;
              if ( v57 >= v63 )
                goto LABEL_23;
              v24 = v57;
              v19 = 0;
              if ( !*(_BYTE *)(v57 + v12) )
              {
                v25 = v64 + 1;
                goto LABEL_34;
              }
            }
            else
            {
              if ( (unsigned __int16)v22 >= a8 )
              {
                Word = 1080;
                goto LABEL_23;
              }
              if ( v69[(unsigned __int16)v22] >= v63 )
                goto LABEL_23;
              v24 = (unsigned __int16)v69[(unsigned __int16)v22];
              v19 = 0;
              if ( !*(_BYTE *)(v24 + v12) )
              {
                v25 = v64 + 1;
LABEL_34:
                *(_BYTE *)(v24 + v12) = v25;
              }
            }
            break;
          case 2:
            v19 = 0;
            v61[0] = 0;
            if ( (unsigned __int16)v22 >= a8 )
            {
LABEL_107:
              Word = 1080;
              break;
            }
            if ( v69[(unsigned __int16)v22] )
            {
              v49 = a5 + (unsigned __int16)v69[(unsigned __int16)v22];
              Word = ReadWord(v11, v61, v49);
              if ( !Word )
              {
                v50 = v61[0];
                v51 = Mem_Alloc(2LL * v61[0]);
                v19 = 0;
                v43 = v51;
                if ( v51 )
                {
                  Word = ReadGenericRepeat(v11, v51, (unsigned int)WORD_CONTROL, v49 + 2, (__int64)&v66, v50, 2);
                  if ( !Word )
                  {
                    v52 = 0;
                    if ( v50 )
                    {
                      v53 = v67;
                      v54 = v63;
                      v55 = v64;
                      do
                      {
                        if ( *(_WORD *)(v43 + 2LL * v52) < v54 )
                        {
                          v56 = *(unsigned __int16 *)(v43 + 2LL * v52);
                          if ( !*(_BYTE *)(v56 + v53) )
                            *(_BYTE *)(v56 + v53) = v55 + 1;
                        }
                        ++v52;
                      }
                      while ( v52 < v50 );
LABEL_80:
                      v17 = v72;
                      v11 = v74;
                      v10 = v73;
                    }
                  }
LABEL_81:
                  v39 = v43;
LABEL_82:
                  Mem_Free(v39);
                  v22 = i;
                  v12 = v67;
                  v16 = v60;
                  v15 = v59;
LABEL_23:
                  v20 = v58;
LABEL_24:
                  v19 = 0;
                  goto LABEL_25;
                }
LABEL_108:
                v12 = v67;
                Word = 1005;
                v22 = i;
                v16 = v60;
              }
LABEL_48:
              v15 = v59;
            }
            break;
          case 3:
            v19 = 0;
            v61[0] = 0;
            if ( (unsigned __int16)v22 >= a8 )
              goto LABEL_107;
            if ( v69[(unsigned __int16)v22] )
            {
              v40 = a5 + (unsigned __int16)v69[(unsigned __int16)v22];
              Word = ReadWord(v11, v61, v40);
              if ( !Word )
              {
                v41 = v61[0];
                v42 = Mem_Alloc(2LL * v61[0]);
                v19 = 0;
                v43 = v42;
                if ( v42 )
                {
                  Word = ReadGenericRepeat(v11, v42, (unsigned int)WORD_CONTROL, v40 + 2, (__int64)&v66, v41, 2);
                  if ( !Word )
                  {
                    v44 = 0;
                    if ( v41 )
                    {
                      v45 = v67;
                      v46 = v63;
                      v47 = v64;
                      do
                      {
                        if ( *(_WORD *)(v43 + 2LL * v44) < v46 )
                        {
                          v48 = *(unsigned __int16 *)(v43 + 2LL * v44);
                          if ( !*(_BYTE *)(v48 + v45) )
                            *(_BYTE *)(v48 + v45) = v47 + 1;
                        }
                        ++v44;
                      }
                      while ( v44 < v41 );
                      goto LABEL_80;
                    }
                  }
                  goto LABEL_81;
                }
                goto LABEL_108;
              }
              goto LABEL_48;
            }
            break;
          case 4:
            v19 = 0;
            v75 = 0;
            v76 = 0;
            if ( (unsigned __int16)v22 >= a8 )
            {
              Word = 1080;
              break;
            }
            v27 = (unsigned __int16)v22;
            v77 = (unsigned __int16)v22;
            if ( v69[(unsigned __int16)v22] )
            {
              if ( *(_QWORD *)v11 )
              {
                v28 = (unsigned int)(unsigned __int16)v69[(unsigned __int16)v22] + a5;
                v29 = v28 + 2;
                if ( (int)v28 + 2 >= (unsigned int)v28 && v29 <= *(_DWORD *)(v11 + 8) )
                {
                  v30 = _byteswap_ushort(*(_WORD *)(v28 + *(_QWORD *)v11));
                  v61[0] = v30;
                  v31 = Mem_Alloc(2LL * v30);
                  v19 = 0;
                  v32 = v31;
                  if ( v31 )
                  {
                    Word = ReadGenericRepeat(v11, v31, (unsigned int)WORD_CONTROL, v29, (__int64)&v66, v30, 2);
                    if ( !Word )
                    {
                      LOWORD(v33) = 0;
                      v70 = 0;
                      while ( (unsigned __int16)v33 < v30 )
                      {
                        if ( *(_WORD *)(v32 + 2LL * (unsigned __int16)v33) )
                        {
                          v71 = (unsigned __int16)v69[v27]
                              + a5
                              + *(unsigned __int16 *)(v32 + 2LL * (unsigned __int16)v33);
                          Word = ReadGeneric(
                                   (__int64 *)v11,
                                   (__int64)&v75,
                                   4u,
                                   (unsigned __int8 *)&GSUBLIGATURE_CONTROL,
                                   v71,
                                   v62);
                          if ( Word )
                            goto LABEL_37;
                          if ( (unsigned __int16)v75 < v63 && !*(_BYTE *)((unsigned __int16)v75 + v67) )
                          {
                            v34 = HIWORD(v75);
                            v35 = Mem_Alloc(2LL * HIWORD(v75) - 2);
                            if ( !v35 )
                            {
                              Mem_Free(v32);
                              Mem_Free(v10);
                              Mem_Free(v17);
                              return 1005;
                            }
                            Word = ReadGenericRepeat(
                                     v11,
                                     v35,
                                     (unsigned int)WORD_CONTROL,
                                     v71 + v62[0],
                                     (__int64)&v66,
                                     (unsigned __int16)v34 - 1,
                                     2);
                            if ( Word )
                            {
                              Mem_Free(v35);
LABEL_37:
                              Mem_Free(v32);
                              goto LABEL_38;
                            }
                            v36 = v34 - 1;
                            for ( j = 0; j < v36; ++j )
                            {
                              if ( *(_WORD *)(v35 + 2LL * j) >= v63 )
                                break;
                              if ( !*(_BYTE *)(*(unsigned __int16 *)(v35 + 2LL * j) + v67) )
                                break;
                            }
                            if ( j == v36 && !*(_BYTE *)((unsigned __int16)v75 + v67) )
                              *(_BYTE *)((unsigned __int16)v75 + v67) = v64 + 1;
                            Mem_Free(v35);
                            v30 = v61[0];
                            v27 = v77;
                          }
                        }
                        HIWORD(v33) = HIWORD(v70);
                        LOWORD(v33) = v70 + 1;
                        v70 = v33;
                      }
                    }
                    v39 = v32;
                    goto LABEL_82;
                  }
                  goto LABEL_108;
                }
              }
              Word = 1001;
            }
            goto LABEL_48;
          default:
            goto LABEL_23;
        }
        v20 = v58;
LABEL_25:
        v21 = v68;
        LOWORD(v22) = v22 + 1;
      }
    }
    return 1005;
  }
  return result;
}

```

## disassembly

```asm
0x1800121e4  mov     [rsp-8+arg_10], rbx
0x1800121e9  push    rbp
0x1800121ea  push    rsi
0x1800121eb  push    rdi
0x1800121ec  push    r12
0x1800121ee  push    r13
0x1800121f0  push    r14
0x1800121f2  push    r15
0x1800121f4  lea     rbp, [rsp-7]
0x1800121f9  sub     rsp, 0C0h
0x180012200  mov     rax, cs:__security_cookie
0x180012207  xor     rax, rsp
0x18001220a  mov     [rbp+37h+var_40], rax
0x18001220e  xor     eax, eax
0x180012210  mov     [rbp+37h+var_60], rcx
0x180012214  xor     r13d, r13d
0x180012217  mov     [rbp+37h+var_58], eax
0x18001221a  mov     [rbp+37h+var_54], ax
0x18001221e  mov     r12, rcx
0x180012221  mov     rcx, [rbp+37h+arg_30]
0x180012225  mov     rdi, rdx
0x180012228  mov     [rbp+37h+var_50], rax
0x18001222c  mov     [rbp+37h+var_48], eax
0x18001222f  mov     eax, [rbp+37h+arg_28]
0x180012232  mov     [rbp+37h+var_9E], r9w
0x180012237  mov     [rbp+37h+var_A0], r8w
0x18001223c  mov     [rbp+37h+var_90], rdx
0x180012240  mov     [rbp+37h+var_80], rcx
0x180012244  mov     [rbp+37h+var_A4], r13w
0x180012249  mov     [rbp+37h+var_98], r13d
0x18001224d  test    eax, eax
0x18001224f  jz      short loc_18001229E
0x180012251  test    rcx, rcx
0x180012254  jz      short loc_18001229E
0x180012256  mov     rcx, [r12]
0x18001225a  test    rcx, rcx
0x18001225d  jz      short loc_180012272
0x18001225f  mov     ebx, [rbp+37h+arg_20]
0x180012262  add     ebx, eax
0x180012264  lea     eax, [rbx+2]
0x180012267  cmp     eax, ebx
0x180012269  jb      short loc_180012272
0x18001226b  cmp     eax, [r12+8]
0x180012270  jbe     short loc_1800122A3
0x180012272  mov     eax, 3E9h
0x180012277  mov     rcx, [rbp+37h+var_40]
0x18001227b  xor     rcx, rsp; StackCookie
0x18001227e  call    __security_check_cookie
0x180012283  mov     rbx, [rsp+0F0h+arg_10]
0x18001228b  add     rsp, 0C0h
0x180012292  pop     r15
0x180012294  pop     r14
0x180012296  pop     r13
0x180012298  pop     r12
0x18001229a  pop     rdi
0x18001229b  pop     rsi
0x18001229c  pop     rbp
0x18001229d  retn
0x18001229e  mov     eax, r13d
0x1800122a1  jmp     short loc_180012277
0x1800122a3  movzx   r14d, byte ptr [rbx+rcx]
0x1800122a8  movzx   eax, byte ptr [rbx+rcx+1]
0x1800122ad  shl     r14w, 8
0x1800122b2  or      r14w, ax
0x1800122b6  movzx   ecx, r14w
0x1800122ba  mov     [rbp+37h+var_AC], r14w
0x1800122bf  sub     ecx, 1
0x1800122c2  jz      loc_180012684
0x1800122c8  cmp     ecx, 1
0x1800122cb  jnz     loc_18001267A
0x1800122d1  lea     rax, [rbp+37h+var_A4]
0x1800122d5  lea     r8d, [rcx+3]
0x1800122d9  mov     [rsp+0F0h+var_C8], rax
0x1800122de  lea     r9, GSUBCOVERAGEFORMAT2_CONTROL
0x1800122e5  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x1800122e9  lea     rdx, [rbp+37h+var_50]
0x1800122ed  mov     rcx, r12
0x1800122f0  call    ReadGeneric
0x1800122f5  test    ax, ax
0x1800122f8  jnz     loc_180012277
0x1800122fe  movzx   esi, word ptr [rbp+37h+var_50+2]
0x180012302  mov     ecx, esi
0x180012304  mov     [rbp+37h+var_AA], si
0x180012308  shl     rcx, 3; Size
0x18001230c  call    Mem_Alloc
0x180012311  mov     [rbp+37h+var_70], rax
0x180012315  mov     r15, rax
0x180012318  test    rax, rax
0x18001231b  jz      loc_180012739
0x180012321  movzx   r9d, [rbp+37h+var_A4]
0x180012326  lea     rax, [rbp+37h+var_98]
0x18001232a  mov     [rsp+0F0h+var_C0], 8
0x180012331  lea     r8, GSUBRANGERECORD_CONTROL
0x180012338  add     r9d, ebx
0x18001233b  mov     word ptr [rsp+0F0h+var_C8], si
0x180012340  mov     rdx, r15
0x180012343  mov     [rsp+0F0h+var_D0], rax
0x180012348  mov     rcx, r12
0x18001234b  call    ReadGenericRepeat
0x180012350  movzx   ebx, ax
0x180012353  test    ax, ax
0x180012356  jnz     loc_180012463
0x18001235c  mov     [rbp+37h+var_68], r13
0x180012360  xor     r11d, r11d
0x180012363  mov     ecx, r11d
0x180012366  mov     [rbp+37h+var_88], r11d
0x18001236a  mov     [rbp+37h+var_B0], ecx
0x18001236d  mov     r9d, r11d
0x180012370  mov     r10d, r11d
0x180012373  mov     [rbp+37h+var_9C], r11d
0x180012377  mov     r8d, 438h
0x18001237d  cmp     cx, si
0x180012380  jnb     loc_18001245B
0x180012386  test    bx, bx
0x180012389  jnz     loc_18001245B
0x18001238f  mov     edx, 1
0x180012394  movzx   eax, cx
0x180012397  cmp     r14w, dx
0x18001239b  jz      short loc_1800123EB
0x18001239d  movzx   edx, r9w
0x1800123a1  add     dx, [r15+rax*8]
0x1800123a6  cmp     dx, [r15+rax*8+2]
0x1800123ac  jnb     loc_18001244C
0x1800123b2  inc     r9w
0x1800123b6  mov     [rbp+37h+var_88], r9d
0x1800123ba  movzx   r11d, [rbp+37h+var_A0]
0x1800123bf  cmp     dx, r11w
0x1800123c3  jnb     short loc_1800123DA
0x1800123c5  movzx   r9d, [rbp+37h+var_9E]
0x1800123ca  movzx   eax, dx
0x1800123cd  movzx   ecx, byte ptr [rax+rdi]
0x1800123d1  cmp     cx, r9w
0x1800123d5  jz      short loc_1800123F9
0x1800123d7  mov     ecx, [rbp+37h+var_B0]
0x1800123da  xor     r11d, r11d
0x1800123dd  mov     r9d, [rbp+37h+var_88]
0x1800123e1  inc     r10w
0x1800123e5  mov     [rbp+37h+var_9C], r10d
0x1800123e9  jmp     short loc_18001237D
0x1800123eb  movzx   edx, word ptr [r13+rax*2+0]
0x1800123f1  inc     cx
0x1800123f4  mov     [rbp+37h+var_B0], ecx
0x1800123f7  jmp     short loc_1800123BA
0x1800123f9  movzx   ecx, [rbp+37h+arg_40]
0x180012400  sub     ecx, 1
0x180012403  jnz     short loc_180012473
0x180012405  mov     ecx, 1
0x18001240a  cmp     [rbp+37h+arg_48], cx
0x180012411  jz      loc_1800129CE
0x180012417  cmp     r10w, [rbp+37h+arg_38]
0x18001241c  jnb     loc_1800129FB
0x180012422  mov     r9, [rbp+37h+var_80]
0x180012426  movzx   eax, r10w
0x18001242a  cmp     [r9+rax*2], r11w
0x18001242f  jnb     short loc_1800123D7
0x180012431  movzx   ecx, word ptr [r9+rax*2]
0x180012436  xor     r11d, r11d
0x180012439  cmp     [rcx+rdi], r11b
0x18001243d  jnz     short loc_180012447
0x18001243f  mov     al, byte ptr [rbp+37h+var_9E]
0x180012442  add     al, 1
0x180012444  mov     [rcx+rdi], al
0x180012447  mov     ecx, [rbp+37h+var_B0]
0x18001244a  jmp     short loc_1800123DD
0x18001244c  mov     word ptr [rbp+37h+var_88], r11w
0x180012451  jmp     short loc_1800123F1
0x180012453  mov     rcx, rdi
0x180012456  call    Mem_Free
0x18001245b  mov     rcx, r13
0x18001245e  call    Mem_Free
0x180012463  mov     rcx, r15
0x180012466  call    Mem_Free
0x18001246b  movzx   eax, bx
0x18001246e  jmp     loc_180012277
0x180012473  sub     ecx, 1
0x180012476  jz      loc_1800128BF
0x18001247c  sub     ecx, 1
0x18001247f  jz      loc_1800127D5
0x180012485  cmp     ecx, 1
0x180012488  jnz     loc_1800123D7
0x18001248e  xor     eax, eax
0x180012490  xor     r11d, r11d
0x180012493  mov     [rbp+37h+var_58], eax
0x180012496  mov     [rbp+37h+var_54], ax
0x18001249a  cmp     r10w, [rbp+37h+arg_38]
0x18001249f  jnb     loc_180012743
0x1800124a5  mov     r9, [rbp+37h+var_80]
0x1800124a9  movzx   r14d, r10w
0x1800124ad  mov     [rbp+37h+var_50], r14
0x1800124b1  cmp     [r9+r14*2], r11w
0x1800124b6  jz      short loc_1800124C6
0x1800124b8  mov     rdx, [r12]
0x1800124bc  test    rdx, rdx
0x1800124bf  jnz     short loc_1800124D0
0x1800124c1  mov     ebx, 3E9h
0x1800124c6  movzx   r14d, [rbp+37h+var_AC]
0x1800124cb  jmp     loc_180012447
0x1800124d0  movzx   eax, word ptr [r9+r14*2]
0x1800124d5  mov     ecx, [rbp+37h+arg_20]
0x1800124d8  add     ecx, eax
0x1800124da  lea     ebx, [rcx+2]
0x1800124dd  cmp     ebx, ecx
0x1800124df  jb      short loc_1800124C1
0x1800124e1  cmp     ebx, [r12+8]
0x1800124e6  ja      short loc_1800124C1
0x1800124e8  movzx   esi, byte ptr [rcx+rdx]
0x1800124ec  movzx   eax, byte ptr [rcx+rdx+1]
0x1800124f1  shl     si, 8
0x1800124f5  or      si, ax
0x1800124f8  movzx   ecx, si
0x1800124fb  add     rcx, rcx; Size
0x1800124fe  mov     [rbp+37h+var_A8], si
0x180012502  call    Mem_Alloc
0x180012507  xor     r11d, r11d
0x18001250a  mov     rdi, rax
0x18001250d  test    rax, rax
0x180012510  jz      loc_1800129B2
0x180012516  mov     [rsp+0F0h+var_C0], 2
0x18001251d  lea     rax, [rbp+37h+var_98]
0x180012521  mov     word ptr [rsp+0F0h+var_C8], si
0x180012526  lea     r8, WORD_CONTROL
0x18001252d  mov     r9d, ebx
0x180012530  mov     [rsp+0F0h+var_D0], rax
0x180012535  mov     rdx, rdi
0x180012538  mov     rcx, r12
0x18001253b  call    ReadGenericRepeat
0x180012540  xor     edx, edx
0x180012542  movzx   ebx, ax
0x180012545  test    ax, ax
0x180012548  jnz     loc_1800127A0
0x18001254e  mov     eax, edx
0x180012550  mov     [rbp+37h+var_78], edx
0x180012553  lea     ecx, [rdx+1]
0x180012556  cmp     ax, si
0x180012559  jnb     loc_1800127A0
0x18001255f  movzx   eax, ax
0x180012562  cmp     [rdi+rax*2], dx
0x180012566  jz      loc_18001266C
0x18001256c  movzx   eax, word ptr [rdi+rax*2]
0x180012570  lea     r9, GSUBLIGATURE_CONTROL
0x180012577  mov     rcx, [rbp+37h+var_80]
0x18001257b  lea     rdx, [rbp+37h+var_58]
0x18001257f  add     eax, [rbp+37h+arg_20]
0x180012582  mov     r8d, 4
0x180012588  movzx   ecx, word ptr [rcx+r14*2]
0x18001258d  add     eax, ecx
0x18001258f  lea     rcx, [rbp+37h+var_A4]
0x180012593  mov     [rsp+0F0h+var_C8], rcx
0x180012598  mov     rcx, r12
0x18001259b  mov     [rbp+37h+var_74], eax
0x18001259e  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800125a2  call    ReadGeneric
0x1800125a7  xor     edx, edx
0x1800125a9  movzx   ebx, ax
0x1800125ac  test    ax, ax
0x1800125af  jnz     loc_180012453
0x1800125b5  movzx   eax, [rbp+37h+var_A0]
0x1800125b9  cmp     word ptr [rbp+37h+var_58], ax
0x1800125bd  jnb     loc_180012667
0x1800125c3  movzx   eax, word ptr [rbp+37h+var_58]
0x1800125c7  mov     rcx, [rbp+37h+var_90]
0x1800125cb  cmp     [rax+rcx], dl
0x1800125ce  jnz     loc_180012667
0x1800125d4  movzx   r14d, word ptr [rbp+37h+var_58+2]
0x1800125d9  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[r14*2]; Size
0x1800125e1  call    Mem_Alloc
0x1800125e6  mov     rsi, rax
0x1800125e9  test    rax, rax
0x1800125ec  jz      loc_180012721
0x1800125f2  movzx   r9d, [rbp+37h+var_A4]
0x1800125f7  lea     ecx, [r14-1]
0x1800125fb  add     r9d, [rbp+37h+var_74]
0x1800125ff  lea     rax, [rbp+37h+var_98]
0x180012603  mov     [rsp+0F0h+var_C0], 2
0x18001260a  lea     r8, WORD_CONTROL
0x180012611  mov     word ptr [rsp+0F0h+var_C8], cx
0x180012616  mov     rdx, rsi
0x180012619  mov     rcx, r12
0x18001261c  mov     [rsp+0F0h+var_D0], rax
0x180012621  call    ReadGenericRepeat
0x180012626  xor     r10d, r10d
0x180012629  movzx   ebx, ax
0x18001262c  test    ax, ax
0x18001262f  jnz     loc_180012A04
0x180012635  mov     edx, r14d
0x180012638  lea     r11d, [r10+1]
0x18001263c  sub     edx, r11d
0x18001263f  mov     ecx, r10d
0x180012642  test    edx, edx
0x180012644  jg      loc_18001274B
0x18001264a  movzx   eax, cx
0x18001264d  cmp     eax, edx
0x18001264f  jz      loc_180012780
0x180012655  mov     rcx, rsi
0x180012658  call    Mem_Free
0x18001265d  movzx   esi, [rbp+37h+var_A8]
0x180012661  xor     edx, edx
0x180012663  mov     r14, [rbp+37h+var_50]
0x180012667  mov     ecx, 1
0x18001266c  mov     eax, [rbp+37h+var_78]
  ... truncated ...
```
