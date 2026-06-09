# ORCreateHiveHandle

- ea: `0x180073960`
- end: `0x180073b6e`
- name: `ORCreateHiveHandle`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180071b00`
- `0x180071f88`

## callees

- `0x180003b26`
- `0x180003b32`
- `0x180003c78`
- `0x180004829`
- `0x180073960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073b3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073b3a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800739dd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800739dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739ed`

## pseudocode

```c
__int64 __fastcall ORCreateHiveHandle(__int64 a1, unsigned __int64 a2, _WORD *a3, _QWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  size_t v13; // rdi
  void *v14; // rax
  unsigned int v15; // r9d
  __m128i v16; // xmm3
  __m128i v17; // xmm2
  __int64 v18; // r8
  unsigned __int64 v19; // xmm0_8
  __int64 v20; // rax
  void *v22; // rcx

  *a4 = 0;
  v8 = (char *)o__aligned_malloc_0(0x118u, 0x10u);
  v9 = v8;
  if ( !v8 )
    return 8;
  memset_0(v8, 0, 0x118u);
  *(_DWORD *)v9 = -1092567328;
  *((_QWORD *)v9 + 2) = a1;
  *((_DWORD *)v9 + 6) = *(_DWORD *)(a1 + 24) - 4096 + (*(_DWORD *)(a1 + 20) << 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v9 + 136), 0x80000400) )
  {
    LastError = GetLastError();
LABEL_19:
    v22 = (void *)*((_QWORD *)v9 + 5);
    if ( v22 )
      aligned_free(v22);
    aligned_free(v9);
    return LastError;
  }
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = 2 * v11;
    if ( v12 > 0xFFFF )
    {
      *((_WORD *)v9 + 16) = -1;
      LastError = 87;
      goto LABEL_18;
    }
    v13 = (unsigned __int16)v12;
    *((_WORD *)v9 + 16) = v12;
    *((_WORD *)v9 + 17) = v12;
    v14 = o__aligned_malloc_0((unsigned __int16)v12, 0x10u);
    *((_QWORD *)v9 + 5) = v14;
    if ( !v14 )
    {
      LastError = 8;
LABEL_18:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
      goto LABEL_19;
    }
    memcpy_0(v14, a3, v13);
  }
  if ( a2 > 0xFFFFFFFF )
  {
    *((_DWORD *)v9 + 12) = -1;
    LastError = 534;
    goto LABEL_18;
  }
  *((_DWORD *)v9 + 12) = a2;
  *((_QWORD *)v9 + 11) = v9 + 80;
  v15 = 0;
  *((_QWORD *)v9 + 10) = v9 + 80;
  v16 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)(v9 + 184), (__m128i)(unsigned __int64)(v9 + 184));
  do
  {
    v17 = _mm_add_epi64(
            _mm_slli_epi64(
              _mm_unpacklo_epi32(
                _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v15), 0), _mm_loadl_epi64((const __m128i *)&_xmm)),
                (__m128i)0LL),
              4u),
            v16);
    v18 = 2LL * v15;
    v19 = _mm_srli_si128(v17, 8).m128i_u64[0];
    *(_QWORD *)&v9[16 * v15 + 192] = v17.m128i_i64[0];
    v20 = v15 + 1;
    v15 += 2;
    *(_QWORD *)&v9[8 * v18 + 184] = v17.m128i_i64[0];
    *(_QWORD *)&v9[16 * v20 + 192] = v19;
    *(_QWORD *)&v9[16 * v20 + 184] = v19;
  }
  while ( v15 < 6 );
  *a4 = v9;
  *((_QWORD *)v9 + 13) = v9 + 96;
  *((_QWORD *)v9 + 12) = v9 + 96;
  *((_QWORD *)v9 + 15) = v9 + 112;
  *((_QWORD *)v9 + 14) = v9 + 112;
  *((_QWORD *)v9 + 9) = v9 + 64;
  *((_QWORD *)v9 + 8) = v9 + 64;
  return 0;
}

