# ComTaskMgrBase::UninitSingleton(void)

- ea: `0x140003250`
- end: `0x140003260`
- name: `?UninitSingleton@ComTaskMgrBase@@EEAAJXZ`
- size: `16`
- prototype: `__int64 __fastcall(ComTaskMgrBase *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400036b0`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::UninitSingleton(ComTaskMgrBase *this)
{
  ComTaskMgrBase::WaitForShutdownGuards();
  return 0;
}

```

## disassembly

```asm
0x140003250  sub     rsp, 28h
0x140003254  call    ?WaitForShutdownGuards@ComTaskMgrBase@@KAJXZ; ComTaskMgrBase::WaitForShutdownGuards(void)
0x140003259  xor     eax, eax
0x14000325b  add     rsp, 28h
0x14000325f  retn
```
