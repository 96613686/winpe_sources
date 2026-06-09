# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18003849c`
- end: `0x1800384ee`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180038c50`

## callees

- `0x18003849c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800384a5`
- `KERNEL32!GetCurrentThreadId` at `0x1800384a5`

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
0x18003849c  push    rbx
0x18003849e  sub     rsp, 20h
0x1800384a2  mov     rbx, rcx
0x1800384a5  call    cs:__imp_GetCurrentThreadId
0x1800384ab  mov     r9d, eax
0x1800384ae  mov     ecx, eax
0x1800384b0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800384ba  shr     r9, 2
0x1800384be  mul     r9
0x1800384c1  shr     rdx, 3
0x1800384c5  lea     r8, [rdx+rdx*4]
0x1800384c9  add     r8, r8
0x1800384cc  sub     r9, r8
0x1800384cf  mov     rax, [rbx+r9*8]
0x1800384d3  jmp     short loc_1800384DD
0x1800384d5  cmp     [rax], ecx
0x1800384d7  jz      short loc_1800384E8
0x1800384d9  mov     rax, [rax+8]
0x1800384dd  test    rax, rax
0x1800384e0  jnz     short loc_1800384D5
0x1800384e2  add     rsp, 20h
0x1800384e6  pop     rbx
0x1800384e7  retn
0x1800384e8  add     rax, 10h
0x1800384ec  jmp     short loc_1800384E2
```
