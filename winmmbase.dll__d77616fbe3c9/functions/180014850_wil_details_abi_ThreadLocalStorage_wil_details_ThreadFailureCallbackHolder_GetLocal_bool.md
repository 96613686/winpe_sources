# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180014850`
- end: `0x1800148a8`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800142ec`

## callees

- `0x180014850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001485d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001485d`

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
0x180014850  push    rbx
0x180014852  sub     rsp, 20h
0x180014856  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001485d  call    cs:__imp_GetCurrentThreadId
0x180014863  mov     r8d, eax
0x180014866  mov     r9d, eax
0x180014869  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014873  shr     r8, 2
0x180014877  mul     r8
0x18001487a  shr     rdx, 3
0x18001487e  lea     rcx, [rdx+rdx*4]
0x180014882  add     rcx, rcx
0x180014885  sub     r8, rcx
0x180014888  mov     rax, [rbx+r8*8]
0x18001488c  jmp     short loc_180014897
0x18001488e  cmp     [rax], r9d
0x180014891  jz      short loc_1800148A2
0x180014893  mov     rax, [rax+8]
0x180014897  test    rax, rax
0x18001489a  jnz     short loc_18001488E
0x18001489c  add     rsp, 20h
0x1800148a0  pop     rbx
0x1800148a1  retn
0x1800148a2  add     rax, 10h
0x1800148a6  jmp     short loc_18001489C
```
