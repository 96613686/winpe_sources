# WriteNameRecords

- ea: `0x180010b90`
- end: `0x1800110c7`
- name: `WriteNameRecords`
- size: `1335`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180027dd8`
- `0x180028f78`

## callees

- `0x180010b90`
- `0x180011640`
- `0x180011fc8`
- `0x180012020`
- `0x180013230`
- `0x1800164a0`
- `0x18001e7c4`
- `0x18001e9a1`
- `0x18002a542`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall WriteNameRecords(
        _QWORD *a1,
        _WORD *a2,
        unsigned __int16 a3,
        int a4,
        unsigned __int16 a5,
        _DWORD *a6)
{
  __int64 v6; // rdi
  _WORD *v8; // r15
  __int64 v9; // r14
  unsigned int GenericSize; // esi
  char *v11; // r13
  unsigned __int16 v12; // dx
  unsigned int v13; // r12d
  unsigned __int16 v14; // si
  __int64 v15; // r8
  unsigned __int16 *v16; // rcx
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // cx
  unsigned __int16 v19; // dx
  _QWORD *v20; // r8
  unsigned __int16 *v21; // rsi
  __int64 v22; // rax
  const void *v23; // r14
  int v24; // edi
  char *v25; // rbx
  __int64 v26; // rax
  const void *v27; // rdx
  size_t v28; // rbp
  unsigned __int16 v29; // r15
  __int64 v30; // rdi
  __int64 v31; // r12
  __int64 v32; // rsi
  unsigned __int16 v33; // di
  unsigned __int16 i; // bx
  unsigned __int16 *v35; // rax
  unsigned __int16 v36; // r14
  __int64 v37; // rsi
  __int64 v38; // rdi
  __int64 v39; // rax
  const void *v40; // rbp
  unsigned int v41; // r15d
  unsigned int v42; // r12d
  unsigned __int16 v43; // bx
  int v44; // ebx
  bool v46; // zf
  char *v47; // r15
  __int64 v48; // rdx
  int v49; // eax
  __int16 v50; // cx
  int v51; // eax
  __int16 v52; // [rsp+30h] [rbp-68h]
  int v53; // [rsp+34h] [rbp-64h]
  __int16 v54; // [rsp+38h] [rbp-60h]
  unsigned __int16 v55; // [rsp+38h] [rbp-60h]
  unsigned int v56; // [rsp+3Ch] [rbp-5Ch]
  unsigned __int16 v57; // [rsp+40h] [rbp-58h]
  int v58; // [rsp+44h] [rbp-54h]
  __int16 v59; // [rsp+48h] [rbp-50h] BYREF
  int v60; // [rsp+4Ah] [rbp-4Eh]
  unsigned __int16 *v61; // [rsp+50h] [rbp-48h]

  v6 = a3;
  v60 = 0;
  v8 = a2;
  a5 = 0;
  v9 = (__int64)a1;
  *a6 = 0;
  if ( !a2 || !a3 )
    return 1000;
  qsort_0(a2, a3, 0x28u, AscendingNameRecordCompare);
  v59 = 0;
  GenericSize = (unsigned __int16)GetGenericSize(&NAME_HEADER_CONTROL);
  v11 = (char *)Mem_Alloc(8 * v6);
  if ( !v11 )
    return 1005;
  v12 = 0;
  v13 = GenericSize;
  v56 = GenericSize;
  v14 = 0;
  do
  {
    v15 = 20LL * v12;
    if ( !a4 || !*(_DWORD *)&v8[v15 + 16] )
    {
      v16 = (unsigned __int16 *)&v11[8 * v14];
      *v16 = v12;
      v16[1] = v8[v15 + 4];
      v16[3] = 0;
      ++v14;
      v16[2] = v12;
      v8[v15 + 5] = 0;
    }
    ++v12;
  }
  while ( v12 < (unsigned __int16)v6 );
  v57 = v14;
  v17 = 0;
  v53 = 0;
  v54 = v14 * GetGenericSize(&NAME_RECORD_CONTROL);
  v18 = GetGenericSize(&NAME_HEADER_CONTROL) + v54;
  v55 = v18;
  HIWORD(v60) = v18;
  if ( v14 )
  {
    qsort_0(v11, v14, 8u, DescendingStringLengthCompare);
    v52 = 1;
    v19 = 1;
    if ( v14 > 1u )
    {
      v20 = a2;
      do
      {
        v21 = (unsigned __int16 *)&v11[8 * v19];
        v61 = v21;
        v22 = *v21;
        v23 = (const void *)v20[5 * v22 + 3];
        if ( !v23 )
          v23 = (const void *)v20[5 * v22 + 2];
        v24 = v19;
        v25 = &v11[8 * v19];
        v26 = *((unsigned __int16 *)v25 - 4);
        v27 = (const void *)v20[5 * v26 + 3];
        if ( !v27 )
          v27 = (const void *)v20[5 * v26 + 2];
        v28 = v21[1];
        if ( (_WORD)v28 != *((_WORD *)v25 - 3) || (v51 = memcmp_0(v23, v27, v21[1]), v20 = a2, v51) )
        {
          v58 = v24 - 1;
          if ( v24 - 1 > 0 )
          {
            v29 = 0;
            while ( 1 )
            {
              v30 = 8LL * v29;
              v31 = *(unsigned __int16 *)&v11[v30 + 4];
              v32 = v20[5 * v31 + 3];
              if ( !v32 )
                v32 = v20[5 * v31 + 2];
              v33 = *(_WORD *)&v11[v30 + 2] - v28;
              for ( i = 0; i <= v33; ++i )
              {
                if ( !memcmp_0(v23, (const void *)(v32 + i), v28) )
                {
                  v35 = v61;
                  v61[2] = v31;
                  v35[3] = i;
                  goto LABEL_27;
                }
              }
              if ( ++v29 >= v58 )
                break;
              v20 = a2;
            }
LABEL_27:
            v20 = a2;
          }
        }
        else
        {
          v21[2] = *((_WORD *)v25 - 2);
          v21[3] = *((_WORD *)v25 - 1);
        }
        v14 = v57;
        v19 = v52 + 1;
        v52 = v19;
      }
      while ( v19 < v57 );
      v8 = a2;
      v17 = 0;
      v13 = v56;
    }
    qsort_0(v11, v14, 8u, AscendingRecordIndexCompare);
    v36 = 0;
    if ( v14 )
    {
      while ( 1 )
      {
        v37 = *(unsigned __int16 *)&v11[8 * v36];
        v38 = (__int64)&v8[20 * v37];
        if ( !*(_WORD *)(v38 + 12) )
        {
          v39 = *(unsigned __int16 *)&v11[8 * v36 + 4];
          if ( (_WORD)v37 == (_WORD)v39 )
          {
            v40 = *(const void **)(v38 + 24);
            *(_WORD *)(v38 + 10) = *(_WORD *)&v11[8 * v36 + 6] + v17;
            if ( !v40 )
              v40 = *(const void **)(v38 + 16);
            v41 = *(unsigned __int16 *)(v38 + 8);
            v42 = v17 + v55;
            v43 = CheckOutOffset(a1, v42);
            if ( v43 )
              goto LABEL_42;
            memcpy_0((void *)(*a1 + v42), v40, v41);
            HIWORD(v44) = HIWORD(v53);
            LOWORD(v44) = *(_WORD *)(v38 + 8) + v53;
            v8 = a2;
            v53 = v44;
          }
          else
          {
            v46 = v8[20 * v39 + 6] == 0;
            v47 = (char *)&v8[20 * v39];
            if ( v46 )
            {
              v48 = *((_QWORD *)v47 + 3);
              *((_WORD *)v47 + 5) = v17;
              *((_WORD *)v47 + 6) = 1;
              if ( !v48 )
                v48 = *((_QWORD *)v47 + 2);
              v43 = WriteBytes(a1, v48, v17 + (unsigned int)v55, *((unsigned __int16 *)v47 + 4));
              if ( v43 )
                goto LABEL_42;
              HIWORD(v49) = HIWORD(v53);
              LOWORD(v49) = *((_WORD *)v47 + 4) + v53;
              v53 = v49;
            }
            v50 = *((_WORD *)v47 + 5) + *(_WORD *)&v11[8 * v36 + 6];
            v8 = a2;
            a2[20 * v37 + 5] = v50;
          }
          v13 = v56;
          v8[20 * v37 + 6] = 1;
        }
        v43 = WriteGeneric((__int64)a1, v38, 0xCu, (unsigned __int8 *)&NAME_RECORD_CONTROL, v13, &a5);
        if ( v43 )
          goto LABEL_42;
        ++v36;
        v14 = v57;
        v13 += a5;
        v56 = v13;
        if ( v36 >= v57 )
          break;
        v17 = v53;
      }
    }
    v18 = v55;
    v9 = (__int64)a1;
  }
  LOWORD(v60) = v14;
  *a6 = (unsigned __int16)v53 + v18;
  v43 = WriteGeneric(v9, (__int64)&v59, 6u, (unsigned __int8 *)&NAME_HEADER_CONTROL, 0, &a5);
LABEL_42:
  free_0(v11);
  return v43;
}

```

