# GenerateRandomBits(uchar *,ulong)

- ea: `0x18000fee0`
- end: `0x18000ff0d`
- name: `?GenerateRandomBits@@YAKPEAEK@Z`
- size: `45`
- prototype: `unsigned int __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e9f4`
- `0x1800112c0`
- `0x180050a00`
- `0x18005d974`
- `0x18005fde0`
- `0x180075cf0`
- `0x18007c28c`
- `0x18007e64c`
- `0x18008141c`
- `0x180081d80`

## callees

- `0x18000fee0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ff05`
- `ntdll!RtlNtStatusToDosError` at `0x18000ff05`
- `bcrypt!BCryptGenRandom` at `0x18000fef2`
- `bcrypt!BCryptGenRandom` at `0x18000fef2`

## pseudocode

```c

```
