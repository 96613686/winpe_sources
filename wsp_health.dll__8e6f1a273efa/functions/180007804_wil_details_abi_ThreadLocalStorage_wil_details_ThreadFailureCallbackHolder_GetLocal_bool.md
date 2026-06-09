# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007804`
- end: `0x180007863`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007304`

## callees

- `0x180007804`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007811`

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
0x180007804  push    rbx
0x180007806  sub     rsp, 20h
0x18000780a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007811  call    cs:__imp_GetCurrentThreadId
0x180007818  nop     dword ptr [rax+rax+00h]
0x18000781d  mov     r8d, eax
0x180007820  mov     r9d, eax
0x180007823  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000782d  shr     r8, 2
0x180007831  mul     r8
0x180007834  shr     rdx, 3
0x180007838  lea     rcx, [rdx+rdx*4]
0x18000783c  add     rcx, rcx
0x18000783f  sub     r8, rcx
0x180007842  mov     rax, [rbx+r8*8]
0x180007846  jmp     short loc_180007851
0x180007848  cmp     [rax], r9d
0x18000784b  jz      short loc_18000785D
0x18000784d  mov     rax, [rax+8]
0x180007851  test    rax, rax
0x180007854  jnz     short loc_180007848
0x180007856  add     rsp, 20h
0x18000785a  pop     rbx
0x18000785b  retn
0x18000785d  add     rax, 10h
0x180007861  jmp     short loc_180007856
```
