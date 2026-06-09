# GetSHA1Hash(uchar *,ulong,uchar *,ulong)

- ea: `0x180050820`
- end: `0x180050942`
- name: `?GetSHA1Hash@@YAJPEAEK0K@Z`
- size: `290`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, unsigned __int8 *, DWORD)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18004d030`
- `0x18004d350`
- `0x180050514`
- `0x180050820`
- `0x180050944`
- `0x1800653ba`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x18005090c`
- `ADVAPI32!CryptDestroyHash` at `0x18005090c`
- `ADVAPI32!CryptHashData` at `0x1800508ca`
- `ADVAPI32!CryptHashData` at `0x1800508ca`
- `ADVAPI32!CryptCreateHash` at `0x1800508aa`
- `ADVAPI32!CryptCreateHash` at `0x1800508aa`
- `ADVAPI32!CryptGetHashParam` at `0x1800508ea`
- `ADVAPI32!CryptGetHashParam` at `0x1800508ea`

## pseudocode

```c

```
