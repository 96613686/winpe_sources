# PathFileExistsDefExtAndAttributesA

- ea: `0x180018d28`
- end: `0x180018db6`
- name: `PathFileExistsDefExtAndAttributesA`
- size: `142`
- prototype: `__int64 __fastcall(LPCSTR pszPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180018ce0`

## callees

- `0x180013066`
- `0x180017d50`
- `0x180018bd0`
- `0x180018d28`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeA` at `0x180018d55`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeA` at `0x180018d55`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x180018d66`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x180018d66`

## pseudocode

```c
__int64 __fastcall PathFileExistsDefExtAndAttributesA(LPCSTR pszPath, int a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  _BYTE v6[328]; // [rsp+20h] [rbp-148h] BYREF

  result = 0;
  if ( pszPath )
  {
    v5 = -1;
    do
      ++v5;
    while ( pszPath[v5] );
    if ( pszPath[v5 - 1] == 92 && !PathIsRelativeA(pszPath) || !a2 || *PathFindExtensionA(pszPath) && (a2 & 0x40) != 0 )
    {
      return PathFileExistsAndAttributesA(pszPath);
    }
    else
    {
      memset_0(v6, 0, 0x140u);
      return ApplyDefaultExts_0(pszPath);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018d28  mov     [rsp+arg_0], rbx
0x180018d2d  push    rdi
0x180018d2e  sub     rsp, 160h
0x180018d35  xor     eax, eax
0x180018d37  mov     edi, edx
0x180018d39  mov     rbx, rcx
0x180018d3c  test    rcx, rcx
0x180018d3f  jz      short loc_180018DA5
0x180018d41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018d45  inc     rax
0x180018d48  cmp     byte ptr [rcx+rax], 0
0x180018d4c  jnz     short loc_180018D45
0x180018d4e  cmp     byte ptr [rax+rcx-1], 5Ch ; '\'
0x180018d53  jnz     short loc_180018D5F
0x180018d55  call    cs:__imp_PathIsRelativeA
0x180018d5b  test    eax, eax
0x180018d5d  jz      short loc_180018D9B
0x180018d5f  test    edi, edi
0x180018d61  jz      short loc_180018D9B
0x180018d63  mov     rcx, rbx; pszPath
0x180018d66  call    cs:__imp_PathFindExtensionA
0x180018d6c  cmp     byte ptr [rax], 0
0x180018d6f  jz      short loc_180018D77
0x180018d71  test    dil, 40h
0x180018d75  jnz     short loc_180018D9B
0x180018d77  xor     edx, edx; Val
0x180018d79  lea     rcx, [rsp+168h+var_148]; void *
0x180018d7e  mov     r8d, 140h; Size
0x180018d84  call    memset_0
0x180018d89  lea     r9, [rsp+168h+var_148]
0x180018d8e  mov     r8d, edi
0x180018d91  mov     rcx, rbx; lpFileName
0x180018d94  call    ApplyDefaultExts_0
0x180018d99  jmp     short loc_180018DA5
0x180018d9b  xor     edx, edx
0x180018d9d  mov     rcx, rbx; pszPath
0x180018da0  call    PathFileExistsAndAttributesA
0x180018da5  mov     rbx, [rsp+168h+arg_0]
0x180018dad  add     rsp, 160h
0x180018db4  pop     rdi
0x180018db5  retn
```
