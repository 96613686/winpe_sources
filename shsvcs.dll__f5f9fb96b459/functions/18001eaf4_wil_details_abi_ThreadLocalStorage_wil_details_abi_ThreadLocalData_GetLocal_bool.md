# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18001eaf4`
- end: `0x18001eb46`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ee18`

## callees

- `0x18001eaf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eafd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eafd`

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
0x18001eaf4  push    rbx
0x18001eaf6  sub     rsp, 20h
0x18001eafa  mov     rbx, rcx
0x18001eafd  call    cs:__imp_GetCurrentThreadId
0x18001eb03  mov     r9d, eax
0x18001eb06  mov     ecx, eax
0x18001eb08  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001eb12  shr     r9, 2
0x18001eb16  mul     r9
0x18001eb19  shr     rdx, 3
0x18001eb1d  lea     r8, [rdx+rdx*4]
0x18001eb21  add     r8, r8
0x18001eb24  sub     r9, r8
0x18001eb27  mov     rax, [rbx+r9*8]
0x18001eb2b  jmp     short loc_18001EB35
0x18001eb2d  cmp     [rax], ecx
0x18001eb2f  jz      short loc_18001EB40
0x18001eb31  mov     rax, [rax+8]
0x18001eb35  test    rax, rax
0x18001eb38  jnz     short loc_18001EB2D
0x18001eb3a  add     rsp, 20h
0x18001eb3e  pop     rbx
0x18001eb3f  retn
0x18001eb40  add     rax, 10h
0x18001eb44  jmp     short loc_18001EB3A
```
