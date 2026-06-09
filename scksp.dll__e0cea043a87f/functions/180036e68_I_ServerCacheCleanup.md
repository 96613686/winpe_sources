# I_ServerCacheCleanup

- ea: `0x180036e68`
- end: `0x180036eed`
- name: `I_ServerCacheCleanup`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180037070`
- `0x1800375d4`

## callees

- `0x18000d9d0`
- `0x180036e68`
- `0x180036ef4`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e75`

## pseudocode

```c
__int64 (__fastcall *__fastcall I_ServerCacheCleanup(
        struct _RTL_CRITICAL_SECTION *a1))(struct _RTL_CRITICAL_SECTION *, ULONG_PTR)
{
  ULONG_PTR SpinCount; // rdx
  ULONG_PTR v3; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r14
  __int64 i; // rsi
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 (__fastcall *result)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR); // rax

  DeleteCriticalSection(a1);
  SpinCount = a1[1].SpinCount;
  if ( SpinCount )
  {
    do
    {
      v3 = *(_QWORD *)(SpinCount + 48);
      I_ServerCacheFreeItem(a1);
      a1[1].SpinCount = v3;
      SpinCount = v3;
    }
    while ( v3 );
  }
  DebugInfo = a1[1].DebugInfo;
  if ( DebugInfo )
  {
    for ( i = 0; i != 16; ++i )
    {
      v6 = *((_QWORD *)&DebugInfo->Type + i);
      if ( v6 )
      {
        do
        {
          v7 = *(_QWORD *)(v6 + 16);
          CspFreeH(v6);
          v6 = v7;
        }
        while ( v7 );
      }
    }
    CspFreeH(DebugInfo);
  }
  result = (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))a1[1].OwningThread;
  if ( result )
    return (__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, ULONG_PTR))result(a1, SpinCount);
  return result;
}

```

## disassembly

```asm
0x180036e68  push    rbx
0x180036e6a  push    rsi
0x180036e6b  push    rdi
0x180036e6c  push    r14
0x180036e6e  sub     rsp, 28h
0x180036e72  mov     rdi, rcx
0x180036e75  call    cs:__imp_DeleteCriticalSection
0x180036e7b  mov     rdx, [rdi+48h]
0x180036e7f  test    rdx, rdx
0x180036e82  jz      short loc_180036E9C
0x180036e84  mov     rbx, [rdx+30h]
0x180036e88  mov     rcx, rdi
0x180036e8b  call    I_ServerCacheFreeItem
0x180036e90  mov     [rdi+48h], rbx
0x180036e94  mov     rdx, rbx
0x180036e97  test    rbx, rbx
0x180036e9a  jnz     short loc_180036E84
0x180036e9c  mov     r14, [rdi+28h]
0x180036ea0  test    r14, r14
0x180036ea3  jz      short loc_180036ED2
0x180036ea5  xor     esi, esi
0x180036ea7  mov     rcx, [r14+rsi*8]
0x180036eab  test    rcx, rcx
0x180036eae  jz      short loc_180036EC1
0x180036eb0  mov     rbx, [rcx+10h]
0x180036eb4  call    CspFreeH
0x180036eb9  mov     rcx, rbx
0x180036ebc  test    rbx, rbx
0x180036ebf  jnz     short loc_180036EB0
0x180036ec1  inc     rsi
0x180036ec4  cmp     rsi, 10h
0x180036ec8  jnz     short loc_180036EA7
0x180036eca  mov     rcx, r14
0x180036ecd  call    CspFreeH
0x180036ed2  mov     rax, [rdi+38h]
0x180036ed6  test    rax, rax
0x180036ed9  jz      short loc_180036EE3
0x180036edb  mov     rcx, rdi
0x180036ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ee3  add     rsp, 28h
0x180036ee7  pop     r14
0x180036ee9  pop     rdi
0x180036eea  pop     rsi
0x180036eeb  pop     rbx
0x180036eec  retn
```
