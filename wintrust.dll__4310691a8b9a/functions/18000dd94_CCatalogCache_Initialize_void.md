# CCatalogCache::Initialize(void)

- ea: `0x18000dd94`
- end: `0x18000de32`
- name: `?Initialize@CCatalogCache@@QEAAHXZ`
- size: `158`
- prototype: `__int64 __fastcall(CCatalogCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dab0`

## callees

- `0x18000dd94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000de2a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ddb5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ddb5`
- `CRYPT32!I_CryptCreateLruCache` at `0x18000de0f`
- `CRYPT32!I_CryptCreateLruCache` at `0x18000de0f`

## pseudocode

```c
__int64 __fastcall CCatalogCache::Initialize(CCatalogCache *this)
{
  unsigned int LruCache; // ebx
  _QWORD v3[7]; // [rsp+20h] [rbp-38h] BYREF

  InitializeCriticalSection(&g_CatalogCache);
  v3[0] = 1;
  v3[3] = 0;
  qword_180069DC0 = 0;
  v3[1] = CatalogCacheFreeEntryData;
  v3[2] = CatalogCacheHashIdentifier;
  v3[4] = 0x300000003LL;
  LruCache = I_CryptCreateLruCache(v3, &qword_180069DC0);
  if ( !LruCache )
    DeleteCriticalSection(&g_CatalogCache);
  return LruCache;
}

```

## disassembly

```asm
0x18000dd94  push    rbx
0x18000dd96  sub     rsp, 50h
0x18000dd9a  xorps   xmm0, xmm0
0x18000dd9d  xor     eax, eax
0x18000dd9f  movups  [rsp+58h+var_38], xmm0
0x18000dda4  movups  [rsp+58h+var_28], xmm0
0x18000dda9  mov     [rsp+58h+var_18], rax
0x18000ddae  lea     rcx, ?g_CatalogCache@@3VCCatalogCache@@A; lpCriticalSection
0x18000ddb5  call    cs:__imp_InitializeCriticalSection
0x18000ddbb  jmp     short loc_18000DDC1
0x18000ddbd  xor     eax, eax
0x18000ddbf  jmp     short loc_18000DE1D
0x18000ddc1  mov     qword ptr [rsp+58h+var_38], 1
0x18000ddca  mov     qword ptr [rsp+58h+var_28+8], 0
0x18000ddd3  mov     cs:qword_180069DC0, 0
0x18000ddde  lea     rax, ?CatalogCacheFreeEntryData@@YAXPEAX@Z; CatalogCacheFreeEntryData(void *)
0x18000dde5  mov     qword ptr [rsp+58h+var_38+8], rax
0x18000ddea  lea     rax, ?CatalogCacheHashIdentifier@@YAKPEAU_CRYPTOAPI_BLOB@@@Z; CatalogCacheHashIdentifier(_CRYPTOAPI_BLOB *)
0x18000ddf1  mov     qword ptr [rsp+58h+var_28], rax
0x18000ddf6  mov     eax, 3
0x18000ddfb  mov     dword ptr [rsp+58h+var_18], eax
0x18000ddff  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000de03  lea     rdx, qword_180069DC0
0x18000de0a  lea     rcx, [rsp+58h+var_38]
0x18000de0f  call    cs:__imp_I_CryptCreateLruCache
0x18000de15  mov     ebx, eax
0x18000de17  test    eax, eax
0x18000de19  jz      short loc_18000DE23
0x18000de1b  mov     eax, ebx
0x18000de1d  add     rsp, 50h
0x18000de21  pop     rbx
0x18000de22  retn
0x18000de23  lea     rcx, ?g_CatalogCache@@3VCCatalogCache@@A; lpCriticalSection
0x18000de2a  call    cs:__imp_DeleteCriticalSection
0x18000de30  jmp     short loc_18000DE1B
```
