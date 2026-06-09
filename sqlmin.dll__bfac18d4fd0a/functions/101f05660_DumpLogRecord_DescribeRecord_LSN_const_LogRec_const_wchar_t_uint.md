# DumpLogRecord::DescribeRecord(LSN const &,LogRec const *,wchar_t *,uint)

- ea: `0x101f05660`
- end: `0x101f0f021`
- name: `?DescribeRecord@DumpLogRecord@@AEAAXAEBVLSN@@PEBVLogRec@@PEA_WI@Z`
- size: `39361`
- prototype: `void __fastcall(DumpLogRecord *__hidden this, const struct LSN *, const struct LogRec *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x101f02740`

## callees

- `0x100401490`
- `0x100402000`
- `0x10042b3d0`
- `0x100441e00`
- `0x100445560`
- `0x10046bf90`
- `0x1004c4700`
- `0x100625f90`
- `0x100626050`
- `0x1007c1a20`
- `0x100a7d300`
- `0x100b4c700`
- `0x100b4c900`
- `0x100b4c920`
- `0x10121ecb0`
- `0x10123db70`
- `0x101278a20`
- `0x101278c70`
- `0x1012c79e0`
- `0x1014cff90`
- `0x1014d0360`
- `0x10162d740`
- `0x1018ca650`
- `0x1019125e0`
- `0x101b7de40`
- `0x101b84be0`
- `0x101b84d20`
- `0x101b84d70`
- `0x101bdf9c0`
- `0x101bdfbc0`
- `0x101bdfc20`
- `0x101c37920`
- `0x101c39040`
- `0x101c39590`
- `0x101ce3f50`
- `0x101ce3f80`
- `0x101d8b530`
- `0x101d8b570`
- `0x101e3d8a0`
- `0x101efeac0`
- `0x101efeb70`
- `0x101efec20`
- `0x101f04e80`
- `0x101f04fa0`
- `0x101f05090`
- `0x101f05660`
- `0x101f17350`
- `0x101f17390`
- `0x101f173c0`
- `0x101f173e0`

## import_xrefs

