# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d320`
- end: `0x18000d37d`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d124`

## callees

- `0x18000d320`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d32d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d32d`

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
0x18000d320  push    rbx
0x18000d322  sub     rsp, 20h
0x18000d326  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d32d  call    cs:__imp_GetCurrentThreadId
0x18000d334  nop     dword ptr [rax+rax+00h]
0x18000d339  mov     r8d, eax
0x18000d33c  mov     r9d, eax
0x18000d33f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d349  shr     r8, 2
0x18000d34d  mul     r8
0x18000d350  shr     rdx, 3
0x18000d354  lea     rcx, [rdx+rdx*4]
0x18000d358  add     rcx, rcx
0x18000d35b  sub     r8, rcx
0x18000d35e  mov     rax, [rbx+r8*8]
0x18000d362  test    rax, rax
0x18000d365  jz      short loc_18000D376
0x18000d367  cmp     [rax], r9d
0x18000d36a  jz      short loc_18000D372
0x18000d36c  mov     rax, [rax+8]
0x18000d370  jmp     short loc_18000D362
0x18000d372  add     rax, 10h
0x18000d376  add     rsp, 20h
0x18000d37a  pop     rbx
0x18000d37b  retn
```
