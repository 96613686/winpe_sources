# TNameResolutionCache::CreateAndAddNode(ushort const *,int,int)

- ea: `0x140009e10`
- end: `0x14000a27f`
- name: `?CreateAndAddNode@TNameResolutionCache@@QEAAJPEBGHH@Z`
- size: `1135`
- prototype: `__int64 __fastcall(TNameResolutionCache *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x140076d2c`

## callees

- `0x1400087f0`
- `0x1400088dc`
- `0x140009e10`
- `0x14000a288`
- `0x14000a2b0`
- `0x14000a468`
- `0x14000a6f0`
- `0x14000a9f0`
- `0x14000fd30`
- `0x140012bc8`
- `0x140018484`
- `0x14002cd10`
- `0x14002cd50`
- `0x140076bc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009f10`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009ffd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a07d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009f10`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009ffd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000a07d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a23f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a23f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a098`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a098`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a0a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a0a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009fb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140009fb7`

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
  __int64 v26; // r15
  TResolutionCacheNode *v27; // rax
  char *v28; // rdx
  char *v29; // r14
  TResolutionCacheNode *v30; // rcx
  char *v31; // r8
  __int64 v32; // rdx
  TResolutionCacheNode *v33; // rcx
  int v35; // [rsp+20h] [rbp-48h]
  __int64 v36; // [rsp+28h] [rbp-40h]
  __int64 v37; // [rsp+30h] [rbp-38h] BYREF
  __int64 v38; // [rsp+38h] [rbp-30h]
  __int64 v39; // [rsp+78h] [rbp+10h]
  DWORD v40; // [rsp+78h] [rbp+10h]

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
          v39 = 24 * i;
          v17 = *(_QWORD *)(*(_QWORD *)(v14 + 24) + 24 * i);
          if ( v17 && !(unsigned int)_o__wcsicmp(a2, v17) )
          {
            operator delete(*(void **)(*(_QWORD *)(v14 + 24) + 24 * i), v18);
            *(_QWORD *)(*(_QWORD *)(v14 + 24) + 24 * i) = 0;
            v19 = *(NCoreLibrary::TReferenceCount **)(*(_QWORD *)(v14 + 24) + v39 + 16);
            if ( v19 )
            {
              NCoreLibrary::TReferenceCount::Release(v19);
              *(_QWORD *)(*(_QWORD *)(v14 + 24) + v39 + 16) = 0;
            }
            break;
          }
        }
        NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v14 + 32));
      }
    }
  }
  AddrInfo = -2147024809;
  v37 = *((_QWORD *)v12 + 7);
  if ( !v37 )
    goto LABEL_36;
  v20 = *((_QWORD *)v12 + 8);
  v36 = v20;
  if ( !v20 )
    goto LABEL_36;
  v21 = *((_QWORD *)this + 19);
  if ( !*(_BYTE *)(v21 + 88) )
  {
LABEL_33:
    AddrInfo = TNameResolutionCache::CacheGetAddrInfo(this, a2, v37, v20);
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
        v26 = 0;
        v37 = (__int64)this + 120;
        AddrInfo = 1;
        v38 = 0;
        if ( this == (TNameResolutionCache *)-120LL )
          goto LABEL_44;
        v26 = *((_QWORD *)this + 17);
LABEL_43:
        v38 = v26;
        while ( 1 )
        {
LABEL_44:
          if ( (unsigned int)NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(&v37) )
          {
            NCoreLibrary::TCriticalSection::Leave((TNameResolutionCache *)((char *)this + 56));
            goto LABEL_52;
          }
          AddrInfo = TResolutionCacheNode::IsSameName((TResolutionCacheNode *)v26, a2);
          if ( !AddrInfo )
            break;
          if ( v26 )
          {
            v26 = *(_QWORD *)(v26 + 16);
            goto LABEL_43;
          }
        }
        ++*(_DWORD *)(v26 + 76);
        NCoreLibrary::TCriticalSection::Leave((TNameResolutionCache *)((char *)this + 56));
        if ( v26 )
          TResolutionCacheNode::Release((TResolutionCacheNode *)v26);
LABEL_52:
        if ( AddrInfo != 1 )
          goto LABEL_69;
      }
      v27 = (TResolutionCacheNode *)*((_QWORD *)v12 + 2);
      if ( a3 )
      {
        if ( v27 )
        {
          v28 = (char *)v12 + 24;
          if ( *((_QWORD *)v12 + 3) )
          {
            v29 = (char *)this + 120;
            if ( v27 != v12 )
            {
              v30 = (TResolutionCacheNode *)*((_QWORD *)v12 + 3);
              v28 = (char *)v12 + 24;
              if ( v30 != v12 )
              {
                *((_QWORD *)v27 + 3) = v30;
                *(_QWORD *)(*(_QWORD *)v28 + 16LL) = *((_QWORD *)v12 + 2);
                *((_QWORD *)v12 + 2) = v12;
                *(_QWORD *)v28 = v12;
              }
            }
            AddrInfo = 0;
            *(_QWORD *)(*((_QWORD *)v29 + 2) + 24LL) = v12;
            *((_QWORD *)v12 + 2) = *((_QWORD *)v29 + 2);
            *(_QWORD *)v28 = v29;
            *((_QWORD *)v29 + 2) = v12;
            goto LABEL_67;
          }
        }
      }
      else if ( v27 )
      {
        v31 = (char *)v12 + 24;
        if ( *((_QWORD *)v12 + 3) )
        {
          v32 = *((_QWORD *)this + 18);
          if ( v27 != v12 )
          {
            v33 = (TResolutionCacheNode *)*((_QWORD *)v12 + 3);
            v31 = (char *)v12 + 24;
            if ( v33 != v12 )
            {
              *((_QWORD *)v27 + 3) = v33;
              *(_QWORD *)(*(_QWORD *)v31 + 16LL) = *((_QWORD *)v12 + 2);
              *((_QWORD *)v12 + 2) = v12;
              *(_QWORD *)v31 = v12;
            }
          }
          AddrInfo = 0;
          *(_QWORD *)(*(_QWORD *)(v32 + 16) + 24LL) = v12;
          *((_QWORD *)v12 + 2) = *(_QWORD *)(v32 + 16);
          *(_QWORD *)v31 = v32;
          *(_QWORD *)(v32 + 16) = v12;
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
  v35 = 1;
  NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)(v21 + 32));
  TickCount = GetTickCount();
  v40 = TickCount;
  for ( j = 0; (unsigned int)j < *(_DWORD *)(v21 + 8); j = (unsigned int)(j + 1) )
  {
    v24 = *(_QWORD *)(v21 + 24);
    if ( *(_QWORD *)(v24 + 24 * j) )
    {
      if ( TickCount - *(_DWORD *)(v24 + 24 * j + 8) < *(_DWORD *)(v21 + 12)
        && !(unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v24 + 24 * j)) )
      {
        v35 = 0;
        break;
      }
      TickCount = v40;
    }
  }
  NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v21 + 32));
  if ( v35 == 1 )
  {
    v20 = v36;
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
0x140009e10  push    rsi
0x140009e12  push    rdi
0x140009e13  push    r12
0x140009e15  push    r14
0x140009e17  push    r15
0x140009e19  sub     rsp, 40h
0x140009e1d  mov     r15d, r9d
0x140009e20  mov     r12d, r8d
0x140009e23  mov     rdi, rdx
0x140009e26  mov     r14, rcx
0x140009e29  test    rdx, rdx
0x140009e2c  jnz     short loc_140009E41
0x140009e2e  mov     eax, 80070057h
0x140009e33  add     rsp, 40h
0x140009e37  pop     r15
0x140009e39  pop     r14
0x140009e3b  pop     r12
0x140009e3d  pop     rdi
0x140009e3e  pop     rsi
0x140009e3f  retn
0x140009e41  mov     ecx, 50h ; 'P'; Size
0x140009e46  mov     [rsp+68h+arg_10], rbp
0x140009e4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009e53  test    rax, rax
0x140009e56  jz      loc_14000A262
0x140009e5c  mov     r8d, r12d; int
0x140009e5f  mov     rdx, rdi; unsigned __int16 *
0x140009e62  mov     rcx, rax; this
0x140009e65  call    ??0TResolutionCacheNode@@QEAA@PEBGH@Z; TResolutionCacheNode::TResolutionCacheNode(ushort const *,int)
0x140009e6a  mov     rbp, rax
0x140009e6d  test    rax, rax
0x140009e70  jz      loc_14000A262
0x140009e76  mov     esi, [rax+48h]
0x140009e79  test    esi, esi
0x140009e7b  js      loc_14000A258
0x140009e81  mov     [rsp+68h+arg_0], rbx
0x140009e86  mov     [rsp+68h+arg_18], r13
0x140009e8e  test    r15d, r15d
0x140009e91  jz      loc_140009F6C
0x140009e97  mov     rdx, rdi
0x140009e9a  call    ?ExpireElement@?$TFastCache@VAddrInfoCacheEntry@@@@QEAAJPEBG@Z; TFastCache<AddrInfoCacheEntry>::ExpireElement(ushort const *)
0x140009e9f  mov     rsi, [r14+98h]
0x140009ea6  cmp     byte ptr [rsi+58h], 0
0x140009eaa  jz      loc_140009F6C
0x140009eb0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140009eb7  nop     word ptr [rax+rax+00000000h]
0x140009ec0  inc     rax
0x140009ec3  cmp     word ptr [rdi+rax*2], 0
0x140009ec8  jnz     short loc_140009EC0
0x140009eca  mov     ecx, [rsi+10h]
0x140009ecd  cmp     rax, rcx
0x140009ed0  ja      loc_140009F6C
0x140009ed6  lea     rcx, [rsi+20h]; this
0x140009eda  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009edf  xor     r13d, r13d
0x140009ee2  cmp     r13d, [rsi+8]
0x140009ee6  jnb     short loc_140009F63
0x140009ee8  lea     rcx, ds:0[r13*2]
0x140009ef0  add     rcx, r13
0x140009ef3  lea     rax, ds:0[rcx*8]
0x140009efb  mov     [rsp+68h+arg_8], rax
0x140009f00  mov     rax, [rsi+18h]
0x140009f04  mov     rdx, [rax+rcx*8]
0x140009f08  test    rdx, rdx
0x140009f0b  jz      short loc_140009F20
0x140009f0d  mov     rcx, rdi
0x140009f10  call    cs:__imp__o__wcsicmp
0x140009f17  nop     dword ptr [rax+rax+00h]
0x140009f1c  test    eax, eax
0x140009f1e  jz      short loc_140009F25
0x140009f20  inc     r13d
0x140009f23  jmp     short loc_140009EE2
0x140009f25  mov     rcx, [rsi+18h]
0x140009f29  mov     r13, [rsp+68h+arg_8]
0x140009f2e  mov     rcx, [rcx+r13]; void *
0x140009f32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009f37  mov     rax, [rsi+18h]
0x140009f3b  mov     qword ptr [rax+r13], 0
0x140009f43  mov     rax, [rsi+18h]
0x140009f47  mov     rcx, [rax+r13+10h]; this
0x140009f4c  test    rcx, rcx
0x140009f4f  jz      short loc_140009F63
0x140009f51  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140009f56  mov     rax, [rsi+18h]
0x140009f5a  mov     qword ptr [rax+r13+10h], 0
0x140009f63  lea     rcx, [rsi+20h]; this
0x140009f67  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x140009f6c  mov     rax, [rbp+38h]
0x140009f70  mov     esi, 80070057h
0x140009f75  mov     [rsp+68h+var_38], rax
0x140009f7a  test    rax, rax
0x140009f7d  jz      loc_14000A068
0x140009f83  mov     rax, [rbp+40h]
0x140009f87  mov     [rsp+68h+var_40], rax
0x140009f8c  test    rax, rax
0x140009f8f  jz      loc_14000A068
0x140009f95  mov     rsi, [r14+98h]
0x140009f9c  cmp     byte ptr [rsi+58h], 0
0x140009fa0  jz      loc_14000A03A
0x140009fa6  lea     rcx, [rsi+20h]; this
0x140009faa  mov     [rsp+68h+var_48], 1
0x140009fb2  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140009fb7  call    cs:__imp_GetTickCount
0x140009fbe  nop     dword ptr [rax+rax+00h]
0x140009fc3  mov     dword ptr [rsp+68h+arg_8], eax
0x140009fc7  xor     r13d, r13d
0x140009fca  nop     word ptr [rax+rax+00h]
0x140009fd0  cmp     r13d, [rsi+8]
0x140009fd4  jnb     short loc_14000A01E
0x140009fd6  mov     rcx, [rsi+18h]
0x140009fda  lea     rdx, ds:0[r13*2]
0x140009fe2  add     rdx, r13
0x140009fe5  mov     r8, [rcx+rdx*8]
0x140009fe9  test    r8, r8
0x140009fec  jz      short loc_14000A011
0x140009fee  sub     eax, [rcx+rdx*8+8]
0x140009ff2  cmp     eax, [rsi+0Ch]
0x140009ff5  jnb     short loc_14000A00D
0x140009ff7  mov     rdx, r8
0x140009ffa  mov     rcx, rdi
0x140009ffd  call    cs:__imp__o__wcsicmp
0x14000a004  nop     dword ptr [rax+rax+00h]
0x14000a009  test    eax, eax
0x14000a00b  jz      short loc_14000A016
0x14000a00d  mov     eax, dword ptr [rsp+68h+arg_8]
0x14000a011  inc     r13d
0x14000a014  jmp     short loc_140009FD0
0x14000a016  mov     [rsp+68h+var_48], 0
0x14000a01e  lea     rcx, [rsi+20h]; this
0x14000a022  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x14000a027  cmp     [rsp+68h+var_48], 1
0x14000a02c  jz      short loc_14000A035
0x14000a02e  mov     esi, 80072AF9h
0x14000a033  jmp     short loc_14000A073
0x14000a035  mov     rax, [rsp+68h+var_40]
0x14000a03a  mov     r8, [rsp+68h+var_38]
0x14000a03f  mov     r9, rax
0x14000a042  mov     rdx, rdi; unsigned __int16 *
0x14000a045  mov     rcx, r14; this
0x14000a048  call    ?CacheGetAddrInfo@TNameResolutionCache@@AEAAJPEBGPEAV?$TList@VTStringNode@@@NCoreLibrary@@1@Z; TNameResolutionCache::CacheGetAddrInfo(ushort const *,NCoreLibrary::TList<TStringNode> *,NCoreLibrary::TList<TStringNode> *)
0x14000a04d  mov     esi, eax
0x14000a04f  cmp     ax, 2AF9h
0x14000a053  jnz     short loc_14000A064
0x14000a055  mov     rcx, [r14+98h]
0x14000a05c  mov     rdx, rdi
0x14000a05f  call    ?AddString@?$TFastCache@VNullCacheEntry@@@@QEAAJPEBGPEAVNullCacheEntry@@@Z; TFastCache<NullCacheEntry>::AddString(ushort const *,NullCacheEntry *)
0x14000a064  test    esi, esi
0x14000a066  jns     short loc_14000A091
0x14000a068  cmp     si, 2AF9h
0x14000a06d  jnz     loc_14000A24B
0x14000a073  lea     rdx, Buffer
0x14000a07a  mov     rcx, rdi
0x14000a07d  call    cs:__imp__o__wcsicmp
0x14000a084  nop     dword ptr [rax+rax+00h]
0x14000a089  test    eax, eax
0x14000a08b  jnz     loc_14000A24B
0x14000a091  lea     rbx, [r14+38h]
0x14000a095  mov     rcx, rbx; lpCriticalSection
0x14000a098  call    cs:__imp_EnterCriticalSection
0x14000a09f  nop     dword ptr [rax+rax+00h]
0x14000a0a4  inc     dword ptr [rbx+2Ch]
0x14000a0a7  call    cs:__imp_GetCurrentThreadId
0x14000a0ae  nop     dword ptr [rax+rax+00h]
0x14000a0b3  mov     [rbx+28h], eax
0x14000a0b6  test    r15d, r15d
0x14000a0b9  jz      short loc_14000A0D5
0x14000a0bb  mov     rdx, rdi; unsigned __int16 *
0x14000a0be  mov     rcx, r14; this
0x14000a0c1  call    ?DeleteNode@TNameResolutionCache@@QEAAJPEBG@Z; TNameResolutionCache::DeleteNode(ushort const *)
0x14000a0c6  mov     esi, eax
0x14000a0c8  test    eax, eax
0x14000a0ca  js      loc_14000A22C
0x14000a0d0  jmp     loc_14000A15E
0x14000a0d5  mov     rcx, rbx; this
0x14000a0d8  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14000a0dd  lea     rax, [r14+78h]
0x14000a0e1  xor     r15d, r15d
0x14000a0e4  mov     [rsp+68h+var_38], rax
0x14000a0e9  mov     esi, 1
0x14000a0ee  mov     [rsp+68h+var_30], r15
0x14000a0f3  test    rax, rax
0x14000a0f6  jz      short loc_14000A101
0x14000a0f8  mov     r15, [rax+10h]
0x14000a0fc  mov     [rsp+68h+var_30], r15
0x14000a101  lea     rcx, [rsp+68h+var_38]
0x14000a106  call    ?IsDone@TIterator@?$TList@VTResolutionCacheNode@@@NCoreLibrary@@QEBAHXZ; NCoreLibrary::TList<TResolutionCacheNode>::TIterator::IsDone(void)
0x14000a10b  test    eax, eax
0x14000a10d  jnz     short loc_14000A139
0x14000a10f  mov     rdx, rdi; unsigned __int16 *
0x14000a112  mov     rcx, r15; this
0x14000a115  call    ?IsSameName@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsSameName(ushort const *)
0x14000a11a  mov     esi, eax
0x14000a11c  test    eax, eax
0x14000a11e  jz      short loc_14000A12B
0x14000a120  test    r15, r15
0x14000a123  jz      short loc_14000A101
0x14000a125  mov     r15, [r15+10h]
0x14000a129  jmp     short loc_14000A0FC
0x14000a12b  inc     dword ptr [r15+4Ch]
0x14000a12f  mov     rcx, rbx; this
0x14000a132  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x14000a137  jmp     short loc_14000A148
0x14000a139  mov     rcx, rbx; this
0x14000a13c  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x14000a141  xor     r15d, r15d
0x14000a144  test    esi, esi
0x14000a146  jnz     short loc_14000A155
0x14000a148  test    r15, r15
0x14000a14b  jz      short loc_14000A155
0x14000a14d  mov     rcx, r15; this
0x14000a150  call    ?Release@TResolutionCacheNode@@QEAAKXZ; TResolutionCacheNode::Release(void)
0x14000a155  cmp     esi, 1
0x14000a158  jnz     loc_14000A22C
0x14000a15e  mov     rax, [rbp+10h]
0x14000a162  test    r12d, r12d
0x14000a165  jz      short loc_14000A1C6
0x14000a167  test    rax, rax
0x14000a16a  jz      loc_14000A220
0x14000a170  cmp     qword ptr [rbp+18h], 0
0x14000a175  lea     rdx, [rbp+18h]
0x14000a179  jz      loc_14000A220
0x14000a17f  add     r14, 78h ; 'x'
0x14000a183  cmp     rax, rbp
0x14000a186  jz      short loc_14000A1AB
0x14000a188  mov     rcx, [rbp+18h]
0x14000a18c  lea     rdx, [rbp+18h]
0x14000a190  cmp     rcx, rbp
0x14000a193  jz      short loc_14000A1AB
0x14000a195  mov     [rax+18h], rcx
0x14000a199  mov     rcx, [rdx]
0x14000a19c  mov     rax, [rbp+10h]
0x14000a1a0  mov     [rcx+10h], rax
0x14000a1a4  mov     [rbp+10h], rbp
0x14000a1a8  mov     [rdx], rbp
0x14000a1ab  mov     rax, [r14+10h]
0x14000a1af  xor     esi, esi
0x14000a1b1  mov     [rax+18h], rbp
0x14000a1b5  mov     rax, [r14+10h]
0x14000a1b9  mov     [rbp+10h], rax
0x14000a1bd  mov     [rdx], r14
0x14000a1c0  mov     [r14+10h], rbp
0x14000a1c4  jmp     short loc_14000A225
0x14000a1c6  test    rax, rax
0x14000a1c9  jz      short loc_14000A220
0x14000a1cb  cmp     qword ptr [rbp+18h], 0
0x14000a1d0  lea     r8, [rbp+18h]
0x14000a1d4  jz      short loc_14000A220
0x14000a1d6  mov     rdx, [r14+90h]
0x14000a1dd  cmp     rax, rbp
0x14000a1e0  jz      short loc_14000A205
0x14000a1e2  mov     rcx, [rbp+18h]
0x14000a1e6  lea     r8, [rbp+18h]
0x14000a1ea  cmp     rcx, rbp
0x14000a1ed  jz      short loc_14000A205
0x14000a1ef  mov     [rax+18h], rcx
0x14000a1f3  mov     rcx, [r8]
0x14000a1f6  mov     rax, [rbp+10h]
0x14000a1fa  mov     [rcx+10h], rax
0x14000a1fe  mov     [rbp+10h], rbp
0x14000a202  mov     [r8], rbp
0x14000a205  mov     rax, [rdx+10h]
0x14000a209  xor     esi, esi
0x14000a20b  mov     [rax+18h], rbp
0x14000a20f  mov     rax, [rdx+10h]
0x14000a213  mov     [rbp+10h], rax
0x14000a217  mov     [r8], rdx
0x14000a21a  mov     [rdx+10h], rbp
0x14000a21e  jmp     short loc_14000A225
0x14000a220  mov     esi, 80004005h
0x14000a225  test    esi, esi
0x14000a227  js      short loc_14000A22C
0x14000a229  inc     dword ptr [rbp+4Ch]
0x14000a22c  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14000a230  mov     eax, [rbx+2Ch]
0x14000a233  jnz     short loc_14000A23C
0x14000a235  mov     dword ptr [rbx+28h], 0
0x14000a23c  mov     rcx, rbx; lpCriticalSection
0x14000a23f  call    cs:__imp_LeaveCriticalSection
0x14000a246  nop     dword ptr [rax+rax+00h]
0x14000a24b  mov     rbx, [rsp+68h+arg_0]
0x14000a250  mov     r13, [rsp+68h+arg_18]
0x14000a258  mov     rcx, rbp; this
0x14000a25b  call    ?Release@TResolutionCacheNode@@QEAAKXZ; TResolutionCacheNode::Release(void)
0x14000a260  jmp     short loc_14000A267
0x14000a262  mov     esi, 8007000Eh
0x14000a267  mov     rbp, [rsp+68h+arg_10]
0x14000a26f  mov     eax, esi
0x14000a271  add     rsp, 40h
0x14000a275  pop     r15
0x14000a277  pop     r14
0x14000a279  pop     r12
0x14000a27b  pop     rdi
0x14000a27c  pop     rsi
0x14000a27d  retn
```
