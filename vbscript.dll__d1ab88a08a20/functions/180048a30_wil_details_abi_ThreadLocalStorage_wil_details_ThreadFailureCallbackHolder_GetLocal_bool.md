# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180048a30`
- end: `0x180048a8d`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800485d4`

## callees

- `0x180048a30`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180048a3d`
- `KERNEL32!GetCurrentThreadId` at `0x180048a3d`

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
0x180048a30  push    rbx
0x180048a32  sub     rsp, 20h
0x180048a36  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180048a3d  call    cs:__imp_GetCurrentThreadId
0x180048a44  nop     dword ptr [rax+rax+00h]
0x180048a49  mov     r8d, eax
0x180048a4c  mov     r9d, eax
0x180048a4f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180048a59  shr     r8, 2
0x180048a5d  mul     r8
0x180048a60  shr     rdx, 3
0x180048a64  lea     rcx, [rdx+rdx*4]
0x180048a68  add     rcx, rcx
0x180048a6b  sub     r8, rcx
0x180048a6e  mov     rax, [rbx+r8*8]
0x180048a72  test    rax, rax
0x180048a75  jz      short loc_180048A86
0x180048a77  cmp     [rax], r9d
0x180048a7a  jz      short loc_180048A82
0x180048a7c  mov     rax, [rax+8]
0x180048a80  jmp     short loc_180048A72
0x180048a82  add     rax, 10h
0x180048a86  add     rsp, 20h
0x180048a8a  pop     rbx
0x180048a8b  retn
```
