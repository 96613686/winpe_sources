# CShareSecurityInformation::MapGeneric(_GUID const *,uchar *,ulong *)

- ea: `0x18000bd70`
- end: `0x18000bd8b`
- name: `?MapGeneric@CShareSecurityInformation@@UEAAJPEBU_GUID@@PEAEPEAK@Z`
- size: `27`
- prototype: `__int64 __fastcall(CShareSecurityInformation *this, const struct _GUID *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000bd7e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000bd7e`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::MapGeneric(
        CShareSecurityInformation *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  MapGenericMask(a4, &ShareMap);
  return 0;
}

```

## disassembly

```asm
0x18000bd70  sub     rsp, 28h
0x18000bd74  lea     rdx, ?ShareMap@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000bd7b  mov     rcx, r9; AccessMask
0x18000bd7e  call    cs:__imp_MapGenericMask
0x18000bd84  xor     eax, eax
0x18000bd86  add     rsp, 28h
0x18000bd8a  retn
```
