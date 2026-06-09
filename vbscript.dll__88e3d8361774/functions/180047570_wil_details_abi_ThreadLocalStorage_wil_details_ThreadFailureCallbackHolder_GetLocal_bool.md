# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180047570`
- end: `0x1800475c6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004713c`

## callees

- `0x180047570`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004757d`
- `KERNEL32!GetCurrentThreadId` at `0x18004757d`

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
0x180047570  push    rbx
0x180047572  sub     rsp, 20h
0x180047576  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004757d  call    cs:__imp_GetCurrentThreadId
0x180047583  mov     r8d, eax
0x180047586  mov     r9d, eax
0x180047589  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180047593  shr     r8, 2
0x180047597  mul     r8
0x18004759a  shr     rdx, 3
0x18004759e  lea     rcx, [rdx+rdx*4]
0x1800475a2  add     rcx, rcx
0x1800475a5  sub     r8, rcx
0x1800475a8  mov     rax, [rbx+r8*8]
0x1800475ac  test    rax, rax
0x1800475af  jz      short loc_1800475C0
0x1800475b1  cmp     [rax], r9d
0x1800475b4  jz      short loc_1800475BC
0x1800475b6  mov     rax, [rax+8]
0x1800475ba  jmp     short loc_1800475AC
0x1800475bc  add     rax, 10h
0x1800475c0  add     rsp, 20h
0x1800475c4  pop     rbx
0x1800475c5  retn
```
