# LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)

- ea: `0x180036ab8`
- end: `0x180036b25`
- name: `?_AllocateSegmentDirectory@CLKRLinearHashTable@LKRhash@@CAQEAVCDirEntry@2@_K@Z`
- size: `109`
- prototype: `struct LKRhash::CDirEntry *__fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180036ce0`
- `0x180037044`
- `0x1800375b0`

## callees

- `0x180036848`
- `0x180036ab8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036ae3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036ae3`

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
0x180036ab8  mov     [rsp+arg_0], rbx
0x180036abd  push    rdi
0x180036abe  sub     rsp, 20h
0x180036ac2  mov     rdi, rcx
0x180036ac5  mov     eax, 8
0x180036aca  mul     rcx
0x180036acd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180036ad4  cmovb   rax, rcx
0x180036ad8  add     rax, 8
0x180036adc  cmovb   rax, rcx
0x180036ae0  mov     rcx, rax; Size
0x180036ae3  call    cs:__imp_malloc
0x180036aea  nop     dword ptr [rax+rax+00h]
0x180036aef  test    rax, rax
0x180036af2  jz      short loc_180036B14
0x180036af4  lea     rbx, [rax+8]
0x180036af8  mov     [rax], rdi
0x180036afb  mov     rcx, rbx; void *
0x180036afe  lea     r9, ??0CDirEntry@LKRhash@@QEAA@XZ; void *(*)(void *)
0x180036b05  mov     r8, rdi; unsigned __int64
0x180036b08  mov     edx, 8; unsigned __int64
0x180036b0d  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180036b12  jmp     short loc_180036B16
0x180036b14  xor     ebx, ebx
0x180036b16  mov     rax, rbx
0x180036b19  mov     rbx, [rsp+28h+arg_0]
0x180036b1e  add     rsp, 20h
0x180036b22  pop     rdi
0x180036b23  retn
```
