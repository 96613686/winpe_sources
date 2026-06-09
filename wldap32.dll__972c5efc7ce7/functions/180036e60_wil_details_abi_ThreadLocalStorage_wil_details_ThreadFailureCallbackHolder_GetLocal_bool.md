# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180036e60`
- end: `0x180036ebd`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036a08`

## callees

- `0x180036e60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036e6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036e6d`

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
0x180036e60  push    rbx
0x180036e62  sub     rsp, 20h
0x180036e66  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180036e6d  call    cs:__imp_GetCurrentThreadId
0x180036e74  nop     dword ptr [rax+rax+00h]
0x180036e79  mov     r8d, eax
0x180036e7c  mov     r9d, eax
0x180036e7f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180036e89  shr     r8, 2
0x180036e8d  mul     r8
0x180036e90  shr     rdx, 3
0x180036e94  lea     rcx, [rdx+rdx*4]
0x180036e98  add     rcx, rcx
0x180036e9b  sub     r8, rcx
0x180036e9e  mov     rax, [rbx+r8*8]
0x180036ea2  test    rax, rax
0x180036ea5  jz      short loc_180036EB6
0x180036ea7  cmp     [rax], r9d
0x180036eaa  jz      short loc_180036EB2
0x180036eac  mov     rax, [rax+8]
0x180036eb0  jmp     short loc_180036EA2
0x180036eb2  add     rax, 10h
0x180036eb6  add     rsp, 20h
0x180036eba  pop     rbx
0x180036ebb  retn
```
