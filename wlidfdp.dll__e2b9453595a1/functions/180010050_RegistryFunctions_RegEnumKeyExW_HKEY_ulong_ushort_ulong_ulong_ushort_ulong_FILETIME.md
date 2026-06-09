# RegistryFunctions::RegEnumKeyExW(HKEY__ *,ulong,ushort *,ulong *,ulong *,ushort *,ulong *,_FILETIME *)

- ea: `0x180010050`
- end: `0x1800100a7`
- name: `?RegEnumKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGPEAK212PEAU_FILETIME@@@Z`
- size: `87`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, unsigned int *lpcchName, unsigned int *lpReserved, unsigned __int16 *lpClass, unsigned int *lpcchClass, struct _FILETIME *lpftLastWriteTime)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001009b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001009b`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumKeyExW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned int *lpcchName,
        unsigned int *lpReserved,
        unsigned __int16 *lpClass,
        unsigned int *lpcchClass,
        struct _FILETIME *lpftLastWriteTime)
{
  return RegEnumKeyExW(a2, a3, a4, lpcchName, lpReserved, lpClass, lpcchClass, lpftLastWriteTime);
}

```

## disassembly

```asm
0x180010050  push    rbx
0x180010052  sub     rsp, 40h
0x180010056  mov     rax, [rsp+48h+arg_40]
0x18001005e  mov     r10, r9
0x180010061  mov     r9, [rsp+48h+lpcchName]; lpcchName
0x180010066  mov     r11d, r8d
0x180010069  mov     [rsp+48h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001006e  mov     rcx, rdx; hKey
0x180010071  mov     rax, [rsp+48h+arg_38]
0x180010079  mov     r8, r10; lpName
0x18001007c  mov     [rsp+48h+lpcchClass], rax; lpcchClass
0x180010081  mov     edx, r11d; dwIndex
0x180010084  mov     rax, [rsp+48h+arg_30]
0x18001008c  mov     [rsp+48h+lpClass], rax; lpClass
0x180010091  mov     rax, [rsp+48h+arg_28]
0x180010096  mov     [rsp+48h+lpReserved], rax; lpReserved
0x18001009b  call    cs:__imp_RegEnumKeyExW
0x1800100a1  add     rsp, 40h
0x1800100a5  pop     rbx
0x1800100a6  retn
```
