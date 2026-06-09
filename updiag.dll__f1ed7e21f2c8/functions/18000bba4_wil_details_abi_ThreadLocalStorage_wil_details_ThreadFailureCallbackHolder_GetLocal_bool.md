# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000bba4`
- end: `0x18000bc53`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c4a0`
- `0x180015fb0`
- `0x1800360f8`
- `0x180036a08`
- `0x1800371e8`

## callees

- `0x18000a438`
- `0x18000bba4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbc2`

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
  v6 = CurrentThreadId % 0xAuLL;
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
0x18000bba4  mov     [rsp+arg_0], rbx
0x18000bba9  mov     [rsp+arg_8], rbp
0x18000bbae  mov     [rsp+arg_10], rsi
0x18000bbb3  push    rdi
0x18000bbb4  sub     rsp, 20h
0x18000bbb8  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000bbbf  mov     bpl, dl
0x18000bbc2  call    cs:__imp_GetCurrentThreadId
0x18000bbc8  mov     ebx, eax
0x18000bbca  mov     esi, eax
0x18000bbcc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000bbd6  mul     rsi
0x18000bbd9  shr     rdx, 3
0x18000bbdd  lea     rcx, [rdx+rdx*4]
0x18000bbe1  add     rcx, rcx
0x18000bbe4  sub     rbx, rcx
0x18000bbe7  mov     rax, [rdi+rbx*8]
0x18000bbeb  jmp     short loc_18000BBF5
0x18000bbed  cmp     [rax], esi
0x18000bbef  jz      short loc_18000BC36
0x18000bbf1  mov     rax, [rax+8]
0x18000bbf5  test    rax, rax
0x18000bbf8  jnz     short loc_18000BBED
0x18000bbfa  test    bpl, bpl
0x18000bbfd  jz      short loc_18000BC3C
0x18000bbff  lea     edx, [rax+18h]; dwBytes
0x18000bc02  xor     ecx, ecx; dwFlags
0x18000bc04  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bc09  mov     rcx, rax
0x18000bc0c  test    rax, rax
0x18000bc0f  jz      short loc_18000BC3C
0x18000bc11  mov     [rax], esi
0x18000bc13  xor     eax, eax
0x18000bc15  mov     [rcx+4], eax
0x18000bc18  mov     [rcx+8], rax
0x18000bc1c  mov     [rcx+10h], rax
0x18000bc20  mov     rax, [rdi+rbx*8]
0x18000bc24  mov     [rcx+8], rax
0x18000bc28  lock cmpxchg [rdi+rbx*8], rcx
0x18000bc2e  jnz     short loc_18000BC20
0x18000bc30  lea     rax, [rcx+10h]
0x18000bc34  jmp     short loc_18000BC3E
0x18000bc36  add     rax, 10h
0x18000bc3a  jmp     short loc_18000BC3E
0x18000bc3c  xor     eax, eax
0x18000bc3e  mov     rbx, [rsp+28h+arg_0]
0x18000bc43  mov     rbp, [rsp+28h+arg_8]
0x18000bc48  mov     rsi, [rsp+28h+arg_10]
0x18000bc4d  add     rsp, 20h
0x18000bc51  pop     rdi
0x18000bc52  retn
```
