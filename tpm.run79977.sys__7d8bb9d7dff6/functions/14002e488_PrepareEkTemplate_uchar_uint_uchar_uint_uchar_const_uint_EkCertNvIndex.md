# PrepareEkTemplate(uchar *,uint *,uchar *,uint,uchar const *,uint,EkCertNvIndex *)

- ea: `0x14002e488`
- end: `0x14002ecab`
- name: `?PrepareEkTemplate@@YAJPEAEPEAI0IPEBEIPEAVEkCertNvIndex@@@Z`
- size: `2083`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int, const unsigned __int8 *Src, unsigned int, struct EkCertNvIndex *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002d050`

## callees

- `0x14002dde8`
- `0x14002e488`
- `0x140039840`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall PrepareEkTemplate(
        unsigned __int8 *a1,
        unsigned int *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        const unsigned __int8 *Src,
        unsigned int a6,
        struct EkCertNvIndex *a7)
{
  unsigned int v7; // r10d
  __int64 v10; // rax
  unsigned int *v11; // r11
  unsigned int v12; // r9d
  const void *v13; // r10
  __int64 v14; // r14
  __int16 v15; // r12
  __int16 v16; // r13
  unsigned int v17; // ebp
  unsigned __int64 v18; // rbx
  int v19; // r15d
  __int16 v20; // dx
  unsigned int v21; // ecx
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // edi
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // r13d
  unsigned __int64 v33; // rbp
  unsigned __int64 v34; // rbx
  __int16 v35; // ax
  __int16 v36; // r12
  __int64 result; // rax
  unsigned int v38; // eax
  unsigned int v39; // r8d
  __int16 v40; // cx
  size_t v41; // rdx
  unsigned int v42; // edi
  __int64 v43; // rcx
  unsigned __int64 v44; // rax
  __int16 v45; // ax
  __int16 v46; // dx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int16 v50; // ax
  __int64 v51; // rcx
  __int16 v52; // ax
  unsigned __int16 v53; // r9
  __int64 v54; // rdx
  unsigned __int64 v55; // r8
  __int64 v56; // rcx
  unsigned int v57; // edx
  __int64 v58; // rdx
  __int16 v59; // ax
  unsigned __int16 v60; // ax
  unsigned int v61; // r12d
  __int64 v62; // r9
  unsigned __int64 v63; // r10
  __int16 v64; // r11
  int v65; // edi
  __int64 v66; // rcx
  unsigned int v67; // edx
  int v68; // r14d
  unsigned __int16 v69; // bp
  unsigned __int16 v70; // r13
  unsigned int v71; // ebp
  __int64 v72; // rcx
  unsigned int v73; // ebp
  __int16 v74; // [rsp+20h] [rbp-78h]
  unsigned __int16 v75; // [rsp+20h] [rbp-78h]
  unsigned int v76; // [rsp+28h] [rbp-70h]
  const unsigned __int8 *v77; // [rsp+28h] [rbp-70h]
  __int64 v78; // [rsp+30h] [rbp-68h] BYREF
  __int16 v80; // [rsp+B0h] [rbp+18h]
  __int16 v81; // [rsp+B0h] [rbp+18h]

  v7 = a4;
  if ( a3 )
  {
    if ( !a1 )
      return 3221225485LL;
    if ( !a2 )
      return 3221225485LL;
    if ( a4 > 0x400 )
      return 3221225485LL;
    v32 = a6;
    if ( a6 > 0x400 )
      return 3221225485LL;
    v33 = a4;
    if ( a4 < 2uLL )
      return 3221225485LL;
    v34 = *a2;
    if ( v34 < 2 )
    {
      v19 = 1116;
      goto LABEL_133;
    }
    v35 = *(_WORD *)a3;
    *(_WORD *)a1 = *(_WORD *)a3;
    v36 = __ROR2__(v35, 8);
    if ( v36 != 1 && v36 != 35 )
      return 3221225474LL;
    v19 = 602;
    if ( v36 != 1 )
      v19 = 1116;
    if ( a4 < 4uLL )
      return 3221225485LL;
    if ( v34 < 4 )
      goto LABEL_133;
    *((_WORD *)a1 + 1) = *((_WORD *)a3 + 1);
    if ( a4 < 8uLL )
      return 3221225485LL;
    if ( v34 < 8 )
      goto LABEL_133;
    v38 = *((_DWORD *)a3 + 1);
    *((_DWORD *)a1 + 1) = v38;
    if ( (_byteswap_ulong(v38) & 0x30032) != 0x30032 )
      return 3221225485LL;
    v39 = 10;
    if ( a4 < 0xAuLL )
      return 3221225485LL;
    if ( v34 < 0xA )
      goto LABEL_133;
    v40 = *((_WORD *)a3 + 4);
    *((_WORD *)a1 + 4) = v40;
    v41 = (unsigned __int16)__ROR2__(v40, 8);
    if ( v36 == 1 )
      v19 = v41 + v19 - 64;
    if ( (_WORD)v41 )
    {
      if ( (unsigned __int16)v41 > 0x80u )
        return 3221225485LL;
      v42 = v41 + 10;
      if ( (unsigned int)(v41 + 10) < 0xA || v42 > a4 )
        return 3221225485LL;
      if ( v42 > (unsigned int)v34 )
        goto LABEL_133;
      memmove(a1 + 10, a3 + 10, v41);
      v7 = a4;
      v39 = v42;
    }
    v43 = v39 + 2;
    if ( (unsigned int)v43 < v39 )
      return 3221225485LL;
    v44 = v39 + 2LL;
    if ( v44 > v33 )
      return 3221225485LL;
    if ( v44 > v34 )
    {
LABEL_133:
      result = 3221225532LL;
      *a2 = v19;
      return result;
    }
    v45 = *(_WORD *)&a3[v39];
    *(_WORD *)&a1[v39] = v45;
    v46 = __ROR2__(v45, 8);
    if ( v46 == 6 || v46 == 19 )
    {
      v47 = v39 + 4;
      if ( (unsigned int)v47 < (unsigned int)v43 || v43 + 2 > v33 )
        return 3221225485LL;
      if ( v43 + 2 > v34 )
        goto LABEL_133;
      *(_WORD *)&a1[v43] = *(_WORD *)&a3[v43];
      v48 = v39 + 6;
      if ( (unsigned int)v48 < (unsigned int)v47 || v47 + 2 > v33 )
        return 3221225485LL;
      if ( v47 + 2 > v34 )
        goto LABEL_133;
      *(_WORD *)&a1[v47] = *(_WORD *)&a3[v47];
      v49 = v39 + 8;
      if ( (unsigned int)v49 < (unsigned int)v48 || v48 + 2 > v33 )
        return 3221225485LL;
      if ( v48 + 2 > v34 )
        goto LABEL_133;
      v50 = *(_WORD *)&a3[v48];
      *(_WORD *)&a1[v48] = v50;
      if ( __ROR2__(v50, 8) != 16 )
        return 3221225485LL;
      v51 = v39 + 10;
      if ( (unsigned int)v51 < (unsigned int)v49 || v49 + 2 > v33 )
        return 3221225485LL;
      if ( v49 + 2 > v34 )
        goto LABEL_133;
      v52 = *(_WORD *)&a3[v49];
      *(_WORD *)&a1[v49] = v52;
      v53 = __ROR2__(v52, 8);
      if ( v36 == 1 )
      {
        v54 = v39 + 14;
        if ( (unsigned int)v54 < (unsigned int)v51 || v51 + 4 > v33 )
          return 3221225485LL;
        if ( v51 + 4 <= v34 )
        {
          v29 = v39 + 16;
          *(_DWORD *)&a1[v51] = *(_DWORD *)&a3[v51];
          if ( v39 + 16 >= v39 + 14 )
          {
            v55 = v54 + 2;
            v56 = (unsigned int)v54;
            if ( v54 + 2 <= v33 )
            {
              v57 = v29 + (unsigned __int16)__ROR2__(*(_WORD *)&a3[v54], 8);
              if ( v57 >= v29 && v57 <= v7 )
              {
                v17 = (unsigned __int16)(((unsigned int)v53 + 7) >> 3);
                v19 = v17 + v19 - 512;
                if ( v55 <= v34 )
                {
                  *(_WORD *)&a1[v56] = __ROR2__(v17, 8);
                  if ( v29 + v17 >= v29 && v29 + v17 <= (unsigned int)v34 )
                  {
                    if ( Src )
                    {
                      if ( a6 > v17 )
                        v32 = (unsigned __int16)(((unsigned int)v53 + 7) >> 3);
                      memmove(&a1[v29], Src, v32);
                      v29 += v32;
                      LOWORD(v17) = v17 - v32;
                    }
LABEL_31:
                    memset(&a1[v29], 0, (unsigned __int16)v17);
                    v31 = (unsigned __int16)v17;
LABEL_130:
                    v29 += v31;
LABEL_131:
                    result = 0;
                    *a2 = v29;
                    return result;
                  }
                }
                goto LABEL_133;
              }
            }
          }
          return 3221225485LL;
        }
        goto LABEL_133;
      }
      v58 = v39 + 12;
      if ( (unsigned int)v58 < (unsigned int)v51 || v51 + 2 > v33 )
        return 3221225485LL;
      if ( v51 + 2 > v34 )
        goto LABEL_133;
      v59 = *(_WORD *)&a3[v51];
      *(_WORD *)&a1[v51] = v59;
      v60 = __ROR2__(v59, 8);
      if ( v60 == 7 )
        goto LABEL_99;
      if ( v60 == 16 )
      {
        v61 = v39 + 14;
LABEL_102:
        if ( v61 < (unsigned int)v58 )
          return 3221225485LL;
        v62 = (unsigned int)v58;
        v63 = (unsigned int)v58 + 2LL;
        if ( v63 > v33 )
          return 3221225485LL;
        v64 = *(_WORD *)&a3[(unsigned int)v58];
        v65 = (unsigned __int16)__ROR2__(v64, 8);
        v66 = v61 + v65;
        if ( (unsigned int)v66 < v61 )
          return 3221225485LL;
        if ( (unsigned int)v66 > a4 )
          return 3221225485LL;
        v67 = v66 + 2;
        if ( (int)v66 + 2 < (unsigned int)v66 )
          return 3221225485LL;
        if ( v66 + 2 > v33 )
          return 3221225485LL;
        v81 = *(_WORD *)&a3[v66];
        v68 = (unsigned __int16)__ROR2__(v81, 8);
        if ( v68 + v67 < v67 || v68 + v67 > a4 )
          return 3221225485LL;
        if ( Src )
        {
          v69 = a6;
          if ( (unsigned __int16)a6 > (unsigned __int16)v65 )
            v69 = v65;
          v70 = a6 - v69;
          v75 = v69;
          v77 = &Src[v69];
          if ( (unsigned __int16)(a6 - v69) > (unsigned __int16)v68 )
            v70 = v68;
        }
        else
        {
          v69 = 0;
          v75 = 0;
          v70 = 0;
          v77 = 0;
        }
        v19 = v68 + v65 + v19 - 1024;
        if ( v63 <= v34 )
        {
          *(_WORD *)&a1[v62] = v64;
          if ( (unsigned int)v66 <= (unsigned int)v34 )
          {
            if ( Src )
            {
              memmove(&a1[v61], Src, v69);
              v71 = v61 + v69;
              LOWORD(v65) = v65 - v75;
            }
            else
            {
              v71 = v61;
            }
            memset(&a1[v71], 0, (unsigned __int16)v65);
            v72 = v71 + (unsigned __int16)v65;
            v73 = v72 + 2;
            if ( (int)v72 + 2 >= (unsigned int)v72 && v72 + 2 <= v34 )
            {
              *(_WORD *)&a1[v72] = v81;
              if ( v68 + v73 >= v73 && v68 + v73 <= (unsigned int)v34 )
              {
                if ( v77 )
                {
                  memmove(&a1[v73], v77, v70);
                  v29 = v73 + v70;
                  LOWORD(v68) = v68 - v70;
                }
                else
                {
                  v29 = v72 + 2;
                }
                memset(&a1[v29], 0, (unsigned __int16)v68);
                v31 = (unsigned __int16)v68;
                goto LABEL_130;
              }
            }
          }
        }
        goto LABEL_133;
      }
      if ( v60 == 32 || (unsigned int)v60 - 33 <= 1 )
      {
LABEL_99:
        if ( v39 + 14 < v39 + 12 || v58 + 2 > v33 )
          return 3221225485LL;
        if ( v58 + 2 > v34 )
          goto LABEL_133;
        *(_WORD *)&a1[v58] = *(_WORD *)&a3[v58];
        LODWORD(v58) = v39 + 14;
        v61 = v39 + 16;
        goto LABEL_102;
      }
    }
    return 3221225474LL;
  }
  v10 = DefaultTemplateForIndex(&v78, a7);
  v12 = *(unsigned __int16 *)(v10 + 8);
  v13 = *(const void **)(v10 + 16);
  v14 = *(unsigned __int16 *)(v10 + 24);
  v15 = *(_WORD *)(v10 + 26);
  v16 = *(_WORD *)(v10 + 28);
  v17 = *(unsigned __int16 *)(v10 + 40);
  v80 = *(_WORD *)(v10 + 30);
  v76 = *(_DWORD *)(v10 + 36);
  v74 = *(_WORD *)(v10 + 32);
  if ( a1 && v11 )
  {
    v18 = *v11;
    v19 = 391;
    if ( v18 >= 2 )
    {
      v20 = *(_WORD *)(v10 + 2);
      v21 = *(_DWORD *)(v10 + 4);
      *(_WORD *)a1 = __ROR2__(*(_WORD *)v10, 8);
      if ( v18 >= 4 )
      {
        *((_WORD *)a1 + 1) = __ROR2__(v20, 8);
        if ( v18 >= 8 )
        {
          *((_DWORD *)a1 + 1) = _byteswap_ulong(v21);
          if ( v18 >= 0xA )
          {
            v22 = v12 + 10;
            *((_WORD *)a1 + 4) = __ROR2__(v12, 8);
            if ( (unsigned int)v22 >= 0xA && (unsigned int)v22 <= (unsigned int)v18 )
            {
              memmove(a1 + 10, v13, v12);
              v23 = (unsigned int)(v22 + 2);
              if ( (unsigned int)v23 >= (unsigned int)v22 && v22 + 2 <= v18 )
              {
                v24 = (unsigned int)(v22 + 4);
                *(_WORD *)&a1[v22] = __ROR2__(v14, 8);
                if ( (unsigned int)v24 >= (unsigned int)v23 && v23 + 2 <= v18 )
                {
                  *(_WORD *)&a1[v23] = __ROR2__(v15, 8);
                  v25 = (unsigned int)(v22 + 6);
                  if ( (unsigned int)v25 >= (unsigned int)v24 && v24 + 2 <= v18 )
                  {
                    *(_WORD *)&a1[v24] = __ROR2__(v16, 8);
                    v26 = (unsigned int)(v22 + 8);
                    if ( (unsigned int)v26 >= (unsigned int)v25 && v25 + 2 <= v18 )
                    {
                      *(_WORD *)&a1[v25] = __ROR2__(v80, 8);
                      v27 = (unsigned int)(v22 + 10);
                      if ( (unsigned int)v27 >= (unsigned int)v26 && v26 + 2 <= v18 )
                      {
                        *(_WORD *)&a1[v26] = __ROR2__(v74, 8);
                        v28 = (unsigned int)(v22 + 14);
                        if ( (unsigned int)v28 >= (unsigned int)v27 && v27 + 4 <= v18 )
                        {
                          v29 = v22 + 16;
                          *(_DWORD *)&a1[v27] = _byteswap_ulong(v76);
                          if ( (int)v27 + 6 >= (unsigned int)(v27 + 4) && v28 + 2 <= v18 )
                          {
                            *(_WORD *)&a1[v28] = __ROR2__(v17, 8);
                            if ( v29 + v17 >= v29 && v29 + v17 <= (unsigned int)v18 )
                            {
                              if ( Src )
                              {
                                v30 = a6;
                                if ( a6 > v17 )
                                  v30 = v17;
                                memmove(&a1[v29], Src, v30);
                                v29 += v30;
                                LOWORD(v17) = v17 - v30;
                              }
                              if ( !(_WORD)v17 )
                                goto LABEL_131;
                              goto LABEL_31;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    goto LABEL_133;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14002e488  mov     rax, rsp
0x14002e48b  mov     [rax+8], rbx
0x14002e48f  mov     [rax+20h], r9d
0x14002e493  mov     [rax+10h], rdx
0x14002e497  push    rbp
0x14002e498  push    rsi
0x14002e499  push    rdi
0x14002e49a  push    r12
0x14002e49c  push    r13
0x14002e49e  push    r14
0x14002e4a0  push    r15
0x14002e4a2  sub     rsp, 60h
0x14002e4a6  mov     r10d, r9d
0x14002e4a9  mov     r14, r8
0x14002e4ac  mov     r11, rdx
0x14002e4af  mov     rsi, rcx
0x14002e4b2  test    r8, r8
0x14002e4b5  jnz     loc_14002E6F6
0x14002e4bb  mov     rdx, [rsp+98h+arg_30]
0x14002e4c3  lea     rcx, [rax-68h]
0x14002e4c7  call    ?DefaultTemplateForIndex@@YA?AU_EKCERT_TEMPLATE@@PEAVEkCertNvIndex@@@Z; DefaultTemplateForIndex(EkCertNvIndex *)
0x14002e4cc  movzx   ecx, word ptr [rax+1Eh]
0x14002e4d0  movzx   edx, word ptr [rax+20h]
0x14002e4d4  movzx   r9d, word ptr [rax+8]
0x14002e4d9  mov     r10, [rax+10h]
0x14002e4dd  movzx   r14d, word ptr [rax+18h]
0x14002e4e2  movzx   r12d, word ptr [rax+1Ah]
0x14002e4e7  movzx   r13d, word ptr [rax+1Ch]
0x14002e4ec  movzx   ebp, word ptr [rax+28h]
0x14002e4f0  mov     [rsp+98h+arg_10], cx
0x14002e4f8  mov     ecx, [rax+24h]
0x14002e4fb  mov     dword ptr [rsp+98h+var_70], ecx
0x14002e4ff  mov     [rsp+98h+var_78], dx
0x14002e504  test    rsi, rsi
0x14002e507  jz      loc_14002EC8D
0x14002e50d  test    r11, r11
0x14002e510  jz      loc_14002EC8D
0x14002e516  mov     ebx, [r11]
0x14002e519  mov     r15d, 187h
0x14002e51f  cmp     rbx, 2
0x14002e523  jb      loc_14002EC7B
0x14002e529  movzx   edx, word ptr [rax+2]
0x14002e52d  mov     ecx, [rax+4]
0x14002e530  movzx   eax, word ptr [rax]
0x14002e533  ror     ax, 8
0x14002e537  mov     [rsi], ax
0x14002e53a  cmp     rbx, 4
0x14002e53e  jb      loc_14002EC7B
0x14002e544  ror     dx, 8
0x14002e548  mov     [rsi+2], dx
0x14002e54c  cmp     rbx, 8
0x14002e550  jb      loc_14002EC7B
0x14002e556  mov     r8d, 0Ah
0x14002e55c  bswap   ecx
0x14002e55e  mov     [rsi+4], ecx
0x14002e561  cmp     rbx, r8
0x14002e564  jb      loc_14002EC7B
0x14002e56a  movzx   eax, r9w
0x14002e56e  lea     edi, [r9+0Ah]
0x14002e572  ror     ax, 8
0x14002e576  mov     [rsi+8], ax
0x14002e57a  cmp     edi, r8d
0x14002e57d  jb      loc_14002EC7B
0x14002e583  cmp     edi, ebx
0x14002e585  ja      loc_14002EC7B
0x14002e58b  mov     r8d, r9d; Size
0x14002e58e  lea     rcx, [rsi+0Ah]; void *
0x14002e592  mov     rdx, r10; Src
0x14002e595  call    memmove
0x14002e59a  lea     edx, [rdi+2]
0x14002e59d  cmp     edx, edi
0x14002e59f  jb      loc_14002EC7B
0x14002e5a5  lea     rax, [rdi+2]
0x14002e5a9  cmp     rax, rbx
0x14002e5ac  ja      loc_14002EC7B
0x14002e5b2  ror     r14w, 8
0x14002e5b7  lea     ecx, [rdx+2]
0x14002e5ba  mov     [rdi+rsi], r14w
0x14002e5bf  cmp     ecx, edx
0x14002e5c1  jb      loc_14002EC7B
0x14002e5c7  lea     rax, [rdx+2]
0x14002e5cb  cmp     rax, rbx
0x14002e5ce  ja      loc_14002EC7B
0x14002e5d4  ror     r12w, 8
0x14002e5d9  mov     [rdx+rsi], r12w
0x14002e5de  lea     edx, [rcx+2]
0x14002e5e1  cmp     edx, ecx
0x14002e5e3  jb      loc_14002EC7B
0x14002e5e9  lea     rax, [rcx+2]
0x14002e5ed  cmp     rax, rbx
0x14002e5f0  ja      loc_14002EC7B
0x14002e5f6  ror     r13w, 8
0x14002e5fb  mov     [rcx+rsi], r13w
0x14002e600  lea     ecx, [rdx+2]
0x14002e603  cmp     ecx, edx
0x14002e605  jb      loc_14002EC7B
0x14002e60b  lea     rax, [rdx+2]
0x14002e60f  cmp     rax, rbx
0x14002e612  ja      loc_14002EC7B
0x14002e618  movzx   eax, [rsp+98h+arg_10]
0x14002e620  ror     ax, 8
0x14002e624  mov     [rdx+rsi], ax
0x14002e628  lea     edx, [rcx+2]
0x14002e62b  cmp     edx, ecx
0x14002e62d  jb      loc_14002EC7B
0x14002e633  lea     rax, [rcx+2]
0x14002e637  cmp     rax, rbx
0x14002e63a  ja      loc_14002EC7B
0x14002e640  movzx   eax, [rsp+98h+var_78]
0x14002e645  ror     ax, 8
0x14002e649  mov     [rcx+rsi], ax
0x14002e64d  lea     ecx, [rdx+4]
0x14002e650  cmp     ecx, edx
0x14002e652  jb      loc_14002EC7B
0x14002e658  lea     rax, [rdx+4]
0x14002e65c  cmp     rax, rbx
0x14002e65f  ja      loc_14002EC7B
0x14002e665  mov     eax, dword ptr [rsp+98h+var_70]
0x14002e669  lea     edi, [rcx+2]
0x14002e66c  bswap   eax
0x14002e66e  mov     [rdx+rsi], eax
0x14002e671  cmp     edi, ecx
0x14002e673  jb      loc_14002EC7B
0x14002e679  lea     rax, [rcx+2]
0x14002e67d  cmp     rax, rbx
0x14002e680  ja      loc_14002EC7B
0x14002e686  movzx   eax, bp
0x14002e689  ror     ax, 8
0x14002e68d  mov     [rcx+rsi], ax
0x14002e691  lea     ecx, [rdi+rbp]
0x14002e694  mov     eax, ebp
0x14002e696  cmp     ecx, edi
0x14002e698  jb      loc_14002EC7B
0x14002e69e  cmp     ecx, ebx
0x14002e6a0  ja      loc_14002EC7B
0x14002e6a6  mov     rdx, [rsp+98h+Src]; Src
0x14002e6ae  xor     r15d, r15d
0x14002e6b1  test    rdx, rdx
0x14002e6b4  jz      short loc_14002E6D4
0x14002e6b6  mov     ebx, [rsp+98h+arg_28]
0x14002e6bd  cmp     ebx, eax
0x14002e6bf  mov     ecx, edi
0x14002e6c1  cmova   ebx, eax
0x14002e6c4  add     rcx, rsi; void *
0x14002e6c7  mov     r8d, ebx; Size
0x14002e6ca  call    memmove
0x14002e6cf  add     edi, ebx
0x14002e6d1  sub     bp, bx
0x14002e6d4  cmp     r15w, bp
0x14002e6d8  jnb     loc_14002EC66
0x14002e6de  mov     ecx, edi
0x14002e6e0  xor     edx, edx; Val
0x14002e6e2  add     rcx, rsi; void *
0x14002e6e5  movzx   r8d, bp; Size
0x14002e6e9  call    memset
0x14002e6ee  movzx   eax, bp
0x14002e6f1  jmp     loc_14002EC64
0x14002e6f6  test    rsi, rsi
0x14002e6f9  jz      loc_14002EC8D
0x14002e6ff  test    r11, r11
0x14002e702  jz      loc_14002EC8D
0x14002e708  mov     eax, 400h
0x14002e70d  cmp     r10d, eax
0x14002e710  ja      loc_14002EC8D
0x14002e716  mov     r13d, [rsp+98h+arg_28]
0x14002e71e  cmp     r13d, eax
0x14002e721  ja      loc_14002EC8D
0x14002e727  mov     rbp, r10
0x14002e72a  cmp     r10, 2
0x14002e72e  jb      loc_14002EC8D
0x14002e734  mov     ebx, [rdx]
0x14002e736  cmp     rbx, 2
0x14002e73a  jb      loc_14002EC75
0x14002e740  movzx   eax, word ptr [r8]
0x14002e744  mov     r9d, 1
0x14002e74a  movzx   r12d, ax
0x14002e74e  mov     [rcx], ax
0x14002e751  ror     r12w, 8
0x14002e756  cmp     r9w, r12w
0x14002e75a  jz      short loc_14002E770
0x14002e75c  lea     eax, [r9+22h]
0x14002e760  cmp     ax, r12w
0x14002e764  jz      short loc_14002E770
0x14002e766  mov     eax, 0C0000002h
0x14002e76b  jmp     loc_14002EC92
0x14002e770  cmp     r9w, r12w
0x14002e774  mov     eax, 45Ch
0x14002e779  mov     r15d, 25Ah
0x14002e77f  cmovnz  r15d, eax
0x14002e783  cmp     rbp, 4
0x14002e787  jb      loc_14002EC8D
0x14002e78d  cmp     rbx, 4
0x14002e791  jb      loc_14002EC7B
0x14002e797  movzx   eax, word ptr [r8+2]
0x14002e79c  mov     [rcx+2], ax
0x14002e7a0  cmp     rbp, 8
0x14002e7a4  jb      loc_14002EC8D
0x14002e7aa  cmp     rbx, 8
0x14002e7ae  jb      loc_14002EC7B
0x14002e7b4  mov     eax, [r8+4]
0x14002e7b8  mov     [rcx+4], eax
0x14002e7bb  mov     ecx, 30032h
0x14002e7c0  bswap   eax
0x14002e7c2  and     eax, ecx
0x14002e7c4  cmp     eax, ecx
0x14002e7c6  jnz     loc_14002EC8D
0x14002e7cc  mov     r8d, 0Ah
0x14002e7d2  cmp     rbp, r8
0x14002e7d5  jb      loc_14002EC8D
0x14002e7db  cmp     rbx, r8
0x14002e7de  jb      loc_14002EC7B
0x14002e7e4  movzx   ecx, word ptr [r14+8]
0x14002e7e9  movzx   eax, cx
0x14002e7ec  mov     [rsi+8], cx
0x14002e7f0  ror     ax, 8
0x14002e7f4  movzx   edx, ax
0x14002e7f7  cmp     r9w, r12w
0x14002e7fb  jnz     short loc_14002E804
0x14002e7fd  add     r15d, 0FFFFFFC0h
0x14002e801  add     r15d, edx
0x14002e804  test    dx, dx
0x14002e807  jz      short loc_14002E84F
0x14002e809  mov     eax, 80h
0x14002e80e  cmp     ax, dx
0x14002e811  jb      loc_14002EC8D
0x14002e817  lea     edi, [rdx+0Ah]
0x14002e81a  cmp     edi, r8d
0x14002e81d  jb      loc_14002EC8D
0x14002e823  cmp     edi, r10d
0x14002e826  ja      loc_14002EC8D
0x14002e82c  cmp     edi, ebx
0x14002e82e  ja      loc_14002EC7B
0x14002e834  mov     r8, rdx; Size
0x14002e837  lea     rcx, [rsi+0Ah]; void *
0x14002e83b  lea     rdx, [r14+0Ah]; Src
0x14002e83f  call    memmove
0x14002e844  mov     r10d, [rsp+98h+arg_18]
0x14002e84c  mov     r8d, edi
0x14002e84f  lea     ecx, [r8+2]
0x14002e853  cmp     ecx, r8d
0x14002e856  jb      loc_14002EC8D
0x14002e85c  mov     r9d, r8d
0x14002e85f  lea     rax, [r9+2]
0x14002e863  cmp     rax, rbp
0x14002e866  ja      loc_14002EC8D
0x14002e86c  cmp     rax, rbx
0x14002e86f  ja      loc_14002EC7B
0x14002e875  movzx   eax, word ptr [r9+r14]
0x14002e87a  movzx   edx, ax
0x14002e87d  mov     [r9+rsi], ax
0x14002e882  ror     dx, 8
0x14002e886  cmp     dx, 6
0x14002e88a  jz      short loc_14002E896
0x14002e88c  cmp     dx, 13h
0x14002e890  jnz     loc_14002E766
0x14002e896  lea     edx, [rcx+2]
0x14002e899  cmp     edx, ecx
0x14002e89b  jb      loc_14002EC8D
0x14002e8a1  lea     rax, [rcx+2]
0x14002e8a5  cmp     rax, rbp
0x14002e8a8  ja      loc_14002EC8D
0x14002e8ae  cmp     rax, rbx
0x14002e8b1  ja      loc_14002EC7B
0x14002e8b7  movzx   eax, word ptr [rcx+r14]
0x14002e8bc  mov     [rcx+rsi], ax
0x14002e8c0  lea     ecx, [rdx+2]
0x14002e8c3  cmp     ecx, edx
0x14002e8c5  jb      loc_14002EC8D
0x14002e8cb  lea     rax, [rdx+2]
0x14002e8cf  cmp     rax, rbp
0x14002e8d2  ja      loc_14002EC8D
0x14002e8d8  cmp     rax, rbx
0x14002e8db  ja      loc_14002EC7B
0x14002e8e1  movzx   eax, word ptr [rdx+r14]
0x14002e8e6  mov     [rdx+rsi], ax
0x14002e8ea  lea     edx, [rcx+2]
0x14002e8ed  cmp     edx, ecx
0x14002e8ef  jb      loc_14002EC8D
0x14002e8f5  lea     rax, [rcx+2]
0x14002e8f9  cmp     rax, rbp
0x14002e8fc  ja      loc_14002EC8D
0x14002e902  cmp     rax, rbx
0x14002e905  ja      loc_14002EC7B
0x14002e90b  movzx   eax, word ptr [rcx+r14]
0x14002e910  mov     r11d, 10h
0x14002e916  mov     [rcx+rsi], ax
0x14002e91a  ror     ax, 8
0x14002e91e  cmp     r11w, ax
0x14002e922  jnz     loc_14002EC8D
0x14002e928  lea     ecx, [rdx+2]
0x14002e92b  cmp     ecx, edx
0x14002e92d  jb      loc_14002EC8D
0x14002e933  lea     rax, [rdx+2]
0x14002e937  cmp     rax, rbp
0x14002e93a  ja      loc_14002EC8D
0x14002e940  cmp     rax, rbx
0x14002e943  ja      loc_14002EC7B
0x14002e949  movzx   eax, word ptr [rdx+r14]
0x14002e94e  movzx   r9d, ax
0x14002e952  mov     [rdx+rsi], ax
  ... truncated ...
```
