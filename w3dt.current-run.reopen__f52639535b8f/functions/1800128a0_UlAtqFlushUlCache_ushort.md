# UlAtqFlushUlCache(ushort *)

- ea: `0x1800128a0`
- end: `0x180012932`
- name: `?UlAtqFlushUlCache@@YAJPEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(PCWSTR UrlPrefix)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800128a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800128e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800128e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001290c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001290c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800128ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800128ca`
- `HTTPAPI!HttpFlushResponseCache` at `0x180012903`
- `HTTPAPI!HttpFlushResponseCache` at `0x180012903`

## pseudocode

```c
__int64 __fastcall UlAtqFlushUlCache(PCWSTR UrlPrefix)
{
  WP_CONTEXT *v2; // rsi
  _QWORD *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  void *v5; // rcx

  if ( !UrlPrefix )
    return 2147942487LL;
  v2 = g_pwpContext;
  if ( !g_pwpContext )
    return 2147942450LL;
  v3 = (_QWORD *)*((_QWORD *)g_pwpContext + 96);
  v4 = (RTL_SRWLOCK *)(v3[1] * ((unsigned __int64)GetCurrentThreadId() % v3[2]) + *v3);
  AcquireSRWLockShared(v4);
  v5 = (void *)*((_QWORD *)v2 + 95);
  if ( v5 )
    HttpFlushResponseCache(v5, UrlPrefix, 0, 0);
  ReleaseSRWLockShared(v4);
  return 0;
}

```

## disassembly

```asm
0x1800128a0  mov     [rsp+arg_0], rbx
0x1800128a5  mov     [rsp+arg_8], rsi
0x1800128aa  push    rdi
0x1800128ab  sub     rsp, 20h
0x1800128af  mov     rdi, rcx
0x1800128b2  test    rcx, rcx
0x1800128b5  jz      short loc_180012924
0x1800128b7  mov     rsi, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x1800128be  test    rsi, rsi
0x1800128c1  jz      short loc_18001292B
0x1800128c3  mov     rbx, [rsi+300h]
0x1800128ca  call    cs:__imp_GetCurrentThreadId
0x1800128d0  mov     eax, eax
0x1800128d2  xor     edx, edx
0x1800128d4  div     qword ptr [rbx+10h]
0x1800128d8  mov     ecx, edx
0x1800128da  imul    rcx, [rbx+8]
0x1800128df  mov     rbx, [rbx]
0x1800128e2  add     rbx, rcx
0x1800128e5  mov     rcx, rbx; SRWLock
0x1800128e8  call    cs:__imp_AcquireSRWLockShared
0x1800128ee  mov     rcx, [rsi+2F8h]; RequestQueueHandle
0x1800128f5  test    rcx, rcx
0x1800128f8  jz      short loc_180012909
0x1800128fa  xor     r9d, r9d; Overlapped
0x1800128fd  xor     r8d, r8d; Flags
0x180012900  mov     rdx, rdi; UrlPrefix
0x180012903  call    cs:__imp_HttpFlushResponseCache
0x180012909  mov     rcx, rbx; SRWLock
0x18001290c  call    cs:__imp_ReleaseSRWLockShared
0x180012912  xor     eax, eax
0x180012914  mov     rbx, [rsp+28h+arg_0]
0x180012919  mov     rsi, [rsp+28h+arg_8]
0x18001291e  add     rsp, 20h
0x180012922  pop     rdi
0x180012923  retn
0x180012924  mov     eax, 80070057h
0x180012929  jmp     short loc_180012914
0x18001292b  mov     eax, 80070032h
0x180012930  jmp     short loc_180012914
```
