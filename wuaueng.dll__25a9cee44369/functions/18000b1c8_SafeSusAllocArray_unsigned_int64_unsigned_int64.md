# SafeSusAllocArray(unsigned __int64,unsigned __int64)

- ea: `0x18000b1c8`
- end: `0x18000b222`
- name: `?SafeSusAllocArray@@YAPEAX_K0@Z`
- size: `90`
- prototype: `LPVOID __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000abbc`
- `0x18000acb4`
- `0x18000f64c`
- `0x18000fa6c`

## callees

- `0x18000b1c8`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b209`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b209`

## pseudocode

```c
LPVOID __fastcall SafeSusAllocArray(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T v2; // rbx
  HANDLE ProcessHeap; // rax

  v2 = a1 * a2;
  if ( !is_mul_ok(a1, a2) )
    return 0;
  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, v2);
}

```

## disassembly

```asm
0x18000b1c8  push    rbx
0x18000b1ca  sub     rsp, 30h
0x18000b1ce  mov     rax, cs:__security_cookie
0x18000b1d5  xor     rax, rsp
0x18000b1d8  mov     [rsp+38h+var_10], rax
0x18000b1dd  mov     rax, rdx
0x18000b1e0  mov     [rsp+38h+var_18], 0
0x18000b1e9  mul     rcx
0x18000b1ec  mov     rbx, rax
0x18000b1ef  test    rdx, rdx
0x18000b1f2  jz      short loc_18000B1F8
0x18000b1f4  xor     eax, eax
0x18000b1f6  jmp     short loc_18000B20F
0x18000b1f8  call    cs:__imp_GetProcessHeap
0x18000b1fe  mov     r8, rbx; dwBytes
0x18000b201  mov     edx, 8; dwFlags
0x18000b206  mov     rcx, rax; hHeap
0x18000b209  call    cs:__imp_HeapAlloc
0x18000b20f  mov     rcx, [rsp+38h+var_10]
0x18000b214  xor     rcx, rsp; StackCookie
0x18000b217  call    __security_check_cookie
0x18000b21c  add     rsp, 30h
0x18000b220  pop     rbx
0x18000b221  retn
```
