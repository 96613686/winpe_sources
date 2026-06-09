# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800058dc`
- end: `0x18000597a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005868`
- `0x180009bf4`

## callees

- `0x1800058dc`
- `0x180005eb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ef`

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
0x1800058dc  push    rbx
0x1800058de  push    rbp
0x1800058df  push    rsi
0x1800058e0  push    rdi
0x1800058e1  sub     rsp, 28h
0x1800058e5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800058ec  mov     bpl, dl
0x1800058ef  call    cs:__imp_GetCurrentThreadId
0x1800058f5  mov     ebx, eax
0x1800058f7  mov     esi, eax
0x1800058f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005903  shr     rbx, 2
0x180005907  mul     rbx
0x18000590a  shr     rdx, 3
0x18000590e  lea     rcx, [rdx+rdx*4]
0x180005912  add     rcx, rcx
0x180005915  sub     rbx, rcx
0x180005918  mov     rax, [rdi+rbx*8]
0x18000591c  test    rax, rax
0x18000591f  jz      short loc_180005938
0x180005921  cmp     [rax], esi
0x180005923  jz      short loc_18000592B
0x180005925  mov     rax, [rax+8]
0x180005929  jmp     short loc_18000591C
0x18000592b  add     rax, 10h
0x18000592f  add     rsp, 28h
0x180005933  pop     rdi
0x180005934  pop     rsi
0x180005935  pop     rbp
0x180005936  pop     rbx
0x180005937  retn
0x180005938  test    bpl, bpl
0x18000593b  jz      short loc_180005976
0x18000593d  mov     edx, 18h; dwBytes
0x180005942  xor     ecx, ecx; dwFlags
0x180005944  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005949  mov     rcx, rax
0x18000594c  test    rax, rax
0x18000594f  jz      short loc_180005976
0x180005951  mov     [rax], esi
0x180005953  xor     eax, eax
0x180005955  mov     [rcx+4], eax
0x180005958  mov     [rcx+8], rax
0x18000595c  mov     [rcx+10h], rax
0x180005960  mov     rax, [rdi+rbx*8]
0x180005964  mov     [rcx+8], rax
0x180005968  lock cmpxchg [rdi+rbx*8], rcx
0x18000596e  jnz     short loc_180005960
0x180005970  lea     rax, [rcx+10h]
0x180005974  jmp     short loc_18000592F
0x180005976  xor     eax, eax
0x180005978  jmp     short loc_18000592F
```
