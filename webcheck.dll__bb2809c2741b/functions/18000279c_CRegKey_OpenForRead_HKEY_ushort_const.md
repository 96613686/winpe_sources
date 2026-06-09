# CRegKey::OpenForRead(HKEY__ *,ushort const *)

- ea: `0x18000279c`
- end: `0x1800027d2`
- name: `?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `54`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800027e0`
- `0x180002b10`
- `0x180002e30`
- `0x180002f20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800027ba`
- `ADVAPI32!RegOpenKeyExW` at `0x1800027ba`

## pseudocode

```c
__int64 __fastcall CRegKey::OpenForRead(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)
{
  return RegOpenKeyExW(hKey, lpSubKey, 0, 9u, phkResult) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18000279c  sub     rsp, 38h
0x1800027a0  mov     rax, r8
0x1800027a3  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800027a8  mov     r10, rdx
0x1800027ab  mov     r9d, 9; samDesired
0x1800027b1  mov     rdx, rax; lpSubKey
0x1800027b4  mov     rcx, r10; hKey
0x1800027b7  xor     r8d, r8d; ulOptions
0x1800027ba  call    cs:__imp_RegOpenKeyExW
0x1800027c0  xor     ecx, ecx
0x1800027c2  sub     ecx, eax
0x1800027c4  neg     ecx
0x1800027c6  sbb     eax, eax
0x1800027c8  and     eax, 80004005h
0x1800027cd  add     rsp, 38h
0x1800027d1  retn
```
