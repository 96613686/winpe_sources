# LiteCryptUtilities::HmacHashHelper(unsigned __int64,unsigned __int64,uint,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180113738`
- end: `0x180113ac3`
- name: `?HmacHashHelper@LiteCryptUtilities@@YAJ_K0IPEAEK1KPEAPEAEPEAK@Z`
- size: `907`
- prototype: `__int64 __usercall@<rax>(HCRYPTPROV hProv@<rcx>, HCRYPTKEY hKey@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, DWORD dwDataLen, BYTE *, DWORD, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1801124c4`

## callees

- `0x180009e98`
- `0x18000a354`
- `0x18000a36c`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180039b00`
- `0x18011236c`
- `0x180113738`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801139ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801139ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011397c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011397c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113a01`
- `CRYPTSP!CryptHashData` at `0x1801138dc`
- `CRYPTSP!CryptHashData` at `0x180113928`
- `CRYPTSP!CryptHashData` at `0x1801138dc`
- `CRYPTSP!CryptHashData` at `0x180113928`
- `CRYPTSP!CryptCreateHash` at `0x180113849`
- `CRYPTSP!CryptCreateHash` at `0x180113849`
- `CRYPTSP!CryptGetHashParam` at `0x180113972`
- `CRYPTSP!CryptGetHashParam` at `0x1801139f7`
- `CRYPTSP!CryptGetHashParam` at `0x180113972`
- `CRYPTSP!CryptGetHashParam` at `0x1801139f7`
- `CRYPTSP!CryptSetHashParam` at `0x18011389f`
- `CRYPTSP!CryptSetHashParam` at `0x18011389f`

## pseudocode

```c

```
