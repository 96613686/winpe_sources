# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002801c`
- end: `0x180028079`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027598`

## callees

- `0x18002801c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028029`

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
0x18002801c  push    rbx
0x18002801e  sub     rsp, 20h
0x180028022  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180028029  call    cs:__imp_GetCurrentThreadId
0x180028030  nop     dword ptr [rax+rax+00h]
0x180028035  mov     r8d, eax
0x180028038  mov     r9d, eax
0x18002803b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180028045  shr     r8, 2
0x180028049  mul     r8
0x18002804c  shr     rdx, 3
0x180028050  lea     rcx, [rdx+rdx*4]
0x180028054  add     rcx, rcx
0x180028057  sub     r8, rcx
0x18002805a  mov     rax, [rbx+r8*8]
0x18002805e  test    rax, rax
0x180028061  jz      short loc_180028072
0x180028063  cmp     [rax], r9d
0x180028066  jz      short loc_18002806E
0x180028068  mov     rax, [rax+8]
0x18002806c  jmp     short loc_18002805E
0x18002806e  add     rax, 10h
0x180028072  add     rsp, 20h
0x180028076  pop     rbx
0x180028077  retn
```
