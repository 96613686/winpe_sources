# _dynamic_initializer_for__s_ControlProtocol__

- ea: `0x180001280`
- end: `0x1800012ae`
- name: `_dynamic_initializer_for__s_ControlProtocol__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001898`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000128b`
- `KERNEL32!InitializeCriticalSection` at `0x18000128b`

## pseudocode

```c
int dynamic_initializer_for__s_ControlProtocol__()
{
  InitializeCriticalSection(&stru_180015920);
  dword_180015948 = 0;
  return atexit(dynamic_atexit_destructor_for__s_ControlProtocol__);
}

```

## disassembly

```asm
0x180001280  sub     rsp, 28h
0x180001284  lea     rcx, stru_180015920; lpCriticalSection
0x18000128b  call    cs:__imp_InitializeCriticalSection
0x180001292  nop     dword ptr [rax+rax+00h]
0x180001297  and     cs:dword_180015948, 0
0x18000129e  lea     rcx, _dynamic_atexit_destructor_for__s_ControlProtocol__
0x1800012a5  add     rsp, 28h
0x1800012a9  jmp     atexit
```
