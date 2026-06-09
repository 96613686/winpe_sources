# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18003dbdc`
- end: `0x18003dc34`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003d708`

## callees

- `0x18003dbdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dbe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dbe9`

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
0x18003dbdc  push    rbx
0x18003dbde  sub     rsp, 20h
0x18003dbe2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003dbe9  call    cs:__imp_GetCurrentThreadId
0x18003dbef  mov     r8d, eax
0x18003dbf2  mov     r9d, eax
0x18003dbf5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003dbff  shr     r8, 2
0x18003dc03  mul     r8
0x18003dc06  shr     rdx, 3
0x18003dc0a  lea     rcx, [rdx+rdx*4]
0x18003dc0e  add     rcx, rcx
0x18003dc11  sub     r8, rcx
0x18003dc14  mov     rax, [rbx+r8*8]
0x18003dc18  jmp     short loc_18003DC23
0x18003dc1a  cmp     [rax], r9d
0x18003dc1d  jz      short loc_18003DC2E
0x18003dc1f  mov     rax, [rax+8]
0x18003dc23  test    rax, rax
0x18003dc26  jnz     short loc_18003DC1A
0x18003dc28  add     rsp, 20h
0x18003dc2c  pop     rbx
0x18003dc2d  retn
0x18003dc2e  add     rax, 10h
0x18003dc32  jmp     short loc_18003DC28
```
