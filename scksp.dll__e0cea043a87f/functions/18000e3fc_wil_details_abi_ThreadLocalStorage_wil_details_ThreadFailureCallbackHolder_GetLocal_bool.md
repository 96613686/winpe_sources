# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000e3fc`
- end: `0x18000e454`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dcc8`

## callees

- `0x18000e3fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e409`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e409`

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
0x18000e3fc  push    rbx
0x18000e3fe  sub     rsp, 20h
0x18000e402  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e409  call    cs:__imp_GetCurrentThreadId
0x18000e40f  mov     r9d, eax
0x18000e412  mov     r8d, eax
0x18000e415  shr     r8, 2
0x18000e419  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000e423  mul     r8
0x18000e426  shr     rdx, 3
0x18000e42a  lea     rcx, [rdx+rdx*4]
0x18000e42e  add     rcx, rcx
0x18000e431  sub     r8, rcx
0x18000e434  mov     rax, [rbx+r8*8]
0x18000e438  jmp     short loc_18000E443
0x18000e43a  cmp     [rax], r9d
0x18000e43d  jz      short loc_18000E44E
0x18000e43f  mov     rax, [rax+8]
0x18000e443  test    rax, rax
0x18000e446  jnz     short loc_18000E43A
0x18000e448  add     rsp, 20h
0x18000e44c  pop     rbx
0x18000e44d  retn
0x18000e44e  add     rax, 10h
0x18000e452  jmp     short loc_18000E448
```
