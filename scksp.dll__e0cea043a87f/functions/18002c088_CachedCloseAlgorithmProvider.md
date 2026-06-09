# CachedCloseAlgorithmProvider

- ea: `0x18002c088`
- end: `0x18002c101`
- name: `CachedCloseAlgorithmProvider`
- size: `121`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b838`

## callees

- `0x18002c088`
- `0x18002c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c0df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c0df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c0ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c0ac`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c0ee`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c0ee`

## pseudocode

```c
__int64 __fastcall CachedCloseAlgorithmProvider(BCRYPT_ALG_HANDLE hAlgorithm)
{
  __int64 Cache; // rbx
  int v3; // esi
  unsigned int v4; // edi
  int i; // edx
  __int64 v6; // rcx

  Cache = getCache();
  if ( !Cache )
    return (unsigned int)BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  v3 = 0;
  v4 = 0;
  AcquireSRWLockShared(g_pHandleCacheLock);
  for ( i = 0; i < 8; ++i )
  {
    v6 = 224LL * i;
    if ( *(BCRYPT_ALG_HANDLE *)(v6 + Cache) == hAlgorithm )
    {
      _InterlockedDecrement64((volatile signed __int64 *)(v6 + Cache + 8));
      v3 = 1;
      break;
    }
  }
  ReleaseSRWLockShared(g_pHandleCacheLock);
  if ( !v3 )
    return (unsigned int)BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return v4;
}

```

## disassembly

```asm
0x18002c088  push    rbx
0x18002c08a  push    rbp
0x18002c08b  push    rsi
0x18002c08c  push    rdi
0x18002c08d  sub     rsp, 28h
0x18002c091  mov     rbp, rcx
0x18002c094  call    getCache
0x18002c099  mov     rbx, rax
0x18002c09c  test    rax, rax
0x18002c09f  jz      short loc_18002C0E9
0x18002c0a1  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c0a8  xor     esi, esi
0x18002c0aa  xor     edi, edi
0x18002c0ac  call    cs:__imp_AcquireSRWLockShared
0x18002c0b2  xor     edx, edx
0x18002c0b4  cmp     edx, 8
0x18002c0b7  jge     short loc_18002C0D8
0x18002c0b9  movsxd  rax, edx
0x18002c0bc  imul    rcx, rax, 0E0h
0x18002c0c3  cmp     [rcx+rbx], rbp
0x18002c0c7  jz      short loc_18002C0CD
0x18002c0c9  inc     edx
0x18002c0cb  jmp     short loc_18002C0B4
0x18002c0cd  lock dec qword ptr [rcx+rbx+8]
0x18002c0d3  mov     esi, 1
0x18002c0d8  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c0df  call    cs:__imp_ReleaseSRWLockShared
0x18002c0e5  test    esi, esi
0x18002c0e7  jnz     short loc_18002C0F6
0x18002c0e9  xor     edx, edx; dwFlags
0x18002c0eb  mov     rcx, rbp; hAlgorithm
0x18002c0ee  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002c0f4  mov     edi, eax
0x18002c0f6  mov     eax, edi
0x18002c0f8  add     rsp, 28h
0x18002c0fc  pop     rdi
0x18002c0fd  pop     rsi
0x18002c0fe  pop     rbp
0x18002c0ff  pop     rbx
0x18002c100  retn
```
