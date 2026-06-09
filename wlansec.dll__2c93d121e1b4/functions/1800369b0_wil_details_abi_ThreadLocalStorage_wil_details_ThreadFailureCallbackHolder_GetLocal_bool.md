# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800369b0`
- end: `0x180036a55`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034144`
- `0x18005e534`

## callees

- `0x1800369b0`
- `0x18004e32c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800369c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800369c3`

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
0x1800369b0  push    rbx
0x1800369b2  push    rbp
0x1800369b3  push    rsi
0x1800369b4  push    rdi
0x1800369b5  sub     rsp, 28h
0x1800369b9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800369c0  mov     bpl, dl
0x1800369c3  call    cs:__imp_GetCurrentThreadId
0x1800369ca  nop     dword ptr [rax+rax+00h]
0x1800369cf  mov     ebx, eax
0x1800369d1  mov     esi, eax
0x1800369d3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800369dd  shr     rbx, 2
0x1800369e1  mul     rbx
0x1800369e4  shr     rdx, 3
0x1800369e8  lea     rcx, [rdx+rdx*4]
0x1800369ec  add     rcx, rcx
0x1800369ef  sub     rbx, rcx
0x1800369f2  mov     rax, [rdi+rbx*8]
0x1800369f6  test    rax, rax
0x1800369f9  jz      short loc_180036A0B
0x1800369fb  cmp     [rax], esi
0x1800369fd  jz      short loc_180036A05
0x1800369ff  mov     rax, [rax+8]
0x180036a03  jmp     short loc_1800369F6
0x180036a05  add     rax, 10h
0x180036a09  jmp     short loc_180036A4B
0x180036a0b  test    bpl, bpl
0x180036a0e  jz      short loc_180036A49
0x180036a10  mov     edx, 18h; dwBytes
0x180036a15  xor     ecx, ecx; dwFlags
0x180036a17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180036a1c  mov     rcx, rax
0x180036a1f  test    rax, rax
0x180036a22  jz      short loc_180036A49
0x180036a24  mov     [rax], esi
0x180036a26  xor     eax, eax
0x180036a28  mov     [rcx+4], eax
0x180036a2b  mov     [rcx+8], rax
0x180036a2f  mov     [rcx+10h], rax
0x180036a33  mov     rax, [rdi+rbx*8]
0x180036a37  mov     [rcx+8], rax
0x180036a3b  lock cmpxchg [rdi+rbx*8], rcx
0x180036a41  jnz     short loc_180036A33
0x180036a43  lea     rax, [rcx+10h]
0x180036a47  jmp     short loc_180036A4B
0x180036a49  xor     eax, eax
0x180036a4b  add     rsp, 28h
0x180036a4f  pop     rdi
0x180036a50  pop     rsi
0x180036a51  pop     rbp
0x180036a52  pop     rbx
0x180036a53  retn
```
