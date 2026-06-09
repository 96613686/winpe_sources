# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008d5c`
- end: `0x180008db4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008884`

## callees

- `0x180008d5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d69`

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
0x180008d5c  push    rbx
0x180008d5e  sub     rsp, 20h
0x180008d62  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008d69  call    cs:__imp_GetCurrentThreadId
0x180008d6f  mov     r8d, eax
0x180008d72  mov     r9d, eax
0x180008d75  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008d7f  shr     r8, 2
0x180008d83  mul     r8
0x180008d86  shr     rdx, 3
0x180008d8a  lea     rcx, [rdx+rdx*4]
0x180008d8e  add     rcx, rcx
0x180008d91  sub     r8, rcx
0x180008d94  mov     rax, [rbx+r8*8]
0x180008d98  jmp     short loc_180008DA3
0x180008d9a  cmp     [rax], r9d
0x180008d9d  jz      short loc_180008DAE
0x180008d9f  mov     rax, [rax+8]
0x180008da3  test    rax, rax
0x180008da6  jnz     short loc_180008D9A
0x180008da8  add     rsp, 20h
0x180008dac  pop     rbx
0x180008dad  retn
0x180008dae  add     rax, 10h
0x180008db2  jmp     short loc_180008DA8
```
