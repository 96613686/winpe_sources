# GetGroupEntry

- ea: `0x18001de20`
- end: `0x18001de4e`
- name: `GetGroupEntry`
- size: `46`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x180012800`
- `0x180016a40`
- `0x18001af20`
- `0x18001decc`
- `0x18001e77c`
- `0x18001ed64`

## callees

- `0x18001dc28`

## pseudocode

```c
__int64 __fastcall GetGroupEntry(_QWORD **a1, unsigned int a2, __int64 a3)
{
  int GroupEntry; // eax
  __int64 v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  GroupEntry = FindGroupEntry(a1, a2, a3, &v5, 1);
  return v5 & -(__int64)(GroupEntry != 0);
}

```

## disassembly

```asm
0x18001de20  sub     rsp, 38h
0x18001de24  lea     r9, [rsp+38h+arg_18]
0x18001de29  mov     [rsp+38h+arg_18], 0
0x18001de32  mov     [rsp+38h+var_18], 1
0x18001de3a  call    FindGroupEntry
0x18001de3f  neg     eax
0x18001de41  sbb     rax, rax
0x18001de44  and     rax, [rsp+38h+arg_18]
0x18001de49  add     rsp, 38h
0x18001de4d  retn
```
