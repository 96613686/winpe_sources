# BlbLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x140092184`
- end: `0x1400923e9`
- name: `?BlbLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `613`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140024088`
- `0x1400257cc`
- `0x140047a50`
- `0x14005a3b8`
- `0x14007d630`
- `0x140093d00`
- `0x140096d34`
- `0x1400b9950`
- `0x14010191c`
- `0x140130e1c`

## callees

- `0x140006ca8`
- `0x14000bb4c`
- `0x140051e98`
- `0x140092184`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400923cf`
- `KERNEL32!SetLastError` at `0x1400923cf`
- `KERNEL32!GetSystemDirectoryW` at `0x1400921a5`
- `KERNEL32!GetSystemDirectoryW` at `0x14009224c`
- `KERNEL32!GetSystemDirectoryW` at `0x1400921a5`
- `KERNEL32!GetSystemDirectoryW` at `0x14009224c`
- `KERNEL32!LocalAlloc` at `0x14009222f`
- `KERNEL32!LocalAlloc` at `0x14009222f`
- `KERNEL32!LocalFree` at `0x1400923a6`
- `KERNEL32!LocalFree` at `0x1400923a6`
- `KERNEL32!LoadLibraryExW` at `0x140092326`
- `KERNEL32!LoadLibraryExW` at `0x140092326`
- `KERNEL32!GetLastError` at `0x1400921b1`
- `KERNEL32!GetLastError` at `0x140092334`
- `KERNEL32!GetLastError` at `0x140092350`
- `KERNEL32!GetLastError` at `0x1400921b1`
- `KERNEL32!GetLastError` at `0x140092334`
- `KERNEL32!GetLastError` at `0x140092350`

## pseudocode

```c

```
