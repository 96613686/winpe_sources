# WapComputeHttpRequestHeaderBufferSize

- ea: `0x18000bfc0`
- end: `0x18000c735`
- name: `WapComputeHttpRequestHeaderBufferSize`
- size: `1909`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a598`

## callees

- `0x18000a468`
- `0x18000b6a4`
- `0x18000bfc0`
- `0x18000c740`
- `0x18000d710`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c17d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c17d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c1a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c1a4`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c602`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c671`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c6e0`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c602`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c671`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000c6e0`

## pseudocode

```c
__int64 __fastcall WapComputeHttpRequestHeaderBufferSize(__int64 a1, _QWORD *a2)
{
  RTL_SRWLOCK *v2; // r15
  __int64 v3; // rbx
  __int64 v4; // r8
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r13
  RTL_SRWLOCK *v7; // r14
  __m128i *v8; // r10
  __int64 v9; // rax
  _DWORD *Ptr; // rcx
  __m128i v11; // xmm6
  int v12; // ebx
  int v13; // ebx
  UINT v14; // ecx
  int v15; // ebx
  UINT v16; // ecx
  int v17; // ebx
  int v18; // ebx
  UINT v19; // ecx
  UINT *v20; // rax
  _BYTE *v21; // rbx
  char v22; // bl
  RTL_SRWLOCK *v23; // r12
  unsigned __int8 v24; // bl
  RTL_SRWLOCK *v25; // rsi
  RTL_SRWLOCK *v26; // r14
  RTL_SRWLOCK *v27; // rdi
  __int64 result; // rax
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rdi
  int v31; // esi
  __int64 v32; // r9
  unsigned __int64 v33; // r11
  unsigned __int64 v34; // rbx
  int j; // eax
  unsigned __int64 v36; // r10
  _QWORD *v37; // r9
  _QWORD *v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rcx
  __int64 v42; // rdi
  unsigned __int64 v43; // rbx
  char *v44; // rcx
  __int64 v45; // rcx
  unsigned __int8 v46; // r11
  int i; // r9d
  unsigned __int64 v48; // rax
  _DWORD *inited; // rcx
  int v50; // edx
  int v51; // r8d
  int v52; // eax
  __int64 v53; // rax
  unsigned __int64 v54; // rdx
  unsigned __int64 v55; // rcx
  PVOID v56; // rax
  bool v57; // zf
  __int64 v58; // rax
  unsigned __int64 v59; // rcx
  UINT v60; // ebx
  UINT v61; // ebx
  UINT v62; // ebx
  unsigned __int64 v63; // [rsp+40h] [rbp-79h] BYREF
  __int64 v64; // [rsp+48h] [rbp-71h]
  __int64 v65; // [rsp+50h] [rbp-69h] BYREF
  __int64 v66; // [rsp+58h] [rbp-61h]
  __int64 v67; // [rsp+60h] [rbp-59h]
  __int64 v68; // [rsp+68h] [rbp-51h]
  RTL_SRWLOCK *v69; // [rsp+70h] [rbp-49h]
  RTL_SRWLOCK *v70; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v71; // [rsp+80h] [rbp-39h] BYREF
  _QWORD *v72; // [rsp+88h] [rbp-31h]
  UINT CodePage[4]; // [rsp+90h] [rbp-29h] BYREF
  UINT v74[2]; // [rsp+A0h] [rbp-19h]
  struct _cpinfo CPInfo; // [rsp+A8h] [rbp-11h] BYREF

  v2 = 0;
  v64 = a1;
  *a2 = 0;
  v3 = a1;
  v4 = *(int *)(a1 + 324);
  v72 = a2;
  v71 = 0;
  if ( (_DWORD)v4 )
  {
    if ( (unsigned int)v4 > 8 )
    {
      v63 = 1;
      v6 = 1;
      goto LABEL_5;
    }
    v5 = qword_180099418[2 * v4];
  }
  else
  {
    v45 = *(_QWORD *)(a1 + 312);
    v5 = -1;
    do
      ++v5;
    while ( *(_BYTE *)(v45 + v5) );
  }
  v6 = v5 + 1;
  v63 = 1;
  if ( v5 + 1 < v5 )
    return 534;
LABEL_5:
  v7 = *(RTL_SRWLOCK **)(v3 + 328);
  v8 = (__m128i *)(v3 + 4548);
  v69 = v7;
  if ( (_DWORD)v4 == 3 )
  {
    result = WaQueryUriHttpRequestHost((char *)v7, (__int64 *)(v3 + 4548), 0, &v63);
    if ( (_DWORD)result )
      return result;
    v44 = (char *)(v63 + 6);
    if ( v63 + 6 < v63 )
      return 534;
    goto LABEL_29;
  }
  v9 = *(_QWORD *)(v3 + 88);
  Ptr = v7[7].Ptr;
  v65 = 4;
  v67 = 0;
  v68 = 0;
  *(_OWORD *)CodePage = 0;
  if ( *(_QWORD *)(v3 + 96) != v9 )
  {
    v66 = 0;
    *(_QWORD *)v74 = 0;
    if ( (unsigned int)(*Ptr - 1) <= 1 )
    {
      if ( v3 == -4548 )
      {
        v20 = (UINT *)&xmmword_1800AD538;
        goto LABEL_22;
      }
      v11 = (__m128i)*(unsigned __int64 *)(v3 + 4564);
      v12 = _mm_cvtsi128_si32(*v8);
      *(__m128i *)CodePage = *v8;
      *(_QWORD *)v74 = v11.m128i_i64[0];
      if ( !v12 )
      {
        *(_QWORD *)CodePage = xmmword_1800AD538;
        goto LABEL_13;
      }
      v13 = v12 & 0x771;
      CodePage[0] = v13;
      if ( (v13 & 1) != 0 )
      {
        v14 = CodePage[1];
      }
      else
      {
        v14 = DWORD1(xmmword_1800AD538);
        v13 |= 1u;
        CodePage[0] = v13;
        CodePage[1] = DWORD1(xmmword_1800AD538);
      }
      if ( v14 == 65001 )
      {
LABEL_13:
        if ( !CodePage[2] )
        {
          *(_QWORD *)&CodePage[2] = *((_QWORD *)&xmmword_1800AD538 + 1);
          goto LABEL_17;
        }
        v15 = CodePage[2] & 0x771;
        CodePage[2] = v15;
        if ( (v15 & 1) != 0 )
        {
          v16 = CodePage[3];
        }
        else
        {
          v16 = HIDWORD(xmmword_1800AD538);
          v15 |= 1u;
          CodePage[2] = v15;
          CodePage[3] = HIDWORD(xmmword_1800AD538);
        }
        if ( v16 == 65001 )
        {
LABEL_17:
          v17 = _mm_cvtsi128_si32(v11);
          if ( v17 )
          {
            v18 = v17 & 0x771;
            v74[0] = v18;
            if ( (v18 & 1) != 0 )
            {
              v19 = v74[1];
            }
            else
            {
              v19 = HIDWORD(qword_1800AD548);
              v18 |= 1u;
              v74[0] = v18;
              v74[1] = HIDWORD(qword_1800AD548);
            }
            switch ( v19 )
            {
              case 0xFDE9u:
                goto LABEL_21;
              case 0u:
                v62 = dword_1800AD530 | v18;
                goto LABEL_134;
              case 0xD698u:
                goto LABEL_132;
            }
            memset(&CPInfo, 0, sizeof(CPInfo));
            if ( GetCPInfo(v19, &CPInfo) )
            {
              if ( CPInfo.MaxCharSize == 1 )
              {
                v62 = v18 | 0x40000000;
LABEL_134:
                v74[0] = v62;
                goto LABEL_21;
              }
              if ( CPInfo.MaxCharSize == 2 )
              {
LABEL_132:
                v62 = v18 | 0x80000000;
                goto LABEL_134;
              }
            }
          }
          else
          {
            *(_QWORD *)v74 = qword_1800AD548;
          }
LABEL_21:
          v20 = CodePage;
LABEL_22:
          v21 = v7[4].Ptr;
          v63 = (unsigned __int64)v20;
          v22 = v21[240];
          if ( (v22 & 0x20) == 0 )
            return 87;
          v23 = v7 + 1;
          v24 = v22 & 0xE0;
          AcquireSRWLockShared(v7 + 1);
          v25 = (RTL_SRWLOCK *)v7[5].Ptr;
          v26 = v7 + 5;
          if ( v25 == v26 )
          {
            v27 = 0;
          }
          else
          {
            do
            {
              v27 = v25 - 1;
              v2 = v25;
              if ( LOBYTE(v25[29].Ptr) == v24 )
              {
                v46 = v24;
                for ( i = 0; v46 && i < 8; ++i )
                {
                  if ( (v46 & (unsigned __int8)(1 << i)) != 0 )
                  {
                    if ( (*((_DWORD *)v69[4].Ptr + 6 * i + 10) & ~*((_DWORD *)&v65 + i)) != LODWORD(v27[3 * i + 5].Ptr) )
                      goto LABEL_68;
                    v46 ^= 1 << i;
                  }
                }
                v48 = *(_QWORD *)v63 - *(unsigned __int64 *)((char *)&v27[30].Ptr + 4);
                if ( *(PVOID *)v63 == *(PVOID *)((char *)&v27[30].Ptr + 4) )
                {
                  v48 = *(_QWORD *)(v63 + 8) - *(unsigned __int64 *)((char *)&v27[31].Ptr + 4);
                  if ( !v48 )
                    v48 = *(_QWORD *)(v63 + 16) - *(unsigned __int64 *)((char *)&v27[32].Ptr + 4);
                }
                if ( !v48 )
                  break;
              }
LABEL_68:
              v25 = (RTL_SRWLOCK *)v25->Ptr;
              v27 = 0;
            }
            while ( v25 != v26 );
          }
          v70 = v27;
          ReleaseSRWLockShared(v23);
          v7 = v69;
          if ( !v27 )
          {
            result = WapUriCreateTransformedA(v69, v24, (__int64)&v65, (_QWORD *)v63, v2, &v70);
            if ( (_DWORD)result )
              return result;
            v27 = v70;
          }
          v44 = (char *)v27[28].Ptr;
          if ( (unsigned __int64)v44 > 0xC3500 )
            return 534;
          v3 = v64;
          goto LABEL_29;
        }
        if ( !v16 )
        {
          v61 = dword_1800AD530 | v15;
          goto LABEL_124;
        }
        if ( v16 != 54936 )
        {
          memset(&CPInfo, 0, sizeof(CPInfo));
          if ( !GetCPInfo(v16, &CPInfo) )
            goto LABEL_17;
          if ( CPInfo.MaxCharSize == 1 )
          {
            v61 = v15 | 0x40000000;
LABEL_124:
            CodePage[2] = v61;
            goto LABEL_17;
          }
          if ( CPInfo.MaxCharSize != 2 )
            goto LABEL_17;
        }
        v61 = v15 | 0x80000000;
        goto LABEL_124;
      }
      if ( !v14 )
      {
        v60 = dword_1800AD530 | v13;
        goto LABEL_114;
      }
      if ( v14 != 54936 )
      {
        memset(&CPInfo, 0, sizeof(CPInfo));
        if ( !GetCPInfo(v14, &CPInfo) )
          goto LABEL_13;
        if ( CPInfo.MaxCharSize == 1 )
        {
          v60 = v13 | 0x40000000;
LABEL_114:
          CodePage[0] = v60;
          goto LABEL_13;
        }
        if ( CPInfo.MaxCharSize != 2 )
          goto LABEL_13;
      }
      v60 = v13 | 0x80000000;
      goto LABEL_114;
    }
    return 87;
  }
  LODWORD(v66) = 0;
  *(_QWORD *)v74 = 0;
  if ( (unsigned int)(*Ptr - 1) > 1 )
    return 87;
  inited = (_DWORD *)WapUriInitCodePageParameters(v3 + 4548, CodePage);
  v50 = 335544324;
  LOBYTE(v51) = -48;
  v52 = 201326596;
  if ( (*inited & 0x100) != 0 )
    v52 = 335544324;
  LOBYTE(v50) = 41;
  HIDWORD(v66) = v52;
  result = WapUriGetTransformedStringA((_DWORD)v7, v50, v51, (unsigned int)&v65, (__int64)inited, 0, (__int64)&v63);
  if ( (_DWORD)result )
    return result;
  v44 = (char *)v63;
LABEL_29:
  v29 = (unsigned __int64)&v44[v6];
  if ( (unsigned __int64)&v44[v6] < v6 )
    return 534;
  v30 = v29 + 11;
  if ( v29 + 11 < v29 )
    return 534;
  v31 = *(_DWORD *)(v3 + 324);
  v32 = v31 == 3 ? v3 + 1072 : v3 + 344;
  v33 = 0;
  v34 = 0;
  for ( j = 0; j < 41; ++j )
  {
    if ( *(_QWORD *)(v32 + 16LL * j) )
    {
      v36 = v33 + *(_QWORD *)WaHttpRequestHeaderMapTable[j];
      if ( v36 < v33 )
        return 534;
      v33 = v36 + *(_QWORD *)(v32 + 16LL * j + 8);
      if ( v33 < v36 )
        return 534;
      ++v34;
    }
  }
  v37 = (_QWORD *)(v32 + 704);
  v38 = (_QWORD *)*v37;
  while ( v38 != v37 )
  {
    v39 = v33 + v38[3];
    if ( v39 < v33 )
      return 534;
    v33 = v39 + v38[5];
    if ( v33 < v39 )
      return 534;
    v38 = (_QWORD *)*v38;
    ++v34;
  }
  v40 = v30 + v33;
  if ( v30 + v33 < v30 )
    return 534;
  if ( v34 > 0x3FFFFFFFFFFFFFFFLL )
    return 534;
  v41 = v40 + 4 * v34;
  if ( v41 < v40 )
    return 534;
  v42 = v64;
  if ( v31 == 3 || (*(_BYTE *)(v64 + 1800) & 1) == 0 )
  {
    v43 = v40 + 4 * v34;
    if ( v31 != 3 && (*(_DWORD *)(v64 + 1800) & 0x40000000) != 0 )
    {
      v43 = v41 + 28;
      if ( v41 + 28 < v41 )
        return 534;
    }
  }
  else
  {
    v43 = v41 + 38;
    if ( v41 + 38 < v41 )
      return 534;
  }
  result = WaQueryUriHttpRequestHost((char *)v7, (__int64 *)(v64 + 4548), 0, &v71);
  if ( !(_DWORD)result )
  {
    v53 = v71 + 8;
    if ( v71 >= 0xFFFFFFFFFFFFFFF8uLL )
      return 534;
    v54 = v53 + v43;
    if ( v53 + v43 < v43 )
      return 534;
    if ( *(_DWORD *)(v42 + 324) == 3 )
    {
      v58 = 6;
    }
    else
    {
      v55 = (unsigned __int64)v7[32].Ptr;
      v56 = 0;
      if ( v55 <= 0x186A0 )
        v56 = v7[32].Ptr;
      v57 = v56 == 0;
      v58 = 0;
      if ( !v57 )
      {
        if ( v55 <= 0x186A0 )
          v58 = (__int64)v7[32].Ptr;
        ++v58;
      }
    }
    v59 = v54 + v58;
    if ( v54 + v58 < v54 || v59 + 3 < v59 )
      return 534;
    *v72 = v59 + 3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bfc0  mov     [rsp-8+arg_10], rbx
0x18000bfc5  push    rbp
0x18000bfc6  push    rsi
0x18000bfc7  push    rdi
0x18000bfc8  push    r12
0x18000bfca  push    r13
0x18000bfcc  push    r14
0x18000bfce  push    r15
0x18000bfd0  lea     rbp, [rsp-27h]
0x18000bfd5  sub     rsp, 0E0h
0x18000bfdc  mov     rax, cs:__security_cookie
0x18000bfe3  xor     rax, rsp
0x18000bfe6  mov     [rbp+57h+var_50], rax
0x18000bfea  xor     r15d, r15d
0x18000bfed  mov     [rbp+57h+var_C8], rcx
0x18000bff1  mov     [rdx], r15
0x18000bff4  mov     rbx, rcx
0x18000bff7  movsxd  r8, dword ptr [rcx+144h]
0x18000bffe  lea     rcx, __ImageBase
0x18000c005  mov     [rbp+57h+var_88], rdx
0x18000c009  mov     [rbp+57h+var_90], r15
0x18000c00d  test    r8d, r8d
0x18000c010  jz      loc_18000C320
0x18000c016  js      loc_18000C5B5
0x18000c01c  cmp     r8d, 9
0x18000c020  jnb     loc_18000C5B5
0x18000c026  mov     rax, r8
0x18000c029  add     rax, rax
0x18000c02c  mov     rax, ds:rva qword_180099418[rcx+rax*8]
0x18000c034  lea     r13, [rax+1]
0x18000c038  mov     [rbp+57h+var_D0], 1
0x18000c040  cmp     r13, rax
0x18000c043  jb      loc_18000C2F1
0x18000c049  mov     r14, [rbx+148h]
0x18000c050  lea     r10, [rbx+11C4h]
0x18000c057  mov     [rbp+57h+var_A0], r14
0x18000c05b  cmp     r8d, 3
0x18000c05f  jz      loc_18000C55B
0x18000c065  mov     rax, [rbx+58h]
0x18000c069  xorps   xmm0, xmm0
0x18000c06c  mov     rcx, [r14+38h]
0x18000c070  mov     [rbp+57h+var_C0], 4
0x18000c078  mov     [rbp+57h+var_B0], r15
0x18000c07c  mov     [rbp+57h+var_A8], r15
0x18000c080  movups  xmmword ptr [rbp+57h+CodePage], xmm0
0x18000c084  cmp     [rbx+60h], rax
0x18000c088  jz      loc_18000C416
0x18000c08e  xor     eax, eax
0x18000c090  mov     [rbp+57h+var_B8], r15
0x18000c094  mov     qword ptr [rbp+57h+var_70], rax
0x18000c098  mov     eax, [rcx]
0x18000c09a  dec     eax
0x18000c09c  cmp     eax, 1
0x18000c09f  ja      loc_18000C5C8
0x18000c0a5  test    r10, r10
0x18000c0a8  jz      loc_18000C71F
0x18000c0ae  movups  xmm0, xmmword ptr [r10]
0x18000c0b2  movaps  [rsp+110h+var_40], xmm6
0x18000c0ba  movsd   xmm6, qword ptr [r10+10h]
0x18000c0c0  movd    ebx, xmm0
0x18000c0c4  movups  xmmword ptr [rbp+57h+CodePage], xmm0
0x18000c0c8  movsd   qword ptr [rbp+57h+var_70], xmm6
0x18000c0cd  test    ebx, ebx
0x18000c0cf  jz      loc_18000C3E6
0x18000c0d5  and     ebx, 771h
0x18000c0db  mov     [rbp+57h+CodePage], ebx
0x18000c0de  test    bl, 1
0x18000c0e1  jz      loc_18000C5D2
0x18000c0e7  mov     ecx, [rbp+57h+CodePage+4]; CodePage
0x18000c0ea  cmp     ecx, 0FDE9h
0x18000c0f0  jnz     loc_18000C5E6
0x18000c0f6  mov     ebx, [rbp+57h+CodePage+8]
0x18000c0f9  test    ebx, ebx
0x18000c0fb  jz      loc_18000C3F6
0x18000c101  and     ebx, 771h
0x18000c107  mov     [rbp+57h+CodePage+8], ebx
0x18000c10a  test    bl, 1
0x18000c10d  jz      loc_18000C641
0x18000c113  mov     ecx, [rbp+57h+CodePage+0Ch]; CodePage
0x18000c116  cmp     ecx, 0FDE9h
0x18000c11c  jnz     loc_18000C655
0x18000c122  movd    ebx, xmm6
0x18000c126  movaps  xmm6, [rsp+110h+var_40]
0x18000c12e  test    ebx, ebx
0x18000c130  jz      loc_18000C406
0x18000c136  and     ebx, 771h
0x18000c13c  mov     [rbp+57h+var_70], ebx
0x18000c13f  test    bl, 1
0x18000c142  jz      loc_18000C6B0
0x18000c148  mov     ecx, [rbp+57h+var_70+4]; CodePage
0x18000c14b  cmp     ecx, 0FDE9h
0x18000c151  jnz     loc_18000C6C4
0x18000c157  lea     rax, [rbp+57h+CodePage]
0x18000c15b  mov     rbx, [r14+20h]
0x18000c15f  mov     [rbp+57h+var_D0], rax
0x18000c163  movzx   ebx, byte ptr [rbx+0F0h]
0x18000c16a  test    bl, 20h
0x18000c16d  jz      loc_18000C72B
0x18000c173  lea     r12, [r14+8]
0x18000c177  and     bl, 0E0h
0x18000c17a  mov     rcx, r12; SRWLock
0x18000c17d  call    cs:__imp_AcquireSRWLockShared
0x18000c184  nop     dword ptr [rax+rax+00h]
0x18000c189  mov     rsi, [r14+28h]
0x18000c18d  add     r14, 28h ; '('
0x18000c191  cmp     rsi, r14
0x18000c194  jnz     loc_18000C340
0x18000c19a  mov     rdi, r15
0x18000c19d  mov     rcx, r12; SRWLock
0x18000c1a0  mov     [rbp+57h+var_98], rdi
0x18000c1a4  call    cs:__imp_ReleaseSRWLockShared
0x18000c1ab  nop     dword ptr [rax+rax+00h]
0x18000c1b0  mov     r14, [rbp+57h+var_A0]
0x18000c1b4  test    rdi, rdi
0x18000c1b7  jnz     loc_18000C2FF
0x18000c1bd  mov     r9, [rbp+57h+var_D0]
0x18000c1c1  lea     rax, [rbp+57h+var_98]
0x18000c1c5  mov     [rsp+110h+var_E8], rax
0x18000c1ca  lea     r8, [rbp+57h+var_C0]
0x18000c1ce  movzx   edx, bl
0x18000c1d1  mov     [rsp+110h+var_F0], r15
0x18000c1d6  mov     rcx, r14
0x18000c1d9  call    WapUriCreateTransformedA
0x18000c1de  test    eax, eax
0x18000c1e0  jz      loc_18000C2FB
0x18000c1e6  xor     r15d, r15d
0x18000c1e9  mov     rcx, r15
0x18000c1ec  test    eax, eax
0x18000c1ee  jnz     loc_18000C527
0x18000c1f4  mov     rbx, [rbp+57h+var_C8]
0x18000c1f8  lea     rax, [rcx+r13]
0x18000c1fc  cmp     rax, r13
0x18000c1ff  jb      loc_18000C2F1
0x18000c205  lea     rdi, [rax+0Bh]
0x18000c209  cmp     rdi, rax
0x18000c20c  jb      loc_18000C2F1
0x18000c212  mov     esi, [rbx+144h]
0x18000c218  cmp     esi, 3
0x18000c21b  jz      loc_18000C54F
0x18000c221  lea     r9, [rbx+158h]
0x18000c228  mov     r11, r15
0x18000c22b  lea     r12, __ImageBase
0x18000c232  mov     rbx, r15
0x18000c235  mov     eax, r15d
0x18000c238  cmp     eax, 29h ; ')'
0x18000c23b  jge     short loc_18000C27A
0x18000c23d  movsxd  rdx, eax
0x18000c240  mov     r8, rdx
0x18000c243  add     r8, r8
0x18000c246  cmp     qword ptr [r9+r8*8], 0
0x18000c24b  jnz     short loc_18000C251
0x18000c24d  inc     eax
0x18000c24f  jmp     short loc_18000C238
0x18000c251  mov     rcx, rva WaHttpRequestHeaderMapTable[r12+rdx*8]
0x18000c259  mov     r10, [rcx]
0x18000c25c  add     r10, r11
0x18000c25f  cmp     r10, r11
0x18000c262  jb      loc_18000C2F1
0x18000c268  mov     r11, [r9+r8*8+8]
0x18000c26d  add     r11, r10
0x18000c270  cmp     r11, r10
0x18000c273  jb      short loc_18000C2F1
0x18000c275  inc     rbx
0x18000c278  jmp     short loc_18000C24D
0x18000c27a  add     r9, 2C0h
0x18000c281  mov     rcx, [r9]
0x18000c284  cmp     rcx, r9
0x18000c287  jz      short loc_18000C2A9
0x18000c289  mov     rdx, [rcx+18h]
0x18000c28d  add     rdx, r11
0x18000c290  cmp     rdx, r11
0x18000c293  jb      short loc_18000C2F1
0x18000c295  mov     r11, [rcx+28h]
0x18000c299  add     r11, rdx
0x18000c29c  cmp     r11, rdx
0x18000c29f  jb      short loc_18000C2F1
0x18000c2a1  mov     rcx, [rcx]
0x18000c2a4  inc     rbx
0x18000c2a7  jmp     short loc_18000C284
0x18000c2a9  lea     rax, [rdi+r11]
0x18000c2ad  cmp     rax, rdi
0x18000c2b0  jb      short loc_18000C2F1
0x18000c2b2  mov     rcx, 3FFFFFFFFFFFFFFFh
0x18000c2bc  cmp     rbx, rcx
0x18000c2bf  ja      short loc_18000C2F1
0x18000c2c1  lea     rcx, [rax+rbx*4]
0x18000c2c5  cmp     rcx, rax
0x18000c2c8  jb      short loc_18000C2F1
0x18000c2ca  mov     rdi, [rbp+57h+var_C8]
0x18000c2ce  cmp     esi, 3
0x18000c2d1  jz      loc_18000C487
0x18000c2d7  test    byte ptr [rdi+708h], 1
0x18000c2de  jz      loc_18000C487
0x18000c2e4  lea     rbx, [rcx+26h]
0x18000c2e8  cmp     rbx, rcx
0x18000c2eb  jnb     loc_18000C493
0x18000c2f1  mov     eax, 216h
0x18000c2f6  jmp     loc_18000C527
0x18000c2fb  mov     rdi, [rbp+57h+var_98]
0x18000c2ff  mov     rcx, [rdi+0E0h]
0x18000c306  xor     r15d, r15d
0x18000c309  cmp     rcx, 0C3500h
0x18000c310  jbe     loc_18000C1F4
0x18000c316  mov     eax, 216h
0x18000c31b  jmp     loc_18000C1E9
0x18000c320  mov     rcx, [rbx+138h]
0x18000c327  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c32e  xchg    ax, ax
0x18000c330  inc     rax
0x18000c333  cmp     [rcx+rax], r15b
0x18000c337  jnz     short loc_18000C330
0x18000c339  jmp     loc_18000C034
0x18000c340  lea     rdi, [rsi-8]
0x18000c344  mov     r15, rsi
0x18000c347  cmp     [rdi+0F0h], bl
0x18000c34d  jnz     short loc_18000C3A8
0x18000c34f  movzx   r11d, bl
0x18000c353  xor     r9d, r9d
0x18000c356  test    r11b, r11b
0x18000c359  jz      short loc_18000C377
0x18000c35b  cmp     r9d, 8
0x18000c35f  jge     short loc_18000C377
0x18000c361  mov     ecx, r9d
0x18000c364  mov     r10d, 1
0x18000c36a  shl     r10b, cl
0x18000c36d  test    r10b, r11b
0x18000c370  jnz     short loc_18000C3B8
0x18000c372  inc     r9d
0x18000c375  jmp     short loc_18000C356
0x18000c377  mov     rcx, [rbp+57h+var_D0]
0x18000c37b  mov     rax, [rcx]
0x18000c37e  sub     rax, [rdi+0F4h]
0x18000c385  jnz     short loc_18000C39F
0x18000c387  mov     rax, [rcx+8]
0x18000c38b  sub     rax, [rdi+0FCh]
0x18000c392  jnz     short loc_18000C39F
0x18000c394  mov     rax, [rcx+10h]
0x18000c398  sub     rax, [rdi+104h]
0x18000c39f  test    rax, rax
0x18000c3a2  jz      loc_18000C19D
0x18000c3a8  mov     rsi, [rsi]
0x18000c3ab  xor     edi, edi
0x18000c3ad  cmp     rsi, r14
0x18000c3b0  jz      loc_18000C19D
0x18000c3b6  jmp     short loc_18000C340
0x18000c3b8  movsxd  rcx, r9d
0x18000c3bb  mov     edx, dword ptr [rbp+rcx*4+57h+var_C0]
0x18000c3bf  lea     rax, [rcx+rcx*2]
0x18000c3c3  lea     r8, ds:0[rax*8]
0x18000c3cb  not     edx
0x18000c3cd  mov     rax, [rbp+57h+var_A0]
0x18000c3d1  mov     rax, [rax+20h]
0x18000c3d5  and     edx, [r8+rax+28h]
0x18000c3da  cmp     edx, [rdi+r8+28h]
0x18000c3df  jnz     short loc_18000C3A8
0x18000c3e1  xor     r11b, r10b
0x18000c3e4  jmp     short loc_18000C372
0x18000c3e6  mov     rax, qword ptr cs:xmmword_1800AD538
0x18000c3ed  mov     qword ptr [rbp+57h+CodePage], rax
0x18000c3f1  jmp     loc_18000C0F6
0x18000c3f6  mov     rax, qword ptr cs:xmmword_1800AD538+8
0x18000c3fd  mov     qword ptr [rbp+57h+CodePage+8], rax
0x18000c401  jmp     loc_18000C122
0x18000c406  mov     rax, cs:qword_1800AD548
0x18000c40d  mov     qword ptr [rbp+57h+var_70], rax
0x18000c411  jmp     loc_18000C157
0x18000c416  xor     eax, eax
0x18000c418  mov     dword ptr [rbp+57h+var_B8], r15d
0x18000c41c  mov     qword ptr [rbp+57h+var_70], rax
0x18000c420  mov     eax, [rcx]
0x18000c422  dec     eax
0x18000c424  cmp     eax, 1
0x18000c427  ja      loc_18000C5C8
0x18000c42d  lea     rdx, [rbp+57h+CodePage]
0x18000c431  mov     rcx, r10
0x18000c434  call    WapUriInitCodePageParameters
0x18000c439  mov     rcx, rax
0x18000c43c  lea     r9, [rbp+57h+var_C0]
0x18000c440  mov     edx, 14000004h
0x18000c445  mov     r8b, 0D0h
0x18000c448  test    dword ptr [rax], 100h
0x18000c44e  mov     eax, 0C000004h
0x18000c453  cmovnz  eax, edx
0x18000c456  mov     dl, 29h ; ')'
0x18000c458  mov     dword ptr [rbp+57h+var_B8+4], eax
0x18000c45b  lea     rax, [rbp+57h+var_D0]
0x18000c45f  mov     [rsp+110h+var_E0], rax
0x18000c464  mov     [rsp+110h+var_E8], r15
0x18000c469  mov     [rsp+110h+var_F0], rcx
0x18000c46e  mov     rcx, r14
0x18000c471  call    WapUriGetTransformedStringA
0x18000c476  test    eax, eax
0x18000c478  jnz     loc_18000C527
0x18000c47e  mov     rcx, [rbp+57h+var_D0]
0x18000c482  jmp     loc_18000C1F8
0x18000c487  mov     rbx, rcx
0x18000c48a  cmp     esi, 3
0x18000c48d  jnz     loc_18000C589
0x18000c493  lea     r9, [rbp+57h+var_90]
0x18000c497  xor     r8d, r8d
  ... truncated ...
```
