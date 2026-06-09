# PathFileExistsDefExtA

- ea: `0x180018ce0`
- end: `0x180018d1f`
- name: `PathFileExistsDefExtA`
- size: `63`
- prototype: `__int64 __fastcall(LPCSTR pszPath)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018dd0`

## callees

- `0x180018ce0`
- `0x180018d28`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x180018cef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x180018cef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x180018cfc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x180018cfc`

## pseudocode

```c
__int64 __fastcall PathFileExistsDefExtA(LPCSTR pszPath, int a2)
{
  if ( PathIsUNCServerA(pszPath) || PathIsUNCServerShareA(pszPath) )
    return 0;
  else
    return PathFileExistsDefExtAndAttributesA(pszPath, a2);
}

```

## disassembly

```asm
0x180018ce0  mov     [rsp+arg_0], rbx
0x180018ce5  push    rdi
0x180018ce6  sub     rsp, 20h
0x180018cea  mov     edi, edx
0x180018cec  mov     rbx, rcx
0x180018cef  call    cs:__imp_PathIsUNCServerA
0x180018cf5  test    eax, eax
0x180018cf7  jnz     short loc_180018D12
0x180018cf9  mov     rcx, rbx; pszPath
0x180018cfc  call    cs:__imp_PathIsUNCServerShareA
0x180018d02  test    eax, eax
0x180018d04  jnz     short loc_180018D12
0x180018d06  mov     edx, edi
0x180018d08  mov     rcx, rbx; pszPath
0x180018d0b  call    PathFileExistsDefExtAndAttributesA
0x180018d10  jmp     short loc_180018D14
0x180018d12  xor     eax, eax
0x180018d14  mov     rbx, [rsp+28h+arg_0]
0x180018d19  add     rsp, 20h
0x180018d1d  pop     rdi
0x180018d1e  retn
```
