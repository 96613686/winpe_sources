# __memset_query

- ea: `0x1400036c0`
- end: `0x1400036e6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003640`

## callees

- `0x140003040`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x1400036c0  push    r9
0x1400036c2  push    r8
0x1400036c4  push    rdx
0x1400036c5  push    rcx
0x1400036c6  push    rax
0x1400036c7  sub     rsp, 30h
0x1400036cb  movaps  [rsp+58h+var_38], xmm0
0x1400036d0  call    __cpu_features_init
0x1400036d5  movaps  xmm0, [rsp+58h+var_38]
0x1400036da  add     rsp, 30h
0x1400036de  pop     rax
0x1400036df  pop     rcx
0x1400036e0  pop     rdx
0x1400036e1  pop     r8
0x1400036e3  pop     r9
0x1400036e5  retn
```
