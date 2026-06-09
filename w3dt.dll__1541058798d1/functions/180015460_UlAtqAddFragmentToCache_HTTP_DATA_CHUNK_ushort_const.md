# UlAtqAddFragmentToCache(_HTTP_DATA_CHUNK *,ushort const *)

- ea: `0x180015460`
- end: `0x1800154f6`
- name: `?UlAtqAddFragmentToCache@@YAJPEAU_HTTP_DATA_CHUNK@@PEBG@Z`
- size: `150`
- prototype: `__int64 __fastcall(PHTTP_DATA_CHUNK DataChunk, PCWSTR UrlPrefix)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012050`
- `0x180015460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800154d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800154d6`
- `HTTPAPI!HttpAddFragmentToCache` at `0x1800154c2`
- `HTTPAPI!HttpAddFragmentToCache` at `0x1800154c2`

## pseudocode

```c
__int64 __fastcall UlAtqAddFragmentToCache(PHTTP_DATA_CHUNK DataChunk, PCWSTR UrlPrefix)
{
  void *v5; // rax
  signed int v6; // ebx
  struct _HTTP_CACHE_POLICY CachePolicy; // [rsp+50h] [rbp+18h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp+20h] BYREF

  CachePolicy = (struct _HTTP_CACHE_POLICY)1LL;
  SRWLock = 0;
  if ( !g_pwpContext )
    return 2147942450LL;
  v5 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
  if ( v5 )
    v6 = HttpAddFragmentToCache(v5, UrlPrefix, DataChunk, &CachePolicy, 0);
  else
    v6 = 6;
  ReleaseSRWLockShared(SRWLock);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015460  mov     [rsp+arg_0], rbx
0x180015465  push    rdi
0x180015466  sub     rsp, 30h
0x18001546a  mov     rdi, rcx
0x18001546d  mov     qword ptr [rsp+38h+CachePolicy.Policy], 1
0x180015476  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18001547d  mov     rbx, rdx
0x180015480  mov     [rsp+38h+SRWLock], 0
0x180015489  test    rcx, rcx
0x18001548c  jnz     short loc_180015495
0x18001548e  mov     eax, 80070032h
0x180015493  jmp     short loc_1800154EB
0x180015495  add     rcx, 2F8h; this
0x18001549c  lea     rdx, [rsp+38h+SRWLock]; void **
0x1800154a1  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x1800154a6  test    rax, rax
0x1800154a9  jz      short loc_1800154CC
0x1800154ab  lea     r9, [rsp+38h+CachePolicy]; CachePolicy
0x1800154b0  mov     [rsp+38h+Overlapped], 0; Overlapped
0x1800154b9  mov     r8, rdi; DataChunk
0x1800154bc  mov     rdx, rbx; UrlPrefix
0x1800154bf  mov     rcx, rax; RequestQueueHandle
0x1800154c2  call    cs:__imp_HttpAddFragmentToCache
0x1800154c8  mov     ebx, eax
0x1800154ca  jmp     short loc_1800154D1
0x1800154cc  mov     ebx, 6
0x1800154d1  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800154d6  call    cs:__imp_ReleaseSRWLockShared
0x1800154dc  test    ebx, ebx
0x1800154de  jle     short loc_1800154E9
0x1800154e0  movzx   ebx, bx
0x1800154e3  or      ebx, 80070000h
0x1800154e9  mov     eax, ebx
0x1800154eb  mov     rbx, [rsp+38h+arg_0]
0x1800154f0  add     rsp, 30h
0x1800154f4  pop     rdi
0x1800154f5  retn
```
