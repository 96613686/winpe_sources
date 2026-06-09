# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008f60`
- end: `0x180008fb6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b28`

## callees

- `0x180008f60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f6d`

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
0x180008f60  push    rbx
0x180008f62  sub     rsp, 20h
0x180008f66  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008f6d  call    cs:__imp_GetCurrentThreadId
0x180008f73  mov     r8d, eax
0x180008f76  mov     r9d, eax
0x180008f79  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008f83  shr     r8, 2
0x180008f87  mul     r8
0x180008f8a  shr     rdx, 3
0x180008f8e  lea     rcx, [rdx+rdx*4]
0x180008f92  add     rcx, rcx
0x180008f95  sub     r8, rcx
0x180008f98  mov     rax, [rbx+r8*8]
0x180008f9c  test    rax, rax
0x180008f9f  jz      short loc_180008FB0
0x180008fa1  cmp     [rax], r9d
0x180008fa4  jz      short loc_180008FAC
0x180008fa6  mov     rax, [rax+8]
0x180008faa  jmp     short loc_180008F9C
0x180008fac  add     rax, 10h
0x180008fb0  add     rsp, 20h
0x180008fb4  pop     rbx
0x180008fb5  retn
```
