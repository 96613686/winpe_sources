# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18001b35c`
- end: `0x18001b3ac`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b304`

## callees

- `0x18001b35c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b365`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001b35c  push    rbx
0x18001b35e  sub     rsp, 20h
0x18001b362  mov     rbx, rcx
0x18001b365  call    cs:__imp_GetCurrentThreadId
0x18001b36b  mov     ecx, eax
0x18001b36d  mov     r9d, eax
0x18001b370  shr     r9, 2
0x18001b374  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001b37e  mul     r9
0x18001b381  shr     rdx, 3
0x18001b385  lea     r8, [rdx+rdx*4]
0x18001b389  add     r8, r8
0x18001b38c  sub     r9, r8
0x18001b38f  mov     rax, [rbx+r9*8]
0x18001b393  test    rax, rax
0x18001b396  jz      short loc_18001B3A6
0x18001b398  cmp     [rax], ecx
0x18001b39a  jz      short loc_18001B3A2
0x18001b39c  mov     rax, [rax+8]
0x18001b3a0  jmp     short loc_18001B393
0x18001b3a2  add     rax, 10h
0x18001b3a6  add     rsp, 20h
0x18001b3aa  pop     rbx
0x18001b3ab  retn
```
