# SafeSusAllocArray(unsigned __int64,unsigned __int64)

- ea: `0x14000d538`
- end: `0x14000d592`
- name: `?SafeSusAllocArray@@YAPEAX_K0@Z`
- size: `90`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cb5c`
- `0x14000cc58`
- `0x14000cd5c`
- `0x140014cac`
- `0x1400150cc`
- `0x140015dec`
- `0x1400164c8`
- `0x1400168cc`
- `0x140016cd4`
- `0x1400170dc`
- `0x140017624`
- `0x1400189f4`
- `0x140018b14`

## callees

- `0x14000d538`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d579`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d568`

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
0x14000d538  push    rbx
0x14000d53a  sub     rsp, 30h
0x14000d53e  mov     rax, cs:__security_cookie
0x14000d545  xor     rax, rsp
0x14000d548  mov     [rsp+38h+var_10], rax
0x14000d54d  mov     rax, rdx
0x14000d550  mov     [rsp+38h+var_18], 0
0x14000d559  mul     rcx
0x14000d55c  mov     rbx, rax
0x14000d55f  test    rdx, rdx
0x14000d562  jz      short loc_14000D568
0x14000d564  xor     eax, eax
0x14000d566  jmp     short loc_14000D57F
0x14000d568  call    cs:__imp_GetProcessHeap
0x14000d56e  mov     r8, rbx; dwBytes
0x14000d571  mov     edx, 8; dwFlags
0x14000d576  mov     rcx, rax; hHeap
0x14000d579  call    cs:__imp_HeapAlloc
0x14000d57f  mov     rcx, [rsp+38h+var_10]
0x14000d584  xor     rcx, rsp; StackCookie
0x14000d587  call    __security_check_cookie
0x14000d58c  add     rsp, 30h
0x14000d590  pop     rbx
0x14000d591  retn
```
