# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000ec4c`
- end: `0x18000ec9e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f1ac`

## callees

- `0x18000ec4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec55`

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
0x18000ec4c  push    rbx
0x18000ec4e  sub     rsp, 20h
0x18000ec52  mov     rbx, rcx
0x18000ec55  call    cs:__imp_GetCurrentThreadId
0x18000ec5b  mov     r9d, eax
0x18000ec5e  mov     ecx, eax
0x18000ec60  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ec6a  shr     r9, 2
0x18000ec6e  mul     r9
0x18000ec71  shr     rdx, 3
0x18000ec75  lea     r8, [rdx+rdx*4]
0x18000ec79  add     r8, r8
0x18000ec7c  sub     r9, r8
0x18000ec7f  mov     rax, [rbx+r9*8]
0x18000ec83  jmp     short loc_18000EC8D
0x18000ec85  cmp     [rax], ecx
0x18000ec87  jz      short loc_18000EC98
0x18000ec89  mov     rax, [rax+8]
0x18000ec8d  test    rax, rax
0x18000ec90  jnz     short loc_18000EC85
0x18000ec92  add     rsp, 20h
0x18000ec96  pop     rbx
0x18000ec97  retn
0x18000ec98  add     rax, 10h
0x18000ec9c  jmp     short loc_18000EC92
```
