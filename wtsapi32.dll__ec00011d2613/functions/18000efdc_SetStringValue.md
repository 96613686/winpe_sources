# SetStringValue

- ea: `0x18000efdc`
- end: `0x18000f01e`
- name: `SetStringValue`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a580`

## callees

- `0x18000efdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f013`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f013`

## pseudocode

```c
LSTATUS __fastcall SetStringValue(__int64 a1, HKEY a2, const WCHAR *a3, const BYTE *lpData)
{
  __int64 v4; // rax

  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  return RegSetValueExW(a2, a3, 0, 1u, lpData, 2 * v4 + 2);
}

```

## disassembly

```asm
0x18000efdc  sub     rsp, 38h
0x18000efe0  mov     r10, r8
0x18000efe3  mov     r11, rdx
0x18000efe6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efea  inc     rax
0x18000efed  cmp     word ptr [r9+rax*2], 0
0x18000eff3  jnz     short loc_18000EFEA
0x18000eff5  add     rax, rax
0x18000eff8  xor     r8d, r8d; Reserved
0x18000effb  add     eax, 2
0x18000effe  mov     rdx, r10; lpValueName
0x18000f001  mov     [rsp+38h+cbData], eax; cbData
0x18000f005  mov     rcx, r11; hKey
0x18000f008  mov     [rsp+38h+lpData], r9; lpData
0x18000f00d  mov     r9d, 1; dwType
0x18000f013  call    cs:__imp_RegSetValueExW
0x18000f019  add     rsp, 38h
0x18000f01d  retn
```
