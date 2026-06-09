# SafeSusAllocArray(unsigned __int64,unsigned __int64)

- ea: `0x18000b21c`
- end: `0x18000b276`
- name: `?SafeSusAllocArray@@YAPEAX_K0@Z`
- size: `90`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac10`
- `0x18000ad08`
- `0x18000f69c`
- `0x18000fabc`

## callees

- `0x18000b21c`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b25d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b25d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b24c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b24c`

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
0x18000b21c  push    rbx
0x18000b21e  sub     rsp, 30h
0x18000b222  mov     rax, cs:__security_cookie
0x18000b229  xor     rax, rsp
0x18000b22c  mov     [rsp+38h+var_10], rax
0x18000b231  mov     rax, rdx
0x18000b234  mov     [rsp+38h+var_18], 0
0x18000b23d  mul     rcx
0x18000b240  mov     rbx, rax
0x18000b243  test    rdx, rdx
0x18000b246  jz      short loc_18000B24C
0x18000b248  xor     eax, eax
0x18000b24a  jmp     short loc_18000B263
0x18000b24c  call    cs:__imp_GetProcessHeap
0x18000b252  mov     r8, rbx; dwBytes
0x18000b255  mov     edx, 8; dwFlags
0x18000b25a  mov     rcx, rax; hHeap
0x18000b25d  call    cs:__imp_HeapAlloc
0x18000b263  mov     rcx, [rsp+38h+var_10]
0x18000b268  xor     rcx, rsp; StackCookie
0x18000b26b  call    __security_check_cookie
0x18000b270  add     rsp, 30h
0x18000b274  pop     rbx
0x18000b275  retn
```
