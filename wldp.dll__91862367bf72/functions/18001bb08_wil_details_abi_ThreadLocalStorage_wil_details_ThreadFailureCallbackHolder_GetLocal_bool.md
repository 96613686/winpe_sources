# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001bb08`
- end: `0x18001bb5e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c264`

## callees

- `0x18001bb08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb15`

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
0x18001bb08  push    rbx
0x18001bb0a  sub     rsp, 20h
0x18001bb0e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bb15  call    cs:__imp_GetCurrentThreadId
0x18001bb1b  mov     r9d, eax
0x18001bb1e  mov     r8d, eax
0x18001bb21  shr     r8, 2
0x18001bb25  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001bb2f  mul     r8
0x18001bb32  shr     rdx, 3
0x18001bb36  lea     rcx, [rdx+rdx*4]
0x18001bb3a  add     rcx, rcx
0x18001bb3d  sub     r8, rcx
0x18001bb40  mov     rax, [rbx+r8*8]
0x18001bb44  test    rax, rax
0x18001bb47  jz      short loc_18001BB58
0x18001bb49  cmp     [rax], r9d
0x18001bb4c  jz      short loc_18001BB54
0x18001bb4e  mov     rax, [rax+8]
0x18001bb52  jmp     short loc_18001BB44
0x18001bb54  add     rax, 10h
0x18001bb58  add     rsp, 20h
0x18001bb5c  pop     rbx
0x18001bb5d  retn
```
