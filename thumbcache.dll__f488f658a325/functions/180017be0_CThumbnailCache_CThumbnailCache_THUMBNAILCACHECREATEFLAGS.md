# CThumbnailCache::CThumbnailCache(THUMBNAILCACHECREATEFLAGS)

- ea: `0x180017be0`
- end: `0x180017d3e`
- name: `??0CThumbnailCache@@AEAA@W4THUMBNAILCACHECREATEFLAGS@@@Z`
- size: `350`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ac20`
- `0x18000c3d0`
- `0x180017d50`
- `0x180018e10`
- `0x180019004`
- `0x180019110`
- `0x18002ed6c`

## callees

- `0x180017be0`
- `0x1800182e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c81`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180017d24`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180017d24`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::CThumbnailCache(__int64 a1, int a2)
{
  __int64 v3; // r14
  unsigned __int64 v5; // rbx
  __int64 v6; // rax
  __m128i v7; // xmm0

  *(_DWORD *)(a1 + 40) = 1;
  *(_QWORD *)a1 = &CThumbnailCache::`vftable'{for `IThumbnailCache3'};
  v3 = a1 + 592;
  *(_QWORD *)(a1 + 8) = &CThumbnailCache::`vftable'{for `IThumbnailCachePrivate'};
  v5 = a1 + 600;
  *(_QWORD *)(a1 + 16) = &CThumbnailCache::`vftable'{for `IThumbnailReclaimCallback'};
  *(_QWORD *)(a1 + 24) = &CThumbnailCache::`vftable'{for `IThumbnailCachePrimer'};
  *(_QWORD *)(a1 + 32) = &CThumbnailCache::`vftable'{for `IImageStore'};
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 592) = &CCompressedBitmapSerializer::`vftable';
  *(_QWORD *)(a1 + 600) = &CMappedBitmapSerializer::`vftable';
  *(_DWORD *)(a1 + 720) = 0;
  *(_QWORD *)(a1 + 736) = 0;
  *(_BYTE *)(a1 + 744) = 0;
  *(_WORD *)(a1 + 756) = 0;
  *(_BYTE *)(a1 + 758) = 0;
  *(_DWORD *)(a1 + 760) = 0;
  *(_DWORD *)(a1 + 764) = GetCurrentThreadId();
  *(_DWORD *)(a1 + 768) = a2;
  *(_QWORD *)(a1 + 776) = 0;
  *(_QWORD *)(a1 + 784) = 0;
  *(_QWORD *)(a1 + 792) = 0;
  DllAddRef();
  DllAddRef();
  _InterlockedIncrement(&g_fhCache);
  v6 = 0;
  v7 = _mm_unpacklo_epi64((__m128i)v5, (__m128i)v5);
  do
  {
    *(__m128i *)(a1 + 8 * v6 + 608) = v7;
    v6 += 2;
  }
  while ( v6 != 4 );
  *(_QWORD *)(a1 + 640) = v3;
  *(_QWORD *)(a1 + 648) = v3;
  *(_QWORD *)(a1 + 656) = v3;
  *(_QWORD *)(a1 + 664) = v3;
  *(_QWORD *)(a1 + 672) = v3;
  *(_QWORD *)(a1 + 680) = v3;
  *(_QWORD *)(a1 + 688) = v3;
  *(_QWORD *)(a1 + 704) = v3;
  *(_QWORD *)(a1 + 696) = v3;
  *(_QWORD *)(a1 + 712) = 0;
  *(_DWORD *)(a1 + 772) = SHWindowsPolicy(&POLID_DisableThumbnailsOnNetworkFolders);
  return a1;
}

