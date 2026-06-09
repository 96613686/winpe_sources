# RegistryFunctions::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x18000ff10`
- end: `0x18000ff76`
- name: `?RegCreateKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `102`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, DWORD, unsigned __int16 *lpClass, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, HKEY *phkResult, unsigned int *lpdwDisposition)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ff6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ff6a`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegCreateKeyExW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned __int16 *lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  return RegCreateKeyExW(a2, a3, a4, lpClass, dwOptions, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition);
}

```

## disassembly

```asm
0x18000ff10  push    rbx
0x18000ff12  sub     rsp, 50h
0x18000ff16  mov     rax, [rsp+58h+arg_48]
0x18000ff1e  mov     r10d, r9d
0x18000ff21  mov     r9, [rsp+58h+lpClass]; lpClass
0x18000ff29  mov     r11, r8
0x18000ff2c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000ff31  mov     rcx, rdx; hKey
0x18000ff34  mov     rax, [rsp+58h+arg_40]
0x18000ff3c  mov     r8d, r10d; Reserved
0x18000ff3f  mov     [rsp+58h+phkResult], rax; phkResult
0x18000ff44  mov     rdx, r11; lpSubKey
0x18000ff47  mov     rax, [rsp+58h+arg_38]
0x18000ff4f  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000ff54  mov     eax, [rsp+58h+arg_30]
0x18000ff5b  mov     [rsp+58h+samDesired], eax; samDesired
0x18000ff5f  mov     eax, [rsp+58h+arg_28]
0x18000ff66  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18000ff6a  call    cs:__imp_RegCreateKeyExW
0x18000ff70  add     rsp, 50h
0x18000ff74  pop     rbx
0x18000ff75  retn
```
