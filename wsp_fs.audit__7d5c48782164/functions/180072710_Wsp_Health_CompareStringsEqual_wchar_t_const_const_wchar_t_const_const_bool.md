# Wsp::Health::CompareStringsEqual(wchar_t const * const &,wchar_t const * const &,bool)

- ea: `0x180072710`
- end: `0x180072742`
- name: `?CompareStringsEqual@Health@Wsp@@YA_NAEBQEB_W0_N@Z`
- size: `50`
- prototype: `bool __fastcall(Wsp::Health *__hidden this, const wchar_t *const *, const wchar_t *const *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18007279c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007272a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007272a`

## pseudocode

```c
bool __fastcall Wsp::Health::CompareStringsEqual(LPCWCH *this, LPCWCH *a2, const wchar_t *const *a3)
{
  return CompareStringOrdinal(*this, -1, *a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180072710  sub     rsp, 38h
0x180072714  mov     r8, [rdx]; lpString2
0x180072717  or      eax, 0FFFFFFFFh
0x18007271a  mov     rcx, [rcx]; lpString1
0x18007271d  mov     r9d, eax; cchCount2
0x180072720  mov     edx, eax; cchCount1
0x180072722  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18007272a  call    cs:__imp_CompareStringOrdinal
0x180072731  nop     dword ptr [rax+rax+00h]
0x180072736  cmp     eax, 2
0x180072739  setz    al
0x18007273c  add     rsp, 38h
0x180072740  retn
```
