# WsSetConfigBool

- ea: `0x18003169c`
- end: `0x1800316df`
- name: `WsSetConfigBool`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002d1e8`

## callees

- `0x18003169c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316cd`

## pseudocode

```c
LSTATUS __fastcall WsSetConfigBool(HKEY *a1, const WCHAR *a2, unsigned int a3)
{
  HKEY v4; // rcx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 > 1 )
    return 87;
  v4 = *a1;
  Data = a3;
  return RegSetValueExW(v4, a2, 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x18003169c  sub     rsp, 38h
0x1800316a0  cmp     r8d, 1
0x1800316a4  jbe     short loc_1800316AD
0x1800316a6  mov     eax, 57h ; 'W'
0x1800316ab  jmp     short loc_1800316D9
0x1800316ad  mov     rcx, [rcx]; hKey
0x1800316b0  lea     rax, [rsp+38h+Data]
0x1800316b5  mov     r9d, 4; dwType
0x1800316bb  mov     [rsp+38h+Data], r8d
0x1800316c0  mov     [rsp+38h+cbData], r9d; cbData
0x1800316c5  xor     r8d, r8d; Reserved
0x1800316c8  mov     [rsp+38h+lpData], rax; lpData
0x1800316cd  call    cs:__imp_RegSetValueExW
0x1800316d4  nop     dword ptr [rax+rax+00h]
0x1800316d9  add     rsp, 38h
0x1800316dd  retn
```
