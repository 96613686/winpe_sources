# RegistryFunctions::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)

- ea: `0x180010160`
- end: `0x1800101a4`
- name: `?RegGetStringValue@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1PEAGPEAK@Z`
- size: `68`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *pvData, unsigned int *pcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010198`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010198`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegGetStringValue(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *pvData,
        unsigned int *pcbData)
{
  return RegGetValueW(a2, a3, a4, 2u, 0, pvData, pcbData);
}

```

## disassembly

```asm
0x180010160  push    rbx
0x180010162  sub     rsp, 40h
0x180010166  mov     rax, [rsp+48h+arg_28]
0x18001016b  mov     r10, r9
0x18001016e  mov     [rsp+48h+pcbData], rax; pcbData
0x180010173  mov     r11, r8
0x180010176  mov     rax, [rsp+48h+arg_20]
0x18001017b  mov     rcx, rdx; hkey
0x18001017e  mov     [rsp+48h+pvData], rax; pvData
0x180010183  mov     r9d, 2; dwFlags
0x180010189  mov     r8, r10; lpValue
0x18001018c  mov     [rsp+48h+pdwType], 0; pdwType
0x180010195  mov     rdx, r11; lpSubKey
0x180010198  call    cs:__imp_RegGetValueW
0x18001019e  add     rsp, 40h
0x1800101a2  pop     rbx
0x1800101a3  retn
```
