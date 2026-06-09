# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001e7b0`
- end: `0x18001e806`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e37c`

## callees

- `0x18001e7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e7bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e7bd`

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
0x18001e7b0  push    rbx
0x18001e7b2  sub     rsp, 20h
0x18001e7b6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001e7bd  call    cs:__imp_GetCurrentThreadId
0x18001e7c3  mov     r8d, eax
0x18001e7c6  mov     r9d, eax
0x18001e7c9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001e7d3  shr     r8, 2
0x18001e7d7  mul     r8
0x18001e7da  shr     rdx, 3
0x18001e7de  lea     rcx, [rdx+rdx*4]
0x18001e7e2  add     rcx, rcx
0x18001e7e5  sub     r8, rcx
0x18001e7e8  mov     rax, [rbx+r8*8]
0x18001e7ec  test    rax, rax
0x18001e7ef  jz      short loc_18001E800
0x18001e7f1  cmp     [rax], r9d
0x18001e7f4  jz      short loc_18001E7FC
0x18001e7f6  mov     rax, [rax+8]
0x18001e7fa  jmp     short loc_18001E7EC
0x18001e7fc  add     rax, 10h
0x18001e800  add     rsp, 20h
0x18001e804  pop     rbx
0x18001e805  retn
```
