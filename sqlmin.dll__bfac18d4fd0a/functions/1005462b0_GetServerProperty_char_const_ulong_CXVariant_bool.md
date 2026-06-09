# GetServerProperty(char const *,ulong,CXVariant *,bool)

- ea: `0x1005462b0`
- end: `0x100546640`
- name: `?GetServerProperty@@YAXPEBDKPEAVCXVariant@@_N@Z`
- size: `912`
- prototype: `void __fastcall(const char *, unsigned int, struct CXVariant *, bool)`
- caller_count: `5`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x100546230`
- `0x1009df630`
- `0x100a4e660`
- `0x100a4e6e0`
- `0x1023adb40`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x1004025c0`
- `0x100402920`
- `0x10040da80`
- `0x10040fc00`
- `0x100418690`
- `0x10041b5d0`
- `0x10041e3e0`
- `0x10042b3d0`
- `0x100433170`
- `0x10047bc10`
- `0x1004b4d70`
- `0x1004e8470`
- `0x100546110`
- `0x1005462b0`
- `0x10056afe0`
- `0x10056b280`
- `0x10056b530`
- `0x100623200`
- `0x100624b90`
- `0x100625030`
- `0x10073aa00`
- `0x1007864d0`
- `0x100a51c80`
- `0x100a52830`
- `0x100a52b30`
- `0x101b8fa60`
- `0x102221670`
- `0x1022e24f0`
- `0x1022e3bd0`
- `0x1023ac950`

## import_xrefs

