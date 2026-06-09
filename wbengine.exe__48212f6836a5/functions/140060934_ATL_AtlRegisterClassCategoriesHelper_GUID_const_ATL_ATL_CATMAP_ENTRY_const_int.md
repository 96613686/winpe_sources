# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x140060934`
- end: `0x140060d13`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `991`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140060650`
- `0x140067f4c`

## callees

- `0x140006ca8`
- `0x140007dec`
- `0x1400088f0`
- `0x140008d80`
- `0x140009330`
- `0x1400095d0`
- `0x140009900`
- `0x140014bc0`
- `0x140014fd8`
- `0x140060934`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x140060bc2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140060c93`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140060bc2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140060c93`
- `msvcrt!wcscat_s` at `0x140060b1d`
- `msvcrt!wcscat_s` at `0x140060b37`
- `msvcrt!wcscat_s` at `0x140060c19`
- `msvcrt!wcscat_s` at `0x140060c34`
- `msvcrt!wcscat_s` at `0x140060b1d`
- `msvcrt!wcscat_s` at `0x140060b37`
- `msvcrt!wcscat_s` at `0x140060c19`
- `msvcrt!wcscat_s` at `0x140060c34`
- `msvcrt!wcscpy_s` at `0x140060b03`
- `msvcrt!wcscpy_s` at `0x140060bfe`
- `msvcrt!wcscpy_s` at `0x140060b03`
- `msvcrt!wcscpy_s` at `0x140060bfe`
- `ole32!StringFromGUID2` at `0x140060ae7`
- `ole32!StringFromGUID2` at `0x140060ae7`
- `ole32!CoCreateInstance` at `0x1400609d7`
- `ole32!CoCreateInstance` at `0x1400609d7`

## string_xrefs

- `0x140060997`: `0 && L"Use OBJECT_ENTRY_NON_CREATEABLE_EX macro if you want to register class categories for non creatable objects."`
- `0x140060af8`: `CLSID\`
- `0x140060bf0`: `CLSID\`

## pseudocode

```c

```
