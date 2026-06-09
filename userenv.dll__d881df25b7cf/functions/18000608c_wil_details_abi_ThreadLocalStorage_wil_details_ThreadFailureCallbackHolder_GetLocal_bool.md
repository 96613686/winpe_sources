# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000608c`
- end: `0x180006131`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006010`
- `0x18000a574`

## callees

- `0x18000608c`
- `0x180006668`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000609f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000609f`

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
0x18000608c  push    rbx
0x18000608e  push    rbp
0x18000608f  push    rsi
0x180006090  push    rdi
0x180006091  sub     rsp, 28h
0x180006095  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000609c  mov     bpl, dl
0x18000609f  call    cs:__imp_GetCurrentThreadId
0x1800060a6  nop     dword ptr [rax+rax+00h]
0x1800060ab  mov     ebx, eax
0x1800060ad  mov     esi, eax
0x1800060af  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800060b9  shr     rbx, 2
0x1800060bd  mul     rbx
0x1800060c0  shr     rdx, 3
0x1800060c4  lea     rcx, [rdx+rdx*4]
0x1800060c8  add     rcx, rcx
0x1800060cb  sub     rbx, rcx
0x1800060ce  mov     rax, [rdi+rbx*8]
0x1800060d2  test    rax, rax
0x1800060d5  jz      short loc_1800060EF
0x1800060d7  cmp     [rax], esi
0x1800060d9  jz      short loc_1800060E1
0x1800060db  mov     rax, [rax+8]
0x1800060df  jmp     short loc_1800060D2
0x1800060e1  add     rax, 10h
0x1800060e5  add     rsp, 28h
0x1800060e9  pop     rdi
0x1800060ea  pop     rsi
0x1800060eb  pop     rbp
0x1800060ec  pop     rbx
0x1800060ed  retn
0x1800060ef  test    bpl, bpl
0x1800060f2  jz      short loc_18000612D
0x1800060f4  mov     edx, 18h; dwBytes
0x1800060f9  xor     ecx, ecx; dwFlags
0x1800060fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006100  mov     rcx, rax
0x180006103  test    rax, rax
0x180006106  jz      short loc_18000612D
0x180006108  mov     [rax], esi
0x18000610a  xor     eax, eax
0x18000610c  mov     [rcx+4], eax
0x18000610f  mov     [rcx+8], rax
0x180006113  mov     [rcx+10h], rax
0x180006117  mov     rax, [rdi+rbx*8]
0x18000611b  mov     [rcx+8], rax
0x18000611f  lock cmpxchg [rdi+rbx*8], rcx
0x180006125  jnz     short loc_180006117
0x180006127  lea     rax, [rcx+10h]
0x18000612b  jmp     short loc_1800060E5
0x18000612d  xor     eax, eax
0x18000612f  jmp     short loc_1800060E5
```
