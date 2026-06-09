# IsNameTheLocalMachineOrAClusterSpooler

- ea: `0x14000aab0`
- end: `0x14000abf4`
- name: `IsNameTheLocalMachineOrAClusterSpooler`
- size: `324`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14000aab0`
- `0x14000ac00`
- `0x14000afe0`
- `0x140016160`
- `0x140018020`
- `0x14002cd50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000ab75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000ab75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000abac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000abac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ab35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ab35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ab44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ab44`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000aafd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000aafd`

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
0x14000aab0  push    rbx
0x14000aab2  push    rbp
0x14000aab3  push    rsi
0x14000aab4  push    rdi
0x14000aab5  push    r14
0x14000aab7  push    r15
0x14000aab9  sub     rsp, 38h
0x14000aabd  mov     rbx, rcx
0x14000aac0  mov     ebp, 1
0x14000aac5  test    rcx, rcx
0x14000aac8  jz      loc_14000ABE4
0x14000aace  cmp     word ptr [rcx], 5Ch ; '\'
0x14000aad2  jnz     loc_14000ABE4
0x14000aad8  cmp     word ptr [rcx+2], 5Ch ; '\'
0x14000aadd  jnz     loc_14000ABE4
0x14000aae3  or      r9d, 0FFFFFFFFh; cchCount1
0x14000aae7  lea     r8, ?szMachineName@@3PAGA; lpString1
0x14000aaee  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x14000aaf3  mov     edx, ebp; dwCmpFlags
0x14000aaf5  mov     [rsp+68h+lpString2], rcx; lpString2
0x14000aafa  lea     ecx, [rbp+7Eh]; Locale
0x14000aafd  call    cs:__imp_CompareStringW
0x14000ab04  nop     dword ptr [rax+rax+00h]
0x14000ab09  cmp     eax, 2
0x14000ab0c  jz      loc_14000ABE4
0x14000ab12  lea     rcx, [rbx+4]; unsigned __int16 *
0x14000ab16  call    ?DuplicateServerName@@YAPEAGPEBG@Z; DuplicateServerName(ushort const *)
0x14000ab1b  mov     rbx, rax
0x14000ab1e  test    rax, rax
0x14000ab21  jz      loc_14000ABE4
0x14000ab27  mov     rsi, cs:?g_pNameCache@@3PEAVTNameResolutionCache@@EA; TNameResolutionCache * g_pNameCache
0x14000ab2e  lea     rdi, [rsi+38h]
0x14000ab32  mov     rcx, rdi; lpCriticalSection
0x14000ab35  call    cs:__imp_EnterCriticalSection
0x14000ab3c  nop     dword ptr [rax+rax+00h]
0x14000ab41  add     [rdi+2Ch], ebp
0x14000ab44  call    cs:__imp_GetCurrentThreadId
0x14000ab4b  nop     dword ptr [rax+rax+00h]
0x14000ab50  lea     r14, [rsi+78h]
0x14000ab54  mov     [rdi+28h], eax
0x14000ab57  xor     esi, esi
0x14000ab59  mov     r15d, ebp
0x14000ab5c  test    r14, r14
0x14000ab5f  jz      short loc_14000AB99
0x14000ab61  mov     rsi, [r14+10h]
0x14000ab65  cmp     rsi, r14
0x14000ab68  jz      short loc_14000AB99
0x14000ab6a  mov     rdx, [rsi+28h]
0x14000ab6e  lea     rcx, Buffer
0x14000ab75  call    cs:__imp__o__wcsicmp
0x14000ab7c  nop     dword ptr [rax+rax+00h]
0x14000ab81  test    eax, eax
0x14000ab83  jz      short loc_14000AB8B
0x14000ab85  mov     rsi, [rsi+10h]
0x14000ab89  jmp     short loc_14000AB65
0x14000ab8b  mov     rdx, rbx; unsigned __int16 *
0x14000ab8e  mov     rcx, rsi; this
0x14000ab91  call    ?IsNameInNodeCache@TResolutionCacheNode@@QEAAJPEBG@Z; TResolutionCacheNode::IsNameInNodeCache(ushort const *)
0x14000ab96  mov     r15d, eax
0x14000ab99  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x14000ab9d  mov     ecx, [rdi+2Ch]
0x14000aba0  jnz     short loc_14000ABA9
0x14000aba2  mov     dword ptr [rdi+28h], 0
0x14000aba9  mov     rcx, rdi; lpCriticalSection
0x14000abac  call    cs:__imp_LeaveCriticalSection
0x14000abb3  nop     dword ptr [rax+rax+00h]
0x14000abb8  test    r15d, r15d
0x14000abbb  jz      short loc_14000ABD7
0x14000abbd  mov     rcx, rbx; unsigned __int16 *
0x14000abc0  call    CacheIsNameCluster
0x14000abc5  test    eax, eax
0x14000abc7  jz      short loc_14000ABD7
0x14000abc9  mov     r8, rbx; unsigned __int16 *
0x14000abcc  call    ?CheckIfNameIsInNodeCacheUsingIp@TNameResolutionCache@@QEAAJPEBG0@Z; TNameResolutionCache::CheckIfNameIsInNodeCacheUsingIp(ushort const *,ushort const *)
0x14000abd1  test    eax, eax
0x14000abd3  jz      short loc_14000ABD7
0x14000abd5  xor     ebp, ebp
0x14000abd7  test    rbx, rbx
0x14000abda  jz      short loc_14000ABE4
0x14000abdc  mov     rcx, rbx; void *
0x14000abdf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000abe4  mov     eax, ebp
0x14000abe6  add     rsp, 38h
0x14000abea  pop     r15
0x14000abec  pop     r14
0x14000abee  pop     rdi
0x14000abef  pop     rsi
0x14000abf0  pop     rbp
0x14000abf1  pop     rbx
0x14000abf2  retn
```
