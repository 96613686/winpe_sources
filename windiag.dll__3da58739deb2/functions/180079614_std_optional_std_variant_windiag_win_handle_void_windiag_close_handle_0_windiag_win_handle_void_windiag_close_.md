# std::optional<std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>>::emplace<windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(windiag::win_handle<HKEY__ *,windiag::close_hkey,0> &&)

- ea: `0x180079614`
- end: `0x18007967c`
- name: `??$emplace@U?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@windiag@@@?$optional@V?$variant@U?$win_handle@PEAXUclose_handle@windiag@@$0A@@windiag@@U?$win_handle@PEAXUclose_handle@windiag@@$0?0@2@U?$win_handle@PEAUHINSTANCE__@@Uclose_dll@windiag@@$0A@@2@U?$win_handle@PEAUSC_HANDLE__@@Uclose_scm@windiag@@$0A@@2@U?$win_handle@PEAXUclose_hlocal@windiag@@$0A@@2@U?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@2@@std@@@std@@QEAAAEAV?$variant@U?$win_handle@PEAXUclose_handle@windiag@@$0A@@windiag@@U?$win_handle@PEAXUclose_handle@windiag@@$0?0@2@U?$win_handle@PEAUHINSTANCE__@@Uclose_dll@windiag@@$0A@@2@U?$win_handle@PEAUSC_HANDLE__@@Uclose_scm@windiag@@$0A@@2@U?$win_handle@PEAXUclose_hlocal@windiag@@$0A@@2@U?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@2@@1@$$QEAU?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@windiag@@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18007a220`

## callees

- `0x180079614`
- `0x180079814`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079658`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079658`

## pseudocode

```c

```
