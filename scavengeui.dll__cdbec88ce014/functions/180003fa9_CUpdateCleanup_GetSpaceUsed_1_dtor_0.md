# _CUpdateCleanup::GetSpaceUsed_::_1_::dtor$0

- ea: `0x180003fa9`
- end: `0x180003fb5`
- name: `_CUpdateCleanup::GetSpaceUsed_::_1_::dtor$0`
- size: `12`
- prototype: `void **__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800030f0`

## pseudocode

```c
void **__fastcall CUpdateCleanup::GetSpaceUsed_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return RAII::CAutoDismDelete<_DismPackage *>::~CAutoDismDelete<_DismPackage *>((_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x180003fa9  lea     rcx, [rdx+40h]
0x180003fb0  jmp     ??1?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@UEAA@XZ; RAII::CAutoDismDelete<_DismPackage *>::~CAutoDismDelete<_DismPackage *>(void)
```
