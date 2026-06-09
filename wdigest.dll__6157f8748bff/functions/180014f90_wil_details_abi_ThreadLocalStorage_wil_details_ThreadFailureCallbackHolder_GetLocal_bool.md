# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180014f90`
- end: `0x180014fe6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b58`

## callees

- `0x180014f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f9d`

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
0x180014f90  push    rbx
0x180014f92  sub     rsp, 20h
0x180014f96  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014f9d  call    cs:__imp_GetCurrentThreadId
0x180014fa3  mov     r8d, eax
0x180014fa6  mov     r9d, eax
0x180014fa9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014fb3  shr     r8, 2
0x180014fb7  mul     r8
0x180014fba  shr     rdx, 3
0x180014fbe  lea     rcx, [rdx+rdx*4]
0x180014fc2  add     rcx, rcx
0x180014fc5  sub     r8, rcx
0x180014fc8  mov     rax, [rbx+r8*8]
0x180014fcc  test    rax, rax
0x180014fcf  jz      short loc_180014FE0
0x180014fd1  cmp     [rax], r9d
0x180014fd4  jz      short loc_180014FDC
0x180014fd6  mov     rax, [rax+8]
0x180014fda  jmp     short loc_180014FCC
0x180014fdc  add     rax, 10h
0x180014fe0  add     rsp, 20h
0x180014fe4  pop     rbx
0x180014fe5  retn
```
