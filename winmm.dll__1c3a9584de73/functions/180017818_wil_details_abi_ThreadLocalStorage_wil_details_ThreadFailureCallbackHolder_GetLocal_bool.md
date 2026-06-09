# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180017818`
- end: `0x18001786e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800172fc`

## callees

- `0x180017818`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017825`

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
0x180017818  push    rbx
0x18001781a  sub     rsp, 20h
0x18001781e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180017825  call    cs:__imp_GetCurrentThreadId
0x18001782b  mov     r9d, eax
0x18001782e  mov     r8d, eax
0x180017831  shr     r8, 2
0x180017835  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001783f  mul     r8
0x180017842  shr     rdx, 3
0x180017846  lea     rcx, [rdx+rdx*4]
0x18001784a  add     rcx, rcx
0x18001784d  sub     r8, rcx
0x180017850  mov     rax, [rbx+r8*8]
0x180017854  test    rax, rax
0x180017857  jz      short loc_180017868
0x180017859  cmp     [rax], r9d
0x18001785c  jz      short loc_180017864
0x18001785e  mov     rax, [rax+8]
0x180017862  jmp     short loc_180017854
0x180017864  add     rax, 10h
0x180017868  add     rsp, 20h
0x18001786c  pop     rbx
0x18001786d  retn
```
