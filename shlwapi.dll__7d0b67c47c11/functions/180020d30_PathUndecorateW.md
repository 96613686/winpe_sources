# PathUndecorateW

- ea: `0x180020d30`
- end: `0x180020dbc`
- name: `PathUndecorateW`
- size: `140`
- prototype: `void __stdcall(LPWSTR pszPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180020d30`
- `0x1800369dd`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180020d4b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180020d4b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180020d94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180020d94`

## pseudocode

```c
void __stdcall PathUndecorateW(LPWSTR pszPath)
{
  const WCHAR *ExtensionW; // rax
  const WCHAR *v3; // rsi
  LPWSTR v4; // rbx
  int v5; // eax

  if ( pszPath )
  {
    ExtensionW = PathFindExtensionW(pszPath);
    v3 = ExtensionW;
    if ( ExtensionW > pszPath && *(ExtensionW - 1) == 93 )
    {
      v4 = (LPWSTR)(ExtensionW - 2);
      if ( ExtensionW - 2 > pszPath )
      {
        do
        {
          if ( (unsigned __int16)(*v4 - 48) > 9u )
            break;
          --v4;
        }
        while ( v4 > pszPath );
        if ( *v4 == 91 && v4 > pszPath && *(v4 - 1) != 92 )
        {
          v5 = lstrlenW(ExtensionW);
          memmove_0(v4, v3, 2LL * (unsigned int)(v5 + 1));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180020d30  test    rcx, rcx
0x180020d33  jz      locret_180020DBB
0x180020d39  mov     [rsp+arg_0], rbx
0x180020d3e  mov     [rsp+arg_8], rsi
0x180020d43  push    rdi
0x180020d44  sub     rsp, 20h
0x180020d48  mov     rdi, rcx
0x180020d4b  call    cs:__imp_PathFindExtensionW
0x180020d51  mov     rsi, rax
0x180020d54  cmp     rax, rdi
0x180020d57  jbe     short loc_180020DAC
0x180020d59  cmp     word ptr [rax-2], 5Dh ; ']'
0x180020d5e  jnz     short loc_180020DAC
0x180020d60  lea     rbx, [rax-4]
0x180020d64  cmp     rbx, rdi
0x180020d67  jbe     short loc_180020DAC
0x180020d69  movzx   ecx, word ptr [rbx]
0x180020d6c  sub     cx, 30h ; '0'
0x180020d70  cmp     cx, 9
0x180020d74  ja      short loc_180020D7F
0x180020d76  sub     rbx, 2
0x180020d7a  cmp     rbx, rdi
0x180020d7d  ja      short loc_180020D69
0x180020d7f  cmp     word ptr [rbx], 5Bh ; '['
0x180020d83  jnz     short loc_180020DAC
0x180020d85  cmp     rbx, rdi
0x180020d88  jbe     short loc_180020DAC
0x180020d8a  cmp     word ptr [rbx-2], 5Ch ; '\'
0x180020d8f  jz      short loc_180020DAC
0x180020d91  mov     rcx, rsi; lpString
0x180020d94  call    cs:__imp_lstrlenW
0x180020d9a  mov     rdx, rsi; Src
0x180020d9d  mov     rcx, rbx; void *
0x180020da0  lea     r8d, [rax+1]
0x180020da4  add     r8, r8; Size
0x180020da7  call    memmove_0
0x180020dac  mov     rbx, [rsp+28h+arg_0]
0x180020db1  mov     rsi, [rsp+28h+arg_8]
0x180020db6  add     rsp, 20h
0x180020dba  pop     rdi
0x180020dbb  retn
```
