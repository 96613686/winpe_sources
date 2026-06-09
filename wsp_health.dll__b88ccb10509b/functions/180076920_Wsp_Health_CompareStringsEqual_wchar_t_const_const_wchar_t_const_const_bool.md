# Wsp::Health::CompareStringsEqual(wchar_t const * const &,wchar_t const * const &,bool)

- ea: `0x180076920`
- end: `0x18007694b`
- name: `?CompareStringsEqual@Health@Wsp@@YA_NAEBQEB_W0_N@Z`
- size: `43`
- prototype: `bool __fastcall(Wsp::Health *__hidden this, const wchar_t *const *, const wchar_t *const *, bool)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800769a4`
- `0x180076c1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007693a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007693a`

## pseudocode

```c
bool __fastcall Wsp::Health::CompareStringsEqual(LPCWCH *this, LPCWCH *a2, const wchar_t *const *a3)
{
  return CompareStringOrdinal(*this, -1, *a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180076920  sub     rsp, 38h
0x180076924  mov     r8, [rdx]; lpString2
0x180076927  or      eax, 0FFFFFFFFh
0x18007692a  mov     rcx, [rcx]; lpString1
0x18007692d  mov     r9d, eax; cchCount2
0x180076930  mov     edx, eax; cchCount1
0x180076932  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18007693a  call    cs:__imp_CompareStringOrdinal
0x180076940  cmp     eax, 2
0x180076943  setz    al
0x180076946  add     rsp, 38h
0x18007694a  retn
```
