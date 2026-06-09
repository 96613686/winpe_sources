# CDownloadDirNameCache::GenerateHash(DownloadManagerUpdateID const &,uchar * *,ulong *)

- ea: `0x1800e97d0`
- end: `0x1800e99d7`
- name: `?GenerateHash@CDownloadDirNameCache@@CAJAEBUDownloadManagerUpdateID@@PEAPEAEPEAK@Z`
- size: `519`
- prototype: `__int64 __fastcall(const struct DownloadManagerUpdateID *this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e99e0`

## callees

- `0x1800e97d0`
- `0x1800e9f18`
- `0x180113a10`
- `0x180113ae8`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e983b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e98e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e983b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e98e6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800e99af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800e99af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800e98dc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800e993f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800e98dc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800e993f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800e98bb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800e98bb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9867`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9963`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9996`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9867`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9963`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800e9996`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800e9831`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800e9831`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800e9885`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800e9885`

## pseudocode

```c

```
