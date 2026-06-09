# TNameResolutionCache::CreateAndAddNode(ushort const *,int,int)

- ea: `0x140009190`
- end: `0x1400095c4`
- name: `?CreateAndAddNode@TNameResolutionCache@@QEAAJPEBGHH@Z`
- size: `1076`
- prototype: `__int64 __fastcall(TNameResolutionCache *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14006fe04`

## callees

- `0x140007c00`
- `0x140007cec`
- `0x140009190`
- `0x1400095cc`
- `0x1400095f0`
- `0x1400097a8`
- `0x140009930`
- `0x140009c08`
- `0x14000eae0`
- `0x140011ab8`
- `0x140017080`
- `0x14002a830`
- `0x14002a870`
- `0x14006fcb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009286`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009361`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400093db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009286`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009361`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400093db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000958b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000958b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400093f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400093f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400093f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400093f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009327`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009327`

## pseudocode

```c
__int64 __fastcall TNameResolutionCache::CreateAndAddNode(
        TNameResolutionCache *this,
        unsigned __int16 *a2,
        int a3,
        int a4)
{
  TResolutionCacheNode *v9; // rax
  TResolutionCacheNode *v10; // rax
  __int64 v11; // rcx
  TResolutionCacheNode *v12; // rbp
  int AddrInfo; // esi
  __int64 v14; // rsi
  unsigned __int64 v15; // rax
  __int64 i; // r13
  __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  NCoreLibrary::TReferenceCount *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rsi
  DWORD TickCount; // eax
  __int64 j; // r13
  __int64 v24; // rcx
  char *v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r15
  TResolutionCacheNode *v30; // rax
  char *v31; // rdx
  char *v32; // r14
  TResolutionCacheNode *v33; // rcx
  char *v34; // r8
  __int64 v35; // rdx
  TResolutionCacheNode *v36; // rcx
  int v38; // [rsp+20h] [rbp-48h]
  __int64 v39; // [rsp+28h] [rbp-40h]
  __int64 v40; // [rsp+30h] [rbp-38h] BYREF
  __int64 v41; // [rsp+38h] [rbp-30h]
  __int64 v42; // [rsp+78h] [rbp+10h]
  DWORD v43; // [rsp+78h] [rbp+10h]

  if ( !a2 )
    return 2147942487LL;
  v9 = (TResolutionCacheNode *)operator new(0x50u);
  if ( !v9 )
    return (unsigned int)-2147024882;
  v10 = TResolutionCacheNode::TResolutionCacheNode(v9, a2, a3);
  if ( (v12 = v10) == 0 )
    return (unsigned int)-2147024882;
  AddrInfo = *((_DWORD *)v10 + 18);
  if ( AddrInfo < 0 )
    goto LABEL_72;
  if ( a4 )
  {
    TFastCache<AddrInfoCacheEntry>::ExpireElement(v11, a2);
    v14 = *((_QWORD *)this + 19);
    if ( *(_BYTE *)(v14 + 88) )
    {
      v15 = -1;
      do
        ++v15;
      while ( a2[v15] );
      if ( v15 <= *(unsigned int *)(v14 + 16) )
      {
        NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)(v14 + 32));
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v14 + 8); i = (unsigned int)(i + 1) )
        {
          v42 = 24 * i;
          v17 = *(_QWORD *)(*(_QWORD *)(v14 + 24) + 24 * i);
          if ( v17 && !(unsigned int)_o__wcsicmp(a2, v17) )
          {
            operator delete(*(void **)(*(_QWORD *)(v14 + 24) + 24 * i), v18);
            *(_QWORD *)(*(_QWORD *)(v14 + 24) + 24 * i) = 0;
            v19 = *(NCoreLibrary::TReferenceCount **)(*(_QWORD *)(v14 + 24) + v42 + 16);
            if ( v19 )
            {
              NCoreLibrary::TReferenceCount::Release(v19);
              *(_QWORD *)(*(_QWORD *)(v14 + 24) + v42 + 16) = 0;
            }
            break;
          }
        }
        NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v14 + 32));
      }
    }
  }
  AddrInfo = -2147024809;
  v40 = *((_QWORD *)v12 + 7);
  if ( !v40 )
    goto LABEL_36;
  v20 = *((_QWORD *)v12 + 8);
  v39 = v20;
  if ( !v20 )
    goto LABEL_36;
  v21 = *((_QWORD *)this + 19);
  if ( !*(_BYTE *)(v21 + 88) )
  {
LABEL_33:
    AddrInfo = TNameResolutionCache::CacheGetAddrInfo(this, a2, v40, v20);
    if ( (_WORD)AddrInfo == 11001 )
      TFastCache<NullCacheEntry>::AddString(*((_QWORD *)this + 19), a2);
    if ( AddrInfo >= 0 )
    {
LABEL_38:
      v25 = (char *)this + 56;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      ++*((_DWORD *)this + 25);
      *((_DWORD *)this + 24) = GetCurrentThreadId();
      if ( a4 )
      {
        AddrInfo = TNameResolutionCache::DeleteNode(this, a2);
        if ( AddrInfo < 0 )
        {
LABEL_69:
          if ( (*((_DWORD *)v25 + 11))-- == 1 )
            *((_DWORD *)v25 + 10) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)v25);
          goto LABEL_72;
        }
      }
      else
      {
        NCoreLibrary::TCriticalSection::Enter((TNameResolutionCache *)((char *)this + 56));
        v29 = 0;
        v40 = (__int64)this + 120;
        AddrInfo = 1;
        v41 = 0;
        if ( this == (TNameResolutionCache *)-120LL )
          goto LABEL_44;
        v29 = *((_QWORD *)this + 17);
LABEL_43:
        v41 = v29;
        while ( 1 )
        {
LABEL_44:
          if ( (unsigned int)NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(&v40, v26, v27, v28) )
          {
            NCoreLibrary::TCriticalSection::Leave((TNameResolutionCache *)((char *)this + 56));
            goto LABEL_52;
          }
          AddrInfo = TResolutionCacheNode::IsSameName((TResolutionCacheNode *)v29, a2);
          if ( !AddrInfo )
            break;
          if ( v29 )
          {
            v29 = *(_QWORD *)(v29 + 16);
            goto LABEL_43;
          }
        }
        ++*(_DWORD *)(v29 + 76);
        NCoreLibrary::TCriticalSection::Leave((TNameResolutionCache *)((char *)this + 56));
        if ( v29 )
          TResolutionCacheNode::Release((TResolutionCacheNode *)v29);
LABEL_52:
        if ( AddrInfo != 1 )
          goto LABEL_69;
      }
      v30 = (TResolutionCacheNode *)*((_QWORD *)v12 + 2);
      if ( a3 )
      {
        if ( v30 )
        {
          v31 = (char *)v12 + 24;
          if ( *((_QWORD *)v12 + 3) )
          {
            v32 = (char *)this + 120;
            if ( v30 != v12 )
            {
              v33 = (TResolutionCacheNode *)*((_QWORD *)v12 + 3);
              v31 = (char *)v12 + 24;
              if ( v33 != v12 )
              {
                *((_QWORD *)v30 + 3) = v33;
                *(_QWORD *)(*(_QWORD *)v31 + 16LL) = *((_QWORD *)v12 + 2);
                *((_QWORD *)v12 + 2) = v12;
                *(_QWORD *)v31 = v12;
              }
            }
            AddrInfo = 0;
            *(_QWORD *)(*((_QWORD *)v32 + 2) + 24LL) = v12;
            *((_QWORD *)v12 + 2) = *((_QWORD *)v32 + 2);
            *(_QWORD *)v31 = v32;
            *((_QWORD *)v32 + 2) = v12;
            goto LABEL_67;
          }
        }
      }
      else if ( v30 )
      {
        v34 = (char *)v12 + 24;
        if ( *((_QWORD *)v12 + 3) )
        {
          v35 = *((_QWORD *)this + 18);
          if ( v30 != v12 )
          {
            v36 = (TResolutionCacheNode *)*((_QWORD *)v12 + 3);
            v34 = (char *)v12 + 24;
            if ( v36 != v12 )
            {
              *((_QWORD *)v30 + 3) = v36;
              *(_QWORD *)(*(_QWORD *)v34 + 16LL) = *((_QWORD *)v12 + 2);
              *((_QWORD *)v12 + 2) = v12;
              *(_QWORD *)v34 = v12;
            }
          }
          AddrInfo = 0;
          *(_QWORD *)(*(_QWORD *)(v35 + 16) + 24LL) = v12;
          *((_QWORD *)v12 + 2) = *(_QWORD *)(v35 + 16);
          *(_QWORD *)v34 = v35;
          *(_QWORD *)(v35 + 16) = v12;
          goto LABEL_67;
        }
      }
      AddrInfo = -2147467259;
