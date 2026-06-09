# SqosClientNodeComparisonRoutine

- ea: `0x140005dc4`
- end: `0x140005ddd`
- name: `SqosClientNodeComparisonRoutine`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400117e4`

## callees

- `0x140008e20`

## pseudocode

```c
int __fastcall SqosClientNodeComparisonRoutine(const void *a1, __int64 a2)
{
  return memcmp(a1, (const void *)(a2 + 24), 0x10u);
}

```

## disassembly

```asm
0x140005dc4  sub     rsp, 28h
0x140005dc8  add     rdx, 18h; Buf2
0x140005dcc  mov     r8d, 10h; Size
0x140005dd2  call    memcmp
0x140005dd7  add     rsp, 28h
0x140005ddb  retn
```
