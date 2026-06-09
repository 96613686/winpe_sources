# SHRegDuplicateKey

- ea: `0x1800207cc`
- end: `0x1800207f4`
- name: `SHRegDuplicateKey`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f860`
- `0x18001f8a0`

## callees

- `0x1800207cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800207dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800207dd`

## pseudocode

```c
LSTATUS __fastcall SHRegDuplicateKey(HKEY a1, REGSAM a2, HKEY *phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(a1, 0, 0, a2, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800207cc  sub     rsp, 38h
0x1800207d0  mov     [rsp+38h+phkResult], r8; phkResult
0x1800207d5  mov     r9d, edx; samDesired
0x1800207d8  xor     r8d, r8d; ulOptions
0x1800207db  xor     edx, edx; lpSubKey
0x1800207dd  call    cs:__imp_RegOpenKeyExW
0x1800207e3  test    eax, eax
0x1800207e5  jle     short loc_1800207EF
0x1800207e7  movzx   eax, ax
0x1800207ea  or      eax, 80070000h
0x1800207ef  add     rsp, 38h
0x1800207f3  retn
```
