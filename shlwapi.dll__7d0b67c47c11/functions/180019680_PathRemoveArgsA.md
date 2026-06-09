# PathRemoveArgsA

- ea: `0x180019680`
- end: `0x1800196ab`
- name: `PathRemoveArgsA`
- size: `43`
- prototype: `void __stdcall(LPSTR pszPath)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180019680`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsA` at `0x18001968d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsA` at `0x18001968d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksA` at `0x18001969f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksA` at `0x18001969f`

## pseudocode

```c
void __stdcall PathRemoveArgsA(LPSTR pszPath)
{
  LPSTR ArgsA; // rax

  if ( pszPath )
  {
    ArgsA = PathGetArgsA(pszPath);
    if ( *ArgsA )
      *(ArgsA - 1) = 0;
    PathRemoveBlanksA(pszPath);
  }
}

```

## disassembly

```asm
0x180019680  test    rcx, rcx
0x180019683  jz      short locret_1800196AA
0x180019685  push    rbx
0x180019686  sub     rsp, 20h
0x18001968a  mov     rbx, rcx
0x18001968d  call    cs:__imp_PathGetArgsA
0x180019693  cmp     byte ptr [rax], 0
0x180019696  jz      short loc_18001969C
0x180019698  mov     byte ptr [rax-1], 0
0x18001969c  mov     rcx, rbx; pszPath
0x18001969f  call    cs:__imp_PathRemoveBlanksA
0x1800196a5  add     rsp, 20h
0x1800196a9  pop     rbx
0x1800196aa  retn
```
