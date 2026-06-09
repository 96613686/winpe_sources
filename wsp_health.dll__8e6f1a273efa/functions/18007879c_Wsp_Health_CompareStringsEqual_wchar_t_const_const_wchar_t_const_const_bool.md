# Wsp::Health::CompareStringsEqual(wchar_t const * const &,wchar_t const * const &,bool)

- ea: `0x18007879c`
- end: `0x1800787ce`
- name: `?CompareStringsEqual@Health@Wsp@@YA_NAEBQEB_W0_N@Z`
- size: `50`
- prototype: `bool __fastcall(Wsp::Health *__hidden this, const wchar_t *const *, const wchar_t *const *, bool)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180078828`
- `0x180078aa0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800787b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800787b6`

## pseudocode

```c
bool __fastcall Wsp::Health::CompareStringsEqual(LPCWCH *this, LPCWCH *a2, const wchar_t *const *a3)
{
  return CompareStringOrdinal(*this, -1, *a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x18007879c  sub     rsp, 38h
0x1800787a0  mov     r8, [rdx]; lpString2
0x1800787a3  or      eax, 0FFFFFFFFh
0x1800787a6  mov     rcx, [rcx]; lpString1
0x1800787a9  mov     r9d, eax; cchCount2
0x1800787ac  mov     edx, eax; cchCount1
0x1800787ae  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800787b6  call    cs:__imp_CompareStringOrdinal
0x1800787bd  nop     dword ptr [rax+rax+00h]
0x1800787c2  cmp     eax, 2
0x1800787c5  setz    al
0x1800787c8  add     rsp, 38h
0x1800787cc  retn
```
