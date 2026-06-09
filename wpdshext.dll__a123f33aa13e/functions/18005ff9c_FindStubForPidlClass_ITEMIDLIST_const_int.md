# FindStubForPidlClass(_ITEMIDLIST const *,int)

- ea: `0x18005ff9c`
- end: `0x1800600e6`
- name: `?FindStubForPidlClass@@YAPEAUHWND__@@PEFBU_ITEMIDLIST@@H@Z`
- size: `330`
- prototype: `HWND __fastcall(LPCITEMIDLIST pidl1, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005fdc0`

## callees

- `0x180035590`
- `0x18005ff9c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180060007`
- `KERNEL32!lstrcmpiW` at `0x180060007`
- `SHLWAPI!__imp_SHLockShared` at `0x180060071`
- `SHLWAPI!__imp_SHLockShared` at `0x180060071`
- `SHLWAPI!__imp_SHUnlockShared` at `0x180060098`
- `SHLWAPI!__imp_SHUnlockShared` at `0x1800600b4`
- `SHLWAPI!__imp_SHUnlockShared` at `0x180060098`
- `SHLWAPI!__imp_SHUnlockShared` at `0x1800600b4`
- `USER32!GetWindow` at `0x1800600a6`
- `USER32!GetWindow` at `0x1800600a6`
- `USER32!GetClassNameW` at `0x18005fff5`
- `USER32!GetClassNameW` at `0x18005fff5`
- `USER32!FindWindowW` at `0x18005ffd5`
- `USER32!FindWindowW` at `0x18005ffd5`
- `USER32!GetWindowThreadProcessId` at `0x18006002a`
- `USER32!GetWindowThreadProcessId` at `0x18006002a`
- `USER32!SendMessageTimeoutW` at `0x180060058`
- `USER32!SendMessageTimeoutW` at `0x180060058`
- `SHELL32!__imp_ILIsEqual` at `0x18006008b`
- `SHELL32!__imp_ILIsEqual` at `0x18006008b`

## pseudocode

```c

```
