# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800148b0`
- end: `0x180014902`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b34`

## callees

- `0x1800148b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148b9`

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
0x1800148b0  push    rbx
0x1800148b2  sub     rsp, 20h
0x1800148b6  mov     rbx, rcx
0x1800148b9  call    cs:__imp_GetCurrentThreadId
0x1800148bf  mov     r9d, eax
0x1800148c2  mov     ecx, eax
0x1800148c4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800148ce  shr     r9, 2
0x1800148d2  mul     r9
0x1800148d5  shr     rdx, 3
0x1800148d9  lea     r8, [rdx+rdx*4]
0x1800148dd  add     r8, r8
0x1800148e0  sub     r9, r8
0x1800148e3  mov     rax, [rbx+r9*8]
0x1800148e7  jmp     short loc_1800148F1
0x1800148e9  cmp     [rax], ecx
0x1800148eb  jz      short loc_1800148FC
0x1800148ed  mov     rax, [rax+8]
0x1800148f1  test    rax, rax
0x1800148f4  jnz     short loc_1800148E9
0x1800148f6  add     rsp, 20h
0x1800148fa  pop     rbx
0x1800148fb  retn
0x1800148fc  add     rax, 10h
0x180014900  jmp     short loc_1800148F6
```
