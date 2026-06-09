# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001c694`
- end: `0x18001c6ec`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ba18`

## callees

- `0x18001c694`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c6a1`
- `KERNEL32!GetCurrentThreadId` at `0x18001c6a1`

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
0x18001c694  push    rbx
0x18001c696  sub     rsp, 20h
0x18001c69a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001c6a1  call    cs:__imp_GetCurrentThreadId
0x18001c6a7  mov     r8d, eax
0x18001c6aa  mov     r9d, eax
0x18001c6ad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001c6b7  shr     r8, 2
0x18001c6bb  mul     r8
0x18001c6be  shr     rdx, 3
0x18001c6c2  lea     rcx, [rdx+rdx*4]
0x18001c6c6  add     rcx, rcx
0x18001c6c9  sub     r8, rcx
0x18001c6cc  mov     rax, [rbx+r8*8]
0x18001c6d0  jmp     short loc_18001C6DB
0x18001c6d2  cmp     [rax], r9d
0x18001c6d5  jz      short loc_18001C6E6
0x18001c6d7  mov     rax, [rax+8]
0x18001c6db  test    rax, rax
0x18001c6de  jnz     short loc_18001C6D2
0x18001c6e0  add     rsp, 20h
0x18001c6e4  pop     rbx
0x18001c6e5  retn
0x18001c6e6  add     rax, 10h
0x18001c6ea  jmp     short loc_18001C6E0
```
