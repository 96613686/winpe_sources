# RegistryFunctions::RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x180010340`
- end: `0x18001037a`
- name: `?RegQueryValueExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGPEAK2PEAE2@Z`
- size: `58`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, unsigned int *, unsigned int *lpType, unsigned __int8 *lpData, unsigned int *lpcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001036e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001036e`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryValueExW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *lpType,
        unsigned __int8 *lpData,
        unsigned int *lpcbData)
{
  return RegQueryValueExW(a2, a3, a4, lpType, lpData, lpcbData);
}

```

## disassembly

```asm
0x180010340  push    rbx
0x180010342  sub     rsp, 30h
0x180010346  mov     rax, [rsp+38h+arg_30]
0x18001034b  mov     r10, r9
0x18001034e  mov     r9, [rsp+38h+lpType]; lpType
0x180010353  mov     r11, r8
0x180010356  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001035b  mov     rcx, rdx; hKey
0x18001035e  mov     rax, [rsp+38h+arg_28]
0x180010363  mov     r8, r10; lpReserved
0x180010366  mov     rdx, r11; lpValueName
0x180010369  mov     [rsp+38h+lpData], rax; lpData
0x18001036e  call    cs:__imp_RegQueryValueExW
0x180010374  add     rsp, 30h
0x180010378  pop     rbx
0x180010379  retn
```