```

## disassembly

```asm
0x180017be0  push    rbx
0x180017be2  push    rbp
0x180017be3  push    rsi
0x180017be4  push    rdi
0x180017be5  push    r14
0x180017be7  sub     rsp, 20h
0x180017beb  xor     ebp, ebp
0x180017bed  mov     dword ptr [rcx+28h], 1
0x180017bf4  lea     rax, ??_7CThumbnailCache@@6BIThumbnailCache3@@@; const CThumbnailCache::`vftable'{for `IThumbnailCache3'}
0x180017bfb  mov     edi, edx
0x180017bfd  mov     [rcx], rax
0x180017c00  lea     r14, [rcx+250h]
0x180017c07  lea     rax, ??_7CThumbnailCache@@6BIThumbnailCachePrivate@@@; const CThumbnailCache::`vftable'{for `IThumbnailCachePrivate'}
0x180017c0e  mov     rsi, rcx
0x180017c11  mov     [rcx+8], rax
0x180017c15  lea     rbx, [rcx+258h]
0x180017c1c  lea     rax, ??_7CThumbnailCache@@6BIThumbnailReclaimCallback@@@; const CThumbnailCache::`vftable'{for `IThumbnailReclaimCallback'}
0x180017c23  mov     [rcx+10h], rax
0x180017c27  lea     rax, ??_7CThumbnailCache@@6BIThumbnailCachePrimer@@@; const CThumbnailCache::`vftable'{for `IThumbnailCachePrimer'}
0x180017c2e  mov     [rcx+18h], rax
0x180017c32  lea     rax, ??_7CThumbnailCache@@6BIImageStore@@@; const CThumbnailCache::`vftable'{for `IImageStore'}
0x180017c39  mov     [rcx+20h], rax
0x180017c3d  lea     rax, ??_7CCompressedBitmapSerializer@@6B@; const CCompressedBitmapSerializer::`vftable'
0x180017c44  mov     [rcx+38h], rbp
0x180017c48  mov     [rcx+40h], rbp
0x180017c4c  mov     [r14], rax
0x180017c4f  lea     rax, ??_7CMappedBitmapSerializer@@6B@; const CMappedBitmapSerializer::`vftable'
0x180017c56  mov     [rbx], rax
0x180017c59  mov     [rcx+2D0h], ebp
0x180017c5f  mov     [rcx+2E0h], rbp
0x180017c66  mov     [rcx+2E8h], bpl
0x180017c6d  mov     [rcx+2F4h], bp
0x180017c74  mov     [rcx+2F6h], bpl
0x180017c7b  mov     [rcx+2F8h], ebp
0x180017c81  call    cs:__imp_GetCurrentThreadId
0x180017c87  mov     [rsi+2FCh], eax
0x180017c8d  mov     [rsi+300h], edi
0x180017c93  mov     [rsi+308h], rbp
0x180017c9a  mov     [rsi+310h], rbp
0x180017ca1  mov     [rsi+318h], rbp
0x180017ca8  call    DllAddRef
0x180017cad  call    DllAddRef
0x180017cb2  lock inc cs:?g_fhCache@@3VCFileHandleCache@@A; CFileHandleCache g_fhCache
0x180017cb9  movq    xmm0, rbx
0x180017cbe  mov     eax, ebp
0x180017cc0  punpcklqdq xmm0, xmm0
0x180017cc4  movdqu  xmmword ptr [rsi+rax*8+260h], xmm0
0x180017ccd  add     rax, 2
0x180017cd1  cmp     rax, 4
0x180017cd5  jnz     short loc_180017CC4
0x180017cd7  lea     rcx, POLID_DisableThumbnailsOnNetworkFolders
0x180017cde  mov     [rsi+280h], r14
0x180017ce5  mov     [rsi+288h], r14
0x180017cec  mov     [rsi+290h], r14
0x180017cf3  mov     [rsi+298h], r14
0x180017cfa  mov     [rsi+2A0h], r14
0x180017d01  mov     [rsi+2A8h], r14
0x180017d08  mov     [rsi+2B0h], r14
0x180017d0f  mov     [rsi+2C0h], r14
0x180017d16  mov     [rsi+2B8h], r14
0x180017d1d  mov     [rsi+2C8h], rbp
0x180017d24  call    cs:__imp_SHWindowsPolicy
0x180017d2a  mov     [rsi+304h], eax
0x180017d30  mov     rax, rsi
0x180017d33  add     rsp, 20h
0x180017d37  pop     r14
0x180017d39  pop     rdi
0x180017d3a  pop     rsi
0x180017d3b  pop     rbp
0x180017d3c  pop     rbx
0x180017d3d  retn
```
