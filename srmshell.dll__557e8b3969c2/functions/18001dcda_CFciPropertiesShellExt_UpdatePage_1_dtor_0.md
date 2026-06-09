# _CFciPropertiesShellExt::UpdatePage_::_1_::dtor$0

- ea: `0x18001dcda`
- end: `0x18001dce6`
- name: `_CFciPropertiesShellExt::UpdatePage_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180004c98`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::UpdatePage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CFciPushVariable<bool>::~CFciPushVariable<bool>(a2 + 56);
}

```

## disassembly

```asm
0x18001dcda  lea     rcx, [rdx+38h]
0x18001dce1  jmp     ??1?$CFciPushVariable@_N@@QEAA@XZ; CFciPushVariable<bool>::~CFciPushVariable<bool>(void)
```
