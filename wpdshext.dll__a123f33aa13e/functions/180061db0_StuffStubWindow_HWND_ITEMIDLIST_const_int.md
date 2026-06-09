# _StuffStubWindow(HWND__ *,_ITEMIDLIST const *,int)

- ea: `0x180061db0`
- end: `0x180061e75`
- name: `?_StuffStubWindow@@YAPEAXPEAUHWND__@@PEFBU_ITEMIDLIST@@H@Z`
- size: `197`
- prototype: `void *__fastcall(HWND hWnd, const struct _ITEMIDLIST *Src, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005fdc0`

## callees

- `0x180061db0`
- `0x1800755a8`

## import_xrefs

- `SHLWAPI!__imp_SHAllocShared` at `0x180061df9`
- `SHLWAPI!__imp_SHAllocShared` at `0x180061df9`
- `SHLWAPI!__imp_SHLockShared` at `0x180061e0e`
- `SHLWAPI!__imp_SHLockShared` at `0x180061e0e`
- `SHLWAPI!__imp_SHUnlockShared` at `0x180061e34`
- `SHLWAPI!__imp_SHUnlockShared` at `0x180061e34`
- `SHLWAPI!__imp_SHFreeShared` at `0x180061e5a`
- `SHLWAPI!__imp_SHFreeShared` at `0x180061e5a`
- `USER32!SendMessageW` at `0x180061e48`
- `USER32!SendMessageW` at `0x180061e48`
- `USER32!GetWindowThreadProcessId` at `0x180061de8`
- `USER32!GetWindowThreadProcessId` at `0x180061de8`
- `SHELL32!__imp_ILGetSize` at `0x180061dd7`
- `SHELL32!__imp_ILGetSize` at `0x180061dd7`

## pseudocode

```c

```
