# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180019984`
- end: `0x1800199e3`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019484`

## callees

- `0x180019984`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019991`

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
0x180019984  push    rbx
0x180019986  sub     rsp, 20h
0x18001998a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180019991  call    cs:__imp_GetCurrentThreadId
0x180019998  nop     dword ptr [rax+rax+00h]
0x18001999d  mov     r8d, eax
0x1800199a0  mov     r9d, eax
0x1800199a3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800199ad  shr     r8, 2
0x1800199b1  mul     r8
0x1800199b4  shr     rdx, 3
0x1800199b8  lea     rcx, [rdx+rdx*4]
0x1800199bc  add     rcx, rcx
0x1800199bf  sub     r8, rcx
0x1800199c2  mov     rax, [rbx+r8*8]
0x1800199c6  jmp     short loc_1800199D1
0x1800199c8  cmp     [rax], r9d
0x1800199cb  jz      short loc_1800199DD
0x1800199cd  mov     rax, [rax+8]
0x1800199d1  test    rax, rax
0x1800199d4  jnz     short loc_1800199C8
0x1800199d6  add     rsp, 20h
0x1800199da  pop     rbx
0x1800199db  retn
0x1800199dd  add     rax, 10h
0x1800199e1  jmp     short loc_1800199D6
```
