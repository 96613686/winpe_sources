# CEcsHash::HashData(uint,void const *,ulong,void *,ulong,ulong *)

- ea: `0x180067e84`
- end: `0x180068035`
- name: `?HashData@CEcsHash@@SAJIPEBXKPEAXKPEAK@Z`
- size: `433`
- prototype: `__int64 __fastcall(ALG_ID Algid, BYTE *pbData, DWORD dwDataLen, BYTE *, DWORD pdwDataLen, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180033a2c`
- `0x18007b724`
- `0x1800a0dc4`
- `0x1800d098c`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180067e84`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x180068013`
- `ADVAPI32!CryptDestroyHash` at `0x180068013`
- `ADVAPI32!CryptGetHashParam` at `0x180067fb3`
- `ADVAPI32!CryptGetHashParam` at `0x180067fb3`
- `ADVAPI32!CryptHashData` at `0x180067f58`
- `ADVAPI32!CryptHashData` at `0x180067f58`
- `ADVAPI32!CryptCreateHash` at `0x180067f06`
- `ADVAPI32!CryptCreateHash` at `0x180067f06`

## pseudocode

```c

```