LABEL_67:
      if ( AddrInfo >= 0 )
        ++*((_DWORD *)v12 + 19);
      goto LABEL_69;
    }
LABEL_36:
    if ( (_WORD)AddrInfo != 11001 )
      goto LABEL_72;
    goto LABEL_37;
  }
  v38 = 1;
  NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)(v21 + 32));
  TickCount = GetTickCount();
  v43 = TickCount;
  for ( j = 0; (unsigned int)j < *(_DWORD *)(v21 + 8); j = (unsigned int)(j + 1) )
  {
    v24 = *(_QWORD *)(v21 + 24);
    if ( *(_QWORD *)(v24 + 24 * j) )
    {
      if ( TickCount - *(_DWORD *)(v24 + 24 * j + 8) < *(_DWORD *)(v21 + 12)
        && !(unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v24 + 24 * j)) )
      {
        v38 = 0;
        break;
      }
      TickCount = v43;
    }
  }
  NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v21 + 32));
  if ( v38 == 1 )
  {
    v20 = v39;
    goto LABEL_33;
  }
  AddrInfo = -2147013895;
LABEL_37:
  if ( !(unsigned int)_o__wcsicmp(a2, &Buffer) )
    goto LABEL_38;
LABEL_72:
  TResolutionCacheNode::Release(v12);
  return (unsigned int)AddrInfo;
}

