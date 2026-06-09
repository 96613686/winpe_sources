# _RunUpdateDeploymentSession_::_1_::dtor$0

- ea: `0x140021527`
- end: `0x140021533`
- name: `_RunUpdateDeploymentSession_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140001b38`

## pseudocode

```c
__int64 __fastcall RunUpdateDeploymentSession_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return XInterface<IUnknown>::~XInterface<IUnknown>(a2 + 80);
}

```

## disassembly

```asm
0x140021527  lea     rcx, [rdx+50h]
0x14002152e  jmp     ??1?$XInterface@UIUnknown@@@@QEAA@XZ; XInterface<IUnknown>::~XInterface<IUnknown>(void)
```
