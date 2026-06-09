# UlAtqRemoveFragmentFromCache(ushort const *)

- ea: `0x1800158e0`
- end: `0x180015956`
- name: `?UlAtqRemoveFragmentFromCache@@YAJPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(PCWSTR UrlPrefix)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012050`
- `0x1800158e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001593b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001593b`
- `HTTPAPI!HttpFlushResponseCache` at `0x180015927`
- `HTTPAPI!HttpFlushResponseCache` at `0x180015927`

## pseudocode

```c
__int64 __fastcall UlAtqRemoveFragmentFromCache(PCWSTR UrlPrefix)
{
  void *v3; // rax
  signed int v4; // ebx
  PSRWLOCK SRWLock; // [rsp+38h] [rbp+10h] BYREF

  SRWLock = 0;
  if ( !g_pwpContext )
    return 2147942450LL;
  v3 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), (void **)&SRWLock);
  if ( v3 )
    v4 = HttpFlushResponseCache(v3, UrlPrefix, 0, 0);
  else
    v4 = 6;
  ReleaseSRWLockShared(SRWLock);
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800158e0  push    rbx
0x1800158e2  sub     rsp, 20h
0x1800158e6  mov     rbx, rcx
0x1800158e9  mov     [rsp+28h+SRWLock], 0
0x1800158f2  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x1800158f9  test    rcx, rcx
0x1800158fc  jnz     short loc_180015905
0x1800158fe  mov     eax, 80070032h
0x180015903  jmp     short loc_180015950
0x180015905  add     rcx, 2F8h; this
0x18001590c  lea     rdx, [rsp+28h+SRWLock]; void **
0x180015911  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x180015916  test    rax, rax
0x180015919  jz      short loc_180015931
0x18001591b  xor     r9d, r9d; Overlapped
0x18001591e  xor     r8d, r8d; Flags
0x180015921  mov     rdx, rbx; UrlPrefix
0x180015924  mov     rcx, rax; RequestQueueHandle
0x180015927  call    cs:__imp_HttpFlushResponseCache
0x18001592d  mov     ebx, eax
0x18001592f  jmp     short loc_180015936
0x180015931  mov     ebx, 6
0x180015936  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18001593b  call    cs:__imp_ReleaseSRWLockShared
0x180015941  test    ebx, ebx
0x180015943  jle     short loc_18001594E
0x180015945  movzx   ebx, bx
0x180015948  or      ebx, 80070000h
0x18001594e  mov     eax, ebx
0x180015950  add     rsp, 20h
0x180015954  pop     rbx
0x180015955  retn
```
