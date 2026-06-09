# CRegInfo::EnumKeyWithVer(ushort const *,ushort const *,CPtrAry<ushort *> *)

- ea: `0x18000c7f8`
- end: `0x18000c977`
- name: `?EnumKeyWithVer@CRegInfo@@SAJPEBG0PEAV?$CPtrAry@PEAG@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, wchar_t *SubStr, CImplPtrAry *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dc78`
- `0x18003e744`

## callees

- `0x18000c7f8`
- `0x18004a28c`
- `0x18004d030`
- `0x1800653c0`
- `0x1800653e6`

## import_xrefs

- `ucrtbase_clr0400!wcsncmp` at `0x18000c8a2`
- `ucrtbase_clr0400!wcsncmp` at `0x18000c8a2`
- `ADVAPI32!RegCloseKey` at `0x18000c952`
- `ADVAPI32!RegCloseKey` at `0x18000c952`
- `ADVAPI32!RegEnumKeyExW` at `0x18000c927`
- `ADVAPI32!RegEnumKeyExW` at `0x18000c927`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c85d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c85d`

## pseudocode

```c

```
