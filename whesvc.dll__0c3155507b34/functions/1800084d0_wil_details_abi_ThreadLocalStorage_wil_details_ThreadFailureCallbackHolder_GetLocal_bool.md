# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800084d0`
- end: `0x18000856c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b1d8`
- `0x18001ae08`
- `0x18001b190`
- `0x18001bbc8`
- `0x1800238cc`

## callees

- `0x1800084d0`
- `0x180008c88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084e3`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v6 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v2 + 8 * v6); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v8 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v9 = (signed __int64)v8;
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v10 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v9, v10) );
  return v9 + 16;
}

```

## disassembly

```asm
0x1800084d0  push    rbx
0x1800084d2  push    rbp
0x1800084d3  push    rsi
0x1800084d4  push    rdi
0x1800084d5  sub     rsp, 28h
0x1800084d9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800084e0  mov     bpl, dl
0x1800084e3  call    cs:__imp_GetCurrentThreadId
0x1800084e9  mov     ebx, eax
0x1800084eb  mov     esi, eax
0x1800084ed  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800084f7  shr     rbx, 2
0x1800084fb  mul     rbx
0x1800084fe  shr     rdx, 3
0x180008502  lea     rcx, [rdx+rdx*4]
0x180008506  add     rcx, rcx
0x180008509  sub     rbx, rcx
0x18000850c  mov     rax, [rdi+rbx*8]
0x180008510  jmp     short loc_18000851A
0x180008512  cmp     [rax], esi
0x180008514  jz      short loc_18000855B
0x180008516  mov     rax, [rax+8]
0x18000851a  test    rax, rax
0x18000851d  jnz     short loc_180008512
0x18000851f  test    bpl, bpl
0x180008522  jz      short loc_180008561
0x180008524  lea     edx, [rax+18h]; dwBytes
0x180008527  xor     ecx, ecx; dwFlags
0x180008529  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000852e  mov     rcx, rax
0x180008531  test    rax, rax
0x180008534  jz      short loc_180008561
0x180008536  mov     [rax], esi
0x180008538  xor     eax, eax
0x18000853a  mov     [rcx+4], eax
0x18000853d  mov     [rcx+8], rax
0x180008541  mov     [rcx+10h], rax
0x180008545  mov     rax, [rdi+rbx*8]
0x180008549  mov     [rcx+8], rax
0x18000854d  lock cmpxchg [rdi+rbx*8], rcx
0x180008553  jnz     short loc_180008545
0x180008555  lea     rax, [rcx+10h]
0x180008559  jmp     short loc_180008563
0x18000855b  add     rax, 10h
0x18000855f  jmp     short loc_180008563
0x180008561  xor     eax, eax
0x180008563  add     rsp, 28h
0x180008567  pop     rdi
0x180008568  pop     rsi
0x180008569  pop     rbp
0x18000856a  pop     rbx
0x18000856b  retn
```
