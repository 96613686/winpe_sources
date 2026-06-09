# [thunk]:CWsmLogConfig::SetLogMaximumSize`adjustor{8}' (unsigned __int64)

- ea: `0x14000bc60`
- end: `0x14000bc69`
- name: `?SetLogMaximumSize@CWsmLogConfig@@W7EAAJ_K@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000bc00`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::SetLogMaximumSize(__int64 a1, __int64 a2)
{
  return CWsmLogConfig::SetLogMaximumSize((__int64 (__fastcall ***)(CWsmLogConfig *))(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000bc60  sub     rcx, 8; this
0x14000bc64  jmp     ?SetLogMaximumSize@CWsmLogConfig@@UEAAJ_K@Z; CWsmLogConfig::SetLogMaximumSize(unsigned __int64)
```
