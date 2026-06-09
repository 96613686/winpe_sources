# MRTComponent_Generalize(void)

- ea: `0x180002670`
- end: `0x180002682`
- name: `?MRTComponent_Generalize@@YAKXZ`
- size: `18`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002368`
- `0x180002688`

## pseudocode

```c
__int64 MRTComponent_Generalize(void)
{
  WDComponent_Cleanup();
  return MRTComponent_Cleanup();
}

```

## disassembly

```asm
0x180002670  sub     rsp, 28h
0x180002674  call    WDComponent_Cleanup
0x180002679  add     rsp, 28h
0x18000267d  jmp     MRTComponent_Cleanup
```
