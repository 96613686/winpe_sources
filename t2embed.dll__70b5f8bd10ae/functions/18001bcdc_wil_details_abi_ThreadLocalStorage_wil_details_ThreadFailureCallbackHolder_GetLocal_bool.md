# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001bcdc`
- end: `0x18001bd7a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf4c`
- `0x180024248`

## callees

- `0x18001bcdc`
- `0x18002551c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001bcef`
- `KERNEL32!GetCurrentThreadId` at `0x18001bcef`

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
0x18001bcdc  push    rbx
0x18001bcde  push    rbp
0x18001bcdf  push    rsi
0x18001bce0  push    rdi
0x18001bce1  sub     rsp, 28h
0x18001bce5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bcec  mov     bpl, dl
0x18001bcef  call    cs:__imp_GetCurrentThreadId
0x18001bcf5  mov     ebx, eax
0x18001bcf7  mov     esi, eax
0x18001bcf9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001bd03  shr     rbx, 2
0x18001bd07  mul     rbx
0x18001bd0a  shr     rdx, 3
0x18001bd0e  lea     rcx, [rdx+rdx*4]
0x18001bd12  add     rcx, rcx
0x18001bd15  sub     rbx, rcx
0x18001bd18  mov     rax, [rdi+rbx*8]
0x18001bd1c  test    rax, rax
0x18001bd1f  jz      short loc_18001BD31
0x18001bd21  cmp     [rax], esi
0x18001bd23  jz      short loc_18001BD2B
0x18001bd25  mov     rax, [rax+8]
0x18001bd29  jmp     short loc_18001BD1C
0x18001bd2b  add     rax, 10h
0x18001bd2f  jmp     short loc_18001BD71
0x18001bd31  test    bpl, bpl
0x18001bd34  jz      short loc_18001BD6F
0x18001bd36  mov     edx, 18h; dwBytes
0x18001bd3b  xor     ecx, ecx; dwFlags
0x18001bd3d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001bd42  mov     rcx, rax
0x18001bd45  test    rax, rax
0x18001bd48  jz      short loc_18001BD6F
0x18001bd4a  mov     [rax], esi
0x18001bd4c  xor     eax, eax
0x18001bd4e  mov     [rcx+4], eax
0x18001bd51  mov     [rcx+8], rax
0x18001bd55  mov     [rcx+10h], rax
0x18001bd59  mov     rax, [rdi+rbx*8]
0x18001bd5d  mov     [rcx+8], rax
0x18001bd61  lock cmpxchg [rdi+rbx*8], rcx
0x18001bd67  jnz     short loc_18001BD59
0x18001bd69  lea     rax, [rcx+10h]
0x18001bd6d  jmp     short loc_18001BD71
0x18001bd6f  xor     eax, eax
0x18001bd71  add     rsp, 28h
0x18001bd75  pop     rdi
0x18001bd76  pop     rsi
0x18001bd77  pop     rbp
0x18001bd78  pop     rbx
0x18001bd79  retn
```
