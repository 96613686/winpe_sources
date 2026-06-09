# ReadAllocEmbeddedHeader

- ea: `0x18001862c`
- end: `0x180018fad`
- name: `ReadAllocEmbeddedHeader`
- size: `2433`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800190a4`
- `0x18002173c`

## callees

- `0x180017ee0`
- `0x18001862c`
- `0x180018fb4`
- `0x180019014`
- `0x180019dc0`
- `0x180019df0`
- `0x18001ac80`
- `0x18001bff0`
- `0x18001d570`
- `0x18001d5c8`
- `0x180023380`
- `0x18002a54e`
- `0x18002b010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800189c4`
- `KERNEL32!HeapAlloc` at `0x1800189c4`
- `KERNEL32!GetProcessHeap` at `0x1800189b6`
- `KERNEL32!GetProcessHeap` at `0x1800189b6`

## pseudocode

```c
__int64 ReadAllocEmbeddedHeader(
        unsigned int (__fastcall *a1)(__int64, _DWORD *, __int64),
        __int64 a2,
        unsigned int *a3,
        ...)
{
  int v6; // ecx
  __int64 v7; // rax
  _DWORD *v8; // rdi
  int FontData; // eax
  LPVOID *v10; // r12
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  void *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned int v19; // r12d
  HANDLE ProcessHeap; // rax
  _DWORD *v21; // rax
  unsigned __int16 v22; // ax
  __int16 v23; // ax
  int v24; // ecx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r14
  int v28; // edx
  unsigned int v29; // r14d
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r14
  int v33; // edx
  unsigned int v34; // r14d
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // r14
  int v38; // edx
  unsigned int v39; // r14d
  __int64 v40; // rax
  unsigned int v41; // r8d
  __int64 v42; // rcx
  __int64 v43; // r14
  int v44; // edx
  unsigned int v45; // r14d
  __int64 v46; // rax
  __int64 v47; // r9
  unsigned int v48; // ecx
  __int64 v49; // r14
  int v50; // eax
  int v51; // r11d
  __int64 v52; // rcx
  __int16 v53; // ax
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r14
  SIZE_T v58; // rcx
  unsigned int v59; // r14d
  void *v60; // rax
  void *v61; // rsi
  _DWORD v63[4]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v64; // [rsp+80h] [rbp+40h] BYREF
  __int64 v65; // [rsp+98h] [rbp+58h] BYREF
  va_list va; // [rsp+98h] [rbp+58h]
  va_list va1; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v65 = va_arg(va1, _QWORD);
  v63[0] = 0;
  LOWORD(v65) = 0;
  v64 = 0;
  if ( a1 )
  {
    if ( a1(a2, v63, 4) == 4 )
    {
      *a3 = v63[0];
      if ( a1(a2, v63, 4) == 4 )
      {
        a3[1] = v63[0];
        if ( a1(a2, v63, 4) == 4 )
        {
          v6 = v63[0];
          a3[2] = v63[0];
          if ( (unsigned int)(v6 - 0x20000) > 0xFFFF )
          {
            if ( v6 == 0x10000 )
            {
              if ( (unsigned int)T2OSSvcReadFontData(a1, a2, (__int64 *)va, 2) == 2 )
              {
                a3[3] = (unsigned __int16)v65;
                if ( (unsigned int)T2OSSvcReadFontData(a1, a2, a3 + 4, 10) == 10
                  && (unsigned int)T2OSSvcReadFontData(a1, a2, (char *)a3 + 26, 1) == 1
                  && (unsigned int)T2OSSvcReadFontData(a1, a2, &v64, 2) == 2 )
                {
                  LOWORD(v65) = v64;
                  a3[7] = (unsigned __int16)PurifyWeightClass(v64);
                  if ( (unsigned int)T2OSSvcReadFontData(a1, a2, (char *)a3 + 27, 1) == 1
                    && (unsigned int)T2OSSvcReadFontData(a1, a2, (__int64 *)va, 2) == 2 )
                  {
                    *((_WORD *)a3 + 16) = PurifiedLicensing((unsigned __int16)v65);
                    *((_WORD *)a3 + 17) = 20556;
                    *(_QWORD *)(a3 + 9) = 0;
                    *(_QWORD *)(a3 + 11) = 0;
                    *(_QWORD *)(a3 + 13) = 0;
                    *(_QWORD *)(a3 + 15) = 0;
                    *(_QWORD *)(a3 + 17) = 0;
                    a3[19] = 0;
                    *((_WORD *)a3 + 40) = 0;
                    if ( (unsigned int)T2OSSvcReadFontData(a1, a2, &v64, 2) == 2 )
                    {
                      LOWORD(v65) = v64;
                      v7 = T2malloc((unsigned int)v64 + 1);
                      v8 = (_DWORD *)v7;
                      if ( v7 )
                      {
                        FontData = T2OSSvcReadFontData(a1, a2, v7, (unsigned __int16)v65);
                        if ( FontData != (unsigned __int16)v65 )
                        {
LABEL_33:
                          v13 = 263;
LABEL_100:
                          v15 = v8;
                          goto LABEL_101;
                        }
                        v10 = (LPVOID *)(a3 + 22);
                        if ( (unsigned int)AllocConvertToUnicode(a3 + 22, (char *)a3 + 82, v8) )
                        {
                          T2free(v8);
                          if ( (unsigned int)T2OSSvcReadFontData(a1, a2, &v64, 2) != 2 )
                          {
LABEL_21:
                            v13 = 263;
LABEL_24:
                            v15 = *v10;
LABEL_101:
                            T2free(v15);
                            return v13;
                          }
                          LOWORD(v65) = v64;
                          v11 = T2malloc((unsigned int)v64 + 1);
                          v8 = (_DWORD *)v11;
                          if ( !v11 )
                          {
LABEL_23:
                            v13 = 266;
                            goto LABEL_24;
                          }
                          v12 = T2OSSvcReadFontData(a1, a2, v11, (unsigned __int16)v65);
                          if ( v12 != (unsigned __int16)v65 )
                            goto LABEL_26;
                          T2free(v8);
                          if ( (unsigned int)T2OSSvcReadFontData(a1, a2, &v64, 2) != 2 )
                            goto LABEL_21;
                          LOWORD(v65) = v64;
                          v14 = T2malloc((unsigned int)v64 + 1);
                          v8 = (_DWORD *)v14;
                          if ( !v14 )
                            goto LABEL_23;
                          v16 = T2OSSvcReadFontData(a1, a2, v14, (unsigned __int16)v65);
                          if ( v16 != (unsigned __int16)v65 )
                          {
LABEL_26:
                            T2free(*v10);
                            goto LABEL_33;
                          }
                          T2free(v8);
                          a3[24] = 0;
                          *((_QWORD *)a3 + 13) = 0;
                          a3[28] = 0;
                          *((_QWORD *)a3 + 15) = 0;
                          a3[32] = 0;
                          *((_QWORD *)a3 + 17) = 0;
                          a3[36] = 0;
                          *((_QWORD *)a3 + 19) = 0;
                          *((_QWORD *)a3 + 20) = 0;
                          a3[42] = 0;
                          *((_QWORD *)a3 + 22) = 0;
                          *((_QWORD *)a3 + 23) = 0;
                          *((_QWORD *)a3 + 24) = 0;
                          return 0;
                        }
LABEL_103:
                        v13 = 266;
                        goto LABEL_100;
                      }
                      return 266;
                    }
                  }
                }
              }
              return 263;
            }
            return 258;
          }
          v17 = *a3;
          if ( (unsigned int)v17 < 0xC )
            return 258;
          v18 = a3[1];
          if ( v17 - 12 <= v18 )
            return 258;
          v19 = v17 - v18 - 12;
          if ( v19 > 0x7FFFFFFF )
            return 266;
          ProcessHeap = GetProcessHeap();
          v21 = HeapAlloc(ProcessHeap, 0, v19);
          v8 = v21;
          if ( !v21 )
            return 266;
          if ( (unsigned int)T2OSSvcReadFontData(a1, a2, v21, v19) != v19 )
            goto LABEL_33;
          if ( v19 < 4uLL )
            goto LABEL_99;
          v63[0] = *v8;
          a3[3] = v63[0];
          if ( v19 < 0xE )
            goto LABEL_99;
          *((_QWORD *)a3 + 2) = *(_QWORD *)(v8 + 1);
          *((_WORD *)a3 + 12) = *((_WORD *)v8 + 6);
          if ( v19 < 0xFuLL )
            goto LABEL_99;
          *((_BYTE *)a3 + 26) = *((_BYTE *)v8 + 14);
          if ( v19 < 0x10uLL )
            goto LABEL_99;
          *((_BYTE *)a3 + 27) = *((_BYTE *)v8 + 15);
          if ( v19 < 0x14uLL )
            goto LABEL_99;
          v63[0] = v8[4];
          v22 = v63[0];
          a3[7] = v63[0];
          a3[7] = (unsigned __int16)PurifyWeightClass(v22);
          if ( v19 < 0x16uLL )
            goto LABEL_99;
          LOWORD(v65) = *((_WORD *)v8 + 10);
          *((_WORD *)a3 + 16) = ((__int64 (*)(void))PurifiedLicensing)();
          if ( v19 < 0x18uLL )
            goto LABEL_99;
          v23 = *((_WORD *)v8 + 11);
          LOWORD(v65) = v23;
          *((_WORD *)a3 + 17) = v23;
          if ( v23 != 20556 )
            goto LABEL_99;
          if ( v19 < 0x1CuLL )
            goto LABEL_99;
          v63[0] = v8[6];
          a3[9] = v63[0];
          if ( v19 < 0x20uLL )
            goto LABEL_99;
          v63[0] = v8[7];
          a3[10] = v63[0];
          if ( v19 < 0x24uLL )
            goto LABEL_99;
          v63[0] = v8[8];
          a3[11] = v63[0];
          if ( v19 < 0x28uLL )
            goto LABEL_99;
          v63[0] = v8[9];
          a3[12] = v63[0];
          if ( v19 < 0x2CuLL )
            goto LABEL_99;
          v63[0] = v8[10];
          a3[13] = v63[0];
          if ( v19 < 0x30uLL )
            goto LABEL_99;
          v63[0] = v8[11];
          a3[14] = v63[0];
          if ( v19 < 0x34uLL )
            goto LABEL_99;
          v63[0] = v8[12];
          a3[15] = v63[0];
          if ( v19 < 0x38uLL )
            goto LABEL_99;
          v63[0] = v8[13];
          a3[16] = v63[0];
          if ( v19 < 0x3CuLL )
            goto LABEL_99;
          v63[0] = v8[14];
          a3[17] = v63[0];
          if ( v19 < 0x40uLL )
            goto LABEL_99;
          v63[0] = v8[15];
          a3[18] = v63[0];
          if ( v19 < 0x44uLL
            || (v63[0] = v8[16], a3[19] = v63[0], v19 < 0x46uLL)
            || (LOWORD(v65) = *((_WORD *)v8 + 34), *((_WORD *)a3 + 40) = v65, v19 < 0x48uLL)
            || (v24 = *((unsigned __int16 *)v8 + 35), LOWORD(v65) = v24, *((_WORD *)a3 + 41) = v24, v24 + 72 > v19) )
          {
LABEL_99:
            v13 = 258;
            goto LABEL_100;
          }
          if ( (unsigned __int16)v24 > 0x3Eu )
            *((_WORD *)a3 + 41) = 62;
          v25 = T2AllocCopyWStrn(v8 + 18);
          *((_QWORD *)a3 + 11) = v25;
          if ( !v25 )
            goto LABEL_102;
          v26 = (unsigned int)(unsigned __int16)v65 + 72;
          if ( v26 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v27 = (unsigned int)(unsigned __int16)v65 + 74;
          LOWORD(v65) = *(_WORD *)((char *)v8 + v26);
          *((_WORD *)a3 + 48) = v65;
          if ( v27 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v28 = *(unsigned __int16 *)((char *)v8 + v27);
          v29 = v26 + 4;
          LOWORD(v65) = v28;
          *((_WORD *)a3 + 49) = v28;
          if ( (int)v26 + 4 + v28 > v19 )
            goto LABEL_98;
          v30 = T2AllocCopyWStrn((char *)v8 + v29);
          *((_QWORD *)a3 + 13) = v30;
          if ( !v30 )
            goto LABEL_102;
          v31 = v29 + *((unsigned __int16 *)a3 + 49);
          if ( v31 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v32 = (unsigned int)(v31 + 2);
          LOWORD(v65) = *(_WORD *)((char *)v8 + v31);
          *((_WORD *)a3 + 56) = v65;
          if ( v32 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v33 = *(unsigned __int16 *)((char *)v8 + v32);
          v34 = v31 + 4;
          LOWORD(v65) = v33;
          *((_WORD *)a3 + 57) = v33;
          if ( (int)v31 + 4 + v33 > v19 )
            goto LABEL_98;
          v35 = T2AllocCopyWStrn((char *)v8 + v34);
          *((_QWORD *)a3 + 15) = v35;
          if ( !v35 )
            goto LABEL_102;
          v36 = v34 + *((unsigned __int16 *)a3 + 57);
          if ( v36 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v37 = (unsigned int)(v36 + 2);
          LOWORD(v65) = *(_WORD *)((char *)v8 + v36);
          *((_WORD *)a3 + 64) = v65;
          if ( v37 + 2 > (unsigned __int64)v19 )
            goto LABEL_98;
          v38 = *(unsigned __int16 *)((char *)v8 + v37);
          v39 = v36 + 4;
          LOWORD(v65) = v38;
          *((_WORD *)a3 + 65) = v38;
          if ( (int)v36 + 4 + v38 > v19 )
            goto LABEL_98;
          v40 = T2AllocCopyWStrn((char *)v8 + v39);
          *((_QWORD *)a3 + 17) = v40;
          if ( !v40 )
            goto LABEL_102;
          v41 = a3[2];
          if ( v41 < 0x20001 )
          {
            a3[36] = 0;
            *((_QWORD *)a3 + 19) = 0;
          }
          else
          {
            v42 = v39 + *((unsigned __int16 *)a3 + 65);
            if ( v42 + 2 > (unsigned __int64)v19 )
              goto LABEL_98;
            v43 = (unsigned int)(v42 + 2);
            LOWORD(v65) = *(_WORD *)((char *)v8 + v42);
            *((_WORD *)a3 + 72) = v65;
            if ( v43 + 2 > (unsigned __int64)v19 )
              goto LABEL_98;
            v44 = *(unsigned __int16 *)((char *)v8 + v43);
            v45 = v42 + 4;
            LOWORD(v65) = v44;
            *((_WORD *)a3 + 73) = v44;
            if ( (_WORD)v44 )
            {
              if ( v45 + v44 > v19 )
                goto LABEL_98;
              v46 = T2AllocCopyWStrn((char *)v8 + v45);
              *((_QWORD *)a3 + 19) = v46;
              v47 = v46;
              if ( !v46 )
                goto LABEL_102;
              v41 = a3[2];
              v48 = v45 + *((unsigned __int16 *)a3 + 73);
            }
            else
            {
              v48 = v42 + 4;
              *((_QWORD *)a3 + 19) = 0;
              v47 = 0;
            }
            if ( v41 >= 0x20002 )
            {
              if ( (unsigned __int64)v48 + 4 <= v19 )
              {
                v49 = v48 + 4;
                v63[0] = *(_DWORD *)((char *)v8 + v48);
                a3[40] = v63[0] ^ 0x50475342;
                v50 = GetByteCheckSum(v47);
                if ( v51 == v50 && v49 + 4 <= (unsigned __int64)v19 )
                {
                  v52 = (unsigned int)(v49 + 4);
                  v63[0] = *(_DWORD *)((char *)v8 + v49);
                  a3[41] = v63[0];
                  if ( v52 + 2 <= (unsigned __int64)v19 )
                  {
                    v53 = *(_WORD *)((char *)v8 + v52);
                    v54 = (unsigned int)(v49 + 6);
                    LOWORD(v65) = v53;
                    *((_WORD *)a3 + 84) = v53;
                    if ( v54 + 2 <= (unsigned __int64)v19 )
                    {
                      v55 = *(unsigned __int16 *)((char *)v8 + v54);
                      LOWORD(v65) = v55;
                      *((_WORD *)a3 + 85) = v55;
                      *((_QWORD *)a3 + 22) = 0;
                      v56 = (unsigned int)(v54 + v55 + 2);
                      if ( v56 + 4 <= (unsigned __int64)v19 )
                      {
                        v57 = (unsigned int)(v56 + 4);
                        v63[0] = *(_DWORD *)((char *)v8 + v56);
                        a3[46] = v63[0];
                        if ( v57 + 4 <= (unsigned __int64)v19 )
                        {
                          v58 = *(unsigned int *)((char *)v8 + v57);
                          v63[0] = v58;
                          a3[47] = v58;
                          if ( (_DWORD)v58 )
                          {
                            v59 = v56 + 8;
                            if ( v59 + (unsigned int)v58 >= v59 && v59 + (unsigned int)v58 <= v19 )
                            {
                              v60 = (void *)T2malloc(v58);
                              v61 = v60;
                              if ( v60 )
                              {
                                memcpy_0(v60, (char *)v8 + v59, a3[47]);
                                if ( (a3[46] & 0x10000000) != 0 )
                                  XORBufferData(v61, a3[47]);
                                goto LABEL_96;
                              }
LABEL_102:
                              DeallocEmbedHeaderData(a3);
                              goto LABEL_103;
                            }
                            goto LABEL_98;
                          }
LABEL_95:
                          v61 = 0;
LABEL_96:
                          *((_QWORD *)a3 + 24) = v61;
                          T2free(v8);
                          return 0;
                        }
                      }
                    }
                  }
                }
              }
LABEL_98:
              DeallocEmbedHeaderData(a3);
              goto LABEL_99;
            }
          }
          *((_QWORD *)a3 + 20) = 0;
          a3[42] = 0;
          *((_QWORD *)a3 + 22) = 0;
          *((_QWORD *)a3 + 23) = 0;
          goto LABEL_95;
        }
      }
    }
  }
  return 263;
}

```

## disassembly

```asm
0x18001862c  mov     [rsp-38h+arg_8], rbx
0x180018631  mov     [rsp-38h+arg_18], r9
0x180018636  push    rbp
0x180018637  push    rsi
0x180018638  push    rdi
0x180018639  push    r12
0x18001863b  push    r13
0x18001863d  push    r14
0x18001863f  push    r15
0x180018641  mov     rbp, rsp
0x180018644  sub     rsp, 40h
0x180018648  xor     r13d, r13d
0x18001864b  mov     rbx, r8
0x18001864e  mov     [rbp+var_10], r13d
0x180018652  mov     r15, rdx
0x180018655  mov     word ptr [rbp+arg_18], r13w
0x18001865a  mov     r14, rcx
0x18001865d  mov     [rbp+arg_0], r13w
0x180018662  test    rcx, rcx
0x180018665  jz      loc_180018F90
0x18001866b  lea     edi, [r13+4]
0x18001866f  mov     rcx, r15
0x180018672  mov     r8d, edi
0x180018675  lea     rdx, [rbp+var_10]
0x180018679  mov     rax, r14
0x18001867c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018681  cmp     eax, edi
0x180018683  jnz     loc_180018F90
0x180018689  mov     eax, [rbp+var_10]
0x18001868c  lea     rdx, [rbp+var_10]
0x180018690  mov     [rbx], eax
0x180018692  mov     r8d, edi
0x180018695  mov     rax, r14
0x180018698  mov     rcx, r15
0x18001869b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a0  cmp     eax, edi
0x1800186a2  jnz     loc_180018F90
0x1800186a8  mov     eax, [rbp+var_10]
0x1800186ab  lea     rdx, [rbp+var_10]
0x1800186af  mov     [rbx+4], eax
0x1800186b2  mov     r8d, edi
0x1800186b5  mov     rax, r14
0x1800186b8  mov     rcx, r15
0x1800186bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c0  cmp     eax, edi
0x1800186c2  jnz     loc_180018F90
0x1800186c8  mov     ecx, [rbp+var_10]
0x1800186cb  mov     edx, 0FFFFh
0x1800186d0  mov     [rbx+8], ecx
0x1800186d3  lea     eax, [rcx-20000h]
0x1800186d9  cmp     eax, edx
0x1800186db  jbe     loc_180018977
0x1800186e1  cmp     ecx, 10000h
0x1800186e7  jnz     loc_180018F89
0x1800186ed  lea     edi, [r13+2]
0x1800186f1  mov     rdx, r15
0x1800186f4  mov     r9d, edi
0x1800186f7  lea     r8, [rbp+arg_18]
0x1800186fb  mov     rcx, r14
0x1800186fe  call    T2OSSvcReadFontData
0x180018703  cmp     eax, edi
0x180018705  jnz     loc_180018F90
0x18001870b  movzx   eax, word ptr [rbp+arg_18]
0x18001870f  lea     r8, [rbx+10h]
0x180018713  lea     r9d, [r13+0Ah]
0x180018717  mov     [rbx+0Ch], eax
0x18001871a  mov     rdx, r15
0x18001871d  mov     rcx, r14
0x180018720  call    T2OSSvcReadFontData
0x180018725  cmp     eax, 0Ah
0x180018728  jnz     loc_180018F90
0x18001872e  lea     esi, [rdi-1]
0x180018731  mov     rdx, r15
0x180018734  mov     r9d, esi
0x180018737  lea     r8, [rbx+1Ah]
0x18001873b  mov     rcx, r14
0x18001873e  call    T2OSSvcReadFontData
0x180018743  cmp     eax, esi
0x180018745  jnz     loc_180018F90
0x18001874b  mov     r9d, edi
0x18001874e  lea     r8, [rbp+arg_0]
0x180018752  mov     rdx, r15
0x180018755  mov     rcx, r14
0x180018758  call    T2OSSvcReadFontData
0x18001875d  cmp     eax, edi
0x18001875f  jnz     loc_180018F90
0x180018765  movzx   ecx, [rbp+arg_0]
0x180018769  mov     word ptr [rbp+arg_18], cx
0x18001876d  call    PurifyWeightClass
0x180018772  movzx   edx, ax
0x180018775  lea     r8, [rbx+1Bh]
0x180018779  mov     [rbx+1Ch], edx
0x18001877c  mov     r9d, esi
0x18001877f  mov     rdx, r15
0x180018782  mov     rcx, r14
0x180018785  call    T2OSSvcReadFontData
0x18001878a  cmp     eax, esi
0x18001878c  jnz     loc_180018F90
0x180018792  mov     r9d, edi
0x180018795  lea     r8, [rbp+arg_18]
0x180018799  mov     rdx, r15
0x18001879c  mov     rcx, r14
0x18001879f  call    T2OSSvcReadFontData
0x1800187a4  cmp     eax, edi
0x1800187a6  jnz     loc_180018F90
0x1800187ac  movzx   ecx, word ptr [rbp+arg_18]
0x1800187b0  call    PurifiedLicensing
0x1800187b5  mov     rcx, r14
0x1800187b8  mov     [rbx+20h], ax
0x1800187bc  mov     r9d, edi
0x1800187bf  mov     word ptr [rbx+22h], 504Ch
0x1800187c5  lea     r8, [rbp+arg_0]
0x1800187c9  mov     [rbx+24h], r13
0x1800187cd  mov     rdx, r15
0x1800187d0  mov     [rbx+2Ch], r13
0x1800187d4  mov     [rbx+34h], r13
0x1800187d8  mov     [rbx+3Ch], r13
0x1800187dc  mov     [rbx+44h], r13
0x1800187e0  mov     [rbx+4Ch], r13d
0x1800187e4  mov     [rbx+50h], r13w
0x1800187e9  call    T2OSSvcReadFontData
0x1800187ee  cmp     eax, edi
0x1800187f0  jnz     loc_180018F90
0x1800187f6  movzx   eax, [rbp+arg_0]
0x1800187fa  mov     edx, esi
0x1800187fc  mov     word ptr [rbp+arg_18], ax
0x180018800  lea     ecx, [rsi+rax]; dwBytes
0x180018803  call    T2malloc
0x180018808  mov     rdi, rax
0x18001880b  test    rax, rax
0x18001880e  jz      loc_180018F82
0x180018814  movzx   r9d, word ptr [rbp+arg_18]
0x180018819  mov     r8, rax
0x18001881c  mov     rdx, r15
0x18001881f  mov     rcx, r14
0x180018822  call    T2OSSvcReadFontData
0x180018827  movzx   ecx, word ptr [rbp+arg_18]
0x18001882b  cmp     eax, ecx
0x18001882d  jnz     loc_1800189EC
0x180018833  lea     r12, [rbx+58h]
0x180018837  mov     r8, rdi
0x18001883a  mov     rcx, r12
0x18001883d  lea     rdx, [rbx+52h]
0x180018841  call    AllocConvertToUnicode
0x180018846  test    eax, eax
0x180018848  jz      loc_180018F7B
0x18001884e  mov     rcx, rdi; lpMem
0x180018851  call    T2free
0x180018856  lea     r9d, [r13+2]
0x18001885a  mov     rdx, r15
0x18001885d  lea     r8, [rbp+arg_0]
0x180018861  mov     rcx, r14
0x180018864  call    T2OSSvcReadFontData
0x180018869  cmp     eax, 2
0x18001886c  jnz     short loc_1800188C3
0x18001886e  movzx   eax, [rbp+arg_0]
0x180018872  mov     edx, esi
0x180018874  mov     word ptr [rbp+arg_18], ax
0x180018878  lea     ecx, [rsi+rax]; dwBytes
0x18001887b  call    T2malloc
0x180018880  mov     rdi, rax
0x180018883  test    rax, rax
0x180018886  jz      short loc_1800188E4
0x180018888  movzx   r9d, word ptr [rbp+arg_18]
0x18001888d  mov     r8, rax
0x180018890  mov     rdx, r15
0x180018893  mov     rcx, r14
0x180018896  call    T2OSSvcReadFontData
0x18001889b  movzx   edx, word ptr [rbp+arg_18]
0x18001889f  cmp     eax, edx
0x1800188a1  jnz     short loc_18001890D
0x1800188a3  mov     rcx, rdi; lpMem
0x1800188a6  call    T2free
0x1800188ab  lea     r9d, [r13+2]
0x1800188af  mov     rdx, r15
0x1800188b2  lea     r8, [rbp+arg_0]
0x1800188b6  mov     rcx, r14
0x1800188b9  call    T2OSSvcReadFontData
0x1800188be  cmp     eax, 2
0x1800188c1  jz      short loc_1800188CA
0x1800188c3  mov     ebx, 107h
0x1800188c8  jmp     short loc_1800188E9
0x1800188ca  movzx   eax, [rbp+arg_0]
0x1800188ce  mov     edx, esi
0x1800188d0  mov     word ptr [rbp+arg_18], ax
0x1800188d4  lea     ecx, [rsi+rax]; dwBytes
0x1800188d7  call    T2malloc
0x1800188dc  mov     rdi, rax
0x1800188df  test    rax, rax
0x1800188e2  jnz     short loc_1800188F2
0x1800188e4  mov     ebx, 10Ah
0x1800188e9  mov     rcx, [r12]
0x1800188ed  jmp     loc_180018F6A
0x1800188f2  movzx   r9d, word ptr [rbp+arg_18]
0x1800188f7  mov     r8, rdi
0x1800188fa  mov     rdx, r15
0x1800188fd  mov     rcx, r14
0x180018900  call    T2OSSvcReadFontData
0x180018905  movzx   ecx, word ptr [rbp+arg_18]
0x180018909  cmp     eax, ecx
0x18001890b  jz      short loc_18001891B
0x18001890d  mov     rcx, [r12]; lpMem
0x180018911  call    T2free
0x180018916  jmp     loc_1800189EC
0x18001891b  mov     rcx, rdi; lpMem
0x18001891e  call    T2free
0x180018923  mov     [rbx+60h], r13d
0x180018927  mov     [rbx+68h], r13
0x18001892b  mov     [rbx+70h], r13d
0x18001892f  mov     [rbx+78h], r13
0x180018933  mov     [rbx+80h], r13d
0x18001893a  mov     [rbx+88h], r13
0x180018941  mov     [rbx+90h], r13d
0x180018948  mov     [rbx+98h], r13
0x18001894f  mov     [rbx+0A0h], r13
0x180018956  mov     [rbx+0A8h], r13d
0x18001895d  mov     [rbx+0B0h], r13
0x180018964  mov     [rbx+0B8h], r13
0x18001896b  mov     [rbx+0C0h], r13
0x180018972  jmp     loc_180018F56
0x180018977  lea     eax, [rcx-20000h]
0x18001897d  cmp     eax, edx
0x18001897f  ja      loc_180018F89
0x180018985  mov     ecx, [rbx]
0x180018987  cmp     ecx, 0Ch
0x18001898a  jb      loc_180018F89
0x180018990  mov     edx, [rbx+4]
0x180018993  lea     rax, [rcx-0Ch]
0x180018997  cmp     rax, rdx
0x18001899a  jbe     loc_180018F89
0x1800189a0  sub     ecx, edx
0x1800189a2  lea     r12d, [rcx-0Ch]
0x1800189a6  cmp     r12d, 7FFFFFFFh
0x1800189ad  ja      loc_180018F82
0x1800189b3  mov     esi, r12d
0x1800189b6  call    cs:__imp_GetProcessHeap
0x1800189bc  mov     r8d, r12d; dwBytes
0x1800189bf  xor     edx, edx; dwFlags
0x1800189c1  mov     rcx, rax; hHeap
0x1800189c4  call    cs:__imp_HeapAlloc
0x1800189ca  mov     rdi, rax
0x1800189cd  test    rax, rax
0x1800189d0  jz      loc_180018F82
0x1800189d6  mov     r9d, r12d
0x1800189d9  mov     r8, rax
0x1800189dc  mov     rdx, r15
0x1800189df  mov     rcx, r14
0x1800189e2  call    T2OSSvcReadFontData
0x1800189e7  cmp     eax, r12d
0x1800189ea  jz      short loc_1800189F6
0x1800189ec  mov     ebx, 107h
0x1800189f1  jmp     loc_180018F67
0x1800189f6  cmp     rsi, 4
0x1800189fa  jb      loc_180018F62
0x180018a00  mov     eax, [rdi]
0x180018a02  mov     [rbp+var_10], eax
0x180018a05  mov     [rbx+0Ch], eax
0x180018a08  cmp     r12d, 0Eh
0x180018a0c  jb      loc_180018F62
0x180018a12  movsd   xmm0, qword ptr [rdi+4]
0x180018a17  movsd   qword ptr [rbx+10h], xmm0
0x180018a1c  movzx   eax, word ptr [rdi+0Ch]
0x180018a20  mov     [rbx+18h], ax
0x180018a24  cmp     rsi, 0Fh
0x180018a28  jb      loc_180018F62
0x180018a2e  mov     al, [rdi+0Eh]
0x180018a31  mov     [rbx+1Ah], al
0x180018a34  cmp     rsi, 10h
0x180018a38  jb      loc_180018F62
0x180018a3e  mov     al, [rdi+0Fh]
0x180018a41  mov     [rbx+1Bh], al
0x180018a44  cmp     rsi, 14h
0x180018a48  jb      loc_180018F62
0x180018a4e  mov     eax, [rdi+10h]
0x180018a51  movzx   ecx, ax
0x180018a54  mov     [rbp+var_10], eax
0x180018a57  mov     [rbx+1Ch], eax
0x180018a5a  call    PurifyWeightClass
0x180018a5f  movzx   edx, ax
0x180018a62  mov     [rbx+1Ch], edx
0x180018a65  cmp     rsi, 16h
0x180018a69  jb      loc_180018F62
0x180018a6f  movzx   ecx, word ptr [rdi+14h]
0x180018a73  mov     word ptr [rbp+arg_18], cx
0x180018a77  call    PurifiedLicensing
0x180018a7c  mov     [rbx+20h], ax
0x180018a80  cmp     rsi, 18h
0x180018a84  jb      loc_180018F62
0x180018a8a  movzx   eax, word ptr [rdi+16h]
0x180018a8e  mov     ecx, 504Ch
0x180018a93  mov     word ptr [rbp+arg_18], ax
0x180018a97  mov     [rbx+22h], ax
0x180018a9b  cmp     ax, cx
0x180018a9e  jnz     loc_180018F62
0x180018aa4  cmp     rsi, 1Ch
0x180018aa8  jb      loc_180018F62
0x180018aae  mov     eax, [rdi+18h]
0x180018ab1  mov     [rbp+var_10], eax
0x180018ab4  mov     [rbx+24h], eax
0x180018ab7  cmp     rsi, 20h ; ' '
  ... truncated ...
```
