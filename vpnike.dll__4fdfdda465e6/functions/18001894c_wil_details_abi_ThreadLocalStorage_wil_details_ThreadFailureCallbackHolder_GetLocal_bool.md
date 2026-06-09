# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001894c`
- end: `0x1800189a4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018334`

## callees

- `0x18001894c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018959`

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
0x18001894c  push    rbx
0x18001894e  sub     rsp, 20h
0x180018952  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018959  call    cs:__imp_GetCurrentThreadId
0x18001895f  mov     r8d, eax
0x180018962  mov     r9d, eax
0x180018965  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001896f  shr     r8, 2
0x180018973  mul     r8
0x180018976  shr     rdx, 3
0x18001897a  lea     rcx, [rdx+rdx*4]
0x18001897e  add     rcx, rcx
0x180018981  sub     r8, rcx
0x180018984  mov     rax, [rbx+r8*8]
0x180018988  jmp     short loc_180018993
0x18001898a  cmp     [rax], r9d
0x18001898d  jz      short loc_18001899E
0x18001898f  mov     rax, [rax+8]
0x180018993  test    rax, rax
0x180018996  jnz     short loc_18001898A
0x180018998  add     rsp, 20h
0x18001899c  pop     rbx
0x18001899d  retn
0x18001899e  add     rax, 10h
0x1800189a2  jmp     short loc_180018998
```
