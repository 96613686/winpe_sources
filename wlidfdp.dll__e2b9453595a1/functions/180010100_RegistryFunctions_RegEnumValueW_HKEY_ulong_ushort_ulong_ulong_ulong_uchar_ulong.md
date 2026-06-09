# RegistryFunctions::RegEnumValueW(HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x180010100`
- end: `0x180010157`
- name: `?RegEnumValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGPEAK22PEAE2@Z`
- size: `87`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, unsigned int *lpcchValueName, unsigned int *lpReserved, unsigned int *lpType, unsigned __int8 *lpData, unsigned int *lpcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001014b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001014b`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumValueW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned int *lpcchValueName,
        unsigned int *lpReserved,
        unsigned int *lpType,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  return RegEnumValueW(a2, a3, a4, lpcchValueName, lpReserved, lpType, lpData, lpcbData);
}

```

## disassembly

```asm
0x180010100  push    rbx
0x180010102  sub     rsp, 40h
0x180010106  mov     rax, [rsp+48h+arg_40]
0x18001010e  mov     r10, r9
0x180010111  mov     r9, [rsp+48h+lpcchValueName]; lpcchValueName
0x180010116  mov     r11d, r8d
0x180010119  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001011e  mov     rcx, rdx; hKey
0x180010121  mov     rax, [rsp+48h+arg_38]
0x180010129  mov     r8, r10; lpValueName
0x18001012c  mov     [rsp+48h+lpData], rax; lpData
0x180010131  mov     edx, r11d; dwIndex
0x180010134  mov     rax, [rsp+48h+arg_30]
0x18001013c  mov     [rsp+48h+lpType], rax; lpType
0x180010141  mov     rax, [rsp+48h+arg_28]
0x180010146  mov     [rsp+48h+lpReserved], rax; lpReserved
0x18001014b  call    cs:__imp_RegEnumValueW
0x180010151  add     rsp, 40h
0x180010155  pop     rbx
0x180010156  retn
```
