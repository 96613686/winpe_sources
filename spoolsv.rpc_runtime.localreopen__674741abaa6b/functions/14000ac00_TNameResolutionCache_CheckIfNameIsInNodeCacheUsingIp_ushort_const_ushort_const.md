# TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(ushort const *,ushort const *)

- ea: `0x14000ac00`
- end: `0x14000aefc`
- name: `?CheckIfNameIsInNodeCacheUsingIp@TNameResolutionCache@@QEAAJPEBG0@Z`
- size: `764`
- prototype: `int(TNameResolutionCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000aab0`

## callees

- `0x1400088dc`
- `0x14000a288`
- `0x14000a6f0`
- `0x14000ac00`
- `0x14000e960`
- `0x14000fd30`
- `0x140019038`
- `0x14002d0a0`
- `0x140076bc4`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000acfb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000acfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000adeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000adeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ad63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ad63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ad72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ad72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000acc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000acc3`

## pseudocode

```c
__int64 __fastcall TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(
        TNameResolutionCache *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  TNameResolutionCache *v4; // r14
  __int64 v5; // rsi
  int v6; // r15d
  DWORD TickCount; // eax
  __int64 i; // r12
  __int64 v9; // rcx
  char *v10; // rbx
  TResolutionCacheNode *v11; // rdi
  unsigned int v12; // r14d
  TResolutionCacheNode *v13; // rsi
  const unsigned int **v15; // rbx
  const unsigned int **v16; // rcx
  const unsigned int **v17; // rbx
  const unsigned int **v18; // rcx
  DWORD v20; // [rsp+28h] [rbp-29h]
  int v21; // [rsp+30h] [rbp-21h] BYREF
  const unsigned int *v22; // [rsp+38h] [rbp-19h] BYREF
  int v23; // [rsp+40h] [rbp-11h]
  const unsigned int **v24; // [rsp+48h] [rbp-9h]
  const unsigned int **v25; // [rsp+50h] [rbp-1h]
  int v26; // [rsp+58h] [rbp+7h] BYREF
  const unsigned int *v27; // [rsp+60h] [rbp+Fh] BYREF
  int v28; // [rsp+68h] [rbp+17h]
  const unsigned int **v29; // [rsp+70h] [rbp+1Fh]
  const unsigned int **v30; // [rsp+78h] [rbp+27h]

  if ( !a3 )
    return 2147942487LL;
  v29 = &v27;
  v30 = &v27;
  v4 = g_pLocalIpAddressesCache;
  v24 = &v22;
  v26 = 1953721460;
  v25 = &v22;
  v27 = &NCoreLibrary::TLink::`vftable';
  v28 = 1802398836;
  v21 = 1953721460;
  v22 = &NCoreLibrary::TLink::`vftable';
  v23 = 1802398836;
  if ( TNameResolutionCache::IsClusterNode(g_pLocalIpAddressesCache) )
    goto LABEL_14;
  v5 = *((_QWORD *)v4 + 19);
  v6 = 1;
  if ( *(_BYTE *)(v5 + 88) )
  {
    NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)(v5 + 32));
    TickCount = GetTickCount();
    v20 = TickCount;
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v5 + 8); i = (unsigned int)(i + 1) )
    {
      v9 = *(_QWORD *)(v5 + 24);
      if ( *(_QWORD *)(v9 + 24 * i) )
      {
        if ( TickCount - *(_DWORD *)(v9 + 24 * i + 8) < *(_DWORD *)(v5 + 12)
          && !(unsigned int)_o__wcsicmp(a3, *(_QWORD *)(v9 + 24 * i)) )
        {
          v6 = 0;
          break;
        }
        TickCount = v20;
      }
    }
    NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v5 + 32));
  }
  if ( v6 == 1 )
  {
LABEL_14:
    if ( (unsigned __int16)TNameResolutionCache::CacheGetAddrInfo(v4, a3, (__int64)&v26, (__int64)&v21) == 11001 )
      TFastCache<NullCacheEntry>::AddString(*((_QWORD *)v4 + 19), a3);
  }
  v10 = (char *)v4 + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 56));
  ++*((_DWORD *)v4 + 25);
  v11 = (TNameResolutionCache *)((char *)v4 + 120);
  *((_DWORD *)v4 + 24) = GetCurrentThreadId();
  v12 = 1;
  if ( v11 )
  {
    v13 = (TResolutionCacheNode *)*((_QWORD *)v11 + 2);
    while ( v13 != v11 )
    {
      if ( !(unsigned int)TResolutionCacheNode::IsSameName(v13, L"..localmachine") )
      {
        v12 = TResolutionCacheNode::CheckIfNameIsInNodeCacheUsingIp(v13, &v26);
        break;
      }
      if ( v13 )
        v13 = (TResolutionCacheNode *)*((_QWORD *)v13 + 2);
    }
  }
  if ( (*((_DWORD *)v10 + 11))-- == 1 )
    *((_DWORD *)v10 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v10);
  v15 = v24;
  if ( v24 != &v22 )
  {
    do
    {
      v16 = v15;
      v15 = (const unsigned int **)v15[2];
      if ( v16 )
        (*(void (__fastcall **)(const unsigned int **, __int64))*v16)(v16, 1);
    }
    while ( v15 != &v22 );
    v15 = v24;
  }
  v22 = &NCoreLibrary::TLink::`vftable';
  if ( v15 != &v22 && v25 != &v22 )
  {
    v15[3] = (const unsigned int *)v25;
    v25[2] = (const unsigned int *)v24;
    v24 = &v22;
    v25 = &v22;
  }
  v17 = v29;
  if ( v29 != &v27 )
  {
    do
    {
      v18 = v17;
      v17 = (const unsigned int **)v17[2];
      if ( v18 )
        (*(void (__fastcall **)(const unsigned int **, __int64))*v18)(v18, 1);
    }
    while ( v17 != &v27 );
    v17 = v29;
  }
  if ( v17 != &v27 && v30 != &v27 )
  {
    v17[3] = (const unsigned int *)v30;
    v30[2] = (const unsigned int *)v29;
  }
  return v12;
}

```

