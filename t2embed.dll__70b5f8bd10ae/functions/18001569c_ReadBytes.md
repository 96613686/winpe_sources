# ReadBytes

- ea: `0x18001569c`
- end: `0x1800156e0`
- name: `ReadBytes`
- size: `68`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd44`
- `0x180014f98`
- `0x1800156e8`
- `0x18001b538`
- `0x180029228`

## callees

- `0x18001569c`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall ReadBytes(__int64 a1, void *a2, unsigned int a3, size_t a4)
{
  if ( !*(_QWORD *)a1 || a4 > 0xFFFFFFFF || (unsigned int)a4 + a3 < a3 || (unsigned int)a4 + a3 > *(_DWORD *)(a1 + 8) )
    return 1001;
  memcpy_0(a2, (const void *)(*(_QWORD *)a1 + a3), a4);
  return 0;
}

```

## disassembly

```asm
0x18001569c  sub     rsp, 28h
0x1800156a0  cmp     qword ptr [rcx], 0
0x1800156a4  mov     r10, rdx
0x1800156a7  jz      short loc_1800156C1
0x1800156a9  mov     eax, 0FFFFFFFFh
0x1800156ae  cmp     r9, rax
0x1800156b1  ja      short loc_1800156C1
0x1800156b3  lea     eax, [r9+r8]
0x1800156b7  cmp     eax, r8d
0x1800156ba  jb      short loc_1800156C1
0x1800156bc  cmp     eax, [rcx+8]
0x1800156bf  jbe     short loc_1800156CB
0x1800156c1  mov     eax, 3E9h
0x1800156c6  add     rsp, 28h
0x1800156ca  retn
0x1800156cb  mov     edx, r8d
0x1800156ce  mov     r8, r9; Size
0x1800156d1  add     rdx, [rcx]; Src
0x1800156d4  mov     rcx, r10; void *
0x1800156d7  call    memcpy_0
0x1800156dc  xor     eax, eax
0x1800156de  jmp     short loc_1800156C6
```
