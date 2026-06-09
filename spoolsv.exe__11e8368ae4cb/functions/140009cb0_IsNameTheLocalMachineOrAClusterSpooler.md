# IsNameTheLocalMachineOrAClusterSpooler

- ea: `0x140009cb0`
- end: `0x140009dd5`
- name: `IsNameTheLocalMachineOrAClusterSpooler`
- size: `293`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x140009cb0`
- `0x140009de0`
- `0x14000a180`
- `0x140014e40`
- `0x140016b74`
- `0x14002a870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009d63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140009d63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009d94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009d94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009d2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009d2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d38`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140009cfd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140009cfd`

## pseudocode

```c
__int64 __fastcall IsNameTheLocalMachineOrAClusterSpooler(PCNZWCH lpString2)
{
  unsigned int v2; // ebp
  unsigned __int16 *v3; // rbx
  TNameResolutionCache *v4; // rsi
  char *v5; // rdi
  TResolutionCacheNode *v6; // r14
  int IsNameInNodeCache; // r15d
  TResolutionCacheNode *i; // rsi
  const unsigned __int16 *v10; // rdx
  TNameResolutionCache *v11; // rcx

  v2 = 1;
  if ( lpString2 )
  {
    if ( *lpString2 == 92 && lpString2[1] == 92 && CompareStringW(0x7Fu, 1u, &szMachineName, -1, lpString2, -1) != 2 )
    {
      v3 = DuplicateServerName(lpString2 + 2);
      if ( v3 )
      {
        v4 = g_pNameCache;
        v5 = (char *)g_pNameCache + 56;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pNameCache + 56));
        ++*((_DWORD *)v5 + 11);
        v6 = (TNameResolutionCache *)((char *)v4 + 120);
        *((_DWORD *)v5 + 10) = GetCurrentThreadId();
        IsNameInNodeCache = 1;
        if ( v4 != (TNameResolutionCache *)-120LL )
        {
          for ( i = (TResolutionCacheNode *)*((_QWORD *)v4 + 17); i != v6; i = (TResolutionCacheNode *)*((_QWORD *)i + 2) )
          {
            if ( !(unsigned int)_o__wcsicmp(&Buffer, *((_QWORD *)i + 5)) )
            {
              IsNameInNodeCache = TResolutionCacheNode::IsNameInNodeCache(i, v3);
              break;
            }
          }
        }
        if ( (*((_DWORD *)v5 + 11))-- == 1 )
          *((_DWORD *)v5 + 10) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)v5);
        if ( IsNameInNodeCache
          && (unsigned int)CacheIsNameCluster(v3)
          && TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(v11, v10, v3) )
        {
          v2 = 0;
        }
        operator delete(v3, (unsigned __int64)v10);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140009cb0  push    rbx
0x140009cb2  push    rbp
0x140009cb3  push    rsi
0x140009cb4  push    rdi
0x140009cb5  push    r14
0x140009cb7  push    r15
0x140009cb9  sub     rsp, 38h
0x140009cbd  mov     rbx, rcx
0x140009cc0  mov     ebp, 1
0x140009cc5  test    rcx, rcx
0x140009cc8  jz      loc_140009DC6
0x140009cce  cmp     word ptr [rcx], 5Ch ; '\'
0x140009cd2  jnz     loc_140009DC6
0x140009cd8  cmp     word ptr [rcx+2], 5Ch ; '\'
0x140009cdd  jnz     loc_140009DC6
0x140009ce3  or      r9d, 0FFFFFFFFh; cchCount1
0x140009ce7  lea     r8, ?szMachineName@@3PAGA; lpString1
0x140009cee  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x140009cf3  mov     edx, ebp; dwCmpFlags
0x140009cf5  mov     [rsp+68h+lpString2], rcx; lpString2
0x140009cfa  lea     ecx, [rbp+7Eh]; Locale
0x140009cfd  call    cs:__imp_CompareStringW
0x140009d03  cmp     eax, 2
0x140009d06  jz      loc_140009DC6
0x140009d0c  lea     rcx, [rbx+4]; unsigned __int16 *
0x140009d10  call    ?DuplicateServerName@@YAPEAGPEBG@Z; DuplicateServerName(ushort const *)
0x140009d15  mov     rbx, rax
0x140009d18  test    rax, rax
0x140009d1b  jz      loc_140009DC6
0x140009d21  mov     rsi, cs:?g_pNameCache@@3PEAVTNameResolutionCache@@EA; TNameResolutionCache * g_pNameCache
0x140009d28  lea     rdi, [rsi+38h]
0x140009d2c  mov     rcx, rdi; lpCriticalSection
0x140009d2f  call    cs:__imp_EnterCriticalSection
0x140009d35  add     [rdi+2Ch], ebp
0x140009d38  call    cs:__imp_GetCurrentThreadId
0x140009d3e  lea     r14, [rsi+78h]
0x140009d42  mov     [rdi+28h], eax
0x140009d45  xor     esi, esi
0x140009d47  mov     r15d, ebp
0x140009d4a  test    r14, r14
0x140009d4d  jz      short loc_140009D81
0x140009d4f  mov     rsi, [r14+10h]
0x140009d53  cmp     rsi, r14
0x140009d56  jz      short loc_140009D81
0x140009d58  mov     rdx, [rsi+28h]
0x140009d5c  lea     rcx, Buffer
0x140009d63  call    cs:__imp__o__wcsicmp
0x140009d69  test    eax, eax
0x140009d6b  jz      short loc_140009D73
0x140009d6d  mov     rsi, [rsi+10h]
0x140009d71  jmp     short loc_140009D53
0x140009d73  mov     rdx, rbx; unsigned __int16 *
0x140009d76  mov     rcx, rsi; this
0x140009d79  call    ?IsNameInNodeCache@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsNameInNodeCache(ushort const *)
0x140009d7e  mov     r15d, eax
0x140009d81  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x140009d85  mov     ecx, [rdi+2Ch]
0x140009d88  jnz     short loc_140009D91
0x140009d8a  mov     dword ptr [rdi+28h], 0
0x140009d91  mov     rcx, rdi; lpCriticalSection
0x140009d94  call    cs:__imp_LeaveCriticalSection
0x140009d9a  test    r15d, r15d
0x140009d9d  jz      short loc_140009DB9
0x140009d9f  mov     rcx, rbx; unsigned __int16 *
0x140009da2  call    CacheIsNameCluster
0x140009da7  test    eax, eax
0x140009da9  jz      short loc_140009DB9
0x140009dab  mov     r8, rbx; unsigned __int16 *
0x140009dae  call    ?CheckIfNameIsInNodeCacheUsingIp@TNameResolutionCache@@QEAAJPEBG0@Z; TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(ushort const *,ushort const *)
0x140009db3  test    eax, eax
0x140009db5  jz      short loc_140009DB9
0x140009db7  xor     ebp, ebp
0x140009db9  test    rbx, rbx
0x140009dbc  jz      short loc_140009DC6
0x140009dbe  mov     rcx, rbx; void *
0x140009dc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009dc6  mov     eax, ebp
0x140009dc8  add     rsp, 38h
0x140009dcc  pop     r15
0x140009dce  pop     r14
0x140009dd0  pop     rdi
0x140009dd1  pop     rsi
0x140009dd2  pop     rbp
0x140009dd3  pop     rbx
0x140009dd4  retn
```
