# RegistryFunctions::RegGetValueW(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)

- ea: `0x1800101b0`
- end: `0x1800101fa`
- name: `?RegGetValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1KPEAKPEAX2@Z`
- size: `74`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD dwFlags, unsigned int *pdwType, PVOID pvData, unsigned int *pcbData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800101ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800101ee`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegGetValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwFlags,
        unsigned int *pdwType,
        PVOID pvData,
        unsigned int *pcbData)
{
  return RegGetValueW(a2, a3, a4, dwFlags, pdwType, pvData, pcbData);
}

```

## disassembly

```asm
0x1800101b0  push    rbx
0x1800101b2  sub     rsp, 40h
0x1800101b6  mov     rax, [rsp+48h+arg_38]
0x1800101be  mov     r10, r9
0x1800101c1  mov     r9d, [rsp+48h+dwFlags]; dwFlags
0x1800101c6  mov     r11, r8
0x1800101c9  mov     [rsp+48h+pcbData], rax; pcbData
0x1800101ce  mov     rcx, rdx; hkey
0x1800101d1  mov     rax, [rsp+48h+arg_30]
0x1800101d9  mov     r8, r10; lpValue
0x1800101dc  mov     [rsp+48h+pvData], rax; pvData
0x1800101e1  mov     rdx, r11; lpSubKey
0x1800101e4  mov     rax, [rsp+48h+arg_28]
0x1800101e9  mov     [rsp+48h+pdwType], rax; pdwType
0x1800101ee  call    cs:__imp_RegGetValueW
0x1800101f4  add     rsp, 40h
0x1800101f8  pop     rbx
0x1800101f9  retn
```
