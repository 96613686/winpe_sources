# WaQueryUriHttpRequestHost

- ea: `0x18000b6a4`
- end: `0x18000bfb5`
- name: `WaQueryUriHttpRequestHost`
- size: `2321`
- prototype: `__int64 __fastcall(char *, __int64 *, _QWORD *, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009eec`
- `0x18000a710`
- `0x18000bfc0`
- `0x18000e128`
- `0x18008ca78`

## callees

- `0x18000b6a4`
- `0x18000cea0`
- `0x18000dc18`
- `0x18000dc64`
- `0x18000df68`
- `0x180013820`
- `0x1800391c0`
- `0x18006aa60`
- `0x1800722f0`
- `0x180083570`
- `0x180091678`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b792`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b792`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b7e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b7e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bade`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bade`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb82`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000be14`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18000be14`

## pseudocode

```c
__int64 __fastcall WaQueryUriHttpRequestHost(char *a1, __int64 *a2, _QWORD *a3, unsigned __int64 *a4)
{
  unsigned __int64 *v4; // rsi
  _QWORD *v5; // r12
  char *v6; // r13
  __int64 v7; // rcx
  UINT v8; // ecx
  __int16 v9; // bx
  UINT v10; // eax
  int v11; // edi
  UINT *v12; // rdi
  __int64 v13; // rax
  int v14; // ebx
  int v15; // edx
  char *v16; // rcx
  char *v17; // r14
  int v18; // edx
  __int64 v19; // rax
  unsigned __int8 v20; // bl
  __int64 v21; // r12
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int64 v33; // r15
  __int64 v34; // r12
  __int64 v35; // rcx
  unsigned int v36; // edi
  unsigned __int64 v37; // rcx
  LPVOID *v38; // rsi
  int v39; // eax
  unsigned int v40; // edi
  bool v41; // zf
  int v42; // eax
  __int128 v43; // xmm0
  void *v44; // xmm1_8
  unsigned __int64 v45; // rax
  __int64 v47; // rdi
  __int64 v48; // rax
  _QWORD *v49; // rsi
  int v50; // edx
  char *v51; // rax
  _QWORD *v52; // r15
  _QWORD *v53; // r11
  _QWORD *v54; // rdx
  int j; // esi
  void *v56; // r8
  unsigned __int64 v57; // r12
  char *Heap; // rax
  char *v59; // r15
  __int64 v60; // r13
  char v61; // r15
  void *v62; // xmm1_8
  _QWORD *v63; // rax
  char v64; // r9
  int i; // r8d
  __int64 v66; // rax
  UINT v67; // edi
  unsigned __int64 PercentEncodeLength; // rax
  __int64 v69; // [rsp+28h] [rbp-D8h]
  char v70; // [rsp+40h] [rbp-C0h]
  __int64 v71; // [rsp+48h] [rbp-B8h] BYREF
  int v72; // [rsp+50h] [rbp-B0h]
  int v73; // [rsp+54h] [rbp-ACh]
  int v74; // [rsp+58h] [rbp-A8h]
  unsigned __int64 *v75; // [rsp+60h] [rbp-A0h]
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  char *v77; // [rsp+70h] [rbp-90h] BYREF
  int v78[2]; // [rsp+78h] [rbp-88h]
  char *v79; // [rsp+80h] [rbp-80h]
  _QWORD *v80; // [rsp+88h] [rbp-78h]
  _OWORD v81[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE CPInfo[24]; // [rsp+B0h] [rbp-50h] BYREF
  UINT CodePage[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v84; // [rsp+D8h] [rbp-28h]
  LPVOID lpMem[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v86; // [rsp+F0h] [rbp-10h]
  __int128 v87; // [rsp+100h] [rbp+0h]
  __int128 v88; // [rsp+110h] [rbp+10h]
  __int128 v89; // [rsp+120h] [rbp+20h]
  __int128 v90; // [rsp+130h] [rbp+30h]
  __int128 v91; // [rsp+140h] [rbp+40h]
  __int128 v92; // [rsp+150h] [rbp+50h]
  __int128 v93; // [rsp+160h] [rbp+60h]
  __int128 v94; // [rsp+170h] [rbp+70h]
  __int128 v95; // [rsp+180h] [rbp+80h]
  __int128 v96; // [rsp+190h] [rbp+90h]

  v75 = a4;
  v80 = a3;
  v77 = a1;
  v4 = a4;
  v84 = 0;
  v5 = a3;
  v6 = a1;
  *(_OWORD *)CodePage = 0;
  if ( !a2 )
  {
    v9 = xmmword_1800AD538;
    v12 = (UINT *)&xmmword_1800AD538;
    goto LABEL_10;
  }
  v7 = *a2;
  v84 = qword_1800AD548;
  *(_QWORD *)&CodePage[2] = *((_QWORD *)&xmmword_1800AD538 + 1);
  *(_QWORD *)CodePage = v7;
  if ( !(_DWORD)v7 )
  {
    v9 = xmmword_1800AD538;
    *(_QWORD *)CodePage = xmmword_1800AD538;
    goto LABEL_9;
  }
  v8 = v7 & 0x771;
  CodePage[0] = v8;
  v9 = v8;
  if ( (v8 & 1) != 0 )
  {
    v10 = CodePage[1];
  }
  else
  {
    v9 = v8 | 1;
    CodePage[0] = v8 | 1;
    v10 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)xmmword_1800AD538, 4));
    CodePage[1] = v10;
  }
  v11 = v8 | 1;
  if ( (v8 & 1) != 0 )
    v11 = v8;
  if ( !v10 )
  {
    v67 = dword_1800AD530 | v11;
    goto LABEL_112;
  }
  if ( v10 != 65001 )
  {
    if ( v10 != 54936 )
    {
      memset(CPInfo, 0, 20);
      if ( !GetCPInfo(v10, (LPCPINFO)CPInfo) )
        goto LABEL_9;
      if ( *(_DWORD *)CPInfo == 1 )
      {
        v67 = v11 | 0x40000000;
LABEL_112:
        v9 = v67;
        CodePage[0] = v67;
        goto LABEL_9;
      }
      if ( *(_DWORD *)CPInfo != 2 )
        goto LABEL_9;
    }
    v67 = v11 | 0x80000000;
    goto LABEL_112;
  }
LABEL_9:
  v12 = CodePage;
LABEL_10:
  v13 = *((_QWORD *)v6 + 4);
  *(_QWORD *)v78 = v12;
  v14 = (v9 & 0x100) != 0 ? 335544324 : 201326596;
  if ( (*(_BYTE *)(v13 + 240) & 8) == 0 )
  {
    v36 = 87;
    goto LABEL_65;
  }
  AcquireSRWLockShared((PSRWLOCK)v6 + 1);
  v15 = ~v14 & *(_DWORD *)(*((_QWORD *)v6 + 4) + 112LL);
  v16 = (char *)*((_QWORD *)v6 + 5);
  if ( v16 == v6 + 40 )
  {
    v17 = 0;
    v79 = 0;
  }
  else
  {
    do
    {
      v17 = v16 - 8;
      v79 = v16;
      if ( (v16[232] & 8) != 0 && v15 == *((_DWORD *)v17 + 28) && *(_QWORD *)v12 == *(_QWORD *)(v17 + 244) )
        break;
      v16 = *(char **)v16;
      v17 = 0;
    }
    while ( v16 != v6 + 40 );
  }
  ReleaseSRWLockShared((PSRWLOCK)v6 + 1);
  if ( v17 )
  {
LABEL_37:
    v45 = *((_QWORD *)v17 + 13);
    if ( v45 > 0x186A0 )
    {
      v36 = 534;
      goto LABEL_64;
    }
    *v75 = v45;
    if ( v5 )
      *v5 = *((_QWORD *)v17 + 12);
    return 0;
  }
  v19 = *((_QWORD *)v6 + 4);
  memset(v81, 0, sizeof(v81));
  HIDWORD(v81[0]) = v14;
  v20 = 0;
  LOBYTE(v18) = 8;
  v70 = 8;
  LODWORD(v21) = 0;
  v22 = *(_OWORD *)(v19 + 40);
  *(_OWORD *)lpMem = *(_OWORD *)(v19 + 24);
  v23 = *(_OWORD *)(v19 + 56);
  v86 = v22;
  v24 = *(_OWORD *)(v19 + 72);
  v87 = v23;
  v25 = *(_OWORD *)(v19 + 88);
  v88 = v24;
  v26 = *(_OWORD *)(v19 + 104);
  v89 = v25;
  v27 = *(_OWORD *)(v19 + 120);
  v90 = v26;
  v28 = *(_OWORD *)(v19 + 136);
  v91 = v27;
  v29 = *(_OWORD *)(v19 + 152);
  v92 = v28;
  v30 = *(_OWORD *)(v19 + 168);
  v93 = v29;
  v31 = *(_OWORD *)(v19 + 184);
  v94 = v30;
  v32 = *(_OWORD *)(v19 + 200);
  v95 = v31;
  v96 = v32;
  while ( 1 )
  {
    v72 = v21;
    if ( (int)v21 >= 8 )
      break;
    LOBYTE(v74) = 1 << v21;
    if ( ((unsigned __int8)v18 & (unsigned __int8)(1 << v21)) == 0 )
      goto LABEL_18;
    v37 = (int)v21;
    v76 = (int)v21;
    memset(CPInfo, 0, sizeof(CPInfo));
    v38 = &lpMem[3 * (int)v21];
    if ( (_DWORD)v21 == 3 )
    {
      v42 = HIDWORD(v81[0]) & (_DWORD)v38[2] & 0x1C000000;
      if ( v42 )
      {
        switch ( v42 )
        {
          case 0x4000000:
            goto LABEL_29;
          case 0x8000000:
            if ( !*((_QWORD *)v6 + 29) )
              goto LABEL_43;
            if ( (v20 & 8) != 0 && *v38 )
            {
              v71 = (__int64)*v38;
              WxFreeHeapEx(&v71);
              LOBYTE(v18) = v70;
              v37 = 3;
            }
            v43 = *((_OWORD *)v6 + 14);
            v44 = (void *)*((_QWORD *)v6 + 30);
            break;
          case 0x10000000:
LABEL_29:
            if ( (v20 & 8) != 0 && *v38 )
            {
              v71 = (__int64)*v38;
              WxFreeHeapEx(&v71);
              LOBYTE(v18) = v70;
              v37 = 3;
            }
            v43 = *(_OWORD *)(v6 + 200);
            v44 = (void *)*((_QWORD *)v6 + 27);
            break;
          default:
            goto LABEL_43;
        }
        *(_OWORD *)v38 = v43;
        v20 &= ~8u;
        v38[2] = v44;
      }
    }
    v39 = *((_DWORD *)v38 + 4);
    LOBYTE(v18) = (1 << v21) ^ v18;
    v40 = v39 & *((_DWORD *)v81 + v37);
    v70 = v18;
    v41 = (*((_DWORD *)v81 + v37) & 0x1000000) == 0;
    v73 = v39;
    if ( !v41 && (v39 & 0xE003FE08) != 0 )
      v40 |= 0x1000008u;
    if ( v40 )
    {
      if ( (v40 & 0x202) != 0 || ((unsigned __int8)v40 & BYTE1(v40) & 0xF8) != 0 )
      {
LABEL_43:
        v36 = 87;
        goto LABEL_53;
      }
      if ( (v40 & 0xF8) != 0 )
      {
        PercentEncodeLength = WapUriGetPercentEncodeLength((unsigned int)v21, v40, &lpMem[3 * (int)v21]);
        v37 = (unsigned __int64)v38[1];
        v57 = PercentEncodeLength;
        v71 = v37;
        if ( PercentEncodeLength < v37 )
          goto LABEL_20;
      }
      else
      {
        v57 = (unsigned __int64)v38[1];
        v71 = v57;
      }
      if ( v57 - 1 > 0x1869F )
        goto LABEL_43;
      if ( 2 * v57 < v57 )
        goto LABEL_133;
      Heap = (char *)WxAllocateHeapEx(v37, 2 * v57);
      v59 = Heap;
      if ( !Heap )
        goto LABEL_133;
      if ( (v40 & 0xE003FFFF) != 0 )
      {
        if ( (*((_BYTE *)v81 + 4 * v76) & 4) != 0 )
        {
          if ( (*((_DWORD *)v81 + v76) & 0x40000000) != 0 )
          {
            v36 = 87;
LABEL_132:
            v77 = v59;
            WxFreeHeapEx(&v77);
            goto LABEL_53;
          }
          v40 |= 4u;
        }
        v60 = (__int64)*v38;
        v69 = v57;
        v21 = v72;
        v36 = WapUriTransformIriComponentCharacters(
                v72,
                v40,
                (unsigned int)*v38,
                v71,
                (__int64)Heap,
                v69,
                (__int64)&CPInfo[8]);
        if ( v36 )
          goto LABEL_132;
        *(_QWORD *)CPInfo = v59;
        WapUriUpdateIriComponentEncodedFlags((unsigned int)v21, CPInfo);
        *(_DWORD *)&CPInfo[16] = v73 & 0x1DFC0000 | *(_DWORD *)&CPInfo[16] & dword_18009D088[v21];
        v40 = *((_DWORD *)v81 + v21) & *(_DWORD *)&CPInfo[16];
      }
      else
      {
        v21 = v71;
        v60 = (__int64)*v38;
        memcpy_0(Heap, *v38, 2 * v71);
        *(_QWORD *)&CPInfo[8] = v21;
        LODWORD(v21) = v72;
        *(_DWORD *)&CPInfo[16] = v73;
        *(_QWORD *)CPInfo = v59;
      }
      v61 = v74;
      if ( ((unsigned __int8)v74 & v20) != 0 && v60 )
      {
        v76 = v60;
        WxFreeHeapEx(&v76);
      }
      v20 |= v61;
      v62 = *(void **)&CPInfo[16];
      *(_OWORD *)v38 = *(_OWORD *)CPInfo;
      v38[2] = v62;
      if ( (_DWORD)v21 == 5 )
      {
        v36 = WapUriTransformPath(v38, v40);
        if ( v36 )
          goto LABEL_53;
      }
      v6 = v77;
      LOBYTE(v18) = v70;
    }
LABEL_18:
    if ( !(_BYTE)v18 )
      break;
    LODWORD(v21) = v21 + 1;
  }
  v33 = *((_QWORD *)v6 + 7);
  v34 = *(_QWORD *)v78;
  LOBYTE(v18) = 8;
  v71 = 0;
  if ( (unsigned int)WapUriRecomposeA(v33, v18, (int)lpMem, v78[0], 0, 0, 0, (__int64)&v71)
    || (v47 = v71, (unsigned __int64)(v71 - 1) > 0xC34FF) )
  {
LABEL_20:
    v36 = 534;
    goto LABEL_53;
  }
  v48 = WxAllocateHeapEx(v35, v71 + 272);
  v49 = (_QWORD *)v48;
  if ( !v48 )
  {
LABEL_133:
    v36 = 8;
    goto LABEL_53;
  }
  *(_QWORD *)v48 = 0;
  v50 = v48 + 24;
  *(_DWORD *)v48 = 1430868565;
  *(_BYTE *)(v48 + 240) = 8;
  *(_OWORD *)(v48 + 244) = *(_OWORD *)v34;
  LOBYTE(v50) = 8;
  *(_QWORD *)(v48 + 260) = *(_QWORD *)(v34 + 16);
  v36 = WapUriRecomposeA(v33, v50, (int)lpMem, v34, (void *)(v48 + 24), v48 + 272, v47, 0);
  if ( v36 )
  {
    WapUriFreeTransformedUri(v49);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)v6 + 1);
    v51 = v79;
    v52 = v6 + 40;
    if ( !v79 )
      v51 = v6 + 40;
    v53 = *(_QWORD **)v51;
    if ( *(_QWORD **)v51 == v52 )
      goto LABEL_50;
    v63 = *(_QWORD **)v51;
    do
    {
      v17 = (char *)(v63 - 1);
      if ( *((_BYTE *)v63 + 232) == 8 )
      {
        v64 = 8;
        for ( i = 0; v64 && i < 8; ++i )
        {
          if ( ((unsigned __int8)v64 & (unsigned __int8)(1 << i)) != 0 )
          {
            if ( (*(_DWORD *)(*((_QWORD *)v6 + 4) + 24LL * i + 40) & ~*((_DWORD *)v81 + i)) != *(_DWORD *)&v17[24 * i + 40] )
              goto LABEL_94;
            v64 ^= 1 << i;
          }
        }
        v66 = *(_QWORD *)v34 - *(_QWORD *)(v17 + 244);
        if ( *(_QWORD *)v34 == *(_QWORD *)(v17 + 244) )
        {
          v66 = *(_QWORD *)(v34 + 8) - *(_QWORD *)(v17 + 252);
          if ( !v66 )
            v66 = *(_QWORD *)(v34 + 16) - *(_QWORD *)(v17 + 260);
        }
        if ( !v66 )
          break;
      }
LABEL_94:
      v63 = (_QWORD *)*v53;
      v17 = 0;
      v53 = v63;
    }
    while ( v63 != v52 );
    if ( !v17 )
    {
LABEL_50:
      v54 = (_QWORD *)*((_QWORD *)v6 + 6);
      if ( (_QWORD *)*v54 != v52 )
        __fastfail(3u);
      v17 = (char *)v49;
      v49[1] = v52;
      v49[2] = v54;
      *v54 = v49 + 1;
      *((_QWORD *)v6 + 6) = v49 + 1;
    }
    else
    {
      WapUriFreeTransformedUri(v49);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)v6 + 1);
    v36 = 0;
  }
