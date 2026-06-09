# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800199ec`
- end: `0x180019a45`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019d18`

## callees

- `0x1800199ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800199f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800199f5`

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
0x1800199ec  push    rbx
0x1800199ee  sub     rsp, 20h
0x1800199f2  mov     rbx, rcx
0x1800199f5  call    cs:__imp_GetCurrentThreadId
0x1800199fc  nop     dword ptr [rax+rax+00h]
0x180019a01  mov     r9d, eax
0x180019a04  mov     ecx, eax
0x180019a06  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180019a10  shr     r9, 2
0x180019a14  mul     r9
0x180019a17  shr     rdx, 3
0x180019a1b  lea     r8, [rdx+rdx*4]
0x180019a1f  add     r8, r8
0x180019a22  sub     r9, r8
0x180019a25  mov     rax, [rbx+r9*8]
0x180019a29  jmp     short loc_180019A33
0x180019a2b  cmp     [rax], ecx
0x180019a2d  jz      short loc_180019A3F
0x180019a2f  mov     rax, [rax+8]
0x180019a33  test    rax, rax
0x180019a36  jnz     short loc_180019A2B
0x180019a38  add     rsp, 20h
0x180019a3c  pop     rbx
0x180019a3d  retn
0x180019a3f  add     rax, 10h
0x180019a43  jmp     short loc_180019A38
```
