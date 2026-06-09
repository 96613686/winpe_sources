# CDecoder::emulate_extensions_relaxed(ushort const *,ulong)

- ea: `0x18006e160`
- end: `0x18006e589`
- name: `?emulate_extensions_relaxed@CDecoder@@AEAAJPEBGK@Z`
- size: `1065`
- prototype: `__int64 __fastcall(CDecoder *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18006dea8`

## callees

- `0x180002a88`
- `0x1800034b0`
- `0x18000614c`
- `0x18004c4d8`
- `0x1800689f8`
- `0x18006a4b8`
- `0x18006a884`
- `0x18006ac80`
- `0x18006e160`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006e1ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006e1ea`

## string_xrefs

- `0x18006e1a4`: `Emulate word %s, %d extensions\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDecoder::emulate_extensions_relaxed(CDecoder *this, const unsigned __int16 *a2, char a3)
{
  __int64 v5; // r8
  unsigned int v6; // r15d
  int v7; // r14d
  bool v8; // r13
  __int16 *v9; // rcx
  __int16 v10; // ax
  __int16 *v11; // rdx
  bool v12; // r12
  unsigned __int16 *v13; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  const unsigned __int16 *v17; // r14
  int matched; // eax
  __int64 v19; // rdi
  unsigned int i; // r15d
  struct CPPT *v21; // rax
  struct CPPT *v22; // r13
  int j; // esi
  struct NGTREE *v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  bool v29; // [rsp+30h] [rbp-D0h]
  bool v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  int v32; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v36; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v37; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+9Ch] [rbp-64h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v42; // [rsp+B0h] [rbp-50h]
  __int16 v43; // [rsp+C0h] [rbp-40h] BYREF
  char v44; // [rsp+C2h] [rbp-3Eh] BYREF

  v42 = a2;
  TraceTag((struct CDebugTag *)&g_tagEmulate, L"Emulate word %s, %d extensions\n", a2, *((unsigned int *)this + 596));
  v6 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v35 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 464LL) == 1041 )
  {
    if ( (unsigned int)_o_wcsncpy_s(&v43, 513, v5, 512) )
      return (unsigned int)-2147467259;
    v8 = 0;
    v30 = 0;
    v9 = (__int16 *)&v44;
    if ( v43 != 47 )
      v9 = &v43;
    v10 = *v9;
    if ( *v9 )
    {
      v11 = v9;
      do
      {
        if ( v10 == 47 )
        {
          *v11 = 127;
        }
        else if ( v10 == 59 )
        {
          *v11 = 0;
        }
        v10 = *++v11;
      }
      while ( *v11 );
    }
  }
  else
  {
    v8 = 1;
    v30 = 1;
    LODWORD(v9) = v5;
  }
  v7 = ParseEngineWord((_DWORD)v9, (unsigned int)&v33, (unsigned int)&v37, (unsigned int)&v34, (__int64)&v35);
  v31 = v7;
  if ( v7 >= 0 )
  {
    v36 = a3 & 1;
    v12 = !(a3 & 1);
    if ( v8 )
    {
      v13 = v37;
      v14 = v35;
    }
    else
    {
      v13 = v33;
      v14 = v34;
    }
    v34 = v14;
    v33 = v13;
    v15 = *((_QWORD *)this + 300);
    v16 = v15;
    if ( *((_DWORD *)this + 604) )
    {
      v17 = v13;
      do
      {
        if ( (*(_BYTE *)v16 & 3) == 0 )
        {
          matched = CDecoder::MatchNGTFanout(
                      this,
                      *(struct NGTREE **)(v16 + 8),
                      *(struct CPPT **)(v16 + 24),
                      (struct TOKEN *)(v16 + 16),
                      *(_BYTE *)(v16 + 4) & 0x3F,
                      *(_WORD *)(v16 + 6),
                      v17,
                      v14,
                      v8,
                      v12,
                      *(_QWORD *)(v16 + 32));
          if ( matched > 0 )
          {
            *(_QWORD *)(v16 + 32) += matched;
            if ( v15 < v16 )
            {
              *(_OWORD *)v15 = *(_OWORD *)v16;
              *(_OWORD *)(v15 + 16) = *(_OWORD *)(v16 + 16);
              *(_QWORD *)(v15 + 32) = *(_QWORD *)(v16 + 32);
            }
            v15 += 40LL;
          }
        }
        ++v6;
        v16 += 40LL;
        v14 = v34;
      }
      while ( v6 < *((_DWORD *)this + 604) );
      v7 = v31;
    }
    *((_DWORD *)this + 604) = (__int64)(v15 - *((_QWORD *)this + 300)) / 40;
    v19 = *((_QWORD *)this + 293);
    for ( i = 0; i < *((_DWORD *)this + 596); ++i )
    {
      v21 = CDecoder::HypExtPPT(this, (const struct HYP_EXT *)v19);
      v22 = v21;
      if ( (*(_DWORD *)v19 & 3) != 0 )
      {
        if ( (*(_DWORD *)v19 & 3) == 1 )
        {
          v38 = 0;
          v40 = 0;
          v39 = 0;
          v41 = 4;
          v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int64 *))(**((_QWORD **)v21 + 2)
                                                                                              + 48LL))(
                 *((_QWORD *)v21 + 2),
                 v42,
                 v36,
                 &v38);
          if ( v7 < 0 )
          {
            CSPArray<unsigned short *,unsigned short *>::~CSPArray<unsigned short *,unsigned short *>(&v38);
            return (unsigned int)v7;
          }
          CDecoder::EmulateUgt(this, v19, *(unsigned __int16 *)(v19 + 12), v22, &v38);
          CSPArray<unsigned short *,unsigned short *>::~CSPArray<unsigned short *,unsigned short *>(&v38);
        }
      }
      else
      {
        for ( j = 0; ; ++j )
        {
          v24 = (struct NGTREE *)(*(_QWORD *)(v19 + 32) + 4LL * j);
          v35 = (unsigned __int64)v24;
          if ( *(_DWORD *)v24 < 0x20000000u )
          {
            if ( j )
              break;
          }
          v32 = CDecoder::MatchNGTFanout(
                  this,
                  v24,
                  v22,
                  (struct TOKEN *)(v19 + 40),
                  *(_BYTE *)(v19 + 4) & 0x3F,
                  *(_WORD *)(v19 + 12),
                  v33,
                  v34,
                  v30,
                  v12,
                  0);
          if ( v32 > 0 )
          {
            v7 = EnsureArrayVoid(
                   (void **)this + 300,
                   0x28u,
                   *((_DWORD *)this + 604) + 1,
                   (unsigned int *)this + 602,
                   *((_DWORD *)this + 603),
                   *((struct CHeap **)this + 299),
                   v29);
            if ( v7 < 0 )
              return (unsigned int)v7;
            v25 = *((unsigned int *)this + 604);
            *((_DWORD *)this + 604) = v25 + 1;
            v26 = 5 * v25;
            v27 = *((_QWORD *)this + 300);
            *(_DWORD *)(v27 + 8 * v26) ^= (*(_DWORD *)v19 ^ *(_DWORD *)(v27 + 8 * v26)) & 3;
            *(_BYTE *)(v27 + 8 * v26 + 4) ^= (*(_BYTE *)(v19 + 4) ^ *(_BYTE *)(v27 + 8 * v26 + 4)) & 0x3F;
            *(_WORD *)(v27 + 8 * v26 + 6) = *(_WORD *)(v19 + 12);
            *(_QWORD *)(v27 + 8 * v26 + 8) = v35;
            *(_QWORD *)(v27 + 8 * v26 + 16) = *(_QWORD *)(v19 + 40);
            *(_QWORD *)(v27 + 8 * v26 + 24) = v22;
            *(_QWORD *)(v27 + 8 * v26 + 32) = v32;
          }
        }
      }
      v19 += 48;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006e160  mov     [rsp-8+arg_10], rbx
