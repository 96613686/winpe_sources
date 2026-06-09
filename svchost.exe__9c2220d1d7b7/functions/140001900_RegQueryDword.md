# RegQueryDword

- ea: `0x140001900`
- end: `0x14000195b`
- name: `RegQueryDword`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140006a3c`
- `0x140006d84`

## callees

- `0x140001900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001930`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001930`

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
0x140001900  push    rbx
0x140001902  sub     rsp, 40h
0x140001906  mov     rbx, r8
0x140001909  mov     [rsp+48h+Type], 0
0x140001911  lea     rax, [rsp+48h+cbData]
0x140001916  mov     [rsp+48h+cbData], 4
0x14000191e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140001923  lea     r9, [rsp+48h+Type]; lpType
0x140001928  xor     r8d, r8d; lpReserved
0x14000192b  mov     [rsp+48h+lpData], rbx; lpData
0x140001930  call    cs:__imp_RegQueryValueExW
0x140001937  nop     dword ptr [rax+rax+00h]
0x14000193c  test    eax, eax
0x14000193e  jnz     short loc_140001947
0x140001940  cmp     [rsp+48h+Type], 4
0x140001945  jnz     short loc_14000194E
0x140001947  add     rsp, 40h
0x14000194b  pop     rbx
0x14000194c  retn
0x14000194e  mov     dword ptr [rbx], 0
0x140001954  mov     eax, 70Ch
0x140001959  jmp     short loc_140001947
```
