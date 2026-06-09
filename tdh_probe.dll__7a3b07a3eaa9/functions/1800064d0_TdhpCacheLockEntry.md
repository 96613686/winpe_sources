# TdhpCacheLockEntry

- ea: `0x1800064d0`
- end: `0x180006650`
- name: `TdhpCacheLockEntry`
- size: `384`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x1800074e8`
- `0x18001e820`
- `0x1800259a4`
- `0x1800268b0`
- `0x180026ae4`
- `0x180026dc8`
- `0x180026f34`
- `0x1800270cc`
- `0x180029a28`
- `0x180029e6c`

## callees

- `0x1800059e8`
- `0x1800064d0`
- `0x180006660`
- `0x180007720`
- `0x180024318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000653c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000653c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800065fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800065fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006604`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006639`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006639`

## pseudocode

```c
struct TDH_MOF_INFO *__fastcall TdhpCacheLockEntry(struct TDH_CACHE *a1, __int64 a2)
{
  struct TDH_CACHE *v2; // r9
  unsigned __int8 v4; // al
  __int64 v5; // r8
  __int64 v6; // rcx
  char v7; // al
  RTL_SRWLOCK *v8; // rbx
  struct TDH_MOF_INFO *v9; // rbp
  struct TDH_MOF_INFO *v10; // r14
  __int64 i; // rsi
  _DWORD *Ptr; // rcx
  RTL_SRWLOCK *v13; // r15
  struct TDH_MOF_INFO *v15; // r8
  HANDLE ProcessHeap; // rax
  struct TDH_MOF_INFO *v17; // rsi
  unsigned int v18; // [rsp+50h] [rbp+8h] BYREF

  v18 = 0;
  v2 = a1;
  if ( !a1 )
    v2 = g_TdhCache;
  v4 = 0;
  v5 = 0;
  do
  {
    v6 = (unsigned int)(v5 + 3);
    v7 = __ROL1__(
           *(_BYTE *)((unsigned int)(v5 + 2) + a2)
         ^ __ROL1__(*(_BYTE *)((unsigned int)(v5 + 1) + a2) ^ __ROL1__(*(_BYTE *)(v5 + a2) ^ v4, 3), 3),
           3);
    v5 = (unsigned int)(v5 + 4);
    v4 = __ROL1__(*(_BYTE *)(v6 + a2) ^ v7, 3);
  }
  while ( (unsigned int)v5 < 0x10 );
  v8 = (RTL_SRWLOCK *)((char *)v2 + 64 * (unsigned __int64)v4);
  do
  {
    AcquireSRWLockShared(v8);
    v9 = 0;
    v10 = 0;
    for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
    {
      Ptr = v8[i + 1].Ptr;
      v13 = &v8[i];
      if ( Ptr )
      {
        if ( Ptr[2] == *(_DWORD *)a2
          && Ptr[3] == *(_DWORD *)(a2 + 4)
          && Ptr[4] == *(_DWORD *)(a2 + 8)
          && Ptr[5] == *(_DWORD *)(a2 + 12) )
        {
          v9 = (struct TDH_MOF_INFO *)v8[i + 1].Ptr;
          break;
        }
      }
      else
      {
        if ( !v10 )
        {
          v10 = TdhpCacheEntryAllocate((const struct _GUID *)a2);
          if ( !v10 )
            goto LABEL_18;
        }
        if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&v13[1], (signed __int64)v10, 0) )
        {
          v9 = v10;
          goto LABEL_18;
        }
        if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)((char *)v13[1].Ptr + 8), (const struct _GUID *)a2) )
        {
          v9 = v15;
          break;
        }
      }
    }
    if ( v9 != v10 && v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
LABEL_18:
    if ( v9 )
      return v9;
    ReleaseSRWLockShared(v8);
    AcquireSRWLockExclusive(v8);
    v17 = TdhpFindOrAddEntry((struct TDH_CACHE_BUCKET *)v8, (const struct _GUID *)a2, &v18);
    if ( !v17 && !v18 )
      v17 = TdhpCacheEvictAndAddEntry((struct TDH_CACHE_BUCKET *)v8, (const struct _GUID *)a2);
    ReleaseSRWLockExclusive(v8);
  }
  while ( v17 );
  return 0;
}

