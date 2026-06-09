# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000417c`
- end: `0x1800041d2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ca8`

## callees

- `0x18000417c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004189`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(v0 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000417c  push    rbx
0x18000417e  sub     rsp, 20h
0x180004182  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004189  call    cs:__imp_GetCurrentThreadId
0x18000418f  mov     r8d, eax
0x180004192  mov     r9d, eax
0x180004195  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000419f  shr     r8, 2
0x1800041a3  mul     r8
0x1800041a6  shr     rdx, 3
0x1800041aa  lea     rcx, [rdx+rdx*4]
0x1800041ae  add     rcx, rcx
0x1800041b1  sub     r8, rcx
0x1800041b4  mov     rax, [rbx+r8*8]
0x1800041b8  test    rax, rax
0x1800041bb  jz      short loc_1800041CC
0x1800041bd  cmp     [rax], r9d
0x1800041c0  jz      short loc_1800041C8
0x1800041c2  mov     rax, [rax+8]
0x1800041c6  jmp     short loc_1800041B8
0x1800041c8  add     rax, 10h
0x1800041cc  add     rsp, 20h
0x1800041d0  pop     rbx
0x1800041d1  retn
```
