# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000e45c`
- end: `0x18000e4ae`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e780`

## callees

- `0x18000e45c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e465`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e465`

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
0x18000e45c  push    rbx
0x18000e45e  sub     rsp, 20h
0x18000e462  mov     rbx, rcx
0x18000e465  call    cs:__imp_GetCurrentThreadId
0x18000e46b  mov     ecx, eax
0x18000e46d  mov     r9d, eax
0x18000e470  shr     r9, 2
0x18000e474  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000e47e  mul     r9
0x18000e481  shr     rdx, 3
0x18000e485  lea     r8, [rdx+rdx*4]
0x18000e489  add     r8, r8
0x18000e48c  sub     r9, r8
0x18000e48f  mov     rax, [rbx+r9*8]
0x18000e493  jmp     short loc_18000E49D
0x18000e495  cmp     [rax], ecx
0x18000e497  jz      short loc_18000E4A8
0x18000e499  mov     rax, [rax+8]
0x18000e49d  test    rax, rax
0x18000e4a0  jnz     short loc_18000E495
0x18000e4a2  add     rsp, 20h
0x18000e4a6  pop     rbx
0x18000e4a7  retn
0x18000e4a8  add     rax, 10h
0x18000e4ac  jmp     short loc_18000E4A2
```