- `Secur32!GetUserNameExW` at `0x100a4df4d`
- `Secur32!GetUserNameExW` at `0x100a4e011`
- `Secur32!GetUserNameExW` at `0x100a4df4d`
- `Secur32!GetUserNameExW` at `0x100a4e011`
- `KERNEL32!GetEnvironmentVariableW` at `0x100a4e458`
- `KERNEL32!GetEnvironmentVariableW` at `0x100a4e458`
- `KERNEL32!GetCurrentProcessId` at `0x100a4c667`
- `KERNEL32!GetCurrentProcessId` at `0x100a4c667`
- `KERNEL32!GetComputerNameExW` at `0x100a4c4ea`
- `KERNEL32!GetComputerNameExW` at `0x100a4c5ac`
- `KERNEL32!GetComputerNameExW` at `0x100a4c4ea`
- `KERNEL32!GetComputerNameExW` at `0x100a4c5ac`
- `KERNEL32!GetComputerNameW` at `0x100a4c65a`
- `KERNEL32!GetComputerNameW` at `0x100a4c65a`
- `KERNEL32!GetLastError` at `0x100a4df5b`
- `KERNEL32!GetLastError` at `0x100a4df5b`
- `svl!SvlPathGetDefaultPathSeparator` at `0x100a4e3da`
- `svl!SvlPathGetDefaultPathSeparator` at `0x100a4e3da`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100546300`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100546320`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100a4d773`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100a4dbdf`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100546300`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100546320`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100a4d773`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100a4dbdf`
- `sqlTsEs!?LCIDFromCID@@YAKK@Z` at `0x100a4c880`
- `sqlTsEs!?LCIDFromCID@@YAKK@Z` at `0x100a4c880`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x100a4c92f`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x100a4c92f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x1005463fd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c277`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c2cc`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c380`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c409`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c47c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c4b1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c527`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c5eb`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c679`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c6db`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c703`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c751`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c7c8`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c81c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c892`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c901`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c945`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c9b1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c9f6`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ca2e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4caa6`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4caeb`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cb2a`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cb61`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cbc9`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cc7a`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cd49`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ce0f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ce4f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cec8`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cf49`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cfe1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d020`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d098`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d313`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d39c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d3bf`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d5ad`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d5ee`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d737`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d7ce`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d895`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d94c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4db4f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dc0b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dc7d`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dce3`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dd1e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dd8f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ddc4`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4de06`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4de41`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dee0`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e04b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e0cd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e14f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e208`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e33b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e3ae`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e40e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e473`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e4fc`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e52f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e58b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e5b9`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e5fd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e634`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x1005463fd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c277`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c2cc`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c380`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c409`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c47c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c4b1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c527`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c5eb`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c679`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c6db`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c703`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c751`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c7c8`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c81c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c892`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c901`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c945`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c9b1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4c9f6`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ca2e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4caa6`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4caeb`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cb2a`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cb61`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cbc9`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cc7a`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cd49`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ce0f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ce4f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cec8`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cf49`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4cfe1`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d020`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d098`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d313`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d39c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d3bf`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d5ad`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d5ee`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d737`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d7ce`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d895`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4d94c`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4db4f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dc0b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dc7d`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dce3`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dd1e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dd8f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4ddc4`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4de06`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4de41`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4dee0`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e04b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e0cd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e14f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e208`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e33b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e3ae`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e40e`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e473`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e4fc`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e52f`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e58b`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e5b9`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e5fd`
- `sqlTsEs!?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z` at `0x100a4e634`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x100a4c7b5`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x100a4c7f1`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x100a4c7b5`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x100a4c7f1`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4c20b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4c22f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4c27d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4c69f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4d4c1`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4d4dd`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4d717`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100a4de74`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100a4d79d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4d838`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4daf4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4e179`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4e295`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4d838`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4daf4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4e179`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100a4e295`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100a4dfe3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100a4e285`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100a4dfe3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100a4e285`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100a4dbb1`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100a4dbb1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c2fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c3b0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c439`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c554`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c61b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c781`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100a4c84c`

## string_xrefs

- `0x100a4e2aa`: `%ls\Polybase\Configuration`
- `0x100a4e37f`: `Compute`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall GetServerProperty(const char *a1, int a2, struct CXVariant *a3, char a4)
{
  unsigned int v8; // edi
  _DWORD *v9; // r9
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  BOOL v13; // esi
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdi
  const unsigned __int8 *v19; // rax
  __int64 v20; // rdi
  size_t v21; // rdi
  unsigned __int8 *v22; // rax
  __int64 v23; // rdi
  unsigned __int8 *v24; // rax
  __int64 v25; // rdi
  size_t v26; // rdi
  unsigned __int8 *v27; // rax
  BOOL v28; // ebx
  BOOL v29; // ebx
  __int64 v30; // rdi
  size_t v31; // rdi
  unsigned __int8 *v32; // rax
  BOOL ComputerName; // eax
  __int64 v34; // rdi
  size_t v35; // rdi
  unsigned __int8 *v36; // rax
  DWORD CurrentProcessId; // ebx
  const wchar_t *v38; // rbx
  bool v39; // cc
  unsigned __int8 *v40; // rax
  unsigned __int8 v41; // bl
  unsigned __int8 v42; // al
  unsigned __int8 *v43; // rax
  unsigned int v44; // ebx
  int v45; // edx
  int v46; // ecx
  int v47; // edx
  int v48; // ebx
  size_t v49; // rdi
  unsigned __int8 *v50; // rax
  BOOL v51; // esi
  int v52; // ebx
  int v53; // ebx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  char v57; // al
  BOOL v58; // ebx
  BOOL v59; // ebx
  int v60; // ebx
  unsigned __int8 v61; // di
  int v62; // eax
  _QWORD *v63; // rdi
  bool v64; // zf
  _QWORD *v65; // rcx
  unsigned __int8 v66; // di
  int v67; // eax
  _QWORD *v68; // rdi
  _QWORD *v69; // rcx
  unsigned __int8 v70; // di
  int v71; // eax
  _QWORD *v72; // rdi
  _QWORD *v73; // rcx
  int v74; // ebx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  int v78; // r14d
  BOOL v79; // esi
  const wchar_t *v80; // rbx
  __int64 v81; // rdi
  BOOL v82; // esi
  wchar_t *v83; // rbx
  __int64 v84; // rdi
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rcx
  wchar_t *v96; // rax
  const unsigned __int8 *v97; // rsi
  __int64 v98; // rdi
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rdi
  unsigned __int8 *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rdi
  int v108; // ebx
  _DWORD *v109; // r9
  unsigned __int16 MasterDbId; // ax
  __int64 v111; // rax
  __int64 FCB; // rbx
  const unsigned __int8 *v113; // rdx
  __int64 v114; // rdi
  __int64 v115; // rax
  int v116; // ecx
  int v117; // esi
  int v118; // edi
  int v119; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v121; // rdi
  unsigned int v122; // edi
  unsigned __int8 *v123; // rax
  __int64 v124; // r8
  _QWORD *v125; // rdi
  char v126; // dl
  __int64 v127; // rax
  struct __crt_locale_pointers *v128; // rax
  __int64 v129; // rdi
  size_t v130; // rdi
  unsigned __int8 *v131; // rax
  struct IErrorReportingManager *ErrorReportingManager; // rax
  _DWORD *v133; // r9
  char v134; // al
  int v135; // edi
  char v136; // al
  int v137; // edi
  unsigned int v138; // edi
  unsigned __int8 *v139; // rax
  __int64 v140; // rbx
  BOOL v141; // ebx
  BOOL v142; // edi
  unsigned __int8 *v143; // rbx
  unsigned __int8 *v144; // rdi
  __int64 v145; // rdi
  __int64 v146; // rax
  struct IMemObj *v147; // r10
  unsigned __int64 v148; // rax
  unsigned __int8 *v149; // r12
  ULONG v150; // esi
  __int64 v151; // rdx
  __int64 v152; // rcx
  BOOL v153; // ebx
  __int64 v154; // rdx
  __int64 v155; // rcx
  BOOL IsPolybaseProvisioned; // ebx
  struct __crt_locale_pointers *v157; // rax
  __int64 v158; // rbx
  __int64 v159; // rdx
  wchar_t *v160; // r14
  struct __crt_locale_pointers *v161; // rax
  const unsigned __int8 *v162; // rbx
  __int64 v163; // rdi
  int v164; // ebx
  unsigned __int8 *v165; // rax
  __int64 v166; // rdi
  unsigned int v167; // edi
  unsigned __int8 *v168; // rax
  BOOL v169; // ebx
  char ControllerEndpoint; // al
  unsigned __int8 *v171; // rbx
  __int64 v172; // rdi
  int v173; // ebx
  BOOL v174; // ebx
  signed __int32 v175[8]; // [rsp+0h] [rbp-100h] BYREF
  LPBYTE v176; // [rsp+20h] [rbp-E0h]
  LPDWORD v177; // [rsp+28h] [rbp-D8h]
  __int64 v178; // [rsp+30h] [rbp-D0h]
  unsigned int Size; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Size_4[2]; // [rsp+44h] [rbp-BCh] BYREF
  _WORD v181[2]; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v182; // [rsp+4Ch] [rbp-B4h] BYREF
  __int128 v183; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v184; // [rsp+60h] [rbp-A0h]
  wchar_t String; // [rsp+70h] [rbp-90h] BYREF
  DWORD v186; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v187; // [rsp+7Ch] [rbp-84h] BYREF
  BYTE v188[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v189; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v190; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v191; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v192; // [rsp+90h] [rbp-70h] BYREF
  DWORD nSize; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v194; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v195; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v196; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v197; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v198; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v199; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v200; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v201; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v202; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v203; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v204; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v205; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v206; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v207; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v208; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v209; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned int v210; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v211; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int v212; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v213; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v214; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v215; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v216; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v217; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v218; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v219; // [rsp+FCh] [rbp-4h] BYREF
  int v220; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v221; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v222; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v223; // [rsp+10Ch] [rbp+Ch] BYREF
  unsigned int v224; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v225; // [rsp+114h] [rbp+14h] BYREF
  unsigned int v226; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v227; // [rsp+11Ch] [rbp+1Ch] BYREF
  unsigned int v228; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v229; // [rsp+124h] [rbp+24h] BYREF
  unsigned int v230; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v231; // [rsp+12Ch] [rbp+2Ch] BYREF
  unsigned int v232; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v233; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v234; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v235; // [rsp+13Ch] [rbp+3Ch] BYREF
  unsigned int v236; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v237; // [rsp+144h] [rbp+44h] BYREF
  DWORD v238; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v239; // [rsp+14Ch] [rbp+4Ch] BYREF
  unsigned int v240; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v241; // [rsp+154h] [rbp+54h] BYREF
  unsigned int v242; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v243; // [rsp+15Ch] [rbp+5Ch] BYREF
  unsigned int v244; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v245; // [rsp+164h] [rbp+64h] BYREF
  unsigned int v246; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v247; // [rsp+16Ch] [rbp+6Ch] BYREF
  _QWORD *v248; // [rsp+170h] [rbp+70h] BYREF
  int v249; // [rsp+178h] [rbp+78h]
  _QWORD *v250; // [rsp+180h] [rbp+80h] BYREF
  int v251; // [rsp+188h] [rbp+88h]
  _QWORD *v252; // [rsp+190h] [rbp+90h] BYREF
  int v253; // [rsp+198h] [rbp+98h]
  unsigned __int8 *v254; // [rsp+1A0h] [rbp+A0h]
  unsigned __int8 *v255; // [rsp+1A8h] [rbp+A8h]
  unsigned __int8 *v256; // [rsp+1B0h] [rbp+B0h] BYREF
  HKEY v257; // [rsp+1B8h] [rbp+B8h] BYREF
  wchar_t *Context; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD *v259; // [rsp+1D0h] [rbp+D0h] BYREF
  HKEY v260; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v261; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v262; // [rsp+1F0h] [rbp+F0h]
  __int128 v263; // [rsp+200h] [rbp+100h] BYREF
  __int128 v264; // [rsp+210h] [rbp+110h]
  __int64 v265; // [rsp+220h] [rbp+120h]
  wchar_t *v266; // [rsp+228h] [rbp+128h]
  int v267; // [rsp+230h] [rbp+130h] BYREF
  __int64 v268; // [rsp+238h] [rbp+138h] BYREF
  char v269; // [rsp+240h] [rbp+140h]
  int v270; // [rsp+244h] [rbp+144h]
  __int128 v271; // [rsp+250h] [rbp+150h]
  __int64 v272; // [rsp+260h] [rbp+160h]
  int v273; // [rsp+268h] [rbp+168h]
  _BYTE v274[168]; // [rsp+270h] [rbp+170h] BYREF
  int v275; // [rsp+318h] [rbp+218h]
  _BYTE v276[12288]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v277; // [rsp+3320h] [rbp+3220h]
  int v278; // [rsp+3328h] [rbp+3228h]
  unsigned __int8 v279; // [rsp+3871h] [rbp+3771h]
  _BYTE v280[12288]; // [rsp+3880h] [rbp+3780h] BYREF
  __int64 v281; // [rsp+6880h] [rbp+6780h]
  int v282; // [rsp+6888h] [rbp+6788h]
  unsigned __int8 v283; // [rsp+6DD2h] [rbp+6CD2h]
  _BYTE v284[12288]; // [rsp+6DE0h] [rbp+6CE0h] BYREF
  __int64 v285; // [rsp+9DE0h] [rbp+9CE0h]
  int v286; // [rsp+9DE8h] [rbp+9CE8h]
  unsigned __int8 v287; // [rsp+A333h] [rbp+A233h]
  wchar_t Buffer[128]; // [rsp+A340h] [rbp+A240h] BYREF
  __int16 v289; // [rsp+A440h] [rbp+A340h]
  wchar_t Src[264]; // [rsp+A450h] [rbp+A350h] BYREF
  WCHAR v291[264]; // [rsp+A660h] [rbp+A560h] BYREF
  wchar_t v292[264]; // [rsp+A870h] [rbp+A770h] BYREF

  v265 = -2;
  Size = 256;
  v8 = *(_DWORD *)CDefaultCollation::PDCServer();
  v183 = CTypeInfo::tiSSWName;
  v184 = xmmword_1031D5B70;
  CDefaultCollation::PDCServer();
  if ( CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v183) )
    DWORD1(v184) = *v9;
  *(_BYTE *)a3 = 3;
  if ( (unsigned int)(a2 - 1) <= 0xFF )
  {
    _mm_lfence();
    v12 = LookupProperty((const struct SysProp *)&x_rgspServerProperty, 75, a1, a2);
    if ( v12 )
    {
      if ( !a4 )
      {
        if ( dword_1031852C8 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v11 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
          if ( (*(_BYTE *)(v11 + 270) & 2) == 0 )
          {
            switch ( v12 )
            {
              case 1:
              case 2:
              case 4:
              case 5:
              case 22:
              case 25:
              case 32:
              case 34:
              case 37:
              case 43:
              case 44:
              case 48:
                return;
              default:
                break;
            }
          }
        }
        else if ( dword_103172528 && (byte_1031852E9 || byte_1031852E8) && !byte_1031852E4 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v11 = SystemThread_TlsIndex;
          if ( *(_QWORD *)(SystemThread_TlsOffset + ThreadLocalStoragePointer[SystemThread_TlsIndex]) )
          {
            v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset)
                            + 72LL);
            if ( (*(_BYTE *)(v11 + 270) & 2) == 0 )
            {
              switch ( v12 )
              {
                case 1:
                case 2:
                case 4:
                case 5:
                case 6:
                case 7:
                case 8:
                case 9:
                case 25:
                case 32:
                case 34:
                case 37:
                case 43:
                case 44:
                case 48:
                  return;
                default:
                  break;
              }
            }
          }
        }
        else if ( dword_103184474 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v11 = SystemThread_TlsIndex;
          if ( *(_QWORD *)(SystemThread_TlsOffset + ThreadLocalStoragePointer[SystemThread_TlsIndex])
            && (unsigned __int8)ContextAccessor::FSQLFilterLevelBasic(
                                  *(_QWORD *)(SystemThread_TlsOffset
                                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)),
                                  3) )
          {
            switch ( v12 )
            {
              case 3:
              case 10:
              case 11:
              case 12:
              case 13:
              case 14:
              case 15:
              case 16:
              case 17:
              case 18:
              case 19:
              case 20:
              case 21:
              case 23:
              case 24:
              case 26:
              case 27:
              case 28:
              case 30:
              case 31:
              case 35:
              case 36:
              case 38:
              case 39:
              case 46:
              case 47:
              case 49:
              case 50:
              case 51:
              case 52:
              case 53:
              case 54:
              case 55:
              case 56:
              case 57:
              case 58:
              case 59:
              case 60:
              case 61:
              case 67:
              case 71:
                break;
              default:
                return;
            }
          }
        }
        else if ( !dword_103172528 )
        {
          if ( v12 == 43 )
            return;
          if ( v12 == 44 )
            return;
          v11 = (unsigned int)(v12 - 48);
          if ( v12 == 48 || v12 == 67 )
            return;
        }
      }
      switch ( v12 )
      {
        case 1:
          v28 = dword_103172568 != 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v191) = v28;
          v14 = *((_DWORD *)a3 + 4) - v191;
          goto LABEL_18;
        case 2:
          CurrentProcessId = GetCurrentProcessId();
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v196) = CurrentProcessId;
          v14 = *((_DWORD *)a3 + 4) - v196;
          goto LABEL_18;
        case 3:
          v187 = 0;
          v38 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *, unsigned int *, _QWORD))(*(_QWORD *)s_pServerConf + 200LL))(
                                   s_pServerConf,
                                   &v187,
                                   0);
          Size = v187;
          v39 = v187 - 1 <= 0xFF;
          goto LABEL_74;
        case 4:
          nSize = 129;
          if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize) )
            return;
          v289 = 0;
          v30 = -1;
          do
            ++v30;
          while ( Buffer[v30] );
          Size = 2 * v30;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v31 = (unsigned int)(2 * v30);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v32 = CXVariantBase::SsVarPbDataVal(a3, &v194);
          memmove(v32, Buffer, v31);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v31 - v194;
          goto LABEL_19;
        case 5:
          if ( !dword_103172550 )
          {
            v16 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
            if ( (unsigned int)IsDefaultInstanceName(v16) )
              return;
          }
          v17 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v17 + 2 * v18) );
          Size = 2 * v18;
          if ( (unsigned int)(2 * v18 - 1) > 0xFF )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v19 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf
                                                                                                  + 224LL))(s_pServerConf);
          CXVariantBase::SsVarCopyDataValFromPb(a3, v19, Size);
          goto LABEL_20;
        case 6:
        case 8:
          v20 = -1;
          do
            ++v20;
          while ( *(&pszSrch + v20) );
          Size = 2 * v20;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v21 = (unsigned int)(2 * v20);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v22 = CXVariantBase::SsVarPbDataVal(a3, &v247);
          memmove(v22, &pszSrch, v21);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v21 - v247;
          goto LABEL_19;
        case 7:
          memset_0(Src, 0, 0x20Au);
          GetDefaultBackupPath(Src, 0x105u);
          v23 = -1;
          do
            ++v23;
          while ( Src[v23] );
          Size = 2 * v23;
          if ( 2 * (int)v23 <= 0 )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v24 = CXVariantBase::SsVarPbDataVal(a3, &v189);
          memmove(v24, Src, Size);
          v15 = *((_DWORD *)a3 + 4) + Size - v189;
          goto LABEL_19;
        case 9:
          v25 = -1;
          do
            ++v25;
          while ( *((_WORD *)qword_1033C2940 + v25) );
          Size = 2 * v25;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v26 = (unsigned int)(2 * v25);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v27 = CXVariantBase::SsVarPbDataVal(a3, &v190);
          memmove(v27, qword_1033C2940, v26);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v26 - v190;
          goto LABEL_19;
        case 10:
          if ( !FGetCollationName(v8, Buffer, (int *)&Size) )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v49 = Size;
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v50 = CXVariantBase::SsVarPbDataVal(a3, &v203);
          memmove(v50, Buffer, v49);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v49 - v203;
          goto LABEL_19;
        case 11:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v204) = v8;
          v14 = *((_DWORD *)a3 + 4) - v204;
          goto LABEL_18;
        case 12:
          v51 = FIsFulltextInstalled() && !dword_103172554;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v205) = v51;
          v14 = *((_DWORD *)a3 + 4) - v205;
          goto LABEL_18;
        case 13:
          v44 = LCIDFromCID(v8);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v201) = v44;
          v14 = *((_DWORD *)a3 + 4) - v201;
          goto LABEL_18;
        case 14:
          v45 = (v8 >> 12) & 1 | 2;
          if ( (v8 & 0x2000) == 0 )
            v45 = (v8 >> 12) & 1;
          v46 = v45 | 0x10000;
          if ( (v8 & 0x4000) == 0 )
            v46 = v45;
          v47 = v46 | 0x20000;
          if ( (v8 & 0x8000) == 0 )
            v47 = v46;
          v48 = v47 | 8;
          if ( (v8 & 0x200) == 0 )
            v48 = v47;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v202) = v48;
          v14 = *((_DWORD *)a3 + 4) - v202;
          goto LABEL_18;
        case 15:
          v41 = CSIDFromCID(v8);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiUI1);
          *CXVariantBase::SsVarPbDataVal(a3, &v199) = v41;
          v15 = *((_DWORD *)a3 + 4) - v199 + 1;
          goto LABEL_19;
        case 16:
          v42 = CSIDFromCID(v8);
          Size = getcssoname(v42, 1001, Buffer, 258);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v43 = CXVariantBase::SsVarPbDataVal(a3, &v200);
          memmove(v43, Buffer, Size);
          v15 = *((_DWORD *)a3 + 4) + Size - v200;
          goto LABEL_19;
        case 17:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiUI1);
          *CXVariantBase::SsVarPbDataVal(a3, &v197) = HIBYTE(v8);
          v15 = *((_DWORD *)a3 + 4) - v197 + 1;
          goto LABEL_19;
        case 18:
          Size = getcssoname(HIBYTE(v8), 2001, Buffer, 258);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v40 = CXVariantBase::SsVarPbDataVal(a3, &v198);
          memmove(v40, Buffer, Size);
          v15 = *((_DWORD *)a3 + 4) + Size - v198;
          goto LABEL_19;
        case 19:
          v79 = dword_103171A60 == 1
             && !(unsigned __int8)ContextAccessor::FSQLFilterLevelBasic(
                                    *(_QWORD *)(SystemThread_TlsOffset
                                              + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)),
                                    3);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v216) = v79;
          v14 = *((_DWORD *)a3 + 4) - v216;
          goto LABEL_18;
        case 20:
          v80 = 0;
          if ( (unsigned __int8)ContextAccessor::FSQLFilterLevelBasic(
                                  *(_QWORD *)(SystemThread_TlsOffset
                                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)),
                                  3)
            || dword_103171E00 == -1 )
          {
            v80 = L"DISABLED";
          }
          else if ( dword_103171E00 )
          {
            if ( dword_103171E00 == 2 )
              v80 = L"PER_PROCESSOR";
          }
          else
          {
            v80 = L"PER_SEAT";
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v81 = -1;
          do
            ++v81;
          while ( v80[v81] );
          goto LABEL_157;
        case 21:
          v82 = (dword_10316ECB0 & 1) != 0
             && !(unsigned __int8)ContextAccessor::FSQLFilterLevelBasic(
                                    *(_QWORD *)(SystemThread_TlsOffset
                                              + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)),
                                    3);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v217) = v82;
          v14 = *((_DWORD *)a3 + 4) - v217;
          goto LABEL_18;
        case 22:
          if ( dword_103171E00 == -1 )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v218) = dword_103171E04;
          v14 = *((_DWORD *)a3 + 4) - v218;
          goto LABEL_18;
        case 23:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v99 = 8LL * SystemThread_TlsIndex;
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v99)
                                                 + SystemThread_TlsOffset)
                                     + 72LL)
                         + 270LL)
              & 4) != 0
            || dword_103172528 && (byte_1031852E9 || byte_1031852E8) && !byte_1031852E4
            || (v100 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                               + SystemThread_TlsIndex)
                                             + SystemThread_TlsOffset)
                                 + 72LL),
                (*(_BYTE *)(v100 + 270) & 8) != 0)
            || *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v100, v99) + 478)
            && dword_1031852C8
            && !byte_1031852D8
            || !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v102, v101) + 478) && dword_1031852C8 )
          {
            Size = 22;
            CXVariantBase::SsVarCopyDataValFromPb(a3, L"12.0.2000.8", 0x16u);
          }
          else
          {
            Size = 22;
            CXVariantBase::SsVarCopyDataValFromPb(a3, L"16.0.1000.6", 0x16u);
          }
          goto LABEL_20;
        case 24:
          v83 = (wchar_t *)L"RTM";
          if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v11, ThreadLocalStoragePointer) + 478)
            && dword_1031852C8
            && !byte_1031852D8 )
          {
            v83 = L"GA";
          }
          v84 = -1;
          do
            ++v84;
          while ( v83[v84] );
          goto LABEL_173;
        case 25:
          v108 = *(_DWORD *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                           + 12);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v222) = v108;
          v14 = *((_DWORD *)a3 + 4) - v222;
          goto LABEL_18;
        case 26:
          if ( !(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 280LL))(s_pServerConf) )
            return;
          v38 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf
                                                                                          + 280LL))(s_pServerConf);
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 72LL)
                         + 270LL)
              & 4) != 0
            || dword_1031852C8
            || dword_103172528 && (byte_1031852E9 || byte_1031852E8) && !byte_1031852E4
            || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex)
                                                 + SystemThread_TlsOffset)
                                     + 72LL)
                         + 270LL)
              & 8) != 0 )
          {
            v38 = L"SQL Azure";
          }
          v103 = -1;
          do
            ++v103;
          while ( v38[v103] );
          Size = 2 * v103;
          v39 = (unsigned int)(2 * v103 - 1) <= 0xFF;
LABEL_74:
          if ( v39 )
            goto LABEL_75;
          return;
        case 27:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v219) = dword_103171A5C;
          v14 = *((_DWORD *)a3 + 4) - v219;
          goto LABEL_18;
        case 28:
          if ( !(unsigned int)GetSpEngineEdition(&v220) )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          v104 = CXVariantBase::SsVarPbDataVal(a3, &v221);
          *(_DWORD *)v104 = v220;
          v14 = *((_DWORD *)a3 + 4) - v221;
          goto LABEL_18;
        case 29:
          v261 = CTypeInfo::tiMaxPathName;
          v262 = xmmword_103369680;
          CDefaultCollation::PDCServer();
          if ( CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v261) )
            DWORD1(v262) = *v109;
          MasterDbId = GetMasterDbId();
          v111 = g_dbtableFactory[4](MasterDbId);
          FCB = FileMgr::GetFCB(*(_QWORD *)(*(_QWORD *)(v111 + 4624) + 1696LL), 1, 0);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v261);
          v113 = (const unsigned __int8 *)(FCB + 2368);
          v114 = -1;
          do
            ++v114;
          while ( *(_WORD *)&v113[2 * v114] );
          CXVariantBase::SsVarCopyDataValFromPb(a3, v113, (unsigned int)(2 * v114));
          goto LABEL_20;
        case 30:
          v115 = *((_QWORD *)qword_10316ECA0 + 11);
          if ( !v115 )
            return;
          v116 = *(_DWORD *)(*(_QWORD *)(v115 + 4624) + 1668LL);
          v117 = (unsigned __int16)v116;
          v118 = BYTE2(v116);
          v119 = HIBYTE(v116);
          DefaultLocale = GetDefaultLocale();
          LODWORD(v178) = v117;
          LODWORD(v177) = v118;
          LODWORD(v176) = v119;
          if ( (int)StringCchPrintf_lW(
                      Buffer,
                      (unsigned int)((unsigned __int64)(int)Size >> 1),
                      L"%d.%02d.%d",
                      DefaultLocale,
                      v176,
                      v177,
                      v178) < 0 )
          {
            v122 = 0;
          }
          else
          {
            v121 = -1;
            do
              ++v121;
            while ( Buffer[v121] );
            v122 = 2 * v121;
          }
          Size = v122;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          if ( v122 > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v123 = CXVariantBase::SsVarPbDataVal(a3, &v223);
          memmove(v123, Buffer, v122);
          v15 = *((_DWORD *)a3 + 4) + v122 - v223;
          goto LABEL_19;
        case 31:
          v124 = *((_QWORD *)qword_10316ECA0 + 11);
          if ( !v124 )
            return;
          if ( (*(_DWORD *)(v124 + 632) & 0x400) != 0 )
          {
            v267 = 0;
            v268 = 0;
            v269 = 0;
            v270 = 0;
            v272 = 0;
            v273 = 0;
            v271 = 0;
            BootPagePtr::Init(&v267, 0, *(_QWORD *)(v124 + 4624), 0);
            BootPagePtr::GetAccess(&v267, 2);
            v126 = v267;
            if ( (v267 & 1) != 0 )
              v127 = v271;
            else
              v127 = *(_QWORD *)v268 + *(unsigned __int16 *)(*(_QWORD *)v268 + 8190LL);
            v125 = (_QWORD *)(v127 + 676);
            if ( v127 == -676 )
            {
              *_errno() = 22;
              _invalid_parameter_noinfo();
              v126 = v267;
            }
            else
            {
              v125 = (_QWORD *)*v125;
            }
            if ( (v126 & 1) == 0 )
            {
              PageRef::Unlatch((PageRef *)&v268);
              if ( (_QWORD)v271 )
              {
                operator delete((void *)v271, 0x6FAu);
                *(_QWORD *)&v271 = 0;
              }
            }
            BootPagePtr::Release((BootPagePtr *)&v267, 0);
            if ( v268 || (v267 & 1) != 0 )
            {
              if ( (v267 & 1) == 0 )
              {
                PageRef::Unlatch((PageRef *)&v268);
                if ( (_QWORD)v271 )
                {
                  operator delete((void *)v271, 0x6FAu);
                  *(_QWORD *)&v271 = 0;
                }
              }
              BootPagePtr::Release((BootPagePtr *)&v267, 0);
            }
            if ( (_QWORD)v271 )
            {
              operator delete((void *)v271, 0x6FAu);
              *(_QWORD *)&v271 = 0;
            }
            PageRef::~PageRef((PageRef *)&v268);
          }
          else
          {
            utgettime((struct SQLDATEBASE *)&v259, 0, 0);
            v125 = v259;
          }
          if ( !v125 )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiDate);
          *(_QWORD *)CXVariantBase::SsVarPbDataVal(a3, &v224) = v125;
          v15 = *((_DWORD *)a3 + 4) - v224 + 8;
          goto LABEL_19;
        case 32:
          v186 = 129;
          if ( dword_103172568 )
            ComputerName = GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &v186);
          else
            ComputerName = GetComputerNameW(Buffer, &v186);
          if ( !ComputerName )
            return;
          v289 = 0;
          v34 = -1;
          do
            ++v34;
          while ( Buffer[v34] );
          Size = 2 * v34;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v35 = (unsigned int)(2 * v34);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v36 = CXVariantBase::SsVarPbDataVal(a3, &v195);
          memmove(v36, Buffer, v35);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v35 - v195;
          goto LABEL_19;
        case 33:
          v128 = GetDefaultLocale();
          LODWORD(v178) = 30319;
          LODWORD(v176) = 4;
          StringCchPrintf_lW(Buffer, 0x1Eu, L"v%d.%d.%d", v128, v176, 0, v178);
          v129 = -1;
          do
            ++v129;
          while ( Buffer[v129] );
          Size = 2 * v129;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v130 = (unsigned int)(2 * v129);
          if ( Size > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v131 = CXVariantBase::SsVarPbDataVal(a3, &v225);
          memmove(v131, Buffer, v130);
          v15 = *((_DWORD *)a3 + 4) + (unsigned int)v130 - v225;
          goto LABEL_19;
        case 34:
          ErrorReportingManager = GetErrorReportingManager();
          v80 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IErrorReportingManager *))(*(_QWORD *)ErrorReportingManager
                                                                                            + 56LL))(ErrorReportingManager);
          v263 = CTypeInfo::tiMaxPathName;
          v264 = xmmword_103369680;
          CDefaultCollation::PDCServer();
          if ( CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v263) )
            DWORD1(v264) = *v133;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v263);
          v81 = -1;
          do
            ++v81;
          while ( v80[v81] );
LABEL_157:
          CXVariantBase::SsVarCopyDataValFromPb(a3, (const unsigned __int8 *)v80, (unsigned int)(2 * v81));
          goto LABEL_20;
        case 35:
        case 36:
        case 56:
          return;
        case 37:
          CFilestreamFeatureState::GetShareName(
            (CFilestreamFeatureState *)qword_103171C80,
            (struct FSTR_SHARENAME *)v274);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v138 = 2 * v275;
          if ( (unsigned int)(2 * v275) > 0x1F40 )
            utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
          v139 = CXVariantBase::SsVarPbDataVal(a3, &v228);
          memmove(v139, v274, v138);
          v15 = *((_DWORD *)a3 + 4) + v138 - v228;
          goto LABEL_19;
        case 38:
          v136 = ContextAccessor::FSQLFilterLevelBasic(
                   *(_QWORD *)(SystemThread_TlsOffset
                             + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)),
                   3);
          v137 = dword_103171DD0;
          if ( v136 )
            v137 = 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v227) = v137;
          v14 = *((_DWORD *)a3 + 4) - v227;
          goto LABEL_18;
        case 39:
          v134 = ContextAccessor::FSQLFilterLevelBasic(
                   *(_QWORD *)(SystemThread_TlsOffset
                             + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)),
                   3);
          v135 = dword_103171CD8;
          if ( v134 )
            v135 = 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v226) = v135;
          v14 = *((_DWORD *)a3 + 4) - v226;
          goto LABEL_18;
        case 40:
          v29 = dword_103172558 != 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v192) = v29;
          v14 = *((_DWORD *)a3 + 4) - v192;
          goto LABEL_18;
        case 41:
          v52 = dword_103334C50;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v206) = v52;
          v14 = *((_DWORD *)a3 + 4) - v206;
          goto LABEL_18;
        case 42:
          if ( CHadrArManager::s_pArManager )
            v78 = *((_DWORD *)CHadrArManager::s_pArManager + 516);
          else
            v78 = 2;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v215) = v78;
          v14 = *((_DWORD *)a3 + 4) - v215;
          goto LABEL_18;
        case 43:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiDate);
          *(_QWORD *)CXVariantBase::SsVarPbDataVal(a3, &v229) = qword_103172680;
          v15 = *((_DWORD *)a3 + 4) - v229 + 8;
          goto LABEL_19;
        case 44:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiDate);
          v140 = StartUp::sm_sdServerStartTimeUtc;
          *(_QWORD *)CXVariantBase::SsVarPbDataVal(a3, &v230) = v140;
          v15 = *((_DWORD *)a3 + 4) - v230 + 8;
          goto LABEL_19;
        case 45:
          if ( !dword_103172520 )
            return;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v231) = 1;
          v14 = *((_DWORD *)a3 + 4) - v231;
          goto LABEL_18;
        case 46:
          v141 = IsMiaaInstance();
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v232) = v141;
          v14 = *((_DWORD *)a3 + 4) - v232;
          goto LABEL_18;
        case 47:
          v142 = dword_103172538
              || *((_BYTE *)s_pServerConf + 17)
              && !dword_10316ECB4
              && !dword_10317253C
              && !dword_103172574
              && (!dword_103185704 || !dword_103172528);
          if ( !dword_103172528 )
            goto LABEL_341;
          if ( !dword_1031852C8 )
          {
            if ( byte_10316E8EC || (byte_10317B055 & 0x40) != 0 )
            {
              v142 = 1;
              goto LABEL_341;
            }
            goto LABEL_346;
          }
          if ( !byte_10316E8EC && (byte_10317B055 & 0x40) == 0 || (v142 = 1, !IsBusinessCritical()) )
LABEL_346:
            v142 = 0;
LABEL_341:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v233) = v142;
          v14 = *((_DWORD *)a3 + 4) - v233;
LABEL_18:
          v15 = v14 + 4;
LABEL_19:
          *((_QWORD *)a3 + 2) = v15;
LABEL_20:
          *(_BYTE *)a3 = 0;
          return;
        case 48:
          v143 = 0;
          v144 = 0;
          v255 = 0;
          v254 = 0;
          v182 = 0;
          if ( !GetUserNameExW(NameSamCompatible, 0, &v182) && GetLastError() == 234 )
          {
            v145 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v146 = *(_QWORD *)(v145 + 256);
            if ( !v146 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v146 = *(_QWORD *)(v145 + 256);
            }
            v147 = *(struct IMemObj **)(*(_QWORD *)(v146 + 992) + 320LL);
            v148 = 2LL * (v182 + 1);
            if ( !is_mul_ok(v182 + 1, 2u) )
              v148 = -1;
            v149 = (unsigned __int8 *)operator new[](v148, v147, "sql\\ntdbms\\metadata\\src\\sysprop.cpp", 5389, 6u);
            if ( v149 )
              operator delete(0, 2u);
            v144 = v149;
            v255 = v149;
            if ( GetUserNameExW(NameSamCompatible, (LPWSTR)v149, &v182) )
            {
              v144 = 0;
              v255 = 0;
              if ( v149 )
                operator delete[](0);
              v143 = v149;
              v254 = v149;
              v150 = 2 * v182;
              CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
              CXVariantBase::SsVarCopyDataValFromPb(a3, v149, v150);
            }
            else
            {
              v143 = v254;
            }
          }
          operator delete[](v143);
          operator delete(v144, 2u);
          goto LABEL_20;
        case 49:
          if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v11, ThreadLocalStoragePointer) + 537) )
          {
            v153 = 0;
          }
          else
          {
            CPolybaseFeatureManager::MaybeInitExecPaths(&g_PolybaseFeatureManager);
            v153 = qword_1031D6150 != 0;
          }
          if ( dword_1031852C8
            && !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v152, v151) + 371)
            && (qword_10317B120 & 0x8000) == 0 )
          {
            v153 = 1;
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v234) = v153;
          v14 = *((_DWORD *)a3 + 4) - v234;
          goto LABEL_18;
        case 50:
          IsPolybaseProvisioned = CPolybaseFeatureManager::IsPolybaseProvisioned(
                                    (CPolybaseFeatureManager *)&g_PolybaseFeatureManager,
                                    1);
          if ( dword_1031852C8
            && !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v155, v154) + 371)
            && (qword_10317B120 & 0x8000) == 0 )
          {
            IsPolybaseProvisioned = 1;
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v235) = IsPolybaseProvisioned;
          v14 = *((_DWORD *)a3 + 4) - v235;
          goto LABEL_18;
        case 51:
          v83 = L"1000";
          v85 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
          if ( (*(_BYTE *)(*(_QWORD *)(v85 + 72) + 270LL) & 4) != 0
            || *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v85, SystemThread_TlsIndex) + 478)
            && dword_1031852C8
            && !byte_1031852D8
            || !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v87, v86) + 478) && dword_1031852C8 )
          {
            v83 = L"2000";
          }
          v84 = -1;
          do
            ++v84;
          while ( v83[v84] );
          goto LABEL_173;
        case 52:
          Size_4[0] = 0;
          v83 = wcsstr(Size_4, L"GDR");
          if ( !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v89, v88) + 478) )
            goto LABEL_192;
          if ( byte_1031852D8 )
          {
            v83 = (wchar_t *)L"GDR";
LABEL_188:
            v84 = -1;
            do
              ++v84;
            while ( v83[v84] );
LABEL_173:
            CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
            CXVariantBase::SsVarCopyDataValFromPb(a3, (const unsigned __int8 *)v83, (unsigned int)(2 * v84));
            goto LABEL_20;
          }
          if ( dword_1031852C8 )
            return;
LABEL_192:
          if ( v83 )
            goto LABEL_188;
          v83 = wcsstr(Size_4, L"OD");
          if ( v83 )
            goto LABEL_188;
          break;
        case 53:
          v83 = L"16";
          v90 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
          if ( (*(_BYTE *)(*(_QWORD *)(v90 + 72) + 270LL) & 4) != 0
            || dword_103172528 && (byte_1031852E9 || byte_1031852E8) && !byte_1031852E4
            || *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v90, SystemThread_TlsIndex) + 478)
            && dword_1031852C8
            && !byte_1031852D8
            || !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v92, v91) + 478) && dword_1031852C8 )
          {
            v83 = L"12";
          }
          v84 = -1;
          do
            ++v84;
          while ( v83[v84] );
          goto LABEL_173;
        case 54:
          v93 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
          if ( (*(_BYTE *)(*(_QWORD *)(v93 + 72) + 270LL) & 4) == 0
            && (!dword_103172528 || !byte_1031852E9 && !byte_1031852E8 || byte_1031852E4)
            && (!*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v93, SystemThread_TlsIndex) + 478)
             || !dword_1031852C8
             || byte_1031852D8) )
          {
            CFeatureSwitchesLangSvc::GetCurrentInstance(v95, v94);
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          CXVariantBase::SsVarCopyDataValFromPb(a3, (const unsigned __int8 *)L"0", 2u);
          goto LABEL_20;
        case 55:
          Context = 0;
          String = 0;
          v96 = wcstok_s(&String, L"-", &Context);
          v97 = (const unsigned __int8 *)v96;
          if ( !v96 || !wcsstr(v96, L"CU") )
            return;
          v98 = -1;
          do
            ++v98;
          while ( *(_WORD *)&v97[2 * v98] );
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          CXVariantBase::SsVarCopyDataValFromPb(a3, v97, (unsigned int)(2 * v98));
          goto LABEL_20;
        case 57:
          if ( dword_103172520 )
          {
            v13 = 1;
          }
          else
          {
            v257 = 0;
            v157 = GetDefaultLocale();
            StringCchPrintf_lW(v292, 0x105u, L"%ls\\%ls", v157, &word_103179B96, L"AdvancedAnalytics");
            v13 = IniRegOpenKeyExW(-2147483646, (int)v292, 0, 131097, &v257) == 0;
            if ( v257 )
              IniRegCloseKey();
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v236) = v13;
          v14 = *((_DWORD *)a3 + 4) - v236;
          goto LABEL_18;
        case 58:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v237) = 1;
          v14 = *((_DWORD *)a3 + 4) - v237;
          goto LABEL_18;
        case 59:
          v158 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v159 = *(_QWORD *)(v158 + 256);
          if ( !v159 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v159 = *(_QWORD *)(v158 + 256);
          }
          v160 = (wchar_t *)operator new[](
                              0x20Au,
                              *(struct IMemObj **)(v159 + 1000),
                              "sql\\ntdbms\\metadata\\src\\sysprop.cpp",
                              5502,
                              6u);
          v266 = v160;
          v161 = GetDefaultLocale();
          StringCchPrintf_lW(v160, 0x105u, L"%ls\\Polybase\\Configuration", v161, &word_10317A7D2);
          if ( (unsigned int)IniRegOpenKeyExW(-2147483646, (int)v160, 0, 1, &v260) )
            goto LABEL_387;
          *(_DWORD *)v188 = 0;
          v238 = 4;
          IniRegQueryValueExW((int)v260, (int)L"NodeRole", 0, 0, v188, &v238);
          if ( *(_DWORD *)v188 == 1 )
          {
            v162 = L"Head";
          }
          else
          {
            if ( *(_DWORD *)v188 != 2 )
            {
LABEL_387:
              operator delete[](v160);
              return;
            }
            v162 = (const unsigned __int8 *)L"Compute";
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v163 = -1;
          do
            ++v163;
          while ( *(_WORD *)&v162[2 * v163] );
          CXVariantBase::SsVarCopyDataValFromPb(a3, v162, 2 * v163);
          operator delete[](v160);
          goto LABEL_20;
        case 60:
          v164 = *(unsigned __int8 *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v11, ThreadLocalStoragePointer) + 685);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v239) = v164;
          v14 = *((_DWORD *)a3 + 4) - v239;
          goto LABEL_18;
        case 61:
          v181[0] = 0;
          if ( (int)SvlPathGetDefaultPathSeparator(v181) < 0 )
            utassert_fail(1u, "SUCCEEDED(hr)", "sysprop.cpp", 5576, 0);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          v165 = CXVariantBase::SsVarPbDataVal(a3, &v240);
          *(_WORD *)v165 = v181[0];
          v15 = *((_DWORD *)a3 + 4) - v240 + 2;
          goto LABEL_19;
        case 62:
          v53 = 0;
          if ( *((_DWORD *)qword_10316ECA0 + 19) >= 2u )
          {
            v54 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8LL);
            if ( v54 )
            {
              v55 = *(_QWORD *)(v54 + 4624);
              if ( *(_WORD *)(v55 + 1720) == 2 && (v56 = *(_QWORD *)(v55 + 26096)) != 0 )
                v57 = *(_BYTE *)(v56 + 7105);
              else
                v57 = 0;
              LOBYTE(v53) = v57 != 0;
            }
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v207) = v53;
          v14 = *((_DWORD *)a3 + 4) - v207;
          goto LABEL_18;
        case 63:
          v74 = 0;
          if ( *((_DWORD *)qword_10316ECA0 + 19) >= 2u )
          {
            v75 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8LL);
            if ( v75 )
            {
              v76 = *(_QWORD *)(v75 + 4624);
              if ( *(_WORD *)(v76 + 1720) == 2 )
              {
                v77 = *(_QWORD *)(v76 + 26096);
                if ( v77 )
                {
                  if ( *(_BYTE *)(v77 + 7105) )
                    v74 = *(_DWORD *)(v77 + 7108);
                }
              }
            }
          }
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v214) = v74;
          v14 = *((_DWORD *)a3 + 4) - v214;
          goto LABEL_18;
        case 64:
          if ( FPDWFeaturesExposed() && GetEnvironmentVariableW(L"SQLSERVR_XDB_NODE_NAME", v291, 0x104u) - 1 <= 0x102 )
          {
            CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
            v166 = -1;
            do
              ++v166;
            while ( v291[v166] );
            v167 = 2 * v166;
            if ( v167 > 0x1F40 )
              utassert_fail(1u, "cbLen <= x_cbStringMost", "Sql\\Ntdbms\\include\\typesystem\\_retypesbase.inl", 586, 0);
            v168 = CXVariantBase::SsVarPbDataVal(a3, &v241);
            memmove(v168, v291, v167);
            v15 = *((_DWORD *)a3 + 4) + v167 - v241;
          }
          else
          {
            CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
            CXVariantBase::SsVarPbDataVal(a3, &v242);
            v15 = *((_DWORD *)a3 + 4) - v242;
          }
          goto LABEL_19;
        case 65:
          v169 = byte_10317AB00 != 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v243) = v169;
          v14 = *((_DWORD *)a3 + 4) - v243;
          goto LABEL_18;
        case 66:
          v256 = 0;
          ControllerEndpoint = GetControllerEndpoint(&v256);
          v171 = v256;
          if ( ControllerEndpoint )
          {
            v172 = -1;
            do
              ++v172;
            while ( *(_WORD *)&v256[2 * v172] );
            CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
            CXVariantBase::SsVarCopyDataValFromPb(a3, v171, (unsigned int)(2 * v172));
          }
          else
          {
            CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
            CXVariantBase::SsVarPbDataVal(a3, &v244);
            *((_QWORD *)a3 + 2) = *((_DWORD *)a3 + 4) - v244;
          }
          operator delete[](v171);
          goto LABEL_20;
        case 67:
          v173 = 0;
          if ( GetTdsHandle() )
            v173 = *((unsigned __int8 *)GetTdsHandle() + 1820);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v245) = v173;
          v14 = *((_DWORD *)a3 + 4) - v245;
          goto LABEL_18;
        case 68:
          v58 = *((_DWORD *)qword_10316ECA0 + 35) == 1;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v208) = v58;
          v14 = *((_DWORD *)a3 + 4) - v208;
          goto LABEL_18;
        case 69:
          v59 = *((_DWORD *)qword_10316ECA0 + 36) == 1;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v209) = v59;
          v14 = *((_DWORD *)a3 + 4) - v209;
          goto LABEL_18;
        case 70:
          v60 = *((_DWORD *)qword_10316ECA0 + 38);
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v210) = v60;
          v14 = *((_DWORD *)a3 + 4) - v210;
          goto LABEL_18;
        case 71:
          v174 = (unsigned __int8)CGlobalBabylonPolicyProvider::FRBACEnabled() != 0;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiI4);
          *(_DWORD *)CXVariantBase::SsVarPbDataVal(a3, &v246) = v174;
          v14 = *((_DWORD *)a3 + 4) - v246;
          goto LABEL_18;
        case 72:
          v248 = &SysConfigPagePtr::sm_ConfigurationLock;
          v249 = 0;
          TAutoMutex<SOS_RecursiveMutex,4294967295>::GetAccess(&v248, 4195019);
          v277 = 0;
          v278 = 0;
          SysConfigPagePtr::InitFromDisk((struct SysConfigPagePtr *)v276);
          v61 = v279;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiUI1);
          *CXVariantBase::SsVarPbDataVal(a3, &v211) = v61;
          *((_QWORD *)a3 + 2) = *((_DWORD *)a3 + 4) - v211 + 1;
          v62 = v249;
          if ( v249 )
          {
            v63 = v248;
            do
            {
              v64 = v63[8]-- == 1;
              if ( v64 )
              {
                _InterlockedOr(v175, 0);
                v65 = v248;
                v248[6] = 0;
                v65[7] = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v65, 0);
                v62 = v249;
              }
              v64 = v62-- == 1;
              v249 = v62;
            }
            while ( !v64 );
          }
          goto LABEL_20;
        case 73:
          v250 = &SysConfigPagePtr::sm_ConfigurationLock;
          v251 = 0;
          TAutoMutex<SOS_RecursiveMutex,4294967295>::GetAccess(&v250, 4195019);
          v281 = 0;
          v282 = 0;
          SysConfigPagePtr::InitFromDisk((struct SysConfigPagePtr *)v280);
          v66 = v283;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiUI1);
          *CXVariantBase::SsVarPbDataVal(a3, &v212) = v66;
          *((_QWORD *)a3 + 2) = *((_DWORD *)a3 + 4) - v212 + 1;
          v67 = v251;
          if ( v251 )
          {
            v68 = v250;
            do
            {
              v64 = v68[8]-- == 1;
              if ( v64 )
              {
                _InterlockedOr(v175, 0);
                v69 = v250;
                v250[6] = 0;
                v69[7] = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v69, 0);
                v67 = v251;
              }
              v64 = v67-- == 1;
              v251 = v67;
            }
            while ( !v64 );
          }
          goto LABEL_20;
        case 74:
          v252 = &SysConfigPagePtr::sm_ConfigurationLock;
          v253 = 0;
          TAutoMutex<SOS_RecursiveMutex,4294967295>::GetAccess(&v252, 4195019);
          v285 = 0;
          v286 = 0;
          SysConfigPagePtr::InitFromDisk((struct SysConfigPagePtr *)v284);
          v70 = v287;
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&CTypeInfo::tiUI1);
          *CXVariantBase::SsVarPbDataVal(a3, &v213) = v70;
          *((_QWORD *)a3 + 2) = *((_DWORD *)a3 + 4) - v213 + 1;
          v71 = v253;
          if ( v253 )
          {
            v72 = v252;
            do
            {
              v64 = v72[8]-- == 1;
              if ( v64 )
              {
                _InterlockedOr(v175, 0);
                v73 = v252;
                v252[6] = 0;
                v73[7] = 0;
                EventAutoInternal<SuspendQueueSLock>::Signal(v73, 0);
                v71 = v253;
              }
              v64 = v71-- == 1;
              v253 = v71;
            }
            while ( !v64 );
          }
          goto LABEL_20;
        case 75:
          v105 = 8LL * SystemThread_TlsIndex;
          if ( *(char *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v105)
                                               + SystemThread_TlsOffset)
                                   + 72LL)
                       + 270LL) < 0
            || dword_103172528 && (byte_1031852E9 || byte_1031852E8) && !byte_1031852E4 )
          {
            return;
          }
          v106 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset)
                           + 72LL);
          if ( (*(_BYTE *)(v106 + 270) & 8) != 0
            || !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v106, v105) + 478) )
          {
            return;
          }
          v38 = L"CU";
          if ( dword_1031852C8 && !byte_1031852D8
            || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                   + SystemThread_TlsIndex))
                                     + 72LL)
                         + 270LL)
              & 4) != 0 )
          {
            v38 = L"Continuous";
          }
          v107 = -1;
          do
            ++v107;
          while ( v38[v107] );
          Size = 2 * v107;
LABEL_75:
          CXVariant::SsVarSetTypeTag(a3, (const struct CTypeInfo *)&v183);
          CXVariantBase::SsVarCopyDataValFromPb(a3, (const unsigned __int8 *)v38, Size);
          goto LABEL_20;
        default:
          goto LABEL_20;
      }
    }
  }
}

```

