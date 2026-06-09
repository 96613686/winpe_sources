# CreateFile2

- ea: `0x14001a39c`
- end: `0x14001a3cb`
- name: `CreateFile2`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001b67c`

## callees

- `0x14001a3fc`

## pseudocode

```c
__int64 __fastcall CreateFile2(const WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return CreateFileInternal(a1, 0x80000000, 1u, 3, a5, 2);
}

```

## disassembly

```asm
0x14001a39c  sub     rsp, 38h
0x14001a3a0  mov     rax, [rsp+38h+arg_20]
0x14001a3a5  mov     r9d, 3
0x14001a3ab  mov     [rsp+38h+var_10], 2; int
0x14001a3b3  mov     edx, 80000000h
0x14001a3b8  mov     [rsp+38h+var_18], rax; __int64
0x14001a3bd  lea     r8d, [r9-2]
0x14001a3c1  call    CreateFileInternal
0x14001a3c6  add     rsp, 38h
0x14001a3ca  retn
```
