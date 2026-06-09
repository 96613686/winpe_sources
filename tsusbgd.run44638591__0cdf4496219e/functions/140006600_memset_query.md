# __memset_query

- ea: `0x140006600`
- end: `0x140006626`
- name: `__memset_query`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006580`

## callees

- `0x1400010d0`

## pseudocode

```c
void _memset_query()
{
  _cpu_features_init();
}

```

## disassembly

```asm
0x140006600  push    r9
0x140006602  push    r8
0x140006604  push    rdx
0x140006605  push    rcx
0x140006606  push    rax
0x140006607  sub     rsp, 30h
0x14000660b  movaps  [rsp+58h+var_38], xmm0
0x140006610  call    __cpu_features_init
0x140006615  movaps  xmm0, [rsp+58h+var_38]
0x14000661a  add     rsp, 30h
0x14000661e  pop     rax
0x14000661f  pop     rcx
0x140006620  pop     rdx
0x140006621  pop     r8
0x140006623  pop     r9
0x140006625  retn
```
