# ldapWStringsIdentical

- ea: `0x180020910`
- end: `0x180020960`
- name: `ldapWStringsIdentical`
- size: `80`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int cchCount1, PCNZWCH lpString2, int cchCount2)`
- caller_count: `14`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017854`
- `0x18001ba9c`
- `0x180020320`
- `0x1800207ec`
- `0x1800245ec`
- `0x18002d8d8`
- `0x18002e6d4`
- `0x1800442b0`
- `0x18004459c`
- `0x180046038`
- `0x1800494d4`
- `0x180049d3c`
- `0x18004a6c4`
- `0x18004b28c`

## callees

- `0x180020910`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020938`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020938`

## pseudocode

```c
bool __fastcall ldapWStringsIdentical(PCNZWCH lpString1, int cchCount1, PCNZWCH lpString2, int cchCount2)
{
  if ( !lpString1 )
    return lpString2 == 0;
  if ( lpString2 )
    return CompareStringW(0x400u, 1u, lpString1, cchCount1, lpString2, cchCount2) == 2;
  return 0;
}

```

## disassembly

```asm
0x180020910  sub     rsp, 38h
0x180020914  test    rcx, rcx
0x180020917  jz      short loc_180020950
0x180020919  test    r8, r8
0x18002091c  jz      short loc_18002095C
0x18002091e  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180020923  mov     r9d, edx; cchCount1
0x180020926  mov     [rsp+38h+lpString2], r8; lpString2
0x18002092b  mov     edx, 1; dwCmpFlags
0x180020930  mov     r8, rcx; lpString1
0x180020933  mov     ecx, 400h; Locale
0x180020938  call    cs:__imp_CompareStringW
0x18002093f  nop     dword ptr [rax+rax+00h]
0x180020944  cmp     eax, 2
0x180020947  setz    al
0x18002094a  add     rsp, 38h
0x18002094e  retn
0x180020950  test    r8, r8
0x180020953  setz    al
0x180020956  add     rsp, 38h
0x18002095a  retn
0x18002095c  xor     al, al
0x18002095e  jmp     short loc_18002094A
```
