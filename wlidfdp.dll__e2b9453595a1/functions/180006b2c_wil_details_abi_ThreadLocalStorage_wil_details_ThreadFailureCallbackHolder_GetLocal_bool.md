# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006b2c`
- end: `0x180006bca`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000665c`
- `0x18000d818`

## callees

- `0x180006b2c`
- `0x180007a58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b3f`

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
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

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
  v9 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v10 = (signed __int64)v9;
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x180006b2c  push    rbx
0x180006b2e  push    rbp
0x180006b2f  push    rsi
0x180006b30  push    rdi
0x180006b31  sub     rsp, 28h
0x180006b35  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006b3c  mov     bpl, dl
0x180006b3f  call    cs:__imp_GetCurrentThreadId
0x180006b45  mov     ebx, eax
0x180006b47  mov     esi, eax
0x180006b49  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006b53  shr     rbx, 2
0x180006b57  mul     rbx
0x180006b5a  shr     rdx, 3
0x180006b5e  lea     rcx, [rdx+rdx*4]
0x180006b62  add     rcx, rcx
0x180006b65  sub     rbx, rcx
0x180006b68  mov     rax, [rdi+rbx*8]
0x180006b6c  test    rax, rax
0x180006b6f  jz      short loc_180006B81
0x180006b71  cmp     [rax], esi
0x180006b73  jz      short loc_180006B7B
0x180006b75  mov     rax, [rax+8]
0x180006b79  jmp     short loc_180006B6C
0x180006b7b  add     rax, 10h
0x180006b7f  jmp     short loc_180006BC1
0x180006b81  test    bpl, bpl
0x180006b84  jz      short loc_180006BBF
0x180006b86  mov     edx, 18h; dwBytes
0x180006b8b  xor     ecx, ecx; dwFlags
0x180006b8d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006b92  mov     rcx, rax
0x180006b95  test    rax, rax
0x180006b98  jz      short loc_180006BBF
0x180006b9a  mov     [rax], esi
0x180006b9c  xor     eax, eax
0x180006b9e  mov     [rcx+4], eax
0x180006ba1  mov     [rcx+8], rax
0x180006ba5  mov     [rcx+10h], rax
0x180006ba9  mov     rax, [rdi+rbx*8]
0x180006bad  mov     [rcx+8], rax
0x180006bb1  lock cmpxchg [rdi+rbx*8], rcx
0x180006bb7  jnz     short loc_180006BA9
0x180006bb9  lea     rax, [rcx+10h]
0x180006bbd  jmp     short loc_180006BC1
0x180006bbf  xor     eax, eax
0x180006bc1  add     rsp, 28h
0x180006bc5  pop     rdi
0x180006bc6  pop     rsi
0x180006bc7  pop     rbp
0x180006bc8  pop     rbx
0x180006bc9  retn
```
