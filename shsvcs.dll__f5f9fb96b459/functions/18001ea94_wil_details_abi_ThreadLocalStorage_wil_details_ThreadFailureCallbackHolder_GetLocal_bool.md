# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001ea94`
- end: `0x18001eaec`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e5a4`

## callees

- `0x18001ea94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eaa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eaa1`

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
0x18001ea94  push    rbx
0x18001ea96  sub     rsp, 20h
0x18001ea9a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001eaa1  call    cs:__imp_GetCurrentThreadId
0x18001eaa7  mov     r8d, eax
0x18001eaaa  mov     r9d, eax
0x18001eaad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001eab7  shr     r8, 2
0x18001eabb  mul     r8
0x18001eabe  shr     rdx, 3
0x18001eac2  lea     rcx, [rdx+rdx*4]
0x18001eac6  add     rcx, rcx
0x18001eac9  sub     r8, rcx
0x18001eacc  mov     rax, [rbx+r8*8]
0x18001ead0  jmp     short loc_18001EADB
0x18001ead2  cmp     [rax], r9d
0x18001ead5  jz      short loc_18001EAE6
0x18001ead7  mov     rax, [rax+8]
0x18001eadb  test    rax, rax
0x18001eade  jnz     short loc_18001EAD2
0x18001eae0  add     rsp, 20h
0x18001eae4  pop     rbx
0x18001eae5  retn
0x18001eae6  add     rax, 10h
0x18001eaea  jmp     short loc_18001EAE0
```
