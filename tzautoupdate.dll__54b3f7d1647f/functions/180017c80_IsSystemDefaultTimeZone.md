# IsSystemDefaultTimeZone

- ea: `0x180017c80`
- end: `0x180017cb6`
- name: `IsSystemDefaultTimeZone`
- size: `54`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800179f4`
- `0x180018254`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ca1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ca1`

## pseudocode

```c
_BOOL8 __fastcall IsSystemDefaultTimeZone(PCNZWCH lpString1)
{
  return CompareStringW(0x7Fu, 0, lpString1, -1, L"SystemDefaultTimeZone", -1) == 2;
}

```

## disassembly

```asm
0x180017c80  sub     rsp, 38h
0x180017c84  xor     edx, edx; dwCmpFlags
0x180017c86  lea     rax, aSystemdefaultt; "SystemDefaultTimeZone"
0x180017c8d  or      r9d, 0FFFFFFFFh; cchCount1
0x180017c91  mov     r8, rcx; lpString1
0x180017c94  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180017c99  mov     [rsp+38h+lpString2], rax; lpString2
0x180017c9e  lea     ecx, [rdx+7Fh]; Locale
0x180017ca1  call    cs:__imp_CompareStringW
0x180017ca7  xor     ecx, ecx
0x180017ca9  cmp     eax, 2
0x180017cac  setz    cl
0x180017caf  mov     eax, ecx
0x180017cb1  add     rsp, 38h
0x180017cb5  retn
```
