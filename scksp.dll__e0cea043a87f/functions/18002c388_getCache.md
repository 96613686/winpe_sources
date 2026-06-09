# getCache

- ea: `0x18002c388`
- end: `0x18002c422`
- name: `getCache`
- size: `154`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c088`
- `0x18002c1fc`
- `0x18002c2f4`

## callees

- `0x180009e82`
- `0x18002c048`
- `0x18002c068`
- `0x18002c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002c3f2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002c3f2`

## pseudocode

```c
__int64 getCache()
{
  __int64 v0; // rdi
  void *v1; // rax
  signed __int64 v2; // rbx
  RTL_SRWLOCK *v3; // rax
  signed __int64 v4; // rbx

  v0 = 0;
  if ( !g_handleCache )
  {
    v1 = (void *)MSCryptAlloc(1792);
    v2 = (signed __int64)v1;
    if ( !v1 )
      return v0;
    memset_0(v1, 0, 0x700u);
    if ( _InterlockedCompareExchange64(&g_handleCache, v2, 0) )
      MSCryptFree(v2);
  }
  if ( g_pHandleCacheLock )
    return g_handleCache;
  v3 = (RTL_SRWLOCK *)MSCryptAlloc(8);
  v4 = (signed __int64)v3;
  if ( v3 )
  {
    InitializeSRWLock(v3);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pHandleCacheLock, v4, 0) )
      MSCryptFree(v4);
    return g_handleCache;
  }
  return v0;
}

```

## disassembly

```asm
0x18002c388  mov     [rsp+arg_0], rbx
0x18002c38d  push    rdi
0x18002c38e  sub     rsp, 20h
0x18002c392  xor     edi, edi
0x18002c394  cmp     cs:g_handleCache, rdi
0x18002c39b  jnz     short loc_18002C3D4
0x18002c39d  mov     ecx, 700h
0x18002c3a2  call    MSCryptAlloc
0x18002c3a7  mov     rbx, rax
0x18002c3aa  test    rax, rax
0x18002c3ad  jz      short loc_18002C414
0x18002c3af  xor     edx, edx; Val
0x18002c3b1  mov     r8d, 700h; Size
0x18002c3b7  mov     rcx, rax; void *
0x18002c3ba  call    memset_0
0x18002c3bf  xor     eax, eax
0x18002c3c1  lock cmpxchg cs:g_handleCache, rbx
0x18002c3ca  jz      short loc_18002C3D4
0x18002c3cc  mov     rcx, rbx
0x18002c3cf  call    MSCryptFree
0x18002c3d4  cmp     cs:g_pHandleCacheLock, rdi
0x18002c3db  jnz     short loc_18002C40D
0x18002c3dd  mov     ecx, 8
0x18002c3e2  call    MSCryptAlloc
0x18002c3e7  mov     rbx, rax
0x18002c3ea  test    rax, rax
0x18002c3ed  jz      short loc_18002C414
0x18002c3ef  mov     rcx, rax; SRWLock
0x18002c3f2  call    cs:__imp_InitializeSRWLock
0x18002c3f8  xor     eax, eax
0x18002c3fa  lock cmpxchg cs:g_pHandleCacheLock, rbx
0x18002c403  jz      short loc_18002C40D
0x18002c405  mov     rcx, rbx
0x18002c408  call    MSCryptFree
0x18002c40d  mov     rdi, cs:g_handleCache
0x18002c414  mov     rbx, [rsp+28h+arg_0]
0x18002c419  mov     rax, rdi
0x18002c41c  add     rsp, 20h
0x18002c420  pop     rdi
0x18002c421  retn
```
