# LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)

- ea: `0x180033fc8`
- end: `0x18003402e`
- name: `?_AllocateSegmentDirectory@CLKRLinearHashTable@LKRhash@@CAQEAVCDirEntry@2@_K@Z`
- size: `102`
- prototype: `struct LKRhash::CDirEntry *__fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800341e0`
- `0x180034544`
- `0x180034aa8`

## callees

- `0x180033d8c`
- `0x180033fc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033ff3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033ff3`

## pseudocode

```c
struct LKRhash::CDirEntry *__fastcall LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64 a1)
{
  __int64 v2; // rax
  bool v3; // cf
  size_t v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  v2 = 8 * a1;
  if ( !is_mul_ok(a1, 8u) )
    v2 = -1;
  v3 = __CFADD__(v2, 8);
  v4 = v2 + 8;
  if ( v3 )
    v4 = -1;
  v5 = malloc(v4);
  if ( !v5 )
    return 0;
  v6 = v5 + 1;
  *v5 = a1;
  `vector constructor iterator'(v5 + 1, 8u, a1, (void *(*)(void *))LKRhash::CDirEntry::CDirEntry);
  return (struct LKRhash::CDirEntry *)v6;
}

```

## disassembly

```asm
0x180033fc8  mov     [rsp+arg_0], rbx
0x180033fcd  push    rdi
0x180033fce  sub     rsp, 20h
0x180033fd2  mov     rdi, rcx
0x180033fd5  mov     eax, 8
0x180033fda  mul     rcx
0x180033fdd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033fe4  cmovb   rax, rcx
0x180033fe8  add     rax, 8
0x180033fec  cmovb   rax, rcx
0x180033ff0  mov     rcx, rax; Size
0x180033ff3  call    cs:__imp_malloc
0x180033ff9  test    rax, rax
0x180033ffc  jz      short loc_18003401E
0x180033ffe  lea     rbx, [rax+8]
0x180034002  mov     [rax], rdi
0x180034005  mov     rcx, rbx; void *
0x180034008  lea     r9, ??0CDirEntry@LKRhash@@QEAA@XZ; void *(*)(void *)
0x18003400f  mov     r8, rdi; unsigned __int64
0x180034012  mov     edx, 8; unsigned __int64
0x180034017  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003401c  jmp     short loc_180034020
0x18003401e  xor     ebx, ebx
0x180034020  mov     rax, rbx
0x180034023  mov     rbx, [rsp+28h+arg_0]
0x180034028  add     rsp, 20h
0x18003402c  pop     rdi
0x18003402d  retn
```
