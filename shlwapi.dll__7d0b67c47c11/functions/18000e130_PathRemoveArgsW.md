# PathRemoveArgsW

- ea: `0x18000e130`
- end: `0x18000e167`
- name: `PathRemoveArgsW`
- size: `55`
- prototype: `void __stdcall(LPWSTR pszPath)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e130`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18000e156`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18000e156`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x18000e144`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x18000e144`

## pseudocode

```c
void __stdcall PathRemoveArgsW(LPWSTR pszPath)
{
  LPWSTR ArgsW; // rax

  if ( pszPath )
  {
    ArgsW = PathGetArgsW(pszPath);
    if ( *ArgsW )
      *(ArgsW - 1) = 0;
    PathRemoveBlanksW(pszPath);
  }
}

```

## disassembly

```asm
0x18000e130  test    rcx, rcx
0x18000e133  jz      short locret_18000E166
0x18000e135  mov     [rsp+arg_0], rbx
0x18000e13a  push    rdi
0x18000e13b  sub     rsp, 20h
0x18000e13f  mov     rbx, rcx
0x18000e142  xor     edi, edi
0x18000e144  call    cs:__imp_PathGetArgsW
0x18000e14a  cmp     [rax], di
0x18000e14d  jz      short loc_18000E153
0x18000e14f  mov     [rax-2], di
0x18000e153  mov     rcx, rbx; pszPath
0x18000e156  call    cs:__imp_PathRemoveBlanksW
0x18000e15c  mov     rbx, [rsp+28h+arg_0]
0x18000e161  add     rsp, 20h
0x18000e165  pop     rdi
0x18000e166  retn
```
