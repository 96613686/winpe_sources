# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18003dc3c`
- end: `0x18003dc8e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003df4c`

## callees

- `0x18003dc3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dc45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dc45`

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
0x18003dc3c  push    rbx
0x18003dc3e  sub     rsp, 20h
0x18003dc42  mov     rbx, rcx
0x18003dc45  call    cs:__imp_GetCurrentThreadId
0x18003dc4b  mov     r9d, eax
0x18003dc4e  mov     ecx, eax
0x18003dc50  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003dc5a  shr     r9, 2
0x18003dc5e  mul     r9
0x18003dc61  shr     rdx, 3
0x18003dc65  lea     r8, [rdx+rdx*4]
0x18003dc69  add     r8, r8
0x18003dc6c  sub     r9, r8
0x18003dc6f  mov     rax, [rbx+r9*8]
0x18003dc73  jmp     short loc_18003DC7D
0x18003dc75  cmp     [rax], ecx
0x18003dc77  jz      short loc_18003DC88
0x18003dc79  mov     rax, [rax+8]
0x18003dc7d  test    rax, rax
0x18003dc80  jnz     short loc_18003DC75
0x18003dc82  add     rsp, 20h
0x18003dc86  pop     rbx
0x18003dc87  retn
0x18003dc88  add     rax, 10h
0x18003dc8c  jmp     short loc_18003DC82
```