## disassembly

```asm
0x180010b90  mov     r11, rsp
0x180010b93  mov     [r11+10h], rdx
0x180010b97  mov     [r11+8], rcx
0x180010b9b  push    rbp
0x180010b9c  push    rsi
0x180010b9d  push    rdi
0x180010b9e  push    r14
0x180010ba0  push    r15
0x180010ba2  sub     rsp, 70h
0x180010ba6  mov     rax, [rsp+98h+arg_28]
0x180010bae  xor     esi, esi
0x180010bb0  movzx   edi, r8w
0x180010bb4  mov     ebp, r9d
0x180010bb7  mov     [rsp+98h+var_4E], esi
0x180010bbb  mov     r15, rdx
0x180010bbe  mov     [r11+28h], si
0x180010bc3  mov     r14, rcx
0x180010bc6  mov     [rax], esi
0x180010bc8  test    rdx, rdx
0x180010bcb  jz      loc_1800110BD
0x180010bd1  test    di, di
0x180010bd4  jz      loc_1800110BD
0x180010bda  mov     [r11+18h], rbx
0x180010bde  lea     r9, AscendingNameRecordCompare; CompareFunction
0x180010be5  mov     r8d, 28h ; '('; SizeOfElements
0x180010beb  mov     [r11-38h], r13
0x180010bef  mov     edx, edi; NumOfElements
0x180010bf1  mov     rcx, r15; Base
0x180010bf4  call    qsort_0
0x180010bf9  lea     rcx, NAME_HEADER_CONTROL
0x180010c00  mov     [rsp+98h+var_50], si
0x180010c05  call    GetGenericSize
0x180010c0a  lea     rcx, ds:0[rdi*8]; Size
0x180010c12  movzx   esi, ax
0x180010c15  call    Mem_Alloc
0x180010c1a  mov     r13, rax
0x180010c1d  test    rax, rax
0x180010c20  jz      loc_180011071
0x180010c26  mov     [rsp+98h+var_30], r12
0x180010c2b  xor     edx, edx
0x180010c2d  mov     r12d, esi
0x180010c30  mov     [rsp+98h+var_5C], esi
0x180010c34  xor     esi, esi
0x180010c36  xor     eax, eax
0x180010c38  mov     [rsp+98h+var_58], esi
0x180010c3c  cmp     ax, di
0x180010c3f  jnb     short loc_180010C96
0x180010c41  movzx   eax, dx
0x180010c44  lea     rcx, [rax+rax*4]
0x180010c48  lea     r8, ds:0[rcx*8]
0x180010c50  test    ebp, ebp
0x180010c52  jz      short loc_180010C5C
0x180010c54  cmp     dword ptr [r8+r15+20h], 0
0x180010c5a  jnz     short loc_180010C8A
0x180010c5c  movzx   eax, si
0x180010c5f  lea     rcx, ds:0[rax*8]
0x180010c67  add     rcx, r13
0x180010c6a  mov     [rcx], dx
0x180010c6d  movzx   eax, word ptr [r8+r15+8]
0x180010c73  mov     [rcx+2], ax
0x180010c77  xor     eax, eax
0x180010c79  mov     [rcx+6], ax
0x180010c7d  inc     si
0x180010c80  mov     [rcx+4], dx
0x180010c84  mov     [r8+r15+0Ah], ax
0x180010c8a  inc     dx
0x180010c8d  cmp     dx, di
0x180010c90  jb      short loc_180010C41
0x180010c92  mov     [rsp+98h+var_58], esi
0x180010c96  xor     ebx, ebx
0x180010c98  lea     rcx, NAME_RECORD_CONTROL
0x180010c9f  mov     [rsp+98h+var_64], ebx
0x180010ca3  call    GetGenericSize
0x180010ca8  movzx   ecx, si
0x180010cab  movzx   eax, ax
0x180010cae  imul    eax, ecx
0x180010cb1  lea     rcx, NAME_HEADER_CONTROL
0x180010cb8  mov     [rsp+98h+var_60], eax
0x180010cbc  call    GetGenericSize
0x180010cc1  mov     ecx, [rsp+98h+var_60]
0x180010cc5  add     cx, ax
0x180010cc8  mov     [rsp+98h+var_60], ecx
0x180010ccc  mov     word ptr [rsp+98h+var_4E+2], cx
0x180010cd1  test    si, si
0x180010cd4  jz      loc_180010F5B
0x180010cda  movzx   edx, si; NumOfElements
0x180010cdd  lea     r9, DescendingStringLengthCompare; CompareFunction
0x180010ce4  mov     r8d, 8; SizeOfElements
0x180010cea  mov     rcx, r13; Base
0x180010ced  call    qsort_0
0x180010cf2  mov     eax, 1
0x180010cf7  mov     [rsp+98h+var_68], ax
0x180010cfc  movzx   edx, ax
0x180010cff  cmp     ax, si
0x180010d02  jnb     loc_180010E14
0x180010d08  mov     r8, [rsp+98h+arg_8]
0x180010d10  movzx   eax, dx
0x180010d13  lea     rsi, ds:0[rax*8]
0x180010d1b  add     rsi, r13
0x180010d1e  mov     [rsp+98h+var_48], rsi
0x180010d23  movzx   eax, word ptr [rsi]
0x180010d26  lea     rcx, [rax+rax*4]
0x180010d2a  mov     r14, [r8+rcx*8+18h]
0x180010d2f  test    r14, r14
0x180010d32  jnz     short loc_180010D39
0x180010d34  mov     r14, [r8+rcx*8+10h]
0x180010d39  movzx   edi, dx
0x180010d3c  lea     rbx, ds:0[rdi*8]
0x180010d44  add     rbx, r13
0x180010d47  movzx   eax, word ptr [rbx-8]
0x180010d4b  lea     rcx, [rax+rax*4]
0x180010d4f  mov     rdx, [r8+rcx*8+18h]
0x180010d54  test    rdx, rdx
0x180010d57  jnz     short loc_180010D5E
0x180010d59  mov     rdx, [r8+rcx*8+10h]; Buf2
0x180010d5e  movzx   ebp, word ptr [rsi+2]
0x180010d62  cmp     bp, [rbx-6]
0x180010d66  jz      loc_18001107B
0x180010d6c  dec     edi
0x180010d6e  mov     [rsp+98h+var_54], edi
0x180010d72  test    edi, edi
0x180010d74  jle     short loc_180010DE9
0x180010d76  xor     r15d, r15d
0x180010d79  nop     dword ptr [rax+00000000h]
0x180010d80  movzx   eax, r15w
0x180010d84  lea     rdi, ds:0[rax*8]
0x180010d8c  movzx   r12d, word ptr [rdi+r13+4]
0x180010d92  lea     rax, [r12+r12*4]
0x180010d96  mov     rsi, [r8+rax*8+18h]
0x180010d9b  test    rsi, rsi
0x180010d9e  jnz     short loc_180010DA5
0x180010da0  mov     rsi, [r8+rax*8+10h]
0x180010da5  movzx   edi, word ptr [rdi+r13+2]
0x180010dab  sub     di, bp
0x180010dae  xor     ebx, ebx
0x180010db0  cmp     bx, di
0x180010db3  ja      loc_180010FCF
0x180010db9  movzx   edx, bx
0x180010dbc  mov     r8, rbp; Size
0x180010dbf  add     rdx, rsi; Buf2
0x180010dc2  mov     rcx, r14; Buf1
0x180010dc5  call    memcmp_0
0x180010dca  test    eax, eax
0x180010dcc  jz      short loc_180010DD3
0x180010dce  inc     bx
0x180010dd1  jmp     short loc_180010DB0
0x180010dd3  mov     rax, [rsp+98h+var_48]
0x180010dd8  mov     [rax+4], r12w
0x180010ddd  mov     [rax+6], bx
0x180010de1  mov     r8, [rsp+98h+arg_8]
0x180010de9  movzx   edx, [rsp+98h+var_68]
0x180010dee  mov     esi, [rsp+98h+var_58]
0x180010df2  inc     dx
0x180010df5  mov     [rsp+98h+var_68], dx
0x180010dfa  cmp     dx, si
0x180010dfd  jb      loc_180010D10
0x180010e03  mov     r15, [rsp+98h+arg_8]
0x180010e0b  mov     ebx, [rsp+98h+var_64]
0x180010e0f  mov     r12d, [rsp+98h+var_5C]
0x180010e14  movzx   edx, si; NumOfElements
0x180010e17  lea     r9, AscendingRecordIndexCompare; CompareFunction
0x180010e1e  mov     r8d, 8; SizeOfElements
0x180010e24  mov     rcx, r13; Base
0x180010e27  call    qsort_0
0x180010e2c  xor     eax, eax
0x180010e2e  xor     r14d, r14d
0x180010e31  cmp     ax, si
0x180010e34  jnb     loc_180010F4F
0x180010e3a  nop     word ptr [rax+rax+00h]
0x180010e40  movzx   ebp, r14w
0x180010e44  movzx   esi, word ptr [r13+rbp*8+0]
0x180010e4a  lea     rax, [rsi+rsi*4]
0x180010e4e  cmp     word ptr [r15+rax*8+0Ch], 0
0x180010e55  lea     rdi, [r15+rax*8]
0x180010e59  jnz     loc_180010EF6
0x180010e5f  movzx   eax, word ptr [r13+rbp*8+4]
0x180010e65  cmp     si, ax
0x180010e68  jnz     loc_180010FEE
0x180010e6e  movzx   eax, bx
0x180010e71  add     ax, [r13+rbp*8+6]
0x180010e77  mov     rbp, [rdi+18h]
0x180010e7b  mov     [rdi+0Ah], ax
0x180010e7f  test    rbp, rbp
0x180010e82  jnz     short loc_180010E88
0x180010e84  mov     rbp, [rdi+10h]
0x180010e88  movzx   r15d, word ptr [rdi+8]
0x180010e8d  movzx   r12d, word ptr [rsp+98h+var_60]
0x180010e93  mov     r8d, r15d
0x180010e96  mov     rcx, [rsp+98h+arg_0]
0x180010e9e  movzx   eax, bx
0x180010ea1  add     r12d, eax
0x180010ea4  mov     edx, r12d
0x180010ea7  call    CheckOutOffset
0x180010eac  movzx   ebx, ax
0x180010eaf  test    ax, ax
0x180010eb2  jnz     loc_180010FA6
0x180010eb8  mov     rax, [rsp+98h+arg_0]
0x180010ec0  mov     r8d, r15d; Size
0x180010ec3  mov     ecx, r12d
0x180010ec6  mov     rdx, rbp; Src
0x180010ec9  add     rcx, [rax]; void *
0x180010ecc  call    memcpy_0
0x180010ed1  mov     ebx, [rsp+98h+var_64]
0x180010ed5  add     bx, [rdi+8]
0x180010ed9  mov     r15, [rsp+98h+arg_8]
0x180010ee1  mov     [rsp+98h+var_64], ebx
0x180010ee5  mov     r12d, [rsp+98h+var_5C]
0x180010eea  lea     rax, [rsi+rsi*4]
0x180010eee  mov     word ptr [r15+rax*8+0Ch], 1
0x180010ef6  mov     rcx, [rsp+98h+arg_0]
0x180010efe  lea     rax, [rsp+98h+arg_20]
0x180010f06  mov     [rsp+98h+var_70], rax
0x180010f0b  lea     r9, NAME_RECORD_CONTROL
0x180010f12  mov     r8d, 0Ch
0x180010f18  mov     [rsp+98h+var_78], r12d
0x180010f1d  mov     rdx, rdi
0x180010f20  call    WriteGeneric
0x180010f25  movzx   ebx, ax
0x180010f28  test    ax, ax
0x180010f2b  jnz     short loc_180010FA6
0x180010f2d  movzx   eax, [rsp+98h+arg_20]
0x180010f35  inc     r14w
0x180010f39  mov     esi, [rsp+98h+var_58]
0x180010f3d  add     r12d, eax
0x180010f40  mov     [rsp+98h+var_5C], r12d
0x180010f45  cmp     r14w, si
0x180010f49  jb      loc_1800110B4
0x180010f4f  mov     ecx, [rsp+98h+var_60]
0x180010f53  mov     r14, [rsp+98h+arg_0]
0x180010f5b  movzx   eax, word ptr [rsp+98h+var_64]
0x180010f60  lea     r9, NAME_HEADER_CONTROL
0x180010f67  movzx   ecx, cx
0x180010f6a  lea     rdx, [rsp+98h+var_50]
0x180010f6f  add     ecx, eax
0x180010f71  mov     word ptr [rsp+98h+var_4E], si
0x180010f76  mov     rax, [rsp+98h+arg_28]
0x180010f7e  mov     r8d, 6
0x180010f84  mov     [rax], ecx
0x180010f86  lea     rax, [rsp+98h+arg_20]
0x180010f8e  mov     [rsp+98h+var_70], rax
0x180010f93  mov     rcx, r14
0x180010f96  mov     [rsp+98h+var_78], 0
0x180010f9e  call    WriteGeneric
0x180010fa3  movzx   ebx, ax
0x180010fa6  mov     rcx, r13; Block
0x180010fa9  call    free_0
0x180010fae  mov     r12, [rsp+98h+var_30]
0x180010fb3  movzx   eax, bx
0x180010fb6  mov     rbx, [rsp+98h+arg_10]
0x180010fbe  mov     r13, [rsp+98h+var_38]
0x180010fc3  add     rsp, 70h
0x180010fc7  pop     r15
0x180010fc9  pop     r14
0x180010fcb  pop     rdi
0x180010fcc  pop     rsi
0x180010fcd  pop     rbp
0x180010fce  retn
0x180010fcf  inc     r15w
0x180010fd3  movzx   eax, r15w
0x180010fd7  cmp     eax, [rsp+98h+var_54]
0x180010fdb  jge     loc_180010DE1
0x180010fe1  mov     r8, [rsp+98h+arg_8]
0x180010fe9  jmp     loc_180010D80
0x180010fee  lea     rcx, [rax+rax*4]
0x180010ff2  cmp     word ptr [r15+rcx*8+0Ch], 0
0x180010ff9  lea     r15, [r15+rcx*8]
0x180010ffd  jnz     short loc_18001104F
0x180010fff  mov     rdx, [r15+18h]
0x180011003  mov     [r15+0Ah], bx
0x180011008  mov     word ptr [r15+0Ch], 1
0x18001100f  test    rdx, rdx
0x180011012  jz      loc_1800110AB
0x180011018  movzx   r8d, word ptr [rsp+98h+var_60]
0x18001101e  movzx   r9d, word ptr [r15+8]
0x180011023  mov     rcx, [rsp+98h+arg_0]
0x18001102b  movzx   eax, bx
0x18001102e  add     r8d, eax
0x180011031  call    WriteBytes
0x180011036  movzx   ebx, ax
0x180011039  test    ax, ax
0x18001103c  jnz     loc_180010FA6
0x180011042  mov     eax, [rsp+98h+var_64]
0x180011046  add     ax, [r15+8]
0x18001104b  mov     [rsp+98h+var_64], eax
0x18001104f  movzx   ecx, word ptr [r13+rbp*8+6]
0x180011055  lea     rax, [rsi+rsi*4]
0x180011059  add     cx, [r15+0Ah]
0x18001105e  mov     r15, [rsp+98h+arg_8]
0x180011066  mov     [r15+rax*8+0Ah], cx
0x18001106c  jmp     loc_180010EE5
0x180011071  mov     eax, 3EDh
0x180011076  jmp     loc_180010FB6
0x18001107b  mov     r8, rbp; Size
0x18001107e  mov     rcx, r14; Buf1
0x180011081  call    memcmp_0
0x180011086  mov     r8, [rsp+98h+arg_8]
0x18001108e  test    eax, eax
0x180011090  jnz     loc_180010D6C
0x180011096  movzx   eax, word ptr [rbx-4]
0x18001109a  mov     [rsi+4], ax
  ... truncated ...
```
