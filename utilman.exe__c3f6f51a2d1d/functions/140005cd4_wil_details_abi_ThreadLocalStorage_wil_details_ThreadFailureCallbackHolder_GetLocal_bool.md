# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140005cd4`
- end: `0x140005d79`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400057d4`
- `0x14000f650`

## callees

- `0x140005cd4`
- `0x140007100`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005ce7`
- `KERNEL32!GetCurrentThreadId` at `0x140005ce7`

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
0x140005cd4  push    rbx
0x140005cd6  push    rbp
0x140005cd7  push    rsi
0x140005cd8  push    rdi
0x140005cd9  sub     rsp, 28h
0x140005cdd  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005ce4  mov     bpl, dl
0x140005ce7  call    cs:__imp_GetCurrentThreadId
0x140005cee  nop     dword ptr [rax+rax+00h]
0x140005cf3  mov     ebx, eax
0x140005cf5  mov     esi, eax
0x140005cf7  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005d01  shr     rbx, 2
0x140005d05  mul     rbx
0x140005d08  shr     rdx, 3
0x140005d0c  lea     rcx, [rdx+rdx*4]
0x140005d10  add     rcx, rcx
0x140005d13  sub     rbx, rcx
0x140005d16  mov     rax, [rdi+rbx*8]
0x140005d1a  test    rax, rax
0x140005d1d  jz      short loc_140005D2F
0x140005d1f  cmp     [rax], esi
0x140005d21  jz      short loc_140005D29
0x140005d23  mov     rax, [rax+8]
0x140005d27  jmp     short loc_140005D1A
0x140005d29  add     rax, 10h
0x140005d2d  jmp     short loc_140005D6F
0x140005d2f  test    bpl, bpl
0x140005d32  jz      short loc_140005D6D
0x140005d34  mov     edx, 18h; dwBytes
0x140005d39  xor     ecx, ecx; dwFlags
0x140005d3b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005d40  mov     rcx, rax
0x140005d43  test    rax, rax
0x140005d46  jz      short loc_140005D6D
0x140005d48  mov     [rax], esi
0x140005d4a  xor     eax, eax
0x140005d4c  mov     [rcx+4], eax
0x140005d4f  mov     [rcx+8], rax
0x140005d53  mov     [rcx+10h], rax
0x140005d57  mov     rax, [rdi+rbx*8]
0x140005d5b  mov     [rcx+8], rax
0x140005d5f  lock cmpxchg [rdi+rbx*8], rcx
0x140005d65  jnz     short loc_140005D57
0x140005d67  lea     rax, [rcx+10h]
0x140005d6b  jmp     short loc_140005D6F
0x140005d6d  xor     eax, eax
0x140005d6f  add     rsp, 28h
0x140005d73  pop     rdi
0x140005d74  pop     rsi
0x140005d75  pop     rbp
0x140005d76  pop     rbx
0x140005d77  retn
```
