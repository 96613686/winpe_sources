# _pGetUninstallInterfaceCommon_::_1_::dtor$0

- ea: `0x1800138a3`
- end: `0x1800138af`
- name: `_pGetUninstallInterfaceCommon_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d674`

## pseudocode

```c
__int64 __fastcall pGetUninstallInterfaceCommon_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return RAII::CAutoWdsLibFree<unsigned short *>::~CAutoWdsLibFree<unsigned short *>(a2 + 112);
}

```

## disassembly

```asm
0x1800138a3  lea     rcx, [rdx+70h]
0x1800138aa  jmp     ??1?$CAutoWdsLibFree@PEAG@RAII@@UEAA@XZ; RAII::CAutoWdsLibFree<ushort *>::~CAutoWdsLibFree<ushort *>(void)
```