```

## disassembly

```asm
0x180073960  push    rbx
0x180073962  push    rbp
0x180073963  push    rsi
0x180073964  push    rdi
0x180073965  push    r12
0x180073967  push    r14
0x180073969  push    r15
0x18007396b  sub     rsp, 20h
0x18007396f  xor     r12d, r12d
0x180073972  mov     rbp, rdx
0x180073975  mov     rdi, rcx
0x180073978  mov     [r9], r12
0x18007397b  mov     r15d, 118h
0x180073981  mov     r14, r9
0x180073984  mov     ecx, r15d; Size
0x180073987  mov     rsi, r8
0x18007398a  lea     edx, [r12+10h]; Alignment
0x18007398f  call    _o__aligned_malloc_0
0x180073994  mov     rbx, rax
0x180073997  test    rax, rax
0x18007399a  jnz     short loc_1800739A4
0x18007399c  lea     edi, [rax+8]
0x18007399f  jmp     loc_180073B5C
0x1800739a4  mov     r8, r15; Size
0x1800739a7  xor     edx, edx; Val
0x1800739a9  mov     rcx, rbx; void *
0x1800739ac  call    memset_0
0x1800739b1  mov     dword ptr [rbx], 0BEE0BEE0h
0x1800739b7  lea     r15, [rbx+88h]
0x1800739be  mov     [rbx+10h], rdi
0x1800739c2  mov     edx, 80000400h; dwSpinCount
0x1800739c7  mov     ecx, [rdi+14h]
0x1800739ca  mov     eax, [rdi+18h]
0x1800739cd  shl     ecx, 0Ch
0x1800739d0  add     eax, 0FFFFF000h
0x1800739d5  add     ecx, eax
0x1800739d7  mov     [rbx+18h], ecx
0x1800739da  mov     rcx, r15; lpCriticalSection
0x1800739dd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800739e4  nop     dword ptr [rax+rax+00h]
0x1800739e9  test    eax, eax
0x1800739eb  jnz     short loc_180073A00
0x1800739ed  call    cs:__imp_GetLastError
0x1800739f4  nop     dword ptr [rax+rax+00h]
0x1800739f9  mov     edi, eax
0x1800739fb  jmp     loc_180073B46
0x180073a00  test    rsi, rsi
0x180073a03  jz      short loc_180073A5A
0x180073a05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180073a09  inc     rax
0x180073a0c  cmp     [rsi+rax*2], r12w
0x180073a11  jnz     short loc_180073A09
0x180073a13  add     rax, rax
0x180073a16  mov     ecx, 0FFFFh
0x180073a1b  cmp     rax, rcx
0x180073a1e  ja      loc_180073B24
0x180073a24  movzx   edi, ax
0x180073a27  mov     edx, 10h; Alignment
0x180073a2c  mov     [rbx+20h], di
0x180073a30  mov     ecx, edi; Size
0x180073a32  mov     [rbx+22h], di
0x180073a36  call    _o__aligned_malloc_0
0x180073a3b  mov     [rbx+28h], rax
0x180073a3f  test    rax, rax
0x180073a42  jnz     short loc_180073A4C
0x180073a44  lea     edi, [rax+8]
0x180073a47  jmp     loc_180073B37
0x180073a4c  mov     r8, rdi; Size
0x180073a4f  mov     rdx, rsi; Src
0x180073a52  mov     rcx, rax; void *
0x180073a55  call    memcpy_0
0x180073a5a  mov     eax, 0FFFFFFFFh
0x180073a5f  cmp     rbp, rax
0x180073a62  ja      loc_180073B2F
0x180073a68  lea     rax, [rbx+50h]
0x180073a6c  mov     [rbx+30h], ebp
0x180073a6f  mov     [rax+8], rax
0x180073a73  mov     r9d, r12d
0x180073a76  mov     [rax], rax
0x180073a79  lea     rax, [rbx+0B8h]
0x180073a80  movq    xmm3, rax
0x180073a85  punpcklqdq xmm3, xmm3
0x180073a89  movq    xmm0, cs:__xmm@00000003000000020000000100000000
0x180073a91  xorps   xmm1, xmm1
0x180073a94  mov     r8d, r9d
0x180073a97  movd    xmm2, r9d
0x180073a9c  pshufd  xmm2, xmm2, 0
0x180073aa1  paddd   xmm2, xmm0
0x180073aa5  lea     rax, [r8+0Ch]
0x180073aa9  punpckldq xmm2, xmm1
0x180073aad  add     rax, rax
0x180073ab0  psllq   xmm2, 4
0x180073ab5  paddq   xmm2, xmm3
0x180073ab9  add     r8, r8
0x180073abc  movdqa  xmm0, xmm2
0x180073ac0  psrldq  xmm0, 8
0x180073ac5  movq    qword ptr [rbx+rax*8], xmm2
0x180073aca  lea     eax, [r9+1]
0x180073ace  mov     edx, eax
0x180073ad0  add     r9d, 2
0x180073ad4  add     rax, 0Ch
0x180073ad8  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x180073ae2  add     rax, rax
0x180073ae5  add     rdx, rdx
0x180073ae8  movq    qword ptr [rbx+rax*8], xmm0
0x180073aed  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x180073af6  cmp     r9d, 6
0x180073afa  jb      short loc_180073A89
0x180073afc  lea     rax, [rbx+60h]
0x180073b00  mov     [r14], rbx
0x180073b03  mov     [rax+8], rax
0x180073b07  mov     [rax], rax
0x180073b0a  lea     rax, [rbx+70h]
0x180073b0e  mov     [rax+8], rax
0x180073b12  mov     [rax], rax
0x180073b15  lea     rax, [rbx+40h]
0x180073b19  mov     [rax+8], rax
0x180073b1d  mov     [rax], rax
0x180073b20  xor     eax, eax
0x180073b22  jmp     short loc_180073B5E
0x180073b24  mov     [rbx+20h], cx
0x180073b28  mov     edi, 57h ; 'W'
0x180073b2d  jmp     short loc_180073B37
0x180073b2f  mov     [rbx+30h], eax
0x180073b32  mov     edi, 216h
0x180073b37  mov     rcx, r15; lpCriticalSection
0x180073b3a  call    cs:__imp_DeleteCriticalSection
0x180073b41  nop     dword ptr [rax+rax+00h]
0x180073b46  mov     rcx, [rbx+28h]; Block
0x180073b4a  test    rcx, rcx
0x180073b4d  jz      short loc_180073B54
0x180073b4f  call    _aligned_free
0x180073b54  mov     rcx, rbx; Block
0x180073b57  call    _aligned_free
0x180073b5c  mov     eax, edi
0x180073b5e  add     rsp, 20h
0x180073b62  pop     r15
0x180073b64  pop     r14
0x180073b66  pop     r12
0x180073b68  pop     rdi
0x180073b69  pop     rsi
0x180073b6a  pop     rbp
0x180073b6b  pop     rbx
0x180073b6c  retn
```
