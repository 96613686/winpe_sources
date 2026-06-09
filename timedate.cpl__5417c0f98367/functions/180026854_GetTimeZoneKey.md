# GetTimeZoneKey

- ea: `0x180026854`
- end: `0x18002687e`
- name: `GetTimeZoneKey`
- size: `42`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180024984`
- `0x180024e1c`
- `0x180024f30`
- `0x1800251f8`
- `0x180025658`
- `0x1800257cc`
- `0x180026010`
- `0x180026360`
- `0x180028220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026866`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026866`

## pseudocode

```c
__int64 __fastcall GetTimeZoneKey(HKEY a1, const WCHAR *a2, HKEY *phkResult)
{
  return RegOpenKeyExW(a1, a2, 0, 0x20019u, phkResult) != 0 ? 0x80040204 : 0;
}

```

## disassembly

```asm
0x180026854  sub     rsp, 38h
0x180026858  mov     [rsp+38h+phkResult], r8; phkResult
0x18002685d  mov     r9d, 20019h; samDesired
0x180026863  xor     r8d, r8d; ulOptions
0x180026866  call    cs:__imp_RegOpenKeyExW
0x18002686c  xor     ecx, ecx
0x18002686e  sub     ecx, eax
0x180026870  neg     ecx
0x180026872  sbb     eax, eax
0x180026874  and     eax, 80040204h
0x180026879  add     rsp, 38h
0x18002687d  retn
```
