# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800070ac`
- end: `0x18000715b`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `175`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000acf4`

## callees

- `0x180003584`
- `0x1800070ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070ca`

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
0x1800070ac  mov     [rsp+arg_0], rbx
0x1800070b1  mov     [rsp+arg_8], rbp
0x1800070b6  mov     [rsp+arg_10], rsi
0x1800070bb  push    rdi
0x1800070bc  sub     rsp, 20h
0x1800070c0  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800070c7  mov     bpl, dl
0x1800070ca  call    cs:__imp_GetCurrentThreadId
0x1800070d0  mov     ebx, eax
0x1800070d2  mov     esi, eax
0x1800070d4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800070de  mul     rsi
0x1800070e1  shr     rdx, 3
0x1800070e5  lea     rcx, [rdx+rdx*4]
0x1800070e9  add     rcx, rcx
0x1800070ec  sub     rbx, rcx
0x1800070ef  mov     rax, [rdi+rbx*8]
0x1800070f3  jmp     short loc_1800070FD
0x1800070f5  cmp     [rax], esi
0x1800070f7  jz      short loc_18000713E
0x1800070f9  mov     rax, [rax+8]
0x1800070fd  test    rax, rax
0x180007100  jnz     short loc_1800070F5
0x180007102  test    bpl, bpl
0x180007105  jz      short loc_180007144
0x180007107  lea     edx, [rax+18h]; dwBytes
0x18000710a  xor     ecx, ecx; dwFlags
0x18000710c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007111  mov     rcx, rax
0x180007114  test    rax, rax
0x180007117  jz      short loc_180007144
0x180007119  mov     [rax], esi
0x18000711b  xor     eax, eax
0x18000711d  mov     [rcx+4], eax
0x180007120  mov     [rcx+8], rax
0x180007124  mov     [rcx+10h], rax
0x180007128  mov     rax, [rdi+rbx*8]
0x18000712c  mov     [rcx+8], rax
0x180007130  lock cmpxchg [rdi+rbx*8], rcx
0x180007136  jnz     short loc_180007128
0x180007138  lea     rax, [rcx+10h]
0x18000713c  jmp     short loc_180007146
0x18000713e  add     rax, 10h
0x180007142  jmp     short loc_180007146
0x180007144  xor     eax, eax
0x180007146  mov     rbx, [rsp+28h+arg_0]
0x18000714b  mov     rbp, [rsp+28h+arg_8]
0x180007150  mov     rsi, [rsp+28h+arg_10]
0x180007155  add     rsp, 20h
0x180007159  pop     rdi
0x18000715a  retn
```
