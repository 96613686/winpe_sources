# SQLLicense::LoadSqlBoot(HINSTANCE__ * (*)(wchar_t const *,int,wchar_t const *,int))

- ea: `0x100449dd0`
- end: `0x100449e7e`
- name: `?LoadSqlBoot@SQLLicense@@IEAA_NP6APEAUHINSTANCE__@@PEB_WH0H@Z@Z`
- size: `174`
- prototype: `bool __fastcall(SQLLicense *__hidden this, HINSTANCE (*)(const wchar_t *, int, const wchar_t *, int))`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100448530`

## callees

- `0x100402f10`
- `0x100449dd0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100449e27`
- `KERNEL32!GetProcAddress` at `0x100449e46`
- `KERNEL32!GetProcAddress` at `0x100449e27`
- `KERNEL32!GetProcAddress` at `0x100449e46`

## string_xrefs

- `0x100449df0`: `sqlboot.dll`
- `0x100449e17`: `CreateSKUCookie`

## pseudocode

```c

```
