# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008174`
- end: `0x1800081d1`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c74`

## callees

- `0x180008174`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008181`

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
0x180008174  push    rbx
0x180008176  sub     rsp, 20h
0x18000817a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008181  call    cs:__imp_GetCurrentThreadId
0x180008188  nop     dword ptr [rax+rax+00h]
0x18000818d  mov     r8d, eax
0x180008190  mov     r9d, eax
0x180008193  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000819d  shr     r8, 2
0x1800081a1  mul     r8
0x1800081a4  shr     rdx, 3
0x1800081a8  lea     rcx, [rdx+rdx*4]
0x1800081ac  add     rcx, rcx
0x1800081af  sub     r8, rcx
0x1800081b2  mov     rax, [rbx+r8*8]
0x1800081b6  test    rax, rax
0x1800081b9  jz      short loc_1800081CA
0x1800081bb  cmp     [rax], r9d
0x1800081be  jz      short loc_1800081C6
0x1800081c0  mov     rax, [rax+8]
0x1800081c4  jmp     short loc_1800081B6
0x1800081c6  add     rax, 10h
0x1800081ca  add     rsp, 20h
0x1800081ce  pop     rbx
0x1800081cf  retn
```
