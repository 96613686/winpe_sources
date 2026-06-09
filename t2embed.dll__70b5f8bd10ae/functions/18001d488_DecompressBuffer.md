# DecompressBuffer

- ea: `0x18001d488`
- end: `0x18001d4ab`
- name: `DecompressBuffer`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800190a4`

## callees

- `0x180019eec`

## pseudocode

```c
__int64 __fastcall DecompressBuffer(void *a1, __int64 a2, LPVOID *a3, __int64 a4, __int64 a5)
{
  return (unsigned int)T2OSSvcDecompressFontBuffer(a1, a2, a3, a4, a5) == 0 ? 0x111 : 0;
}

```

## disassembly

```asm
0x18001d488  sub     rsp, 38h
0x18001d48c  mov     rax, [rsp+38h+arg_20]
0x18001d491  mov     [rsp+38h+var_18], rax
0x18001d496  call    T2OSSvcDecompressFontBuffer
0x18001d49b  neg     eax
0x18001d49d  sbb     eax, eax
0x18001d49f  not     eax
0x18001d4a1  and     eax, 111h
0x18001d4a6  add     rsp, 38h
0x18001d4aa  retn
```
