# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180015794`
- end: `0x1800157ec`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b0c`

## callees

- `0x180015794`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157a1`

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
0x180015794  push    rbx
0x180015796  sub     rsp, 20h
0x18001579a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800157a1  call    cs:__imp_GetCurrentThreadId
0x1800157a7  mov     r8d, eax
0x1800157aa  mov     r9d, eax
0x1800157ad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800157b7  shr     r8, 2
0x1800157bb  mul     r8
0x1800157be  shr     rdx, 3
0x1800157c2  lea     rcx, [rdx+rdx*4]
0x1800157c6  add     rcx, rcx
0x1800157c9  sub     r8, rcx
0x1800157cc  mov     rax, [rbx+r8*8]
0x1800157d0  test    rax, rax
0x1800157d3  jnz     short loc_1800157DB
0x1800157d5  add     rsp, 20h
0x1800157d9  pop     rbx
0x1800157da  retn
0x1800157db  cmp     [rax], r9d
0x1800157de  jz      short loc_1800157E6
0x1800157e0  mov     rax, [rax+8]
0x1800157e4  jmp     short loc_1800157D0
0x1800157e6  add     rax, 10h
0x1800157ea  jmp     short loc_1800157D5
```
