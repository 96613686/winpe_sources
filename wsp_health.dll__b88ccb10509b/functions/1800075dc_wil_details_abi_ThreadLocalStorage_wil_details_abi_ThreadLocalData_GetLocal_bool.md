# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800075dc`
- end: `0x18000762e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007900`

## callees

- `0x1800075dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075e5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(a1 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
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
0x1800075dc  push    rbx
0x1800075de  sub     rsp, 20h
0x1800075e2  mov     rbx, rcx
0x1800075e5  call    cs:__imp_GetCurrentThreadId
0x1800075eb  mov     r9d, eax
0x1800075ee  mov     ecx, eax
0x1800075f0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800075fa  shr     r9, 2
0x1800075fe  mul     r9
0x180007601  shr     rdx, 3
0x180007605  lea     r8, [rdx+rdx*4]
0x180007609  add     r8, r8
0x18000760c  sub     r9, r8
0x18000760f  mov     rax, [rbx+r9*8]
0x180007613  jmp     short loc_18000761D
0x180007615  cmp     [rax], ecx
0x180007617  jz      short loc_180007628
0x180007619  mov     rax, [rax+8]
0x18000761d  test    rax, rax
0x180007620  jnz     short loc_180007615
0x180007622  add     rsp, 20h
0x180007626  pop     rbx
0x180007627  retn
0x180007628  add     rax, 10h
0x18000762c  jmp     short loc_180007622
```
