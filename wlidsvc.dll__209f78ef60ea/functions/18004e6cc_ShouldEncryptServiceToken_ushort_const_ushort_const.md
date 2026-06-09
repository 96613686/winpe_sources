# ShouldEncryptServiceToken(ushort const *,ushort const *)

- ea: `0x18004e6cc`
- end: `0x18004e767`
- name: `?ShouldEncryptServiceToken@@YA_NPEBG0@Z`
- size: `155`
- prototype: `bool __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002795c`
- `0x18009fdd0`

## callees

- `0x18004e6cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e6f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e709`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e71d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e6f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e709`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e71d`
- `ntdll!wcsstr` at `0x18004e731`
- `ntdll!wcsstr` at `0x18004e746`
- `ntdll!wcsstr` at `0x18004e731`
- `ntdll!wcsstr` at `0x18004e746`

## string_xrefs

- `0x18004e713`: `TOKEN_BROKER`

## pseudocode

```c

```
