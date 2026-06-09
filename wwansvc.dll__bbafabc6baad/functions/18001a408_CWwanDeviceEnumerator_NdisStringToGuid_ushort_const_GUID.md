# CWwanDeviceEnumerator::_NdisStringToGuid(ushort const *,_GUID &)

- ea: `0x18001a408`
- end: `0x18001a603`
- name: `?_NdisStringToGuid@CWwanDeviceEnumerator@@CAKPEBGAEAU_GUID@@@Z`
- size: `507`
- prototype: `unsigned int __fastcall(char *, UUID *Uuid)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x18001a680`
- `0x18001b060`
- `0x18001bd18`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180019fe4`
- `0x18001a028`
- `0x18001a06c`
- `0x18001a098`
- `0x18001a27c`
- `0x18001a408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a551`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a584`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a551`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a584`
- `RPCRT4!UuidFromStringW` at `0x18001a5bc`
- `RPCRT4!UuidFromStringW` at `0x18001a5bc`

## string_xrefs

- `0x18001a445`: `onecoreuap\net\wwan\service\core\wwandeviceenumerator.cpp`
- `0x18001a4bf`: `onecoreuap\net\wwan\service\core\wwandeviceenumerator.cpp`
- `0x18001a52c`: `onecoreuap\net\wwan\service\core\wwandeviceenumerator.cpp`
- `0x18001a520`: `StringCchCopyW failed to copy device name`

## pseudocode

```c

```