## disassembly

```asm
0x1005462b0  push    rbp
0x1005462b2  push    rbx
0x1005462b3  push    rsi
0x1005462b4  push    rdi
0x1005462b5  push    r12
0x1005462b7  push    r14
0x1005462b9  push    r15
0x1005462bb  lea     rbp, [rsp-0A990h]
0x1005462c3  mov     eax, 0AA90h
0x1005462c8  call    _alloca_probe
0x1005462cd  sub     rsp, rax
0x1005462d0  mov     [rbp+0A9C0h+var_A8A0], 0FFFFFFFFFFFFFFFEh
0x1005462db  mov     rax, cs:__security_cookie
0x1005462e2  xor     rax, rsp
0x1005462e5  mov     [rbp+0A9C0h+var_40], rax
0x1005462ec  movzx   esi, r9b
0x1005462f0  mov     r15, r8
0x1005462f3  mov     ebx, edx
0x1005462f5  mov     r14, rcx
0x1005462f8  mov     dword ptr [rsp+0AAC0h+Size], 100h
0x100546300  call    cs:__imp_?PDCServer@CDefaultCollation@@SAPEAV1@XZ; CDefaultCollation::PDCServer(void)
0x100546306  mov     edi, [rax]
0x100546308  movups  xmm0, cs:?tiSSWName@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiSSWName
0x10054630f  movups  [rsp+0AAC0h+var_AA70], xmm0
0x100546314  movups  xmm1, cs:xmmword_1031D5B70
0x10054631b  movups  [rsp+0AAC0h+var_AA60], xmm1
0x100546320  call    cs:__imp_?PDCServer@CDefaultCollation@@SAPEAV1@XZ; CDefaultCollation::PDCServer(void)
0x100546326  mov     r9, rax
0x100546329  lea     rcx, [rsp+0AAC0h+var_AA70]; this
0x10054632e  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100546333  test    al, al
0x100546335  jz      short loc_10054633E
0x100546337  mov     eax, [r9]
0x10054633a  mov     dword ptr [rsp+0AAC0h+var_AA60+4], eax
0x10054633e  mov     byte ptr [r15], 3
0x100546342  lea     eax, [rbx-1]
0x100546345  cmp     eax, 0FFh
0x10054634a  ja      def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100546350  lfence
0x100546353  mov     r9d, ebx; int
0x100546356  mov     r8, r14; char *
0x100546359  mov     edx, 4Bh ; 'K'; int
0x10054635e  lea     rcx, ?x_rgspServerProperty@@3PAUSysProp@@A; struct SysProp *
0x100546365  call    ?LookupProperty@@YAHPEBUSysProp@@HPEBDH@Z; LookupProperty(SysProp const *,int,char const *,int)
0x10054636a  mov     ebx, eax
0x10054636c  test    eax, eax
0x10054636e  jz      def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100546374  lea     r14, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x10054637b  test    sil, sil
0x10054637e  jnz     short def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100546380  cmp     cs:dword_1031852C8, 0
0x100546387  jnz     loc_100A4C1AB
0x10054638d  cmp     cs:dword_103172528, 0
0x100546394  jnz     loc_100A4C0A2
0x10054639a  cmp     cs:dword_103184474, 0
0x1005463a1  jnz     loc_100A4C137
0x1005463a7  cmp     cs:dword_103172528, 0
0x1005463ae  jnz     short def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x1005463b0  mov     ecx, ebx
0x1005463b2  sub     ecx, 2Bh ; '+'
0x1005463b5  jz      short def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x1005463b7  sub     ecx, 1
0x1005463ba  jz      short def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x1005463bc  sub     ecx, 4
0x1005463bf  jz      short def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x1005463c1  cmp     ecx, 13h
0x1005463c4  jz      short def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x1005463c6  dec     ebx; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x1005463c8  cmp     ebx, 4Ah
0x1005463cb  ja      short def_1005463DB; jumptable 00000001005463DB default case
0x1005463cd  movsxd  rax, ebx
0x1005463d0  mov     ecx, ds:(jpt_1005463DB - 100400000h)[r14+rax*4]
0x1005463d8  add     rcx, r14
0x1005463db  jmp     rcx; switch jump
0x1005463de  cmp     cs:dword_103172520, 0; jumptable 00000001005463DB case 57
0x1005463e5  jz      loc_100A4E170
0x1005463eb  mov     esi, 1
0x1005463f0  jmp     short loc_1005463F3
0x1005463f3  lea     rdx, ?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x1005463fa  mov     rcx, r15
0x1005463fd  call    cs:__imp_?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z; CXVariant::SsVarSetTypeTag(CTypeInfo const *)
0x100546403  lea     rdx, [rbp+0A9C0h+var_A980]; unsigned int *
0x100546407  mov     rcx, r15; this
0x10054640a  call    ?SsVarPbDataVal@CXVariantBase@@QEBAPEAEPEAK@Z; CXVariantBase::SsVarPbDataVal(ulong *)
0x10054640f  mov     [rax], esi
0x100546411  mov     eax, [r15+10h]
0x100546415  sub     eax, [rbp+0A9C0h+var_A980]
0x100546418  jmp     short loc_10054641B
0x10054641b  add     eax, 4
0x10054641e  mov     [r15+10h], rax
0x100546422  mov     byte ptr [r15], 0; jumptable 00000001005463DB default case
0x100546426  mov     rcx, [rbp+0A9C0h+var_40]; jumptable 00000001005463DB cases 35,36,56
0x10054642d  xor     rcx, rsp; StackCookie
0x100546430  call    __security_check_cookie
0x100546435  add     rsp, 0AA90h
0x10054643c  pop     r15
0x10054643e  pop     r14
0x100546440  pop     r12
0x100546442  pop     rdi
0x100546443  pop     rsi
0x100546444  pop     rbx
0x100546445  pop     rbp
0x100546446  retn
0x100a4c0a2  cmp     cs:byte_1031852E9, sil
0x100a4c0a9  jnz     short loc_100A4C0B8
0x100a4c0ab  cmp     cs:byte_1031852E8, sil
0x100a4c0b2  jz      loc_10054639A
0x100a4c0b8  cmp     cs:byte_1031852E4, 0
0x100a4c0bf  jnz     loc_10054639A
0x100a4c0c5  mov     rdx, gs:58h
0x100a4c0ce  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100a4c0d5  mov     ecx, [rax]
0x100a4c0d7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100a4c0de  mov     r8d, [rax]
0x100a4c0e1  mov     rax, [rdx+rcx*8]
0x100a4c0e5  cmp     qword ptr [r8+rax], 0
0x100a4c0ea  jz      def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c0f0  mov     rax, gs:58h
0x100a4c0f9  mov     rcx, [rax+rcx*8]
0x100a4c0fd  mov     rax, [rcx+r8]
0x100a4c101  mov     rcx, [rax+48h]
0x100a4c105  test    byte ptr [rcx+10Eh], 2
0x100a4c10c  jnz     def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c112  lea     eax, [rbx-1]; switch 48 cases
0x100a4c115  cmp     eax, 2Fh
0x100a4c118  ja      def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c11e  cdqe
0x100a4c120  movzx   eax, ds:(byte_100546458 - 100400000h)[r14+rax]
0x100a4c129  mov     ecx, ds:(jpt_100A4C134 - 100400000h)[r14+rax*4]
0x100a4c131  add     rcx, r14
0x100a4c134  jmp     rcx; switch jump
0x100a4c137  mov     rdx, gs:58h
0x100a4c140  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100a4c147  mov     ecx, [rax]
0x100a4c149  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100a4c150  mov     r8d, [rax]
0x100a4c153  mov     rax, [rdx+rcx*8]
0x100a4c157  cmp     qword ptr [r8+rax], 0
0x100a4c15c  jz      def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c162  mov     rax, gs:58h
0x100a4c16b  mov     rcx, [rax+rcx*8]
0x100a4c16f  mov     edx, 3
0x100a4c174  mov     rcx, [r8+rcx]
0x100a4c178  call    cs:__imp_?FSQLFilterLevelBasic@ContextAccessor@@YA_NVContextHandle@@W4EFilterLevel@@@Z; ContextAccessor::FSQLFilterLevelBasic(ContextHandle,EFilterLevel)
0x100a4c17e  test    al, al
0x100a4c180  jz      def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c186  lea     eax, [rbx-1]; switch 71 cases
0x100a4c189  cmp     eax, 46h
0x100a4c18c  ja      def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100a4c192  cdqe
0x100a4c194  movzx   eax, ds:(byte_100546494 - 100400000h)[r14+rax]
0x100a4c19d  mov     ecx, ds:(jpt_100A4C1A8 - 100400000h)[r14+rax*4]
0x100a4c1a5  add     rcx, r14
0x100a4c1a8  jmp     rcx; switch jump
0x100a4c1ab  mov     rdx, gs:58h
0x100a4c1b4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100a4c1bb  mov     ecx, [rax]
0x100a4c1bd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100a4c1c4  mov     eax, [rax]
0x100a4c1c6  add     rax, [rdx+rcx*8]
0x100a4c1ca  mov     rax, [rax]
0x100a4c1cd  mov     rcx, [rax+48h]
0x100a4c1d1  test    byte ptr [rcx+10Eh], 2
0x100a4c1d8  jnz     def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c1de  lea     eax, [rbx-1]; switch 48 cases
0x100a4c1e1  cmp     eax, 2Fh
0x100a4c1e4  ja      def_100A4C134; jumptable 0000000100A4C134 default case, cases 3,10-24,26-31,33,35,36,38-42,45-47
0x100a4c1ea  cdqe
0x100a4c1ec  movzx   eax, ds:(byte_100546610 - 100400000h)[r14+rax]
0x100a4c1f5  mov     ecx, ds:(jpt_100A4C200 - 100400000h)[r14+rax*4]
0x100a4c1fd  add     rcx, r14
0x100a4c200  jmp     rcx; switch jump
0x100a4c202  cmp     cs:dword_103172550, 0; jumptable 00000001005463DB case 5
0x100a4c209  jnz     short loc_100A4C22F
0x100a4c20b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100a4c212  mov     rcx, [rax]
0x100a4c215  mov     rax, [rcx]
0x100a4c218  call    qword ptr [rax+0E0h]
0x100a4c21e  mov     rcx, rax
0x100a4c221  call    cs:__imp_IsDefaultInstanceName
0x100a4c227  test    eax, eax
0x100a4c229  jnz     def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100a4c22f  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100a4c236  mov     rcx, [rax]
0x100a4c239  mov     rax, [rcx]
0x100a4c23c  call    qword ptr [rax+0E0h]
0x100a4c242  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100a4c249  nop     dword ptr [rax+00000000h]
0x100a4c250  lea     rdi, [rdi+1]
0x100a4c254  cmp     word ptr [rax+rdi*2], 0
0x100a4c259  jnz     short loc_100A4C250
0x100a4c25b  lea     eax, [rdi+rdi]
0x100a4c25e  mov     dword ptr [rsp+0AAC0h+Size], eax
0x100a4c262  dec     eax
0x100a4c264  cmp     eax, 0FFh
0x100a4c269  ja      def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100a4c26f  lea     rdx, [rsp+0AAC0h+var_AA70]
0x100a4c274  mov     rcx, r15
0x100a4c277  call    cs:__imp_?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z; CXVariant::SsVarSetTypeTag(CTypeInfo const *)
0x100a4c27d  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100a4c284  mov     rcx, [rax]
0x100a4c287  mov     rax, [rcx]
0x100a4c28a  call    qword ptr [rax+0E0h]
0x100a4c290  mov     r8d, dword ptr [rsp+0AAC0h+Size]; Size
0x100a4c295  mov     rdx, rax; Src
0x100a4c298  mov     rcx, r15; this
0x100a4c29b  call    ?SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z; CXVariantBase::SsVarCopyDataValFromPb(uchar const *,ulong)
0x100a4c2a0  jmp     def_1005463DB; jumptable 00000001005463DB default case
0x100a4c2a5  lea     r14, pszSrch; jumptable 00000001005463DB cases 6,8
0x100a4c2ac  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100a4c2b3  inc     rdi
0x100a4c2b6  cmp     word ptr [r14+rdi*2], 0
0x100a4c2bc  jnz     short loc_100A4C2B3
0x100a4c2be  add     edi, edi
0x100a4c2c0  mov     dword ptr [rsp+0AAC0h+Size], edi
0x100a4c2c4  lea     rdx, [rsp+0AAC0h+var_AA70]
0x100a4c2c9  mov     rcx, r15
0x100a4c2cc  call    cs:__imp_?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z; CXVariant::SsVarSetTypeTag(CTypeInfo const *)
0x100a4c2d2  mov     edi, dword ptr [rsp+0AAC0h+Size]
0x100a4c2d6  cmp     edi, 1F40h
0x100a4c2dc  jbe     short loc_100A4C302
0x100a4c2de  xor     ebx, ebx
0x100a4c2e0  mov     [rsp+0AAC0h+var_AAA0], rbx
0x100a4c2e5  mov     r9d, 24Ah
0x100a4c2eb  lea     r8, ?szFileName@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "Sql\\Ntdbms\\include\\typesystem\\_rety"...
0x100a4c2f2  lea     rdx, ?szExpression@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "cbLen <= x_cbStringMost"
0x100a4c2f9  lea     ecx, [rbx+1]
0x100a4c2fc  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100a4c302  lea     rdx, [rbp+0A9C0h+var_A954]; unsigned int *
0x100a4c306  mov     rcx, r15; this
0x100a4c309  call    ?SsVarPbDataVal@CXVariantBase@@QEBAPEAEPEAK@Z; CXVariantBase::SsVarPbDataVal(ulong *)
0x100a4c30e  mov     r8, rdi; Size
0x100a4c311  mov     rdx, r14; Src
0x100a4c314  mov     rcx, rax; void *
0x100a4c317  call    memmove
0x100a4c31c  sub     edi, [rbp+0A9C0h+var_A954]
0x100a4c31f  add     edi, [r15+10h]
0x100a4c323  mov     eax, edi
0x100a4c325  jmp     loc_10054641E
0x100a4c32a  xor     edx, edx; jumptable 00000001005463DB case 7
0x100a4c32c  mov     r8d, 20Ah; Size
0x100a4c332  lea     rcx, [rbp+0A9C0h+Src]; void *
0x100a4c339  call    memset_0
0x100a4c33e  mov     edx, 105h; unsigned __int64
0x100a4c343  lea     rcx, [rbp+0A9C0h+Src]; wchar_t *
0x100a4c34a  call    GetDefaultBackupPath
0x100a4c34f  lea     rax, [rbp+0A9C0h+Src]
0x100a4c356  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100a4c35d  nop     dword ptr [rax]
0x100a4c360  inc     rdi
0x100a4c363  cmp     word ptr [rax+rdi*2], 0
0x100a4c368  jnz     short loc_100A4C360
0x100a4c36a  add     edi, edi
0x100a4c36c  mov     dword ptr [rsp+0AAC0h+Size], edi
0x100a4c370  test    edi, edi
0x100a4c372  jle     def_100A4C1A8; jumptable 00000001005463DB cases 35,36,56
0x100a4c378  lea     rdx, [rsp+0AAC0h+var_AA70]
0x100a4c37d  mov     rcx, r15
0x100a4c380  call    cs:__imp_?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z; CXVariant::SsVarSetTypeTag(CTypeInfo const *)
0x100a4c386  mov     edi, dword ptr [rsp+0AAC0h+Size]
0x100a4c38a  cmp     edi, 1F40h
0x100a4c390  jbe     short loc_100A4C3B6
0x100a4c392  xor     ebx, ebx
0x100a4c394  mov     [rsp+0AAC0h+var_AAA0], rbx
0x100a4c399  mov     r9d, 24Ah
0x100a4c39f  lea     r8, ?szFileName@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "Sql\\Ntdbms\\include\\typesystem\\_rety"...
0x100a4c3a6  lea     rdx, ?szExpression@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "cbLen <= x_cbStringMost"
0x100a4c3ad  lea     ecx, [rbx+1]
0x100a4c3b0  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100a4c3b6  lea     rdx, [rbp+0A9C0h+var_AA3C]; unsigned int *
0x100a4c3ba  mov     rcx, r15; this
0x100a4c3bd  call    ?SsVarPbDataVal@CXVariantBase@@QEBAPEAEPEAK@Z; CXVariantBase::SsVarPbDataVal(ulong *)
0x100a4c3c2  mov     rcx, rax; void *
0x100a4c3c5  mov     r8, rdi; Size
0x100a4c3c8  lea     rdx, [rbp+0A9C0h+Src]; Src
0x100a4c3cf  call    memmove
0x100a4c3d4  sub     edi, [rbp+0A9C0h+var_AA3C]
0x100a4c3d7  add     edi, [r15+10h]
0x100a4c3db  mov     eax, edi
0x100a4c3dd  jmp     loc_10054641E
0x100a4c3e2  lea     r14, qword_1033C2940; jumptable 00000001005463DB case 9
0x100a4c3e9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100a4c3f0  inc     rdi
0x100a4c3f3  cmp     word ptr [r14+rdi*2], 0
0x100a4c3f9  jnz     short loc_100A4C3F0
0x100a4c3fb  add     edi, edi
0x100a4c3fd  mov     dword ptr [rsp+0AAC0h+Size], edi
0x100a4c401  lea     rdx, [rsp+0AAC0h+var_AA70]
0x100a4c406  mov     rcx, r15
0x100a4c409  call    cs:__imp_?SsVarSetTypeTag@CXVariant@@QEAAXPEBVCTypeInfo@@@Z; CXVariant::SsVarSetTypeTag(CTypeInfo const *)
0x100a4c40f  mov     edi, dword ptr [rsp+0AAC0h+Size]
0x100a4c413  cmp     edi, 1F40h
0x100a4c419  jbe     short loc_100A4C43F
0x100a4c41b  xor     ebx, ebx
0x100a4c41d  mov     [rsp+0AAC0h+var_AAA0], rbx
0x100a4c422  mov     r9d, 24Ah
0x100a4c428  lea     r8, ?szFileName@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "Sql\\Ntdbms\\include\\typesystem\\_rety"...
0x100a4c42f  lea     rdx, ?szExpression@?6??SsVarCopyDataValFromPb@CXVariantBase@@QEAAXPEBEK@Z@4QBDB; "cbLen <= x_cbStringMost"
0x100a4c436  lea     ecx, [rbx+1]
0x100a4c439  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
  ... truncated ...
```
