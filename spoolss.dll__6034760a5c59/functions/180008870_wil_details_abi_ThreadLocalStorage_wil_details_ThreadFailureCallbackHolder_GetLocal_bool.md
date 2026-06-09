# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008870`
- end: `0x1800088c6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008258`

## callees

- `0x180008870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000887d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000887d`

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
0x180008870  push    rbx
0x180008872  sub     rsp, 20h
0x180008876  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000887d  call    cs:__imp_GetCurrentThreadId
0x180008883  mov     r8d, eax
0x180008886  mov     r9d, eax
0x180008889  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008893  shr     r8, 2
0x180008897  mul     r8
0x18000889a  shr     rdx, 3
0x18000889e  lea     rcx, [rdx+rdx*4]
0x1800088a2  add     rcx, rcx
0x1800088a5  sub     r8, rcx
0x1800088a8  mov     rax, [rbx+r8*8]
0x1800088ac  test    rax, rax
0x1800088af  jz      short loc_1800088C0
0x1800088b1  cmp     [rax], r9d
0x1800088b4  jz      short loc_1800088BC
0x1800088b6  mov     rax, [rax+8]
0x1800088ba  jmp     short loc_1800088AC
0x1800088bc  add     rax, 10h
0x1800088c0  add     rsp, 20h
0x1800088c4  pop     rbx
0x1800088c5  retn
```
