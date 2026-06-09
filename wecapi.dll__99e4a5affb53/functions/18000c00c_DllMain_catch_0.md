# DllMain$catch$0

- ea: `0x18000c00c`
- end: `0x18000c02a`
- name: `DllMain$catch$0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllMain_catch_0()
{
  return 0;
}

```

## disassembly

```asm
0x18000c00c  mov     [rsp+arg_8], rdx
0x18000c011  push    rbp
0x18000c012  sub     rsp, 20h
0x18000c016  mov     rbp, rdx
0x18000c019  mov     rax, 0
0x18000c023  add     rsp, 20h
0x18000c027  pop     rbp
0x18000c028  retn
```
