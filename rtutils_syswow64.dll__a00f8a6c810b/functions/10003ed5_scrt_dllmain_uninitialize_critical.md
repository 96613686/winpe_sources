# ___scrt_dllmain_uninitialize_critical

- ea: `0x10003ed5`
- end: `0x10003ee2`
- name: `___scrt_dllmain_uninitialize_critical`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100039eb`

## callees

- `0x1000470d`

## pseudocode

```c
int __cdecl __scrt_dllmain_uninitialize_critical(int a1)
{
  __scrt_stub_for_acrt_initialize(0);
  return __scrt_stub_for_acrt_initialize(a1);
}

```

## disassembly

```asm
0x10003ed5  push    0
0x10003ed7  call    ___scrt_stub_for_acrt_initialize
0x10003edc  pop     ecx
0x10003edd  jmp     ___scrt_stub_for_acrt_initialize
```
