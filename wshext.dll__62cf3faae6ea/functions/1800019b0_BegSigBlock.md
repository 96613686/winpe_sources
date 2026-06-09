# BegSigBlock

- ea: `0x1800019b0`
- end: `0x1800019d7`
- name: `BegSigBlock`
- size: `39`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001490`
- `0x180002360`
- `0x180008f7c`

## callees

- `0x1800019b0`

## pseudocode

```c
const wchar_t *__fastcall BegSigBlock(int a1)
{
  if ( a1 == 2 )
    return L"\r\n// SIG // Begin signature block";
  if ( a1 == 3 )
    return L"\r\n<signature>";
  return L"\r\n'' SIG '' Begin signature block";
}

```

## disassembly

```asm
0x1800019b0  cmp     ecx, 2
0x1800019b3  jnz     short loc_1800019BD
0x1800019b5  lea     rax, aSigBeginSignat; "\r\n// SIG // Begin signature block"
0x1800019bc  retn
0x1800019bd  sub     ecx, 1
0x1800019c0  jnz     short loc_1800019CA
0x1800019c2  lea     rax, aSigBeginSignat_0; "\r\n'' SIG '' Begin signature block"
0x1800019c9  retn
0x1800019ca  cmp     ecx, 2
0x1800019cd  jnz     short loc_1800019C2
0x1800019cf  lea     rax, aSignature; "\r\n<signature>"
0x1800019d6  retn
```
