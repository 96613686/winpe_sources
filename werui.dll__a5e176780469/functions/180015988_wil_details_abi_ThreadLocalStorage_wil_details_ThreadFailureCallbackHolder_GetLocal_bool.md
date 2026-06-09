# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180015988`
- end: `0x1800159de`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800157b8`

## callees

- `0x180015988`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015995`
- `KERNEL32!GetCurrentThreadId` at `0x180015995`

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
0x180015988  push    rbx
0x18001598a  sub     rsp, 20h
0x18001598e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180015995  call    cs:__imp_GetCurrentThreadId
0x18001599b  mov     r8d, eax
0x18001599e  mov     r9d, eax
0x1800159a1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800159ab  shr     r8, 2
0x1800159af  mul     r8
0x1800159b2  shr     rdx, 3
0x1800159b6  lea     rcx, [rdx+rdx*4]
0x1800159ba  add     rcx, rcx
0x1800159bd  sub     r8, rcx
0x1800159c0  mov     rax, [rbx+r8*8]
0x1800159c4  test    rax, rax
0x1800159c7  jz      short loc_1800159D8
0x1800159c9  cmp     [rax], r9d
0x1800159cc  jz      short loc_1800159D4
0x1800159ce  mov     rax, [rax+8]
0x1800159d2  jmp     short loc_1800159C4
0x1800159d4  add     rax, 10h
0x1800159d8  add     rsp, 20h
0x1800159dc  pop     rbx
0x1800159dd  retn
```