```

## disassembly

```asm
0x1800064d0  mov     [rsp+arg_10], rbx
0x1800064d5  push    rbp
0x1800064d6  push    rsi
0x1800064d7  push    rdi
0x1800064d8  push    r14
0x1800064da  push    r15
0x1800064dc  sub     rsp, 20h
0x1800064e0  test    rcx, rcx
0x1800064e3  mov     [rsp+48h+arg_0], 0
0x1800064eb  mov     r9, rcx
0x1800064ee  mov     rdi, rdx
0x1800064f1  cmovz   r9, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800064f9  xor     al, al
0x1800064fb  xor     r8d, r8d
0x1800064fe  xchg    ax, ax
0x180006500  xor     al, [r8+rdx]
0x180006504  lea     ecx, [r8+1]
0x180006508  rol     al, 3
0x18000650b  xor     al, [rcx+rdx]
0x18000650e  lea     ecx, [r8+2]
0x180006512  rol     al, 3
0x180006515  xor     al, [rcx+rdx]
0x180006518  lea     ecx, [r8+3]
0x18000651c  rol     al, 3
0x18000651f  add     r8d, 4
0x180006523  xor     al, [rcx+rdx]
0x180006526  rol     al, 3
0x180006529  cmp     r8d, 10h
0x18000652d  jb      short loc_180006500
0x18000652f  movzx   ebx, al
0x180006532  shl     rbx, 6
0x180006536  add     rbx, r9
0x180006539  mov     rcx, rbx; SRWLock
0x18000653c  call    cs:__imp_AcquireSRWLockShared
0x180006542  xor     ebp, ebp
0x180006544  xor     r14d, r14d
0x180006547  xor     esi, esi
0x180006549  cmp     esi, 7
0x18000654c  jnb     short loc_180006582
0x18000654e  mov     rcx, [rbx+rsi*8+8]
0x180006553  lea     r15, [rbx+rsi*8]
0x180006557  test    rcx, rcx
0x18000655a  jz      short loc_1800065A5
0x18000655c  mov     eax, [rdi]
0x18000655e  cmp     [rcx+8], eax
0x180006561  jnz     short loc_18000656B
0x180006563  mov     eax, [rdi+4]
0x180006566  cmp     [rcx+0Ch], eax
0x180006569  jz      short loc_18000656F
0x18000656b  inc     esi
0x18000656d  jmp     short loc_180006549
0x18000656f  mov     eax, [rdi+8]
0x180006572  cmp     [rcx+10h], eax
0x180006575  jnz     short loc_18000656B
0x180006577  mov     eax, [rdi+0Ch]
0x18000657a  cmp     [rcx+14h], eax
0x18000657d  jnz     short loc_18000656B
0x18000657f  mov     rbp, rcx
0x180006582  cmp     rbp, r14
0x180006585  jz      short loc_18000658C
0x180006587  test    r14, r14
0x18000658a  jnz     short loc_1800065E2
0x18000658c  test    rbp, rbp
0x18000658f  jz      short loc_1800065F8
0x180006591  mov     rax, rbp
0x180006594  mov     rbx, [rsp+48h+arg_10]
0x180006599  add     rsp, 20h
0x18000659d  pop     r15
0x18000659f  pop     r14
0x1800065a1  pop     rdi
0x1800065a2  pop     rsi
0x1800065a3  pop     rbp
0x1800065a4  retn
0x1800065a5  test    r14, r14
0x1800065a8  jnz     short loc_1800065BA
0x1800065aa  mov     rcx, rdi; struct _GUID *
0x1800065ad  call    ?TdhpCacheEntryAllocate@@YAPEAUTDH_MOF_INFO@@PEBU_GUID@@@Z; TdhpCacheEntryAllocate(_GUID const *)
0x1800065b2  mov     r14, rax
0x1800065b5  test    rax, rax
0x1800065b8  jz      short loc_18000658C
0x1800065ba  xor     eax, eax
0x1800065bc  lock cmpxchg [r15+8], r14
0x1800065c2  jz      short loc_1800065DD
0x1800065c4  mov     r8, [r15+8]
0x1800065c8  mov     rdx, rdi; struct _GUID *
0x1800065cb  lea     rcx, [r8+8]; struct _GUID *
0x1800065cf  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800065d4  test    eax, eax
0x1800065d6  jz      short loc_18000656B
0x1800065d8  mov     rbp, r8
0x1800065db  jmp     short loc_180006582
0x1800065dd  mov     rbp, r14
0x1800065e0  jmp     short loc_18000658C
0x1800065e2  call    cs:__imp_GetProcessHeap
0x1800065e8  mov     r8, r14; lpMem
0x1800065eb  xor     edx, edx; dwFlags
0x1800065ed  mov     rcx, rax; hHeap
0x1800065f0  call    cs:__imp_HeapFree
0x1800065f6  jmp     short loc_18000658C
0x1800065f8  mov     rcx, rbx; SRWLock
0x1800065fb  call    cs:__imp_ReleaseSRWLockShared
0x180006601  mov     rcx, rbx; SRWLock
0x180006604  call    cs:__imp_AcquireSRWLockExclusive
0x18000660a  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x18000660f  mov     rdx, rdi; struct _GUID *
0x180006612  mov     rcx, rbx; struct TDH_CACHE_BUCKET *
0x180006615  call    ?TdhpFindOrAddEntry@@YAPEAUTDH_MOF_INFO@@PEAUTDH_CACHE_BUCKET@@PEBU_GUID@@PEAK@Z; TdhpFindOrAddEntry(TDH_CACHE_BUCKET *,_GUID const *,ulong *)
0x18000661a  mov     rsi, rax
0x18000661d  test    rax, rax
0x180006620  jnz     short loc_180006636
0x180006622  cmp     [rsp+48h+arg_0], eax
0x180006626  jnz     short loc_180006636
0x180006628  mov     rdx, rdi; struct _GUID *
0x18000662b  mov     rcx, rbx; struct TDH_CACHE_BUCKET *
0x18000662e  call    ?TdhpCacheEvictAndAddEntry@@YAPEAUTDH_MOF_INFO@@PEAUTDH_CACHE_BUCKET@@PEBU_GUID@@@Z; TdhpCacheEvictAndAddEntry(TDH_CACHE_BUCKET *,_GUID const *)
0x180006633  mov     rsi, rax
0x180006636  mov     rcx, rbx; SRWLock
0x180006639  call    cs:__imp_ReleaseSRWLockExclusive
0x18000663f  test    rsi, rsi
0x180006642  jnz     loc_180006539
0x180006648  mov     rax, rsi
0x18000664b  jmp     loc_180006594
```
