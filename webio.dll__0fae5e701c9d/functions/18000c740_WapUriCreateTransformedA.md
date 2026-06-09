# WapUriCreateTransformedA

- ea: `0x18000c740`
- end: `0x18000ce8e`
- name: `WapUriCreateTransformedA`
- size: `1870`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a710`
- `0x18000bfc0`
- `0x18000d710`
- `0x18000d8f0`

## callees

- `0x18000c740`
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

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c935`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c984`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca9b`

## pseudocode

```c
__int64 __fastcall WapUriCreateTransformedA(
        RTL_SRWLOCK *a1,
        unsigned __int8 a2,
        __int64 a3,
        _QWORD *a4,
        RTL_SRWLOCK *a5,
        RTL_SRWLOCK **a6)
{
  unsigned __int8 v6; // bl
  char *Ptr; // rax
  _QWORD *v8; // r12
  RTL_SRWLOCK *v10; // r9
  unsigned __int8 v11; // r15
  signed int v12; // r14d
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  unsigned __int8 v24; // r12
  PVOID v25; // r15
  __int64 v26; // rcx
  __int64 v27; // r14
  __int64 v28; // rax
  RTL_SRWLOCK *v29; // rsi
  unsigned int v30; // r13d
  RTL_SRWLOCK *v31; // rax
  RTL_SRWLOCK *v32; // r14
  RTL_SRWLOCK **v33; // r15
  RTL_SRWLOCK **v34; // rcx
  RTL_SRWLOCK *v35; // r14
  int *v36; // rcx
  int v37; // r13d
  int *v38; // rdx
  int v39; // esi
  int v40; // eax
  PVOID v41; // xmm1_8
  int j; // edi
  void *v43; // r8
  int *v44; // rsi
  unsigned __int64 v46; // rdx
  __int64 v47; // rcx
  unsigned int v48; // eax
  int *v49; // r13
  __int64 v50; // xmm1_8
  RTL_SRWLOCK *v51; // rax
  RTL_SRWLOCK *v52; // r13
  unsigned __int8 v53; // r11
  int i; // r9d
  unsigned __int64 v55; // rax
  PVOID v56; // xmm1_8
  unsigned __int64 PercentEncodeLength; // rax
  unsigned __int64 v58; // [rsp+40h] [rbp-C0h]
  __int64 *v59; // [rsp+48h] [rbp-B8h]
  int v60; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+60h] [rbp-A0h]
  void *Heap; // [rsp+70h] [rbp-90h]
  __int128 v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  _QWORD *v66; // [rsp+90h] [rbp-70h]
  RTL_SRWLOCK **v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  int v70[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-40h]
  __int128 v72; // [rsp+D0h] [rbp-30h]
  __int128 v73; // [rsp+E0h] [rbp-20h]
  __int128 v74; // [rsp+F0h] [rbp-10h]
  __int128 v75; // [rsp+100h] [rbp+0h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  __int128 v77; // [rsp+120h] [rbp+20h]
  __int128 v78; // [rsp+130h] [rbp+30h]
  __int128 v79; // [rsp+140h] [rbp+40h]
  __int128 v80; // [rsp+150h] [rbp+50h]
  __int128 v81; // [rsp+160h] [rbp+60h]

  v67 = a6;
  v6 = 0;
  Ptr = (char *)a1[4].Ptr;
  v8 = a4;
  v66 = a4;
  v62 = a3;
  v10 = a1;
  v11 = a2;
  v12 = 0;
  v13 = *(_OWORD *)(Ptr + 40);
  *(_OWORD *)v70 = *(_OWORD *)(Ptr + 24);
  v14 = *(_OWORD *)(Ptr + 56);
  v71 = v13;
  v15 = *(_OWORD *)(Ptr + 72);
  v72 = v14;
  v16 = *(_OWORD *)(Ptr + 88);
  v73 = v15;
  v17 = *(_OWORD *)(Ptr + 104);
  v74 = v16;
  v18 = *(_OWORD *)(Ptr + 120);
  v75 = v17;
  v19 = *(_OWORD *)(Ptr + 136);
  v76 = v18;
  v20 = *(_OWORD *)(Ptr + 152);
  v77 = v19;
  v21 = *(_OWORD *)(Ptr + 168);
  v78 = v20;
  v22 = *(_OWORD *)(Ptr + 184);
  v79 = v21;
  v23 = *(_OWORD *)(Ptr + 200);
  v80 = v22;
  v81 = v23;
  if ( a2 )
  {
    while ( 1 )
    {
      if ( v12 >= 8 )
      {
LABEL_5:
        v8 = v66;
        break;
      }
      v24 = 1 << v12;
      if ( ((unsigned __int8)(1 << v12) & v11) != 0 )
      {
        v36 = (int *)v12;
        v37 = *(_DWORD *)(a3 + 4LL * v12);
        v64 = 0;
        v38 = &v70[6 * v12];
        v59 = (__int64 *)v38;
        v69 = 4LL * v12;
        v65 = 0;
        if ( v12 == 3 )
        {
          v40 = v37 & v38[4] & 0x1C000000;
          if ( v40 )
          {
            if ( v40 == 0x10000000 || v40 == 0x4000000 )
            {
              if ( (v6 & 8) != 0 && *(_QWORD *)v38 )
              {
                v68 = *(_QWORD *)v38;
                WxFreeHeapEx(&v68);
                v38 = &v70[6 * v12];
                a3 = v62;
                v10 = a1;
              }
              v6 &= ~8u;
              v41 = v10[27].Ptr;
              *(_OWORD *)v38 = *(_OWORD *)&v10[25].Ptr;
              *((_QWORD *)v38 + 2) = v41;
            }
            else
            {
              if ( v40 != 0x8000000 || !v10[29].Ptr )
                goto LABEL_26;
              if ( (v6 & 8) != 0 && *(_QWORD *)v38 )
              {
                v68 = *(_QWORD *)v38;
                WxFreeHeapEx(&v68);
                v38 = &v70[6 * v12];
                a3 = v62;
                v10 = a1;
              }
              v6 &= ~8u;
              v56 = v10[30].Ptr;
              *(_OWORD *)v38 = *(_OWORD *)&v10[28].Ptr;
              *((_QWORD *)v38 + 2) = v56;
            }
          }
        }
        v11 ^= 1 << v12;
        v60 = v38[4];
        v39 = v37 & v60;
        if ( (v37 & 0x1000000) != 0 && (v60 & 0xE003FE08) != 0 )
          v39 |= 0x1000008u;
        if ( v39 )
        {
          if ( (v39 & 0x202) != 0 || ((unsigned __int8)v39 & BYTE1(v39) & 0xF8) != 0 )
            goto LABEL_26;
          if ( (v39 & 0xF8) != 0 )
          {
            PercentEncodeLength = WapUriGetPercentEncodeLength(v12, v39, (__int64 *)v38);
            v36 = &v70[6 * v12];
            v46 = PercentEncodeLength;
            v68 = PercentEncodeLength;
            v58 = v59[1];
            if ( PercentEncodeLength < v58 )
              goto LABEL_38;
          }
          else
          {
            v46 = *((_QWORD *)v38 + 1);
            v68 = v46;
            v58 = v46;
          }
          if ( v46 - 1 > 0x1869F )
            goto LABEL_26;
          if ( 2 * v46 < v46 )
            goto LABEL_94;
          Heap = (void *)WxAllocateHeapEx(v36, 2 * v46);
          v47 = (__int64)Heap;
          if ( !Heap )
            goto LABEL_94;
          if ( (v39 & 0xE003FFFF) != 0 )
          {
            if ( (v37 & 4) != 0 )
            {
              if ( (v37 & 0x40000000) != 0 )
              {
                v30 = 87;
LABEL_71:
                v69 = v47;
                WxFreeHeapEx(&v69);
LABEL_27:
                v35 = 0;
                goto LABEL_28;
              }
              v39 |= 4u;
            }
            v48 = WapUriTransformIriComponentCharacters(v12, v39, *v59, v58, (__int64)Heap, v68, (_QWORD *)&v64 + 1);
            if ( v48 )
            {
              v47 = (__int64)Heap;
              v30 = v48;
              goto LABEL_71;
            }
            *(_QWORD *)&v64 = Heap;
            WapUriUpdateIriComponentEncodedFlags((unsigned int)v12, &v64);
            LODWORD(v65) = v60 & 0x1DFC0000 | v65 & *(int *)((char *)dword_18009D088 + v69);
            v39 = v37 & v65;
            v49 = &v70[6 * v12];
          }
          else
          {
            v49 = &v70[6 * v12];
            memcpy_0(Heap, (const void *)*v59, 2 * v58);
            *(_QWORD *)&v64 = Heap;
            *((_QWORD *)&v64 + 1) = v58;
            LODWORD(v65) = v60;
          }
          if ( (v24 & v6) != 0 && *(_QWORD *)v49 )
          {
            v69 = *(_QWORD *)v49;
            WxFreeHeapEx(&v69);
          }
          v6 |= v24;
          v50 = v65;
          *(_OWORD *)v49 = v64;
          *((_QWORD *)v49 + 2) = v50;
          if ( v12 == 5 )
          {
            v30 = WapUriTransformPath((__int64)v49, v39);
            if ( v30 )
              goto LABEL_27;
          }
          a3 = v62;
          v10 = a1;
        }
      }
      if ( !v11 )
        goto LABEL_5;
      ++v12;
    }
  }
  if ( !v8 )
  {
LABEL_26:
    v30 = 87;
    goto LABEL_27;
  }
  v25 = v10[7].Ptr;
  v68 = 0;
  if ( (unsigned int)WapUriRecomposeA((int)v25, a2, (int)v70, (int)v8, 0, 0, 0, (__int64)&v68)
    || (v27 = v68, (unsigned __int64)(v68 - 1) > 0xC34FF) )
  {
LABEL_38:
    v30 = 534;
    goto LABEL_27;
  }
  v28 = WxAllocateHeapEx(v26, v68 + 272);
  v29 = (RTL_SRWLOCK *)v28;
  if ( !v28 )
  {
LABEL_94:
    v30 = 8;
    goto LABEL_27;
  }
  *(_QWORD *)v28 = 0;
  *(_DWORD *)v28 = 1430868565;
  *(_BYTE *)(v28 + 240) = a2;
  *(_OWORD *)(v28 + 244) = *(_OWORD *)v8;
  *(_QWORD *)(v28 + 260) = v8[2];
  v30 = WapUriRecomposeA((int)v25, a2, (int)v70, (int)v8, (void *)(v28 + 24), v28 + 272, v27, 0);
  if ( v30 )
  {
    WapUriFreeTransformedUri(v29);
    goto LABEL_27;
  }
  AcquireSRWLockExclusive(a1 + 1);
  v31 = a5;
  v32 = a1 + 5;
  if ( !a5 )
    v31 = a1 + 5;
  v33 = (RTL_SRWLOCK **)v31->Ptr;
  if ( v31->Ptr == v32 )
  {
LABEL_14:
    v34 = (RTL_SRWLOCK **)a1[6].Ptr;
    if ( *v34 != v32 )
      __fastfail(3u);
    v29[1].Ptr = v32;
    v29[2].Ptr = v34;
    *v34 = v29 + 1;
    a1[6].Ptr = &v29[1];
    v35 = v29;
  }
  else
  {
    v51 = (RTL_SRWLOCK *)v31->Ptr;
    while ( 1 )
    {
      v52 = v51 - 1;
      if ( LOBYTE(v51[29].Ptr) == a2 )
      {
        v53 = a2;
        for ( i = 0; v53 && i < 8; ++i )
        {
          if ( ((unsigned __int8)(1 << i) & v53) != 0 )
          {
            if ( (*((_DWORD *)a1[4].Ptr + 6 * i + 10) & ~*(_DWORD *)(v62 + 4LL * i)) != LODWORD(v52[3 * i + 5].Ptr) )
              goto LABEL_68;
            v53 ^= 1 << i;
          }
        }
        v55 = *v66 - *(unsigned __int64 *)((char *)&v52[30].Ptr + 4);
        if ( (PVOID)*v66 == *(PVOID *)((char *)&v52[30].Ptr + 4) )
        {
          v55 = v66[1] - *(unsigned __int64 *)((char *)&v52[31].Ptr + 4);
          if ( !v55 )
            v55 = v66[2] - *(unsigned __int64 *)((char *)&v52[32].Ptr + 4);
        }
        if ( !v55 )
          break;
      }
LABEL_68:
      v51 = *v33;
      v33 = (RTL_SRWLOCK **)v51;
      if ( v51 == v32 )
        goto LABEL_14;
    }
    WapUriFreeTransformedUri(v29);
    v35 = v52;
  }
  ReleaseSRWLockExclusive(a1 + 1);
  v30 = 0;
LABEL_28:
  for ( j = 0; v6; ++j )
  {
    if ( j >= 8 )
      break;
    if ( ((unsigned __int8)(1 << j) & v6) != 0 )
    {
      v6 ^= 1 << j;
      v43 = *(void **)&v70[6 * j];
      v44 = &v70[6 * j];
      if ( v43 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(*(_QWORD *)&v70[6 * j]);
        else
          HeapFree(g_hWxProcessHeap, 0, v43);
        *(_QWORD *)v44 = 0;
      }
      *((_QWORD *)v44 + 1) = 0;
    }
  }
  *v67 = v35;
  return v30;
}

```

