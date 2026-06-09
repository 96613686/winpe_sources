# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000757c`
- end: `0x1800075d4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070a4`

## callees

- `0x18000757c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007589`

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
0x18000757c  push    rbx
0x18000757e  sub     rsp, 20h
0x180007582  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007589  call    cs:__imp_GetCurrentThreadId
0x18000758f  mov     r8d, eax
0x180007592  mov     r9d, eax
0x180007595  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000759f  shr     r8, 2
0x1800075a3  mul     r8
0x1800075a6  shr     rdx, 3
0x1800075aa  lea     rcx, [rdx+rdx*4]
0x1800075ae  add     rcx, rcx
0x1800075b1  sub     r8, rcx
0x1800075b4  mov     rax, [rbx+r8*8]
0x1800075b8  jmp     short loc_1800075C3
0x1800075ba  cmp     [rax], r9d
0x1800075bd  jz      short loc_1800075CE
0x1800075bf  mov     rax, [rax+8]
0x1800075c3  test    rax, rax
0x1800075c6  jnz     short loc_1800075BA
0x1800075c8  add     rsp, 20h
0x1800075cc  pop     rbx
0x1800075cd  retn
0x1800075ce  add     rax, 10h
0x1800075d2  jmp     short loc_1800075C8
```
