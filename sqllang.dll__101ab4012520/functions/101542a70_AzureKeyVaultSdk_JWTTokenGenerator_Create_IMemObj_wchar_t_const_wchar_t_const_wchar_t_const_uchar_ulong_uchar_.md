# AzureKeyVaultSdk::JWTTokenGenerator::Create(IMemObj *,wchar_t const *,wchar_t const *,wchar_t const *,uchar *,ulong,uchar *,ulong,void *,char * *)

- ea: `0x101542a70`
- end: `0x101543bed`
- name: `?Create@JWTTokenGenerator@AzureKeyVaultSdk@@QEAA?AUKeyVaultOpResult@2@PEAVIMemObj@@PEB_W11PEAEK2KPEAXPEAPEAD@Z`
- size: `4477`
- prototype: `struct AzureKeyVaultSdk::KeyVaultOpResult __high(struct IMemObj *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, void *, char **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1015442d0`

## callees

- `0x100401070`
- `0x100403080`
- `0x10084a500`
- `0x100cb74e0`
- `0x100cb7a90`
- `0x101542a70`
- `0x1015498b0`
- `0x10154b490`
- `0x10154bbb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x101542c53`
- `KERNEL32!GetLastError` at `0x101542cca`
- `KERNEL32!GetLastError` at `0x101542c53`
- `KERNEL32!GetLastError` at `0x101542cca`
- `ole32!CoCreateGuid` at `0x101542f4f`
- `ole32!CoCreateGuid` at `0x101542f4f`
- `ole32!StringFromGUID2` at `0x101542fd7`
- `ole32!StringFromGUID2` at `0x101542fd7`
- `secforwarder!BCryptOpenAlgorithmProvider` at `0x1015435b5`
- `secforwarder!BCryptOpenAlgorithmProvider` at `0x1015435b5`
- `secforwarder!CryptBinaryToStringW` at `0x101542c42`
- `secforwarder!CryptBinaryToStringW` at `0x101542cc0`
- `secforwarder!CryptBinaryToStringW` at `0x101542c42`
- `secforwarder!CryptBinaryToStringW` at `0x101542cc0`
- `secforwarder!BCryptFinishHash` at `0x101543772`
- `secforwarder!BCryptFinishHash` at `0x101543772`
- `secforwarder!BCryptCloseAlgorithmProvider` at `0x101543ad5`
- `secforwarder!BCryptCloseAlgorithmProvider` at `0x101543ad5`
- `secforwarder!BCryptHashData` at `0x1015436b7`
- `secforwarder!BCryptHashData` at `0x1015436b7`
- `secforwarder!BCryptCreateHash` at `0x101543678`
- `secforwarder!BCryptCreateHash` at `0x101543678`
- `secforwarder!BCryptSignHash` at `0x1015437c6`
- `secforwarder!BCryptSignHash` at `0x101543858`
- `secforwarder!BCryptSignHash` at `0x1015437c6`
- `secforwarder!BCryptSignHash` at `0x101543858`
- `secforwarder!BCryptGetProperty` at `0x1015435fe`
- `secforwarder!BCryptGetProperty` at `0x1015436ff`
- `secforwarder!BCryptGetProperty` at `0x1015435fe`
- `secforwarder!BCryptGetProperty` at `0x1015436ff`
- `secforwarder!BCryptDestroyHash` at `0x101543ae4`
- `secforwarder!BCryptDestroyHash` at `0x101543ae4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101542c88`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101542c88`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542de8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542ee5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542f8c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543015`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015432b4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543517`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10154363b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543742`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543806`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015439b8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542de8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542ee5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101542f8c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543015`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015432b4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543517`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10154363b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543742`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101543806`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015439b8`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542bd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542c04`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542c9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542cf3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542e14`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542f11`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542f31`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542fa0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543029`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015432e0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015432ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543335`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154337f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015433ab`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015433cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154341d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543450`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543543`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543562`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154359a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154364f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543756`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154381a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438dc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543a04`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b09`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b14`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b1f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b35`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b40`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b4b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b56`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b61`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b77`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b82`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b98`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543ba4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543baf`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543bba`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542bd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542c04`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542c9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542cf3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542e14`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542f11`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542f31`
- `sqldk!??_V@YAXPEAX@Z` at `0x101542fa0`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543029`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015432e0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015432ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543335`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154337f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015433ab`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015433cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154341d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543450`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543543`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543562`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154359a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154364f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543756`
- `sqldk!??_V@YAXPEAX@Z` at `0x10154381a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438dc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015438fc`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543a04`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b09`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b14`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b1f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b35`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b40`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b4b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b56`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b61`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b77`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b82`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543b98`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543ba4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543baf`
- `sqldk!??_V@YAXPEAX@Z` at `0x101543bba`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x101543954`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x101543954`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10154305d`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10154305d`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x10154306a`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x10154306a`

## string_xrefs

- `0x101543165`: `/oauth2/token`
- `0x101542dd5`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x101542ed2`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x1015432a1`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x101543504`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x1015439a6`: `sql\ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x101542f78`: `sql\ntdbms\msql\security\src\AzureKeyVaultSdk.cpp`
- `0x101543001`: `sql\ntdbms\msql\security\src\AzureKeyVaultSdk.cpp`
- `0x10154362b`: `sql\ntdbms\msql\security\src\AzureKeyVaultSdk.cpp`
- `0x101543732`: `sql\ntdbms\msql\security\src\AzureKeyVaultSdk.cpp`
- `0x1015437f6`: `sql\ntdbms\msql\security\src\AzureKeyVaultSdk.cpp`
- `0x101542c7b`: `sql\ntdbms\msql\security\src\Base64UtilsForSec.cpp`

## pseudocode

```c

```
