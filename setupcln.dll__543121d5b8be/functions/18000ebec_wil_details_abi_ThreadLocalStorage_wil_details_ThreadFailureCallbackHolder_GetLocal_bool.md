# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000ebec`
- end: `0x18000ec44`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e714`

## callees

- `0x18000ebec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebf9`

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
0x18000ebec  push    rbx
0x18000ebee  sub     rsp, 20h
0x18000ebf2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ebf9  call    cs:__imp_GetCurrentThreadId
0x18000ebff  mov     r8d, eax
0x18000ec02  mov     r9d, eax
0x18000ec05  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ec0f  shr     r8, 2
0x18000ec13  mul     r8
0x18000ec16  shr     rdx, 3
0x18000ec1a  lea     rcx, [rdx+rdx*4]
0x18000ec1e  add     rcx, rcx
0x18000ec21  sub     r8, rcx
0x18000ec24  mov     rax, [rbx+r8*8]
0x18000ec28  jmp     short loc_18000EC33
0x18000ec2a  cmp     [rax], r9d
0x18000ec2d  jz      short loc_18000EC3E
0x18000ec2f  mov     rax, [rax+8]
0x18000ec33  test    rax, rax
0x18000ec36  jnz     short loc_18000EC2A
0x18000ec38  add     rsp, 20h
0x18000ec3c  pop     rbx
0x18000ec3d  retn
0x18000ec3e  add     rax, 10h
0x18000ec42  jmp     short loc_18000EC38
```
