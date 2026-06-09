# CPL_SwitchToOrLaunch(HWND__ *,HINSTANCE__ *,ushort const *,int,ulong,ushort const *,ulong *,IUnknown *)

- ea: `0x18028f74c`
- end: `0x18028fced`
- name: `?CPL_SwitchToOrLaunch@@YAHPEAUHWND__@@PEAUHINSTANCE__@@PEBGHK2PEAKPEAUIUnknown@@@Z`
- size: `1441`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, HINSTANCE@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, const unsigned __int16 *, unsigned int *, struct IUnknown *)`
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18029131c`
- `0x180291480`
- `0x1802914b0`
- `0x1802914e0`

## callees

- `0x180016364`
- `0x18001aae0`
- `0x18003ef10`
- `0x1800afb90`
- `0x1801783a0`
- `0x18018b018`
- `0x180249490`
- `0x18024a53c`
- `0x18028f268`
- `0x18028f400`
- `0x18028f658`
- `0x18028f6b4`
- `0x18028f74c`
- `0x18028fcf4`
- `0x18028fe64`
- `0x180290050`
- `0x1802908c8`
- `0x18029091c`
- `0x180290cf8`
- `0x180290d5c`
- `0x180290f64`
- `0x180290ff0`
- `0x1803916e4`
- `0x18050f17c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18028fc1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18028fc1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18028fc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18028fc86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18028f896`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18028f896`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18028fc08`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18028fc57`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18028fc08`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18028fc57`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18028f8cd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18028f8ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18028f8cd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18028f8ef`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18028faca`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18028faca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18028f8b4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18028f8b4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18028f943`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18028f943`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18028f7b9`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18028f7b9`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x18028fa90`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x18028fa90`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18028f7f5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18028fb75`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18028f7f5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18028fb75`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x18028f7c9`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x18028fb2e`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x18028f7c9`
- `Windows.Storage!SHIsCurrentThreadOnUserDesktop` at `0x18028fb2e`

## string_xrefs

- `0x18028f8c3`: `rundll32.exe`

## pseudocode

```c

```
