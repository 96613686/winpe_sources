# __acrt_initialize_command_line

- ea: `0x100430180`
- end: `0x1004301a5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x100430184`
- `KERNEL32!GetCommandLineA` at `0x100430184`
- `KERNEL32!GetCommandLineW` at `0x100430191`
- `KERNEL32!GetCommandLineW` at `0x100430191`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  acmdln = GetCommandLineA();
  wcmdln = GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x100430180  sub     rsp, 28h
0x100430184  call    cs:__imp_GetCommandLineA
0x10043018a  mov     cs:_acmdln, rax
0x100430191  call    cs:__imp_GetCommandLineW
0x100430197  mov     cs:_wcmdln, rax
0x10043019e  mov     al, 1
0x1004301a0  add     rsp, 28h
0x1004301a4  retn
```
