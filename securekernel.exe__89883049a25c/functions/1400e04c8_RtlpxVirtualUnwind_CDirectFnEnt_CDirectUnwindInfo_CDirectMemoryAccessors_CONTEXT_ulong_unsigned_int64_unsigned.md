# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x1400e04c8`
- end: `0x1400e0ff9`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAX27@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2865`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14001c4bc`
- `0x1400d7a84`
- `0x1400e1b78`

## callees

- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de4dc`
- `0x1400de54c`
- `0x1400de648`
- `0x1400df038`
- `0x1400e0284`
- `0x1400e0470`
- `0x1400e04c8`
- `0x1400fc62c`

## pseudocode

```c
__int64 RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
        int a1,
        __int64 a2,
        _BYTE *a3,
        ...)
{
  __int64 v4; // r13
  __int64 v6; // r13
  _QWORD *v7; // rdi
  _QWORD *v8; // rbx
  __int64 result; // rax
  __int64 v10; // rbx
  unsigned int v11; // r12d
  unsigned int v12; // edi
  __int64 i; // r13
  __int16 v14; // ax
  __int64 v15; // rax
  int v16; // edi
  _BYTE *j; // rcx
  char v18; // dl
  int v19; // r9d
  char v20; // r8
  bool v21; // zf
  int v22; // ecx
  __int64 v23; // r12
  __int64 v24; // r8
  char *v25; // rdi
  char v26; // r12
  char v27; // al
  int v28; // eax
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // rcx
  _QWORD *v31; // rax
  char v32; // al
  __int64 Context; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  _QWORD **v36; // rbx
  unsigned int v37; // r12d
  _QWORD *v38; // rbx
  __int64 v39; // rcx
  char v40; // cl
  int v41; // edx
  _QWORD *v42; // r9
  unsigned int v43; // r12d
  __int64 v44; // rdx
  _QWORD *v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  unsigned int v48; // r9d
  __int16 v49; // ax
  unsigned int v50; // edi
  int v51; // r8d
  int v52; // edx
  int v53; // r12d
  unsigned int v54; // r11d
  unsigned int v55; // r9d
  __int16 v56; // ax
  _BYTE *v57; // rcx
  __int64 v58; // r9
  unsigned int v59; // [rsp+44h] [rbp-B4h]
  int v60; // [rsp+44h] [rbp-B4h]
  int v61; // [rsp+48h] [rbp-B0h]
  _QWORD *v62; // [rsp+58h] [rbp-A0h]
  _QWORD *v63; // [rsp+68h] [rbp-90h]
  _QWORD *v64; // [rsp+70h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-78h] BYREF
  __int64 v66; // [rsp+88h] [rbp-70h]
  __int64 v67; // [rsp+90h] [rbp-68h]
  __int64 v68; // [rsp+98h] [rbp-60h]
  __int64 v69; // [rsp+A0h] [rbp-58h]
  __int64 v70; // [rsp+A8h] [rbp-50h]
  __int64 v71; // [rsp+B0h] [rbp-48h]
  unsigned int *v74; // [rsp+118h] [rbp+20h] BYREF
  va_list va; // [rsp+118h] [rbp+20h]
  __int64 v76; // [rsp+120h] [rbp+28h]
  _BYTE *v77; // [rsp+128h] [rbp+30h]
  _QWORD *v78; // [rsp+130h] [rbp+38h]
  __int64 *v79; // [rsp+138h] [rbp+40h]
  _QWORD *v80; // [rsp+140h] [rbp+48h]
  __int64 v81; // [rsp+148h] [rbp+50h]
  __int64 v82; // [rsp+150h] [rbp+58h]
  _QWORD *v83; // [rsp+158h] [rbp+60h]
  va_list va1; // [rsp+160h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v74 = va_arg(va1, unsigned int *);
  v76 = va_arg(va1, _QWORD);
  v77 = va_arg(va1, _BYTE *);
  v78 = va_arg(va1, _QWORD *);
  v79 = va_arg(va1, __int64 *);
  v80 = va_arg(va1, _QWORD *);
  v81 = va_arg(va1, _QWORD);
  v82 = va_arg(va1, _QWORD);
  v83 = va_arg(va1, _QWORD *);
  v4 = a2;
  if ( v74 )
  {
    v10 = a2 + v74[2];
    v11 = *(_BYTE *)v10 & 7;
    if ( v11 >= 3 )
      return 3221225659LL;
    if ( v77 && !*v77 )
      goto LABEL_19;
    LODWORD(v82) = 0;
    if ( v11 < 2 )
    {
      if ( (unsigned int)RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(v74, a2, v10) )
      {
LABEL_19:
        LODWORD(v82) = 1;
        goto LABEL_22;
      }
      if ( a1 < 0 )
        return 3221225512LL;
    }
LABEL_22:
    v67 = 0;
    LODWORD(v83) = 0;
    v61 = 0;
    if ( (*(_BYTE *)(v10 + 3) & 0xF) != 0 )
    {
      v12 = (_DWORD)a3 - v4 - *v74;
      if ( v12 >= *(unsigned __int8 *)(v10 + 1) || (*(_BYTE *)v10 & 0x20) != 0 )
        goto LABEL_29;
      for ( i = 0; (unsigned int)i < *(unsigned __int8 *)(v10 + 2); i = (unsigned int)RtlpUnwindOpSlots()
                                                                      + (unsigned int)i )
      {
        if ( (HIBYTE(*(_WORD *)(v10 + 2 * i + 4)) & 0xF) == 3 )
          break;
      }
      v14 = *(_WORD *)(v10 + 2 * i + 4);
      v4 = a2;
      if ( v12 >= (unsigned __int8)v14 )
LABEL_29:
        v61 = 1;
    }
    if ( v61 )
    {
      v16 = *(unsigned __int8 *)(v10 + 3);
      v15 = RtlpAmd64GetContextGp<_CONTEXT *>(v76, *(_BYTE *)(v10 + 3) & 0xF) - (v16 & 0xFFFFFFF0);
    }
    else
    {
      v15 = *(_QWORD *)(v76 + 152);
    }
    *v79 = v15;
    if ( !(_DWORD)v82 )
    {
      if ( v11 < 2 )
      {
        j = a3;
        v18 = *a3;
        v59 = 0;
        if ( *a3 != 72 )
          goto LABEL_44;
        if ( a3[1] == 0x83 && a3[2] == 0xC4 )
        {
LABEL_38:
          for ( j = a3 + 4; ; j += 2 )
          {
LABEL_48:
            while ( 1 )
            {
              v18 = *j;
LABEL_49:
              if ( (v18 & 0xF8) != 0x58 )
                break;
              ++j;
            }
            if ( (v18 & 0xF0) != 0x40 || (j[1] & 0xF8) != 0x58 )
              break;
          }
          if ( v18 == -14 )
            v18 = *++j;
          if ( (unsigned __int8)(v18 + 62) <= 1u || v18 == -13 && j[1] == 0xC3 )
            goto LABEL_67;
          if ( ((v18 + 23) & 0xFD) != 0 )
          {
            if ( v18 == -1 && j[1] == 37 )
            {
              LODWORD(v83) = 1;
              goto LABEL_71;
            }
            if ( (v18 & 0xF8) == 0x48 && j[1] == 0xFF )
            {
              v21 = (j[2] & 0x38) == 32;
              goto LABEL_66;
            }
          }
          else
          {
            if ( v18 == -21 )
              v28 = (char)j[1] + 2;
            else
              v28 = *(_DWORD *)(j + 1) + 5;
            v29 = (unsigned __int64)&j[v28 - v4];
            v30 = *v74;
            if ( v29 < v30 || v29 >= v74[1] )
            {
              v23 = a2;
              if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                RtlReadUCharFromUser(v29 + a2);
              v31 = (_QWORD *)RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(&v65, v74, a2, v29 + a2);
              if ( !*v31 || v29 == *(_DWORD *)*v31 )
              {
                v22 = 1;
                LODWORD(v83) = 1;
LABEL_70:
                if ( v22 )
                {
LABEL_71:
                  v24 = v76;
                  v66 = v76;
                  v63 = (_QWORD *)v81;
                  v65 = v81;
                  v25 = a3;
                  v26 = *a3;
                  LOBYTE(v82) = v26;
                  if ( (v26 & 0xF8) == 0x48 )
                  {
                    v27 = a3[1];
                    switch ( v27 )
                    {
                      case -125:
                        *(_QWORD *)(v76 + 152) += (char)a3[3];
LABEL_74:
                        v25 = a3 + 4;
LABEL_95:
                        v26 = *v25;
                        LOBYTE(v82) = *v25;
                        break;
                      case -127:
                        *(_QWORD *)(v76 + 152) += *(int *)(a3 + 3);
LABEL_94:
                        v25 = a3 + 7;
                        goto LABEL_95;
                      case -115:
                        v32 = a3[2] & 0xF8;
                        if ( v32 == 96 )
                        {
                          Context = RtlpAmd64GetContextGp<_CONTEXT *>(v76, v59);
                          v24 = v76;
                          *(_QWORD *)(v76 + 152) = Context;
                          *(_QWORD *)(v24 + 152) = Context + (char)a3[3];
                          goto LABEL_74;
                        }
                        if ( v32 == -96 )
                        {
                          v34 = *(int *)(a3 + 3);
                          v35 = RtlpAmd64GetContextGp<_CONTEXT *>(v76, v59);
                          v24 = v76;
                          *(_QWORD *)(v76 + 152) = v35 + v34;
                          goto LABEL_94;
                        }
                        break;
                    }
                  }
                  v36 = (_QWORD **)(v66 + 152);
                  while ( 1 )
                  {
                    if ( (v26 & 0xF8) == 0x58 )
                    {
                      v37 = v26 & 7;
                      LODWORD(v82) = v37;
                      v62 = (_QWORD *)(v24 + 152);
                      v38 = *(_QWORD **)(v24 + 152);
                      if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                      {
                        v69 = 1;
                        ProbeForRead(v38, 1u, 4u);
                      }
                      if ( *v63
                        && ((unsigned __int64)v38 < *(_QWORD *)*v63
                         || (unsigned __int64)v38 > **(_QWORD **)(v81 + 8) - 8LL) )
                      {
                        return 3221225512LL;
                      }
                      RtlpAmd64SetContextGp<_CONTEXT *>(v76, v37, *v38);
                      v39 = *(_QWORD *)(v81 + 16);
                      if ( v39 )
                        *(_QWORD *)(v39 + 8LL * v37 + 128) = v38;
                      *v62 += 8LL;
                      ++v25;
                      v36 = (_QWORD **)(v66 + 152);
                    }
                    else
                    {
                      if ( (v26 & 0xF0) != 0x40 || (v40 = v25[1], (v40 & 0xF8) != 0x58) )
                      {
                        if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                        {
                          v71 = 8;
                          v45 = *v36;
                          v71 = 1;
                          ProbeForRead(v45, 1u, 4u);
                        }
                        if ( !*v63
                          || (unsigned __int64)*v36 >= *(_QWORD *)*v63
                          && (unsigned __int64)*v36 <= **(_QWORD **)(v81 + 8) - 8LL )
                        {
                          v46 = *v36;
                          v47 = v76;
                          *(_QWORD *)(v76 + 248) = **v36;
                          *v36 = v46 + 1;
                          if ( v77 )
                            *v77 = 0;
LABEL_149:
                          if ( v80 )
                            *v80 = v67;
                          if ( (_DWORD)v83 && v61 )
                            *v79 = *(_QWORD *)(v47 + 152) - 8LL;
                          return 0;
                        }
                        return 3221225512LL;
                      }
                      v41 = v40 & 7;
                      v60 = v41;
                      v42 = *v36;
                      v64 = *v36;
                      if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
                      {
                        v70 = 1;
                        ProbeForRead(v42, 1u, 4u);
                        v42 = v64;
                        v41 = v60;
                      }
                      if ( *v63
                        && ((unsigned __int64)v42 < *(_QWORD *)*v63
                         || (unsigned __int64)v42 > **(_QWORD **)(v81 + 8) - 8LL) )
                      {
                        return 3221225512LL;
                      }
                      v43 = v41 | (8 * (v26 & 1));
                      RtlpAmd64SetContextGp<_CONTEXT *>(v76, v43, *v42);
                      v44 = *(_QWORD *)(v81 + 16);
                      if ( v44 )
                        *(_QWORD *)(v44 + 8LL * v43 + 128) = v64;
                      ++*v36;
                      v25 += 2;
                    }
                    v26 = *v25;
                    LOBYTE(v82) = *v25;
                    v24 = v76;
                  }
                }
                goto LABEL_143;
              }
LABEL_69:
              v22 = (int)v83;
              goto LABEL_70;
            }
            if ( v29 == v30 )
            {
              v21 = (*(_BYTE *)v10 & 0x20) == 0;
LABEL_66:
              if ( v21 )
              {
LABEL_67:
                v22 = 1;
                LODWORD(v83) = 1;
                v23 = a2;
                goto LABEL_70;
              }
            }
          }
          v23 = a2;
          goto LABEL_69;
        }
        if ( a3[1] != 0x81 || a3[2] != 0xC4 )
        {
LABEL_44:
          if ( (v18 & 0xFE) != 0x48 )
            goto LABEL_49;
          if ( a3[1] != 0x8D )
            goto LABEL_49;
          v19 = a3[2] & 7 | (8 * (v18 & 1));
          v59 = v19;
          if ( !v19 || v19 != (*(_BYTE *)(v10 + 3) & 0xF) )
            goto LABEL_49;
          v20 = a3[2] & 0xF8;
          if ( v20 == 96 )
            goto LABEL_38;
          if ( v20 != -96 )
            goto LABEL_49;
        }
        j = a3 + 7;
        goto LABEL_48;
      }
      v48 = *(unsigned __int8 *)(v10 + 2);
      if ( (_BYTE)v48 )
      {
        v49 = *(_WORD *)(v10 + 4);
        if ( (HIBYTE(v49) & 0xF) == 6 )
        {
          v50 = (unsigned __int8)v49;
          v51 = (_DWORD)a3 - v4;
          if ( (v49 & 0x1000) != 0 )
          {
            v52 = v74[1] - (unsigned __int8)v49;
            v53 = v51 - v52 < (unsigned int)(unsigned __int8)v49;
            LODWORD(v83) = v53;
          }
          else
          {
            v52 = 0;
            v53 = (int)v83;
          }
          if ( v53 )
            goto LABEL_140;
          v54 = v48;
          if ( v48 > 1 )
          {
            v55 = 1;
            while ( 1 )
            {
              v56 = *(_WORD *)(v10 + 2LL * v55 + 4);
              if ( (HIBYTE(v56) & 0xF) != 6 )
                goto LABEL_138;
              v52 = (unsigned __int8)v56 + (HIBYTE(v56) >> 4 << 8);
              if ( !v52 )
                goto LABEL_138;
              v52 = v74[1] - v52;
              if ( v51 - v52 < v50 )
                break;
              if ( ++v55 >= v54 )
                goto LABEL_138;
            }
            v53 = 1;
            LODWORD(v83) = 1;
LABEL_138:
            LODWORD(v4) = a2;
          }
          if ( v53 )
          {
LABEL_140:
            RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
              v4,
              (_DWORD)a3,
              v51 - v52,
              (_DWORD)v74,
              v76,
              v81);
            if ( v77 )
              *v77 = 0;
            goto LABEL_148;
          }
        }
      }
    }
    v23 = a2;
LABEL_143:
    result = RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
               v23,
               (_DWORD)a3,
               *v79,
               (_DWORD)v74,
               v76,
               (__int64)v77,
               (__int64)va,
               v81);
    if ( (int)result < 0 )
      return result;
    if ( (a1 & 0x7FFFFFFF) != 0 )
    {
      v57 = (_BYTE *)(v23 + v74[2]);
      if ( (_DWORD)a3 - (_DWORD)v23 - *v74 >= (unsigned __int8)v57[1] && ((*v57 >> 3) & (unsigned __int8)a1) != 0 )
      {
        v58 = (unsigned __int8)v57[2] + (v57[2] & 1u);
        *v78 = &v57[2 * (unsigned int)(v58 + 2) + 4];
        v67 = v23 + *(unsigned int *)&v57[2 * v58 + 4];
      }
    }
