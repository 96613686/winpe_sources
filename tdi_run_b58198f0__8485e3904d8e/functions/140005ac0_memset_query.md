# __memset_query

- ea: `0x140005ac0`
- end: `0x140005ae6`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005a40`

## callees

- `0x1400042f0`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140005ac0  push    r9
0x140005ac2  push    r8
0x140005ac4  push    rdx
0x140005ac5  push    rcx
0x140005ac6  push    rax
0x140005ac7  sub     rsp, 30h
0x140005acb  movaps  [rsp+58h+var_38], xmm0
0x140005ad0  call    __cpu_features_init
0x140005ad5  movaps  xmm0, [rsp+58h+var_38]
0x140005ada  add     rsp, 30h
0x140005ade  pop     rax
0x140005adf  pop     rcx
0x140005ae0  pop     rdx
0x140005ae1  pop     r8
0x140005ae3  pop     r9
0x140005ae5  retn
```
