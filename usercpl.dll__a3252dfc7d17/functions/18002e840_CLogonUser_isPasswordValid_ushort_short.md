# CLogonUser::isPasswordValid(ushort *,short *)

- ea: `0x18002e840`
- end: `0x18002e945`
- name: `?isPasswordValid@CLogonUser@@UEAAJPEAGPEAF@Z`
- size: `261`
- prototype: `int(CLogonUser *__hidden this, unsigned __int16 *, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18002e840`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e8f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e8f9`
- `ADVAPI32!LogonUserW` at `0x18002e8ea`
- `ADVAPI32!LogonUserW` at `0x18002e8ea`
- `KERNEL32!GetComputerNameW` at `0x18002e8b1`
- `KERNEL32!GetComputerNameW` at `0x18002e8b1`

## pseudocode

```c

```
