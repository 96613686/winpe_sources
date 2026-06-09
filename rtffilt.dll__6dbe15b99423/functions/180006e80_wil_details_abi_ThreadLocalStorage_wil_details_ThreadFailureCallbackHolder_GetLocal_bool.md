# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006e80`
- end: `0x180006f1c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f9c0`
- `0x180010b80`

## callees

- `0x180006e80`
- `0x180007d28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e93`

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
0x180006e80  push    rbx
0x180006e82  push    rbp
0x180006e83  push    rsi
0x180006e84  push    rdi
0x180006e85  sub     rsp, 28h
0x180006e89  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006e90  mov     bpl, dl
0x180006e93  call    cs:__imp_GetCurrentThreadId
0x180006e99  mov     ebx, eax
0x180006e9b  mov     esi, eax
0x180006e9d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006ea7  shr     rbx, 2
0x180006eab  mul     rbx
0x180006eae  shr     rdx, 3
0x180006eb2  lea     rcx, [rdx+rdx*4]
0x180006eb6  add     rcx, rcx
0x180006eb9  sub     rbx, rcx
0x180006ebc  mov     rax, [rdi+rbx*8]
0x180006ec0  jmp     short loc_180006ECA
0x180006ec2  cmp     [rax], esi
0x180006ec4  jz      short loc_180006F0B
0x180006ec6  mov     rax, [rax+8]
0x180006eca  test    rax, rax
0x180006ecd  jnz     short loc_180006EC2
0x180006ecf  test    bpl, bpl
0x180006ed2  jz      short loc_180006F11
0x180006ed4  lea     edx, [rax+18h]; dwBytes
0x180006ed7  xor     ecx, ecx; dwFlags
0x180006ed9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006ede  mov     rcx, rax
0x180006ee1  test    rax, rax
0x180006ee4  jz      short loc_180006F11
0x180006ee6  mov     [rax], esi
0x180006ee8  xor     eax, eax
0x180006eea  mov     [rcx+4], eax
0x180006eed  mov     [rcx+8], rax
0x180006ef1  mov     [rcx+10h], rax
0x180006ef5  mov     rax, [rdi+rbx*8]
0x180006ef9  mov     [rcx+8], rax
0x180006efd  lock cmpxchg [rdi+rbx*8], rcx
0x180006f03  jnz     short loc_180006EF5
0x180006f05  lea     rax, [rcx+10h]
0x180006f09  jmp     short loc_180006F13
0x180006f0b  add     rax, 10h
0x180006f0f  jmp     short loc_180006F13
0x180006f11  xor     eax, eax
0x180006f13  add     rsp, 28h
0x180006f17  pop     rdi
0x180006f18  pop     rsi
0x180006f19  pop     rbp
0x180006f1a  pop     rbx
0x180006f1b  retn
```
