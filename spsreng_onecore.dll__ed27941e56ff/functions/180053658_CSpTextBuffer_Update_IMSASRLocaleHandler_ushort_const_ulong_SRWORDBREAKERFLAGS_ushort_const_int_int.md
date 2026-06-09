# CSpTextBuffer::Update(IMSASRLocaleHandler *,ushort const *,ulong,SRWORDBREAKERFLAGS,ushort const *,int,int)

- ea: `0x180053658`
- end: `0x180053be7`
- name: `?Update@CSpTextBuffer@@QEAAJPEAUIMSASRLocaleHandler@@PEBGKW4SRWORDBREAKERFLAGS@@1HH@Z`
- size: `1423`
- prototype: `__int64 __fastcall(__int64, struct IMSASRLocaleHandler *, _WORD *, int, int, unsigned __int16 *, __int64, int)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011660`
- `0x180013110`
- `0x180051e44`
- `0x18005d560`

## callees

- `0x180004312`
- `0x18001474c`
- `0x18004c4d8`
- `0x18004c544`
- `0x1800529dc`
- `0x180052abc`
- `0x180053108`
- `0x180053658`
- `0x180053bf0`
- `0x180053c74`
- `0x180053e04`
- `0x1800ff514`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053b04`

## pseudocode

```c
__int64 __fastcall CSpTextBuffer::Update(
        __int64 a1,
        struct IMSASRLocaleHandler *a2,
        _WORD *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        __int64 a7,
        int a8)
{
  __int64 v8; // rsi
  struct IMSASRLocaleHandler *v10; // r12
  int v13; // edi
  int v14; // ecx
  char *v15; // r14
  char *v16; // rax
  unsigned int v17; // r13d
  int v18; // eax
  int v19; // r8d
  __int64 *v20; // r12
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 *v29; // r12
  unsigned int i; // r10d
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // eax
  __int64 v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rax
  void *v43; // rcx
  int v44; // edx
  unsigned __int16 *v45; // rax
  void *Src[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v47; // [rsp+58h] [rbp-28h]
  LPVOID pv[3]; // [rsp+68h] [rbp-18h]
  int v50; // [rsp+D8h] [rbp+58h] BYREF

  LODWORD(v8) = a4;
  v10 = a2;
  *(_OWORD *)Src = 0;
  v47 = 0;
  *(_OWORD *)pv = 0;
  if ( a4 == -1 )
  {
    if ( a3 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
    }
    else
    {
      LODWORD(v8) = 0;
    }
  }
  if ( *(_BYTE *)(a1 + 24)
    && *(_DWORD *)(a1 + 40) == (_DWORD)v8
    && !memcmp_0(*(const void **)(a1 + 32), a3, 2LL * (unsigned int)v8) )
  {
    return 1;
  }
  v13 = 0;
  CSpTextBuffer::PartialReset((CSpTextBuffer *)a1);
  if ( a3 && (_DWORD)v8 )
  {
    v14 = 0;
    a5 = 0;
    v15 = (char *)a3;
    *(_OWORD *)Src = 0;
    v16 = (char *)&a3[(unsigned int)v8];
    v17 = 0;
    *(_DWORD *)(a1 + 16) = 0;
    *(_DWORD *)(a1 + 56) = 0;
    *(_WORD *)(a1 + 24) = 0;
    v47 = 0;
    *(_OWORD *)pv = 0;
    while ( v15 < v16 )
    {
      v50 = (v16 - v15) >> 1;
      v18 = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, char *, int *))(*(_QWORD *)v10 + 72LL))(
              v10,
              v15,
              &v50);
      if ( v18 == 1 )
      {
        v19 = *(_DWORD *)(a1 + 16);
        if ( v19 )
        {
          v20 = (__int64 *)(a1 + 8);
          if ( (*(_BYTE *)(*(_QWORD *)(a1 + 8) + 24LL * (unsigned int)(v19 - 1) + 4) & 2) == 0 )
          {
            v13 = EnsureArrayVoid(
                    (void **)(a1 + 8),
                    0x18u,
                    v19 + 1,
                    (unsigned int *)(a1 + 20),
                    0x64u,
                    (struct CHeap *)&g_heap);
            if ( v13 < 0 )
              return (unsigned int)v13;
            v21 = 3LL * *(unsigned int *)(a1 + 16);
            v22 = *v20;
            *(_OWORD *)(v22 + 8 * v21) = 0;
            *(_QWORD *)(v22 + 8 * v21 + 16) = 0;
            *(_DWORD *)(*v20 + 24LL * *(unsigned int *)(a1 + 16)) = *(_DWORD *)(a1 + 56);
            v23 = *v20;
            v24 = 3LL * *(unsigned int *)(a1 + 16);
            *(_DWORD *)(v23 + 8 * v24 + 4) &= 0x1Fu;
            *(_DWORD *)(v23 + 8 * v24 + 4) |= 32 * ((v15 - (char *)a3) >> 1);
            v25 = 3LL * *(unsigned int *)(a1 + 16);
            v26 = *v20;
            *(_DWORD *)(v26 + 8 * v25 + 8) &= 3u;
            *(_DWORD *)(v26 + 8 * v25 + 8) |= 4u;
            *(_DWORD *)(*v20 + 24LL * (unsigned int)(*(_DWORD *)(a1 + 16))++ + 4) |= 2u;
          }
          v10 = a2;
        }
        v14 = a5;
        v15 += 2;
      }
      else
      {
        if ( v18 < 0 )
          goto LABEL_47;
        v27 = 14;
        if ( !*(_DWORD *)(a1 + 4) )
          v27 = 6;
        v28 = *(_QWORD *)v10;
        v18 = a8
            ? (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, char *, _QWORD, __int64, void **))(v28 + 216))(
                v10,
                v15,
                (unsigned int)v50,
                v27,
                Src)
            : (*(unsigned __int64 (__fastcall **)(struct IMSASRLocaleHandler *, char *, _QWORD, __int64, void **))(v28 + 80))(
                v10,
                v15,
                (unsigned int)v50,
                v27,
                Src);
        if ( v18 < 0 )
        {
LABEL_47:
          v14 = v18;
          a5 = v18;
        }
        else
        {
          if ( LODWORD(Src[0]) )
          {
            v29 = (__int64 *)(a1 + 8);
            v13 = EnsureArrayVoid(
                    (void **)(a1 + 8),
                    0x18u,
                    LODWORD(Src[0]) + *(_DWORD *)(a1 + 16),
                    (unsigned int *)(a1 + 20),
                    0x64u,
                    (struct CHeap *)&g_heap);
            if ( v13 < 0 )
              return (unsigned int)v13;
            for ( i = 0; i < LODWORD(Src[0]); ++i )
            {
              v31 = 3LL * *(unsigned int *)(a1 + 16);
              v32 = *v29;
              *(_OWORD *)(v32 + 8 * v31) = 0;
              *(_QWORD *)(v32 + 8 * v31 + 16) = 0;
              *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16)) = -1;
              v33 = *v29;
              v34 = 3LL * *(unsigned int *)(a1 + 16);
              *(_DWORD *)(v33 + 8 * v34 + 4) &= 0x1Fu;
              *(_DWORD *)(v33 + 8 * v34 + 4) |= 32 * ((v15 - (char *)a3) >> 1);
              if ( pv[0] )
              {
                v35 = *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) + 32 * *((_DWORD *)pv[0] + 3 * i);
                *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) = v35
                                                                          ^ (*(_DWORD *)(*v29
                                                                                       + 24LL
                                                                                       * *(unsigned int *)(a1 + 16)
                                                                                       + 4)
                                                                           ^ v35)
                                                                          & 0x1F;
                *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 8) = *(_DWORD *)(*v29
                                                                                      + 24LL
                                                                                      * *(unsigned int *)(a1 + 16)
                                                                                      + 8)
                                                                          & 3
                                                                          | (4 * *((unsigned __int16 *)pv[0] + 6 * i + 2));
                *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) ^= (*(_DWORD *)(*v29
                                                                                        + 24LL
                                                                                        * *(unsigned int *)(a1 + 16)
                                                                                        + 4)
                                                                            ^ (16 * *((_DWORD *)pv[0] + 3 * i + 2)))
                                                                           & 0x10;
                *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) = *(_DWORD *)(*v29
                                                                                      + 24LL
                                                                                      * *(unsigned int *)(a1 + 16)
                                                                                      + 4)
                                                                          & 0xFFFFFFFD
                                                                          | *((_DWORD *)pv[0] + 3 * i + 2) & 2;
                v36 = *(unsigned int *)(a1 + 16);
                v37 = *v29;
                v38 = 24 * v36;
                if ( !(_DWORD)v36
                  || (v39 = 4,
                      ((*(_DWORD *)(v38 + v37 + 4) ^ *(_DWORD *)(v37 + 24LL * (unsigned int)(v36 - 1) + 4)) & 0xFFFFFFE0) != 0) )
                {
                  v39 = 0;
                }
                *(_DWORD *)(v37 + v38 + 4) &= ~4u;
                *(_DWORD *)(v37 + v38 + 4) |= v39;
                *(_DWORD *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) = *(_DWORD *)(*v29
                                                                                      + 24LL
                                                                                      * *(unsigned int *)(a1 + 16)
                                                                                      + 4)
                                                                          & 0xFFFFFFF7
                                                                          | (2 * (*((_DWORD *)pv[0] + 3 * i + 2) & 4));
              }
              v40 = *v29;
              v41 = *(_QWORD *)(v47 + 8LL * i);
              if ( (*(_BYTE *)(*v29 + 24LL * *(unsigned int *)(a1 + 16) + 4) & 8) != 0 )
              {
                *(_QWORD *)(v40 + 24LL * *(unsigned int *)(a1 + 16) + 16) = v41;
                *(_BYTE *)(a1 + 72) = 1;
              }
              else
              {
                *(_DWORD *)(v40 + 24LL * *(unsigned int *)(a1 + 16)) = (signed __int64)(v41
                                                                                      + 2LL * *(unsigned int *)(a1 + 56)
                                                                                      - (unsigned __int64)Src[1]) >> 1;
                v42 = -1;
                do
                  ++v42;
                while ( *(_WORD *)(*(_QWORD *)(v47 + 8LL * i) + 2 * v42) );
                v17 += v42 + 1;
              }
              ++*(_DWORD *)(a1 + 16);
            }
            v13 = ReallocArrayVoid((void **)(a1 + 48), 2u, v17 + *(_DWORD *)(a1 + 56), (struct CHeap *)&g_heap, 0);
            if ( v13 < 0 )
              return (unsigned int)v13;
            memcpy_0((void *)(*(_QWORD *)(a1 + 48) + 2LL * *(unsigned int *)(a1 + 56)), Src[1], 2LL * v17);
            *(_DWORD *)(a1 + 56) += v17;
            v10 = a2;
            v17 = 0;
          }
          CoTaskMemFree(pv[1]);
          v14 = a5;
          pv[1] = 0;
        }
        if ( v50 <= 0 )
          break;
        v15 += 2 * v50;
      }
      v16 = (char *)&a3[(unsigned int)v8];
    }
    if ( v14 < 0 )
    {
      return (unsigned int)v14;
    }
    else
    {
      v13 = ReallocArrayVoid((void **)(a1 + 32), 2u, v8, (struct CHeap *)&g_heap, 0);
      if ( v13 >= 0 )
      {
        v43 = *(void **)(a1 + 32);
        *(_DWORD *)(a1 + 40) = v8;
        memcpy_0(v43, a3, 2LL * (unsigned int)v8);
        v44 = (int)a6;
        if ( !a6 || (v45 = CHeap::WcsDup((CHeap *)&g_heap, a6), (*(_QWORD *)(a1 + 64) = v45) != 0) )
        {
          v13 = CSpTextBuffer::PrepareSearchForTNLattices((CSpTextBuffer *)a1, v44);
          if ( v13 >= 0 )
          {
            CSpTextBuffer::UpdateOptionalAndContentFlags((CSpTextBuffer *)a1, v10);
            CSpTextBuffer::UpdateContentMatchMode((CSpTextBuffer *)a1);
            if ( (int)CSpTextBuffer::SetActiveRange((CSpTextBuffer *)a1, 0, 0) >= 0 )
              CSpTextBuffer::UpdateRestHasContentFlags((CSpTextBuffer *)a1);
            *(_BYTE *)(a1 + 24) = 1;
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180053658  mov     [rsp-38h+arg_10], rbx
0x18005365d  mov     [rsp-38h+arg_8], rdx
0x180053662  push    rbp
0x180053663  push    rsi
0x180053664  push    rdi
0x180053665  push    r12
0x180053667  push    r13
0x180053669  push    r14
0x18005366b  push    r15
0x18005366d  mov     rbp, rsp
0x180053670  sub     rsp, 80h
0x180053677  xorps   xmm0, xmm0
0x18005367a  xor     r14d, r14d
0x18005367d  mov     esi, r9d
0x180053680  mov     r15, r8
0x180053683  mov     r12, rdx
0x180053686  mov     rbx, rcx
0x180053689  movups  xmmword ptr [rbp+Src], xmm0
0x18005368d  movups  [rbp+var_28], xmm0
0x180053691  movups  xmmword ptr [rbp+pv], xmm0
0x180053695  cmp     r9d, 0FFFFFFFFh
0x180053699  jnz     short loc_1800536B3
0x18005369b  test    r8, r8
0x18005369e  jnz     short loc_1800536A5
0x1800536a0  mov     esi, r14d
0x1800536a3  jmp     short loc_1800536B3
0x1800536a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800536a9  inc     rsi
0x1800536ac  cmp     [r8+rsi*2], r14w
0x1800536b1  jnz     short loc_1800536A9
0x1800536b3  cmp     [rcx+18h], r14b
0x1800536b7  jz      short loc_1800536DE
0x1800536b9  cmp     [rcx+28h], esi
0x1800536bc  jnz     short loc_1800536DE
0x1800536be  mov     rcx, [rcx+20h]; Buf1
0x1800536c2  mov     rdx, r15; Buf2
0x1800536c5  mov     r8d, esi
0x1800536c8  add     r8, r8; Size
0x1800536cb  call    memcmp_0
0x1800536d0  test    eax, eax
0x1800536d2  jnz     short loc_1800536DE
0x1800536d4  mov     eax, 1
0x1800536d9  jmp     loc_180053BCC
0x1800536de  mov     rcx, rbx; this
0x1800536e1  mov     edi, r14d
0x1800536e4  call    ?PartialReset@CSpTextBuffer@@QEAAXXZ; CSpTextBuffer::PartialReset(void)
0x1800536e9  test    r15, r15
0x1800536ec  jz      loc_180053BCA
0x1800536f2  test    esi, esi
0x1800536f4  jz      loc_180053BCA
0x1800536fa  xorps   xmm0, xmm0
0x1800536fd  mov     eax, esi
0x1800536ff  mov     ecx, r14d
0x180053702  lea     rdi, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x180053709  mov     [rbp+arg_20], ecx
0x18005370c  mov     r14, r15
0x18005370f  movups  xmmword ptr [rbp+Src], xmm0
0x180053713  lea     r13, [rax+rax]
0x180053717  lea     rax, [r15+r13]
0x18005371b  mov     [rbp+Size], r13
0x18005371f  xor     r13d, r13d
0x180053722  mov     [rbp+arg_0], rax
0x180053726  mov     [rbx+10h], r13d
0x18005372a  mov     [rbx+38h], r13d
0x18005372e  mov     [rbx+18h], r13w
0x180053733  movups  [rbp+var_28], xmm0
0x180053737  movups  xmmword ptr [rbp+pv], xmm0
0x18005373b  cmp     r14, rax
0x18005373e  jnb     loc_180053B29
0x180053744  sub     rax, r14
0x180053747  lea     r8, [rbp+arg_18]
0x18005374b  sar     rax, 1
0x18005374e  mov     rdx, r14
0x180053751  mov     [rbp+arg_18], eax
0x180053754  mov     rcx, r12
0x180053757  mov     rax, [r12]
0x18005375b  mov     rax, [rax+48h]
0x18005375f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053764  cmp     eax, 1
0x180053767  jnz     loc_18005384D
0x18005376d  mov     r8d, [rbx+10h]
0x180053771  test    r8d, r8d
0x180053774  jz      loc_18005383D
0x18005377a  lea     eax, [r8-1]
0x18005377e  lea     rdx, [rax+rax*2]
0x180053782  lea     r12, [rbx+8]
0x180053786  mov     rax, [r12]
0x18005378a  test    byte ptr [rax+rdx*8+4], 2
0x18005378f  jnz     loc_180053839
0x180053795  lea     r9, [rbx+14h]; unsigned int *
0x180053799  mov     [rsp+80h+var_58], rdi; struct CHeap *
0x18005379e  inc     r8d; unsigned int
0x1800537a1  mov     dword ptr [rsp+80h+var_60], 64h ; 'd'; unsigned int
0x1800537a9  mov     edx, 18h; unsigned __int64
0x1800537ae  mov     rcx, r12; void **
0x1800537b1  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800537b6  mov     edi, eax
0x1800537b8  test    eax, eax
0x1800537ba  js      loc_180053BCA
0x1800537c0  mov     eax, [rbx+10h]
0x1800537c3  lea     rdi, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800537ca  xor     edx, edx
0x1800537cc  xorps   xmm0, xmm0
0x1800537cf  lea     rcx, [rax+rax*2]
0x1800537d3  mov     rax, [r12]
0x1800537d7  movups  xmmword ptr [rax+rcx*8], xmm0
0x1800537db  mov     [rax+rcx*8+10h], rdx
0x1800537e0  mov     eax, [rbx+10h]
0x1800537e3  mov     rcx, [r12]
0x1800537e7  lea     rdx, [rax+rax*2]
0x1800537eb  mov     eax, [rbx+38h]
0x1800537ee  mov     [rcx+rdx*8], eax
0x1800537f1  mov     eax, [rbx+10h]
0x1800537f4  mov     rcx, [r12]
0x1800537f8  lea     rdx, [rax+rax*2]
0x1800537fc  mov     rax, r14
0x1800537ff  and     dword ptr [rcx+rdx*8+4], 1Fh
0x180053804  sub     rax, r15
0x180053807  sar     rax, 1
0x18005380a  shl     eax, 5
0x18005380d  or      [rcx+rdx*8+4], eax
0x180053811  mov     eax, [rbx+10h]
0x180053814  lea     rcx, [rax+rax*2]
0x180053818  mov     rax, [r12]
0x18005381c  and     dword ptr [rax+rcx*8+8], 3
0x180053821  or      dword ptr [rax+rcx*8+8], 4
0x180053826  mov     eax, [rbx+10h]
0x180053829  lea     rcx, [rax+rax*2]
0x18005382d  mov     rax, [r12]
0x180053831  or      dword ptr [rax+rcx*8+4], 2
0x180053836  inc     dword ptr [rbx+10h]
0x180053839  mov     r12, [rbp+arg_8]
0x18005383d  mov     ecx, [rbp+arg_20]
0x180053840  add     r14, 2
0x180053844  mov     rax, [rbp+arg_0]
0x180053848  jmp     loc_18005373B
0x18005384d  test    eax, eax
0x18005384f  js      loc_180053B13
0x180053855  cmp     [rbx+4], r13d
0x180053859  lea     rcx, [rbp+Src]
0x18005385d  mov     r8d, [rbp+arg_18]
0x180053861  mov     eax, 6
0x180053866  mov     qword ptr [rsp+80h+var_60], rcx
0x18005386b  mov     rdx, r14
0x18005386e  mov     rcx, r12
0x180053871  lea     r9d, [rax+8]
0x180053875  cmovz   r9d, eax
0x180053879  mov     rax, [r12]
0x18005387d  cmp     [rbp+arg_38], r13d
0x180053881  jz      short loc_18005388C
0x180053883  mov     rax, [rax+0D8h]
0x18005388a  jmp     short loc_180053890
0x18005388c  mov     rax, [rax+50h]
0x180053890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053895  test    eax, eax
0x180053897  js      loc_180053B13
0x18005389d  mov     ecx, dword ptr [rbp+Src]
0x1800538a0  test    ecx, ecx
0x1800538a2  jz      loc_180053B00
0x1800538a8  mov     r8d, [rbx+10h]
0x1800538ac  lea     r12, [rbx+8]
0x1800538b0  add     r8d, ecx; unsigned int
0x1800538b3  mov     [rsp+80h+var_58], rdi; struct CHeap *
0x1800538b8  mov     rcx, r12; void **
0x1800538bb  mov     dword ptr [rsp+80h+var_60], 64h ; 'd'; unsigned int
0x1800538c3  lea     r9, [rbx+14h]; unsigned int *
0x1800538c7  mov     edx, 18h; unsigned __int64
0x1800538cc  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x1800538d1  mov     edi, eax
0x1800538d3  test    eax, eax
0x1800538d5  js      loc_180053BCA
0x1800538db  xor     edi, edi
0x1800538dd  mov     r10d, edi
0x1800538e0  cmp     r10d, dword ptr [rbp+Src]
0x1800538e4  jnb     loc_180053AA9
0x1800538ea  mov     eax, [rbx+10h]
0x1800538ed  xor     edx, edx
0x1800538ef  xorps   xmm0, xmm0
0x1800538f2  mov     r11d, r10d
0x1800538f5  lea     rcx, [rax+rax*2]
0x1800538f9  mov     rax, [r12]
0x1800538fd  movups  xmmword ptr [rax+rcx*8], xmm0
0x180053901  mov     [rax+rcx*8+10h], rdx
0x180053906  mov     eax, [rbx+10h]
0x180053909  lea     rcx, [rax+rax*2]
0x18005390d  mov     rax, [r12]
0x180053911  mov     dword ptr [rax+rcx*8], 0FFFFFFFFh
0x180053918  mov     eax, [rbx+10h]
0x18005391b  mov     rcx, [r12]
0x18005391f  lea     rdx, [rax+rax*2]
0x180053923  mov     rax, r14
0x180053926  and     dword ptr [rcx+rdx*8+4], 1Fh
0x18005392b  sub     rax, r15
0x18005392e  sar     rax, 1
0x180053931  shl     eax, 5
0x180053934  or      [rcx+rdx*8+4], eax
0x180053938  mov     rdx, [rbp+pv]
0x18005393c  test    rdx, rdx
0x18005393f  jz      loc_180053A4B
0x180053945  mov     eax, [rbx+10h]
0x180053948  lea     rdi, [r11+r11*2]
0x18005394c  mov     edx, [rdx+rdi*4]
0x18005394f  mov     r8, [r12]
0x180053953  shl     edx, 5
0x180053956  lea     r9, [rax+rax*2]
0x18005395a  add     edx, [r8+r9*8+4]
0x18005395f  mov     eax, edx
0x180053961  xor     eax, [r8+r9*8+4]
0x180053966  and     eax, 1Fh
0x180053969  xor     eax, edx
0x18005396b  mov     [r8+r9*8+4], eax
0x180053970  xor     r9d, r9d
0x180053973  mov     eax, [rbx+10h]
0x180053976  mov     rdx, [r12]
0x18005397a  lea     r8, [rax+rax*2]
0x18005397e  mov     rax, [rbp+pv]
0x180053982  movzx   ecx, word ptr [rax+rdi*4+4]
0x180053987  mov     eax, [rdx+r8*8+8]
0x18005398c  shl     ecx, 2
0x18005398f  and     eax, 3
0x180053992  or      ecx, eax
0x180053994  mov     [rdx+r8*8+8], ecx
0x180053999  mov     eax, [rbx+10h]
0x18005399c  mov     rdx, [r12]
0x1800539a0  lea     r8, [rax+rax*2]
0x1800539a4  mov     rax, [rbp+pv]
0x1800539a8  mov     ecx, [rax+rdi*4+8]
0x1800539ac  shl     ecx, 4
0x1800539af  xor     ecx, [rdx+r8*8+4]
0x1800539b4  and     ecx, 10h
0x1800539b7  xor     [rdx+r8*8+4], ecx
0x1800539bc  mov     eax, [rbx+10h]
0x1800539bf  mov     rdx, [r12]
0x1800539c3  lea     r8, [rax+rax*2]
0x1800539c7  mov     rax, [rbp+pv]
0x1800539cb  mov     ecx, [rax+rdi*4+8]
0x1800539cf  mov     eax, [rdx+r8*8+4]
0x1800539d4  and     ecx, 2
0x1800539d7  and     eax, 0FFFFFFFDh
0x1800539da  or      ecx, eax
0x1800539dc  mov     [rdx+r8*8+4], ecx
0x1800539e1  mov     ecx, [rbx+10h]
0x1800539e4  mov     rdx, [r12]
0x1800539e8  lea     rax, [rcx+rcx*2]
0x1800539ec  lea     r8, ds:0[rax*8]
0x1800539f4  test    ecx, ecx
0x1800539f6  jz      short loc_180053A14
0x1800539f8  lea     eax, [rcx-1]
0x1800539fb  lea     rax, [rax+rax*2]
0x1800539ff  mov     ecx, [rdx+rax*8+4]
0x180053a03  lea     eax, [r9+4]
0x180053a07  xor     ecx, [r8+rdx+4]
0x180053a0c  test    ecx, 0FFFFFFE0h
0x180053a12  jz      short loc_180053A17
0x180053a14  mov     eax, r9d
0x180053a17  and     dword ptr [rdx+r8+4], 0FFFFFFFBh
0x180053a1d  or      [rdx+r8+4], eax
0x180053a22  mov     eax, [rbx+10h]
0x180053a25  mov     rdx, [r12]
0x180053a29  lea     r8, [rax+rax*2]
0x180053a2d  mov     rax, [rbp+pv]
0x180053a31  mov     ecx, [rax+rdi*4+8]
0x180053a35  mov     eax, [rdx+r8*8+4]
0x180053a3a  and     ecx, 4
0x180053a3d  add     ecx, ecx
0x180053a3f  and     eax, 0FFFFFFF7h
0x180053a42  or      ecx, eax
0x180053a44  mov     [rdx+r8*8+4], ecx
0x180053a49  xor     edi, edi
0x180053a4b  mov     eax, [rbx+10h]
0x180053a4e  mov     r9, [r12]
0x180053a52  lea     r8, [rax+rax*2]
0x180053a56  mov     rax, qword ptr [rbp+var_28]
0x180053a5a  test    byte ptr [r9+r8*8+4], 8
0x180053a60  mov     rcx, [rax+r11*8]
0x180053a64  jnz     short loc_180053A95
0x180053a66  mov     edx, [rbx+38h]
0x180053a69  lea     rax, [rcx+rdx*2]
0x180053a6d  sub     rax, [rbp+Src+8]
0x180053a71  sar     rax, 1
0x180053a74  mov     [r9+r8*8], eax
0x180053a78  mov     rax, qword ptr [rbp+var_28]
0x180053a7c  mov     rcx, [rax+r11*8]
0x180053a80  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053a84  inc     rax
0x180053a87  cmp     [rcx+rax*2], di
0x180053a8b  jnz     short loc_180053A84
0x180053a8d  inc     r13d
0x180053a90  add     r13d, eax
0x180053a93  jmp     short loc_180053A9E
0x180053a95  mov     [r9+r8*8+10h], rcx
0x180053a9a  mov     byte ptr [rbx+48h], 1
0x180053a9e  inc     dword ptr [rbx+10h]
0x180053aa1  inc     r10d
0x180053aa4  jmp     loc_1800538E0
0x180053aa9  mov     r8d, [rbx+38h]
0x180053aad  lea     r9, ?g_heap@@3VCHeap@@A; struct CHeap *
0x180053ab4  add     r8d, r13d; unsigned int
0x180053ab7  mov     [rsp+80h+var_60], dil; bool
0x180053abc  mov     edx, 2; unsigned __int64
  ... truncated ...
```
