# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001ecfc`
- end: `0x18001ed52`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e788`

## callees

- `0x18001ecfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed09`

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
0x18001ecfc  push    rbx
0x18001ecfe  sub     rsp, 20h
0x18001ed02  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001ed09  call    cs:__imp_GetCurrentThreadId
0x18001ed0f  mov     r9d, eax
0x18001ed12  mov     r8d, eax
0x18001ed15  shr     r8, 2
0x18001ed19  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001ed23  mul     r8
0x18001ed26  shr     rdx, 3
0x18001ed2a  lea     rcx, [rdx+rdx*4]
0x18001ed2e  add     rcx, rcx
0x18001ed31  sub     r8, rcx
0x18001ed34  mov     rax, [rbx+r8*8]
0x18001ed38  test    rax, rax
0x18001ed3b  jz      short loc_18001ED4C
0x18001ed3d  cmp     [rax], r9d
0x18001ed40  jz      short loc_18001ED48
0x18001ed42  mov     rax, [rax+8]
0x18001ed46  jmp     short loc_18001ED38
0x18001ed48  add     rax, 10h
0x18001ed4c  add     rsp, 20h
0x18001ed50  pop     rbx
0x18001ed51  retn
```
