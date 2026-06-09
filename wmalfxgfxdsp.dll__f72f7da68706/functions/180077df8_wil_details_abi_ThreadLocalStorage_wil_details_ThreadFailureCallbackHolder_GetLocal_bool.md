# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180077df8`
- end: `0x180077e4e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014ae8`

## callees

- `0x180077df8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077e05`

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
0x180077df8  push    rbx
0x180077dfa  sub     rsp, 20h
0x180077dfe  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180077e05  call    cs:__imp_GetCurrentThreadId
0x180077e0b  mov     r8d, eax
0x180077e0e  mov     r9d, eax
0x180077e11  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180077e1b  shr     r8, 2
0x180077e1f  mul     r8
0x180077e22  shr     rdx, 3
0x180077e26  lea     rcx, [rdx+rdx*4]
0x180077e2a  add     rcx, rcx
0x180077e2d  sub     r8, rcx
0x180077e30  mov     rax, [rbx+r8*8]
0x180077e34  test    rax, rax
0x180077e37  jz      short loc_180077E48
0x180077e39  cmp     [rax], r9d
0x180077e3c  jz      short loc_180077E44
0x180077e3e  mov     rax, [rax+8]
0x180077e42  jmp     short loc_180077E34
0x180077e44  add     rax, 10h
0x180077e48  add     rsp, 20h
0x180077e4c  pop     rbx
0x180077e4d  retn
```
