# __memset_query

- ea: `0x140001d00`
- end: `0x140001d26`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001c80`

## callees

- `0x140001980`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140001d00  push    r9
0x140001d02  push    r8
0x140001d04  push    rdx
0x140001d05  push    rcx
0x140001d06  push    rax
0x140001d07  sub     rsp, 30h
0x140001d0b  movaps  [rsp+58h+var_38], xmm0
0x140001d10  call    __cpu_features_init
0x140001d15  movaps  xmm0, [rsp+58h+var_38]
0x140001d1a  add     rsp, 30h
0x140001d1e  pop     rax
0x140001d1f  pop     rcx
0x140001d20  pop     rdx
0x140001d21  pop     r8
0x140001d23  pop     r9
0x140001d25  retn
```
