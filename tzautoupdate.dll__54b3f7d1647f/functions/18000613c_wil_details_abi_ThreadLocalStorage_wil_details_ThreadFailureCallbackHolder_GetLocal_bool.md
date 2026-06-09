# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000613c`
- end: `0x180006192`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a64`

## callees

- `0x18000613c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006149`

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
0x18000613c  push    rbx
0x18000613e  sub     rsp, 20h
0x180006142  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006149  call    cs:__imp_GetCurrentThreadId
0x18000614f  mov     r8d, eax
0x180006152  mov     r9d, eax
0x180006155  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000615f  shr     r8, 2
0x180006163  mul     r8
0x180006166  shr     rdx, 3
0x18000616a  lea     rcx, [rdx+rdx*4]
0x18000616e  add     rcx, rcx
0x180006171  sub     r8, rcx
0x180006174  mov     rax, [rbx+r8*8]
0x180006178  test    rax, rax
0x18000617b  jz      short loc_18000618C
0x18000617d  cmp     [rax], r9d
0x180006180  jz      short loc_180006188
0x180006182  mov     rax, [rax+8]
0x180006186  jmp     short loc_180006178
0x180006188  add     rax, 10h
0x18000618c  add     rsp, 20h
0x180006190  pop     rbx
0x180006191  retn
```
