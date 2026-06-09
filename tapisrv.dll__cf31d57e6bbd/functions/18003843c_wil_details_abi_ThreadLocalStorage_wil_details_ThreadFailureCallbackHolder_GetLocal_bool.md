# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18003843c`
- end: `0x180038494`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037f64`

## callees

- `0x18003843c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180038449`
- `KERNEL32!GetCurrentThreadId` at `0x180038449`

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
0x18003843c  push    rbx
0x18003843e  sub     rsp, 20h
0x180038442  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180038449  call    cs:__imp_GetCurrentThreadId
0x18003844f  mov     r8d, eax
0x180038452  mov     r9d, eax
0x180038455  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003845f  shr     r8, 2
0x180038463  mul     r8
0x180038466  shr     rdx, 3
0x18003846a  lea     rcx, [rdx+rdx*4]
0x18003846e  add     rcx, rcx
0x180038471  sub     r8, rcx
0x180038474  mov     rax, [rbx+r8*8]
0x180038478  jmp     short loc_180038483
0x18003847a  cmp     [rax], r9d
0x18003847d  jz      short loc_18003848E
0x18003847f  mov     rax, [rax+8]
0x180038483  test    rax, rax
0x180038486  jnz     short loc_18003847A
0x180038488  add     rsp, 20h
0x18003848c  pop     rbx
0x18003848d  retn
0x18003848e  add     rax, 10h
0x180038492  jmp     short loc_180038488
```
