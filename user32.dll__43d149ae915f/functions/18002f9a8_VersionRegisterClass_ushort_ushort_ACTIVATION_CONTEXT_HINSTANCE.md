# VersionRegisterClass(ushort *,ushort *,_ACTIVATION_CONTEXT *,HINSTANCE__ * *)

- ea: `0x18002f9a8`
- end: `0x18002faf1`
- name: `?VersionRegisterClass@@YAHPEAG0PEAU_ACTIVATION_CONTEXT@@PEAPEAUHINSTANCE__@@@Z`
- size: `329`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, struct _ACTIVATION_CONTEXT *, HINSTANCE *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002b310`
- `0x18002da30`
- `0x18002e1a4`

## callees

- `0x18002f9a8`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserGetAtomName` at `0x18002fa7a`
- `win32u!NtUserGetAtomName` at `0x18002fa7a`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x18002fa96`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800977a6`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x18002fa96`
- `ntdll!RtlDeactivateActivationContextUnsafeFast` at `0x1800977a6`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x18002fa07`
- `ntdll!RtlActivateActivationContextUnsafeFast` at `0x18002fa07`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fadd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fadd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fa16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fa16`

## pseudocode

```c

```
