# RegistryFunctions::RegEnumKeyW(HKEY__ *,ulong,ushort *,ulong)

- ea: `0x1800100b0`
- end: `0x1800100ec`
- name: `?RegEnumKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@KPEAGK@Z`
- size: `60`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, DWORD, unsigned __int16 *, DWORD cchName)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800100e1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800100e1`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegEnumKeyW(
        RegistryFunctions *this,
        HKEY a2,
        DWORD a3,
        unsigned __int16 *a4,
        DWORD cchName)
{
  return RegEnumKeyExW(a2, a3, a4, &cchName, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x1800100b0  sub     rsp, 48h
0x1800100b4  xor     ecx, ecx
0x1800100b6  mov     rax, r9
0x1800100b9  mov     [rsp+48h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x1800100be  lea     r9, [rsp+48h+cchName]; lpcchName
0x1800100c3  mov     [rsp+48h+lpcchClass], rcx; lpcchClass
0x1800100c8  mov     r10d, r8d
0x1800100cb  mov     [rsp+48h+lpClass], rcx; lpClass
0x1800100d0  mov     r11, rdx
0x1800100d3  mov     [rsp+48h+lpReserved], rcx; lpReserved
0x1800100d8  mov     r8, rax; lpName
0x1800100db  mov     rcx, r11; hKey
0x1800100de  mov     edx, r10d; dwIndex
0x1800100e1  call    cs:__imp_RegEnumKeyExW
0x1800100e7  add     rsp, 48h
0x1800100eb  retn
```
