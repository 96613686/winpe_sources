# CompressBuffer

- ea: `0x180020588`
- end: `0x1800205b3`
- name: `CompressBuffer`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800205bc`
- `0x18002089c`

## callees

- `0x180022aec`

## pseudocode

```c
__int64 __fastcall CompressBuffer(void *a1, __int64 a2, LPVOID *a3, __int64 a4, __int64 a5)
{
  return (unsigned int)T2OSSvcCompressFontBuffer(a1, a2, (__int64)a3, a3, a4, a5) == 0 ? 0x100 : 0;
}

```

## disassembly

```asm
0x180020588  sub     rsp, 38h
0x18002058c  mov     rax, [rsp+38h+arg_20]
0x180020591  mov     [rsp+38h+var_10], rax
0x180020596  mov     [rsp+38h+var_18], r9
0x18002059b  mov     r9, r8
0x18002059e  call    T2OSSvcCompressFontBuffer
0x1800205a3  neg     eax
0x1800205a5  sbb     eax, eax
0x1800205a7  not     eax
0x1800205a9  and     eax, 100h
0x1800205ae  add     rsp, 38h
0x1800205b2  retn
```
