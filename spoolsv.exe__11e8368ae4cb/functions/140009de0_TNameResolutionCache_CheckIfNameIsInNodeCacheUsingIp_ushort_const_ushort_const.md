# TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(ushort const *,ushort const *)

- ea: `0x140009de0`
- end: `0x14000a0be`
- name: `?CheckIfNameIsInNodeCacheUsingIp@TNameResolutionCache@@QEAAJPEBG0@Z`
- size: `734`
- prototype: `int(TNameResolutionCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140009cb0`

## callees

- `0x140007cec`
- `0x1400095cc`
- `0x140009930`
- `0x140009de0`
- `0x14000d760`
- `0x14000eae0`
- `0x140017b58`
- `0x14002abc0`
- `0x14006fcb0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009ed6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009ed6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009f41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009f41`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009ea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009ea3`

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
0x140009de0  mov     r11, rsp
0x140009de3  push    rbp
0x140009de4  push    rdi
0x140009de5  lea     rbp, [r11-5Fh]
0x140009de9  sub     rsp, 98h
0x140009df0  mov     rax, cs:__security_cookie
0x140009df7  xor     rax, rsp
0x140009dfa  mov     [rbp+57h+var_28], rax
0x140009dfe  mov     rdi, r8
0x140009e01  test    r8, r8
0x140009e04  jz      loc_14000A0B7
0x140009e0a  mov     [r11+8], rbx
0x140009e0e  lea     rax, [rbp+57h+var_48]
0x140009e12  mov     [rbp+57h+var_38], rax
0x140009e16  lea     rax, [rbp+57h+var_48]
0x140009e1a  mov     [r11+10h], rsi
0x140009e1e  mov     [r11+20h], r12
0x140009e22  lea     r12, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140009e29  mov     [rbp+57h+var_30], rax
0x140009e2d  lea     rax, [rbp+57h+var_70]
0x140009e31  mov     [r11-18h], r13
0x140009e35  mov     [r11-20h], r14
0x140009e39  mov     r14, cs:?g_pLocalIpAddressesCache@@3PEAVTNameResolutionCache@@EA; TNameResolutionCache * g_pLocalIpAddressesCache
0x140009e40  mov     [rbp+57h+var_60], rax
0x140009e44  mov     rcx, r14; this
0x140009e47  lea     rax, [rbp+57h+var_70]
0x140009e4b  mov     [rbp+57h+var_50], 74736C74h
0x140009e52  mov     [rbp+57h+var_58], rax
0x140009e56  mov     [rbp+57h+var_48], r12
0x140009e5a  mov     [rbp+57h+var_40], 6B6E6C74h
0x140009e61  mov     [rbp+57h+var_78], 74736C74h
0x140009e68  mov     [rbp+57h+var_70], r12
0x140009e6c  mov     [rbp+57h+var_68], 6B6E6C74h
0x140009e73  call    ?IsClusterNode@TNameResolutionCache@@AEAA_NXZ; TNameResolutionCache::IsClusterNode(void)
0x140009e78  test    al, al
0x140009e7a  jnz     loc_140009F09
0x140009e80  mov     rsi, [r14+98h]
0x140009e87  mov     [rsp+0A0h+var_20], r15
0x140009e8f  mov     r15d, 1
0x140009e95  cmp     [rsi+58h], al
0x140009e98  jz      short loc_140009EFB
0x140009e9a  lea     rcx, [rsi+20h]; this
0x140009e9e  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009ea3  call    cs:__imp_GetTickCount
0x140009ea9  mov     [rbp+57h+var_80], eax
0x140009eac  xor     r12d, r12d
0x140009eaf  nop
0x140009eb0  cmp     r12d, [rsi+8]
0x140009eb4  jnb     short loc_140009EEB
0x140009eb6  mov     rcx, [rsi+18h]
0x140009eba  lea     rdx, [r12+r12*2]
0x140009ebe  mov     r8, [rcx+rdx*8]
0x140009ec2  test    r8, r8
0x140009ec5  jz      short loc_140009EE3
0x140009ec7  sub     eax, [rcx+rdx*8+8]
0x140009ecb  cmp     eax, [rsi+0Ch]
0x140009ece  jnb     short loc_140009EE0
0x140009ed0  mov     rdx, r8
0x140009ed3  mov     rcx, rdi
0x140009ed6  call    cs:__imp__o__wcsicmp
0x140009edc  test    eax, eax
0x140009ede  jz      short loc_140009EE8
0x140009ee0  mov     eax, [rbp+57h+var_80]
0x140009ee3  inc     r12d
0x140009ee6  jmp     short loc_140009EB0
0x140009ee8  xor     r15d, r15d
0x140009eeb  lea     rcx, [rsi+20h]; this
0x140009eef  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x140009ef4  lea     r12, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140009efb  cmp     r15d, 1
0x140009eff  mov     r15, [rsp+0A0h+var_20]
0x140009f07  jnz     short loc_140009F31
0x140009f09  lea     r9, [rbp+57h+var_78]
0x140009f0d  mov     rdx, rdi; unsigned __int16 *
0x140009f10  lea     r8, [rbp+57h+var_50]
0x140009f14  mov     rcx, r14; this
0x140009f17  call    ?CacheGetAddrInfo@TNameResolutionCache@@AEAAJPEBGPEAV?$TList@VTStringNode@@@NCoreLibrary@@1@Z; TNameResolutionCache::CacheGetAddrInfo(ushort const *,NCoreLibrary::TList<TStringNode> *,NCoreLibrary::TList<TStringNode> *)
0x140009f1c  cmp     ax, 2AF9h
0x140009f20  jnz     short loc_140009F31
0x140009f22  mov     rcx, [r14+98h]
0x140009f29  mov     rdx, rdi
0x140009f2c  call    ?AddString@?$TFastCache@VNullCacheEntry@@@@QEAAJPEBGPEAVNullCacheEntry@@@Z; TFastCache<NullCacheEntry>::AddString(ushort const *,NullCacheEntry *)
0x140009f31  lea     rbx, [r14+38h]
0x140009f35  mov     rcx, rbx; lpCriticalSection
0x140009f38  call    cs:__imp_EnterCriticalSection
0x140009f3e  inc     dword ptr [rbx+2Ch]
0x140009f41  call    cs:__imp_GetCurrentThreadId
0x140009f47  mov     r13, [rsp+90h]
0x140009f4f  lea     rdi, [r14+78h]
0x140009f53  xor     esi, esi
0x140009f55  mov     [rbx+28h], eax
0x140009f58  mov     r14d, 1
0x140009f5e  test    rdi, rdi
0x140009f61  jz      short loc_140009F99
0x140009f63  mov     rsi, [rdi+10h]
0x140009f67  cmp     rsi, rdi
0x140009f6a  jz      short loc_140009F99
0x140009f6c  lea     rdx, ?g_cszLocalMachine@@3QBGB; "..localmachine"
0x140009f73  mov     rcx, rsi; this
0x140009f76  call    ?IsSameName@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsSameName(ushort const *)
0x140009f7b  test    eax, eax
0x140009f7d  jz      short loc_140009F8A
0x140009f7f  test    rsi, rsi
0x140009f82  jz      short loc_140009F67
0x140009f84  mov     rsi, [rsi+10h]
0x140009f88  jmp     short loc_140009F67
0x140009f8a  lea     rdx, [rbp+57h+var_50]
0x140009f8e  mov     rcx, rsi
0x140009f91  call    ?CheckIfNameIsInNodeCacheUsingIp@TResolutionCacheNode@@QEAAJPEAV?$TList@VTStringNode@@@NCoreLibrary@@@Z; TResolutionCacheNode::CheckIfNameIsInNodeCacheUsingIp(NCoreLibrary::TList<TStringNode> *)
0x140009f96  mov     r14d, eax
0x140009f99  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x140009f9d  mov     ecx, [rbx+2Ch]
0x140009fa0  mov     rsi, [rsp+0A0h+arg_8]
0x140009fa8  jnz     short loc_140009FB1
0x140009faa  mov     dword ptr [rbx+28h], 0
0x140009fb1  mov     rcx, rbx; lpCriticalSection
0x140009fb4  call    cs:__imp_LeaveCriticalSection
0x140009fba  mov     rbx, [rbp+57h+var_60]
0x140009fbe  lea     rax, [rbp+57h+var_70]
0x140009fc2  cmp     rbx, rax
0x140009fc5  jz      short loc_140009FF0
0x140009fc7  mov     rcx, rbx
0x140009fca  mov     rbx, [rbx+10h]
0x140009fce  test    rcx, rcx
0x140009fd1  jz      short loc_140009FE3
0x140009fd3  mov     rax, [rcx]
0x140009fd6  mov     edx, 1
0x140009fdb  mov     rax, [rax]
0x140009fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fe3  lea     rax, [rbp+57h+var_70]
0x140009fe7  cmp     rbx, rax
0x140009fea  jnz     short loc_140009FC7
0x140009fec  mov     rbx, [rbp+57h+var_60]
0x140009ff0  lea     rax, [rbp+57h+var_70]
0x140009ff4  mov     [rbp+57h+var_70], r12
0x140009ff8  mov     r12, [rsp+0A0h+arg_18]
0x14000a000  cmp     rbx, rax
0x14000a003  jz      short loc_14000A032
0x14000a005  mov     rax, [rbp+57h+var_58]
0x14000a009  lea     rcx, [rbp+57h+var_70]
0x14000a00d  cmp     rax, rcx
0x14000a010  jz      short loc_14000A032
0x14000a012  mov     [rbx+18h], rax
0x14000a016  mov     rax, [rbp+57h+var_58]
0x14000a01a  mov     rcx, [rbp+57h+var_60]
0x14000a01e  mov     [rax+10h], rcx
0x14000a022  lea     rax, [rbp+57h+var_70]
0x14000a026  mov     [rbp+57h+var_60], rax
0x14000a02a  lea     rax, [rbp+57h+var_70]
0x14000a02e  mov     [rbp+57h+var_58], rax
0x14000a032  mov     rbx, [rbp+57h+var_38]
0x14000a036  lea     rax, [rbp+57h+var_48]
0x14000a03a  cmp     rbx, rax
0x14000a03d  jz      short loc_14000A068
0x14000a03f  mov     rcx, rbx
0x14000a042  mov     rbx, [rbx+10h]
0x14000a046  test    rcx, rcx
0x14000a049  jz      short loc_14000A05B
0x14000a04b  mov     rax, [rcx]
0x14000a04e  mov     edx, 1
0x14000a053  mov     rax, [rax]
0x14000a056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a05b  lea     rax, [rbp+57h+var_48]
0x14000a05f  cmp     rbx, rax
0x14000a062  jnz     short loc_14000A03F
0x14000a064  mov     rbx, [rbp+57h+var_38]
0x14000a068  lea     rax, [rbp+57h+var_48]
0x14000a06c  cmp     rbx, rax
0x14000a06f  jz      short loc_14000A08E
0x14000a071  mov     rax, [rbp+57h+var_30]
0x14000a075  lea     rcx, [rbp+57h+var_48]
0x14000a079  cmp     rax, rcx
0x14000a07c  jz      short loc_14000A08E
0x14000a07e  mov     [rbx+18h], rax
0x14000a082  mov     rax, [rbp+57h+var_30]
0x14000a086  mov     rcx, [rbp+57h+var_38]
0x14000a08a  mov     [rax+10h], rcx
0x14000a08e  mov     rbx, [rsp+0A0h+arg_0]
0x14000a096  mov     eax, r14d
0x14000a099  mov     r14, [rsp+0A0h+var_18]
0x14000a0a1  mov     rcx, [rbp+57h+var_28]
0x14000a0a5  xor     rcx, rsp; StackCookie
0x14000a0a8  call    __security_check_cookie
0x14000a0ad  add     rsp, 98h
0x14000a0b4  pop     rdi
0x14000a0b5  pop     rbp
0x14000a0b6  retn
0x14000a0b7  mov     eax, 80070057h
0x14000a0bc  jmp     short loc_14000A0A1
```