- `sqlTsEs!?DateToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z` at `0x101f05703`
- `sqlTsEs!?DateToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z` at `0x101f05703`
- `sqlTsEs!?TimeToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z` at `0x101f05717`
- `sqlTsEs!?TimeToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z` at `0x101f05717`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x101f08122`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x101f08122`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f0d511`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f05725`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f05a83`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f07ef0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f082a6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f084bf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0875a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08988`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08b57`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08e85`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09049`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0941f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09518`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09aa2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09ec5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a01f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a0ae`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a1f8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a348`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a498`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a5ef`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a752`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0be0d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0bfcd`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0c2c0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ce37`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ce86`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cee7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cf3f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cf99`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cffc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d0da`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d129`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d18a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d1eb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d24b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d29c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d2ff`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d3cc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d453`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d561`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d5ed`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d6d0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d73c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d837`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d8a8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d974`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d9e0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dacc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0db38`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dbd7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dc50`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e076`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e158`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e1cf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e248`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e3f3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e496`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e657`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e6fc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e78f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e948`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0eae6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0eb64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ed1c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ef0c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f05725`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f05a83`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f07ef0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f082a6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f084bf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0875a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08988`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08b57`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f08e85`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09049`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0941f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09518`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09aa2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f09ec5`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a01f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a0ae`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a1f8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a348`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a498`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a5ef`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0a752`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0be0d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0bfcd`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0c2c0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ce37`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ce86`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cee7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cf3f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cf99`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0cffc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d0da`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d129`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d18a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d1eb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d24b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d29c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d2ff`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d3cc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d453`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d561`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d5ed`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d6d0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d73c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d837`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d8a8`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d974`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0d9e0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dacc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0db38`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dbd7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0dc50`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e076`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e158`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e1cf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e248`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e3f3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e496`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e657`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e6fc`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e78f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0e948`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0eae6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0eb64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ed1c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101f0ef0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05cef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05d72`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05e7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05f59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06035`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f062d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f063a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06438`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f065dc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06666`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0676a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0683a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06909`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06b6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06c30`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06cba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06f2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06ffe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f070cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0733d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f07400`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0780a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f078e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f079bb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f07c59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f07d2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f098c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f09a98`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f09cfa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0aa9e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0ab25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0ace5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0adb4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0ae86`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b104`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b1ce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b52a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b62d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b785`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b857`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0b928`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0bbad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0bc73`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0c3b2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0dcf6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0dfc3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0e368`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0ec7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05cef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05d72`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05e7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f05f59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06035`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f062d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f063a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06438`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f065dc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06666`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0676a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f0683a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06909`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06b6a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f06c30`

## string_xrefs

- `0x101f09944`: `WRITE`
- `0x101f09929`: `DELETE`
- `0x101f09920`: `CREATE`
- `0x101f0cb86`: `XdesIds `
- `0x101f0c245`: `XdesIDs: `
- `0x101f0d3e6`: `cache invalidation (cache: %s, keys: %s). `
- `0x101f09023`: `CREATE_HOBT`
- `0x101f05993`: `COMPENSATION`
- `0x101f0993b`: `IN PLACE UPDATE`
- `0x101f0e9fd`: `Server Config Settings Reconfigured`
- `0x101f0ddc4`: `, previous checkpoint completion LSN = `
- `0x101f0dd05`: `XTP complete checkpoint ver %d:  { LSN = `
- `0x101f0dc5e`: `delete bitmap cache invalidation (RowsetId: %I64d).`
- `0x101f0dbe0`: `UNDONE put some delete buffer log record description here`
- `0x101f0e3df`: `Moved `
- `0x101f0e379`: `Uncompress_Page `
- `0x101f0e382`: `Compress_Page `
- `0x101f0e370`: `Copy_CompressionInfo `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DumpLogRecord::DescribeRecord(
        DumpLogRecord *this,
        const struct LSN *a2,
        const struct LogRec *a3,
        wchar_t *a4,
        unsigned int a5)
{
  wchar_t *v5; // r13
  DatabaseMetaLog *v6; // r15
  unsigned __int64 v7; // rcx
  int v8; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v10; // eax
  unsigned int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  const wchar_t *v15; // r9
  __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  const wchar_t *v20; // r9
  __int64 v21; // rdx
  _WORD *v22; // rax
  const wchar_t *v23; // rdi
  const unsigned __int8 *Data; // rax
  int v25; // ebx
  struct __crt_locale_pointers *v26; // rax
  int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // ebx
  const unsigned __int8 *v30; // rax
  unsigned __int8 v31; // r9
  unsigned __int16 v32; // cx
  __int16 v33; // r8
  unsigned int v34; // r9d
  const unsigned __int8 *v35; // rdi
  unsigned __int16 v36; // dx
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int v39; // r10d
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  const unsigned __int8 *v44; // rax
  unsigned int v45; // ebx
  unsigned __int16 v46; // r8
  __int16 v47; // cx
  __int16 v48; // dx
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v50; // r9
  __int64 v51; // rdx
  int v52; // r8d
  __int16 v53; // ax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  char v58; // cl
  const unsigned __int8 *v59; // rax
  const unsigned __int8 *v60; // r8
  unsigned __int8 v61; // r9
  unsigned __int16 v62; // ax
  unsigned __int16 v63; // cx
  __int16 v64; // r8
  unsigned int v65; // ebx
  unsigned int v66; // edi
  const unsigned __int8 *v67; // rsi
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  const unsigned __int8 *v74; // rax
  unsigned int v75; // edi
  unsigned __int16 v76; // dx
  __int16 v77; // cx
  __int16 v78; // dx
  struct RecVersioningInfo *v79; // rax
  __int64 v80; // r9
  __int64 v81; // rdx
  int v82; // r8d
  __int16 v83; // ax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  char v88; // cl
  bool v89; // zf
  int v90; // eax
  const unsigned __int8 *v91; // r8
  unsigned __int8 v92; // dl
  int v93; // eax
  int v94; // ecx
  const unsigned __int8 *v95; // rax
  unsigned int v96; // ebx
  unsigned int v97; // edx
  const unsigned __int8 *v98; // rdi
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  const unsigned __int8 *v105; // rax
  unsigned int v106; // ebx
  unsigned __int16 v107; // r8
  const unsigned __int8 *v108; // r8
  __int16 v109; // ax
  __int16 v110; // cx
  struct RecVersioningInfo *v111; // rax
  __int64 v112; // r9
  __int64 v113; // rdx
  int v114; // r8d
  __int16 v115; // ax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  const unsigned __int8 *v120; // rax
  unsigned int v121; // edi
  unsigned int v122; // ebx
  unsigned int v123; // esi
  const unsigned __int8 *v124; // r9
  unsigned __int8 v125; // dl
  int v126; // r10d
  int v127; // eax
  int v128; // eax
  const unsigned __int8 *v129; // rax
  unsigned __int8 v130; // dl
  unsigned int v131; // edx
  const unsigned __int8 *v132; // rdi
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  unsigned int v137; // r8d
  __int64 v138; // rax
  __int64 v139; // rax
  const unsigned __int8 *v140; // rax
  unsigned int v141; // ebx
  __int16 v142; // ax
  __int16 v143; // cx
  struct RecVersioningInfo *v144; // rax
  __int64 v145; // r8
  __int64 v146; // rdx
  int v147; // r9d
  __int16 v148; // ax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // r8
  const unsigned __int8 *v154; // rax
  unsigned int v155; // edi
  unsigned int v156; // ebx
  unsigned int v157; // ebx
  struct __crt_locale_pointers *v158; // r9
  const wchar_t *v159; // r8
  int v160; // eax
  __int64 v161; // rax
  const wchar_t *v162; // r11
  unsigned int v163; // ebx
  __int64 v164; // r8
  __int64 v165; // r9
  const wchar_t *v166; // r10
  __int64 v167; // rdx
  _WORD *v168; // rax
  const unsigned __int8 *v169; // rax
  const wchar_t *v170; // r11
  unsigned int v171; // ebx
  __int64 v172; // r8
  wchar_t *v173; // rax
  __int64 v174; // r9
  const wchar_t *v175; // r10
  __int64 v176; // rdx
  _WORD *v177; // rax
  __int64 v178; // rdi
  VarLogData *v179; // rbx
  const unsigned __int8 *v180; // rax
  const unsigned __int8 *v181; // r15
  unsigned int v182; // r12d
  const unsigned __int8 *v183; // rax
  const unsigned __int8 *v184; // rcx
  const unsigned __int8 *v185; // rax
  const unsigned __int8 *v186; // rcx
  struct __crt_locale_pointers *v187; // rax
  DatabaseMetaLog *v188; // rsi
  int v189; // eax
  __int64 v190; // r8
  wchar_t *v191; // rax
  __int64 v192; // r9
  const wchar_t *v193; // r10
  __int64 v194; // rdx
  _WORD *v195; // rax
  __int64 v196; // rax
  const unsigned __int8 *v197; // rax
  const unsigned __int8 *v198; // rcx
  const unsigned __int8 *v199; // rax
  const unsigned __int8 *v200; // rcx
  __int64 v201; // rax
  __int64 v202; // rbx
  struct __crt_locale_pointers *v203; // rax
  int v204; // eax
  __int64 v205; // r8
  wchar_t *v206; // rax
  __int64 v207; // r9
  const wchar_t *v208; // r10
  wchar_t *v209; // rdx
  wchar_t *v210; // rax
  __int64 v211; // rax
  int v212; // esi
  unsigned int v213; // ebx
  __int64 v214; // rdi
  const wchar_t *v215; // r8
  unsigned int v216; // r12d
  const unsigned __int8 *v217; // r15
  const unsigned __int8 *v218; // rax
  const unsigned __int8 *v219; // rcx
  __int64 v220; // rbx
  struct __crt_locale_pointers *v221; // rax
  int v222; // eax
  __int64 v223; // r8
  wchar_t *v224; // rax
  __int64 v225; // r9
  const wchar_t *v226; // r10
  wchar_t *v227; // rcx
  __int64 v228; // rdx
  wchar_t *v229; // rax
  __int64 v230; // rax
  int v231; // esi
  unsigned int v232; // ebx
  __int64 v233; // rdi
  const wchar_t *v234; // r8
  unsigned int v235; // r12d
  DatabaseMetaLog *v236; // rbx
  int NonLoggedInCTRRowCount; // ebx
  struct __crt_locale_pointers *v238; // rax
  int v239; // eax
  __int64 v240; // r8
  wchar_t *v241; // rax
  __int64 v242; // r9
  const wchar_t *v243; // r10
  __int64 v244; // rdx
  _WORD *v245; // rax
  __int64 v246; // rax
  const unsigned __int8 *v247; // r15
  const unsigned __int8 *v248; // rax
  const unsigned __int8 *v249; // rcx
  __int64 v250; // rbx
  struct __crt_locale_pointers *v251; // rax
  int v252; // eax
  __int64 v253; // r8
  wchar_t *v254; // rax
  __int64 v255; // r9
  const wchar_t *v256; // r10
  __int64 v257; // rdx
  _WORD *v258; // rax
  __int64 v259; // rax
  unsigned int v260; // esi
  unsigned int v261; // ebx
  __int64 v262; // rdi
  const wchar_t *v263; // r8
  unsigned int v264; // esi
  const wchar_t *v265; // rbx
  __int64 v266; // r11
  __int64 v267; // r8
  wchar_t *v268; // rax
  __int64 v269; // r9
  const wchar_t *v270; // r10
  __int64 v271; // rdx
  _WORD *v272; // rax
  int v273; // r9d
  int v274; // ebx
  struct __crt_locale_pointers *v275; // rax
  int v276; // eax
  __int64 v277; // r8
  wchar_t *v278; // rax
  __int64 v279; // r9
  const wchar_t *v280; // r10
  __int64 v281; // rdx
  _WORD *v282; // rax
  __int64 v283; // rax
  __int64 v284; // r13
  int v285; // r12d
  const wchar_t *v286; // r15
  __int64 v287; // rsi
  struct __crt_locale_pointers *v288; // rax
  int v289; // eax
  __int64 v290; // r8
  wchar_t *v291; // rax
  __int64 v292; // r9
  const wchar_t *v293; // r10
  __int64 v294; // rdx
  _WORD *v295; // rax
  __int64 v296; // rax
  __int64 v297; // r8
  wchar_t *v298; // rax
  __int64 v299; // r9
  const wchar_t *v300; // r10
  wchar_t *v301; // rdx
  __int64 v302; // rcx
  wchar_t *v303; // rax
  __int64 v304; // rax
  __int64 v305; // r8
  wchar_t *v306; // rax
  __int64 v307; // r9
  const wchar_t *v308; // r10
  wchar_t *v309; // rdx
  __int64 v310; // rcx
  wchar_t *v311; // rax
  unsigned int v312; // ebx
  struct __crt_locale_pointers *v313; // rax
  int v314; // eax
  __int64 v315; // rcx
  const unsigned __int8 *v316; // rax
  int v317; // edi
  int v318; // ebx
  struct __crt_locale_pointers *v319; // rax
  int v320; // eax
  __int64 v321; // r8
  wchar_t *v322; // rax
  __int64 v323; // r9
  const wchar_t *v324; // r10
  wchar_t *v325; // rdx
  wchar_t *v326; // rax
  __int64 v327; // rax
  const wchar_t *v328; // rbx
  __int64 v329; // r11
  __int64 v330; // r8
  wchar_t *v331; // rax
  __int64 v332; // r9
  const wchar_t *v333; // r10
  wchar_t *v334; // rdx
  wchar_t *v335; // rax
  int v336; // r9d
  const unsigned __int8 *v337; // rdi
  const struct LSN *v338; // r9
  const wchar_t *v339; // rbx
  __int64 v340; // r8
  wchar_t *v341; // rax
  __int64 v342; // r9
  const wchar_t *v343; // r10
  wchar_t *v344; // rdx
  __int64 v345; // rcx
  wchar_t *v346; // rax
  __int64 v347; // rax
  struct __crt_locale_pointers *v348; // rax
  int v349; // eax
  __int64 v350; // r8
  wchar_t *v351; // rax
  __int64 v352; // r9
  const wchar_t *v353; // r10
  wchar_t *v354; // rdx
  __int64 v355; // rcx
  wchar_t *v356; // rax
  __int64 v357; // rax
  __int64 v358; // r8
  wchar_t *v359; // rax
  __int64 v360; // r9
  const wchar_t *v361; // r10
  wchar_t *v362; // rdx
  __int64 v363; // rcx
  wchar_t *v364; // rax
  const wchar_t *v365; // r8
  unsigned int v366; // ebx
  const wchar_t *v367; // r8
  unsigned int v368; // ebx
  __int64 v369; // r8
  wchar_t *v370; // rax
  __int64 v371; // r9
  const wchar_t *v372; // r10
  wchar_t *v373; // rdx
  __int64 v374; // rcx
  wchar_t *v375; // rax
  int v376; // ebx
  struct __crt_locale_pointers *v377; // rax
  unsigned int v378; // ebx
  __int64 v379; // rax
  int v380; // eax
  __int64 v381; // r8
  wchar_t *v382; // rax
  __int64 v383; // r9
  const wchar_t *v384; // r10
  wchar_t *v385; // rdx
  __int64 v386; // rcx
  wchar_t *v387; // rax
  int v388; // ebx
  struct __crt_locale_pointers *v389; // rax
  __int64 v390; // rax
  struct __crt_locale_pointers *v391; // rax
  int v392; // eax
  __int64 v393; // r8
  wchar_t *v394; // rax
  __int64 v395; // r9
  const wchar_t *v396; // r10
  wchar_t *v397; // rdx
  __int64 v398; // rcx
  wchar_t *v399; // rax
  __int64 v400; // rax
  struct __crt_locale_pointers *v401; // rax
  int v402; // eax
  __int64 v403; // r8
  wchar_t *v404; // rax
  __int64 v405; // r9
  const wchar_t *v406; // r10
  wchar_t *v407; // rdx
  __int64 v408; // rcx
  wchar_t *v409; // rax
  __int64 v410; // rax
  struct __crt_locale_pointers *v411; // rax
  int v412; // eax
  __int64 v413; // r8
  wchar_t *v414; // rax
  __int64 v415; // r9
  const wchar_t *v416; // r10
  wchar_t *v417; // rdx
  __int64 v418; // rcx
  wchar_t *v419; // rax
  __int64 v420; // rax
  struct __crt_locale_pointers *v421; // rax
  int v422; // eax
  __int64 v423; // r8
  wchar_t *v424; // rax
  __int64 v425; // r9
  const wchar_t *v426; // r10
  wchar_t *v427; // rdx
  __int64 v428; // rcx
  wchar_t *v429; // rax
  __int64 v430; // rax
  int v431; // ebx
  struct __crt_locale_pointers *v432; // rax
  int v433; // eax
  __int64 v434; // r8
  wchar_t *v435; // rax
  __int64 v436; // r9
  const wchar_t *v437; // r10
  wchar_t *v438; // rdx
  wchar_t *v439; // rax
  __int64 v440; // rax
  struct __crt_locale_pointers *v441; // rax
  int v442; // eax
  __int64 v443; // r8
  wchar_t *v444; // rax
  __int64 v445; // r9
  const wchar_t *v446; // r10
  __int64 v447; // rdx
  _WORD *v448; // rax
  __int64 v449; // rax
  VarLogData *v450; // rdi
  const unsigned __int8 *v451; // rbx
  const unsigned __int8 *v452; // r15
  const unsigned __int8 *v453; // rbx
  unsigned __int8 v454; // dl
  unsigned __int16 v455; // cx
  __int16 v456; // r8
  unsigned int v457; // edi
  unsigned int v458; // r8d
  int v459; // edx
  int v460; // eax
  int v461; // edx
  const unsigned __int8 *v462; // rcx
  unsigned int v463; // ebx
  __int64 v464; // rdi
  unsigned int v465; // r9d
  const unsigned __int8 *v466; // rdi
  __int64 v467; // rax
  __int64 v468; // rax
  __int64 v469; // rax
  __int64 v470; // rax
  __int64 v471; // rax
  __int64 v472; // rax
  const unsigned __int8 *v473; // rax
  unsigned int v474; // ebx
  unsigned __int16 v475; // dx
  __int16 v476; // cx
  __int16 v477; // dx
  struct RecVersioningInfo *v478; // rax
  __int64 v479; // r9
  __int64 v480; // rdx
  int v481; // r8d
  __int16 v482; // ax
  __int64 v483; // rax
  __int64 v484; // rax
  __int64 v485; // rax
  __int64 v486; // rax
  __int16 v487; // r8
  const unsigned __int8 *v488; // rax
  unsigned int v489; // edi
  unsigned int v490; // ebx
  __int64 v491; // rsi
  char *v492; // r8
  char v493; // dl
  unsigned __int16 v494; // cx
  __int16 v495; // r8
  unsigned int v496; // ebx
  unsigned int v497; // r8d
  int v498; // edx
  int v499; // eax
  const unsigned __int8 *v500; // rcx
  unsigned int v501; // ebx
  unsigned int v502; // edx
  const unsigned __int8 *v503; // rdi
  __int64 v504; // rax
  __int64 v505; // rax
  __int64 v506; // rax
  __int64 v507; // rax
  __int64 v508; // rax
  __int64 v509; // rax
  const unsigned __int8 *v510; // rax
  unsigned int v511; // ebx
  unsigned __int16 v512; // r8
  const unsigned __int8 *v513; // r8
  __int16 v514; // ax
  __int16 v515; // cx
  struct RecVersioningInfo *v516; // rax
  __int64 v517; // r9
  __int64 v518; // rdx
  int v519; // r8d
  __int16 v520; // ax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rax
  __int64 v524; // rax
  __int16 v525; // r8
  const unsigned __int8 *v526; // rax
  unsigned int v527; // edi
  unsigned int v528; // ebx
  struct __crt_locale_pointers *v529; // rax
  int v530; // eax
  __int64 v531; // rax
  __int64 v532; // r8
  const wchar_t *v533; // r9
  __int64 v534; // rdx
  _WORD *v535; // rax
  __int64 v536; // rax
  __int64 v537; // rbx
  struct __crt_locale_pointers *v538; // rax
  int v539; // eax
  __int64 v540; // rax
  __int64 v541; // r8
  const wchar_t *v542; // r9
  __int64 v543; // rdx
  _WORD *v544; // rax
  __int64 v545; // rax
  const unsigned __int8 *v546; // r12
  unsigned int v547; // r15d
  __int64 v548; // r8
  __int64 v549; // rax
  const wchar_t *v550; // r9
  __int64 v551; // rdx
  _WORD *v552; // rax
  unsigned __int16 i; // si
  int v554; // ebx
  struct __crt_locale_pointers *v555; // rax
  int v556; // eax
  __int64 v557; // rax
  char v558; // al
  __int64 v559; // rax
  wchar_t *v560; // rcx
  __int64 v561; // r8
  const wchar_t *v562; // r9
  wchar_t *v563; // rcx
  __int64 v564; // rdx
  wchar_t *v565; // rax
  __int64 v566; // rbx
  __int64 v567; // rax
  __int64 v568; // rax
  wchar_t *v569; // rcx
  __int64 v570; // r8
  wchar_t *v571; // rcx
  __int64 v572; // rdx
  const wchar_t *v573; // r9
  wchar_t *v574; // rax
  DumpLogRecord *v575; // rcx
  DumpLogRecord *v576; // rcx
  DumpLogRecord *v577; // rcx
  DumpLogRecord *v578; // rcx
  DumpLogRecord *v579; // rcx
  DumpLogRecord *v580; // rcx
  unsigned int v581; // ebx
  const wchar_t *LogicalName; // rax
  DumpLogRecord *v583; // rcx
  unsigned int v584; // ebx
  const wchar_t *PhysicalName; // rax
  DumpLogRecord *v586; // rcx
  unsigned int v587; // ebx
  const wchar_t *v588; // rax
  DumpLogRecord *v589; // rcx
  unsigned int v590; // ebx
  const wchar_t *v591; // rax
  DumpLogRecord *v592; // rcx
  unsigned __int16 v593; // si
  const struct LockMigrateLogInfo *LockMigrateInfo; // r14
  DumpLogRecord *v595; // rcx
  DumpLogRecord *v596; // rcx
  const struct HoBtId *HoBtId; // rax
  DumpLogRecord *v598; // rcx
  DumpLogRecord *v599; // rcx
  DumpLogRecord *v600; // rcx
  unsigned __int16 v601; // bx
  DumpLogRecord *v602; // rcx
  DumpLogRecord *v603; // rcx
  const wchar_t *v604; // r8
  DumpLogRecord *v605; // rcx
  const wchar_t *v606; // rax
  unsigned int v607; // r9d
  DumpLogRecord *v608; // rcx
  const struct PageId *NextExtentId; // rax
  unsigned int j; // esi
  DumpLogRecord *v611; // rcx
  DumpLogRecord *v612; // rcx
  char v613; // al
  const wchar_t *v614; // rbx
  int v615; // ecx
  int v616; // ecx
  int v617; // ecx
  const wchar_t *v618; // rdi
  struct __crt_locale_pointers *v619; // rax
  int v620; // eax
  struct __crt_locale_pointers *v621; // rax
  int v622; // eax
  struct __crt_locale_pointers *v623; // rax
  int v624; // eax
  struct __crt_locale_pointers *v625; // rax
  int v626; // eax
  struct __crt_locale_pointers *v627; // rax
  int v628; // eax
  struct __crt_locale_pointers *v629; // rax
  int v630; // eax
  DumpLogRecord *v631; // rcx
  DumpLogRecord *v632; // rcx
  int v633; // ecx
  int v634; // ecx
  int v635; // ecx
  int v636; // ecx
  struct __crt_locale_pointers *v637; // rax
  int v638; // eax
  struct __crt_locale_pointers *v639; // rax
  int v640; // eax
  struct __crt_locale_pointers *v641; // rax
  int v642; // eax
  struct __crt_locale_pointers *v643; // rax
  int v644; // eax
  struct __crt_locale_pointers *v645; // rax
  int v646; // eax
  struct __crt_locale_pointers *v647; // rax
  int v648; // eax
  struct __crt_locale_pointers *v649; // rax
  int v650; // eax
  DumpLogRecord *v651; // rcx
  DumpLogRecord *v652; // rcx
  wchar_t *CacheTypeName; // rbx
  struct __crt_locale_pointers *v654; // rax
  int v655; // eax
  DumpLogRecord *v656; // rcx
  int v657; // ebx
  struct __crt_locale_pointers *v658; // rax
  int v659; // eax
  DumpLogRecord *v660; // rcx
  __int64 v661; // r14
  struct __crt_locale_pointers *v662; // rax
  int v663; // eax
  DumpLogRecord *v664; // rcx
  struct __crt_locale_pointers *v665; // rax
  int v666; // eax
  DumpLogRecord *v667; // rcx
  unsigned int v668; // esi
  int v669; // edi
  int v670; // ebx
  struct __crt_locale_pointers *v671; // rax
  int v672; // eax
  DumpLogRecord *v673; // rcx
  struct __crt_locale_pointers *v674; // rax
  int v675; // r14d
  unsigned int v676; // esi
  int v677; // edi
  unsigned int v678; // ebx
  struct __crt_locale_pointers *v679; // rax
  int v680; // eax
  struct __crt_locale_pointers *v681; // rax
  unsigned int v682; // esi
  int v683; // edi
  int v684; // ebx
  struct __crt_locale_pointers *v685; // rax
  int v686; // eax
  DumpLogRecord *v687; // rcx
  struct __crt_locale_pointers *v688; // rax
  unsigned int v689; // esi
  int v690; // edi
  int v691; // ebx
  struct __crt_locale_pointers *v692; // rax
  int v693; // eax
  struct __crt_locale_pointers *v694; // rax
  struct __crt_locale_pointers *v695; // rax
  int v696; // eax
  DumpLogRecord *v697; // rcx
  unsigned __int64 RowsetId; // rbx
  struct __crt_locale_pointers *v699; // rax
  int v700; // eax
  DumpLogRecord *v701; // rcx
  unsigned __int16 v702; // ax
  unsigned __int16 v703; // cx
  int v704; // eax
  DumpLogRecord *v705; // rcx
  DumpLogRecord *v706; // rcx
  DumpLogRecord *v707; // rcx
  DumpLogRecord *v708; // rcx
  DumpLogRecord *v709; // rcx
  DumpLogRecord *v710; // rcx
  int v711; // eax
  DumpLogRecord *v712; // rcx
  int v713; // eax
  DumpLogRecord *v714; // rcx
  int v715; // eax
  DumpLogRecord *v716; // rcx
  unsigned __int8 v717; // al
  int v718; // ebx
  struct __crt_locale_pointers *v719; // rax
  int v720; // eax
  DumpLogRecord *v721; // rcx
  const wchar_t *v722; // rax
  __int64 v723; // rbx
  struct __crt_locale_pointers *v724; // rax
  int v725; // eax
  DumpLogRecord *v726; // rcx
  struct __crt_locale_pointers *v727; // rax
  int v728; // eax
  DumpLogRecord *v729; // rcx
  struct __crt_locale_pointers *v730; // rax
  int v731; // eax
  DumpLogRecord *v732; // rcx
  DumpLogRecord *v733; // rcx
  DumpLogRecord *v734; // rcx
  unsigned __int64 v735; // rcx
  const wchar_t *v736; // r8
  char v737; // al
  int v738; // ebx
  struct __crt_locale_pointers *v739; // rax
  int v740; // eax
  DumpLogRecord *v741; // rcx
  DumpLogRecord *v742; // rcx
  int v743; // ebx
  struct __crt_locale_pointers *v744; // rax
  int v745; // eax
  DumpLogRecord *v746; // rcx
  DumpLogRecord *v747; // rcx
  const struct PageId *PageId; // rax
  DumpLogRecord *v749; // rcx
  DumpLogRecord *v750; // rcx
  DumpLogRecord *v751; // rcx
  DumpLogRecord *v752; // rcx
  __int64 v753; // rax
  const wchar_t *v754; // r8
  struct __crt_locale_pointers *v755; // rax
  int v756; // eax
  DumpLogRecord *v757; // rcx
  unsigned __int64 I8; // rbx
  struct __crt_locale_pointers *v759; // rax
  int v760; // eax
  DumpLogRecord *v761; // rcx
  DumpLogRecord *v762; // rcx
  __int64 v763; // rbx
  struct __crt_locale_pointers *v764; // rax
  int v765; // eax
  DumpLogRecord *v766; // rcx
  DumpLogRecord *v767; // rcx
  __int16 v768; // ax
  DumpLogRecord *v769; // rcx
  DumpLogRecord *v770; // rcx
  __int16 v771; // ax
  DumpLogRecord *v772; // rcx
  unsigned int v773; // ebx
  struct __crt_locale_pointers *v774; // rax
  int v775; // eax
  DumpLogRecord *v776; // rcx
  DumpLogRecord *v777; // rcx
  const wchar_t *v778; // r8
  char v779; // cl
  __int64 v780; // rax
  DumpLogRecord *v781; // rcx
  unsigned int v782; // r14d
  unsigned int k; // edi
  unsigned int v784; // ebx
  int v785; // esi
  struct __crt_locale_pointers *v786; // r9
  int v787; // eax
  DumpLogRecord *v788; // rcx
  int v789; // eax
  int v790; // ebx
  struct __crt_locale_pointers *v791; // rax
  int v792; // eax
  DumpLogRecord *v793; // rcx
  wchar_t *v794; // r8
  const unsigned __int8 *v795; // r13
  struct LSN *v796; // rbx
  unsigned int v797; // r12d
  __int64 v798; // rax
  __int64 PageIdForStatus; // rax
  _BYTE *v800; // r15
  const unsigned __int8 *v801; // r14
  int v802; // ebx
  int v803; // edi
  struct __crt_locale_pointers *v804; // rax
  int v805; // eax
  DumpLogRecord *v806; // rcx
  wchar_t *v807; // rbx
  DumpLogRecord *v808; // rcx
  char v809; // al
  const wchar_t *v810; // r8
  __int64 v811; // rax
  __int64 v812; // r8
  __int64 v813; // rax
  DumpLogRecord *v814; // rcx
  wchar_t *v815; // rdx
  const wchar_t *v816; // r8
  __int64 v817; // rax
  __int64 v818; // r8
  __int64 v819; // rax
  int v820; // ebx
  struct __crt_locale_pointers *v821; // rax
  int v822; // eax
  DumpLogRecord *v823; // rcx
  const wchar_t *v824; // r8
  DumpLogRecord *v825; // rcx
  unsigned int *v826; // [rsp+20h] [rbp-E0h]
  unsigned int *v827; // [rsp+20h] [rbp-E0h]
  unsigned int *v828; // [rsp+20h] [rbp-E0h]
  unsigned int *v829; // [rsp+20h] [rbp-E0h]
  unsigned int *v830; // [rsp+20h] [rbp-E0h]
  unsigned int *v831; // [rsp+20h] [rbp-E0h]
  unsigned int *v832; // [rsp+20h] [rbp-E0h]
  unsigned int *v833; // [rsp+20h] [rbp-E0h]
  int v834; // [rsp+20h] [rbp-E0h]
  rsize_t DestinationSize; // [rsp+28h] [rbp-D8h]
  rsize_t DestinationSizea; // [rsp+28h] [rbp-D8h]
  unsigned int *v837; // [rsp+30h] [rbp-D0h]
  unsigned int *v838; // [rsp+30h] [rbp-D0h]
  unsigned int *v839; // [rsp+30h] [rbp-D0h]
  unsigned int v840[2]; // [rsp+38h] [rbp-C8h]
  __int64 v841; // [rsp+40h] [rbp-C0h]
  __int64 v842; // [rsp+48h] [rbp-B8h]
  int v843; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v844; // [rsp+68h] [rbp-98h]
  unsigned __int16 v845; // [rsp+6Ah] [rbp-96h] BYREF
  int v846; // [rsp+6Ch] [rbp-94h]
  const unsigned __int8 *v847; // [rsp+70h] [rbp-90h]
  PageComprMgr *v848; // [rsp+78h] [rbp-88h]
  _QWORD v849[3]; // [rsp+80h] [rbp-80h] BYREF
  int v850; // [rsp+98h] [rbp-68h]
  unsigned int v851; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v852; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v853; // [rsp+AAh] [rbp-56h] BYREF
  int v854; // [rsp+ACh] [rbp-54h]
  const unsigned __int8 *v855; // [rsp+B0h] [rbp-50h]
  PageComprMgr *v856; // [rsp+B8h] [rbp-48h]
  unsigned int v857; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v858; // [rsp+C4h] [rbp-3Ch]
  DumpLogRecord *v859; // [rsp+C6h] [rbp-3Ah]
  _TBYTE v860; // [rsp+CEh] [rbp-32h] BYREF
  int v861; // [rsp+D8h] [rbp-28h]
  __int16 v862; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v863; // [rsp+E2h] [rbp-1Eh] BYREF
  int v864; // [rsp+E4h] [rbp-1Ch]
  const unsigned __int8 *v865; // [rsp+E8h] [rbp-18h]
  PageComprMgr *v866; // [rsp+F0h] [rbp-10h]
  unsigned int v867; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v868; // [rsp+FCh] [rbp-4h]
  unsigned __int64 v869; // [rsp+FEh] [rbp-2h]
  _TBYTE v870; // [rsp+106h] [rbp+6h] BYREF
  int v871; // [rsp+110h] [rbp+10h]
  unsigned int v872; // [rsp+118h] [rbp+18h] BYREF
  int v873; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v874; // [rsp+124h] [rbp+24h]
  unsigned __int16 v875; // [rsp+126h] [rbp+26h]
  unsigned int *v876; // [rsp+128h] [rbp+28h]
  DatabaseMetaLog *v877; // [rsp+130h] [rbp+30h]
  int v878; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 v879; // [rsp+13Ch] [rbp+3Ch]
  __int16 v880; // [rsp+13Eh] [rbp+3Eh]
  unsigned int *v881; // [rsp+140h] [rbp+40h]
  unsigned int v882; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v883; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v884; // [rsp+150h] [rbp+50h] BYREF
  __int16 v885; // [rsp+154h] [rbp+54h]
  unsigned int v886; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v887; // [rsp+15Ch] [rbp+5Ch] BYREF
  unsigned int v888; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v889; // [rsp+164h] [rbp+64h] BYREF
  unsigned int v890; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v891; // [rsp+16Ch] [rbp+6Ch] BYREF
  unsigned int v892; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v893[4]; // [rsp+174h] [rbp+74h] BYREF
  unsigned int v894; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v895; // [rsp+17Ch] [rbp+7Ch] BYREF
  struct LSN *v896; // [rsp+180h] [rbp+80h]
  __int64 v897; // [rsp+188h] [rbp+88h]
  int v898; // [rsp+190h] [rbp+90h] BYREF
  __int16 v899; // [rsp+194h] [rbp+94h]
  unsigned int v900; // [rsp+198h] [rbp+98h] BYREF
  unsigned int v901; // [rsp+19Ch] [rbp+9Ch] BYREF
  unsigned int v902; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v903; // [rsp+1A4h] [rbp+A4h] BYREF
  unsigned int v904; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned int v905; // [rsp+1ACh] [rbp+ACh] BYREF
  wchar_t *v906; // [rsp+1B0h] [rbp+B0h]
  unsigned int v907; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v908; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned int v909; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v910; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v911; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v912; // [rsp+1CCh] [rbp+CCh] BYREF
  unsigned int v913; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v914; // [rsp+1D4h] [rbp+D4h] BYREF
  unsigned int v915; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v916; // [rsp+1DCh] [rbp+DCh] BYREF
  VarLogData *v917; // [rsp+1E0h] [rbp+E0h]
  int v918; // [rsp+1E8h] [rbp+E8h] BYREF
  __int16 v919; // [rsp+1ECh] [rbp+ECh]
  __int16 v920; // [rsp+1EEh] [rbp+EEh]
  unsigned int v921; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v922; // [rsp+1F4h] [rbp+F4h] BYREF
  int v923; // [rsp+1F8h] [rbp+F8h] BYREF
  __int16 v924; // [rsp+1FCh] [rbp+FCh]
  SQLDATE v925[8]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v926; // [rsp+208h] [rbp+108h]
  DumpLogRecord *v927; // [rsp+210h] [rbp+110h]
  _BYTE v928[28]; // [rsp+220h] [rbp+120h] BYREF
  int v929; // [rsp+23Ch] [rbp+13Ch]
  int v930; // [rsp+240h] [rbp+140h]
  struct _GUID v931; // [rsp+244h] [rbp+144h]
  __int16 v932; // [rsp+254h] [rbp+154h]
  unsigned int v933; // [rsp+270h] [rbp+170h] BYREF
  int v934; // [rsp+274h] [rbp+174h] BYREF
  int v935; // [rsp+278h] [rbp+178h] BYREF
  unsigned int v936; // [rsp+27Ch] [rbp+17Ch] BYREF
  unsigned int v937; // [rsp+280h] [rbp+180h] BYREF
  unsigned int v938; // [rsp+284h] [rbp+184h] BYREF
  unsigned int v939; // [rsp+288h] [rbp+188h] BYREF
  unsigned int v940; // [rsp+28Ch] [rbp+18Ch] BYREF
  unsigned int v941; // [rsp+290h] [rbp+190h] BYREF
  unsigned int v942; // [rsp+294h] [rbp+194h] BYREF
  unsigned int v943; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v944; // [rsp+29Ch] [rbp+19Ch] BYREF
  unsigned int v945; // [rsp+2A0h] [rbp+1A0h] BYREF
  const unsigned __int8 *v946; // [rsp+2A8h] [rbp+1A8h] BYREF
  unsigned int v947; // [rsp+2B0h] [rbp+1B0h]
  unsigned int v948; // [rsp+2B4h] [rbp+1B4h]
  const unsigned __int8 *v949; // [rsp+2B8h] [rbp+1B8h] BYREF
  unsigned int v950; // [rsp+2C0h] [rbp+1C0h]
  unsigned int v951; // [rsp+2C4h] [rbp+1C4h]
  const unsigned __int8 *v952; // [rsp+2C8h] [rbp+1C8h]
  const unsigned __int8 *v953; // [rsp+2D0h] [rbp+1D0h]
  const unsigned __int8 *v954; // [rsp+2D8h] [rbp+1D8h] BYREF
  unsigned int v955; // [rsp+2E0h] [rbp+1E0h]
  unsigned int v956; // [rsp+2E4h] [rbp+1E4h]
  const unsigned __int8 *v957; // [rsp+2E8h] [rbp+1E8h] BYREF
  unsigned int v958; // [rsp+2F0h] [rbp+1F0h]
  unsigned int v959; // [rsp+2F4h] [rbp+1F4h]
  _DWORD v960[9]; // [rsp+2F8h] [rbp+1F8h] BYREF
  char v961; // [rsp+31Ch] [rbp+21Ch]
  char v962[6]; // [rsp+328h] [rbp+228h] BYREF
  char v963[6]; // [rsp+32Eh] [rbp+22Eh] BYREF
  char v964[6]; // [rsp+334h] [rbp+234h] BYREF
  char v965[6]; // [rsp+33Ah] [rbp+23Ah] BYREF
  char v966[6]; // [rsp+340h] [rbp+240h] BYREF
  char v967[6]; // [rsp+346h] [rbp+246h] BYREF
  char v968[6]; // [rsp+34Ch] [rbp+24Ch] BYREF
  char v969[14]; // [rsp+352h] [rbp+252h] BYREF
  _BYTE v970[80]; // [rsp+360h] [rbp+260h] BYREF
  int v971; // [rsp+3B0h] [rbp+2B0h]
  int v972; // [rsp+3C0h] [rbp+2C0h]
  struct _GUID v973; // [rsp+3C4h] [rbp+2C4h]
  __int16 v974; // [rsp+3D4h] [rbp+2D4h]
  __int64 v975; // [rsp+3E0h] [rbp+2E0h]
  struct _GUID v976; // [rsp+3F8h] [rbp+2F8h] BYREF
  struct _GUID v977; // [rsp+408h] [rbp+308h] BYREF
  struct _GUID v978; // [rsp+418h] [rbp+318h] BYREF
  struct _GUID v979; // [rsp+428h] [rbp+328h] BYREF
  char v980[16]; // [rsp+458h] [rbp+358h] BYREF
  char v981[16]; // [rsp+468h] [rbp+368h] BYREF
  char v982[16]; // [rsp+478h] [rbp+378h] BYREF
  char v983[16]; // [rsp+488h] [rbp+388h] BYREF
  char v984[16]; // [rsp+498h] [rbp+398h] BYREF
  char v985[16]; // [rsp+4A8h] [rbp+3A8h] BYREF
  char v986[16]; // [rsp+4B8h] [rbp+3B8h] BYREF
  char v987[16]; // [rsp+4C8h] [rbp+3C8h] BYREF
  char v988[16]; // [rsp+4D8h] [rbp+3D8h] BYREF
  char v989[16]; // [rsp+4E8h] [rbp+3E8h] BYREF
  char v990[16]; // [rsp+4F8h] [rbp+3F8h] BYREF
  char v991[24]; // [rsp+508h] [rbp+408h] BYREF
  __int64 v992; // [rsp+520h] [rbp+420h] BYREF
  int v993; // [rsp+528h] [rbp+428h]
  __int64 v994; // [rsp+5E0h] [rbp+4E0h] BYREF
  int v995; // [rsp+5E8h] [rbp+4E8h]
  unsigned int v996; // [rsp+5ECh] [rbp+4ECh]
  __int64 v997; // [rsp+5F0h] [rbp+4F0h]
  __int16 v998; // [rsp+5F8h] [rbp+4F8h]
  __int64 v999; // [rsp+5FAh] [rbp+4FAh]
  unsigned __int16 v1000; // [rsp+602h] [rbp+502h]
  __int64 v1001; // [rsp+604h] [rbp+504h]
  unsigned __int16 v1002; // [rsp+60Ch] [rbp+50Ch]
  int v1003; // [rsp+60Eh] [rbp+50Eh]
  __int16 v1004; // [rsp+612h] [rbp+512h]
  int v1005; // [rsp+614h] [rbp+514h]
  __int64 v1006; // [rsp+618h] [rbp+518h]
  __int64 v1007; // [rsp+620h] [rbp+520h]
  __int64 v1008; // [rsp+628h] [rbp+528h]
  __int64 v1009; // [rsp+630h] [rbp+530h]
  _BYTE v1010[1048]; // [rsp+638h] [rbp+538h] BYREF
  __int64 v1011; // [rsp+A50h] [rbp+950h] BYREF
  int v1012; // [rsp+A58h] [rbp+958h]
  unsigned int v1013; // [rsp+A5Ch] [rbp+95Ch]
  __int64 v1014; // [rsp+A60h] [rbp+960h]
  __int16 v1015; // [rsp+A68h] [rbp+968h]
  _BYTE v1016[1046]; // [rsp+A6Ah] [rbp+96Ah] BYREF
  wchar_t v1017[24]; // [rsp+E80h] [rbp+D80h] BYREF
  wchar_t v1018[16]; // [rsp+EB0h] [rbp+DB0h] BYREF
  wchar_t v1019[40]; // [rsp+ED0h] [rbp+DD0h] BYREF
  wchar_t v1020[16]; // [rsp+F20h] [rbp+E20h] BYREF
  wchar_t v1021[24]; // [rsp+F40h] [rbp+E40h] BYREF
  wchar_t v1022[16]; // [rsp+F70h] [rbp+E70h] BYREF
  wchar_t v1023[24]; // [rsp+F90h] [rbp+E90h] BYREF
  wchar_t v1024[24]; // [rsp+FC0h] [rbp+EC0h] BYREF
  wchar_t v1025[16]; // [rsp+FF0h] [rbp+EF0h] BYREF
  wchar_t v1026[16]; // [rsp+1010h] [rbp+F10h] BYREF
  wchar_t v1027[72]; // [rsp+1030h] [rbp+F30h] BYREF
  wchar_t v1028[20]; // [rsp+10C0h] [rbp+FC0h] BYREF
  wchar_t v1029[16]; // [rsp+10E8h] [rbp+FE8h] BYREF
  wchar_t v1030[16]; // [rsp+1108h] [rbp+1008h] BYREF
  wchar_t v1031[16]; // [rsp+1128h] [rbp+1028h] BYREF
  wchar_t v1032[16]; // [rsp+1148h] [rbp+1048h] BYREF
  wchar_t v1033[16]; // [rsp+1168h] [rbp+1068h] BYREF
  wchar_t v1034[24]; // [rsp+1188h] [rbp+1088h] BYREF
  wchar_t v1035[20]; // [rsp+11B8h] [rbp+10B8h] BYREF
  wchar_t v1036[20]; // [rsp+11E0h] [rbp+10E0h] BYREF
  wchar_t v1037[24]; // [rsp+1208h] [rbp+1108h] BYREF
  wchar_t v1038[24]; // [rsp+1238h] [rbp+1138h] BYREF
  wchar_t v1039[28]; // [rsp+1268h] [rbp+1168h] BYREF
  wchar_t v1040[104]; // [rsp+12A0h] [rbp+11A0h] BYREF
  wchar_t v1041[104]; // [rsp+1370h] [rbp+1270h] BYREF
  wchar_t v1042[40]; // [rsp+1440h] [rbp+1340h] BYREF
  wchar_t v1043[40]; // [rsp+1490h] [rbp+1390h] BYREF
  wchar_t v1044[40]; // [rsp+14E0h] [rbp+13E0h] BYREF
  wchar_t v1045[40]; // [rsp+1530h] [rbp+1430h] BYREF
  wchar_t v1046[37]; // [rsp+1580h] [rbp+1480h] BYREF
  wchar_t v1047[43]; // [rsp+15CAh] [rbp+14CAh] BYREF
  wchar_t v1048[200]; // [rsp+1620h] [rbp+1520h] BYREF
  wchar_t v1049[104]; // [rsp+17B0h] [rbp+16B0h] BYREF
  wchar_t v1050[104]; // [rsp+1880h] [rbp+1780h] BYREF
  wchar_t v1051[128]; // [rsp+1950h] [rbp+1850h] BYREF
  wchar_t v1052[128]; // [rsp+1A50h] [rbp+1950h] BYREF
  wchar_t v1053[200]; // [rsp+1B50h] [rbp+1A50h] BYREF
  wchar_t v1054[104]; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  wchar_t v1055[1024]; // [rsp+1DB0h] [rbp+1CB0h] BYREF
  wchar_t v1056[128]; // [rsp+25B0h] [rbp+24B0h] BYREF
  wchar_t v1057[200]; // [rsp+26B0h] [rbp+25B0h] BYREF
  wchar_t v1058[200]; // [rsp+2840h] [rbp+2740h] BYREF
  wchar_t v1059[200]; // [rsp+29D0h] [rbp+28D0h] BYREF
  wchar_t v1060[256]; // [rsp+2B60h] [rbp+2A60h] BYREF
  wchar_t v1061[200]; // [rsp+2D60h] [rbp+2C60h] BYREF
  wchar_t v1062[368]; // [rsp+2EF0h] [rbp+2DF0h] BYREF
  wchar_t v1063[400]; // [rsp+31D0h] [rbp+30D0h] BYREF
  wchar_t v1064[400]; // [rsp+34F0h] [rbp+33F0h] BYREF
  wchar_t v1065[400]; // [rsp+3810h] [rbp+3710h] BYREF
  wchar_t v1066[600]; // [rsp+3B30h] [rbp+3A30h] BYREF
  wchar_t v1067[600]; // [rsp+3FE0h] [rbp+3EE0h] BYREF

  v975 = -2;
  v5 = a4;
  v906 = a4;
  v6 = a3;
  v877 = a3;
  v896 = a2;
  v927 = this;
  *a4 = 0;
  v843 = 1;
  if ( (unsigned int)GetLogRecDateTime(a3, (struct SQLDATE *)v925) )
  {
    v961 = 0;
    SQLDATE::DateToParts(v925, (struct dateparts *)v960);
    SQLDATE::TimeToParts(v925, (struct dateparts *)v960);
    v8 = v960[1] + 1;
    DefaultLocale = GetDefaultLocale();
    v10 = StringCchPrintf_lW(
            v1034,
            0x18u,
            L"%04d/%02d/%02d %02d:%02d:%02d:%03d",
            DefaultLocale,
            v960[0],
            v8,
            v960[2],
            v960[5],
            v960[6],
            v960[7],
            v960[8]);
    if ( v10 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v10;
      LODWORD(DestinationSize) = 3151;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
    }
    v11 = a5;
    if ( a5 && (int)StringCchCatW(v5, 0x100u, v1034) >= 0 )
    {
      v7 = (unsigned __int64)v1034;
      v12 = -1;
      do
        ++v12;
      while ( v1034[v12] );
      v11 -= v12;
      a5 = v11;
      v843 = 0;
    }
  }
  else
  {
    v11 = a5;
  }
  if ( (*((_BYTE *)v6 + 14) & 4) != 0 && v11 )
  {
    if ( v843 )
      goto LABEL_25;
    v13 = 256;
    v7 = (unsigned __int64)v5;
    do
    {
      if ( !*(_WORD *)v7 )
        break;
      v7 += 2LL;
      --v13;
    }
    while ( v13 );
    if ( v13 )
    {
      v14 = 1;
      v15 = L";";
      v7 = (unsigned __int64)&v5[256 - v13];
      v16 = v13;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *(_WORD *)v7 = *v15;
        v7 += 2LL;
        ++v15;
        --v14;
        --v16;
      }
      while ( v16 );
      v17 = (_WORD *)(v7 - 2);
      if ( v16 )
        v17 = (_WORD *)v7;
      *v17 = 0;
      if ( v16 )
      {
        a5 = --v11;
LABEL_25:
        if ( (int)StringCchCatW(v5, 0x100u, L"REPLICATE") >= 0 )
        {
          v11 -= 9;
          a5 = v11;
          v843 = 0;
        }
      }
    }
  }
  if ( (*((_BYTE *)v6 + 14) & 1) == 0 || !v11 )
    goto LABEL_44;
  if ( v843 )
    goto LABEL_42;
  v18 = 256;
  v7 = (unsigned __int64)v5;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2LL;
    --v18;
  }
  while ( v18 );
  if ( v18 )
  {
    v19 = 1;
    v20 = L";";
    v7 = (unsigned __int64)&v5[256 - v18];
    v21 = v18;
    do
    {
      if ( !v19 )
        break;
      if ( !*v20 )
        break;
      *(_WORD *)v7 = *v20;
      v7 += 2LL;
      ++v20;
      --v19;
      --v21;
    }
    while ( v21 );
    v22 = (_WORD *)(v7 - 2);
    if ( v21 )
      v22 = (_WORD *)v7;
    *v22 = 0;
    if ( v21 )
    {
      a5 = --v11;
LABEL_42:
      if ( (int)StringCchCatW(v5, 0x100u, L"COMPENSATION") >= 0 )
      {
        v11 -= 12;
        a5 = v11;
        v843 = 0;
      }
    }
  }
LABEL_44:
  if ( *((_BYTE *)v6 + 22) != 5 )
    goto LABEL_67;
  switch ( *((_WORD *)v6 + 28) )
  {
    case 1:
      v23 = L"m_type";
      break;
    case 2:
      v23 = L"m_typeFlagBits";
      break;
    case 3:
      v23 = L"m_level";
      break;
    case 4:
      v23 = L"m_flagBits";
      break;
    case 8:
      v23 = L"m_prevPage";
      break;
    case 0xE:
      v23 = L"m_fixedLength";
      break;
    case 0x10:
      v23 = L"m_nextPage";
      break;
    case 0x16:
      v23 = L"m_slotCnt";
      break;
    case 0x1C:
      v23 = L"m_freeCnt";
      break;
    case 0x1E:
      v23 = L"m_freeData";
      break;
    case 0x20:
      v23 = L"m_pageId";
      break;
    case 0x26:
      v23 = L"m_reservedCnt";
      break;
    case 0x3A:
      v23 = L"m_ghostRecCnt";
      break;
    default:
      goto LABEL_67;
  }
  Data = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 62), 1u, &v933);
  if ( !Data )
    goto LABEL_67;
  v25 = *Data;
  v26 = GetDefaultLocale();
  LODWORD(DestinationSize) = v25;
  v27 = StringCchPrintf_lW(v1049, 0x64u, L"Field %s . Value: %02lx.", v26, v23, DestinationSize);
  if ( v27 < 0 )
  {
    _mm_lfence();
    LODWORD(v837) = v27;
    LODWORD(DestinationSize) = 7919;
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
    v11 = a5;
  }
  if ( v11 && (int)StringCchCatW(v5, 0x100u, v1049) >= 0 )
  {
    v7 = (unsigned __int64)v1049;
    v28 = -1;
    do
      ++v28;
    while ( v1049[v28] );
    v11 -= v28;
    a5 = v11;
    v29 = 0;
    v843 = 0;
  }
  else
  {
LABEL_67:
    v29 = 0;
  }
  if ( *((_BYTE *)v6 + 22) == 16 )
  {
    v862 = -1;
    v865 = 0;
    v864 = 0;
    v869 = 0;
    *(_QWORD *)((char *)&v870 + 2) = 0;
    v866 = 0;
    v852 = -1;
    v855 = 0;
    v854 = 0;
    v859 = 0;
    *(_QWORD *)((char *)&v860 + 2) = 0;
    v856 = 0;
    if ( *((_WORD *)v6 + 31) >= 2u )
    {
      v30 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 62), 0, &v888);
      v89 = (*v30 & 1) == 0;
      v855 = v30;
      if ( v89 )
      {
        v852 = 0;
        LODWORD(v860) = 0;
        switch ( *v30 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v29 = *((unsigned __int16 *)v30 + 1);
            if ( v29 - 1 > 0x1F9D )
              RaiseInconsistencyError(v30, 6);
            break;
          case 1:
          case 3:
          case 5:
          case 7:
          case 9:
          case 0xB:
          case 0xD:
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
              294,
              "Invalid switch value");
            break;
          case 4:
            v29 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v29 = 1;
            break;
        }
        LODWORD(v856) = v29;
LABEL_92:
        v34 = v854;
      }
      else
      {
        v852 = 1;
        v31 = *v30;
        switch ( *v30 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( *((char *)v30 + 1) < 0 )
            {
              v32 = HIBYTE(*(_WORD *)(v30 + 1)) | ((*(_WORD *)(v30 + 1) & 0x7F) << 8);
              v853 = v32;
              LOWORD(v857) = 3;
              v33 = 3;
            }
            else
            {
              v32 = v30[1];
              v853 = v32;
              LOWORD(v857) = 2;
              v33 = 2;
            }
            v858 = v33 + (((unsigned int)v32 + 1) >> 1);
            if ( v32 > 0x1Eu )
              HIWORD(v857) = (v32 - 1) / 30;
            else
              HIWORD(v857) = 0;
            v861 = 0;
            goto LABEL_92;
          case 1:
          case 2:
          case 3:
          case 5:
          case 6:
          case 7:
          case 9:
          case 0xA:
          case 0xB:
          case 0xD:
          case 0xE:
          case 0xF:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x19:
          case 0x1A:
          case 0x1B:
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
            goto LABEL_92;
          case 4:
            if ( (v31 & 0x1C) == 4 && (v31 & 2) != 0 )
            {
              v857 = 0;
              v853 = 0;
              v858 = 0;
              LOWORD(v860) = 0;
              v34 = 15;
              v854 = 15;
              v861 = 1;
            }
            else
            {
              v857 = 0;
              v853 = 0;
              v858 = 0;
              LOWORD(v860) = 0;
              v34 = 1;
              v854 = 1;
              v861 = 0;
            }
            break;
          case 8:
            v857 = 0;
            v853 = 0;
            v858 = 0;
            LOWORD(v860) = 0;
            v34 = 9;
            v854 = 9;
            v861 = 0;
            break;
        }
      }
      if ( v852 )
      {
        if ( !v34 )
        {
          CDRecord::Resize((CDRecord *)&v853);
          v34 = v854;
        }
        if ( v34 < 9 && ((*v855 & 0x1C) == 0 || (*v855 & 0x1C) == 0xC) )
          v34 = 9;
      }
      else
      {
        if ( !v34 )
        {
          v853 = 0;
          HIDWORD(v856) = v29;
          v34 = v29;
          if ( (*v855 & 0x10) != 0 )
          {
            v34 = (((unsigned int)*(unsigned __int16 *)&v855[v29] + 7) >> 3) + v29 + 2;
            HIDWORD(v856) = v34;
          }
          if ( (*v855 & 0x20) != 0 )
          {
            v35 = &v855[v34];
            v36 = *(_WORD *)v35;
            v858 = v36;
            if ( !v36 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v37 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v37 )
                {
                  v38 = *(_QWORD *)(v37 + 96);
                  if ( v38 )
                  {
                    if ( *(_BYTE *)(v38 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v855, 3);
              v36 = v858;
            }
            v39 = HIDWORD(v856) + 2 + 2 * v36;
            v857 = v39;
            if ( v39 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v40 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v40 )
                {
                  v41 = *(_QWORD *)(v40 + 96);
                  if ( v41 )
                  {
                    if ( *(_BYTE *)(v41 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v855, 4);
              v36 = v858;
              v39 = v857;
            }
            v34 = *(_WORD *)&v35[2 * v36] & 0x7FFF;
            v854 = v34;
            if ( v39 > v34 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v42 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v42 )
                {
                  v43 = *(_QWORD *)(v42 + 96);
                  if ( v43 )
                  {
                    if ( *(_BYTE *)(v43 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v855, 4);
              v36 = v858;
              v39 = v857;
              v34 = v854;
            }
            while ( *(__int16 *)&v35[2 * v36] < 0 )
            {
              v44 = &v855[HIDWORD(v856)];
              if ( v36 == 1 )
                v45 = v39;
              else
                v45 = *(_WORD *)&v44[2 * v36 - 2] & 0x7FFF;
              if ( v45 < v39 || (*(_WORD *)&v44[2 * v36] & 0x7FFFu) < v45 )
              {
                RaiseInconsistencyError(v855, 7);
                v36 = v858;
                v39 = v857;
                v34 = v854;
              }
              if ( v45 < v39 || v45 > v34 )
                goto LABEL_185;
              v46 = *(_WORD *)&v855[v45];
              if ( v46 == 5 )
              {
                v853 |= 2u;
                v858 = v36 - 1;
                WORD2(v860) = v45;
                v47 = *(_WORD *)&v855[(unsigned __int16)v45 + 2];
                v48 = WORD3(v860) & 0xC7FF;
                if ( (v47 & 0x4000) != 0 )
                  v48 = WORD3(v860) ^ (WORD3(v860) ^ v47) & 0x3800;
                WORD3(v860) = v48 ^ (v47 ^ v48) & 0x7FF;
                break;
              }
              if ( v46 >= 0x400u )
              {
                v853 |= 1u;
                v89 = v36-- == 1;
                v858 = v36;
                if ( !v89 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v854 = v34;
            v858 = 0;
            v857 = v34;
          }
          if ( (*v855 & 0x40) != 0 )
          {
            LODWORD(v860) = v34;
            v854 = v34 + 14;
            VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v853);
            v50 = HIDWORD(*(_QWORD *)VersioningInfo);
            v51 = HIWORD(*(_QWORD *)VersioningInfo);
            v52 = 0;
            if ( (((__int16)v51 ^ ((unsigned int)(__int16)v51 >> 1)) & 0x2000) != 0 )
            {
              v53 = v51 & 0xDFFF;
              if ( (v51 & 0x4000) != 0 )
                v53 = v51 | 0x2000;
              LOWORD(v51) = v53;
            }
            if ( (_WORD)v51 == 0xFFFC )
              v52 = (unsigned __int16)v50 >> 5;
            v34 = v52 + v854;
            v854 += v52;
          }
          else
          {
            LODWORD(v860) = 0;
          }
          if ( v859 && v859 < (DumpLogRecord *)&v855[v34] )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v54 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL);
              if ( v54 )
              {
                v55 = *(_QWORD *)(v54 + 96);
                if ( v55 )
                {
                  if ( *(_BYTE *)(v55 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
              v11 = a5;
            }
            RaiseInconsistencyError(v855, 18);
            v34 = v854;
          }
          if ( v34 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v56 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL);
              if ( v56 )
              {
                v57 = *(_QWORD *)(v56 + 96);
                if ( v57 )
                {
                  if ( *(_BYTE *)(v57 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
              v11 = a5;
            }
            RaiseInconsistencyError(v855, 5);
            v34 = v854;
          }
        }
LABEL_185:
        if ( v34 < 9 )
        {
          v58 = *v855 & 0xE;
          if ( !v58 || v58 == 12 )
            v34 = 9;
        }
      }
      if ( v888 != v34 )
        utassert_fail(1u, "fileHeaderRowSize == oldFileHdr.Size()", "dumplog.cpp", 7946, 0);
      v59 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 62), 1u, &v888);
      v60 = v59;
      v89 = (*v59 & 1) == 0;
      v865 = v59;
      if ( v89 )
      {
        v862 = 0;
        v66 = 0;
        LODWORD(v870) = 0;
        switch ( *v59 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v66 = *((unsigned __int16 *)v59 + 1);
            if ( v66 - 1 > 0x1F9D )
              RaiseInconsistencyError(v59, 6);
            break;
          case 1:
          case 3:
          case 5:
          case 7:
          case 9:
          case 0xB:
          case 0xD:
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
              294,
              "Invalid switch value");
            break;
          case 4:
            v66 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v66 = 1;
            break;
        }
        LODWORD(v866) = v66;
        v65 = v864;
      }
      else
      {
        v862 = 1;
        v61 = *v59;
        switch ( *v59 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            v62 = v59[1];
            if ( (v62 & 0x80u) != 0 )
            {
              v63 = HIBYTE(*(_WORD *)(v60 + 1)) | ((*(_WORD *)(v60 + 1) & 0x7F) << 8);
              v863 = v63;
              LOWORD(v867) = 3;
              v64 = 3;
            }
            else
            {
              v63 = v62;
              v863 = v62;
              LOWORD(v867) = 2;
              v64 = 2;
            }
            v868 = v64 + (((unsigned int)v63 + 1) >> 1);
            if ( v63 > 0x1Eu )
              HIWORD(v867) = (v63 - 1) / 30;
            else
              HIWORD(v867) = 0;
            v871 = 0;
            v65 = v864;
            v66 = 0;
            break;
          case 1:
          case 2:
          case 3:
          case 5:
          case 6:
          case 7:
          case 9:
          case 0xA:
          case 0xB:
          case 0xD:
          case 0xE:
          case 0xF:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x19:
          case 0x1A:
          case 0x1B:
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
            v65 = v864;
            v66 = 0;
            break;
          case 4:
            if ( (v61 & 0x1C) == 4 && (v61 & 2) != 0 )
            {
              v867 = 0;
              v863 = 0;
              v868 = 0;
              LOWORD(v870) = 0;
              v65 = 15;
              v864 = 15;
              v871 = 1;
              v66 = 0;
            }
            else
            {
              v867 = 0;
              v863 = 0;
              v868 = 0;
              LOWORD(v870) = 0;
              v65 = 1;
              v864 = 1;
              v871 = 0;
              v66 = 0;
            }
            break;
          case 8:
            v867 = 0;
            v863 = 0;
            v868 = 0;
            LOWORD(v870) = 0;
            v65 = 9;
            v864 = 9;
            v871 = 0;
            v66 = 0;
            break;
        }
      }
      if ( v862 )
      {
        if ( !v65 )
        {
          CDRecord::Resize((CDRecord *)&v863);
          v65 = v864;
        }
        if ( v65 >= 9 )
          goto LABEL_322;
        if ( (*v865 & 0x1C) != 0 )
        {
          v89 = (*v865 & 0x1C) == 12;
LABEL_320:
          if ( v89 )
            goto LABEL_321;
LABEL_322:
          v90 = v65;
LABEL_323:
          if ( v888 != v90 )
          {
            utassert_fail(1u, "fileHeaderRowSize == newFileHdr.Size()", "dumplog.cpp", 7951, 0);
            v65 = v864;
          }
          PhysicalColumnAttribute::Init((PhysicalColumnAttribute *)&v873, -5, 5u, 0, 0);
          if ( v862 )
          {
            v900 = 0;
            v95 = CDRecord::LocateColumnInternal(
                    (CDRecord *)&v863,
                    (const struct PhysicalColumnAttribute *)&v873,
                    (int)v91,
                    &v872,
                    &v900);
            if ( v862 && v866 && *(_QWORD *)v866 && (v875 & 8) == 0 && (v900 & 1) == 0 )
            {
              if ( !v95 || v95 == &g_bitValueOne )
              {
                v872 = 0;
                v95 = 0;
              }
              else
              {
                LODWORD(DestinationSize) = 0;
                v95 = PageComprMgr::DecompressColumnPartialInline(
                        v866,
                        (const struct PhysicalColumnAttribute *)&v873,
                        v95,
                        v872,
                        0,
                        DestinationSize,
                        &v872,
                        v900);
              }
            }
          }
          else
          {
            if ( (v873 & 0xC0000000) != 0x80000000 )
            {
              v92 = *v865;
              if ( (*v865 & 0x10) != 0 )
              {
                if ( v873 < (int)v866 )
                {
                  LODWORD(v91) = (_DWORD)v866;
                  if ( *(unsigned __int16 *)&v865[(unsigned int)v866] >= (unsigned int)v874 )
                  {
                    LOBYTE(v93) = v865[((unsigned __int64)((unsigned int)v874 - 1) >> 3) + 2 + (unsigned int)v866] >> ((v874 - 1) & 7);
                    v94 = 1;
                  }
                  else
                  {
                    v93 = ~(v875 >> 4);
                    v94 = 0;
                  }
                }
                else
                {
                  v93 = ~(v875 >> 4);
                  v94 = 0;
                }
              }
              else
              {
                if ( ((1 << (v92 & 0xE)) & 0x1105) == 0 )
                  goto LABEL_340;
                v93 = ~(v875 >> 4);
                v94 = 0;
              }
              if ( (v93 & 1) != 0 )
              {
                v95 = 0;
                v96 = 0;
LABEL_460:
                v872 = v96;
                goto LABEL_461;
              }
              if ( !v94 && (v875 & 0x10) != 0 )
              {
                v95 = (const unsigned __int8 *)(v876 + 1);
                v96 = *v876;
                goto LABEL_460;
              }
LABEL_340:
              if ( v873 >= 0 )
              {
                if ( (v875 & 8) != 0 )
                {
                  v91 = &v865[v873];
                  v95 = &g_bitValueOne;
                  if ( ((unsigned __int8)(1 << (v875 & 7)) & *v91) == 0 )
                    v95 = &g_bitValueZero;
                  v96 = 1;
                  goto LABEL_460;
                }
                if ( (v875 & 0x10) == 0 )
                  goto LABEL_345;
                if ( (*v865 & 0x10) != 0 )
                {
                  if ( v873 < (int)v866 && *(_WORD *)&v865[(unsigned int)v866] >= v874 )
                    goto LABEL_345;
                }
                else if ( ((1 << (v92 & 0xE)) & 0x1105) == 0 )
                {
LABEL_345:
                  v95 = &v865[v873];
                  v96 = 0;
                  goto LABEL_460;
                }
                v95 = (const unsigned __int8 *)(v876 + 1);
                v96 = *v876;
                goto LABEL_460;
              }
              if ( !v65 )
              {
                v863 = 0;
                v97 = (unsigned int)v866;
                HIDWORD(v866) = (_DWORD)v866;
                if ( (*v865 & 0x10) != 0 )
                {
                  v97 = (((unsigned int)*(unsigned __int16 *)&v865[(unsigned int)v866] + 7) >> 3) + (_DWORD)v866 + 2;
                  HIDWORD(v866) = v97;
                }
                if ( (*v865 & 0x20) != 0 )
                {
                  v98 = &v865[v97];
                  v868 = *(_WORD *)v98;
                  if ( !v868 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v99 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL);
                      if ( v99 )
                      {
                        v100 = *(_QWORD *)(v99 + 96);
                        if ( v100 )
                        {
                          if ( *(_BYTE *)(v100 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                            else
                              ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                      v11 = a5;
                    }
                    RaiseInconsistencyError(v865, 3);
                  }
                  v867 = HIDWORD(v866) + 2 * (v868 + 1);
                  if ( v867 > 0x1F9E )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v101 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v101 )
                      {
                        v102 = *(_QWORD *)(v101 + 96);
                        if ( v102 )
                        {
                          if ( *(_BYTE *)(v102 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                      v11 = a5;
                    }
                    RaiseInconsistencyError(v865, 4);
                  }
                  v97 = *(_WORD *)&v98[2 * v868] & 0x7FFF;
                  v864 = v97;
                  if ( v867 > v97 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v103 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v103 )
                      {
                        v104 = *(_QWORD *)(v103 + 96);
                        if ( v104 )
                        {
                          if ( *(_BYTE *)(v104 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                      v11 = a5;
                    }
                    RaiseInconsistencyError(v865, 4);
                    v97 = v864;
                  }
                  while ( *(__int16 *)&v98[2 * v868] < 0 )
                  {
                    v105 = &v865[HIDWORD(v866)];
                    if ( v868 == 1 )
                      v106 = v867;
                    else
                      v106 = *(_WORD *)&v105[2 * v868 - 2] & 0x7FFF;
                    if ( v106 < v867 || (*(_WORD *)&v105[2 * v868] & 0x7FFFu) < v106 )
                    {
                      RaiseInconsistencyError(v865, 7);
                      v97 = v864;
                    }
                    if ( v106 < v867 || v106 > v97 )
                      goto LABEL_445;
                    v107 = *(_WORD *)&v865[v106];
                    if ( v107 == 5 )
                    {
                      v863 |= 2u;
                      --v868;
                      WORD2(v870) = v106;
                      v108 = &v865[(unsigned __int16)v106];
                      v109 = *((_WORD *)v108 + 1);
                      if ( (v109 & 0x4000) != 0 )
                        v110 = (WORD3(v870) ^ v109) & 0x3800 ^ WORD3(v870);
                      else
                        v110 = WORD3(v870) & 0xC7FF;
                      WORD3(v870) = v110;
                      WORD3(v870) = v110 ^ (*((_WORD *)v108 + 1) ^ v110) & 0x7FF;
                      break;
                    }
                    if ( v107 >= 0x400u )
                    {
                      v863 |= 1u;
                      if ( --v868 )
                        continue;
                    }
                    break;
                  }
                }
                else
                {
                  v864 = v97;
                  v868 = 0;
                  v867 = v97;
                }
                if ( (*v865 & 0x40) != 0 )
                {
                  LODWORD(v870) = v97;
                  v864 = v97 + 14;
                  v111 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v863);
                  v112 = HIDWORD(*(_QWORD *)v111);
                  v113 = HIWORD(*(_QWORD *)v111);
                  v114 = 0;
                  if ( (((__int16)v113 ^ ((unsigned int)(__int16)v113 >> 1)) & 0x2000) != 0 )
                  {
                    v115 = v113 & 0xDFFF;
                    if ( (v113 & 0x4000) != 0 )
                      v115 = v113 | 0x2000;
                    LOWORD(v113) = v115;
                  }
                  if ( (_WORD)v113 == 0xFFFC )
                    v114 = (unsigned __int16)v112 >> 5;
                  v97 = v114 + v864;
                  v864 += v114;
                }
                else
                {
                  LODWORD(v870) = 0;
                }
                if ( v869 && v869 < (unsigned __int64)&v865[v97] )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v116 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v116 )
                    {
                      v117 = *(_QWORD *)(v116 + 96);
                      if ( v117 )
                      {
                        if ( *(_BYTE *)(v117 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                          else
                            ex_raise(34, 68, 21, 1018);
                        }
                      }
                    }
                    v11 = a5;
                  }
                  RaiseInconsistencyError(v865, 18);
                  v97 = v864;
                }
                if ( v97 - 1 > 0x3F3B )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v118 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v118 )
                    {
                      v119 = *(_QWORD *)(v118 + 96);
                      if ( v119 )
                      {
                        if ( *(_BYTE *)(v119 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                          else
                            ex_raise(34, 68, 21, 1005);
                        }
                      }
                    }
                    v11 = a5;
                  }
                  RaiseInconsistencyError(v865, 5);
                }
              }
LABEL_445:
              LODWORD(v91) = (unsigned __int16)v873;
              LOWORD(v91) = -(__int16)v873;
              if ( (v875 & 0x10) != 0 )
              {
                if ( (*v865 & 0x10) == 0 )
                {
                  if ( ((1 << (*v865 & 0xE)) & 0x1105) == 0 )
                    goto LABEL_448;
LABEL_453:
                  v95 = (const unsigned __int8 *)(v876 + 1);
                  v96 = *v876;
                  goto LABEL_460;
                }
                if ( v873 >= (int)v866 || *(_WORD *)&v865[(unsigned int)v866] < v874 )
                  goto LABEL_453;
              }
LABEL_448:
              if ( (__int16)v91 > (unsigned int)v868 )
              {
                v95 = v865;
                v96 = 0;
              }
              else
              {
                v120 = &v865[HIDWORD(v866)];
                if ( (__int16)v91 == 1 )
                {
                  v121 = v867;
                }
                else
                {
                  _mm_lfence();
                  v121 = *(_WORD *)&v120[2 * (__int16)v91 - 2] & 0x7FFF;
                  v11 = a5;
                }
                v122 = *(_WORD *)&v120[2 * (__int16)v91] & 0x7FFF;
                if ( v121 < v867 || v122 < v121 )
                  RaiseInconsistencyError(v865, 7);
                v95 = &v865[v121];
                v96 = v122 - v121;
              }
              goto LABEL_460;
            }
            if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v863) )
            {
              v95 = FixedVarSparseVector::LocateColumn(
                      (FixedVarSparseVector *)((char *)&v870 + 4),
                      (const struct PhysicalColumnAttribute *)&v873,
                      &v872,
                      &v934);
            }
            else
            {
              v872 = 0;
              v95 = 0;
            }
          }
LABEL_461:
          v123 = *(_DWORD *)v95;
          if ( v852 )
          {
            v883 = 0;
            v129 = CDRecord::LocateColumnInternal(
                     (CDRecord *)&v853,
                     (const struct PhysicalColumnAttribute *)&v873,
                     (int)v91,
                     &v872,
                     &v883);
            v7 = (unsigned __int64)v856;
            if ( v856 && *(_QWORD *)v856 && (v875 & 8) == 0 && (v883 & 1) == 0 )
            {
              if ( !v129 || v129 == &g_bitValueOne )
              {
                v872 = 0;
                v129 = 0;
              }
              else
              {
                LODWORD(DestinationSize) = 0;
                v129 = PageComprMgr::DecompressColumnPartialInline(
                         v856,
                         (const struct PhysicalColumnAttribute *)&v873,
                         v129,
                         v872,
                         0,
                         DestinationSize,
                         &v872,
                         v883);
              }
            }
            goto LABEL_621;
          }
          if ( (v873 & 0xC0000000) == 0x80000000 )
          {
            if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v853) )
            {
              v129 = FixedVarSparseVector::LocateColumn(
                       (FixedVarSparseVector *)((char *)&v860 + 4),
                       (const struct PhysicalColumnAttribute *)&v873,
                       &v872,
                       &v935);
            }
            else
            {
              v872 = 0;
              v129 = 0;
            }
            goto LABEL_621;
          }
          v124 = v855;
          v125 = *v855;
          v126 = (int)v856;
          if ( (*v855 & 0x10) != 0 )
          {
            if ( v873 < (int)v856 )
            {
              if ( *(unsigned __int16 *)&v855[(unsigned int)v856] >= (unsigned int)v874 )
              {
                LOBYTE(v128) = v855[((unsigned __int64)((unsigned int)v874 - 1) >> 3) + 2 + (unsigned int)v856] >> ((v874 - 1) & 7);
                v7 = 1;
              }
              else
              {
                v128 = ~(v875 >> 4);
                v7 = 0;
              }
            }
            else
            {
              v128 = ~(v875 >> 4);
              v7 = 0;
            }
            v127 = v128 & 1;
          }
          else
          {
            v7 = v125;
            LOBYTE(v7) = v125 & 0xE;
            if ( ((1 << (v125 & 0xE)) & 0x1105) == 0 )
              goto LABEL_489;
            v127 = ((v875 >> 4) & 1) == 0;
            v7 = 0;
          }
          if ( v127 )
          {
            v129 = 0;
            v872 = 0;
            goto LABEL_621;
          }
          if ( !(_DWORD)v7 && (v875 & 0x10) != 0 )
          {
            v7 = (unsigned __int64)v876;
            v129 = (const unsigned __int8 *)(v876 + 1);
            v872 = *v876;
            goto LABEL_621;
          }
LABEL_489:
          if ( v873 >= 0 )
          {
            if ( (v875 & 8) != 0 )
            {
              v129 = &g_bitValueOne;
              v7 = (unsigned __int64)&g_bitValueZero;
              if ( ((unsigned __int8)(1 << (v875 & 7)) & v855[v873]) == 0 )
                v129 = &g_bitValueZero;
              v872 = 1;
              goto LABEL_621;
            }
            if ( (v875 & 0x10) == 0 )
              goto LABEL_494;
            if ( (*v855 & 0x10) != 0 )
            {
              if ( v873 < (int)v856 && *(_WORD *)&v855[(unsigned int)v856] >= v874 )
                goto LABEL_494;
            }
            else
            {
              v130 = v125 & 0xE;
              v7 = v130;
              if ( ((1 << v130) & 0x1105) == 0 )
              {
LABEL_494:
                v129 = &v855[v873];
                v872 = 0;
                goto LABEL_621;
              }
            }
            goto LABEL_497;
          }
          if ( !v854 )
          {
            v853 = 0;
            HIDWORD(v856) = (_DWORD)v856;
            v131 = (unsigned int)v856;
            if ( (*v855 & 0x10) != 0 )
            {
              v7 = ((unsigned int)*(unsigned __int16 *)&v855[(unsigned int)v856] + 7) >> 3;
              v131 = v7 + (_DWORD)v856 + 2;
              HIDWORD(v856) = v131;
            }
            if ( (*v855 & 0x20) != 0 )
            {
              v132 = &v855[v131];
              v858 = *(_WORD *)v132;
              if ( !v858 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v133 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v133 )
                  {
                    v134 = *(_QWORD *)(v133 + 96);
                    if ( v134 )
                    {
                      if ( *(_BYTE *)(v134 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                        else
                          ex_raise(34, 68, 21, 1003);
                      }
                    }
                  }
                  v11 = a5;
                  v124 = v855;
                }
                RaiseInconsistencyError(v124, 3);
                v124 = v855;
              }
              v131 = HIDWORD(v856) + 2 * (v858 + 1);
              v857 = v131;
              if ( v131 > 0x1F9E )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v135 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v135 )
                  {
                    v136 = *(_QWORD *)(v135 + 96);
                    if ( v136 )
                    {
                      if ( *(_BYTE *)(v136 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                  v11 = a5;
                  v124 = v855;
                }
                RaiseInconsistencyError(v124, 4);
                v131 = v857;
                v124 = v855;
              }
              v137 = *(_WORD *)&v132[2 * v858] & 0x7FFF;
              v854 = v137;
              if ( v131 > v137 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v138 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v138 )
                  {
                    v139 = *(_QWORD *)(v138 + 96);
                    if ( v139 )
                    {
                      if ( *(_BYTE *)(v139 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                  v11 = a5;
                  v124 = v855;
                }
                RaiseInconsistencyError(v124, 4);
                v131 = v857;
                v124 = v855;
                v137 = v854;
              }
              while ( 1 )
              {
                if ( *(__int16 *)&v132[2 * v858] >= 0 )
                {
LABEL_553:
                  v126 = (int)v856;
                  goto LABEL_560;
                }
                v140 = &v124[HIDWORD(v856)];
                if ( v858 == 1 )
                  v141 = v131;
                else
                  v141 = *(_WORD *)&v140[2 * v858 - 2] & 0x7FFF;
                if ( v141 < v131 || (*(_WORD *)&v140[2 * v858] & 0x7FFFu) < v141 )
                {
                  RaiseInconsistencyError(v124, 7);
                  v131 = v857;
                  v124 = v855;
                  v137 = v854;
                }
                if ( v141 < v131 || v141 > v137 )
                {
                  v126 = (int)v856;
                  goto LABEL_595;
                }
                v7 = *(unsigned __int16 *)&v124[v141];
                if ( (_WORD)v7 == 5 )
                  break;
                if ( (unsigned __int16)v7 >= 0x400u )
                {
                  v853 |= 1u;
                  if ( --v858 )
                    continue;
                }
                goto LABEL_553;
              }
              v853 |= 2u;
              --v858;
              WORD2(v860) = v141;
              v142 = *(_WORD *)&v124[(unsigned __int16)v141 + 2];
              if ( (v142 & 0x4000) != 0 )
                v143 = (WORD3(v860) ^ v142) & 0x3800 ^ WORD3(v860);
              else
                v143 = WORD3(v860) & 0xC7FF;
              WORD3(v860) = v143;
              WORD3(v860) = v143 ^ (*(_WORD *)&v124[(unsigned __int16)v141 + 2] ^ v143) & 0x7FF;
              v126 = (int)v856;
            }
            else
            {
              v137 = v131;
              v854 = v131;
              v858 = 0;
              v857 = v131;
            }
LABEL_560:
            if ( (*v124 & 0x40) != 0 )
            {
              LODWORD(v860) = v137;
              v854 = v137 + 14;
              v144 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v853);
              v145 = HIDWORD(*(_QWORD *)v144);
              v146 = HIWORD(*(_QWORD *)v144);
              v147 = 0;
              if ( (((__int16)v146 ^ ((unsigned int)(__int16)v146 >> 1)) & 0x2000) != 0 )
              {
                v148 = v146 & 0xDFFF;
                if ( (v146 & 0x4000) != 0 )
                  v148 = v146 | 0x2000;
                LOWORD(v146) = v148;
              }
              if ( (_WORD)v146 == 0xFFFC )
                v147 = (unsigned __int16)v145 >> 5;
              v137 = v147 + v854;
              v854 += v147;
              v131 = v857;
              v126 = (int)v856;
              v124 = v855;
            }
            else
            {
              LODWORD(v860) = 0;
            }
            v7 = (unsigned __int64)v859;
            if ( v859 && v859 < (DumpLogRecord *)&v124[v137] )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v149 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v149 )
                {
                  v150 = *(_QWORD *)(v149 + 96);
                  if ( v150 )
                  {
                    if ( *(_BYTE *)(v150 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                      else
                        ex_raise(34, 68, 21, 1018);
                    }
                  }
                }
                v11 = a5;
                v124 = v855;
              }
              RaiseInconsistencyError(v124, 18);
              v131 = v857;
              v126 = (int)v856;
              v124 = v855;
              v137 = v854;
            }
            if ( v137 - 1 <= 0x3F3B )
              goto LABEL_595;
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v151 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v151 )
              {
                v152 = *(_QWORD *)(v151 + 96);
                if ( v152 )
                {
                  if ( *(_BYTE *)(v152 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
              v11 = a5;
              v124 = v855;
            }
            RaiseInconsistencyError(v124, 5);
            v126 = (int)v856;
            v124 = v855;
          }
          v131 = v857;
LABEL_595:
          LOWORD(v153) = -(__int16)v873;
          if ( (v875 & 0x10) == 0 )
            goto LABEL_598;
          v7 = *v124;
          if ( (v7 & 0x10) == 0 )
          {
            LOBYTE(v7) = v7 & 0xE;
            if ( ((1 << v7) & 0x1105) == 0 )
              goto LABEL_598;
LABEL_497:
            v7 = (unsigned __int64)v876;
            v129 = (const unsigned __int8 *)(v876 + 1);
            v872 = *v876;
            goto LABEL_621;
          }
          if ( v873 >= v126 )
            goto LABEL_497;
          v7 = (unsigned int)v126;
          if ( *(_WORD *)&v124[v126] >= v874 )
          {
LABEL_598:
            v153 = (__int16)v153;
            if ( (__int16)v153 > (unsigned int)v858 )
            {
              v129 = v124;
              v872 = 0;
            }
            else
            {
              v154 = &v124[HIDWORD(v856)];
              if ( (_DWORD)v153 == 1 )
              {
                v155 = v131;
              }
              else
              {
                _mm_lfence();
                v155 = *(_WORD *)&v154[2 * v153 - 2] & 0x7FFF;
                v11 = a5;
                v131 = v857;
                v124 = v855;
              }
              v156 = *(_WORD *)&v154[2 * v153] & 0x7FFF;
              if ( v155 < v131 || v156 < v155 )
              {
                RaiseInconsistencyError(v124, 7);
                v124 = v855;
              }
              v129 = &v124[v155];
              v872 = v156 - v155;
            }
            goto LABEL_621;
          }
          v7 = (unsigned __int64)v876;
          v129 = (const unsigned __int8 *)(v876 + 1);
          v872 = *v876;
LABEL_621:
          v157 = *(_DWORD *)v129;
          if ( v123 != *(_DWORD *)v129 )
          {
            v158 = GetDefaultLocale();
            v159 = L"Shrink %d (0x%x) to %d (0x%x)";
            if ( v123 > v157 )
              v159 = L"Grow %d (0x%x) to %d (0x%x)";
            v840[0] = v123;
            LODWORD(v837) = v123;
            LODWORD(DestinationSize) = v157;
            LODWORD(v826) = v157;
            v160 = StringCchPrintf_lW(v1050, 0x64u, v159, v158, v826, DestinationSize, v837, *(_QWORD *)v840);
            if ( v160 < 0 )
            {
              _mm_lfence();
              LODWORD(v837) = v160;
              LODWORD(DestinationSize) = 8000;
              ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
              v11 = a5;
            }
            if ( v11 && (int)StringCchCatW(v5, 0x100u, v1050) >= 0 )
            {
              v7 = (unsigned __int64)v1050;
              v161 = -1;
              do
                ++v161;
              while ( v1050[v161] );
              v11 -= v161;
              a5 = v11;
              v843 = 0;
            }
          }
          goto LABEL_631;
        }
      }
      else
      {
        if ( !v65 )
        {
          v863 = 0;
          HIDWORD(v866) = v66;
          v65 = v66;
          if ( (*v865 & 0x10) != 0 )
          {
            v65 = (((unsigned int)*(unsigned __int16 *)&v865[v66] + 7) >> 3) + v66 + 2;
            HIDWORD(v866) = v65;
          }
          if ( (*v865 & 0x20) != 0 )
          {
            v67 = &v865[v65];
            v868 = *(_WORD *)v67;
            if ( !v868 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v68 )
                {
                  v69 = *(_QWORD *)(v68 + 96);
                  if ( v69 )
                  {
                    if ( *(_BYTE *)(v69 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v865, 3);
            }
            v867 = HIDWORD(v866) + 2 * (v868 + 1);
            if ( v867 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v70 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v70 )
                {
                  v71 = *(_QWORD *)(v70 + 96);
                  if ( v71 )
                  {
                    if ( *(_BYTE *)(v71 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v865, 4);
            }
            v65 = *(_WORD *)&v67[2 * v868] & 0x7FFF;
            v864 = v65;
            if ( v867 > v65 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v72 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 8LL);
                if ( v72 )
                {
                  v73 = *(_QWORD *)(v72 + 96);
                  if ( v73 )
                  {
                    if ( *(_BYTE *)(v73 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
                v11 = a5;
              }
              RaiseInconsistencyError(v865, 4);
              v65 = v864;
            }
            while ( *(__int16 *)&v67[2 * v868] < 0 )
            {
              v74 = &v865[HIDWORD(v866)];
              if ( v868 == 1 )
                v75 = v867;
              else
                v75 = *(_WORD *)&v74[2 * v868 - 2] & 0x7FFF;
              if ( v75 < v867 || (*(_WORD *)&v74[2 * v868] & 0x7FFFu) < v75 )
              {
                RaiseInconsistencyError(v865, 7);
                v65 = v864;
              }
              if ( v75 < v867 || v75 > v65 )
                goto LABEL_312;
              v76 = *(_WORD *)&v865[v75];
              if ( v76 == 5 )
              {
                v863 |= 2u;
                --v868;
                WORD2(v870) = v75;
                v77 = *(_WORD *)&v865[(unsigned __int16)v75 + 2];
                v78 = WORD3(v870) & 0xC7FF;
                if ( (v77 & 0x4000) != 0 )
                  v78 = WORD3(v870) ^ (WORD3(v870) ^ v77) & 0x3800;
                WORD3(v870) = v78 ^ (v77 ^ v78) & 0x7FF;
                break;
              }
              if ( v76 >= 0x400u )
              {
                v863 |= 1u;
                if ( --v868 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v864 = v65;
            v868 = 0;
            v867 = v65;
          }
          if ( (*v865 & 0x40) != 0 )
          {
            LODWORD(v870) = v65;
            v864 = v65 + 14;
            v79 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v863);
            v80 = HIDWORD(*(_QWORD *)v79);
            v81 = HIWORD(*(_QWORD *)v79);
            v82 = 0;
            if ( (((__int16)v81 ^ ((unsigned int)(__int16)v81 >> 1)) & 0x2000) != 0 )
            {
              v83 = v81 & 0xDFFF;
              if ( (v81 & 0x4000) != 0 )
                v83 = v81 | 0x2000;
              LOWORD(v81) = v83;
            }
            if ( (_WORD)v81 == 0xFFFC )
              v82 = (unsigned __int16)v80 >> 5;
            v65 = v82 + v864;
            v864 += v82;
          }
          else
          {
            LODWORD(v870) = 0;
          }
          if ( v869 && v869 < (unsigned __int64)&v865[v65] )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v84 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL);
              if ( v84 )
              {
                v85 = *(_QWORD *)(v84 + 96);
                if ( v85 )
                {
                  if ( *(_BYTE *)(v85 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
              v11 = a5;
            }
            RaiseInconsistencyError(v865, 18);
            v65 = v864;
          }
          if ( v65 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v86 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL);
              if ( v86 )
              {
                v87 = *(_QWORD *)(v86 + 96);
                if ( v87 )
                {
                  if ( *(_BYTE *)(v87 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
              v11 = a5;
            }
            RaiseInconsistencyError(v865, 5);
            v65 = v864;
          }
        }
LABEL_312:
        if ( v65 >= 9 )
          goto LABEL_322;
        v88 = *v865 & 0xE;
        if ( v88 )
        {
          v89 = v88 == 12;
          goto LABEL_320;
        }
      }
LABEL_321:
      v90 = 9;
      goto LABEL_323;
    }
  }
LABEL_631:
  if ( *((_BYTE *)v6 + 22) != 0x80 )
    goto LABEL_651;
  if ( *((_WORD *)v6 + 38) )
  {
    v162 = (const wchar_t *)VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 76), 0, &v909);
    v163 = v909 >> 1;
    if ( v11 )
    {
      if ( !v843 )
      {
        v164 = 256;
        v7 = (unsigned __int64)v5;
        do
        {
          if ( !*(_WORD *)v7 )
            break;
          v7 += 2LL;
          --v164;
        }
        while ( v164 );
        if ( !v164 )
          goto LABEL_649;
        v165 = 1;
        v166 = L";";
        v7 = (unsigned __int64)&v5[256 - v164];
        v167 = v164;
        do
        {
          if ( !v165 )
            break;
          if ( !*v166 )
            break;
          *(_WORD *)v7 = *v166;
          v7 += 2LL;
          ++v166;
          --v165;
          --v167;
        }
        while ( v167 );
        v168 = (_WORD *)(v7 - 2);
        if ( v167 )
          v168 = (_WORD *)v7;
        *v168 = 0;
        if ( !v167 )
          goto LABEL_649;
        a5 = --v11;
      }
      if ( (int)StringCchCatNW(v5, 0x100u, v162, v163) >= 0 )
      {
        v11 -= v163;
        a5 = v11;
        v843 = 0;
      }
    }
  }
LABEL_649:
  if ( *((_WORD *)v6 + 38) > 1u )
  {
    v169 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 76), 1u, &v910);
    DumpLogRecord::AppendBytes((DumpLogRecord *)&a5, v5, v169, v910, &a5, 1, &v843);
    v11 = a5;
  }
LABEL_651:
  if ( *((_BYTE *)v6 + 22) != 0x81 )
    goto LABEL_670;
  UICodePageFromCID(*((_DWORD *)v927 + 5));
  v170 = (const wchar_t *)VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 80), 3u, &v911);
  if ( !v170 )
    goto LABEL_670;
  if ( !v911 )
    goto LABEL_670;
  v171 = v911 >> 1;
  if ( !v11 )
    goto LABEL_670;
  if ( v843 )
    goto LABEL_668;
  v172 = 256;
  v173 = v5;
  do
  {
    if ( !*v173 )
      break;
    ++v173;
    --v172;
  }
  while ( v172 );
  if ( v172 )
  {
    v174 = 1;
    v175 = L";";
    v7 = (unsigned __int64)&v5[256 - v172];
    v176 = v172;
    do
    {
      if ( !v174 )
        break;
      if ( !*v175 )
        break;
      *(_WORD *)v7 = *v175;
      v7 += 2LL;
      ++v175;
      --v174;
      --v176;
    }
    while ( v176 );
    v177 = (_WORD *)(v7 - 2);
    if ( v176 )
      v177 = (_WORD *)v7;
    *v177 = 0;
    if ( v176 )
    {
      a5 = --v11;
LABEL_668:
      if ( (int)StringCchCatNW(v5, 0x100u, v170, v171) >= 0 )
      {
        v11 -= v171;
        a5 = v11;
        v843 = 0;
      }
    }
  }
LABEL_670:
  if ( *((_BYTE *)v6 + 22) == 125 )
  {
    v178 = 0;
    v882 = 0;
    v179 = (DatabaseMetaLog *)((char *)v6 + 56);
    v917 = (DatabaseMetaLog *)((char *)v6 + 56);
    v180 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 56), 0, &v882);
    v181 = 0;
    v182 = v882;
    if ( v882 )
      v181 = v180;
    v886 = 0;
    v183 = VarLogData::GetData(v179, 2u, &v886);
    v184 = 0;
    if ( v886 )
      v184 = v183;
    v952 = v184;
    v887 = 0;
    v185 = VarLogData::GetData(v179, 1u, &v887);
    v186 = 0;
    if ( v887 )
      v186 = v185;
    v953 = v186;
    v187 = GetDefaultLocale();
    v188 = v877;
    LODWORD(v826) = *((_DWORD *)v877 + 12);
    v189 = StringCchPrintf_lW(v1027, 0x46u, L"Bytes %d,", v187, v826);
    if ( v189 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v189;
      LODWORD(DestinationSize) = 8086;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
      v11 = a5;
      v182 = v882;
    }
    if ( v11 )
    {
      if ( v843 )
        goto LABEL_693;
      v190 = 256;
      v191 = v5;
      do
      {
        if ( !*v191 )
          break;
        ++v191;
        --v190;
      }
      while ( v190 );
      if ( v190 )
      {
        v192 = 1;
        v193 = L";";
        v7 = (unsigned __int64)&v5[256 - v190];
        v194 = v190;
        do
        {
          if ( !v192 )
            break;
          if ( !*v193 )
            break;
          *(_WORD *)v7 = *v193;
          v7 += 2LL;
          ++v193;
          --v192;
          --v194;
        }
        while ( v194 );
        v195 = (_WORD *)(v7 - 2);
        if ( v194 )
          v195 = (_WORD *)v7;
        *v195 = 0;
        if ( v194 )
        {
          a5 = --v11;
LABEL_693:
          if ( (int)StringCchCatW(v5, 0x100u, v1027) >= 0 )
          {
            v7 = (unsigned __int64)v1027;
            v196 = -1;
            do
              ++v196;
            while ( v1027[v196] );
            v11 -= v196;
            a5 = v11;
            v843 = 0;
          }
        }
      }
    }
    if ( !v181 )
      goto LABEL_742;
    v197 = VarLogData::GetData(v179, 2u, &v912);
    v198 = 0;
    if ( v912 )
      v198 = v197;
    if ( v198 )
    {
      v949 = v198;
      v951 = 8 * v912;
      v950 = (8 * v912 + 7) >> 3;
      v178 = SEBitMap::CountBits((SEBitMap *)&v949);
    }
    v199 = VarLogData::GetData(v179, 1u, &v913);
    v200 = 0;
    if ( v913 )
      v200 = v199;
    if ( v200 )
    {
      v954 = v200;
      v956 = 8 * v913;
      v955 = (8 * v913 + 7) >> 3;
      v201 = SEBitMap::CountBits((SEBitMap *)&v954);
    }
    else
    {
      v201 = 0;
    }
    v202 = *((unsigned int *)v188 + 13) - v201 - v178;
    v203 = GetDefaultLocale();
    v204 = StringCchPrintf_lW(v1027, 0x46u, L"Rows stripped %d;Slots:", v203, v202);
    if ( v204 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v204;
      LODWORD(DestinationSize) = 8100;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
      v11 = a5;
      v182 = v882;
    }
    if ( !v11 )
      goto LABEL_727;
    if ( !v843 )
    {
      v205 = 256;
      v206 = v5;
      do
      {
        if ( !*v206 )
          break;
        ++v206;
        --v205;
      }
      while ( v205 );
      if ( !v205 )
        goto LABEL_727;
      v207 = 1;
      v208 = L";";
      v209 = &v5[256 - v205];
      v7 = v205;
      do
      {
        if ( !v207 )
          break;
        if ( !*v208 )
          break;
        *v209++ = *v208++;
        --v207;
        --v7;
      }
      while ( v7 );
      v210 = v209 - 1;
      if ( v7 )
        v210 = v209;
      *v210 = 0;
      if ( !v7 )
      {
LABEL_727:
        v212 = 0;
        if ( !v182 )
          goto LABEL_741;
        while ( 1 )
        {
          v213 = 8 * v212;
          v214 = 8;
          do
          {
            v7 = (unsigned __int8)v213;
            LOBYTE(v7) = v213 & 7;
            if ( ((v181[(unsigned __int64)v213 >> 3] >> (v213 & 7)) & 1) != 0 )
            {
              if ( !v11 )
                goto LABEL_736;
              v215 = L"1";
            }
            else
            {
              if ( !v11 )
                goto LABEL_736;
              v215 = L"0";
            }
            if ( (int)StringCchCatW(v5, 0x100u, v215) >= 0 )
            {
              --v11;
              v843 = 0;
              a5 = v11;
            }
LABEL_736:
            ++v213;
            --v214;
          }
          while ( v214 );
          v216 = v882;
          if ( v11 && (int)StringCchCatW(v5, 0x100u, L":") >= 0 )
          {
            a5 = --v11;
            v843 = 0;
          }
          if ( ++v212 >= v216 )
          {
LABEL_741:
            v179 = v917;
LABEL_742:
            v217 = v952;
            if ( !v952 )
              goto LABEL_803;
            v218 = VarLogData::GetData(v179, 2u, &v914);
            v219 = 0;
            if ( v914 )
              v219 = v218;
            if ( v219 )
            {
              v957 = v219;
              v959 = 8 * v914;
              v958 = (8 * v914 + 7) >> 3;
              v220 = SEBitMap::CountBits((SEBitMap *)&v957);
            }
            else
            {
              v220 = 0;
            }
            v221 = GetDefaultLocale();
            v222 = StringCchPrintf_lW(v1027, 0x46u, L"Rows purged %d;Slots:", v221, v220);
            if ( v222 < 0 )
            {
              _mm_lfence();
              LODWORD(v837) = v222;
              LODWORD(DestinationSize) = 8141;
              ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
              v11 = a5;
            }
            if ( v11 )
            {
              if ( v843 )
              {
LABEL_764:
                if ( (int)StringCchCatW(v5, 0x100u, v1027) >= 0 )
                {
                  v230 = -1;
                  do
                    ++v230;
                  while ( v1027[v230] );
                  v11 -= v230;
                  a5 = v11;
                  v843 = 0;
                }
              }
              else
              {
                v223 = 256;
                v224 = v5;
                do
                {
                  if ( !*v224 )
                    break;
                  ++v224;
                  --v223;
                }
                while ( v223 );
                if ( v223 )
                {
                  v225 = 1;
                  v226 = L";";
                  v227 = &v5[256 - v223];
                  v228 = v223;
                  do
                  {
                    if ( !v225 )
                      break;
                    if ( !*v226 )
                      break;
                    *v227++ = *v226++;
                    --v225;
                    --v228;
                  }
                  while ( v228 );
                  v229 = v227 - 1;
                  if ( v228 )
                    v229 = v227;
                  *v229 = 0;
                  if ( v228 )
                  {
                    a5 = --v11;
                    goto LABEL_764;
                  }
                }
              }
            }
            v231 = 0;
            if ( !v886 )
              goto LABEL_782;
            while ( 2 )
            {
              v232 = 8 * v231;
              v233 = 8;
LABEL_770:
              if ( ((v217[(unsigned __int64)v232 >> 3] >> (v232 & 7)) & 1) != 0 )
              {
                if ( v11 )
                {
                  v234 = L"1";
LABEL_775:
                  if ( (int)StringCchCatW(v5, 0x100u, v234) >= 0 )
                  {
                    --v11;
                    v843 = 0;
                    a5 = v11;
                  }
                }
              }
              else if ( v11 )
              {
                v234 = L"0";
                goto LABEL_775;
              }
              ++v232;
              if ( !--v233 )
              {
                v235 = v886;
                if ( v11 && (int)StringCchCatW(v5, 0x100u, L":") >= 0 )
                {
                  a5 = --v11;
                  v843 = 0;
                }
                if ( ++v231 >= v235 )
                {
LABEL_782:
                  v236 = v877;
                  if ( PurgeVersionBytesLog::GetNonLoggedInCTRRowCount(v877) )
                  {
                    NonLoggedInCTRRowCount = PurgeVersionBytesLog::GetNonLoggedInCTRRowCount(v236);
                    v238 = GetDefaultLocale();
                    LODWORD(v826) = NonLoggedInCTRRowCount;
                    v239 = StringCchPrintf_lW(v1027, 0x46u, L"NonLoggedInCTRRowCount: %d", v238, v826);
                    if ( v239 < 0 )
                    {
                      _mm_lfence();
                      LODWORD(v837) = v239;
                      LODWORD(DestinationSize) = 8183;
                      ex_raise(
                        4,
                        7,
                        16,
                        1,
                        "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp",
                        DestinationSize,
                        v837);
                      v11 = a5;
                    }
                    if ( v11 )
                    {
                      if ( v843 )
                      {
LABEL_799:
                        if ( (int)StringCchCatW(v5, 0x100u, v1027) >= 0 )
                        {
                          v7 = (unsigned __int64)v1027;
                          v246 = -1;
                          do
                            ++v246;
                          while ( v1027[v246] );
                          v11 -= v246;
                          a5 = v11;
                          v843 = 0;
                        }
                      }
                      else
                      {
                        v240 = 256;
                        v241 = v5;
                        do
                        {
                          if ( !*v241 )
                            break;
                          ++v241;
                          --v240;
                        }
                        while ( v240 );
                        if ( v240 )
                        {
                          v242 = 1;
                          v243 = L";";
                          v7 = (unsigned __int64)&v5[256 - v240];
                          v244 = v240;
                          do
                          {
                            if ( !v242 )
                              break;
                            if ( !*v243 )
                              break;
                            *(_WORD *)v7 = *v243;
                            v7 += 2LL;
                            ++v243;
                            --v242;
                            --v244;
                          }
                          while ( v244 );
                          v245 = (_WORD *)(v7 - 2);
                          if ( v244 )
                            v245 = (_WORD *)v7;
                          *v245 = 0;
                          if ( v244 )
                          {
                            a5 = --v11;
                            goto LABEL_799;
                          }
                        }
                      }
                    }
                  }
LABEL_803:
                  v247 = v953;
                  if ( !v953 )
                    goto LABEL_843;
                  v248 = VarLogData::GetData(v917, 1u, &v915);
                  v249 = 0;
                  if ( v915 )
                    v249 = v248;
                  if ( v249 )
                  {
                    v946 = v249;
                    v948 = 8 * v915;
                    v947 = (8 * v915 + 7) >> 3;
                    v250 = SEBitMap::CountBits((SEBitMap *)&v946);
                  }
                  else
                  {
                    v250 = 0;
                  }
                  v251 = GetDefaultLocale();
                  v252 = StringCchPrintf_lW(v1027, 0x46u, L"Rows unghosted %d;Slots:", v251, v250);
                  if ( v252 < 0 )
                  {
                    _mm_lfence();
                    LODWORD(v837) = v252;
                    LODWORD(DestinationSize) = 8198;
                    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
                    v11 = a5;
                  }
                  if ( v11 )
                  {
                    if ( v843 )
                    {
LABEL_825:
                      if ( (int)StringCchCatW(v5, 0x100u, v1027) >= 0 )
                      {
                        v7 = (unsigned __int64)v1027;
                        v259 = -1;
                        do
                          ++v259;
                        while ( v1027[v259] );
                        v11 -= v259;
                        a5 = v11;
                        v843 = 0;
                      }
                    }
                    else
                    {
                      v253 = 256;
                      v254 = v5;
                      do
                      {
                        if ( !*v254 )
                          break;
                        ++v254;
                        --v253;
                      }
                      while ( v253 );
                      if ( v253 )
                      {
                        v255 = 1;
                        v256 = L";";
                        v7 = (unsigned __int64)&v5[256 - v253];
                        v257 = v253;
                        do
                        {
                          if ( !v255 )
                            break;
                          if ( !*v256 )
                            break;
                          *(_WORD *)v7 = *v256;
                          v7 += 2LL;
                          ++v256;
                          --v255;
                          --v257;
                        }
                        while ( v257 );
                        v258 = (_WORD *)(v7 - 2);
                        if ( v257 )
                          v258 = (_WORD *)v7;
                        *v258 = 0;
                        if ( v257 )
                        {
                          a5 = --v11;
                          goto LABEL_825;
                        }
                      }
                    }
                  }
                  v260 = 0;
                  v883 = 0;
                  if ( !v887 )
                    goto LABEL_843;
                  while ( 2 )
                  {
                    v261 = 8 * v260;
                    v262 = 8;
LABEL_831:
                    v7 = (unsigned __int8)v261;
                    LOBYTE(v7) = v261 & 7;
                    if ( ((v247[(unsigned __int64)v261 >> 3] >> (v261 & 7)) & 1) != 0 )
                    {
                      if ( v11 )
                      {
                        v263 = L"1";
LABEL_836:
                        if ( (int)StringCchCatW(v5, 0x100u, v263) >= 0 )
                        {
                          --v11;
                          v843 = 0;
                          a5 = v11;
                        }
                      }
                    }
                    else if ( v11 )
                    {
                      v263 = L"0";
                      goto LABEL_836;
                    }
                    ++v261;
                    if ( !--v262 )
                    {
                      v264 = v883;
                      if ( v11 && (int)StringCchCatW(v5, 0x100u, L":") >= 0 )
                      {
                        a5 = --v11;
                        v843 = 0;
                      }
                      v260 = v264 + 1;
                      v883 = v260;
                      if ( v260 >= v887 )
                      {
LABEL_843:
                        v6 = v877;
                        goto LABEL_844;
                      }
                      continue;
                    }
                    goto LABEL_831;
                  }
                }
                continue;
              }
              goto LABEL_770;
            }
          }
        }
      }
      a5 = --v11;
    }
    if ( (int)StringCchCatW(v5, 0x100u, v1027) >= 0 )
    {
      v7 = (unsigned __int64)v1027;
      v211 = -1;
      do
        ++v211;
      while ( v1027[v211] );
      v11 -= v211;
      a5 = v11;
      v843 = 0;
    }
    goto LABEL_727;
  }
LABEL_844:
  if ( *((_BYTE *)v6 + 22) == 0x86 || *((_BYTE *)v6 + 22) == 0x87 )
  {
    v265 = (const wchar_t *)(VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 28), 0, &v936) + 528);
    v266 = -1;
    do
      ++v266;
    while ( v265[v266] );
    if ( v11 )
    {
      if ( v843 )
        goto LABEL_861;
      v267 = 256;
      v268 = v5;
      do
      {
        if ( !*v268 )
          break;
        ++v268;
        --v267;
      }
      while ( v267 );
      if ( v267 )
      {
        v269 = 1;
        v270 = L";";
        v7 = (unsigned __int64)&v5[256 - v267];
        v271 = v267;
        do
        {
          if ( !v269 )
            break;
          if ( !*v270 )
            break;
          *(_WORD *)v7 = *v270;
          v7 += 2LL;
          ++v270;
          --v269;
          --v271;
        }
        while ( v271 );
        v272 = (_WORD *)(v7 - 2);
        if ( v271 )
          v272 = (_WORD *)v7;
        *v272 = 0;
        if ( v271 )
        {
          a5 = --v11;
LABEL_861:
          if ( (int)StringCchCatNW(v5, 0x100u, v265, (unsigned int)v266) >= 0 )
          {
            v11 -= v273;
            a5 = v11;
            v843 = 0;
          }
        }
      }
    }
  }
  if ( *((_BYTE *)v6 + 22) == 0xF3 )
  {
    v274 = *((unsigned __int16 *)v6 + 12);
    v275 = GetDefaultLocale();
    LODWORD(v826) = v274;
    v276 = StringCchPrintf_lW(v1028, 0x14u, L"File Id: %d", v275, v826);
    if ( v276 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v276;
      LODWORD(DestinationSize) = 8272;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
      v11 = a5;
    }
    if ( v11 )
    {
      if ( v843 )
        goto LABEL_880;
      v277 = 256;
      v278 = v5;
      do
      {
        if ( !*v278 )
          break;
        ++v278;
        --v277;
      }
      while ( v277 );
      if ( v277 )
      {
        v279 = 1;
        v280 = L";";
        v7 = (unsigned __int64)&v5[256 - v277];
        v281 = v277;
        do
        {
          if ( !v279 )
            break;
          if ( !*v280 )
            break;
          *(_WORD *)v7 = *v280;
          v7 += 2LL;
          ++v280;
          --v279;
          --v281;
        }
        while ( v281 );
        v282 = (_WORD *)(v7 - 2);
        if ( v281 )
          v282 = (_WORD *)v7;
        *v282 = 0;
        if ( v281 )
        {
          a5 = --v11;
LABEL_880:
          if ( (int)StringCchCatW(v5, 0x100u, v1028) >= 0 )
          {
            v7 = (unsigned __int64)v1028;
            v283 = -1;
            do
              ++v283;
            while ( v1028[v283] );
            v11 -= v283;
            a5 = v11;
            v843 = 0;
          }
        }
      }
    }
  }
  if ( *((_BYTE *)v6 + 22) != 0x89 )
    goto LABEL_914;
  v284 = *((_QWORD *)v6 + 3);
  v285 = *((unsigned __int16 *)v6 + 16);
  if ( v285 == 1 )
  {
    v286 = L"CREATE_HOBT";
  }
  else if ( *((_WORD *)v6 + 16) == 2 )
  {
    v286 = L"ALTER_HOBT";
  }
  else if ( *((_WORD *)v6 + 16) == 3 )
  {
    v286 = L"DROP_HOBT";
  }
  else
  {
    v286 = L"Unknown";
  }
  v287 = *((unsigned __int16 *)v877 + 17);
  v288 = GetDefaultLocale();
  LODWORD(v841) = v287;
  v840[0] = WORD2(v284);
  LODWORD(v837) = v284;
  LODWORD(v826) = v285;
  v289 = StringCchPrintf_lW(
           v1057,
           0xC8u,
           L"Action %ld (%s) on HoBt 0x%x:%x, partition 0x%x, rowset %I64d.",
           v288,
           v826,
           v286,
           v837,
           *(_QWORD *)v840,
           v841,
           v287 | (((unsigned int)v284 | ((unsigned __int64)WORD2(v284) << 32)) << 16));
  if ( v289 < 0 )
  {
    _mm_lfence();
    LODWORD(v837) = v289;
    LODWORD(DestinationSize) = 8317;
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
    v11 = a5;
  }
  v5 = v906;
  if ( !v11 )
    goto LABEL_913;
  if ( !v843 )
  {
    v290 = 256;
    v291 = v906;
    do
    {
      if ( !*v291 )
        break;
      ++v291;
      --v290;
    }
    while ( v290 );
    if ( v290 )
    {
      v292 = 1;
      v293 = L";";
      v7 = (unsigned __int64)&v906[256 - v290];
      v294 = v290;
      do
      {
        if ( !v292 )
          break;
        if ( !*v293 )
          break;
        *(_WORD *)v7 = *v293;
        v7 += 2LL;
        ++v293;
        --v292;
        --v294;
      }
      while ( v294 );
      v295 = (_WORD *)(v7 - 2);
      if ( v294 )
        v295 = (_WORD *)v7;
      *v295 = 0;
      if ( v294 )
      {
        a5 = --v11;
        goto LABEL_908;
      }
    }
LABEL_913:
    v6 = v877;
    goto LABEL_914;
  }
LABEL_908:
  if ( (int)StringCchCatW(v5, 0x100u, v1057) >= 0 )
  {
    v7 = (unsigned __int64)v1057;
    v296 = -1;
    do
      ++v296;
    while ( v1057[v296] );
    v11 -= v296;
    a5 = v11;
    v843 = 0;
  }
  v6 = v877;
LABEL_914:
  if ( *((_BYTE *)v6 + 22) != 0x9A )
    goto LABEL_983;
  LSN::FormatAsHexString((LSN *)v6 + 3, v1023, &v937);
  if ( !v11 )
    goto LABEL_952;
  if ( v843 )
    goto LABEL_929;
  v297 = 256;
  v298 = v5;
  do
  {
    if ( !*v298 )
      break;
    ++v298;
    --v297;
  }
  while ( v297 );
  if ( v297 )
  {
    v299 = 1;
    v300 = L";";
    v301 = &v5[256 - v297];
    v302 = v297;
    do
    {
      if ( !v299 )
        break;
      if ( !*v300 )
        break;
      *v301++ = *v300++;
      --v299;
      --v302;
    }
    while ( v302 );
    v303 = v301 - 1;
    if ( v302 )
      v303 = v301;
    *v303 = 0;
    if ( v302 )
    {
      a5 = --v11;
LABEL_929:
      if ( (int)StringCchCatW(v5, 0x100u, L"EndLogLsn ") >= 0 )
      {
        v11 -= 10;
        a5 = v11;
        v843 = 0;
      }
    }
  }
  if ( v11 )
  {
    if ( (int)StringCchCatW(v5, 0x100u, v1023) >= 0 )
    {
      v304 = -1;
      do
        ++v304;
      while ( v1023[v304] );
      v11 -= v304;
      a5 = v11;
      v843 = 0;
    }
    if ( v11 )
    {
      if ( v843 )
        goto LABEL_950;
      v305 = 256;
      v306 = v5;
      do
      {
        if ( !*v306 )
          break;
        ++v306;
        --v305;
      }
      while ( v305 );
      if ( v305 )
      {
        v307 = 1;
        v308 = L";";
        v309 = &v5[256 - v305];
        v310 = v305;
        do
        {
          if ( !v307 )
            break;
          if ( !*v308 )
            break;
          *v309++ = *v308++;
          --v307;
          --v310;
        }
        while ( v310 );
        v311 = v309 - 1;
        if ( v310 )
          v311 = v309;
        *v311 = 0;
        if ( v310 )
        {
          a5 = --v11;
LABEL_950:
          if ( (int)StringCchCatW(v5, 0x100u, L"Page Count ") >= 0 )
          {
            v11 -= 11;
            a5 = v11;
            v843 = 0;
          }
        }
      }
    }
  }
LABEL_952:
  VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 34), 0, &v916);
  v312 = v916 / 6;
  v313 = GetDefaultLocale();
  LODWORD(v826) = v312;
  v314 = StringCchPrintf_lW(v1023, 0x16u, L"%d", v313, v826);
  if ( v314 < 0 )
  {
    _mm_lfence();
    LODWORD(v837) = v314;
    LODWORD(DestinationSize) = 8343;
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
    v11 = a5;
  }
  if ( v11 && (int)StringCchCatW(v5, 0x100u, v1023) >= 0 )
  {
    v315 = -1;
    do
      ++v315;
    while ( v1023[v315] );
    v11 -= v315;
    a5 = v11;
    v843 = 0;
  }
  VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 34), 0, &v921);
  if ( v921 / 6 == 1 )
  {
    v316 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 34), 0, &v938);
    v317 = *(_DWORD *)v316;
    v318 = *((unsigned __int16 *)v316 + 2);
    v319 = GetDefaultLocale();
    LODWORD(DestinationSize) = v317;
    LODWORD(v826) = v318;
    v320 = StringCchPrintf_lW(v1025, 0xEu, L"%04lx:%08lx", v319, v826, DestinationSize);
    if ( v320 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v320;
      LODWORD(DestinationSize) = 3071;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
      v11 = a5;
    }
    if ( v11 )
    {
      if ( !v843 )
      {
        v321 = 256;
        v322 = v5;
        do
        {
          if ( !*v322 )
            break;
          ++v322;
          --v321;
        }
        while ( v321 );
        if ( !v321 )
          goto LABEL_978;
        v323 = 1;
        v324 = L";";
        v325 = &v5[256 - v321];
        v7 = v321;
        do
        {
          if ( !v323 )
            break;
          if ( !*v324 )
            break;
          *v325++ = *v324++;
          --v323;
          --v7;
        }
        while ( v7 );
        v326 = v325 - 1;
        if ( v7 )
          v326 = v325;
        *v326 = 0;
        if ( !v7 )
          goto LABEL_978;
        a5 = --v11;
      }
      if ( (int)StringCchCatW(v5, 0x100u, L"Page ") >= 0 )
      {
        v11 -= 5;
        a5 = v11;
        v843 = 0;
      }
LABEL_978:
      if ( v11 && (int)StringCchCatW(v5, 0x100u, v1025) >= 0 )
      {
        v7 = (unsigned __int64)v1025;
        v327 = -1;
        do
          ++v327;
        while ( v1025[v327] );
        v11 -= v327;
        a5 = v11;
        v843 = 0;
      }
    }
  }
LABEL_983:
  if ( ((*((_BYTE *)v6 + 22) + 114) & 0xFD) != 0 )
    goto LABEL_1002;
  v328 = (const wchar_t *)(VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 28), 0, &v939) + 538);
  v329 = -1;
  do
    ++v329;
  while ( v328[v329] );
  if ( !v11 )
    goto LABEL_1002;
  if ( v843 )
    goto LABEL_1000;
  v330 = 256;
  v331 = v5;
  do
  {
    if ( !*v331 )
      break;
    ++v331;
    --v330;
  }
  while ( v330 );
  if ( v330 )
  {
    v332 = 1;
    v333 = L";";
    v334 = &v5[256 - v330];
    v7 = v330;
    do
    {
      if ( !v332 )
        break;
      if ( !*v333 )
        break;
      *v334++ = *v333++;
      --v332;
      --v7;
    }
    while ( v7 );
    v335 = v334 - 1;
    if ( v7 )
      v335 = v334;
    *v335 = 0;
    if ( v7 )
    {
      a5 = --v11;
LABEL_1000:
      if ( (int)StringCchCatNW(v5, 0x100u, v328, (unsigned int)v329) >= 0 )
      {
        v11 -= v336;
        a5 = v11;
        v843 = 0;
      }
    }
  }
LABEL_1002:
  if ( *((_BYTE *)v6 + 22) == 0x91 )
  {
    v889 = 0;
    v337 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 24), 0, &v889);
    v1011 = 0;
    v1012 = 1;
    v1013 = 0x80000000;
    v1014 = 0;
    v1015 = 0;
    v994 = 0;
    v995 = 2;
    v996 = 0x80000000;
    v997 = 0;
    v998 = 0;
    v999 = 0;
    v1000 = 0;
    v1001 = 0;
    v1002 = 0;
    v1003 = NullXdesId;
    v1004 = word_10318AB38;
    v1005 = 0;
    v1006 = 0;
    v1007 = 0;
    v1008 = 0;
    v1009 = 0;
    if ( *((_WORD *)v337 + 4) == 1 )
    {
      FsDownLevelRecKatmai::Init((FsDownLevelRecKatmai *)&v1011, v337, v889, v896);
    }
    else if ( *((_WORD *)v337 + 4) == 2 )
    {
      FsDownLevelRecSql11::Init((FsDownLevelRecSql11 *)&v994, v337, v889, v338);
    }
    else
    {
      utassert_fail(1u, "FALSE", "dumplog.cpp", 8415, "Invalid switch value");
    }
    switch ( *(_WORD *)v337 )
    {
      case 1:
        v339 = L"CREATE";
        goto LABEL_1015;
      case 2:
        v339 = L"DELETE";
        goto LABEL_1015;
      case 3:
        v339 = L"GARBAGE COLLECTED";
        goto LABEL_1015;
      case 4:
        v339 = L"WRITE";
        goto LABEL_1015;
      case 5:
        v339 = L"CLOSE";
        goto LABEL_1015;
      case 7:
        v339 = L"IN PLACE UPDATE";
LABEL_1015:
        if ( !v11 )
          goto LABEL_1037;
        if ( v843 )
          goto LABEL_1029;
        v340 = 256;
        v341 = v5;
        do
        {
          if ( !*v341 )
            break;
          ++v341;
          --v340;
        }
        while ( v340 );
        if ( v340 )
        {
          v342 = 1;
          v343 = L";";
          v344 = &v5[256 - v340];
          v345 = v340;
          do
          {
            if ( !v342 )
              break;
            if ( !*v343 )
              break;
            *v344++ = *v343++;
            --v342;
            --v345;
          }
          while ( v345 );
          v346 = v344 - 1;
          if ( v345 )
            v346 = v344;
          *v346 = 0;
          if ( v345 )
          {
            a5 = --v11;
LABEL_1029:
            if ( (int)StringCchCatW(v5, 0x100u, L"Operation ") >= 0 )
            {
              v11 -= 10;
              a5 = v11;
              v843 = 0;
            }
          }
        }
        if ( v11 && (int)StringCchCatW(v5, 0x100u, v339) >= 0 )
        {
          _mm_lfence();
          v347 = -1;
          do
            ++v347;
          while ( v339[v347] );
          v11 = a5 - v347;
          a5 -= v347;
          v843 = 0;
        }
LABEL_1037:
        v348 = GetDefaultLocale();
        LODWORD(v826) = *((_DWORD *)v337 + 3);
        v349 = StringCchPrintf_lW(v1019, 0x28u, L"File Id %d", v348, v826);
        if ( v349 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v349;
          LODWORD(DestinationSize) = 8469;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1073;
        if ( v843 )
          goto LABEL_1053;
        v350 = 256;
        v351 = v5;
        do
        {
          if ( !*v351 )
            break;
          ++v351;
          --v350;
        }
        while ( v350 );
        if ( v350 )
        {
          v352 = 1;
          v353 = L";";
          v354 = &v5[256 - v350];
          v355 = v350;
          do
          {
            if ( !v352 )
              break;
            if ( !*v353 )
              break;
            *v354++ = *v353++;
            --v352;
            --v355;
          }
          while ( v355 );
          v356 = v354 - 1;
          if ( v355 )
            v356 = v354;
          *v356 = 0;
          if ( v355 )
          {
            a5 = --v11;
LABEL_1053:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v357 = -1;
              do
                ++v357;
              while ( v1019[v357] );
              v11 -= v357;
              a5 = v11;
              v843 = 0;
            }
          }
        }
        if ( !v11 )
          goto LABEL_1073;
        if ( v843 )
          goto LABEL_1071;
        v358 = 256;
        v359 = v5;
        do
        {
          if ( !*v359 )
            break;
          ++v359;
          --v358;
        }
        while ( v358 );
        if ( v358 )
        {
          v360 = 1;
          v361 = L";";
          v362 = &v5[256 - v358];
          v363 = v358;
          do
          {
            if ( !v360 )
              break;
            if ( !*v361 )
              break;
            *v362++ = *v361++;
            --v360;
            --v363;
          }
          while ( v363 );
          v364 = v362 - 1;
          if ( v363 )
            v364 = v362;
          *v364 = 0;
          if ( v363 )
          {
            a5 = --v11;
LABEL_1071:
            if ( (int)StringCchCatW(v5, 0x100u, L"Name ") >= 0 )
            {
              v11 -= 5;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1073:
        if ( *((_WORD *)v337 + 4) == 1 )
        {
          if ( HIWORD(v1011) )
            v367 = (const wchar_t *)&v1016[WORD2(v1011)];
          else
            v367 = 0;
          v368 = HIWORD(v1011) >> 1;
          if ( v11 && (int)StringCchCatNW(v5, 0x100u, v367, v368) >= 0 )
          {
            v11 -= v368;
            a5 = v11;
            v843 = 0;
          }
        }
        else if ( *((_WORD *)v337 + 4) == 2 )
        {
          if ( HIWORD(v994) )
            v365 = (const wchar_t *)&v1010[WORD2(v994)];
          else
            v365 = 0;
          v366 = HIWORD(v994) >> 1;
          if ( v11 && (int)StringCchCatNW(v5, 0x100u, v365, v366) >= 0 )
          {
            v11 -= v366;
            a5 = v11;
            v843 = 0;
          }
        }
        else
        {
          utassert_fail(1u, "FALSE", "dumplog.cpp", 8500, "Invalid switch value");
        }
        v7 = *(unsigned __int16 *)v337;
        if ( (((_WORD)v7 - 4) & 0xFFFC) != 0 || (_WORD)v7 == 6 )
          goto LABEL_1234;
        if ( !v11 )
          goto LABEL_1106;
        if ( v843 )
          goto LABEL_1104;
        v369 = 256;
        v370 = v5;
        do
        {
          if ( !*v370 )
            break;
          ++v370;
          --v369;
        }
        while ( v369 );
        if ( v369 )
        {
          v371 = 1;
          v372 = L";";
          v373 = &v5[256 - v369];
          v374 = v369;
          do
          {
            if ( !v371 )
              break;
            if ( !*v372 )
              break;
            *v373++ = *v372++;
            --v371;
            --v374;
          }
          while ( v374 );
          v375 = v373 - 1;
          if ( v374 )
            v375 = v373;
          *v375 = 0;
          if ( v374 )
          {
            a5 = --v11;
LABEL_1104:
            if ( (int)StringCchCatW(v5, 0x100u, L"CrLSN ") >= 0 )
            {
              a5 = v11 - 6;
              v843 = 0;
            }
          }
        }
LABEL_1106:
        _mm_lfence();
        v376 = v1000;
        v377 = GetDefaultLocale();
        LODWORD(v837) = v376;
        LODWORD(DestinationSize) = HIDWORD(v999);
        LODWORD(v826) = v999;
        StringCchPrintf_lW(v1024, 0x17u, L"%08lx-%08lx-%04lx", v377, v826, DestinationSize, v837);
        v378 = a5;
        if ( !a5 )
          goto LABEL_1128;
        if ( (int)StringCchCatW(v5, 0x100u, v1024) < 0 )
        {
          v380 = v843;
        }
        else
        {
          v379 = -1;
          do
            ++v379;
          while ( v1024[v379] );
          v378 -= v379;
          a5 = v378;
          v380 = 0;
          v843 = 0;
        }
        if ( !v378 )
          goto LABEL_1128;
        if ( v380 )
          goto LABEL_1126;
        v381 = 256;
        v382 = v5;
        do
        {
          if ( !*v382 )
            break;
          ++v382;
          --v381;
        }
        while ( v381 );
        if ( v381 )
        {
          v383 = 1;
          v384 = L";";
          v385 = &v5[256 - v381];
          v386 = v381;
          do
          {
            if ( !v383 )
              break;
            if ( !*v384 )
              break;
            *v385++ = *v384++;
            --v383;
            --v386;
          }
          while ( v386 );
          v387 = v385 - 1;
          if ( v386 )
            v387 = v385;
          *v387 = 0;
          if ( v386 )
          {
            a5 = --v378;
LABEL_1126:
            if ( (int)StringCchCatW(v5, 0x100u, L"OpLSN ") >= 0 )
            {
              a5 = v378 - 6;
              v843 = 0;
            }
          }
        }
LABEL_1128:
        _mm_lfence();
        v388 = v1002;
        v389 = GetDefaultLocale();
        LODWORD(v838) = v388;
        LODWORD(DestinationSizea) = HIDWORD(v1001);
        LODWORD(v827) = v1001;
        StringCchPrintf_lW(v1024, 0x17u, L"%08lx-%08lx-%04lx", v389, v827, DestinationSizea, v838);
        v11 = a5;
        if ( a5 && (int)StringCchCatW(v5, 0x100u, v1024) >= 0 )
        {
          v7 = (unsigned __int64)v1024;
          v390 = -1;
          do
            ++v390;
          while ( v1024[v390] );
          v11 -= v390;
          a5 = v11;
          v843 = 0;
        }
        if ( *(_WORD *)v337 == 7 )
          goto LABEL_1234;
        v391 = GetDefaultLocale();
        v392 = StringCchPrintf_lW(v1019, 0x28u, L"OldFileSz %I64d", v391, v1006);
        if ( v392 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v392;
          LODWORD(DestinationSize) = 8537;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1154;
        if ( v843 )
          goto LABEL_1150;
        v393 = 256;
        v394 = v5;
        do
        {
          if ( !*v394 )
            break;
          ++v394;
          --v393;
        }
        while ( v393 );
        if ( v393 )
        {
          v395 = 1;
          v396 = L";";
          v397 = &v5[256 - v393];
          v398 = v393;
          do
          {
            if ( !v395 )
              break;
            if ( !*v396 )
              break;
            *v397++ = *v396++;
            --v395;
            --v398;
          }
          while ( v398 );
          v399 = v397 - 1;
          if ( v398 )
            v399 = v397;
          *v399 = 0;
          if ( v398 )
          {
            a5 = --v11;
LABEL_1150:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v400 = -1;
              do
                ++v400;
              while ( v1019[v400] );
              v11 -= v400;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1154:
        v401 = GetDefaultLocale();
        v402 = StringCchPrintf_lW(v1019, 0x28u, L"FileSz %I64d", v401, v1007);
        if ( v402 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v402;
          LODWORD(DestinationSize) = 8546;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1174;
        if ( v843 )
          goto LABEL_1170;
        v403 = 256;
        v404 = v5;
        do
        {
          if ( !*v404 )
            break;
          ++v404;
          --v403;
        }
        while ( v403 );
        if ( v403 )
        {
          v405 = 1;
          v406 = L";";
          v407 = &v5[256 - v403];
          v408 = v403;
          do
          {
            if ( !v405 )
              break;
            if ( !*v406 )
              break;
            *v407++ = *v406++;
            --v405;
            --v408;
          }
          while ( v408 );
          v409 = v407 - 1;
          if ( v408 )
            v409 = v407;
          *v409 = 0;
          if ( v408 )
          {
            a5 = --v11;
LABEL_1170:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v410 = -1;
              do
                ++v410;
              while ( v1019[v410] );
              v11 -= v410;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1174:
        v411 = GetDefaultLocale();
        v412 = StringCchPrintf_lW(v1019, 0x28u, L"Off %I64d", v411, v1008);
        if ( v412 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v412;
          LODWORD(DestinationSize) = 8555;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1194;
        if ( v843 )
          goto LABEL_1190;
        v413 = 256;
        v414 = v5;
        do
        {
          if ( !*v414 )
            break;
          ++v414;
          --v413;
        }
        while ( v413 );
        if ( v413 )
        {
          v415 = 1;
          v416 = L";";
          v417 = &v5[256 - v413];
          v418 = v413;
          do
          {
            if ( !v415 )
              break;
            if ( !*v416 )
              break;
            *v417++ = *v416++;
            --v415;
            --v418;
          }
          while ( v418 );
          v419 = v417 - 1;
          if ( v418 )
            v419 = v417;
          *v419 = 0;
          if ( v418 )
          {
            a5 = --v11;
LABEL_1190:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v420 = -1;
              do
                ++v420;
              while ( v1019[v420] );
              v11 -= v420;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1194:
        v421 = GetDefaultLocale();
        v422 = StringCchPrintf_lW(v1019, 0x28u, L"Sz %I64d", v421, v1009);
        if ( v422 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v422;
          LODWORD(DestinationSize) = 8564;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1214;
        if ( v843 )
          goto LABEL_1210;
        v423 = 256;
        v424 = v5;
        do
        {
          if ( !*v424 )
            break;
          ++v424;
          --v423;
        }
        while ( v423 );
        if ( v423 )
        {
          v425 = 1;
          v426 = L";";
          v427 = &v5[256 - v423];
          v428 = v423;
          do
          {
            if ( !v425 )
              break;
            if ( !*v426 )
              break;
            *v427++ = *v426++;
            --v425;
            --v428;
          }
          while ( v428 );
          v429 = v427 - 1;
          if ( v428 )
            v429 = v427;
          *v429 = 0;
          if ( v428 )
          {
            a5 = --v11;
LABEL_1210:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v430 = -1;
              do
                ++v430;
              while ( v1019[v430] );
              v11 -= v430;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1214:
        v431 = HIWORD(v995);
        v432 = GetDefaultLocale();
        LODWORD(v828) = v431;
        v433 = StringCchPrintf_lW(v1019, 0x28u, L"Flg %04x", v432, v828);
        if ( v433 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v433;
          LODWORD(DestinationSize) = 8573;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          goto LABEL_1234;
        if ( v843 )
          goto LABEL_1230;
        v434 = 256;
        v435 = v5;
        do
        {
          if ( !*v435 )
            break;
          ++v435;
          --v434;
        }
        while ( v434 );
        if ( v434 )
        {
          v436 = 1;
          v437 = L";";
          v438 = &v5[256 - v434];
          v7 = v434;
          do
          {
            if ( !v436 )
              break;
            if ( !*v437 )
              break;
            *v438++ = *v437++;
            --v436;
            --v7;
          }
          while ( v7 );
          v439 = v438 - 1;
          if ( v7 )
            v439 = v438;
          *v439 = 0;
          if ( v7 )
          {
            a5 = --v11;
LABEL_1230:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v7 = (unsigned __int64)v1019;
              v440 = -1;
              do
                ++v440;
              while ( v1019[v440] );
              v11 -= v440;
              a5 = v11;
              v843 = 0;
            }
          }
        }
LABEL_1234:
        if ( *(_WORD *)v337 != 3 || *((_WORD *)v337 + 4) != 2 )
          break;
        v441 = GetDefaultLocale();
        v442 = StringCchPrintf_lW(v1019, 0x28u, L"FileSize %I64d", v441, v1007);
        if ( v442 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v442;
          LODWORD(DestinationSize) = 8589;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( !v11 )
          break;
        if ( v843 )
          goto LABEL_1252;
        v443 = 256;
        v444 = v5;
        do
        {
          if ( !*v444 )
            break;
          ++v444;
          --v443;
        }
        while ( v443 );
        if ( v443 )
        {
          v445 = 1;
          v446 = L";";
          v7 = (unsigned __int64)&v5[256 - v443];
          v447 = v443;
          do
          {
            if ( !v445 )
              break;
            if ( !*v446 )
              break;
            *(_WORD *)v7 = *v446;
            v7 += 2LL;
            ++v446;
            --v445;
            --v447;
          }
          while ( v447 );
          v448 = (_WORD *)(v7 - 2);
          if ( v447 )
            v448 = (_WORD *)v7;
          *v448 = 0;
          if ( v447 )
          {
            a5 = --v11;
LABEL_1252:
            if ( (int)StringCchCatW(v5, 0x100u, v1019) >= 0 )
            {
              v7 = (unsigned __int64)v1019;
              v449 = -1;
              do
                ++v449;
              while ( v1019[v449] );
              v11 -= v449;
              a5 = v11;
              v843 = 0;
            }
          }
        }
        break;
      default:
        utassert_fail(1u, "FALSE", "dumplog.cpp", 8448, "Invalid switch value");
        goto LABEL_1037;
    }
  }
  if ( *((_BYTE *)v6 + 22) != 0x92 )
    goto LABEL_1588;
  v891 = 0;
  v890 = 0;
  v450 = (DatabaseMetaLog *)((char *)v6 + 32);
  v451 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 32), 0, &v891);
  v452 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 32), 1u, &v890);
  v846 = 0;
  *(_QWORD *)((char *)v849 + 6) = 0;
  v849[2] = 0;
  v848 = 0;
  v851 = 0;
  v880 &= 0xFFE0u;
  VarLogData::GetData(v450, 0, &v891);
  VarLogData::GetData(v450, 1u, &v890);
  v453 = v451 + 8;
  v89 = (*v453 & 1) == 0;
  v847 = v453;
  if ( v89 )
  {
    v844 = 0;
    v457 = 0;
    *(_DWORD *)((char *)&v849[1] + 6) = 0;
    switch ( *v453 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v457 = *((unsigned __int16 *)v453 + 1);
        if ( v457 - 1 > 0x1F9D )
          RaiseInconsistencyError(v453, 6);
        break;
      case 1:
      case 3:
      case 5:
      case 7:
      case 9:
      case 0xB:
      case 0xD:
        utassert_fail(
          1u,
          "FALSE",
          "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
          294,
          "Invalid switch value");
        break;
      case 4:
        v457 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v457 = 1;
        break;
    }
    LODWORD(v848) = v457;
  }
  else
  {
    v844 = 1;
    v454 = *v453;
    switch ( *v453 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v453 + 1) < 0 )
        {
          v455 = HIBYTE(*(_WORD *)(v453 + 1)) | ((*(_WORD *)(v453 + 1) & 0x7F) << 8);
          v845 = v455;
          LOWORD(v849[0]) = 3;
          v456 = 3;
        }
        else
        {
          v455 = v453[1];
          v845 = v455;
          LOWORD(v849[0]) = 2;
          v456 = 2;
        }
        WORD2(v849[0]) = v456 + (((unsigned int)v455 + 1) >> 1);
        if ( v455 > 0x1Eu )
          WORD1(v849[0]) = (v455 - 1) / 30;
        else
          WORD1(v849[0]) = 0;
        v850 = 0;
        v457 = 0;
        break;
      case 1:
      case 2:
      case 3:
      case 5:
      case 6:
      case 7:
      case 9:
      case 0xA:
      case 0xB:
      case 0xD:
      case 0xE:
      case 0xF:
      case 0x11:
      case 0x12:
      case 0x13:
      case 0x15:
      case 0x16:
      case 0x17:
      case 0x19:
      case 0x1A:
      case 0x1B:
        utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
        v457 = 0;
        break;
      case 4:
        if ( (v454 & 0x1C) == 4 && (v454 & 2) != 0 )
        {
          LODWORD(v849[0]) = 0;
          v845 = 0;
          WORD2(v849[0]) = 0;
          HIWORD(v849[1]) = 0;
          v846 = 15;
          v850 = 1;
          v457 = 0;
        }
        else
        {
          LODWORD(v849[0]) = 0;
          v845 = 0;
          WORD2(v849[0]) = 0;
          HIWORD(v849[1]) = 0;
          v846 = 1;
          v850 = 0;
          v457 = 0;
        }
        break;
      case 8:
        LODWORD(v849[0]) = 0;
        v845 = 0;
        WORD2(v849[0]) = 0;
        HIWORD(v849[1]) = 0;
        v846 = 9;
        v850 = 0;
        v457 = 0;
        break;
    }
  }
  v878 = -35;
  v879 = 35;
  v458 = v880 & 0xFFE0;
  v880 &= 0xFFE0u;
  v881 = 0;
  if ( !v844 )
  {
    if ( (*v847 & 0x10) != 0 )
    {
      if ( *(_WORD *)&v847[v457] >= 0x23u )
      {
        LOBYTE(v461) = v847[v457 + 6] >> 2;
        v460 = 1;
      }
      else
      {
        v461 = ~(v458 >> 4);
        v460 = 0;
      }
      v459 = v461 & 1;
    }
    else
    {
      if ( ((1 << (*v847 & 0xE)) & 0x1105) == 0 )
        goto LABEL_1292;
      v459 = ((v458 >> 4) & 1) == 0;
      v460 = 0;
    }
    if ( v459 )
    {
      v462 = 0;
      v463 = 0;
      v851 = 0;
      v464 = 0;
      goto LABEL_1407;
    }
    if ( !v460 && (v880 & 0x10) != 0 )
    {
      v462 = (const unsigned __int8 *)4;
      v463 = *v881;
      v851 = *v881;
      v464 = 0;
      goto LABEL_1407;
    }
LABEL_1292:
    if ( !v846 )
    {
      v845 = 0;
      v465 = (unsigned int)v848;
      HIDWORD(v848) = (_DWORD)v848;
      if ( (*v847 & 0x10) != 0 )
      {
        v465 = (((unsigned int)*(unsigned __int16 *)&v847[(unsigned int)v848] + 7) >> 3) + (_DWORD)v848 + 2;
        HIDWORD(v848) = v465;
      }
      if ( (*v847 & 0x20) != 0 )
      {
        v466 = &v847[v465];
        WORD2(v849[0]) = *(_WORD *)v466;
        if ( !WORD2(v849[0]) )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v467 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v467 )
            {
              v468 = *(_QWORD *)(v467 + 96);
              if ( v468 )
              {
                if ( *(_BYTE *)(v468 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 3);
        }
        LODWORD(v849[0]) = HIDWORD(v848) + 2 * (WORD2(v849[0]) + 1);
        if ( LODWORD(v849[0]) > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v469 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v469 )
            {
              v470 = *(_QWORD *)(v469 + 96);
              if ( v470 )
              {
                if ( *(_BYTE *)(v470 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 4);
        }
        v465 = *(_WORD *)&v466[2 * WORD2(v849[0])] & 0x7FFF;
        v846 = v465;
        if ( LODWORD(v849[0]) > v465 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v471 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v471 )
            {
              v472 = *(_QWORD *)(v471 + 96);
              if ( v472 )
              {
                if ( *(_BYTE *)(v472 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 4);
          v465 = v846;
        }
        while ( *(__int16 *)&v466[2 * WORD2(v849[0])] < 0 )
        {
          v473 = &v847[HIDWORD(v848)];
          if ( WORD2(v849[0]) == 1 )
            v474 = v849[0];
          else
            v474 = *(_WORD *)&v473[2 * WORD2(v849[0]) - 2] & 0x7FFF;
          if ( v474 < LODWORD(v849[0]) || (*(_WORD *)&v473[2 * WORD2(v849[0])] & 0x7FFFu) < v474 )
          {
            RaiseInconsistencyError(v847, 7);
            v465 = v846;
          }
          if ( v474 < LODWORD(v849[0]) || v474 > v465 )
            goto LABEL_1383;
          v475 = *(_WORD *)&v847[v474];
          if ( v475 == 5 )
          {
            v845 |= 2u;
            --WORD2(v849[0]);
            WORD1(v849[2]) = v474;
            v476 = *(_WORD *)&v847[(unsigned __int16)v474 + 2];
            v477 = WORD2(v849[2]) & 0xC7FF;
            if ( (v476 & 0x4000) != 0 )
              v477 = WORD2(v849[2]) ^ (WORD2(v849[2]) ^ v476) & 0x3800;
            WORD2(v849[2]) = v477 ^ (v476 ^ v477) & 0x7FF;
            break;
          }
          if ( v475 >= 0x400u )
          {
            v845 |= 1u;
            if ( --WORD2(v849[0]) )
              continue;
          }
          break;
        }
      }
      else
      {
        v846 = v465;
        WORD2(v849[0]) = 0;
        LODWORD(v849[0]) = v465;
      }
      if ( (*v847 & 0x40) != 0 )
      {
        *(_DWORD *)((char *)&v849[1] + 6) = v465;
        v846 = v465 + 14;
        v478 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v845);
        v479 = HIDWORD(*(_QWORD *)v478);
        v480 = HIWORD(*(_QWORD *)v478);
        v481 = 0;
        if ( (((__int16)v480 ^ ((unsigned int)(__int16)v480 >> 1)) & 0x2000) != 0 )
        {
          v482 = v480 & 0xDFFF;
          if ( (v480 & 0x4000) != 0 )
            v482 = v480 | 0x2000;
          LOWORD(v480) = v482;
        }
        if ( (_WORD)v480 == 0xFFFC )
          v481 = (unsigned __int16)v479 >> 5;
        v465 = v481 + v846;
        v846 += v481;
      }
      else
      {
        *(_DWORD *)((char *)&v849[1] + 6) = 0;
      }
      if ( *(_QWORD *)((char *)v849 + 6) && *(_QWORD *)((char *)v849 + 6) < (unsigned __int64)&v847[v465] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v483 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v483 )
          {
            v484 = *(_QWORD *)(v483 + 96);
            if ( v484 )
            {
              if ( *(_BYTE *)(v484 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v11 = a5;
        }
        RaiseInconsistencyError(v847, 18);
        v465 = v846;
      }
      if ( v465 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v485 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v485 )
          {
            v486 = *(_QWORD *)(v485 + 96);
            if ( v486 )
            {
              if ( *(_BYTE *)(v486 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
          v11 = a5;
        }
        RaiseInconsistencyError(v847, 5);
      }
    }
LABEL_1383:
    v487 = -(__int16)v878;
    if ( (v880 & 0x10) == 0 )
      goto LABEL_1386;
    if ( (*v847 & 0x10) != 0 )
    {
      if ( v878 < (int)v848 && *(_WORD *)&v847[(unsigned int)v848] >= v879 )
      {
LABEL_1386:
        if ( v487 > (unsigned int)WORD2(v849[0]) )
        {
          v462 = v847;
          v463 = 0;
          v851 = 0;
          v464 = 0;
        }
        else
        {
          v488 = &v847[HIDWORD(v848)];
          if ( v487 == 1 )
          {
            v489 = v849[0];
          }
          else
          {
            _mm_lfence();
            v489 = *(_WORD *)&v488[2 * v487 - 2] & 0x7FFF;
            v11 = a5;
          }
          v490 = *(_WORD *)&v488[2 * v487] & 0x7FFF;
          if ( v489 < LODWORD(v849[0]) || v490 < v489 )
            RaiseInconsistencyError(v847, 7);
          v462 = &v847[v489];
          v463 = v490 - v489;
          v851 = v463;
          v464 = 0;
        }
        goto LABEL_1407;
      }
    }
    else if ( ((1 << (*v847 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_1386;
    }
    v462 = (const unsigned __int8 *)(v881 + 1);
    v463 = *v881;
    v851 = *v881;
    v464 = 0;
    goto LABEL_1407;
  }
  v464 = 0;
  v901 = 0;
  v462 = CDRecord::LocateColumnInternal(
           (CDRecord *)&v845,
           (const struct PhysicalColumnAttribute *)&v878,
           v458,
           &v851,
           &v901);
  if ( v844 && v848 && *(_QWORD *)v848 && (v880 & 8) == 0 && (v901 & 1) == 0 )
  {
    if ( !v462 || v462 == &g_bitValueOne )
    {
      v463 = 0;
      v851 = 0;
      v462 = 0;
      goto LABEL_1407;
    }
    LODWORD(DestinationSize) = 0;
    v462 = PageComprMgr::DecompressColumnPartialInline(
             v848,
             (const struct PhysicalColumnAttribute *)&v878,
             v462,
             v851,
             0,
             DestinationSize,
             &v851,
             v901);
  }
  v463 = v851;
LABEL_1407:
  v491 = 0;
  if ( v463 && v462 && v463 == 8 )
    v491 = *(_QWORD *)v462;
  v492 = (char *)(v452 + 8);
  v89 = (v452[8] & 1) == 0;
  v847 = v452 + 8;
  if ( v89 )
  {
    v844 = 0;
    v496 = 0;
    v846 = 0;
    *(_DWORD *)((char *)&v849[1] + 6) = 0;
    switch ( *v492 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v496 = *((unsigned __int16 *)v452 + 5);
        if ( v496 - 1 > 0x1F9D )
          RaiseInconsistencyError(v452 + 8, 6);
        break;
      case 1:
      case 3:
      case 5:
      case 7:
      case 9:
      case 0xB:
      case 0xD:
        utassert_fail(
          1u,
          "FALSE",
          "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
          294,
          "Invalid switch value");
        break;
      case 4:
        v496 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v496 = 1;
        break;
    }
    LODWORD(v848) = v496;
    *(_QWORD *)((char *)v849 + 6) = 0;
  }
  else
  {
    v844 = 1;
    v493 = *v492;
    switch ( *v492 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v452 + 9) < 0 )
        {
          v494 = HIBYTE(*(_WORD *)(v452 + 9)) | ((*(_WORD *)(v452 + 9) & 0x7F) << 8);
          v845 = v494;
          LOWORD(v849[0]) = 3;
          v495 = 3;
        }
        else
        {
          v494 = v452[9];
          v845 = v494;
          v495 = 2;
          LOWORD(v849[0]) = 2;
        }
        WORD2(v849[0]) = v495 + (((unsigned int)v494 + 1) >> 1);
        if ( v494 > 0x1Eu )
          WORD1(v849[0]) = (v494 - 1) / 30;
        else
          WORD1(v849[0]) = 0;
        v846 = 0;
        v850 = 0;
        v849[2] = 0;
        v848 = 0;
        v496 = 0;
        break;
      case 1:
      case 2:
      case 3:
      case 5:
      case 6:
      case 7:
      case 9:
      case 0xA:
      case 0xB:
      case 0xD:
      case 0xE:
      case 0xF:
      case 0x11:
      case 0x12:
      case 0x13:
      case 0x15:
      case 0x16:
      case 0x17:
      case 0x19:
      case 0x1A:
      case 0x1B:
        utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
        v849[2] = 0;
        v848 = 0;
        v496 = 0;
        break;
      case 4:
        if ( (v493 & 0x1C) == 4 && (v493 & 2) != 0 )
        {
          memset(v849, 0, sizeof(v849));
          v845 = 0;
          v846 = 15;
          v850 = 1;
          v848 = 0;
          v496 = 0;
        }
        else
        {
          memset(v849, 0, sizeof(v849));
          v845 = 0;
          v846 = 1;
          v850 = 0;
          v848 = 0;
          v496 = 0;
        }
        break;
      case 8:
        memset(v849, 0, sizeof(v849));
        v845 = 0;
        v846 = 9;
        v850 = 0;
        v848 = 0;
        v496 = 0;
        break;
    }
  }
  v878 = -35;
  v879 = 35;
  v497 = v880 & 0xFFE0;
  v880 &= 0xFFE0u;
  v881 = 0;
  if ( !v844 )
  {
    if ( (*v847 & 0x10) != 0 )
    {
      if ( *(_WORD *)&v847[v496] >= 0x23u )
      {
        LOBYTE(v498) = v847[v496 + 6] >> 2;
        v499 = 1;
      }
      else
      {
        v498 = ~(v497 >> 4);
        v499 = 0;
      }
    }
    else
    {
      if ( ((1 << (*v847 & 0xE)) & 0x1105) == 0 )
        goto LABEL_1446;
      LOBYTE(v498) = ~(unsigned __int8)(v497 >> 4);
      v499 = 0;
    }
    if ( (v498 & 1) != 0 )
    {
      v500 = 0;
      v501 = 0;
      v851 = 0;
      goto LABEL_1563;
    }
    if ( !v499 && (v880 & 0x10) != 0 )
    {
      v500 = (const unsigned __int8 *)4;
      v501 = *v881;
      v851 = *v881;
      goto LABEL_1563;
    }
LABEL_1446:
    if ( !v846 )
    {
      v845 = 0;
      v502 = (unsigned int)v848;
      HIDWORD(v848) = (_DWORD)v848;
      if ( (*v847 & 0x10) != 0 )
      {
        v502 = (((unsigned int)*(unsigned __int16 *)&v847[(unsigned int)v848] + 7) >> 3) + (_DWORD)v848 + 2;
        HIDWORD(v848) = v502;
      }
      if ( (*v847 & 0x20) != 0 )
      {
        v503 = &v847[v502];
        WORD2(v849[0]) = *(_WORD *)v503;
        if ( !WORD2(v849[0]) )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v504 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v504 )
            {
              v505 = *(_QWORD *)(v504 + 96);
              if ( v505 )
              {
                if ( *(_BYTE *)(v505 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 3);
        }
        LODWORD(v849[0]) = HIDWORD(v848) + 2 * (WORD2(v849[0]) + 1);
        if ( LODWORD(v849[0]) > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v506 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v506 )
            {
              v507 = *(_QWORD *)(v506 + 96);
              if ( v507 )
              {
                if ( *(_BYTE *)(v507 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 4);
        }
        v502 = *(_WORD *)&v503[2 * WORD2(v849[0])] & 0x7FFF;
        v846 = v502;
        if ( LODWORD(v849[0]) > v502 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v508 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v508 )
            {
              v509 = *(_QWORD *)(v508 + 96);
              if ( v509 )
              {
                if ( *(_BYTE *)(v509 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
            v11 = a5;
          }
          RaiseInconsistencyError(v847, 4);
          v502 = v846;
        }
        while ( *(__int16 *)&v503[2 * WORD2(v849[0])] < 0 )
        {
          v510 = &v847[HIDWORD(v848)];
          if ( WORD2(v849[0]) == 1 )
            v511 = v849[0];
          else
            v511 = *(_WORD *)&v510[2 * WORD2(v849[0]) - 2] & 0x7FFF;
          if ( v511 < LODWORD(v849[0]) || (*(_WORD *)&v510[2 * WORD2(v849[0])] & 0x7FFFu) < v511 )
          {
            RaiseInconsistencyError(v847, 7);
            v502 = v846;
          }
          if ( v511 < LODWORD(v849[0]) || v511 > v502 )
            goto LABEL_1539;
          v512 = *(_WORD *)&v847[v511];
          if ( v512 == 5 )
          {
            v845 |= 2u;
            --WORD2(v849[0]);
            WORD1(v849[2]) = v511;
            v513 = &v847[(unsigned __int16)v511];
            v514 = *((_WORD *)v513 + 1);
            if ( (v514 & 0x4000) != 0 )
              v515 = (WORD2(v849[2]) ^ v514) & 0x3800 ^ WORD2(v849[2]);
            else
              v515 = WORD2(v849[2]) & 0xC7FF;
            WORD2(v849[2]) = v515;
            WORD2(v849[2]) = v515 ^ (*((_WORD *)v513 + 1) ^ v515) & 0x7FF;
            break;
          }
          if ( v512 >= 0x400u )
          {
            v845 |= 1u;
            if ( --WORD2(v849[0]) )
              continue;
          }
          break;
        }
      }
      else
      {
        v846 = v502;
        WORD2(v849[0]) = 0;
        LODWORD(v849[0]) = v502;
      }
      if ( (*v847 & 0x40) != 0 )
      {
        *(_DWORD *)((char *)&v849[1] + 6) = v502;
        v846 = v502 + 14;
        v516 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v845);
        v517 = HIDWORD(*(_QWORD *)v516);
        v518 = HIWORD(*(_QWORD *)v516);
        v519 = 0;
        if ( (((__int16)v518 ^ ((unsigned int)(__int16)v518 >> 1)) & 0x2000) != 0 )
        {
          v520 = v518 & 0xDFFF;
          if ( (v518 & 0x4000) != 0 )
            v520 = v518 | 0x2000;
          LOWORD(v518) = v520;
        }
        if ( (_WORD)v518 == 0xFFFC )
          v519 = (unsigned __int16)v517 >> 5;
        v502 = v519 + v846;
        v846 += v519;
      }
      else
      {
        *(_DWORD *)((char *)&v849[1] + 6) = 0;
      }
      if ( *(_QWORD *)((char *)v849 + 6) && *(_QWORD *)((char *)v849 + 6) < (unsigned __int64)&v847[v502] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v521 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v521 )
          {
            v522 = *(_QWORD *)(v521 + 96);
            if ( v522 )
            {
              if ( *(_BYTE *)(v522 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
          v11 = a5;
        }
        RaiseInconsistencyError(v847, 18);
        v502 = v846;
      }
      if ( v502 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v523 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v523 )
          {
            v524 = *(_QWORD *)(v523 + 96);
            if ( v524 )
            {
              if ( *(_BYTE *)(v524 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
          v11 = a5;
        }
        RaiseInconsistencyError(v847, 5);
      }
    }
LABEL_1539:
    v525 = -(__int16)v878;
    if ( (v880 & 0x10) == 0 )
      goto LABEL_1542;
    if ( (*v847 & 0x10) != 0 )
    {
      if ( v878 < (int)v848 && *(_WORD *)&v847[(unsigned int)v848] >= v879 )
      {
LABEL_1542:
        if ( v525 > (unsigned int)WORD2(v849[0]) )
        {
          v500 = v847;
          v501 = 0;
          v464 = 0;
          v851 = 0;
        }
        else
        {
          v526 = &v847[HIDWORD(v848)];
          if ( v525 == 1 )
          {
            v527 = v849[0];
          }
          else
          {
            _mm_lfence();
            v527 = *(_WORD *)&v526[2 * v525 - 2] & 0x7FFF;
            v11 = a5;
          }
          v528 = *(_WORD *)&v526[2 * v525] & 0x7FFF;
          if ( v527 < LODWORD(v849[0]) || v528 < v527 )
            RaiseInconsistencyError(v847, 7);
          v500 = &v847[v527];
          v501 = v528 - v527;
          v464 = 0;
          v851 = v501;
        }
        goto LABEL_1563;
      }
    }
    else if ( ((1 << (*v847 & 0xE)) & 0x1105) == 0 )
    {
      goto LABEL_1542;
    }
    v500 = (const unsigned __int8 *)(v881 + 1);
    v501 = *v881;
    v464 = 0;
    v851 = *v881;
    goto LABEL_1563;
  }
  v902 = 0;
  v500 = CDRecord::LocateColumnInternal(
           (CDRecord *)&v845,
           (const struct PhysicalColumnAttribute *)&v878,
           v497,
           &v851,
           &v902);
  if ( v844 && v848 && *(_QWORD *)v848 && (v880 & 8) == 0 && (v902 & 1) == 0 )
  {
    if ( !v500 || v500 == &g_bitValueOne )
    {
      v501 = 0;
      v851 = 0;
      v500 = 0;
      goto LABEL_1563;
    }
    LODWORD(DestinationSize) = 0;
    v500 = PageComprMgr::DecompressColumnPartialInline(
             v848,
             (const struct PhysicalColumnAttribute *)&v878,
             v500,
             v851,
             0,
             DestinationSize,
             &v851,
             v902);
  }
  v501 = v851;
LABEL_1563:
  if ( v501 && v500 && v501 == 8 )
    v464 = *(_QWORD *)v500;
  v529 = GetDefaultLocale();
  LODWORD(v837) = v890;
  LODWORD(DestinationSize) = v891;
  v6 = v877;
  LODWORD(v826) = *((_DWORD *)v877 + 7);
  v530 = StringCchPrintf_lW(
           v1060,
           0x100u,
           L"File Id %d; Old Header Len = %d; New HeaderLen = %d; Old Container Size = %I64d; New Container Size = %I64d",
           v529,
           v826,
           DestinationSize,
           v837,
           v491,
           v464);
  if ( v530 < 0 )
  {
    _mm_lfence();
    LODWORD(v837) = v530;
    LODWORD(DestinationSize) = 8674;
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
    v11 = a5;
  }
  if ( v11 )
  {
    if ( v843 )
      goto LABEL_1584;
    v531 = 256;
    v7 = (unsigned __int64)v5;
    do
    {
      if ( !*(_WORD *)v7 )
        break;
      v7 += 2LL;
      --v531;
    }
    while ( v531 );
    if ( v531 )
    {
      v532 = 1;
      v533 = L";";
      v7 = (unsigned __int64)&v5[256 - v531];
      v534 = v531;
      do
      {
        if ( !v532 )
          break;
        if ( !*v533 )
          break;
        *(_WORD *)v7 = *v533;
        v7 += 2LL;
        ++v533;
        --v532;
        --v534;
      }
      while ( v534 );
      v535 = (_WORD *)(v7 - 2);
      if ( v534 )
        v535 = (_WORD *)v7;
      *v535 = 0;
      if ( v534 )
      {
        a5 = --v11;
LABEL_1584:
        if ( (int)StringCchCatW(v5, 0x100u, v1060) >= 0 )
        {
          v7 = (unsigned __int64)v1060;
          v536 = -1;
          do
            ++v536;
          while ( v1060[v536] );
          v11 -= v536;
          a5 = v11;
          v843 = 0;
        }
      }
    }
  }
LABEL_1588:
  if ( *((_BYTE *)v6 + 22) == 0x93 )
  {
    if ( v6 == (DatabaseMetaLog *)-28LL )
    {
      v926 = 0;
      *_errno() = 22;
      _invalid_parameter_noinfo();
      v537 = v926;
    }
    else
    {
      v537 = *(_QWORD *)((char *)v6 + 28);
      v926 = v537;
    }
    v538 = GetDefaultLocale();
    LODWORD(v826) = *((_DWORD *)v6 + 6);
    v539 = StringCchPrintf_lW(
             v1058,
             0xC8u,
             L"Filestream Container Size Delta File Id: %d, Delta: %I64d",
             v538,
             v826,
             v537);
    if ( v539 < 0 )
    {
      _mm_lfence();
      LODWORD(v837) = v539;
      LODWORD(DestinationSize) = 8695;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
      v11 = a5;
    }
    if ( v11 )
    {
      if ( v843 )
        goto LABEL_1608;
      v540 = 256;
      v7 = (unsigned __int64)v5;
      do
      {
        if ( !*(_WORD *)v7 )
          break;
        v7 += 2LL;
        --v540;
      }
      while ( v540 );
      if ( v540 )
      {
        v541 = 1;
        v542 = L";";
        v7 = (unsigned __int64)&v5[256 - v540];
        v543 = v540;
        do
        {
          if ( !v541 )
            break;
          if ( !*v542 )
            break;
          *(_WORD *)v7 = *v542;
          v7 += 2LL;
          ++v542;
          --v541;
          --v543;
        }
        while ( v543 );
        v544 = (_WORD *)(v7 - 2);
        if ( v543 )
          v544 = (_WORD *)v7;
        *v544 = 0;
        if ( v543 )
        {
          a5 = --v11;
LABEL_1608:
          if ( (int)StringCchCatW(v5, 0x100u, v1058) >= 0 )
          {
            v7 = (unsigned __int64)v1058;
            v545 = -1;
            do
              ++v545;
            while ( v1058[v545] );
            v11 -= v545;
            a5 = v11;
            v843 = 0;
          }
        }
      }
    }
  }
  if ( *((_BYTE *)v6 + 22) != 0x98 )
    goto LABEL_1646;
  switch ( *((_BYTE *)v6 + 23) )
  {
    case 0:
    case 0x16:
      v546 = VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 24), 0, &v922);
      v7 = v922;
      v547 = v922 / 0x50;
      if ( !v11 )
        goto LABEL_1630;
      if ( v843 )
        goto LABEL_1628;
      v548 = 256;
      v7 = (unsigned __int64)v5;
      do
      {
        if ( !*(_WORD *)v7 )
          break;
        v7 += 2LL;
        --v548;
      }
      while ( v548 );
      if ( v548 )
      {
        v549 = 1;
        v550 = L";";
        v7 = (unsigned __int64)&v5[256 - v548];
        v551 = v548;
        do
        {
          if ( !v549 )
            break;
          if ( !*v550 )
            break;
          *(_WORD *)v7 = *v550;
          v7 += 2LL;
          ++v550;
          --v549;
          --v551;
        }
        while ( v551 );
        v552 = (_WORD *)(v7 - 2);
        if ( v551 )
          v552 = (_WORD *)v7;
        *v552 = 0;
        if ( v551 )
        {
          a5 = --v11;
LABEL_1628:
          if ( (int)StringCchCatW(v5, 0x100u, L"XdesIDs: ") >= 0 )
          {
            v11 -= 9;
            a5 = v11;
            v843 = 0;
          }
        }
      }
LABEL_1630:
      for ( i = 0; i < (unsigned __int16)v547; ++i )
      {
        if ( i && v11 && (int)StringCchCatW(v5, 0x100u, L",") >= 0 )
        {
          a5 = --v11;
          v843 = 0;
        }
        v554 = *(unsigned __int16 *)&v546[80 * i + 4];
        v555 = GetDefaultLocale();
        LODWORD(DestinationSize) = *(_DWORD *)&v546[80 * i];
        LODWORD(v826) = v554;
        v556 = StringCchPrintf_lW(v1026, 0xEu, L"%04lx:%08lx", v555, v826, DestinationSize);
        if ( v556 < 0 )
        {
          _mm_lfence();
          LODWORD(v837) = v556;
          LODWORD(DestinationSize) = 3187;
          ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", DestinationSize, v837);
          v11 = a5;
        }
        if ( v11 && (int)StringCchCatW(v5, 0x100u, v1026) >= 0 )
        {
          v7 = (unsigned __int64)v1026;
          v557 = -1;
          do
            ++v557;
          while ( v1026[v557] );
          v11 -= v557;
          a5 = v11;
          v843 = 0;
        }
        if ( v11 < 0xF )
          break;
      }
      v6 = v877;
LABEL_1646:
      v558 = *((_BYTE *)v6 + 22);
      if ( v558 != -103 )
        goto LABEL_1690;
      v896 = (struct LSN *)*((_QWORD *)v6 + 4);
      LOWORD(v897) = *((_WORD *)v6 + 20);
      v1017[22] = 0;
      v1017[21] = a0123456789abcd_4[v897 & 0xF];
      v1017[20] = a0123456789abcd_4[((unsigned __int16)v897 >> 4) & 0xF];
      v1017[19] = a0123456789abcd_4[BYTE1(v897) & 0xF];
      v1017[18] = a0123456789abcd_4[(unsigned __int16)v897 >> 12];
      v1017[17] = 58;
      v1017[16] = a0123456789abcd_4[BYTE4(v896) & 0xF];
      v1017[15] = a0123456789abcd_4[BYTE4(v896) >> 4];
      v1017[14] = a0123456789abcd_4[BYTE5(v896) & 0xF];
      v1017[13] = a0123456789abcd_4[WORD2(v896) >> 12];
      v1017[12] = a0123456789abcd_4[BYTE6(v896) & 0xF];
      v1017[11] = a0123456789abcd_4[(HIDWORD(v896) >> 20) & 0xF];
      v1017[10] = a0123456789abcd_4[HIBYTE(v896) & 0xF];
      v1017[9] = a0123456789abcd_4[HIDWORD(v896) >> 28];
      v1017[8] = 58;
      v1017[7] = a0123456789abcd_4[(unsigned __int8)v896 & 0xF];
      v1017[6] = a0123456789abcd_4[(unsigned __int8)v896 >> 4];
      v1017[5] = a0123456789abcd_4[BYTE1(v896) & 0xF];
      v1017[4] = a0123456789abcd_4[(unsigned __int16)v896 >> 12];
      v1017[3] = a0123456789abcd_4[BYTE2(v896) & 0xF];
      v1017[2] = a0123456789abcd_4[((unsigned int)v896 >> 20) & 0xF];
      v1017[1] = a0123456789abcd_4[BYTE3(v896) & 0xF];
      v1017[0] = a0123456789abcd_4[(unsigned int)v896 >> 28];
      if ( !v11 )
        goto LABEL_1668;
      if ( v843 )
        goto LABEL_1661;
      v559 = 256;
      v560 = v5;
      do
      {
        if ( !*v560 )
          break;
        ++v560;
        --v559;
      }
      while ( v559 );
      if ( v559 )
      {
        v561 = 1;
        v562 = L";";
        v563 = &v5[256 - v559];
        v564 = v559;
        do
        {
          if ( !v561 )
            break;
          if ( !*v562 )
            break;
          *v563++ = *v562++;
          --v561;
          --v564;
        }
        while ( v564 );
        v565 = v563 - 1;
        if ( v564 )
          v565 = v563;
        *v565 = 0;
        if ( v564 )
        {
          a5 = --v11;
LABEL_1661:
          if ( (int)StringCchCatW(v5, 0x100u, L"log_minRecoveryLsn ") >= 0 )
          {
            v11 -= 19;
            a5 = v11;
            v843 = 0;
          }
        }
      }
      if ( !v11 )
      {
LABEL_1668:
        v566 = -1;
        goto LABEL_1669;
      }
      v566 = -1;
      if ( (int)StringCchCatW(v5, 0x100u, v1017) >= 0 )
      {
        v567 = -1;
        do
          ++v567;
        while ( v1017[v567] );
        v11 -= v567;
        a5 = v11;
        v843 = 0;
      }
LABEL_1669:
      LSN::FormatAsHexString((LSN *)((char *)v6 + 52), v1017, &v892);
      if ( v11 )
      {
        if ( !v843 )
        {
          v568 = 256;
          v569 = v5;
          do
          {
            if ( !*v569 )
              break;
            ++v569;
            --v568;
          }
          while ( v568 );
          if ( !v568 )
            goto LABEL_1685;
          v570 = 1;
          v571 = &v5[256 - v568];
          v572 = v568;
          v573 = L";";
          do
          {
            if ( !v570 )
              break;
            if ( !*v573 )
              break;
            *v571++ = *v573++;
            --v570;
            --v572;
          }
          while ( v572 );
          v574 = v571 - 1;
          if ( v572 )
            v574 = v571;
          *v574 = 0;
          if ( !v572 )
            goto LABEL_1685;
          a5 = --v11;
        }
        if ( (int)StringCchCatW(v5, 0x100u, L"log_replbeginlsn ") >= 0 )
        {
          v11 -= 17;
          a5 = v11;
          v843 = 0;
        }
LABEL_1685:
        if ( v11 && (int)StringCchCatW(v5, 0x100u, v1017) >= 0 )
        {
          do
            ++v566;
          while ( v1017[v566] );
          a5 = v11 - v566;
          v843 = 0;
        }
      }
      LSN::FormatAsHexString((LSN *)v6 + 8, v1017, &v892);
      DumpLogRecord::Append(v575, v5, L"log_replnextlsn ", &a5, 1, &v843, 0xFFu);
      DumpLogRecord::Append(v576, v5, v1017, &a5, 0, &v843, 0xFFu);
      LSN::FormatAsHexString((LSN *)((char *)v6 + 76), v1017, &v892);
      DumpLogRecord::Append(v577, v5, L"log_distbackuplsn ", &a5, 1, &v843, 0xFFu);
      DumpLogRecord::Append(v578, v5, v1017, &a5, 0, &v843, 0xFFu);
      LSN::FormatAsHexString((LSN *)v6 + 11, v1017, &v892);
      DumpLogRecord::Append(v579, v5, L"log_distlastlsn ", &a5, 1, &v843, 0xFFu);
      DumpLogRecord::Append(v580, v5, v1017, &a5, 0, &v843, 0xFFu);
      v558 = *((_BYTE *)v6 + 22);
LABEL_1690:
      if ( v558 == -76 )
      {
        v581 = *((unsigned __int16 *)v6 + 13) >> 1;
        LogicalName = LogRec_FulltextCreate::GetLogicalName(v6);
        DumpLogRecord::AppendWChars(v583, v5, LogicalName, v581, &a5, 1, &v843);
        v584 = *((unsigned __int16 *)v6 + 14) >> 1;
        PhysicalName = LogRec_FulltextCreate::GetPhysicalName(v6);
        DumpLogRecord::AppendWChars(v586, v5, PhysicalName, v584, &a5, 1, &v843);
        v558 = *((_BYTE *)v6 + 22);
      }
      if ( v558 == -75 )
      {
        v587 = *((unsigned __int16 *)v6 + 13) >> 1;
        v588 = LogRec_FulltextDrop::GetLogicalName(v6);
        DumpLogRecord::AppendWChars(v589, v5, v588, v587, &a5, 1, &v843);
        v590 = *((unsigned __int16 *)v6 + 14) >> 1;
        v591 = LogRec_FulltextDrop::GetPhysicalName(v6);
        DumpLogRecord::AppendWChars(v592, v5, v591, v590, &a5, 1, &v843);
        v558 = *((_BYTE *)v6 + 22);
      }
      if ( v558 == -113 )
      {
        v593 = *((_WORD *)v6 + 16) >> 3;
        LockMigrateInfo = LockMigrateLog::GetLockMigrateInfo(v6);
        UtilDbccFormatPageId(v1030, (DatabaseMetaLog *)((char *)v6 + 24), &v903);
        DumpLogRecord::Append(v595, v5, L"Page ", &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v596, v5, v1030, &a5, 0, &v843, 0xFFu);
        HoBtId = LockMigrateLog::GetHoBtId(v6);
        if ( HoBtId )
        {
          UtilDbccFormatHoBtId(v1039, HoBtId, &v903);
          DumpLogRecord::Append(v599, v5, L"HoBtId ", &a5, 1, &v843, 0xFFu);
          DumpLogRecord::Append(v600, v5, v1039, &a5, 0, &v843, 0xFFu);
        }
        DumpLogRecord::Append(v598, v5, L"XdesIds ", &a5, 1, &v843, 0xFFu);
        v601 = 0;
        if ( v593 )
        {
          do
          {
            UtilDbccFormatXdesId(v1029, (const struct LockMigrateLogInfo *)((char *)LockMigrateInfo + 8 * v601), &v903);
            if ( v601 )
              DumpLogRecord::Append(v602, v5, L",", &a5, 0, &v843, 0xFFu);
            DumpLogRecord::Append(v602, v5, v1029, &a5, 0, &v843, 0xFFu);
            v604 = L" X";
            if ( (*((_BYTE *)LockMigrateInfo + 8 * v601 + 6) & 1) == 0 )
              v604 = L" IX";
            DumpLogRecord::Append(v603, v5, v604, &a5, 0, &v843, 0xFFu);
            if ( a5 < 0x12 )
              break;
            ++v601;
          }
          while ( v601 < v593 );
          v6 = v877;
        }
      }
      if ( *((_BYTE *)v6 + 22) == 0xD3 && *((_BYTE *)v6 + 23) == 7 )
      {
        if ( *(_DWORD *)VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 24), 0, &v904) == 1 )
        {
          v606 = (const wchar_t *)VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 24), 1u, &v904);
          v607 = v904 >> 1;
          if ( v904 >> 1 > 0xFF )
            v607 = 255;
          DumpLogRecord::AppendWChars((DumpLogRecord *)&a5, v5, v606, v607, &a5, 1, &v843);
        }
        else
        {
          DumpLogRecord::Append(v605, v5, L"UNKNOWN DIAG FORMAT ", &a5, 1, &v843, 0xFFu);
        }
      }
      if ( *((_BYTE *)v6 + 22) == 0xD6 )
      {
        VarLogData::Iterator::Iterator((VarLogData::Iterator *)v893);
        DumpLogRecord::Append(v608, v5, L"Extents:", &a5, 1, &v843, 0xFFu);
        BulkAllocLog::InitIter(v6, (struct VarLogData::Iterator *)v893);
        NextExtentId = BulkAllocLog::GetNextExtentId(v6, (struct VarLogData::Iterator *)v893);
        for ( j = 0; NextExtentId; NextExtentId = BulkAllocLog::GetNextExtentId(v6, (struct VarLogData::Iterator *)v893) )
        {
          UtilDbccFormatPageId(v1031, NextExtentId, &v940);
          DumpLogRecord::Append(v611, v5, L" ", &a5, 0, &v843, 0xFFu);
          DumpLogRecord::Append(v612, v5, v1031, &a5, 0, &v843, 0xFFu);
        }
      }
      else
      {
        j = 0;
      }
      v613 = *((_BYTE *)v6 + 22);
      v614 = L"UNKNOWN";
      if ( v613 == -116 )
      {
        v615 = *((_DWORD *)v6 + 8);
        if ( v615 )
        {
          v616 = v615 - 1;
          if ( v616 )
          {
            v617 = v616 - 1;
            if ( v617 )
            {
              if ( v617 == 1 )
              {
                v618 = L"SLOB_PAGE_COUNT";
                v621 = GetDefaultLocale();
                v622 = StringCchPrintf_lW(
                         v1053,
                         0xC8u,
                         L"Reserved page delta: %I64d, Used page delta: %I64d",
                         v621,
                         *((_QWORD *)v6 + 6),
                         *((_QWORD *)v6 + 5));
                if ( v622 < 0 )
                {
                  _mm_lfence();
                  StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9059, v622);
                }
              }
              else
              {
                v618 = L"UNKNOWN";
                v619 = GetDefaultLocale();
                v620 = StringCchPrintf_lW(v1053, 0xC8u, &word_10280BED8, v619);
                if ( v620 < 0 )
                {
                  _mm_lfence();
                  StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9070, v620);
                }
              }
            }
            else
            {
              v618 = L"ROWSET_ROW_COUNT";
              v623 = GetDefaultLocale();
              v624 = StringCchPrintf_lW(v1053, 0xC8u, L"Row count delta: %I64d.", v623, *((_QWORD *)v6 + 5));
              if ( v624 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9044, v624);
              }
            }
          }
          else
          {
            v618 = L"ROWSET_LOB_COUNT";
            v625 = GetDefaultLocale();
            v626 = StringCchPrintf_lW(
                     v1053,
                     0xC8u,
                     L"Reserved page delta: %I64d, Used page delta: %I64d",
                     v625,
                     *((_QWORD *)v6 + 6),
                     *((_QWORD *)v6 + 5));
            if ( v626 < 0 )
            {
              _mm_lfence();
              StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9031, v626);
            }
          }
        }
        else
        {
          v618 = L"HOBT_PAGE_COUNT";
          v627 = GetDefaultLocale();
          v628 = StringCchPrintf_lW(
                   v1053,
                   0xC8u,
                   L"Leaf page delta: %I64d, Reserved page delta: %I64d, Used page delta: %I64d",
                   v627,
                   *((_QWORD *)v6 + 5),
                   *((_QWORD *)v6 + 7),
                   *((_QWORD *)v6 + 6));
          if ( v628 < 0 )
          {
            _mm_lfence();
            StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9017, v628);
          }
        }
        v629 = GetDefaultLocale();
        LODWORD(v826) = *((_DWORD *)v6 + 8);
        v630 = StringCchPrintf_lW(
                 v1059,
                 0xC8u,
                 L"Action %ld (%s) on rowset %I64d. ",
                 v629,
                 v826,
                 v618,
                 *((_QWORD *)v6 + 3));
        if ( v630 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9083, v630);
        }
        DumpLogRecord::Append(v631, v5, v1059, &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v632, v5, v1053, &a5, 0, &v843, 0xFFu);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == 18 )
      {
        v633 = *((_DWORD *)v6 + 12);
        if ( v633 )
        {
          v634 = v633 - 1;
          if ( v634 )
          {
            v635 = v634 - 1;
            if ( v635 )
            {
              v636 = v635 - 1;
              if ( v636 )
              {
                if ( v636 == 1 )
                {
                  v614 = L"SLOBCOUNT";
                  v639 = GetDefaultLocale();
                  v640 = StringCchPrintf_lW(
                           v1048,
                           0xC8u,
                           L"Reserved page count: %I64d, Used page count: %I64d",
                           v639,
                           *((_QWORD *)v6 + 12),
                           *((_QWORD *)v6 + 10));
                  if ( v640 < 0 )
                  {
                    _mm_lfence();
                    StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9152, v640);
                  }
                }
                else
                {
                  v637 = GetDefaultLocale();
                  v638 = StringCchPrintf_lW(v1048, 0xC8u, &word_10280BED8, v637);
                  if ( v638 < 0 )
                  {
                    _mm_lfence();
                    StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9177, v638);
                  }
                }
              }
              else
              {
                v614 = L"ROWSETLOBCOUNT";
                v641 = GetDefaultLocale();
                v642 = StringCchPrintf_lW(
                         v1048,
                         0xC8u,
                         L"Reserved page count: %I64d, Used page count: %I64d",
                         v641,
                         *((_QWORD *)v6 + 12),
                         *((_QWORD *)v6 + 10));
                if ( v642 < 0 )
                {
                  _mm_lfence();
                  StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9124, v642);
                }
              }
            }
            else
            {
              v614 = L"ROWSETCOLUMNCOUNT";
              v643 = GetDefaultLocale();
              LODWORD(v826) = *((_DWORD *)v6 + 20);
              v644 = StringCchPrintf_lW(
                       v1048,
                       0xC8u,
                       L"Column Id: %d, mod count: %I64d",
                       v643,
                       v826,
                       *((_QWORD *)v6 + 11));
              if ( v644 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9166, v644);
              }
            }
          }
          else
          {
            v614 = L"ROWSETCOUNT";
            v645 = GetDefaultLocale();
            v646 = StringCchPrintf_lW(v1048, 0xC8u, L"Row count: %I64d.", v645, *((_QWORD *)v6 + 10));
            if ( v646 < 0 )
            {
              _mm_lfence();
              StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9137, v646);
            }
          }
        }
        else
        {
          v614 = L"HOBTCOUNT";
          v647 = GetDefaultLocale();
          v648 = StringCchPrintf_lW(
                   v1048,
                   0xC8u,
                   L"Leaf page count: %I64d, Reserved page count: %I64d, Used page count: %I64d",
                   v647,
                   *((_QWORD *)v6 + 10),
                   *((_QWORD *)v6 + 14),
                   *((_QWORD *)v6 + 12));
          if ( v648 < 0 )
          {
            _mm_lfence();
            StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9110, v648);
          }
        }
        v649 = GetDefaultLocale();
        LODWORD(v826) = *((_DWORD *)v6 + 12);
        v650 = StringCchPrintf_lW(
                 v1061,
                 0xC8u,
                 L"Action %ld (%s) on rowset %I64d. ",
                 v649,
                 v826,
                 v614,
                 *((_QWORD *)v6 + 7));
        if ( v650 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9190, v650);
        }
        DumpLogRecord::Append(v651, v5, v1061, &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v652, v5, v1048, &a5, 0, &v843, 0xFFu);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == -35 )
      {
        InvalidateCacheLog::DescribeKeys(v6, v1063, 0x190u);
        CacheTypeName = InvalidateCacheLog::GetCacheTypeName(v6);
        v654 = GetDefaultLocale();
        v655 = StringCchPrintf_lW(
                 v1066,
                 0x258u,
                 L"cache invalidation (cache: %s, keys: %s). ",
                 v654,
                 CacheTypeName,
                 v1063);
        if ( v655 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9212, v655);
        }
        DumpLogRecord::Append(v656, v5, v1066, &a5, 1, &v843, 0xFFu);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == -33 )
      {
        v657 = *((_DWORD *)v6 + 10);
        v658 = GetDefaultLocale();
        LODWORD(v837) = v657;
        LODWORD(DestinationSize) = *((_DWORD *)v6 + 6);
        v659 = StringCchPrintf_lW(
                 v1055,
                 0x400u,
                 L"RowsetId:%I64d Type:%d RgId/Primary:%d",
                 v658,
                 *((_QWORD *)v6 + 4),
                 DestinationSize,
                 v837);
        if ( v659 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9232, v659);
        }
        DumpLogRecord::Append(v660, v5, v1055, &a5, 0, &v843, 0xFFu);
        HoBtRowGroupAttribute::HoBtRowGroupAttribute((HoBtRowGroupAttribute *)&v992);
        ColumnStoreColumnSegmentAttribute::ColumnStoreColumnSegmentAttribute((ColumnStoreColumnSegmentAttribute *)v970);
        ColumnStoreDictionaryAttribute::ColumnStoreDictionaryAttribute((ColumnStoreDictionaryAttribute *)v928);
        if ( *(_WORD *)v927 )
        {
          v661 = ((__int64 (*)(void))g_dbtableFactory[4])();
          switch ( *((_DWORD *)v6 + 6) )
          {
            case 0x11:
            case 0x13:
              goto LABEL_1768;
            case 0x12:
              CSIRowgroupLogRecord::GetCSIAttribute<HoBtRowGroupAttribute>(v6, v661, 1, &v992);
              v662 = GetDefaultLocale();
              LODWORD(v826) = v993;
              v663 = StringCchPrintf_lW(v1055, 0x400u, L" State:%d DeltastoreId:%I64d <- ", v662, v826, v992);
              if ( v663 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9258, v663);
              }
              DumpLogRecord::Append(v664, v5, v1055, &a5, 0, &v843, 0xFFu);
LABEL_1768:
              CSIRowgroupLogRecord::GetCSIAttribute<HoBtRowGroupAttribute>(v6, v661, 0, &v992);
              v665 = GetDefaultLocale();
              LODWORD(v826) = v993;
              v666 = StringCchPrintf_lW(v1055, 0x400u, L" State:%d DeltastoreId:%I64d", v665, v826, v992);
              if ( v666 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9272, v666);
              }
              goto LABEL_1793;
            case 0x21:
            case 0x23:
              goto LABEL_1777;
            case 0x22:
              CSIRowgroupLogRecord::GetCSIAttribute<ColumnStoreColumnSegmentAttribute>(v6, v661, 1, v970);
              if ( v974 )
              {
                v976 = v973;
                UtilDbccConvertGUIDToString(&v976, v1042, 0x25u);
                v674 = GetDefaultLocale();
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v672 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d BlockBlobId:%s",
                         v674,
                         v826,
                         DestinationSize,
                         v1042);
              }
              else
              {
                v668 = *(_DWORD *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v986) + 8);
                v669 = *(unsigned __int16 *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v987) + 12);
                v670 = *(__int16 *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v988) + 14);
                v671 = GetDefaultLocale();
                LODWORD(v841) = v670;
                v840[0] = v668;
                LODWORD(v839) = v669;
                LODWORD(DestinationSize) = v972;
                LODWORD(v826) = v971;
                v672 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d SecDictId:%d LOB:%hu:%d:%hu <-",
                         v671,
                         v826,
                         DestinationSize,
                         v839,
                         *(_QWORD *)v840,
                         v841);
                j = 0;
              }
              if ( v672 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9307, v672);
              }
              DumpLogRecord::Append(v673, v5, v1055, &a5, 0, &v843, 0xFFu);
LABEL_1777:
              CSIRowgroupLogRecord::GetCSIAttribute<ColumnStoreColumnSegmentAttribute>(v6, v661, 0, v970);
              if ( v974 )
              {
                v977 = v973;
                UtilDbccConvertGUIDToString(&v977, v1043, 0x25u);
                v681 = GetDefaultLocale();
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v680 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d BlockBlobId:%s",
                         v681,
                         v826,
                         DestinationSize,
                         v1043);
              }
              else
              {
                v675 = *(_DWORD *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v989) + 8);
                v676 = *(unsigned __int16 *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v990) + 12);
                v677 = *(__int16 *)(ColumnStoreColumnSegmentAttribute::GetonDiskLOB(v970, v991) + 14);
                v678 = ColumnStoreColumnSegmentAttribute::GetprimaryDictId((ColumnStoreColumnSegmentAttribute *)v970);
                v679 = GetDefaultLocale();
                LODWORD(v842) = v677;
                LODWORD(v841) = v675;
                v840[0] = v676;
                LODWORD(v839) = v678;
                LODWORD(DestinationSize) = v972;
                LODWORD(v826) = v971;
                v680 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d SecDictId:%d PrimaryDictId:%d LOB:%hu:%d:%hu",
                         v679,
                         v826,
                         DestinationSize,
                         v839,
                         *(_QWORD *)v840,
                         v841,
                         v842);
                j = 0;
              }
              if ( v680 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9344, v680);
              }
              goto LABEL_1793;
            case 0x31:
            case 0x33:
              goto LABEL_1788;
            case 0x32:
              CSIRowgroupLogRecord::GetCSIAttribute<ColumnStoreDictionaryAttribute>(v6, v661, 1, v928);
              if ( v932 )
              {
                v978 = v931;
                UtilDbccConvertGUIDToString(&v978, v1044, 0x25u);
                v688 = GetDefaultLocale();
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v686 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d BlockBlobId:%s",
                         v688,
                         v826,
                         DestinationSize,
                         v1044);
              }
              else
              {
                v682 = *(_DWORD *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v980) + 8);
                v683 = *(unsigned __int16 *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v981) + 12);
                v684 = *(__int16 *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v982) + 14);
                v685 = GetDefaultLocale();
                LODWORD(v841) = v684;
                v840[0] = v682;
                LODWORD(v839) = v683;
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v686 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d LOB:%hu:%d:%hu <-",
                         v685,
                         v826,
                         DestinationSize,
                         v839,
                         *(_QWORD *)v840,
                         v841);
                j = 0;
              }
              if ( v686 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9379, v686);
              }
              DumpLogRecord::Append(v687, v5, v1055, &a5, 0, &v843, 0xFFu);
LABEL_1788:
              CSIRowgroupLogRecord::GetCSIAttribute<ColumnStoreDictionaryAttribute>(v6, v661, 0, v928);
              if ( v932 )
              {
                v979 = v931;
                UtilDbccConvertGUIDToString(&v979, v1045, 0x25u);
                v694 = GetDefaultLocale();
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v693 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d BlockBlobId:%s",
                         v694,
                         v826,
                         DestinationSize,
                         v1045);
              }
              else
              {
                v689 = *(_DWORD *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v983) + 8);
                v690 = *(unsigned __int16 *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v984) + 12);
                v691 = *(__int16 *)(ColumnStoreDictionaryAttribute::GetonDiskLOB(v928, v985) + 14);
                v692 = GetDefaultLocale();
                LODWORD(v841) = v691;
                v840[0] = v689;
                LODWORD(v839) = v690;
                LODWORD(DestinationSize) = v930;
                LODWORD(v826) = v929;
                v693 = StringCchPrintf_lW(
                         v1055,
                         0x400u,
                         L" ColumnId:%d DictId:%d LOB:%hu:%d:%hu",
                         v692,
                         v826,
                         DestinationSize,
                         v839,
                         *(_QWORD *)v840,
                         v841);
                j = 0;
              }
              if ( v693 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9415, v693);
              }
LABEL_1793:
              DumpLogRecord::Append(v667, v5, v1055, &a5, 0, &v843, 0xFFu);
              break;
            default:
              break;
          }
        }
        HoBtRowGroupAttribute::~HoBtRowGroupAttribute((HoBtRowGroupAttribute *)&v992);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == -32 )
      {
        v695 = GetDefaultLocale();
        v696 = StringCchPrintf_lW(v1064, 0x190u, L"UNDONE put some delete buffer log record description here", v695);
        if ( v696 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9438, v696);
        }
        DumpLogRecord::Append(v697, v5, v1064, &a5, 1, &v843, 0xFFu);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == -31 )
      {
        RowsetId = CsiDeleteBitmapInvalidationLog::GetRowsetId(v6);
        v699 = GetDefaultLocale();
        v700 = StringCchPrintf_lW(v1067, 0x258u, L"delete bitmap cache invalidation (RowsetId: %I64d).", v699, RowsetId);
        if ( v700 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9456, v700);
        }
        DumpLogRecord::Append(v701, v5, v1067, &a5, 1, &v843, 0xFFu);
        v613 = *((_BYTE *)v6 + 22);
      }
      if ( v613 == -25 )
      {
        v702 = *((_WORD *)v6 + 12);
        v703 = v702;
        if ( v702 != 3 && v702 != 4 )
        {
          utassert_fail(
            1u,
            "hkCheckpointLog->log_hkVersion == HK_ONDISK_SQL14_CTP2_VER || hkCheckpointLog->log_hkVersion == HK_ONDISK_SQL14_RTM_VER",
            "dumplog.cpp",
            9467,
            0);
          v703 = *((_WORD *)v6 + 12);
        }
        v704 = StringCchPrintfW(v1051, 0x80u, L"XTP complete checkpoint ver %d:  { LSN = ", v703);
        if ( v704 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9484, v704);
        }
        DumpLogRecord::Append(v705, v5, v1051, &a5, 1, &v843, 0xFFu);
        LSN::FormatAsHexString((LSN *)((char *)v6 + 44), v1021, &v894);
        DumpLogRecord::Append(v706, v5, v1021, &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v707, v5, L", previous checkpoint completion LSN = ", &a5, 1, &v843, 0xFFu);
        LSN::FormatAsHexString((LSN *)v6 + 7, v1021, &v894);
        DumpLogRecord::Append(v708, v5, v1021, &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v709, v5, L", close LSN = ", &a5, 1, &v843, 0xFFu);
        LSN::FormatAsHexString((LSN *)((char *)v6 + 68), v1021, &v894);
        DumpLogRecord::Append(v710, v5, v1021, &a5, 1, &v843, 0xFFu);
        v711 = StringCchPrintfW(
                 v1051,
                 0x80u,
                 L", CkptTs = 0x%08I64lx, SerializeTs = 0x%08I64lx }",
                 *(_QWORD *)((char *)v6 + 28),
                 *(_QWORD *)((char *)v6 + 36));
        if ( v711 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9511, v711);
        }
        DumpLogRecord::Append(v712, v5, v1051, &a5, 1, &v843, 0xFFu);
        UtilDbccConvertGUIDToString((const struct _GUID *)((char *)v6 + 116), v1046, 0x25u);
        UtilDbccConvertGUIDToString((const struct _GUID *)((char *)v6 + 132), v1047, 0x25u);
        LSN::FormatAsHexString((LSN *)v6 + 10, v1021, &v894);
        v713 = StringCchPrintfW(
                 v1062,
                 0x16Cu,
                 L", { CkptDir ==> GUIDs = { Rowset %s, Column %s }, MRT = %s }",
                 v1046,
                 v1047,
                 v1021);
        if ( v713 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9536, v713);
        }
        DumpLogRecord::Append(v714, v5, v1062, &a5, 1, &v843, 0xFFu);
      }
      if ( *((_BYTE *)v6 + 22) == 0xE8 )
      {
        if ( *((_WORD *)v6 + 12) != 3 )
          utassert_fail(1u, "chainedLog->log_hkVersion == HK_ONDISK_SQL14_CTP2_VER", "dumplog.cpp", 9545, 0);
        VarLogData::GetData((DatabaseMetaLog *)((char *)v6 + 30), 0, &v941);
        LSN::FormatAsHexString((LSN *)((char *)v6 + 4), v1037, &v942);
        LODWORD(v826) = *((__int16 *)v6 + 14);
        v715 = StringCchPrintfW(
                 v1056,
                 0x80u,
                 L"XTP chained record ver %d:  log_Discriminator = 0x%08x, log_prevRec = %s ",
                 *((unsigned __int16 *)v6 + 12),
                 v826,
                 v1037);
        if ( v715 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9563, v715);
        }
        DumpLogRecord::Append(v716, v5, v1056, &a5, 1, &v843, 0xFFu);
      }
      v717 = *((_BYTE *)v6 + 22);
      if ( v717 == 0xA2 )
      {
        v718 = *((unsigned __int16 *)v6 + 24);
        v719 = GetDefaultLocale();
        LODWORD(v826) = v718;
        v720 = StringCchPrintf_lW(v1065, 0x190u, L"payload length=%u. ", v719, v826);
        if ( v720 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9593, v720);
        }
        DumpLogRecord::Append(v721, v5, v1065, &a5, 1, &v843, 0xFFu);
        v717 = *((_BYTE *)v6 + 22);
      }
      if ( v717 == 0xD9 )
      {
        v722 = (const wchar_t *)DatabaseMetaLog::GetData(v6, 1u, &v943);
        DumpLogRecord::Append((DumpLogRecord *)&v843, v5, v722, &a5, 1, &v843, 0xFFu);
        v717 = *((_BYTE *)v6 + 22);
      }
      if ( v717 == 0xF1 )
      {
        v723 = *((_QWORD *)v6 + 5);
        DumpLogRecord::Append((DumpLogRecord *)v7, v5, L"AuditTxLog for transaction: ", &a5, 1, &v843, 0xFFu);
        v724 = GetDefaultLocale();
        v725 = StringCchPrintf_lW(v1035, 0xEu, L"%I64d", v724, v723);
        if ( v725 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9628, v725);
        }
        DumpLogRecord::Append(v726, v5, v1035, &a5, 0, &v843, 0xFFu);
        v717 = *((_BYTE *)v6 + 22);
      }
      if ( v717 == 0xF4 )
      {
        v727 = GetDefaultLocale();
        LODWORD(v826) = *((_DWORD *)v6 + 6);
        v728 = StringCchPrintf_lW(v1052, 0x80u, L"Start nest Id (%d) ", v727, v826);
        if ( v728 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9652, v728);
        }
        DumpLogRecord::Append(v729, v5, v1052, &a5, 1, &v843, 0xFFu);
        v730 = GetDefaultLocale();
        LODWORD(v829) = *((_DWORD *)v6 + 7);
        v731 = StringCchPrintf_lW(v1052, 0x80u, L"End nest Id (%d) ", v730, v829);
        if ( v731 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9663, v731);
        }
        DumpLogRecord::Append(v732, v5, v1052, &a5, 1, &v843, 0xFFu);
        LSN::FormatAsHexString((LSN *)v6 + 4, v1038, &v944);
        DumpLogRecord::Append(v733, v5, L"PrevLsnOfNest ", &a5, 1, &v843, 0xFFu);
        DumpLogRecord::Append(v734, v5, v1038, &a5, 0, &v843, 0xFFu);
        v717 = *((_BYTE *)v6 + 22);
      }
      if ( v717 >= 0x7Fu )
        return;
      if ( v717 == 20 )
      {
        v735 = *((unsigned int *)v6 + 12);
        if ( (_DWORD)v735 )
        {
          v735 = (unsigned int)(v735 - 1);
          if ( (_DWORD)v735 )
          {
            v735 = (unsigned int)(v735 - 1);
            if ( (_DWORD)v735 )
            {
              if ( (_DWORD)v735 != 1 )
              {
                utassert_fail(1u, "FALSE", "dumplog.cpp", 9719, "Invalid switch value");
                goto LABEL_1848;
              }
              v736 = L"Copy_CompressionInfo ";
            }
            else
            {
              v736 = L"Uncompress_Page ";
            }
          }
          else
          {
            v736 = L"Compress_Page ";
          }
        }
        else
        {
          v736 = L"Reset_PageModCnt ";
        }
        DumpLogRecord::Append((DumpLogRecord *)v735, v5, v736, &a5, 1, &v843, 0xFFu);
      }
LABEL_1848:
      v737 = *((_BYTE *)v6 + 22);
      if ( v737 == 11 || v737 == 12 )
      {
        DumpLogRecord::Append((DumpLogRecord *)v7, v5, L"Moved ", &a5, 1, &v843, 0xFFu);
        v738 = *((unsigned __int16 *)v6 + 27);
        v739 = GetDefaultLocale();
        LODWORD(v830) = v738;
        v740 = StringCchPrintf_lW(v1018, 0xEu, L"%d", v739, v830);
        if ( v740 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9750, v740);
        }
        DumpLogRecord::Append(v741, v5, v1018, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v742, v5, L" row(s) at slot ", &a5, 0, &v843, 0xFFu);
        v743 = *((__int16 *)v6 + 15);
        v744 = GetDefaultLocale();
        LODWORD(v831) = v743;
        v745 = StringCchPrintf_lW(v1018, 0xEu, L"%d", v744, v831);
        if ( v745 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9771, v745);
        }
        DumpLogRecord::Append(v746, v5, v1018, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v747, v5, L" from page ", &a5, 0, &v843, 0xFFu);
        PageId = (const struct PageId *)PageLog::GetPageId(v6, v962);
        UtilDbccFormatPageId(v1018, PageId, &v907);
        DumpLogRecord::Append(v749, v5, v1018, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v750, v5, L" to page ", &a5, 0, &v843, 0xFFu);
        UtilDbccFormatPageId(v1018, (DatabaseMetaLog *)((char *)v6 + 48), &v907);
        DumpLogRecord::Append(v751, v5, v1018, &a5, 0, &v843, 0xFFu);
        v737 = *((_BYTE *)v6 + 22);
      }
      if ( v737 == 19 )
      {
        DumpLogRecord::Append((DumpLogRecord *)v7, v5, L"Changed type ", &a5, 1, &v843, 0xFFu);
        v753 = *((int *)v6 + 12);
        if ( (unsigned int)v753 > 8 )
          v754 = L"Unknown type";
        else
          v754 = (const wchar_t *)(&TreeTypeNames)[v753];
        DumpLogRecord::Append(v752, v5, v754, &a5, 0, &v843, 0xFFu);
        v755 = GetDefaultLocale();
        LODWORD(v832) = *((_DWORD *)v6 + 12);
        v756 = StringCchPrintf_lW(v1040, 0x64u, L" (%d) for AU ", v755, v832);
        if ( v756 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9851, v756);
        }
        DumpLogRecord::Append(v757, v5, v1040, &a5, 0, &v843, 0xFFu);
        v918 = *((_DWORD *)v6 + 16);
        v919 = *((_WORD *)v6 + 34);
        v920 = 0;
        I8 = UnalignedAllocUnitId::GetI8((UnalignedAllocUnitId *)&v918);
        v759 = GetDefaultLocale();
        v760 = StringCchPrintf_lW(v1040, 0x64u, L"%I64d", v759, I8);
        if ( v760 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9866, v760);
        }
        DumpLogRecord::Append(v761, v5, v1040, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v762, v5, L" in rowset ", &a5, 0, &v843, 0xFFu);
        v763 = *((_QWORD *)v6 + 7);
        v764 = GetDefaultLocale();
        v765 = StringCchPrintf_lW(v1040, 0x64u, L"%I64d", v764, v763);
        if ( v765 < 0 )
        {
          _mm_lfence();
          StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9889, v765);
        }
        DumpLogRecord::Append(v766, v5, v1040, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v767, v5, L" from page ", &a5, 0, &v843, 0xFFu);
        v768 = *((_WORD *)v6 + 42);
        v898 = *((_DWORD *)v6 + 20);
        v899 = v768;
        UtilDbccFormatPageId(v1022, (const struct PageId *)&v898, &v908);
        DumpLogRecord::Append(v769, v5, v1022, &a5, 0, &v843, 0xFFu);
        DumpLogRecord::Append(v770, v5, L" to page ", &a5, 0, &v843, 0xFFu);
        v771 = *((_WORD *)v6 + 38);
        v898 = *((_DWORD *)v6 + 18);
        v899 = v771;
        UtilDbccFormatPageId(v1022, (const struct PageId *)&v898, &v908);
        DumpLogRecord::Append(v772, v5, v1022, &a5, 0, &v843, 0xFFu);
        v737 = *((_BYTE *)v6 + 22);
      }
      if ( v737 == 2 )
      {
        v773 = RowLog::DataRowCount(v6);
        v737 = 2;
        if ( v773 > 1 )
        {
          _mm_lfence();
          DumpLogRecord::Append((DumpLogRecord *)v7, v5, L"Inserted ", &a5, 1, &v843, 0xFFu);
          v774 = GetDefaultLocale();
          LODWORD(v833) = v773;
          v775 = StringCchPrintf_lW(v1032, 0xEu, L"%d", v774, v833);
          if ( v775 < 0 )
          {
            _mm_lfence();
            StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 9957, v775);
          }
          DumpLogRecord::Append(v776, v5, v1032, &a5, 0, &v843, 0xFFu);
          DumpLogRecord::Append(v777, v5, L" rows on page.", &a5, 0, &v843, 0xFFu);
          v737 = *((_BYTE *)v6 + 22);
        }
      }
      if ( v737 == 124 )
      {
        DumpLogRecord::Append((DumpLogRecord *)v7, v5, L"Server Config Settings Reconfigured", &a5, 1, &v843, 0xFFu);
        v737 = *((_BYTE *)v6 + 22);
      }
      if ( v737 == 22 )
      {
        v778 = L"InSysXact bit on";
        if ( !*((_BYTE *)v6 + 48) )
          v778 = L"InSysXact bit off";
        DumpLogRecord::Append((DumpLogRecord *)v7, v5, v778, &a5, 1, &v843, 0xFFu);
      }
      if ( (unsigned int)PageLog::IsPossibleAllocationOp(v6)
        || ((v779 = *((_BYTE *)v6 + 23), v779 == 9) || (unsigned __int8)(v779 - 24) <= 1u)
        && *((_BYTE *)v6 + 22) == 7
        && *((_WORD *)v6 + 15) == 1 )
      {
        if ( *((_BYTE *)v6 + 23) == 8 )
        {
          v817 = PageLog::GetPageId(v6, v968);
          v819 = GAMBasePage::ConvertBitToExtentId(v969, v817, v818, 8);
          v884 = *(_DWORD *)v819;
          v885 = *(_WORD *)(v819 + 4);
          UtilDbccFormatPageId(v1020, (const struct PageId *)&v884, &v905);
          v820 = *((unsigned __int16 *)v6 + 25);
          v821 = GetDefaultLocale();
          LODWORD(v826) = v820;
          v822 = StringCchPrintf_lW(v1036, 0x14u, L"%d", v821, v826);
          if ( v822 < 0 )
          {
            _mm_lfence();
            StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 10096, v822);
          }
          v824 = L"Allocated ";
          if ( *((_BYTE *)v6 + 52) )
            v824 = L"Deallocated ";
          DumpLogRecord::Append(v823, v5, v824, &a5, 1, &v843, 0xFFu);
          DumpLogRecord::Append(v825, v5, v1036, &a5, 0, &v843, 0xFFu);
          v834 = 0;
          v816 = L" extent(s) starting at page ";
          v815 = v5;
          goto LABEL_1919;
        }
        if ( *((_BYTE *)v6 + 23) == 9 )
        {
LABEL_1912:
          v811 = PageLog::GetPageId(v6, v966);
          v813 = GAMBasePage::ConvertBitToExtentId(v967, v811, v812, 8);
          v884 = *(_DWORD *)v813;
          v885 = *(_WORD *)(v813 + 4);
          UtilDbccFormatPageId(v1020, (const struct PageId *)&v884, &v905);
          v815 = v5;
          v834 = 1;
          v816 = L"ClearBit ";
          if ( *((_BYTE *)v6 + 52) )
            v816 = L"SetBit ";
LABEL_1919:
          DumpLogRecord::Append(v814, v815, v816, &a5, v834, &v843, 0xFFu);
          v794 = v1020;
LABEL_1920:
          DumpLogRecord::Append(v793, v5, v794, &a5, 0, &v843, 0xFFu);
          return;
        }
        if ( *((_BYTE *)v6 + 23) != 11 )
        {
          if ( (unsigned int)*((unsigned __int8 *)v6 + 23) - 24 >= 2 )
          {
            utassert_fail(1u, "FALSE", "dumplog.cpp", 10174, "Invalid switch value");
            return;
          }
          goto LABEL_1912;
        }
        v795 = RowLog::GetData(v6, 0, &v895);
        v796 = (struct LSN *)RowLog::GetData(v6, 1u, &v895);
        v896 = v796;
        v797 = v895;
        if ( !v895 )
          return;
        while ( 1 )
        {
          v798 = PageLog::GetPageId(v6, v964);
          PageIdForStatus = PFSPage::GetPageIdForStatus(v965, v798);
          v884 = *(_DWORD *)PageIdForStatus;
          v885 = *(_WORD *)(PageIdForStatus + 4);
          UtilDbccFormatPageId(v1020, (const struct PageId *)&v884, &v905);
          v800 = (char *)v796 + j;
          v801 = &v795[j];
          v802 = (unsigned __int8)*v800;
          v803 = *v801;
          v804 = GetDefaultLocale();
          LODWORD(DestinationSize) = v802;
          LODWORD(v826) = v803;
          v805 = StringCchPrintf_lW(v1054, 0x64u, L"0x%02x-->%02x ", v804, v826, DestinationSize);
          if ( v805 < 0 )
          {
            _mm_lfence();
            StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 10040, v805);
            v797 = v895;
          }
          v807 = v906;
          DumpLogRecord::Append(v806, v906, v1054, &a5, 1, &v843, 0xFFu);
          v809 = *v800 & 0x40;
          if ( v809 )
          {
            if ( (*v801 & 0x40) == 0 )
            {
              v810 = L"Allocated ";
LABEL_1909:
              DumpLogRecord::Append(v808, v807, v810, &a5, 1, &v843, 0xFFu);
              goto LABEL_1910;
            }
          }
          else if ( (*v801 & 0x40) == 0 )
          {
            goto LABEL_1910;
          }
          if ( !v809 )
          {
            v810 = L"Deallocated ";
            goto LABEL_1909;
          }
LABEL_1910:
          DumpLogRecord::Append(v808, v807, v1020, &a5, 0, &v843, 0xFFu);
          ++j;
          v796 = v896;
          v6 = v877;
          if ( j >= v797 )
            return;
        }
      }
      if ( v779 == 11 && *((_BYTE *)v6 + 22) == 7 )
      {
        v923 = (*((unsigned __int16 *)v6 + 24) >> 3) - 4;
        v780 = PageLog::GetPageId(v6, v963);
        v781 = (DumpLogRecord *)*(unsigned __int16 *)(v780 + 4);
        v924 = *(_WORD *)(v780 + 4);
        v782 = *((unsigned __int16 *)v6 + 25);
        for ( k = 0; k < v782; ++k )
        {
          v784 = k + (*((_WORD *)v6 + 24) & 7);
          if ( v784 == 3 )
          {
            v790 = *((unsigned __int8 *)v6 + 52);
            v791 = GetDefaultLocale();
            LODWORD(v826) = v790;
            v792 = StringCchPrintf_lW(v1041, 0x64u, L"GhostBit: %d. ", v791, v826);
            if ( v792 < 0 )
            {
              _mm_lfence();
              StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 10228, v792);
            }
          }
          else
          {
            v785 = *((unsigned __int8 *)v6 + 52);
            v786 = GetDefaultLocale();
            if ( v784 == 7 )
            {
              LODWORD(v826) = v785;
              v789 = StringCchPrintf_lW(v1041, 0x64u, L"VersionBit: %d. ", v786, v826);
              if ( v789 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 10210, v789);
              }
            }
            else
            {
              LODWORD(DestinationSize) = v785;
              LODWORD(v826) = v784;
              v787 = StringCchPrintf_lW(
                       v1041,
                       0x64u,
                       L"Bit location: %d. Bit value: %02x. ",
                       v786,
                       v826,
                       DestinationSize);
              if ( v787 < 0 )
              {
                _mm_lfence();
                StringFailureError("sql\\ntdbms\\storeng\\dmu\\dbcc\\source\\dumplog.cpp", 10248, v787);
              }
            }
          }
          DumpLogRecord::Append(v788, v5, v1041, &a5, 1, &v843, 0xFFu);
        }
        DumpLogRecord::Append(v781, v5, L"PageId: ", &a5, 0, &v843, 0xFFu);
        UtilDbccFormatPageId(v1033, (const struct PageId *)&v923, &v945);
        v794 = v1033;
        goto LABEL_1920;
      }
      return;
    case 0x17:
    case 0x1E:
    case 0x26:
    case 0x27:
    case 0x28:
      goto LABEL_1646;
    default:
      utassert_fail(1u, "FALSE", "dumplog.cpp", 8769, "Invalid switch value");
      goto LABEL_1646;
  }
}

```

## disassembly

```asm
0x101f05660  push    rbp
0x101f05662  push    rbx
0x101f05663  push    rsi
0x101f05664  push    rdi
0x101f05665  push    r12
0x101f05667  push    r13
0x101f05669  push    r14
0x101f0566b  push    r15
0x101f0566d  lea     rbp, [rsp-43A8h]
0x101f05675  mov     eax, 44A8h
0x101f0567a  call    _alloca_probe
0x101f0567f  sub     rsp, rax
0x101f05682  mov     [rbp+43E0h+var_4100], 0FFFFFFFFFFFFFFFEh
0x101f0568d  mov     rax, cs:__security_cookie
0x101f05694  xor     rax, rsp
0x101f05697  mov     [rbp+43E0h+var_50], rax
0x101f0569e  mov     r13, r9
0x101f056a1  mov     [rbp+43E0h+var_4330], r9
0x101f056a8  mov     r15, r8
0x101f056ab  mov     [rbp+43E0h+var_43B0], r8
0x101f056af  mov     [rbp+43E0h+var_4360], rdx
0x101f056b6  mov     [rbp+43E0h+var_42D0], rcx
0x101f056bd  xor     edi, edi
0x101f056bf  mov     [r9], di
0x101f056c3  mov     ebx, 1
0x101f056c8  mov     [rsp+44E0h+var_4480], ebx
0x101f056cc  lea     rdx, [rbp+43E0h+var_42E0]; struct SQLDATE *
0x101f056d3  mov     rcx, r8; struct LogRec *
0x101f056d6  call    ?GetLogRecDateTime@@YAHPEBVLogRec@@AEAUSQLDATE@@@Z; GetLogRecDateTime(LogRec const *,SQLDATE &)
0x101f056db  lea     r12, [rdi-1]
0x101f056df  lea     rsi, aSqlNtdbmsStore_419; "sql\\ntdbms\\storeng\\dmu\\dbcc\\source"...
0x101f056e6  test    eax, eax
0x101f056e8  jz      loc_101F05809
0x101f056ee  mov     [rbp+43E0h+var_41C4], dil
0x101f056f5  lea     rdx, [rbp+43E0h+var_41E8]
0x101f056fc  lea     rcx, [rbp+43E0h+var_42E0]
0x101f05703  call    cs:__imp_?DateToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z; SQLDATE::DateToParts(dateparts *)
0x101f05709  lea     rdx, [rbp+43E0h+var_41E8]
0x101f05710  lea     rcx, [rbp+43E0h+var_42E0]
0x101f05717  call    cs:__imp_?TimeToParts@SQLDATE@@QEBAXPEAUdateparts@@@Z; SQLDATE::TimeToParts(dateparts *)
0x101f0571d  mov     ebx, [rbp+43E0h+var_41E4]
0x101f05723  inc     ebx
0x101f05725  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x101f0572b  mov     r9, rax; struct __crt_locale_pointers *
0x101f0572e  mov     eax, [rbp+43E0h+var_41C8]
0x101f05734  mov     [rsp+44E0h+var_4490], eax
0x101f05738  mov     eax, [rbp+43E0h+var_41CC]
0x101f0573e  mov     dword ptr [rsp+44E0h+var_4498], eax
0x101f05742  mov     eax, [rbp+43E0h+var_41D0]
0x101f05748  mov     dword ptr [rsp+44E0h+var_44A0], eax
0x101f0574c  mov     eax, [rbp+43E0h+var_41D4]
0x101f05752  mov     [rsp+44E0h+var_44A8], eax
0x101f05756  mov     eax, [rbp+43E0h+var_41E0]
0x101f0575c  mov     dword ptr [rsp+44E0h+var_44B0], eax
0x101f05760  mov     dword ptr [rsp+44E0h+DestinationSize], ebx
0x101f05764  mov     eax, [rbp+43E0h+var_41E8]
0x101f0576a  mov     dword ptr [rsp+44E0h+var_44C0], eax
0x101f0576e  lea     r8, a04d02d02d02d02; "%04d/%02d/%02d %02d:%02d:%02d:%03d"
0x101f05775  lea     edx, [rdi+18h]; unsigned __int64
0x101f05778  lea     rcx, [rbp+43E0h+var_3358]; wchar_t *
0x101f0577f  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x101f05784  test    eax, eax
0x101f05786  jns     short loc_101F057B6
0x101f05788  lfence
0x101f0578b  mov     dword ptr [rsp+44E0h+var_44B0], eax
0x101f0578f  mov     dword ptr [rsp+44E0h+DestinationSize], 0C4Fh
0x101f05797  mov     [rsp+44E0h+var_44C0], rsi
0x101f0579c  mov     ebx, 1
0x101f057a1  mov     r9d, ebx
0x101f057a4  lea     edx, [rdi+7]
0x101f057a7  lea     ecx, [rdi+4]
0x101f057aa  lea     r8d, [rdi+10h]
0x101f057ae  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101f057b4  jmp     short loc_101F057BB
0x101f057b6  mov     ebx, 1
0x101f057bb  mov     r14d, [rbp+43E0h+arg_20]
0x101f057c2  test    r14d, r14d
0x101f057c5  jz      short loc_101F05810
0x101f057c7  lea     r8, [rbp+43E0h+var_3358]; wchar_t *
0x101f057ce  mov     edx, 100h; unsigned __int64
0x101f057d3  mov     rcx, r13; wchar_t *
0x101f057d6  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x101f057db  test    eax, eax
0x101f057dd  js      short loc_101F05810
0x101f057df  lea     rcx, [rbp+43E0h+var_3358]
0x101f057e6  mov     rax, r12
0x101f057e9  nop     dword ptr [rax+00000000h]
0x101f057f0  inc     rax
0x101f057f3  cmp     [rcx+rax*2], di
0x101f057f7  jnz     short loc_101F057F0
0x101f057f9  sub     r14d, eax
0x101f057fc  mov     [rbp+43E0h+arg_20], r14d
0x101f05803  mov     [rsp+44E0h+var_4480], edi
0x101f05807  jmp     short loc_101F05810
0x101f05809  mov     r14d, [rbp+43E0h+arg_20]
0x101f05810  lea     rsi, asc_1029E9D68; ";"
0x101f05817  test    byte ptr [r15+0Eh], 4
0x101f0581c  jz      loc_101F058EA
0x101f05822  test    r14d, r14d
0x101f05825  jz      loc_101F058EA
0x101f0582b  cmp     [rsp+44E0h+var_4480], edi
0x101f0582f  jnz     loc_101F058C3
0x101f05835  mov     eax, 100h
0x101f0583a  mov     rcx, r13
0x101f0583d  nop     dword ptr [rax]
0x101f05840  cmp     [rcx], di
0x101f05843  jz      short loc_101F0584F
0x101f05845  add     rcx, 2
0x101f05849  sub     rax, 1
0x101f0584d  jnz     short loc_101F05840
0x101f0584f  test    rax, rax
0x101f05852  jz      loc_101F058EA
0x101f05858  mov     r8, rbx
0x101f0585b  mov     r9, rsi
0x101f0585e  lea     rdx, [rax-100h]
0x101f05865  cmovz   rdx, rdi
0x101f05869  mov     ecx, 100h
0x101f0586e  sub     rcx, rax
0x101f05871  add     rcx, rcx
0x101f05874  test    rax, rax
0x101f05877  cmovz   rcx, rdi
0x101f0587b  add     rcx, r13
0x101f0587e  add     rdx, 100h
0x101f05885  jz      short loc_101F058A9
0x101f05887  test    r8, r8
0x101f0588a  jz      short loc_101F058A9
0x101f0588c  movzx   eax, word ptr [r9]
0x101f05890  test    ax, ax
0x101f05893  jz      short loc_101F058A9
0x101f05895  mov     [rcx], ax
0x101f05898  add     rcx, 2
0x101f0589c  add     r9, 2
0x101f058a0  dec     r8
0x101f058a3  sub     rdx, 1
0x101f058a7  jnz     short loc_101F05887
0x101f058a9  lea     rax, [rcx-2]
0x101f058ad  test    rdx, rdx
0x101f058b0  cmovnz  rax, rcx
0x101f058b4  mov     [rax], di
0x101f058b7  jz      short loc_101F058EA
0x101f058b9  dec     r14d
0x101f058bc  mov     [rbp+43E0h+arg_20], r14d
0x101f058c3  lea     r8, aReplicate; "REPLICATE"
0x101f058ca  mov     edx, 100h; unsigned __int64
0x101f058cf  mov     rcx, r13; wchar_t *
0x101f058d2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x101f058d7  test    eax, eax
0x101f058d9  js      short loc_101F058EA
0x101f058db  add     r14d, 0FFFFFFF7h
0x101f058df  mov     [rbp+43E0h+arg_20], r14d
0x101f058e6  mov     [rsp+44E0h+var_4480], edi
0x101f058ea  test    byte ptr [r15+0Eh], 1
0x101f058ef  jz      loc_101F059BA
0x101f058f5  test    r14d, r14d
0x101f058f8  jz      loc_101F059BA
0x101f058fe  cmp     [rsp+44E0h+var_4480], edi
0x101f05902  jnz     loc_101F05993
0x101f05908  mov     eax, 100h
0x101f0590d  mov     rcx, r13
0x101f05910  cmp     [rcx], di
0x101f05913  jz      short loc_101F0591F
0x101f05915  add     rcx, 2
0x101f05919  sub     rax, 1
0x101f0591d  jnz     short loc_101F05910
0x101f0591f  test    rax, rax
0x101f05922  jz      loc_101F059BA
0x101f05928  mov     r8, rbx
0x101f0592b  mov     r9, rsi
0x101f0592e  lea     rdx, [rax-100h]
0x101f05935  cmovz   rdx, rdi
0x101f05939  mov     ecx, 100h
0x101f0593e  sub     rcx, rax
0x101f05941  add     rcx, rcx
0x101f05944  test    rax, rax
0x101f05947  cmovz   rcx, rdi
0x101f0594b  add     rcx, r13
0x101f0594e  add     rdx, 100h
0x101f05955  jz      short loc_101F05979
0x101f05957  test    r8, r8
0x101f0595a  jz      short loc_101F05979
0x101f0595c  movzx   eax, word ptr [r9]
0x101f05960  test    ax, ax
0x101f05963  jz      short loc_101F05979
0x101f05965  mov     [rcx], ax
0x101f05968  add     rcx, 2
0x101f0596c  add     r9, 2
0x101f05970  dec     r8
0x101f05973  sub     rdx, 1
0x101f05977  jnz     short loc_101F05957
0x101f05979  lea     rax, [rcx-2]
0x101f0597d  test    rdx, rdx
0x101f05980  cmovnz  rax, rcx
0x101f05984  mov     [rax], di
0x101f05987  jz      short loc_101F059BA
0x101f05989  dec     r14d
0x101f0598c  mov     [rbp+43E0h+arg_20], r14d
0x101f05993  lea     r8, aCompensation; "COMPENSATION"
0x101f0599a  mov     edx, 100h; unsigned __int64
0x101f0599f  mov     rcx, r13; wchar_t *
0x101f059a2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x101f059a7  test    eax, eax
0x101f059a9  js      short loc_101F059BA
0x101f059ab  add     r14d, 0FFFFFFF4h
0x101f059af  mov     [rbp+43E0h+arg_20], r14d
0x101f059b6  mov     [rsp+44E0h+var_4480], edi
0x101f059ba  lea     rdx, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101f059c1  cmp     byte ptr [r15+16h], 5
0x101f059c6  jnz     def_101F059F0; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f059cc  movzx   eax, word ptr [r15+38h]
0x101f059d1  dec     eax; switch 58 cases
0x101f059d3  cmp     eax, 39h
0x101f059d6  ja      def_101F059F0; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f059dc  cdqe
0x101f059de  movzx   eax, ds:(byte_101F0F05C - 100400000h)[rdx+rax]
0x101f059e6  mov     ecx, ds:(jpt_101F059F0 - 100400000h)[rdx+rax*4]
0x101f059ed  add     rcx, rdx
0x101f059f0  jmp     rcx; switch jump
0x101f059f2  lea     rdi, aMFlagbits; jumptable 0000000101F059F0 case 4
0x101f059f9  jmp     short loc_101F05A65
0x101f059fb  lea     rdi, aMTypeflagbits; jumptable 0000000101F059F0 case 2
0x101f05a02  jmp     short loc_101F05A65
0x101f05a04  lea     rdi, aMPrevpage; jumptable 0000000101F059F0 case 8
0x101f05a0b  jmp     short loc_101F05A65
0x101f05a0d  lea     rdi, aMFixedlength; jumptable 0000000101F059F0 case 14
0x101f05a14  jmp     short loc_101F05A65
0x101f05a16  lea     rdi, aMNextpage; jumptable 0000000101F059F0 case 16
0x101f05a1d  jmp     short loc_101F05A65
0x101f05a1f  lea     rdi, aMSlotcnt_0; jumptable 0000000101F059F0 case 22
0x101f05a26  jmp     short loc_101F05A65
0x101f05a28  lea     rdi, aMFreecnt_0; jumptable 0000000101F059F0 case 28
0x101f05a2f  jmp     short loc_101F05A65
0x101f05a31  lea     rdi, aMFreedata_0; jumptable 0000000101F059F0 case 30
0x101f05a38  jmp     short loc_101F05A65
0x101f05a3a  lea     rdi, aMPageid; jumptable 0000000101F059F0 case 32
0x101f05a41  jmp     short loc_101F05A65
0x101f05a43  lea     rdi, aMReservedcnt; jumptable 0000000101F059F0 case 38
0x101f05a4a  jmp     short loc_101F05A65
0x101f05a4c  lea     rdi, aMGhostreccnt_0; jumptable 0000000101F059F0 case 58
0x101f05a53  jmp     short loc_101F05A65
0x101f05a55  lea     rdi, aMType; jumptable 0000000101F059F0 case 1
0x101f05a5c  jmp     short loc_101F05A65
0x101f05a5e  lea     rdi, aMLevel; jumptable 0000000101F059F0 case 3
0x101f05a65  mov     edx, ebx; unsigned __int16
0x101f05a67  lea     rcx, [r15+3Eh]; this
0x101f05a6b  lea     r8, [rbp+43E0h+var_4270]; unsigned int *
0x101f05a72  call    ?GetData@VarLogData@@QEBAPEBEGAEAI@Z; VarLogData::GetData(ushort,uint &)
0x101f05a77  test    rax, rax
0x101f05a7a  jz      def_101F059F0; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f05a80  movzx   ebx, byte ptr [rax]
0x101f05a83  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x101f05a89  mov     r9, rax; struct __crt_locale_pointers *
0x101f05a8c  mov     dword ptr [rsp+44E0h+DestinationSize], ebx
0x101f05a90  mov     [rsp+44E0h+var_44C0], rdi
0x101f05a95  lea     r8, aFieldSValue02l; "Field %s . Value: %02lx."
0x101f05a9c  mov     edx, 64h ; 'd'; unsigned __int64
0x101f05aa1  lea     rcx, [rbp+43E0h+var_2D30]; wchar_t *
0x101f05aa8  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x101f05aad  test    eax, eax
0x101f05aaf  jns     short loc_101F05AE9
0x101f05ab1  lfence
0x101f05ab4  mov     dword ptr [rsp+44E0h+var_44B0], eax
0x101f05ab8  mov     dword ptr [rsp+44E0h+DestinationSize], 1EEFh
0x101f05ac0  lea     rax, aSqlNtdbmsStore_419; "sql\\ntdbms\\storeng\\dmu\\dbcc\\source"...
0x101f05ac7  mov     [rsp+44E0h+var_44C0], rax
0x101f05acc  mov     edx, 7
0x101f05ad1  lea     ecx, [rdx-3]
0x101f05ad4  lea     r9d, [rdx-6]
0x101f05ad8  lea     r8d, [rdx+9]
0x101f05adc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101f05ae2  mov     r14d, [rbp+43E0h+arg_20]
0x101f05ae9  test    r14d, r14d
0x101f05aec  jz      short def_101F059F0; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f05aee  lea     r8, [rbp+43E0h+var_2D30]; wchar_t *
0x101f05af5  mov     edx, 100h; unsigned __int64
0x101f05afa  mov     rcx, r13; wchar_t *
0x101f05afd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x101f05b02  test    eax, eax
0x101f05b04  js      short def_101F059F0; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f05b06  lea     rcx, [rbp+43E0h+var_2D30]
0x101f05b0d  mov     rax, r12
0x101f05b10  inc     rax
0x101f05b13  cmp     word ptr [rcx+rax*2], 0
0x101f05b18  jnz     short loc_101F05B10
0x101f05b1a  sub     r14d, eax
0x101f05b1d  mov     [rbp+43E0h+arg_20], r14d
0x101f05b24  xor     ebx, ebx
0x101f05b26  mov     [rsp+44E0h+var_4480], ebx
0x101f05b2a  jmp     short loc_101F05B2E
0x101f05b2c  xor     ebx, ebx; jumptable 0000000101F059F0 default case, cases 5-7,9-13,15,17-21,23-27,29,31,33-37,39-57
0x101f05b2e  mov     edi, 2
0x101f05b33  cmp     byte ptr [r15+16h], 10h
0x101f05b38  jnz     loc_101F07FB0
0x101f05b3e  mov     [rbp+43E0h+var_4400], r12w
0x101f05b43  mov     [rbp+43E0h+var_43F8], rbx
0x101f05b47  mov     [rbp+43E0h+var_43FC], ebx
0x101f05b4a  mov     [rbp+43E0h+var_43E2], rbx
0x101f05b4e  mov     qword ptr [rbp+43E0h+var_43DA+2], rbx
0x101f05b52  mov     [rbp+43E0h+var_43F0], rbx
0x101f05b56  mov     [rbp+43E0h+var_4438], r12w
0x101f05b5b  mov     [rbp+43E0h+var_4430], rbx
  ... truncated ...
```
