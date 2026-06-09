# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800063ec`
- end: `0x18000648a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005f14`
- `0x1800468f0`

## callees

- `0x1800063ec`
- `0x180007674`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063ff`

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
0x1800063ec  push    rbx
0x1800063ee  push    rbp
0x1800063ef  push    rsi
0x1800063f0  push    rdi
0x1800063f1  sub     rsp, 28h
0x1800063f5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800063fc  mov     bpl, dl
0x1800063ff  call    cs:__imp_GetCurrentThreadId
0x180006405  mov     ebx, eax
0x180006407  mov     esi, eax
0x180006409  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006413  shr     rbx, 2
0x180006417  mul     rbx
0x18000641a  shr     rdx, 3
0x18000641e  lea     rcx, [rdx+rdx*4]
0x180006422  add     rcx, rcx
0x180006425  sub     rbx, rcx
0x180006428  mov     rax, [rdi+rbx*8]
0x18000642c  test    rax, rax
0x18000642f  jz      short loc_180006441
0x180006431  cmp     [rax], esi
0x180006433  jz      short loc_18000643B
0x180006435  mov     rax, [rax+8]
0x180006439  jmp     short loc_18000642C
0x18000643b  add     rax, 10h
0x18000643f  jmp     short loc_180006481
0x180006441  test    bpl, bpl
0x180006444  jz      short loc_18000647F
0x180006446  mov     edx, 18h; dwBytes
0x18000644b  xor     ecx, ecx; dwFlags
0x18000644d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006452  mov     rcx, rax
0x180006455  test    rax, rax
0x180006458  jz      short loc_18000647F
0x18000645a  mov     [rax], esi
0x18000645c  xor     eax, eax
0x18000645e  mov     [rcx+4], eax
0x180006461  mov     [rcx+8], rax
0x180006465  mov     [rcx+10h], rax
0x180006469  mov     rax, [rdi+rbx*8]
0x18000646d  mov     [rcx+8], rax
0x180006471  lock cmpxchg [rdi+rbx*8], rcx
0x180006477  jnz     short loc_180006469
0x180006479  lea     rax, [rcx+10h]
0x18000647d  jmp     short loc_180006481
0x18000647f  xor     eax, eax
0x180006481  add     rsp, 28h
0x180006485  pop     rdi
0x180006486  pop     rsi
0x180006487  pop     rbp
0x180006488  pop     rbx
0x180006489  retn
```
