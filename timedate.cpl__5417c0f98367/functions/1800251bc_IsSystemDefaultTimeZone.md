# IsSystemDefaultTimeZone

- ea: `0x1800251bc`
- end: `0x1800251f2`
- name: `IsSystemDefaultTimeZone`
- size: `54`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180024f30`
- `0x180025658`
- `0x180025f48`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800251dd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800251dd`

## pseudocode

```c
_BOOL8 __fastcall IsSystemDefaultTimeZone(PCNZWCH lpString1)
{
  return CompareStringW(0x7Fu, 0, lpString1, -1, L"SystemDefaultTimeZone", -1) == 2;
}

```

## disassembly

```asm
0x1800251bc  sub     rsp, 38h
0x1800251c0  xor     edx, edx; dwCmpFlags
0x1800251c2  lea     rax, aSystemdefaultt; "SystemDefaultTimeZone"
0x1800251c9  or      r9d, 0FFFFFFFFh; cchCount1
0x1800251cd  mov     r8, rcx; lpString1
0x1800251d0  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800251d5  mov     [rsp+38h+lpString2], rax; lpString2
0x1800251da  lea     ecx, [rdx+7Fh]; Locale
0x1800251dd  call    cs:__imp_CompareStringW
0x1800251e3  xor     ecx, ecx
0x1800251e5  cmp     eax, 2
0x1800251e8  setz    cl
0x1800251eb  mov     eax, ecx
0x1800251ed  add     rsp, 38h
0x1800251f1  retn
```
