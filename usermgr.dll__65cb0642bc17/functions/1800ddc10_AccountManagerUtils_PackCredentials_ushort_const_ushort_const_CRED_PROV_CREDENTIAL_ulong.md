# AccountManagerUtils::PackCredentials(ushort const *,ushort const *,_CRED_PROV_CREDENTIAL * *,ulong *)

- ea: `0x1800ddc10`
- end: `0x1800dde38`
- name: `?PackCredentials@AccountManagerUtils@@YAJPEBG0PEAPEAU_CRED_PROV_CREDENTIAL@@PEAK@Z`
- size: `552`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, const unsigned __int16 *, struct _CRED_PROV_CREDENTIAL **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800665d4`

## callees

- `0x1800088e8`
- `0x180014e7c`
- `0x180014e9c`
- `0x18006c426`
- `0x1800749bc`
- `0x1800dd768`
- `0x1800ddc10`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800ddc90`
- `msvcrt!wcsnlen` at `0x1800ddcab`
- `msvcrt!wcsnlen` at `0x1800ddc90`
- `msvcrt!wcsnlen` at `0x1800ddcab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ddcfa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ddcfa`

## string_xrefs

- `0x1800dde09`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800ddcd7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c

```
