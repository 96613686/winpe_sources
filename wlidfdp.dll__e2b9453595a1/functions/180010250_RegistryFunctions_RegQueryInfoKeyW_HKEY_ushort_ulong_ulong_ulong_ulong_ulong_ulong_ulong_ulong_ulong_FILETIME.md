# RegistryFunctions::RegQueryInfoKeyW(HKEY__ *,ushort *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *)

- ea: `0x180010250`
- end: `0x1800102e1`
- name: `?RegQueryInfoKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEAGPEAK22222222PEAU_FILETIME@@@Z`
- size: `145`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, unsigned __int16 *, unsigned int *, unsigned int *lpReserved, unsigned int *lpcSubKeys, unsigned int *lpcbMaxSubKeyLen, unsigned int *lpcbMaxClassLen, unsigned int *lpcValues, unsigned int *lpcbMaxValueNameLen, unsigned int *lpcbMaxValueLen, unsigned int *lpcbSecurityDescriptor, struct _FILETIME *lpftLastWriteTime)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800102d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800102d5`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryInfoKeyW(
        RegistryFunctions *this,
        HKEY a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *lpReserved,
        unsigned int *lpcSubKeys,
        unsigned int *lpcbMaxSubKeyLen,
        unsigned int *lpcbMaxClassLen,
        unsigned int *lpcValues,
        unsigned int *lpcbMaxValueNameLen,
        unsigned int *lpcbMaxValueLen,
        unsigned int *lpcbSecurityDescriptor,
        struct _FILETIME *lpftLastWriteTime)
{
  return RegQueryInfoKeyW(
           a2,
           a3,
           a4,
           lpReserved,
           lpcSubKeys,
           lpcbMaxSubKeyLen,
           lpcbMaxClassLen,
           lpcValues,
           lpcbMaxValueNameLen,
           lpcbMaxValueLen,
           lpcbSecurityDescriptor,
           lpftLastWriteTime);
}

```

## disassembly

```asm
0x180010250  push    rbx
0x180010252  sub     rsp, 60h
0x180010256  mov     rax, [rsp+68h+arg_60]
0x18001025e  mov     r10, r9
0x180010261  mov     r9, [rsp+68h+lpReserved]; lpReserved
0x180010269  mov     r11, r8
0x18001026c  mov     [rsp+68h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180010271  mov     rcx, rdx; hKey
0x180010274  mov     rax, [rsp+68h+arg_58]
0x18001027c  mov     r8, r10; lpcchClass
0x18001027f  mov     [rsp+68h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180010284  mov     rdx, r11; lpClass
0x180010287  mov     rax, [rsp+68h+arg_50]
0x18001028f  mov     [rsp+68h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180010294  mov     rax, [rsp+68h+arg_48]
0x18001029c  mov     [rsp+68h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800102a1  mov     rax, [rsp+68h+arg_40]
0x1800102a9  mov     [rsp+68h+lpcValues], rax; lpcValues
0x1800102ae  mov     rax, [rsp+68h+arg_38]
0x1800102b6  mov     [rsp+68h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800102bb  mov     rax, [rsp+68h+arg_30]
0x1800102c3  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800102c8  mov     rax, [rsp+68h+arg_28]
0x1800102d0  mov     [rsp+68h+lpcSubKeys], rax; lpcSubKeys
0x1800102d5  call    cs:__imp_RegQueryInfoKeyW
0x1800102db  add     rsp, 60h
0x1800102df  pop     rbx
0x1800102e0  retn
```
