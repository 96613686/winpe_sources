# ApplicationActivationManagerProxy::ActivateApplication(ushort const *,ushort const *,ACTIVATEOPTIONS,ulong *)

- ea: `0x180034220`
- end: `0x18003448f`
- name: `?ActivateApplication@ApplicationActivationManagerProxy@@UEAAJPEBG0W4ACTIVATEOPTIONS@@PEAK@Z`
- size: `623`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const WCHAR *, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003d24`
- `0x180012450`
- `0x180018180`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002bc68`
- `0x18002d4c8`
- `0x180033ed4`
- `0x180034220`
- `0x180075e54`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003439c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003439c`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18003442b`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18003442b`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x1800343ae`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x1800343ae`

## pseudocode

```c

```
