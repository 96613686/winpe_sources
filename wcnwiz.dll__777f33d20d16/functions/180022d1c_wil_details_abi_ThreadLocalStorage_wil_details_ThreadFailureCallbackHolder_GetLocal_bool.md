# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180022d1c`
- end: `0x180022d72`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022844`

## callees

- `0x180022d1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022d29`

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
0x180022d1c  push    rbx
0x180022d1e  sub     rsp, 20h
0x180022d22  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180022d29  call    cs:__imp_GetCurrentThreadId
0x180022d2f  mov     r8d, eax
0x180022d32  mov     r9d, eax
0x180022d35  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180022d3f  shr     r8, 2
0x180022d43  mul     r8
0x180022d46  shr     rdx, 3
0x180022d4a  lea     rcx, [rdx+rdx*4]
0x180022d4e  add     rcx, rcx
0x180022d51  sub     r8, rcx
0x180022d54  mov     rax, [rbx+r8*8]
0x180022d58  test    rax, rax
0x180022d5b  jz      short loc_180022D6C
0x180022d5d  cmp     [rax], r9d
0x180022d60  jz      short loc_180022D68
0x180022d62  mov     rax, [rax+8]
0x180022d66  jmp     short loc_180022D58
0x180022d68  add     rax, 10h
0x180022d6c  add     rsp, 20h
0x180022d70  pop     rbx
0x180022d71  retn
```