LABEL_148:
    v47 = v76;
    goto LABEL_149;
  }
  v6 = v76;
  v7 = (_QWORD *)(v76 + 152);
  v8 = *(_QWORD **)(v76 + 152);
  v83 = v8;
  if ( (unsigned __int64)a3 < 0x7FFFFFFF0000LL )
  {
    v68 = 1;
    ProbeForRead(v8, 1u, 4u);
  }
  if ( *(_QWORD *)v81
    && ((unsigned __int64)v8 < **(_QWORD **)v81 || (unsigned __int64)v8 > **(_QWORD **)(v81 + 8) - 8LL) )
  {
    return 3221225512LL;
  }
  if ( a3 != (_BYTE *)*v8 )
  {
    *(_QWORD *)(v6 + 248) = *v8;
    *v7 += 8LL;
    *v79 = (__int64)v8;
    if ( v77 )
      *v77 = 0;
    *v78 = 0;
    if ( v80 )
      *v80 = 0;
    return 0;
  }
  return 3221225727LL;
}

```

## disassembly

```asm
0x1400e04c8  mov     rax, rsp
0x1400e04cb  mov     [rax+20h], r9
0x1400e04cf  mov     [rax+18h], r8
0x1400e04d3  mov     [rax+10h], rdx
0x1400e04d7  mov     [rax+8], ecx
0x1400e04da  push    rbx
0x1400e04db  push    rdi
0x1400e04dc  push    r12
0x1400e04de  push    r13
0x1400e04e0  push    r14
0x1400e04e2  push    r15
0x1400e04e4  sub     rsp, 0C8h
0x1400e04eb  mov     r14, r8
0x1400e04ee  mov     r13, rdx
0x1400e04f1  mov     edi, ecx
0x1400e04f3  test    r9, r9
0x1400e04f6  jnz     loc_1400E0612
0x1400e04fc  mov     r13, [rsp+0F8h+arg_20]
0x1400e0504  lea     rdi, [r13+98h]
0x1400e050b  mov     [rsp+0F8h+var_A0], rdi
0x1400e0510  mov     rbx, [rdi]
0x1400e0513  mov     r12, rbx
0x1400e0516  mov     [rsp+0F8h+arg_58], rbx
0x1400e051e  mov     rax, 7FFFFFFF0000h
0x1400e0528  cmp     r8, rax
0x1400e052b  jnb     short loc_1400E0555
0x1400e052d  mov     [rsp+0F8h+var_60], 8
0x1400e0539  lea     r15d, [r9+1]
0x1400e053d  mov     [rsp+0F8h+var_60], r15
0x1400e0545  lea     r8d, [r9+4]; Alignment
0x1400e0549  mov     edx, r15d; Length
0x1400e054c  mov     rcx, rbx; Address
0x1400e054f  call    ProbeForRead
0x1400e0554  nop
0x1400e0555  mov     rcx, [rsp+0F8h+arg_48]
0x1400e055d  mov     rax, [rcx]
0x1400e0560  test    rax, rax
0x1400e0563  jz      short loc_1400E0582
0x1400e0565  cmp     rbx, [rax]
0x1400e0568  jb      loc_1400E0683
0x1400e056e  mov     rax, [rcx+8]
0x1400e0572  mov     rcx, [rax]
0x1400e0575  sub     rcx, 8
0x1400e0579  cmp     rbx, rcx
0x1400e057c  ja      loc_1400E0683
0x1400e0582  xor     eax, eax
0x1400e0584  jmp     short loc_1400E05A6
0x1400e0586  mov     r13, [rsp+0F8h+arg_20]
0x1400e058e  mov     r14, [rsp+0F8h+arg_10]
0x1400e0596  mov     r12, [rsp+0F8h+arg_58]
0x1400e059e  mov     rdi, [rsp+0F8h+var_A0]
0x1400e05a3  mov     rbx, r12
0x1400e05a6  test    eax, eax
0x1400e05a8  js      loc_1400E0FE6
0x1400e05ae  mov     rax, [rbx]
0x1400e05b1  cmp     r14, rax
0x1400e05b4  jnz     short loc_1400E05C0
0x1400e05b6  mov     eax, 0C00000FFh
0x1400e05bb  jmp     loc_1400E0FE6
0x1400e05c0  mov     [r13+0F8h], rax
0x1400e05c7  add     qword ptr [rdi], 8
0x1400e05cb  mov     rax, [rsp+0F8h+arg_38]
0x1400e05d3  mov     [rax], r12
0x1400e05d6  mov     rax, [rsp+0F8h+arg_28]
0x1400e05de  test    rax, rax
0x1400e05e1  jz      short loc_1400E05E6
0x1400e05e3  mov     byte ptr [rax], 0
0x1400e05e6  mov     rax, [rsp+0F8h+arg_30]
0x1400e05ee  mov     qword ptr [rax], 0
0x1400e05f5  mov     rax, [rsp+0F8h+arg_40]
0x1400e05fd  test    rax, rax
0x1400e0600  jz      loc_1400E0FE4
0x1400e0606  mov     qword ptr [rax], 0
0x1400e060d  jmp     loc_1400E0FE4
0x1400e0612  mov     rax, [rsp+0F8h+arg_18]
0x1400e061a  mov     ebx, [rax+8]
0x1400e061d  add     rbx, r13
0x1400e0620  movzx   r12d, byte ptr [rbx]
0x1400e0624  and     r12d, 7
0x1400e0628  cmp     r12d, 3
0x1400e062c  jb      short loc_1400E0638
0x1400e062e  mov     eax, 0C00000BBh
0x1400e0633  jmp     loc_1400E0FE6
0x1400e0638  mov     rax, [rsp+0F8h+arg_28]
0x1400e0640  test    rax, rax
0x1400e0643  jz      short loc_1400E064A
0x1400e0645  cmp     byte ptr [rax], 0
0x1400e0648  jz      short loc_1400E066F
0x1400e064a  mov     dword ptr [rsp+0F8h+arg_50], 0
0x1400e0655  cmp     r12d, 2
0x1400e0659  jnb     short loc_1400E068D
0x1400e065b  mov     r8, rbx
0x1400e065e  mov     rcx, [rsp+0F8h+arg_18]
0x1400e0666  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x1400e066b  test    eax, eax
0x1400e066d  jz      short loc_1400E067F
0x1400e066f  mov     r15d, 1
0x1400e0675  mov     dword ptr [rsp+0F8h+arg_50], r15d
0x1400e067d  jmp     short loc_1400E0693
0x1400e067f  test    edi, edi
0x1400e0681  jns     short loc_1400E068D
0x1400e0683  mov     eax, 0C0000028h
0x1400e0688  jmp     loc_1400E0FE6
0x1400e068d  mov     r15d, 1
0x1400e0693  mov     [rsp+0F8h+var_68], 0
0x1400e069f  xor     eax, eax
0x1400e06a1  mov     dword ptr [rsp+0F8h+arg_58], eax
0x1400e06a8  mov     [rsp+0F8h+var_B8], eax
0x1400e06ac  mov     [rsp+0F8h+var_B0], eax
0x1400e06b0  test    byte ptr [rbx+3], 0Fh
0x1400e06b4  jz      short loc_1400E071A
0x1400e06b6  mov     edi, r14d
0x1400e06b9  sub     edi, r13d
0x1400e06bc  mov     rax, [rsp+0F8h+arg_18]
0x1400e06c4  sub     edi, [rax]
0x1400e06c6  movzx   eax, byte ptr [rbx+1]
0x1400e06ca  cmp     edi, eax
0x1400e06cc  jnb     short loc_1400E0715
0x1400e06ce  test    byte ptr [rbx], 20h
0x1400e06d1  jnz     short loc_1400E0715
0x1400e06d3  xor     r13d, r13d
0x1400e06d6  cmp     [rbx+2], r13b
0x1400e06da  jbe     short loc_1400E0700
0x1400e06dc  movzx   ecx, word ptr [rbx+r13*2+4]
0x1400e06e2  movzx   eax, cx
0x1400e06e5  shr     ax, 8
0x1400e06e9  and     al, 0Fh
0x1400e06eb  cmp     al, 3
0x1400e06ed  jz      short loc_1400E0700
0x1400e06ef  call    RtlpUnwindOpSlots
0x1400e06f4  add     r13d, eax
0x1400e06f7  movzx   eax, byte ptr [rbx+2]
0x1400e06fb  cmp     r13d, eax
0x1400e06fe  jb      short loc_1400E06DC
0x1400e0700  movzx   eax, word ptr [rbx+r13*2+4]
0x1400e0706  movzx   ecx, al
0x1400e0709  mov     r13, [rsp+0F8h+arg_8]
0x1400e0711  cmp     edi, ecx
0x1400e0713  jb      short loc_1400E071A
0x1400e0715  mov     [rsp+0F8h+var_B0], r15d
0x1400e071a  mov     rcx, [rsp+0F8h+arg_20]
0x1400e0722  cmp     [rsp+0F8h+var_B0], 0
0x1400e0727  jnz     short loc_1400E0732
0x1400e0729  mov     rax, [rcx+98h]
0x1400e0730  jmp     short loc_1400E074B
0x1400e0732  movzx   edi, byte ptr [rbx+3]
0x1400e0736  mov     edx, edi
0x1400e0738  and     edx, 0Fh
0x1400e073b  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1400e0740  mov     ecx, 0FFFFFFF0h
0x1400e0745  and     rdi, rcx
0x1400e0748  sub     rax, rdi
0x1400e074b  mov     rcx, [rsp+0F8h+arg_38]
0x1400e0753  mov     [rcx], rax
0x1400e0756  cmp     dword ptr [rsp+0F8h+arg_50], 0
0x1400e075e  jnz     loc_1400E0ED1
0x1400e0764  cmp     r12d, 2
0x1400e0768  jnb     loc_1400E0DAC
0x1400e076e  mov     rcx, r14
0x1400e0771  movzx   edx, byte ptr [r14]
0x1400e0775  mov     [rsp+0F8h+var_B4], 0
0x1400e077d  cmp     dl, 48h ; 'H'
0x1400e0780  jnz     short loc_1400E07A9
0x1400e0782  cmp     byte ptr [r14+1], 83h
0x1400e0787  jnz     short loc_1400E0796
0x1400e0789  cmp     byte ptr [r14+2], 0C4h
0x1400e078e  jnz     short loc_1400E0796
0x1400e0790  lea     rcx, [r14+4]
0x1400e0794  jmp     short loc_1400E07F7
0x1400e0796  cmp     dl, 48h ; 'H'
0x1400e0799  jnz     short loc_1400E07A9
0x1400e079b  cmp     byte ptr [r14+1], 81h
0x1400e07a0  jnz     short loc_1400E07A9
0x1400e07a2  cmp     byte ptr [r14+2], 0C4h
0x1400e07a7  jz      short loc_1400E07F3
0x1400e07a9  mov     al, dl
0x1400e07ab  and     al, 0FEh
0x1400e07ad  cmp     al, 48h ; 'H'
0x1400e07af  jnz     short loc_1400E07F9
0x1400e07b1  cmp     byte ptr [r14+1], 8Dh
0x1400e07b6  jnz     short loc_1400E07F9
0x1400e07b8  movzx   r8d, byte ptr [r14+2]
0x1400e07bd  mov     r9d, edx
0x1400e07c0  and     r9d, r15d
0x1400e07c3  shl     r9d, 3
0x1400e07c7  mov     eax, r8d
0x1400e07ca  and     eax, 7
0x1400e07cd  or      r9d, eax
0x1400e07d0  mov     [rsp+0F8h+var_B4], r9d
0x1400e07d5  jz      short loc_1400E07F9
0x1400e07d7  movzx   eax, byte ptr [rbx+3]
0x1400e07db  and     eax, 0Fh
0x1400e07de  cmp     r9d, eax
0x1400e07e1  jnz     short loc_1400E07F9
0x1400e07e3  and     r8b, 0F8h
0x1400e07e7  cmp     r8b, 60h ; '`'
0x1400e07eb  jz      short loc_1400E0790
0x1400e07ed  cmp     r8b, 0A0h
0x1400e07f1  jnz     short loc_1400E07F9
0x1400e07f3  lea     rcx, [r14+7]
0x1400e07f7  mov     dl, [rcx]
0x1400e07f9  mov     al, dl
0x1400e07fb  and     al, 0F8h
0x1400e07fd  cmp     al, 58h ; 'X'
0x1400e07ff  jnz     short loc_1400E0806
0x1400e0801  add     rcx, r15
0x1400e0804  jmp     short loc_1400E07F7
0x1400e0806  mov     al, dl
0x1400e0808  and     al, 0F0h
0x1400e080a  cmp     al, 40h ; '@'
0x1400e080c  jnz     short loc_1400E081D
0x1400e080e  mov     al, [rcx+1]
0x1400e0811  and     al, 0F8h
0x1400e0813  cmp     al, 58h ; 'X'
0x1400e0815  jnz     short loc_1400E081D
0x1400e0817  add     rcx, 2
0x1400e081b  jmp     short loc_1400E07F7
0x1400e081d  cmp     dl, 0F2h
0x1400e0820  jnz     short loc_1400E0827
0x1400e0822  add     rcx, r15
0x1400e0825  mov     dl, [rcx]
0x1400e0827  lea     eax, [rdx+3Eh]
0x1400e082a  cmp     al, r15b
0x1400e082d  jbe     short loc_1400E0881
0x1400e082f  cmp     dl, 0F3h
0x1400e0832  jnz     short loc_1400E083A
0x1400e0834  cmp     byte ptr [rcx+1], 0C3h
0x1400e0838  jz      short loc_1400E0881
0x1400e083a  lea     eax, [rdx+17h]
0x1400e083d  test    al, 0FDh
0x1400e083f  jz      loc_1400E092A
0x1400e0845  cmp     dl, 0FFh
0x1400e0848  jnz     short loc_1400E086A
0x1400e084a  cmp     byte ptr [rcx+1], 25h ; '%'
0x1400e084e  jnz     short loc_1400E086A
0x1400e0850  mov     ecx, r15d
0x1400e0853  mov     dword ptr [rsp+0F8h+arg_58], ecx
0x1400e085a  mov     [rsp+0F8h+var_B8], ecx
0x1400e085e  mov     r13, 7FFFFFFF0000h
0x1400e0868  jmp     short loc_1400E08C4
0x1400e086a  and     dl, 0F8h
0x1400e086d  cmp     dl, 48h ; 'H'
0x1400e0870  jnz     short loc_1400E08A3
0x1400e0872  cmp     byte ptr [rcx+1], 0FFh
0x1400e0876  jnz     short loc_1400E08A3
0x1400e0878  mov     al, [rcx+2]
0x1400e087b  and     al, 38h
0x1400e087d  cmp     al, 20h ; ' '
0x1400e087f  jnz     short loc_1400E08A3
0x1400e0881  mov     ecx, r15d
0x1400e0884  mov     dword ptr [rsp+0F8h+arg_58], ecx
0x1400e088b  mov     [rsp+0F8h+var_B8], ecx
0x1400e088f  mov     r13, 7FFFFFFF0000h
0x1400e0899  mov     r12, [rsp+0F8h+arg_8]
0x1400e08a1  jmp     short loc_1400E08BC
0x1400e08a3  mov     r13, 7FFFFFFF0000h
0x1400e08ad  mov     r12, [rsp+0F8h+arg_8]
0x1400e08b5  mov     ecx, dword ptr [rsp+0F8h+arg_58]
0x1400e08bc  test    ecx, ecx
0x1400e08be  jz      loc_1400E0ED9
0x1400e08c4  mov     r8, [rsp+0F8h+arg_20]
0x1400e08cc  mov     [rsp+0F8h+var_70], r8
0x1400e08d4  mov     rax, [rsp+0F8h+arg_48]
0x1400e08dc  mov     [rsp+0F8h+var_90], rax
0x1400e08e1  mov     [rsp+0F8h+var_78], rax
0x1400e08e9  mov     rdi, r14
0x1400e08ec  mov     [rsp+0F8h+var_A8], r14
0x1400e08f1  mov     r12b, [r14]
0x1400e08f4  mov     byte ptr [rsp+0F8h+arg_50], r12b
0x1400e08fc  mov     al, r12b
0x1400e08ff  and     al, 0F8h
0x1400e0901  cmp     al, 48h ; 'H'
0x1400e0903  jnz     loc_1400E0A60
0x1400e0909  mov     al, [r14+1]
0x1400e090d  cmp     al, 83h
0x1400e090f  jnz     loc_1400E09D8
0x1400e0915  movsx   rax, byte ptr [r14+3]
0x1400e091a  add     [r8+98h], rax
0x1400e0921  lea     rdi, [r14+4]
0x1400e0925  jmp     loc_1400E0A50
0x1400e092a  mov     r8, rcx
0x1400e092d  sub     r8, r13
0x1400e0930  cmp     dl, 0EBh
0x1400e0933  jnz     short loc_1400E093E
0x1400e0935  movsx   eax, byte ptr [rcx+1]
0x1400e0939  add     eax, 2
0x1400e093c  jmp     short loc_1400E0944
0x1400e093e  mov     eax, [rcx+1]
0x1400e0941  add     eax, 5
0x1400e0944  movsxd  rdi, eax
0x1400e0947  add     rdi, r8
0x1400e094a  mov     r9, [rsp+0F8h+arg_18]
0x1400e0952  mov     ecx, [r9]
0x1400e0955  cmp     rdi, rcx
0x1400e0958  jb      short loc_1400E0974
0x1400e095a  mov     eax, [r9+4]
0x1400e095e  cmp     rdi, rax
0x1400e0961  jnb     short loc_1400E0974
0x1400e0963  cmp     rdi, rcx
0x1400e0966  jnz     loc_1400E08A3
  ... truncated ...
```
