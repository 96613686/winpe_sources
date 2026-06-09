# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000ce6c`
- end: `0x18000cec2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c99c`

## callees

- `0x18000ce6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce79`

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
0x18000ce6c  push    rbx
0x18000ce6e  sub     rsp, 20h
0x18000ce72  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ce79  call    cs:__imp_GetCurrentThreadId
0x18000ce7f  mov     r8d, eax
0x18000ce82  mov     r9d, eax
0x18000ce85  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ce8f  shr     r8, 2
0x18000ce93  mul     r8
0x18000ce96  shr     rdx, 3
0x18000ce9a  lea     rcx, [rdx+rdx*4]
0x18000ce9e  add     rcx, rcx
0x18000cea1  sub     r8, rcx
0x18000cea4  mov     rax, [rbx+r8*8]
0x18000cea8  test    rax, rax
0x18000ceab  jz      short loc_18000CEBC
0x18000cead  cmp     [rax], r9d
0x18000ceb0  jz      short loc_18000CEB8
0x18000ceb2  mov     rax, [rax+8]
0x18000ceb6  jmp     short loc_18000CEA8
0x18000ceb8  add     rax, 10h
0x18000cebc  add     rsp, 20h
0x18000cec0  pop     rbx
0x18000cec1  retn
```
