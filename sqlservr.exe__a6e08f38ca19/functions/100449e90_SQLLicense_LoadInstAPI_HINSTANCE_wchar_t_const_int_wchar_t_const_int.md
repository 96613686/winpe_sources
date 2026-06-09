# SQLLicense::LoadInstAPI(HINSTANCE__ * (*)(wchar_t const *,int,wchar_t const *,int))

- ea: `0x100449e90`
- end: `0x100449f3e`
- name: `?LoadInstAPI@SQLLicense@@IEAA_NP6APEAUHINSTANCE__@@PEB_WH0H@Z@Z`
- size: `174`
- prototype: `bool __fastcall(SQLLicense *__hidden this, HINSTANCE (*)(const wchar_t *, int, const wchar_t *, int))`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x100448530`

## callees

- `0x100402f10`
- `0x100449e90`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100449ee7`
- `KERNEL32!GetProcAddress` at `0x100449f06`
- `KERNEL32!GetProcAddress` at `0x100449ee7`
- `KERNEL32!GetProcAddress` at `0x100449f06`

## string_xrefs

- `0x100449ed7`: `GetInstRegPathByID`
- `0x100449eb0`: `instapi160.dll`
- `0x100449ef6`: `GetInstanceIDFromService`

## pseudocode

```c

```
