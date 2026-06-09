# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002468c`
- end: `0x1800246e2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002423c`

## callees

- `0x18002468c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024699`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024699`

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
0x18002468c  push    rbx
0x18002468e  sub     rsp, 20h
0x180024692  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024699  call    cs:__imp_GetCurrentThreadId
0x18002469f  mov     r8d, eax
0x1800246a2  mov     r9d, eax
0x1800246a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800246af  shr     r8, 2
0x1800246b3  mul     r8
0x1800246b6  shr     rdx, 3
0x1800246ba  lea     rcx, [rdx+rdx*4]
0x1800246be  add     rcx, rcx
0x1800246c1  sub     r8, rcx
0x1800246c4  mov     rax, [rbx+r8*8]
0x1800246c8  test    rax, rax
0x1800246cb  jz      short loc_1800246DC
0x1800246cd  cmp     [rax], r9d
0x1800246d0  jz      short loc_1800246D8
0x1800246d2  mov     rax, [rax+8]
0x1800246d6  jmp     short loc_1800246C8
0x1800246d8  add     rax, 10h
0x1800246dc  add     rsp, 20h
0x1800246e0  pop     rbx
0x1800246e1  retn
```