```

## disassembly

```asm
0x140009190  push    rsi
0x140009192  push    rdi
0x140009193  push    r12
0x140009195  push    r14
0x140009197  push    r15
0x140009199  sub     rsp, 40h
0x14000919d  mov     r15d, r9d
0x1400091a0  mov     r12d, r8d
0x1400091a3  mov     rdi, rdx
0x1400091a6  mov     r14, rcx
0x1400091a9  test    rdx, rdx
0x1400091ac  jnz     short loc_1400091C0
0x1400091ae  mov     eax, 80070057h
0x1400091b3  add     rsp, 40h
0x1400091b7  pop     r15
0x1400091b9  pop     r14
0x1400091bb  pop     r12
0x1400091bd  pop     rdi
0x1400091be  pop     rsi
0x1400091bf  retn
0x1400091c0  mov     ecx, 50h ; 'P'; Size
0x1400091c5  mov     [rsp+68h+arg_10], rbp
0x1400091cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400091d2  test    rax, rax
0x1400091d5  jz      loc_1400095A8
0x1400091db  mov     r8d, r12d; int
0x1400091de  mov     rdx, rdi; unsigned __int16 *
0x1400091e1  mov     rcx, rax; this
0x1400091e4  call    ??0TResolutionCacheNode@@QEAA@PEBGH@Z; TResolutionCacheNode::TResolutionCacheNode(ushort const *,int)
0x1400091e9  mov     rbp, rax
0x1400091ec  test    rax, rax
0x1400091ef  jz      loc_1400095A8
0x1400091f5  mov     esi, [rax+48h]
0x1400091f8  test    esi, esi
0x1400091fa  js      loc_14000959E
0x140009200  mov     [rsp+68h+arg_0], rbx
0x140009205  mov     [rsp+68h+arg_18], r13
0x14000920d  test    r15d, r15d
0x140009210  jz      loc_1400092DC
0x140009216  mov     rdx, rdi
0x140009219  call    ?ExpireElement@?$TFastCache@VAddrInfoCacheEntry@@@@QEAAJPEBG@Z; TFastCache<AddrInfoCacheEntry>::ExpireElement(ushort const *)
0x14000921e  mov     rsi, [r14+98h]
0x140009225  cmp     byte ptr [rsi+58h], 0
0x140009229  jz      loc_1400092DC
0x14000922f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140009236  inc     rax
0x140009239  cmp     word ptr [rdi+rax*2], 0
0x14000923e  jnz     short loc_140009236
0x140009240  mov     ecx, [rsi+10h]
0x140009243  cmp     rax, rcx
0x140009246  ja      loc_1400092DC
0x14000924c  lea     rcx, [rsi+20h]; this
0x140009250  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009255  xor     r13d, r13d
0x140009258  cmp     r13d, [rsi+8]
0x14000925c  jnb     short loc_1400092D3
0x14000925e  lea     rcx, ds:0[r13*2]
0x140009266  add     rcx, r13
0x140009269  lea     rax, ds:0[rcx*8]
0x140009271  mov     [rsp+68h+arg_8], rax
0x140009276  mov     rax, [rsi+18h]
0x14000927a  mov     rdx, [rax+rcx*8]
0x14000927e  test    rdx, rdx
0x140009281  jz      short loc_140009290
0x140009283  mov     rcx, rdi
0x140009286  call    cs:__imp__o__wcsicmp
0x14000928c  test    eax, eax
0x14000928e  jz      short loc_140009295
0x140009290  inc     r13d
0x140009293  jmp     short loc_140009258
0x140009295  mov     rcx, [rsi+18h]
0x140009299  mov     r13, [rsp+68h+arg_8]
0x14000929e  mov     rcx, [rcx+r13]; void *
0x1400092a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400092a7  mov     rax, [rsi+18h]
0x1400092ab  mov     qword ptr [rax+r13], 0
0x1400092b3  mov     rax, [rsi+18h]
0x1400092b7  mov     rcx, [rax+r13+10h]; this
0x1400092bc  test    rcx, rcx
0x1400092bf  jz      short loc_1400092D3
0x1400092c1  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1400092c6  mov     rax, [rsi+18h]
0x1400092ca  mov     qword ptr [rax+r13+10h], 0
0x1400092d3  lea     rcx, [rsi+20h]; this
0x1400092d7  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x1400092dc  mov     rax, [rbp+38h]
0x1400092e0  mov     esi, 80070057h
0x1400092e5  mov     [rsp+68h+var_38], rax
0x1400092ea  test    rax, rax
0x1400092ed  jz      loc_1400093C6
0x1400092f3  mov     rax, [rbp+40h]
0x1400092f7  mov     [rsp+68h+var_40], rax
0x1400092fc  test    rax, rax
0x1400092ff  jz      loc_1400093C6
0x140009305  mov     rsi, [r14+98h]
0x14000930c  cmp     byte ptr [rsi+58h], 0
0x140009310  jz      loc_140009398
0x140009316  lea     rcx, [rsi+20h]; this
0x14000931a  mov     [rsp+68h+var_48], 1
0x140009322  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009327  call    cs:__imp_GetTickCount
0x14000932d  mov     dword ptr [rsp+68h+arg_8], eax
0x140009331  xor     r13d, r13d
0x140009334  cmp     r13d, [rsi+8]
0x140009338  jnb     short loc_14000937C
0x14000933a  mov     rcx, [rsi+18h]
0x14000933e  lea     rdx, ds:0[r13*2]
0x140009346  add     rdx, r13
0x140009349  mov     r8, [rcx+rdx*8]
0x14000934d  test    r8, r8
0x140009350  jz      short loc_14000936F
0x140009352  sub     eax, [rcx+rdx*8+8]
0x140009356  cmp     eax, [rsi+0Ch]
0x140009359  jnb     short loc_14000936B
0x14000935b  mov     rdx, r8
0x14000935e  mov     rcx, rdi
0x140009361  call    cs:__imp__o__wcsicmp
0x140009367  test    eax, eax
0x140009369  jz      short loc_140009374
0x14000936b  mov     eax, dword ptr [rsp+68h+arg_8]
0x14000936f  inc     r13d
0x140009372  jmp     short loc_140009334
0x140009374  mov     [rsp+68h+var_48], 0
0x14000937c  lea     rcx, [rsi+20h]; this
0x140009380  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x140009385  cmp     [rsp+68h+var_48], 1
0x14000938a  jz      short loc_140009393
0x14000938c  mov     esi, 80072AF9h
0x140009391  jmp     short loc_1400093D1
0x140009393  mov     rax, [rsp+68h+var_40]
0x140009398  mov     r8, [rsp+68h+var_38]
0x14000939d  mov     r9, rax
0x1400093a0  mov     rdx, rdi; unsigned __int16 *
0x1400093a3  mov     rcx, r14; this
0x1400093a6  call    ?CacheGetAddrInfo@TNameResolutionCache@@AEAAJPEBGPEAV?$TList@VTStringNode@@@NCoreLibrary@@1@Z; TNameResolutionCache::CacheGetAddrInfo(ushort const *,NCoreLibrary::TList<TStringNode> *,NCoreLibrary::TList<TStringNode> *)
0x1400093ab  mov     esi, eax
0x1400093ad  cmp     ax, 2AF9h
0x1400093b1  jnz     short loc_1400093C2
0x1400093b3  mov     rcx, [r14+98h]
0x1400093ba  mov     rdx, rdi
0x1400093bd  call    ?AddString@?$TFastCache@VNullCacheEntry@@@@QEAAJPEBGPEAVNullCacheEntry@@@Z; TFastCache<NullCacheEntry>::AddString(ushort const *,NullCacheEntry *)
0x1400093c2  test    esi, esi
0x1400093c4  jns     short loc_1400093E9
0x1400093c6  cmp     si, 2AF9h
0x1400093cb  jnz     loc_140009591
0x1400093d1  lea     rdx, Buffer
0x1400093d8  mov     rcx, rdi
0x1400093db  call    cs:__imp__o__wcsicmp
0x1400093e1  test    eax, eax
0x1400093e3  jnz     loc_140009591
0x1400093e9  lea     rbx, [r14+38h]
0x1400093ed  mov     rcx, rbx; lpCriticalSection
0x1400093f0  call    cs:__imp_EnterCriticalSection
0x1400093f6  inc     dword ptr [rbx+2Ch]
0x1400093f9  call    cs:__imp_GetCurrentThreadId
0x1400093ff  mov     [rbx+28h], eax
0x140009402  test    r15d, r15d
0x140009405  jz      short loc_140009421
0x140009407  mov     rdx, rdi; unsigned __int16 *
0x14000940a  mov     rcx, r14; this
0x14000940d  call    ?DeleteNode@TNameResolutionCache@@QEAAJPEBG@Z; TNameResolutionCache::DeleteNode(ushort const *)
0x140009412  mov     esi, eax
0x140009414  test    eax, eax
0x140009416  js      loc_140009578
0x14000941c  jmp     loc_1400094AA
0x140009421  mov     rcx, rbx; this
0x140009424  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009429  lea     rax, [r14+78h]
0x14000942d  xor     r15d, r15d
0x140009430  mov     [rsp+68h+var_38], rax
0x140009435  mov     esi, 1
0x14000943a  mov     [rsp+68h+var_30], r15
0x14000943f  test    rax, rax
0x140009442  jz      short loc_14000944D
0x140009444  mov     r15, [rax+10h]
0x140009448  mov     [rsp+68h+var_30], r15
0x14000944d  lea     rcx, [rsp+68h+var_38]
0x140009452  call    ?IsDone@TIterator@?$TList@VTResolutionCacheNode@@@NCoreLibrary@@QEBAHXZ; NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(void)
0x140009457  test    eax, eax
0x140009459  jnz     short loc_140009485
0x14000945b  mov     rdx, rdi; unsigned __int16 *
0x14000945e  mov     rcx, r15; this
0x140009461  call    ?IsSameName@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsSameName(ushort const *)
0x140009466  mov     esi, eax
0x140009468  test    eax, eax
0x14000946a  jz      short loc_140009477
0x14000946c  test    r15, r15
0x14000946f  jz      short loc_14000944D
0x140009471  mov     r15, [r15+10h]
0x140009475  jmp     short loc_140009448
0x140009477  inc     dword ptr [r15+4Ch]
0x14000947b  mov     rcx, rbx; this
0x14000947e  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x140009483  jmp     short loc_140009494
0x140009485  mov     rcx, rbx; this
0x140009488  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x14000948d  xor     r15d, r15d
0x140009490  test    esi, esi
0x140009492  jnz     short loc_1400094A1
0x140009494  test    r15, r15
0x140009497  jz      short loc_1400094A1
0x140009499  mov     rcx, r15; this
0x14000949c  call    ?Release@TResolutionCacheNode@@QEAAKXZ; TResolutionCacheNode::Release(void)
0x1400094a1  cmp     esi, 1
0x1400094a4  jnz     loc_140009578
0x1400094aa  mov     rax, [rbp+10h]
0x1400094ae  test    r12d, r12d
0x1400094b1  jz      short loc_140009512
0x1400094b3  test    rax, rax
0x1400094b6  jz      loc_14000956C
0x1400094bc  cmp     qword ptr [rbp+18h], 0
0x1400094c1  lea     rdx, [rbp+18h]
0x1400094c5  jz      loc_14000956C
0x1400094cb  add     r14, 78h ; 'x'
0x1400094cf  cmp     rax, rbp
0x1400094d2  jz      short loc_1400094F7
0x1400094d4  mov     rcx, [rbp+18h]
0x1400094d8  lea     rdx, [rbp+18h]
0x1400094dc  cmp     rcx, rbp
0x1400094df  jz      short loc_1400094F7
0x1400094e1  mov     [rax+18h], rcx
0x1400094e5  mov     rcx, [rdx]
0x1400094e8  mov     rax, [rbp+10h]
0x1400094ec  mov     [rcx+10h], rax
0x1400094f0  mov     [rbp+10h], rbp
0x1400094f4  mov     [rdx], rbp
0x1400094f7  mov     rax, [r14+10h]
0x1400094fb  xor     esi, esi
0x1400094fd  mov     [rax+18h], rbp
0x140009501  mov     rax, [r14+10h]
0x140009505  mov     [rbp+10h], rax
0x140009509  mov     [rdx], r14
0x14000950c  mov     [r14+10h], rbp
0x140009510  jmp     short loc_140009571
0x140009512  test    rax, rax
0x140009515  jz      short loc_14000956C
0x140009517  cmp     qword ptr [rbp+18h], 0
0x14000951c  lea     r8, [rbp+18h]
0x140009520  jz      short loc_14000956C
0x140009522  mov     rdx, [r14+90h]
0x140009529  cmp     rax, rbp
0x14000952c  jz      short loc_140009551
0x14000952e  mov     rcx, [rbp+18h]
0x140009532  lea     r8, [rbp+18h]
0x140009536  cmp     rcx, rbp
0x140009539  jz      short loc_140009551
0x14000953b  mov     [rax+18h], rcx
0x14000953f  mov     rcx, [r8]
0x140009542  mov     rax, [rbp+10h]
0x140009546  mov     [rcx+10h], rax
0x14000954a  mov     [rbp+10h], rbp
0x14000954e  mov     [r8], rbp
0x140009551  mov     rax, [rdx+10h]
0x140009555  xor     esi, esi
0x140009557  mov     [rax+18h], rbp
0x14000955b  mov     rax, [rdx+10h]
0x14000955f  mov     [rbp+10h], rax
0x140009563  mov     [r8], rdx
0x140009566  mov     [rdx+10h], rbp
0x14000956a  jmp     short loc_140009571
0x14000956c  mov     esi, 80004005h
0x140009571  test    esi, esi
0x140009573  js      short loc_140009578
0x140009575  inc     dword ptr [rbp+4Ch]
0x140009578  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14000957c  mov     eax, [rbx+2Ch]
0x14000957f  jnz     short loc_140009588
0x140009581  mov     dword ptr [rbx+28h], 0
0x140009588  mov     rcx, rbx; lpCriticalSection
0x14000958b  call    cs:__imp_LeaveCriticalSection
0x140009591  mov     rbx, [rsp+68h+arg_0]
0x140009596  mov     r13, [rsp+68h+arg_18]
0x14000959e  mov     rcx, rbp; this
0x1400095a1  call    ?Release@TResolutionCacheNode@@QEAAKXZ; TResolutionCacheNode::Release(void)
0x1400095a6  jmp     short loc_1400095AD
0x1400095a8  mov     esi, 8007000Eh
0x1400095ad  mov     rbp, [rsp+68h+arg_10]
0x1400095b5  mov     eax, esi
0x1400095b7  add     rsp, 40h
0x1400095bb  pop     r15
0x1400095bd  pop     r14
0x1400095bf  pop     r12
0x1400095c1  pop     rdi
0x1400095c2  pop     rsi
0x1400095c3  retn
```
