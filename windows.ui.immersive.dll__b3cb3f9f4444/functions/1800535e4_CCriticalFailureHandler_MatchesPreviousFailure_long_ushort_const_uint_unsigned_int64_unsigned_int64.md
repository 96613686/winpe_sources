# CCriticalFailureHandler::_MatchesPreviousFailure(long,ushort const *,uint,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800535e4`
- end: `0x1800537fa`
- name: `?_MatchesPreviousFailure@CCriticalFailureHandler@@AEBA_NJPEBGIPEA_K1@Z`
- size: `534`
- prototype: `bool(CCriticalFailureHandler *__hidden this, int, const unsigned __int16 *, unsigned int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800d9e44`

## callees

- `0x180032908`
- `0x1800535e4`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800537c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800537c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053646`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053646`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800536ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800536ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053722`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053722`

## pseudocode

```c

```
