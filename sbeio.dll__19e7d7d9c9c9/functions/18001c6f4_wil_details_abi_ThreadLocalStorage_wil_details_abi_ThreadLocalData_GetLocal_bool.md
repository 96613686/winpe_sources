# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18001c6f4`
- end: `0x18001c746`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ca64`

## callees

- `0x18001c6f4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c6fd`
- `KERNEL32!GetCurrentThreadId` at `0x18001c6fd`

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
0x18001c6f4  push    rbx
0x18001c6f6  sub     rsp, 20h
0x18001c6fa  mov     rbx, rcx
0x18001c6fd  call    cs:__imp_GetCurrentThreadId
0x18001c703  mov     r9d, eax
0x18001c706  mov     ecx, eax
0x18001c708  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001c712  shr     r9, 2
0x18001c716  mul     r9
0x18001c719  shr     rdx, 3
0x18001c71d  lea     r8, [rdx+rdx*4]
0x18001c721  add     r8, r8
0x18001c724  sub     r9, r8
0x18001c727  mov     rax, [rbx+r9*8]
0x18001c72b  jmp     short loc_18001C735
0x18001c72d  cmp     [rax], ecx
0x18001c72f  jz      short loc_18001C740
0x18001c731  mov     rax, [rax+8]
0x18001c735  test    rax, rax
0x18001c738  jnz     short loc_18001C72D
0x18001c73a  add     rsp, 20h
0x18001c73e  pop     rbx
0x18001c73f  retn
0x18001c740  add     rax, 10h
0x18001c744  jmp     short loc_18001C73A
```
