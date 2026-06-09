# CChangeOnlinePasswordPlugin::SetAuthenticationBuffer(uchar *,ulong)

- ea: `0x18005df50`
- end: `0x18005e196`
- name: `?SetAuthenticationBuffer@CChangeOnlinePasswordPlugin@@UEAAJPEAEK@Z`
- size: `582`
- prototype: `int(CChangeOnlinePasswordPlugin *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000442c`
- `0x18000dafc`
- `0x18005df50`
- `0x18005f594`
- `0x1800753b0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e088`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e088`
- `credui!CredUnPackAuthenticationBufferW` at `0x18005dfa5`
- `credui!CredUnPackAuthenticationBufferW` at `0x18005e059`
- `credui!CredUnPackAuthenticationBufferW` at `0x18005dfa5`
- `credui!CredUnPackAuthenticationBufferW` at `0x18005e059`
- `ADVAPI32!LogonUserW` at `0x18005e07e`
- `ADVAPI32!LogonUserW` at `0x18005e07e`

## pseudocode

```c

```
