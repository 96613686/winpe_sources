# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x180008dbc`
- end: `0x180008e0e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090cc`

## callees

- `0x180008dbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc5`

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
0x180008dbc  push    rbx
0x180008dbe  sub     rsp, 20h
0x180008dc2  mov     rbx, rcx
0x180008dc5  call    cs:__imp_GetCurrentThreadId
0x180008dcb  mov     r9d, eax
0x180008dce  mov     ecx, eax
0x180008dd0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008dda  shr     r9, 2
0x180008dde  mul     r9
0x180008de1  shr     rdx, 3
0x180008de5  lea     r8, [rdx+rdx*4]
0x180008de9  add     r8, r8
0x180008dec  sub     r9, r8
0x180008def  mov     rax, [rbx+r9*8]
0x180008df3  jmp     short loc_180008DFD
0x180008df5  cmp     [rax], ecx
0x180008df7  jz      short loc_180008E08
0x180008df9  mov     rax, [rax+8]
0x180008dfd  test    rax, rax
0x180008e00  jnz     short loc_180008DF5
0x180008e02  add     rsp, 20h
0x180008e06  pop     rbx
0x180008e07  retn
0x180008e08  add     rax, 10h
0x180008e0c  jmp     short loc_180008E02
```
