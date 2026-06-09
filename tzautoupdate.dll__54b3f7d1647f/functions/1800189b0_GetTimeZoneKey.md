# GetTimeZoneKey

- ea: `0x1800189b0`
- end: `0x1800189da`
- name: `GetTimeZoneKey`
- size: `42`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY *phkResult)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800179f4`
- `0x180017dd0`
- `0x18001831c`
- `0x18001859c`
- `0x18001a354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800189c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800189c2`

## pseudocode

```c
__int64 __fastcall GetTimeZoneKey(HKEY a1, const WCHAR *a2, HKEY *phkResult)
{
  return RegOpenKeyExW(a1, a2, 0, 0x20019u, phkResult) != 0 ? 0x80040204 : 0;
}

```

## disassembly

```asm
0x1800189b0  sub     rsp, 38h
0x1800189b4  mov     [rsp+38h+phkResult], r8; phkResult
0x1800189b9  mov     r9d, 20019h; samDesired
0x1800189bf  xor     r8d, r8d; ulOptions
0x1800189c2  call    cs:__imp_RegOpenKeyExW
0x1800189c8  xor     ecx, ecx
0x1800189ca  sub     ecx, eax
0x1800189cc  neg     ecx
0x1800189ce  sbb     eax, eax
0x1800189d0  and     eax, 80040204h
0x1800189d5  add     rsp, 38h
0x1800189d9  retn
```
