# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002541c`
- end: `0x180025472`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024f44`

## callees

- `0x18002541c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025429`
- `KERNEL32!GetCurrentThreadId` at `0x180025429`

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
0x18002541c  push    rbx
0x18002541e  sub     rsp, 20h
0x180025422  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180025429  call    cs:__imp_GetCurrentThreadId
0x18002542f  mov     r8d, eax
0x180025432  mov     r9d, eax
0x180025435  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002543f  shr     r8, 2
0x180025443  mul     r8
0x180025446  shr     rdx, 3
0x18002544a  lea     rcx, [rdx+rdx*4]
0x18002544e  add     rcx, rcx
0x180025451  sub     r8, rcx
0x180025454  mov     rax, [rbx+r8*8]
0x180025458  test    rax, rax
0x18002545b  jz      short loc_18002546C
0x18002545d  cmp     [rax], r9d
0x180025460  jz      short loc_180025468
0x180025462  mov     rax, [rax+8]
0x180025466  jmp     short loc_180025458
0x180025468  add     rax, 10h
0x18002546c  add     rsp, 20h
0x180025470  pop     rbx
0x180025471  retn
```
