# Wsp::Health::CompareStringsEqual(wchar_t const * const &,wchar_t const * const &,bool)

- ea: `0x180070bf0`
- end: `0x180070c1b`
- name: `?CompareStringsEqual@Health@Wsp@@YA_NAEBQEB_W0_N@Z`
- size: `43`
- prototype: `bool __fastcall(Wsp::Health *__hidden this, const wchar_t *const *, const wchar_t *const *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180070c74`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070c0a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070c0a`

## pseudocode

```c
bool __fastcall Wsp::Health::CompareStringsEqual(LPCWCH *this, LPCWCH *a2, const wchar_t *const *a3)
{
  return CompareStringOrdinal(*this, -1, *a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180070bf0  sub     rsp, 38h
0x180070bf4  mov     r8, [rdx]; lpString2
0x180070bf7  or      eax, 0FFFFFFFFh
0x180070bfa  mov     rcx, [rcx]; lpString1
0x180070bfd  mov     r9d, eax; cchCount2
0x180070c00  mov     edx, eax; cchCount1
0x180070c02  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180070c0a  call    cs:__imp_CompareStringOrdinal
0x180070c10  cmp     eax, 2
0x180070c13  setz    al
0x180070c16  add     rsp, 38h
0x180070c1a  retn
```