0x18006e165  push    rbp
0x18006e166  push    rsi
0x18006e167  push    rdi
0x18006e168  push    r12
0x18006e16a  push    r13
0x18006e16c  push    r14
0x18006e16e  push    r15
0x18006e170  lea     rbp, [rsp-3E0h]
0x18006e178  sub     rsp, 4E0h
0x18006e17f  mov     rax, cs:__security_cookie
0x18006e186  xor     rax, rsp
0x18006e189  mov     [rbp+410h+var_40], rax
0x18006e190  mov     edi, r8d
0x18006e193  mov     r8, rdx
0x18006e196  mov     [rbp+410h+var_460], rdx
0x18006e19a  mov     rbx, rcx
0x18006e19d  mov     r9d, [rcx+950h]
0x18006e1a4  lea     rdx, aEmulateWordSDE; "Emulate word %s, %d extensions\n"
0x18006e1ab  lea     rcx, ?g_tagEmulate@@3VCDebugTag@@A; struct CDebugTag *
0x18006e1b2  call    ?TraceTag@@YAXPEAVCDebugTag@@PEBGZZ; TraceTag(CDebugTag *,ushort const *,...)
0x18006e1b7  xor     r15d, r15d
0x18006e1ba  mov     [rsp+510h+var_4A8], r15
0x18006e1bf  mov     [rsp+510h+var_4A0], r15
0x18006e1c4  mov     [rbp+410h+var_488], r15
0x18006e1c8  mov     [rsp+510h+var_498], r15
0x18006e1cd  mov     rax, [rbx+50h]
0x18006e1d1  cmp     dword ptr [rax+1D0h], 411h
0x18006e1db  jnz     short loc_18006E248
0x18006e1dd  mov     edx, 201h
0x18006e1e2  lea     r9d, [rdx-1]
0x18006e1e6  lea     rcx, [rbp+410h+var_450]
0x18006e1ea  call    cs:__imp__o_wcsncpy_s
0x18006e1f0  test    eax, eax
0x18006e1f2  jz      short loc_18006E1FF
0x18006e1f4  mov     r14d, 80004005h
0x18006e1fa  jmp     loc_18006E55C
0x18006e1ff  mov     r13b, r15b
0x18006e202  mov     [rsp+510h+var_4B0], r15b
0x18006e207  lea     rcx, [rbp+410h+var_44E]
0x18006e20b  lea     rax, [rbp+410h+var_450]
0x18006e20f  cmp     [rbp+410h+var_450], 2Fh ; '/'
0x18006e214  cmovnz  rcx, rax
0x18006e218  movzx   eax, word ptr [rcx]
0x18006e21b  test    ax, ax
0x18006e21e  jz      short loc_18006E253
0x18006e220  mov     rdx, rcx
0x18006e223  cmp     ax, 2Fh ; '/'
0x18006e227  jnz     short loc_18006E230
0x18006e229  mov     word ptr [rdx], 7Fh
0x18006e22e  jmp     short loc_18006E23A
0x18006e230  cmp     ax, 3Bh ; ';'
0x18006e234  jnz     short loc_18006E23A
0x18006e236  mov     [rdx], r15w
0x18006e23a  add     rdx, 2
0x18006e23e  movzx   eax, word ptr [rdx]
0x18006e241  test    ax, ax
0x18006e244  jnz     short loc_18006E223
0x18006e246  jmp     short loc_18006E253
0x18006e248  mov     r13b, 1
0x18006e24b  mov     [rsp+510h+var_4B0], r13b
0x18006e250  mov     rcx, r8
0x18006e253  lea     rax, [rsp+510h+var_498]
0x18006e258  lea     r9, [rsp+510h+var_4A0]
0x18006e25d  lea     r8, [rbp+410h+var_488]
0x18006e261  lea     rdx, [rsp+510h+var_4A8]
0x18006e266  mov     qword ptr [rsp+510h+var_4F0], rax
0x18006e26b  call    ParseEngineWord
0x18006e270  mov     r14d, eax
0x18006e273  mov     [rsp+510h+var_4AC], eax
0x18006e277  test    eax, eax
0x18006e279  js      loc_18006E55C
0x18006e27f  and     edi, 1
0x18006e282  mov     [rbp+410h+var_490], edi
0x18006e285  mov     r12b, dil
0x18006e288  xor     r12b, 1
0x18006e28c  test    r13b, r13b
0x18006e28f  jz      short loc_18006E29C
0x18006e291  mov     rax, [rbp+410h+var_488]
0x18006e295  mov     rdx, [rsp+510h+var_498]
0x18006e29a  jmp     short loc_18006E2A6
0x18006e29c  mov     rax, [rsp+510h+var_4A8]
0x18006e2a1  mov     rdx, [rsp+510h+var_4A0]
0x18006e2a6  mov     [rsp+510h+var_4A0], rdx
0x18006e2ab  mov     [rsp+510h+var_4A8], rax
0x18006e2b0  mov     rsi, [rbx+960h]
0x18006e2b7  mov     rdi, rsi
0x18006e2ba  cmp     [rbx+970h], r15d
0x18006e2c1  jbe     loc_18006E35C
0x18006e2c7  mov     r14, rax
0x18006e2ca  test    byte ptr [rdi], 3
0x18006e2cd  jnz     short loc_18006E33E
0x18006e2cf  mov     cl, [rdi+4]
0x18006e2d2  and     cl, 3Fh
0x18006e2d5  lea     r9, [rdi+10h]; struct TOKEN *
0x18006e2d9  mov     rax, [rdi+20h]
0x18006e2dd  mov     [rsp+510h+var_4C0], rax; unsigned __int64
0x18006e2e2  mov     [rsp+510h+var_4C8], r12b; bool
0x18006e2e7  mov     [rsp+510h+var_4D0], r13b; bool
0x18006e2ec  mov     [rsp+510h+var_4D8], rdx; unsigned __int64
0x18006e2f1  mov     [rsp+510h+var_4E0], r14; unsigned __int16 *
0x18006e2f6  movzx   eax, word ptr [rdi+6]
0x18006e2fa  mov     word ptr [rsp+510h+var_4E8], ax; unsigned __int16
0x18006e2ff  mov     [rsp+510h+var_4F0], cl; char
0x18006e303  mov     r8, [rdi+18h]; struct CPPT *
0x18006e307  mov     rdx, [rdi+8]; struct NGTREE *
0x18006e30b  mov     rcx, rbx; this
0x18006e30e  call    ?MatchNGTFanout@CDecoder@@AEAAHPEAUNGTREE@@PEAVCPPT@@PEAUTOKEN@@EGPEBG_K_N54@Z; CDecoder::MatchNGTFanout(NGTREE *,CPPT *,TOKEN *,uchar,ushort,ushort const *,unsigned __int64,bool,bool,unsigned __int64)
0x18006e313  test    eax, eax
0x18006e315  jle     short loc_18006E33E
0x18006e317  cdqe
0x18006e319  add     [rdi+20h], rax
0x18006e31d  cmp     rsi, rdi
0x18006e320  jnb     short loc_18006E33A
0x18006e322  movups  xmm0, xmmword ptr [rdi]
0x18006e325  movups  xmmword ptr [rsi], xmm0
0x18006e328  movups  xmm1, xmmword ptr [rdi+10h]
0x18006e32c  movups  xmmword ptr [rsi+10h], xmm1
0x18006e330  movsd   xmm0, qword ptr [rdi+20h]
0x18006e335  movsd   qword ptr [rsi+20h], xmm0
0x18006e33a  add     rsi, 28h ; '('
0x18006e33e  inc     r15d
0x18006e341  add     rdi, 28h ; '('
0x18006e345  cmp     r15d, [rbx+970h]
0x18006e34c  mov     rdx, [rsp+510h+var_4A0]
0x18006e351  jb      loc_18006E2CA
0x18006e357  mov     r14d, [rsp+510h+var_4AC]
0x18006e35c  sub     rsi, [rbx+960h]
0x18006e363  mov     rax, 6666666666666667h
0x18006e36d  imul    rsi
0x18006e370  sar     rdx, 4
0x18006e374  mov     rax, rdx
0x18006e377  shr     rax, 3Fh
0x18006e37b  add     rdx, rax
0x18006e37e  mov     [rbx+970h], edx
0x18006e384  mov     rdi, [rbx+928h]
0x18006e38b  xor     r15d, r15d
0x18006e38e  cmp     r15d, [rbx+950h]
0x18006e395  jnb     loc_18006E55C
0x18006e39b  mov     rdx, rdi; struct HYP_EXT *
0x18006e39e  mov     rcx, rbx; this
0x18006e3a1  call    ?HypExtPPT@CDecoder@@AEBAPEAVCPPT@@PEBUHYP_EXT@@@Z; CDecoder::HypExtPPT(HYP_EXT const *)
0x18006e3a6  mov     r13, rax
0x18006e3a9  mov     ecx, [rdi]
0x18006e3ab  and     ecx, 3
0x18006e3ae  jnz     loc_18006E4DA
0x18006e3b4  xor     esi, esi
0x18006e3b6  movsxd  rdx, esi
0x18006e3b9  mov     rcx, [rdi+20h]
0x18006e3bd  lea     rdx, [rcx+rdx*4]; struct NGTREE *
0x18006e3c1  mov     [rsp+510h+var_498], rdx
0x18006e3c6  cmp     dword ptr [rdx], 20000000h
0x18006e3cc  jnb     short loc_18006E3D6
0x18006e3ce  test    esi, esi
0x18006e3d0  jnz     loc_18006E547
0x18006e3d6  lea     r9, [rdi+28h]; struct TOKEN *
0x18006e3da  mov     cl, [rdi+4]
0x18006e3dd  and     cl, 3Fh
0x18006e3e0  mov     [rsp+510h+var_4C0], 0; unsigned __int64
0x18006e3e9  mov     [rsp+510h+var_4C8], r12b; bool
0x18006e3ee  mov     al, [rsp+510h+var_4B0]
0x18006e3f2  mov     [rsp+510h+var_4D0], al; bool
0x18006e3f6  mov     rax, [rsp+510h+var_4A0]
0x18006e3fb  mov     [rsp+510h+var_4D8], rax; unsigned __int64
0x18006e400  mov     rax, [rsp+510h+var_4A8]
0x18006e405  mov     [rsp+510h+var_4E0], rax; bool
0x18006e40a  movzx   eax, word ptr [rdi+0Ch]
0x18006e40e  mov     word ptr [rsp+510h+var_4E8], ax; unsigned __int16
0x18006e413  mov     [rsp+510h+var_4F0], cl; char
0x18006e417  mov     r8, r13; struct CPPT *
0x18006e41a  mov     rcx, rbx; this
0x18006e41d  call    ?MatchNGTFanout@CDecoder@@AEAAHPEAUNGTREE@@PEAVCPPT@@PEAUTOKEN@@EGPEBG_K_N54@Z; CDecoder::MatchNGTFanout(NGTREE *,CPPT *,TOKEN *,uchar,ushort,ushort const *,unsigned __int64,bool,bool,unsigned __int64)
0x18006e422  mov     [rsp+510h+var_4AC], eax
0x18006e426  test    eax, eax
0x18006e428  jle     loc_18006E4D3
0x18006e42e  lea     r9, [rbx+968h]; unsigned int *
0x18006e435  mov     r8d, [rbx+970h]
0x18006e43c  inc     r8d; unsigned int
0x18006e43f  lea     rcx, [rbx+960h]; void **
0x18006e446  mov     rdx, [rbx+958h]
0x18006e44d  mov     [rsp+510h+var_4E8], rdx; struct CHeap *
0x18006e452  mov     edx, [rbx+96Ch]
0x18006e458  mov     dword ptr [rsp+510h+var_4F0], edx; unsigned int
0x18006e45c  mov     edx, 28h ; '('; unsigned __int64
0x18006e461  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18006e466  mov     r14d, eax
0x18006e469  test    eax, eax
0x18006e46b  js      loc_18006E55C
0x18006e471  mov     edx, [rbx+970h]
0x18006e477  lea     ecx, [rdx+1]
0x18006e47a  mov     [rbx+970h], ecx
0x18006e480  lea     r8, [rdx+rdx*4]
0x18006e484  mov     rdx, [rbx+960h]
0x18006e48b  mov     ecx, [rdx+r8*8]
0x18006e48f  xor     ecx, [rdi]
0x18006e491  and     ecx, 3
0x18006e494  xor     [rdx+r8*8], ecx
0x18006e498  mov     al, [rdx+r8*8+4]
0x18006e49d  xor     al, [rdi+4]
0x18006e4a0  and     al, 3Fh
0x18006e4a2  xor     [rdx+r8*8+4], al
0x18006e4a7  movzx   eax, word ptr [rdi+0Ch]
0x18006e4ab  mov     [rdx+r8*8+6], ax
0x18006e4b1  mov     rax, [rsp+510h+var_498]
0x18006e4b6  mov     [rdx+r8*8+8], rax
0x18006e4bb  mov     rax, [rdi+28h]
0x18006e4bf  mov     [rdx+r8*8+10h], rax
0x18006e4c4  mov     [rdx+r8*8+18h], r13
0x18006e4c9  movsxd  rax, [rsp+510h+var_4AC]
0x18006e4ce  mov     [rdx+r8*8+20h], rax
0x18006e4d3  inc     esi
0x18006e4d5  jmp     loc_18006E3B6
0x18006e4da  cmp     ecx, 1
0x18006e4dd  jnz     short loc_18006E547
0x18006e4df  mov     [rbp+410h+var_480], 0
0x18006e4e7  mov     [rbp+410h+var_474], 0
0x18006e4ef  mov     [rbp+410h+var_478], 0
0x18006e4f6  mov     [rbp+410h+var_468], 4
0x18006e4fe  mov     rcx, [rax+10h]
0x18006e502  mov     rax, [rcx]
0x18006e505  lea     r9, [rbp+410h+var_480]
0x18006e509  mov     r8d, [rbp+410h+var_490]
0x18006e50d  mov     rdx, [rbp+410h+var_460]
0x18006e511  mov     rax, [rax+30h]
0x18006e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e51a  mov     r14d, eax
0x18006e51d  test    eax, eax
0x18006e51f  js      short loc_18006E553
0x18006e521  movzx   r8d, word ptr [rdi+0Ch]
0x18006e526  lea     rax, [rbp+410h+var_480]
0x18006e52a  mov     qword ptr [rsp+510h+var_4F0], rax
0x18006e52f  mov     r9, r13
0x18006e532  mov     rdx, rdi
0x18006e535  mov     rcx, rbx
0x18006e538  call    ?EmulateUgt@CDecoder@@AEAAXPEAUHYP_EXT@@IPEAVCPPT@@PEAV?$CSPArray@II@@@Z; CDecoder::EmulateUgt(HYP_EXT *,uint,CPPT *,CSPArray<uint,uint> *)
0x18006e53d  nop
0x18006e53e  lea     rcx, [rbp+410h+var_480]
0x18006e542  call    ??1?$CSPArray@PEAGPEAG@@QEAA@XZ; CSPArray<ushort *,ushort *>::~CSPArray<ushort *,ushort *>(void)
0x18006e547  inc     r15d
0x18006e54a  add     rdi, 30h ; '0'
0x18006e54e  jmp     loc_18006E38E
0x18006e553  lea     rcx, [rbp+410h+var_480]
0x18006e557  call    ??1?$CSPArray@PEAGPEAG@@QEAA@XZ; CSPArray<ushort *,ushort *>::~CSPArray<ushort *,ushort *>(void)
0x18006e55c  mov     eax, r14d
0x18006e55f  mov     rcx, [rbp+410h+var_40]
0x18006e566  xor     rcx, rsp; StackCookie
0x18006e569  call    __security_check_cookie
0x18006e56e  mov     rbx, [rsp+510h+arg_10]
0x18006e576  add     rsp, 4E0h
0x18006e57d  pop     r15
0x18006e57f  pop     r14
0x18006e581  pop     r13
0x18006e583  pop     r12
0x18006e585  pop     rdi
0x18006e586  pop     rsi
0x18006e587  pop     rbp
0x18006e588  retn
```
