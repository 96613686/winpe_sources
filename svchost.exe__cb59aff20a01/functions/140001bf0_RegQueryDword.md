# RegQueryDword

- ea: `0x140001bf0`
- end: `0x140001c44`
- name: `RegQueryDword`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140006568`
- `0x1400068a4`

## callees

- `0x140001bf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c20`

## pseudocode

```c
LSTATUS __fastcall RegQueryDword(HKEY a1, const WCHAR *a2, BYTE *lpData)
{
  LSTATUS result; // eax
  DWORD cbData[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  Type = 0;
  cbData[0] = 4;
  result = RegQueryValueExW(a1, a2, 0, &Type, lpData, cbData);
  if ( !result && Type != 4 )
  {
    *(_DWORD *)lpData = 0;
    return 1804;
  }
  return result;
}

```

## disassembly

```asm
0x140001bf0  push    rbx
0x140001bf2  sub     rsp, 40h
0x140001bf6  mov     rbx, r8
0x140001bf9  mov     [rsp+48h+Type], 0
0x140001c01  lea     rax, [rsp+48h+cbData]
0x140001c06  mov     [rsp+48h+cbData], 4
0x140001c0e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140001c13  lea     r9, [rsp+48h+Type]; lpType
0x140001c18  xor     r8d, r8d; lpReserved
0x140001c1b  mov     [rsp+48h+lpData], rbx; lpData
0x140001c20  call    cs:__imp_RegQueryValueExW
0x140001c26  test    eax, eax
0x140001c28  jnz     short loc_140001C31
0x140001c2a  cmp     [rsp+48h+Type], 4
0x140001c2f  jnz     short loc_140001C37
0x140001c31  add     rsp, 40h
0x140001c35  pop     rbx
0x140001c36  retn
0x140001c37  mov     dword ptr [rbx], 0
0x140001c3d  mov     eax, 70Ch
0x140001c42  jmp     short loc_140001C31
```