## disassembly

```asm
0x14000ac00  mov     r11, rsp
0x14000ac03  push    rbp
0x14000ac04  push    rdi
0x14000ac05  lea     rbp, [r11-5Fh]
0x14000ac09  sub     rsp, 98h
0x14000ac10  mov     rax, cs:__security_cookie
0x14000ac17  xor     rax, rsp
0x14000ac1a  mov     [rbp+57h+var_28], rax
0x14000ac1e  mov     rdi, r8
0x14000ac21  test    r8, r8
0x14000ac24  jz      loc_14000AEF5
0x14000ac2a  mov     [r11+8], rbx
0x14000ac2e  lea     rax, [rbp+57h+var_48]
0x14000ac32  mov     [rbp+57h+var_38], rax
0x14000ac36  lea     rax, [rbp+57h+var_48]
0x14000ac3a  mov     [r11+10h], rsi
0x14000ac3e  mov     [r11+20h], r12
0x14000ac42  lea     r12, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x14000ac49  mov     [rbp+57h+var_30], rax
0x14000ac4d  lea     rax, [rbp+57h+var_70]
0x14000ac51  mov     [r11-18h], r13
0x14000ac55  mov     [r11-20h], r14
0x14000ac59  mov     r14, cs:?g_pLocalIpAddressesCache@@3PEAVTNameResolutionCache@@EA; TNameResolutionCache * g_pLocalIpAddressesCache
0x14000ac60  mov     [rbp+57h+var_60], rax
0x14000ac64  mov     rcx, r14; this
0x14000ac67  lea     rax, [rbp+57h+var_70]
0x14000ac6b  mov     [rbp+57h+var_50], 74736C74h
0x14000ac72  mov     [rbp+57h+var_58], rax
0x14000ac76  mov     [rbp+57h+var_48], r12
0x14000ac7a  mov     [rbp+57h+var_40], 6B6E6C74h
0x14000ac81  mov     [rbp+57h+var_78], 74736C74h
0x14000ac88  mov     [rbp+57h+var_70], r12
0x14000ac8c  mov     [rbp+57h+var_68], 6B6E6C74h
0x14000ac93  call    ?IsClusterNode@TNameResolutionCache@@AEAA_NXZ; TNameResolutionCache::IsClusterNode(void)
0x14000ac98  test    al, al
0x14000ac9a  jnz     loc_14000AD34
0x14000aca0  mov     rsi, [r14+98h]
0x14000aca7  mov     [rsp+0A0h+var_20], r15
0x14000acaf  mov     r15d, 1
0x14000acb5  cmp     [rsi+58h], al
0x14000acb8  jz      short loc_14000AD26
0x14000acba  lea     rcx, [rsi+20h]; this
0x14000acbe  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14000acc3  call    cs:__imp_GetTickCount
0x14000acca  nop     dword ptr [rax+rax+00h]
0x14000accf  mov     [rbp+57h+var_80], eax
0x14000acd2  xor     r12d, r12d
0x14000acd5  cmp     r12d, [rsi+8]
0x14000acd9  jnb     short loc_14000AD16
0x14000acdb  mov     rcx, [rsi+18h]
0x14000acdf  lea     rdx, [r12+r12*2]
0x14000ace3  mov     r8, [rcx+rdx*8]
0x14000ace7  test    r8, r8
0x14000acea  jz      short loc_14000AD0E
0x14000acec  sub     eax, [rcx+rdx*8+8]
0x14000acf0  cmp     eax, [rsi+0Ch]
0x14000acf3  jnb     short loc_14000AD0B
0x14000acf5  mov     rdx, r8
0x14000acf8  mov     rcx, rdi
0x14000acfb  call    cs:__imp__o__wcsicmp
0x14000ad02  nop     dword ptr [rax+rax+00h]
0x14000ad07  test    eax, eax
0x14000ad09  jz      short loc_14000AD13
0x14000ad0b  mov     eax, [rbp+57h+var_80]
0x14000ad0e  inc     r12d
0x14000ad11  jmp     short loc_14000ACD5
0x14000ad13  xor     r15d, r15d
0x14000ad16  lea     rcx, [rsi+20h]; this
0x14000ad1a  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x14000ad1f  lea     r12, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x14000ad26  cmp     r15d, 1
0x14000ad2a  mov     r15, [rsp+0A0h+var_20]
0x14000ad32  jnz     short loc_14000AD5C
0x14000ad34  lea     r9, [rbp+57h+var_78]
0x14000ad38  mov     rdx, rdi; unsigned __int16 *
0x14000ad3b  lea     r8, [rbp+57h+var_50]
0x14000ad3f  mov     rcx, r14; this
0x14000ad42  call    ?CacheGetAddrInfo@TNameResolutionCache@@AEAAJPEBGPEAV?$TList@VTStringNode@@@NCoreLibrary@@1@Z; TNameResolutionCache::CacheGetAddrInfo(ushort const *,NCoreLibrary::TList<TStringNode> *,NCoreLibrary::TList<TStringNode> *)
0x14000ad47  cmp     ax, 2AF9h
0x14000ad4b  jnz     short loc_14000AD5C
0x14000ad4d  mov     rcx, [r14+98h]
0x14000ad54  mov     rdx, rdi
0x14000ad57  call    ?AddString@?$TFastCache@VNullCacheEntry@@@@QEAAJPEBGPEAVNullCacheEntry@@@Z; TFastCache<NullCacheEntry>::AddString(ushort const *,NullCacheEntry *)
0x14000ad5c  lea     rbx, [r14+38h]
0x14000ad60  mov     rcx, rbx; lpCriticalSection
0x14000ad63  call    cs:__imp_EnterCriticalSection
0x14000ad6a  nop     dword ptr [rax+rax+00h]
0x14000ad6f  inc     dword ptr [rbx+2Ch]
0x14000ad72  call    cs:__imp_GetCurrentThreadId
0x14000ad79  nop     dword ptr [rax+rax+00h]
0x14000ad7e  mov     r13, [rsp+90h]
0x14000ad86  lea     rdi, [r14+78h]
0x14000ad8a  xor     esi, esi
0x14000ad8c  mov     [rbx+28h], eax
0x14000ad8f  mov     r14d, 1
0x14000ad95  test    rdi, rdi
0x14000ad98  jz      short loc_14000ADD0
0x14000ad9a  mov     rsi, [rdi+10h]
0x14000ad9e  cmp     rsi, rdi
0x14000ada1  jz      short loc_14000ADD0
0x14000ada3  lea     rdx, ?g_cszLocalMachine@@3QBGB; "..localmachine"
0x14000adaa  mov     rcx, rsi; this
0x14000adad  call    ?IsSameName@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsSameName(ushort const *)
0x14000adb2  test    eax, eax
0x14000adb4  jz      short loc_14000ADC1
0x14000adb6  test    rsi, rsi
0x14000adb9  jz      short loc_14000AD9E
0x14000adbb  mov     rsi, [rsi+10h]
0x14000adbf  jmp     short loc_14000AD9E
0x14000adc1  lea     rdx, [rbp+57h+var_50]
0x14000adc5  mov     rcx, rsi
0x14000adc8  call    ?CheckIfNameIsInNodeCacheUsingIp@TResolutionCacheNode@@QEAAJPEAV?$TList@VTStringNode@@@NCoreLibrary@@@Z; TResolutionCacheNode::CheckIfNameIsInNodeCacheUsingIp(NCoreLibrary::TList<TStringNode> *)
0x14000adcd  mov     r14d, eax
0x14000add0  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14000add4  mov     ecx, [rbx+2Ch]
0x14000add7  mov     rsi, [rsp+0A0h+arg_8]
0x14000addf  jnz     short loc_14000ADE8
0x14000ade1  mov     dword ptr [rbx+28h], 0
0x14000ade8  mov     rcx, rbx; lpCriticalSection
0x14000adeb  call    cs:__imp_LeaveCriticalSection
0x14000adf2  nop     dword ptr [rax+rax+00h]
0x14000adf7  mov     rbx, [rbp+57h+var_60]
0x14000adfb  lea     rax, [rbp+57h+var_70]
0x14000adff  cmp     rbx, rax
0x14000ae02  jz      short loc_14000AE2D
0x14000ae04  mov     rcx, rbx
0x14000ae07  mov     rbx, [rbx+10h]
0x14000ae0b  test    rcx, rcx
0x14000ae0e  jz      short loc_14000AE20
0x14000ae10  mov     rax, [rcx]
0x14000ae13  mov     edx, 1
0x14000ae18  mov     rax, [rax]
0x14000ae1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae20  lea     rax, [rbp+57h+var_70]
0x14000ae24  cmp     rbx, rax
0x14000ae27  jnz     short loc_14000AE04
0x14000ae29  mov     rbx, [rbp+57h+var_60]
0x14000ae2d  lea     rax, [rbp+57h+var_70]
0x14000ae31  mov     [rbp+57h+var_70], r12
0x14000ae35  mov     r12, [rsp+0A0h+arg_18]
0x14000ae3d  cmp     rbx, rax
0x14000ae40  jz      short loc_14000AE6F
0x14000ae42  mov     rax, [rbp+57h+var_58]
0x14000ae46  lea     rcx, [rbp+57h+var_70]
0x14000ae4a  cmp     rax, rcx
0x14000ae4d  jz      short loc_14000AE6F
0x14000ae4f  mov     [rbx+18h], rax
0x14000ae53  mov     rax, [rbp+57h+var_58]
0x14000ae57  mov     rcx, [rbp+57h+var_60]
0x14000ae5b  mov     [rax+10h], rcx
0x14000ae5f  lea     rax, [rbp+57h+var_70]
0x14000ae63  mov     [rbp+57h+var_60], rax
0x14000ae67  lea     rax, [rbp+57h+var_70]
0x14000ae6b  mov     [rbp+57h+var_58], rax
0x14000ae6f  mov     rbx, [rbp+57h+var_38]
0x14000ae73  lea     rax, [rbp+57h+var_48]
0x14000ae77  cmp     rbx, rax
0x14000ae7a  jz      short loc_14000AEA5
0x14000ae7c  mov     rcx, rbx
0x14000ae7f  mov     rbx, [rbx+10h]
0x14000ae83  test    rcx, rcx
0x14000ae86  jz      short loc_14000AE98
0x14000ae88  mov     rax, [rcx]
0x14000ae8b  mov     edx, 1
0x14000ae90  mov     rax, [rax]
0x14000ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae98  lea     rax, [rbp+57h+var_48]
0x14000ae9c  cmp     rbx, rax
0x14000ae9f  jnz     short loc_14000AE7C
0x14000aea1  mov     rbx, [rbp+57h+var_38]
0x14000aea5  lea     rax, [rbp+57h+var_48]
0x14000aea9  cmp     rbx, rax
0x14000aeac  jz      short loc_14000AECB
0x14000aeae  mov     rax, [rbp+57h+var_30]
0x14000aeb2  lea     rcx, [rbp+57h+var_48]
0x14000aeb6  cmp     rax, rcx
0x14000aeb9  jz      short loc_14000AECB
0x14000aebb  mov     [rbx+18h], rax
0x14000aebf  mov     rax, [rbp+57h+var_30]
0x14000aec3  mov     rcx, [rbp+57h+var_38]
0x14000aec7  mov     [rax+10h], rcx
0x14000aecb  mov     rbx, [rsp+0A0h+arg_0]
0x14000aed3  mov     eax, r14d
0x14000aed6  mov     r14, [rsp+0A0h+var_18]
0x14000aede  mov     rcx, [rbp+57h+var_28]
0x14000aee2  xor     rcx, rsp; StackCookie
0x14000aee5  call    __security_check_cookie
0x14000aeea  add     rsp, 98h
0x14000aef1  pop     rdi
0x14000aef2  pop     rbp
0x14000aef3  retn
0x14000aef5  mov     eax, 80070057h
0x14000aefa  jmp     short loc_14000AEDE
```
