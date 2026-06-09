# GetSourceEntry

- ea: `0x18001de98`
- end: `0x18001dec6`
- name: `GetSourceEntry`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x180012800`
- `0x180016a40`
- `0x18001af20`
- `0x18001decc`
- `0x18001e77c`

## callees

- `0x18001dd8c`

## pseudocode

```c
__int64 __fastcall GetSourceEntry(_QWORD **a1, unsigned int a2, __int64 a3)
{
  int SourceEntry; // eax
  __int64 v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  SourceEntry = FindSourceEntry(a1, a2, a3, &v5, 1);
  return v5 & -(__int64)(SourceEntry != 0);
}

```

## disassembly

```asm
0x18001de98  sub     rsp, 38h
0x18001de9c  lea     r9, [rsp+38h+arg_18]
0x18001dea1  mov     [rsp+38h+arg_18], 0
0x18001deaa  mov     [rsp+38h+var_18], 1
0x18001deb2  call    FindSourceEntry
0x18001deb7  neg     eax
0x18001deb9  sbb     rax, rax
0x18001debc  and     rax, [rsp+38h+arg_18]
0x18001dec1  add     rsp, 38h
0x18001dec5  retn
```
