# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800265e4`
- end: `0x18002663a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025ba4`

## callees

- `0x1800265e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800265f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800265f1`

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
0x1800265e4  push    rbx
0x1800265e6  sub     rsp, 20h
0x1800265ea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800265f1  call    cs:__imp_GetCurrentThreadId
0x1800265f7  mov     r8d, eax
0x1800265fa  mov     r9d, eax
0x1800265fd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180026607  shr     r8, 2
0x18002660b  mul     r8
0x18002660e  shr     rdx, 3
0x180026612  lea     rcx, [rdx+rdx*4]
0x180026616  add     rcx, rcx
0x180026619  sub     r8, rcx
0x18002661c  mov     rax, [rbx+r8*8]
0x180026620  test    rax, rax
0x180026623  jz      short loc_180026634
0x180026625  cmp     [rax], r9d
0x180026628  jz      short loc_180026630
0x18002662a  mov     rax, [rax+8]
0x18002662e  jmp     short loc_180026620
0x180026630  add     rax, 10h
0x180026634  add     rsp, 20h
0x180026638  pop     rbx
0x180026639  retn
```