LABEL_53:
  for ( j = 0; v20 && j < 8; ++j )
  {
    if ( ((unsigned __int8)(1 << j) & v20) != 0 )
    {
      v20 ^= 1 << j;
      v56 = lpMem[3 * j];
      if ( v56 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(lpMem[3 * j]);
        else
          HeapFree(g_hWxProcessHeap, 0, v56);
        lpMem[3 * j] = 0;
      }
      lpMem[3 * j + 1] = 0;
    }
  }
  if ( !v36 )
  {
    v5 = v80;
    goto LABEL_37;
  }
LABEL_64:
  v4 = v75;
LABEL_65:
  if ( v80 )
    *v80 = 0;
  *v4 = 0;
  return v36;
}

```

## disassembly

```asm
0x18000b6a4  mov     [rsp-8+arg_8], rbx
0x18000b6a9  push    rbp
0x18000b6aa  push    rsi
0x18000b6ab  push    rdi
0x18000b6ac  push    r12
0x18000b6ae  push    r13
0x18000b6b0  push    r14
0x18000b6b2  push    r15
0x18000b6b4  lea     rbp, [rsp-0B0h]
0x18000b6bc  sub     rsp, 1B0h
0x18000b6c3  mov     rax, cs:__security_cookie
0x18000b6ca  xor     rax, rsp
0x18000b6cd  mov     [rbp+0E0h+var_40], rax
0x18000b6d4  xor     eax, eax
0x18000b6d6  mov     [rsp+1E0h+var_180], r9
0x18000b6db  mov     [rbp+0E0h+var_158], r8
0x18000b6df  xorps   xmm0, xmm0
0x18000b6e2  mov     [rsp+1E0h+var_170], rcx
0x18000b6e7  mov     rsi, r9
0x18000b6ea  mov     [rbp+0E0h+var_108], rax
0x18000b6ee  mov     r12, r8
0x18000b6f1  mov     r13, rcx
0x18000b6f4  movups  xmmword ptr [rbp+0E0h+CodePage], xmm0
0x18000b6f8  test    rdx, rdx
0x18000b6fb  jz      loc_18000BE54
0x18000b701  mov     rcx, [rdx]
0x18000b704  movsd   xmm0, cs:qword_1800AD548
0x18000b70c  movsd   [rbp+0E0h+var_108], xmm0
0x18000b711  movups  xmm1, cs:xmmword_1800AD538
0x18000b718  movups  xmmword ptr [rbp+0E0h+CodePage], xmm1
0x18000b71c  mov     qword ptr [rbp+0E0h+CodePage], rcx
0x18000b720  test    ecx, ecx
0x18000b722  jz      loc_18000BD98
0x18000b728  and     ecx, 771h
0x18000b72e  mov     edx, ecx
0x18000b730  mov     [rbp+0E0h+CodePage], ecx
0x18000b733  mov     ebx, ecx
0x18000b735  and     edx, 1
0x18000b738  jz      loc_18000BDE0
0x18000b73e  mov     eax, [rbp+0E0h+CodePage+4]
0x18000b741  mov     edi, ecx
0x18000b743  or      edi, 1
0x18000b746  test    edx, edx
0x18000b748  cmovnz  edi, ecx
0x18000b74b  test    eax, eax
0x18000b74d  jz      loc_18000BE44
0x18000b753  cmp     eax, 0FDE9h
0x18000b758  jnz     loc_18000BDFB
0x18000b75e  lea     rdi, [rbp+0E0h+CodePage]
0x18000b762  mov     rax, [r13+20h]
0x18000b766  and     ebx, 100h
0x18000b76c  neg     ebx
0x18000b76e  mov     qword ptr [rsp+1E0h+var_168], rdi
0x18000b773  sbb     ebx, ebx
0x18000b775  and     ebx, 8000000h
0x18000b77b  add     ebx, 0C000004h
0x18000b781  test    byte ptr [rax+0F0h], 8
0x18000b788  jz      loc_18000BE66
0x18000b78e  lea     rcx, [r13+8]; SRWLock
0x18000b792  call    cs:__imp_AcquireSRWLockShared
0x18000b799  nop     dword ptr [rax+rax+00h]
0x18000b79e  mov     rax, [r13+20h]
0x18000b7a2  lea     r15, [r13+28h]
0x18000b7a6  mov     ecx, ebx
0x18000b7a8  not     ecx
0x18000b7aa  mov     edx, [rax+70h]
0x18000b7ad  and     edx, ecx
0x18000b7af  mov     rcx, [r15]
0x18000b7b2  cmp     rcx, r15
0x18000b7b5  jz      loc_18000BBA4
0x18000b7bb  lea     r14, [rcx-8]
0x18000b7bf  mov     [rbp+0E0h+var_160], rcx
0x18000b7c3  test    byte ptr [r14+0F0h], 8
0x18000b7cb  jnz     loc_18000B9B1
0x18000b7d1  mov     rcx, [rcx]
0x18000b7d4  xor     r14d, r14d
0x18000b7d7  cmp     rcx, r15
0x18000b7da  jnz     short loc_18000B7BB
0x18000b7dc  lea     rcx, [r13+8]; SRWLock
0x18000b7e0  call    cs:__imp_ReleaseSRWLockShared
0x18000b7e7  nop     dword ptr [rax+rax+00h]
0x18000b7ec  test    r14, r14
0x18000b7ef  jnz     loc_18000B9DC
0x18000b7f5  mov     rax, [r13+20h]
0x18000b7f9  xorps   xmm0, xmm0
0x18000b7fc  movups  [rbp+0E0h+var_150], xmm0
0x18000b800  mov     dword ptr [rbp+0E0h+var_150+0Ch], ebx
0x18000b803  xor     bl, bl
0x18000b805  movups  [rbp+0E0h+var_140], xmm0
0x18000b809  xor     edi, edi
0x18000b80b  mov     dl, 8
0x18000b80d  movups  xmm0, xmmword ptr [rax+18h]
0x18000b811  mov     [rsp+1E0h+var_1A0], dl
0x18000b815  xor     r12d, r12d
0x18000b818  movups  xmm1, xmmword ptr [rax+28h]
0x18000b81c  movups  xmmword ptr [rbp+0E0h+lpMem], xmm0
0x18000b820  movups  xmm0, xmmword ptr [rax+38h]
0x18000b824  movups  [rbp+0E0h+var_F0], xmm1
0x18000b828  movups  xmm1, xmmword ptr [rax+48h]
0x18000b82c  movups  [rbp+0E0h+var_E0], xmm0
0x18000b830  movups  xmm0, xmmword ptr [rax+58h]
0x18000b834  movups  [rbp+0E0h+var_D0], xmm1
0x18000b838  movups  xmm1, xmmword ptr [rax+68h]
0x18000b83c  movups  [rbp+0E0h+var_C0], xmm0
0x18000b840  movups  xmm0, xmmword ptr [rax+78h]
0x18000b844  movups  [rbp+0E0h+var_B0], xmm1
0x18000b848  movups  xmm1, xmmword ptr [rax+88h]
0x18000b84f  movups  [rbp+0E0h+var_A0], xmm0
0x18000b853  movups  xmm0, xmmword ptr [rax+98h]
0x18000b85a  movups  [rbp+0E0h+var_90], xmm1
0x18000b85e  movups  xmm1, xmmword ptr [rax+0A8h]
0x18000b865  movups  [rbp+0E0h+var_80], xmm0
0x18000b869  movups  xmm0, xmmword ptr [rax+0B8h]
0x18000b870  movups  [rbp+0E0h+var_70], xmm1
0x18000b874  movups  xmm1, xmmword ptr [rax+0C8h]
0x18000b87b  movups  [rbp+0E0h+var_60], xmm0
0x18000b882  movups  [rbp+0E0h+var_50], xmm1
0x18000b889  mov     [rsp+1E0h+var_190], r12d
0x18000b88e  cmp     r12d, 8
0x18000b892  jge     short loc_18000B8B2
0x18000b894  mov     ecx, r12d
0x18000b897  mov     r15d, 1
0x18000b89d  shl     r15b, cl
0x18000b8a0  mov     byte ptr [rsp+1E0h+var_188], r15b
0x18000b8a5  test    r15b, dl
0x18000b8a8  jnz     short loc_18000B904
0x18000b8aa  test    dl, dl
0x18000b8ac  jnz     loc_18000BF73
0x18000b8b2  test    edi, edi
0x18000b8b4  jnz     loc_18000BB39
0x18000b8ba  mov     r15, [r13+38h]
0x18000b8be  lea     rax, [rsp+1E0h+var_198]
0x18000b8c3  mov     r12, qword ptr [rsp+1E0h+var_168]
0x18000b8c8  lea     r8, [rbp+0E0h+lpMem]; int
0x18000b8cc  mov     [rsp+1E0h+var_1A8], rax; __int64
0x18000b8d1  mov     r9, r12; int
0x18000b8d4  mov     [rsp+1E0h+var_1B0], r14; __int64
0x18000b8d9  mov     dl, 8; int
0x18000b8db  mov     [rsp+1E0h+var_1B8], r14; __int64
0x18000b8e0  mov     rcx, r15; int
0x18000b8e3  mov     [rsp+1E0h+var_1C0], r14; void *
0x18000b8e8  mov     [rsp+1E0h+var_198], r14
0x18000b8ed  call    WapUriRecomposeA
0x18000b8f2  test    eax, eax
0x18000b8f4  jz      loc_18000BA46
0x18000b8fa  mov     edi, 216h
0x18000b8ff  jmp     loc_18000BB39
0x18000b904  movsxd  rcx, r12d
0x18000b907  lea     rsi, [rbp+0E0h+lpMem]
0x18000b90b  xorps   xmm0, xmm0
0x18000b90e  mov     [rsp+1E0h+var_178], rcx
0x18000b913  movups  xmmword ptr [rbp+0E0h+CPInfo], xmm0
0x18000b917  lea     rax, [rcx+rcx*2]
0x18000b91b  lea     rsi, [rsi+rax*8]
0x18000b91f  xor     eax, eax
0x18000b921  mov     qword ptr [rbp+0E0h+CPInfo+10h], rax
0x18000b925  cmp     r12d, 3
0x18000b929  jz      short loc_18000B95C
0x18000b92b  mov     eax, [rsi+10h]
0x18000b92e  xor     dl, r15b
0x18000b931  mov     edi, dword ptr [rbp+rcx*4+0E0h+var_150]
0x18000b935  and     edi, eax
0x18000b937  mov     [rsp+1E0h+var_1A0], dl
0x18000b93b  test    dword ptr [rbp+rcx*4+0E0h+var_150], 1000000h
0x18000b943  mov     [rsp+1E0h+var_18C], eax
0x18000b947  jnz     loc_18000BED0
0x18000b94d  test    edi, edi
0x18000b94f  jnz     loc_18000BA30
0x18000b955  xor     edi, edi
0x18000b957  jmp     loc_18000B8AA
0x18000b95c  mov     eax, [rsi+10h]
0x18000b95f  and     eax, dword ptr [rbp+rcx*4+0E0h+var_150]
0x18000b963  and     eax, 1C000000h
0x18000b968  jz      short loc_18000B92B
0x18000b96a  cmp     eax, 4000000h
0x18000b96f  jz      short loc_18000B987
0x18000b971  cmp     eax, 8000000h
0x18000b976  jz      loc_18000BE70
0x18000b97c  cmp     eax, 10000000h
0x18000b981  jnz     loc_18000BA3C
0x18000b987  test    bl, 8
0x18000b98a  jnz     loc_18000BEA9
0x18000b990  movups  xmm0, xmmword ptr [r13+0C8h]
0x18000b998  movsd   xmm1, qword ptr [r13+0D8h]
0x18000b9a1  movups  xmmword ptr [rsi], xmm0
0x18000b9a4  and     bl, 0F7h
0x18000b9a7  movsd   qword ptr [rsi+10h], xmm1
0x18000b9ac  jmp     loc_18000B92B
0x18000b9b1  cmp     edx, [r14+70h]
0x18000b9b5  jnz     loc_18000B7D1
0x18000b9bb  mov     rax, [rdi]
0x18000b9be  cmp     rax, [r14+0F4h]
0x18000b9c5  jz      loc_18000B7DC
0x18000b9cb  jmp     loc_18000B7D1
0x18000b9d0  test    edi, edi
0x18000b9d2  jnz     loc_18000BBB2
0x18000b9d8  mov     r12, [rbp+0E0h+var_158]
0x18000b9dc  mov     rax, [r14+68h]
0x18000b9e0  cmp     rax, 186A0h
0x18000b9e6  ja      loc_18000BFAB
0x18000b9ec  mov     rcx, [rsp+1E0h+var_180]
0x18000b9f1  mov     [rcx], rax
0x18000b9f4  test    r12, r12
0x18000b9f7  jz      short loc_18000BA01
0x18000b9f9  mov     rax, [r14+60h]
0x18000b9fd  mov     [r12], rax
0x18000ba01  xor     edi, edi
0x18000ba03  mov     eax, edi
0x18000ba05  mov     rcx, [rbp+0E0h+var_40]
0x18000ba0c  xor     rcx, rsp; StackCookie
0x18000ba0f  call    __security_check_cookie
0x18000ba14  mov     rbx, [rsp+1E0h+arg_8]
0x18000ba1c  add     rsp, 1B0h
0x18000ba23  pop     r15
0x18000ba25  pop     r14
0x18000ba27  pop     r13
0x18000ba29  pop     r12
0x18000ba2b  pop     rdi
0x18000ba2c  pop     rsi
0x18000ba2d  pop     rbp
0x18000ba2e  retn
0x18000ba30  test    edi, 202h
0x18000ba36  jz      loc_18000BBD3
0x18000ba3c  mov     edi, 57h ; 'W'
0x18000ba41  jmp     loc_18000BB39
0x18000ba46  mov     rdi, [rsp+1E0h+var_198]
0x18000ba4b  lea     rax, [rdi-1]
0x18000ba4f  cmp     rax, 0C34FFh
0x18000ba55  ja      loc_18000B8FA
0x18000ba5b  lea     rdx, [rdi+110h]
0x18000ba62  call    WxAllocateHeapEx
0x18000ba67  mov     rsi, rax
0x18000ba6a  test    rax, rax
0x18000ba6d  jz      loc_18000BF94
0x18000ba73  xor     eax, eax
0x18000ba75  mov     [rsp+1E0h+var_1A8], r14; __int64
0x18000ba7a  mov     [rsi], rax
0x18000ba7d  lea     rdx, [rsi+18h]
0x18000ba81  mov     dword ptr [rsi], 55495255h
0x18000ba87  lea     rax, [rsi+110h]
0x18000ba8e  mov     byte ptr [rsi+0F0h], 8
0x18000ba95  lea     r8, [rbp+0E0h+lpMem]; int
0x18000ba99  movups  xmm0, xmmword ptr [r12]
0x18000ba9e  mov     [rsp+1E0h+var_1B0], rdi; __int64
0x18000baa3  mov     r9, r12; int
0x18000baa6  mov     [rsp+1E0h+var_1B8], rax; __int64
0x18000baab  mov     rcx, r15; int
0x18000baae  movups  xmmword ptr [rsi+0F4h], xmm0
0x18000bab5  mov     [rsp+1E0h+var_1C0], rdx; void *
0x18000baba  mov     dl, 8; int
0x18000babc  movsd   xmm1, qword ptr [r12+10h]
0x18000bac3  movsd   qword ptr [rsi+104h], xmm1
0x18000bacb  call    WapUriRecomposeA
0x18000bad0  mov     edi, eax
0x18000bad2  test    eax, eax
0x18000bad4  jnz     loc_18000BF9E
0x18000bada  lea     rcx, [r13+8]; SRWLock
0x18000bade  call    cs:__imp_AcquireSRWLockExclusive
0x18000bae5  nop     dword ptr [rax+rax+00h]
0x18000baea  mov     rax, [rbp+0E0h+var_160]
0x18000baee  lea     r15, [r13+28h]
0x18000baf2  test    rax, rax
0x18000baf5  cmovz   rax, r15
0x18000baf9  mov     r11, [rax]
0x18000bafc  cmp     r11, r15
0x18000baff  jnz     loc_18000BCEF
0x18000bb05  mov     rdx, [r15+8]
0x18000bb09  cmp     [rdx], r15
0x18000bb0c  jnz     loc_18000BDA6
0x18000bb12  lea     rax, [rsi+8]
0x18000bb16  mov     r14, rsi
0x18000bb19  mov     [rax], r15
0x18000bb1c  mov     [rax+8], rdx
0x18000bb20  mov     [rdx], rax
0x18000bb23  mov     [r15+8], rax
0x18000bb27  lea     rcx, [r13+8]; SRWLock
0x18000bb2b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bb32  nop     dword ptr [rax+rax+00h]
0x18000bb37  xor     edi, edi
0x18000bb39  xor     esi, esi
0x18000bb3b  test    bl, bl
0x18000bb3d  jz      loc_18000B9D0
0x18000bb43  cmp     esi, 8
0x18000bb46  jge     loc_18000B9D0
0x18000bb4c  mov     ecx, esi
0x18000bb4e  mov     edx, 1
0x18000bb53  shl     dl, cl
0x18000bb55  test    bl, dl
0x18000bb57  jz      short loc_18000BBA0
0x18000bb59  movsxd  rax, esi
0x18000bb5c  xor     bl, dl
0x18000bb5e  lea     r15, [rax+rax*2]
0x18000bb62  mov     r8, [rbp+r15*8+0E0h+lpMem]; lpMem
0x18000bb67  test    r8, r8
0x18000bb6a  jz      short loc_18000BB97
0x18000bb6c  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18000bb73  jnz     loc_18000BDAD
0x18000bb79  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18000bb80  xor     edx, edx; dwFlags
0x18000bb82  call    cs:__imp_HeapFree
  ... truncated ...
```