## disassembly

```asm
0x18000c740  push    rbp
0x18000c742  push    rbx
0x18000c743  push    rsi
0x18000c744  push    rdi
0x18000c745  push    r12
0x18000c747  push    r13
0x18000c749  push    r14
0x18000c74b  push    r15
0x18000c74d  lea     rbp, [rsp-88h]
0x18000c755  sub     rsp, 188h
0x18000c75c  mov     rax, cs:__security_cookie
0x18000c763  xor     rax, rsp
0x18000c766  mov     [rbp+0C0h+var_50], rax
0x18000c76a  mov     rax, [rbp+0C0h+arg_28]
0x18000c771  xor     r10d, r10d
0x18000c774  mov     [rbp+0C0h+var_128], rax
0x18000c778  xor     bl, bl
0x18000c77a  mov     rax, [rcx+20h]
0x18000c77e  mov     r12, r9
0x18000c781  mov     [rbp+0C0h+var_130], r9
0x18000c785  movzx   edi, dl
0x18000c788  mov     [rsp+1C0h+var_160], r8
0x18000c78d  mov     r9, rcx
0x18000c790  mov     [rsp+1C0h+var_168], rcx
0x18000c795  mov     r13d, r10d
0x18000c798  mov     [rsp+1C0h+var_158], r10
0x18000c79d  movzx   r15d, dl
0x18000c7a1  mov     r14d, r10d
0x18000c7a4  movups  xmm0, xmmword ptr [rax+18h]
0x18000c7a8  movups  xmm1, xmmword ptr [rax+28h]
0x18000c7ac  movups  xmmword ptr [rbp+0C0h+var_110], xmm0
0x18000c7b0  movups  xmm0, xmmword ptr [rax+38h]
0x18000c7b4  movups  [rbp+0C0h+var_100], xmm1
0x18000c7b8  movups  xmm1, xmmword ptr [rax+48h]
0x18000c7bc  movups  [rbp+0C0h+var_F0], xmm0
0x18000c7c0  movups  xmm0, xmmword ptr [rax+58h]
0x18000c7c4  movups  [rbp+0C0h+var_E0], xmm1
0x18000c7c8  movups  xmm1, xmmword ptr [rax+68h]
0x18000c7cc  movups  [rbp+0C0h+var_D0], xmm0
0x18000c7d0  movups  xmm0, xmmword ptr [rax+78h]
0x18000c7d4  movups  [rbp+0C0h+var_C0], xmm1
0x18000c7d8  movups  xmm1, xmmword ptr [rax+88h]
0x18000c7df  movups  [rbp+0C0h+var_B0], xmm0
0x18000c7e3  movups  xmm0, xmmword ptr [rax+98h]
0x18000c7ea  movups  [rbp+0C0h+var_A0], xmm1
0x18000c7ee  movups  xmm1, xmmword ptr [rax+0A8h]
0x18000c7f5  movups  [rbp+0C0h+var_90], xmm0
0x18000c7f9  movups  xmm0, xmmword ptr [rax+0B8h]
0x18000c800  movups  [rbp+0C0h+var_80], xmm1
0x18000c804  movups  xmm1, xmmword ptr [rax+0C8h]
0x18000c80b  movups  [rbp+0C0h+var_70], xmm0
0x18000c80f  movups  [rbp+0C0h+var_60], xmm1
0x18000c813  test    dl, dl
0x18000c815  jz      short loc_18000C84B
0x18000c817  cmp     r14d, 8
0x18000c81b  jge     short loc_18000C83E
0x18000c81d  mov     ecx, r14d
0x18000c820  mov     esi, 1
0x18000c825  shl     sil, cl
0x18000c828  movzx   r12d, sil
0x18000c82c  test    r15b, sil
0x18000c82f  jnz     loc_18000C99B
0x18000c835  test    r15b, r15b
0x18000c838  jnz     loc_18000CE63
0x18000c83e  test    r13d, r13d
0x18000c841  jnz     loc_18000CA4A
0x18000c847  mov     r12, [rbp+0C0h+var_130]
0x18000c84b  test    r12, r12
0x18000c84e  jz      loc_18000CA44
0x18000c854  mov     r15, [r9+38h]
0x18000c858  lea     rax, [rbp+0C0h+var_120]
0x18000c85c  mov     [rsp+1C0h+var_188], rax; __int64
0x18000c861  lea     r8, [rbp+0C0h+var_110]; int
0x18000c865  mov     [rsp+1C0h+var_190], r10; __int64
0x18000c86a  mov     r9, r12; int
0x18000c86d  mov     [rsp+1C0h+var_198], r10; __int64
0x18000c872  movzx   edx, dil; int
0x18000c876  mov     rcx, r15; int
0x18000c879  mov     [rsp+1C0h+var_1A0], r10; void *
0x18000c87e  mov     [rbp+0C0h+var_120], r10
0x18000c882  call    WapUriRecomposeA
0x18000c887  test    eax, eax
0x18000c889  jnz     loc_18000CADF
0x18000c88f  mov     r14, [rbp+0C0h+var_120]
0x18000c893  lea     rax, [r14-1]
0x18000c897  cmp     rax, 0C34FFh
0x18000c89d  ja      loc_18000CADF
0x18000c8a3  lea     rdx, [r14+110h]
0x18000c8aa  call    WxAllocateHeapEx
0x18000c8af  mov     rsi, rax
0x18000c8b2  test    rax, rax
0x18000c8b5  jz      loc_18000CE76
0x18000c8bb  xor     eax, eax
0x18000c8bd  mov     [rsp+1C0h+var_188], 0; __int64
0x18000c8c6  mov     [rsi], rax
0x18000c8c9  lea     rdx, [rsi+18h]
0x18000c8cd  mov     dword ptr [rsi], 55495255h
0x18000c8d3  lea     rax, [rsi+110h]
0x18000c8da  mov     [rsi+0F0h], dil
0x18000c8e1  lea     r8, [rbp+0C0h+var_110]; int
0x18000c8e5  movups  xmm0, xmmword ptr [r12]
0x18000c8ea  mov     [rsp+1C0h+var_190], r14; __int64
0x18000c8ef  mov     r9, r12; int
0x18000c8f2  mov     [rsp+1C0h+var_198], rax; __int64
0x18000c8f7  mov     rcx, r15; int
0x18000c8fa  movups  xmmword ptr [rsi+0F4h], xmm0
0x18000c901  mov     [rsp+1C0h+var_1A0], rdx; void *
0x18000c906  movzx   edx, dil; int
0x18000c90a  movsd   xmm1, qword ptr [r12+10h]
0x18000c911  movsd   qword ptr [rsi+104h], xmm1
0x18000c919  call    WapUriRecomposeA
0x18000c91e  mov     r13d, eax
0x18000c921  test    eax, eax
0x18000c923  jnz     loc_18000CE81
0x18000c929  mov     r14, [rsp+1C0h+var_168]
0x18000c92e  lea     r12, [r14+8]
0x18000c932  mov     rcx, r12; SRWLock
0x18000c935  call    cs:__imp_AcquireSRWLockExclusive
0x18000c93c  nop     dword ptr [rax+rax+00h]
0x18000c941  mov     rax, [rbp+0C0h+arg_20]
0x18000c948  add     r14, 28h ; '('
0x18000c94c  test    rax, rax
0x18000c94f  cmovz   rax, r14
0x18000c953  mov     r15, [rax]
0x18000c956  cmp     r15, r14
0x18000c959  jnz     loc_18000CC17
0x18000c95f  mov     rcx, [r14+8]
0x18000c963  cmp     [rcx], r14
0x18000c966  jnz     loc_18000CCF1
0x18000c96c  lea     rax, [rsi+8]
0x18000c970  mov     [rax], r14
0x18000c973  mov     [rax+8], rcx
0x18000c977  mov     [rcx], rax
0x18000c97a  mov     [r14+8], rax
0x18000c97e  mov     r14, rsi
0x18000c981  mov     rcx, r12; SRWLock
0x18000c984  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c98b  nop     dword ptr [rax+rax+00h]
0x18000c990  xor     r15d, r15d
0x18000c993  mov     r13d, r15d
0x18000c996  jmp     loc_18000CA52
0x18000c99b  movsxd  rcx, r14d
0x18000c99e  lea     rdx, [rbp+0C0h+var_110]
0x18000c9a2  mov     r13d, [r8+rcx*4]
0x18000c9a6  xorps   xmm0, xmm0
0x18000c9a9  movups  [rsp+1C0h+var_148], xmm0
0x18000c9ae  lea     rax, [rcx+rcx*2]
0x18000c9b2  lea     rdx, [rdx+rax*8]
0x18000c9b6  lea     rax, ds:0[rcx*4]
0x18000c9be  mov     [rsp+1C0h+var_178], rdx
0x18000c9c3  mov     [rbp+0C0h+var_118], rax
0x18000c9c7  xor     eax, eax
0x18000c9c9  mov     [rbp+0C0h+var_138], rax
0x18000c9cd  cmp     r14d, 3
0x18000c9d1  jz      short loc_18000C9F9
0x18000c9d3  mov     eax, [rdx+10h]
0x18000c9d6  xor     r15b, sil
0x18000c9d9  mov     esi, eax
0x18000c9db  mov     [rsp+1C0h+var_170], eax
0x18000c9df  and     esi, r13d
0x18000c9e2  bt      r13d, 18h
0x18000c9e7  jb      loc_18000CDAF
0x18000c9ed  test    esi, esi
0x18000c9ef  jnz     short loc_18000CA38
0x18000c9f1  mov     r13d, r10d
0x18000c9f4  jmp     loc_18000C835
0x18000c9f9  mov     eax, [rdx+10h]
0x18000c9fc  and     eax, r13d
0x18000c9ff  and     eax, 1C000000h
0x18000ca04  jz      short loc_18000C9D3
0x18000ca06  cmp     eax, 10000000h
0x18000ca0b  jnz     loc_18000CCF8
0x18000ca11  test    bl, 8
0x18000ca14  jnz     loc_18000CD7F
0x18000ca1a  movups  xmm0, xmmword ptr [r9+0C8h]
0x18000ca22  and     bl, 0F7h
0x18000ca25  movsd   xmm1, qword ptr [r9+0D8h]
0x18000ca2e  movups  xmmword ptr [rdx], xmm0
0x18000ca31  movsd   qword ptr [rdx+10h], xmm1
0x18000ca36  jmp     short loc_18000C9D3
0x18000ca38  test    esi, 202h
0x18000ca3e  jz      loc_18000CAEA
0x18000ca44  mov     r13d, 57h ; 'W'
0x18000ca4a  mov     r14, [rsp+1C0h+var_158]
0x18000ca4f  xor     r15d, r15d
0x18000ca52  mov     edi, r15d
0x18000ca55  test    bl, bl
0x18000ca57  jz      short loc_18000CAB4
0x18000ca59  cmp     edi, 8
0x18000ca5c  jge     short loc_18000CAB4
0x18000ca5e  mov     ecx, edi
0x18000ca60  mov     edx, 1
0x18000ca65  shl     dl, cl
0x18000ca67  test    bl, dl
0x18000ca69  jz      short loc_18000CAAE
0x18000ca6b  movsxd  rax, edi
0x18000ca6e  lea     rsi, [rbp+0C0h+var_110]
0x18000ca72  xor     bl, dl
0x18000ca74  lea     rcx, [rax+rax*2]
0x18000ca78  mov     r8, [rsi+rcx*8]; lpMem
0x18000ca7c  lea     rsi, [rsi+rcx*8]
0x18000ca80  test    r8, r8
0x18000ca83  jz      short loc_18000CAAA
0x18000ca85  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18000ca8c  jnz     loc_18000CD42
0x18000ca92  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18000ca99  xor     edx, edx; dwFlags
0x18000ca9b  call    cs:__imp_HeapFree
0x18000caa2  nop     dword ptr [rax+rax+00h]
0x18000caa7  mov     [rsi], r15
0x18000caaa  mov     [rsi+8], r15
0x18000caae  inc     edi
0x18000cab0  test    bl, bl
0x18000cab2  jnz     short loc_18000CA59
0x18000cab4  mov     rax, [rbp+0C0h+var_128]
0x18000cab8  mov     [rax], r14
0x18000cabb  mov     eax, r13d
0x18000cabe  mov     rcx, [rbp+0C0h+var_50]
0x18000cac2  xor     rcx, rsp; StackCookie
0x18000cac5  call    __security_check_cookie
0x18000caca  add     rsp, 188h
0x18000cad1  pop     r15
0x18000cad3  pop     r14
0x18000cad5  pop     r13
0x18000cad7  pop     r12
0x18000cad9  pop     rdi
0x18000cada  pop     rsi
0x18000cadb  pop     rbx
0x18000cadc  pop     rbp
0x18000cadd  retn
0x18000cadf  mov     r13d, 216h
0x18000cae5  jmp     loc_18000CA4A
0x18000caea  mov     eax, esi
0x18000caec  shr     eax, 8
0x18000caef  and     eax, esi
0x18000caf1  test    al, 0F8h
0x18000caf3  jnz     loc_18000CA44
0x18000caf9  test    sil, 0F8h
0x18000cafd  jnz     loc_18000CDC5
0x18000cb03  mov     rdx, [rdx+8]
0x18000cb07  mov     [rbp+0C0h+var_120], rdx
0x18000cb0b  mov     [rsp+1C0h+var_180], rdx
0x18000cb10  lea     rax, [rdx-1]
0x18000cb14  cmp     rax, 1869Fh
0x18000cb1a  ja      loc_18000CA44
0x18000cb20  lea     rax, [rdx+rdx]
0x18000cb24  cmp     rax, rdx
0x18000cb27  jb      loc_18000CE76
0x18000cb2d  mov     rdx, rax
0x18000cb30  call    WxAllocateHeapEx
0x18000cb35  mov     [rsp+1C0h+var_150], rax
0x18000cb3a  mov     rcx, rax; void *
0x18000cb3d  test    rax, rax
0x18000cb40  jz      loc_18000CE76
0x18000cb46  test    esi, 0E003FFFFh
0x18000cb4c  jz      loc_18000CDF5
0x18000cb52  test    r13b, 4
0x18000cb56  jz      short loc_18000CB66
0x18000cb58  bt      r13d, 1Eh
0x18000cb5d  jb      loc_18000CE6B
0x18000cb63  or      esi, 4
0x18000cb66  mov     rax, [rsp+1C0h+var_178]
0x18000cb6b  mov     edx, esi
0x18000cb6d  mov     r9, [rsp+1C0h+var_180]
0x18000cb72  mov     r8, [rax]
0x18000cb75  lea     rax, [rbp+0C0h+var_148+8]
0x18000cb79  mov     [rsp+1C0h+var_190], rax
0x18000cb7e  mov     rax, [rbp+0C0h+var_120]
0x18000cb82  mov     [rsp+1C0h+var_198], rax
0x18000cb87  mov     [rsp+1C0h+var_1A0], rcx
0x18000cb8c  mov     ecx, r14d
0x18000cb8f  call    WapUriTransformIriComponentCharacters
0x18000cb94  test    eax, eax
0x18000cb96  jnz     loc_18000CCD7
0x18000cb9c  mov     rax, [rsp+1C0h+var_150]
0x18000cba1  lea     rdx, [rsp+1C0h+var_148]
0x18000cba6  mov     ecx, r14d
0x18000cba9  mov     qword ptr [rsp+1C0h+var_148], rax
0x18000cbae  call    WapUriUpdateIriComponentEncodedFlags
0x18000cbb3  mov     rsi, [rbp+0C0h+var_118]
0x18000cbb7  lea     rax, dword_18009D088
0x18000cbbe  mov     esi, [rsi+rax]
0x18000cbc1  and     esi, dword ptr [rbp+0C0h+var_138]
0x18000cbc4  mov     eax, [rsp+1C0h+var_170]
0x18000cbc8  and     eax, 1DFC0000h
0x18000cbcd  or      esi, eax
0x18000cbcf  mov     dword ptr [rbp+0C0h+var_138], esi
0x18000cbd2  and     esi, r13d
0x18000cbd5  mov     r13, [rsp+1C0h+var_178]
0x18000cbda  test    bl, r12b
0x18000cbdd  jnz     loc_18000CE2A
0x18000cbe3  movups  xmm0, [rsp+1C0h+var_148]
0x18000cbe8  or      bl, r12b
0x18000cbeb  movsd   xmm1, [rbp+0C0h+var_138]
0x18000cbf0  movups  xmmword ptr [r13+0], xmm0
0x18000cbf5  movsd   qword ptr [r13+10h], xmm1
0x18000cbfb  cmp     r14d, 5
0x18000cbff  jz      loc_18000CE49
0x18000cc05  mov     r8, [rsp+1C0h+var_160]
0x18000cc0a  xor     r10d, r10d
  ... truncated ...
```
