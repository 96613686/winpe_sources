# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800080bc`
- end: `0x180008112`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007be8`

## callees

- `0x1800080bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080c9`

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
0x1800080bc  push    rbx
0x1800080be  sub     rsp, 20h
0x1800080c2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800080c9  call    cs:__imp_GetCurrentThreadId
0x1800080cf  mov     r8d, eax
0x1800080d2  mov     r9d, eax
0x1800080d5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800080df  shr     r8, 2
0x1800080e3  mul     r8
0x1800080e6  shr     rdx, 3
0x1800080ea  lea     rcx, [rdx+rdx*4]
0x1800080ee  add     rcx, rcx
0x1800080f1  sub     r8, rcx
0x1800080f4  mov     rax, [rbx+r8*8]
0x1800080f8  test    rax, rax
0x1800080fb  jz      short loc_18000810C
0x1800080fd  cmp     [rax], r9d
0x180008100  jz      short loc_180008108
0x180008102  mov     rax, [rax+8]
0x180008106  jmp     short loc_1800080F8
0x180008108  add     rax, 10h
0x18000810c  add     rsp, 20h
0x180008110  pop     rbx
0x180008111  retn
```
