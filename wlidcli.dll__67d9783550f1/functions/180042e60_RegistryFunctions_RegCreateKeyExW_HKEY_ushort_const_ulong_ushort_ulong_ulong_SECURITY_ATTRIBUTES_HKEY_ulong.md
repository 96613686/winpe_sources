# RegistryFunctions::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x180042e60`
- end: `0x180042ec6`
- name: `?RegCreateKeyExW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `102`
- prototype: `int(RegistryFunctions *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042eba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042eba`

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
0x180042e60  push    rbx
0x180042e62  sub     rsp, 50h
0x180042e66  mov     rax, [rsp+58h+arg_48]
0x180042e6e  mov     r10d, r9d
0x180042e71  mov     r9, [rsp+58h+lpClass]; lpClass
0x180042e79  mov     r11, r8
0x180042e7c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180042e81  mov     rcx, rdx; hKey
0x180042e84  mov     rax, [rsp+58h+arg_40]
0x180042e8c  mov     r8d, r10d; Reserved
0x180042e8f  mov     [rsp+58h+phkResult], rax; phkResult
0x180042e94  mov     rdx, r11; lpSubKey
0x180042e97  mov     rax, [rsp+58h+arg_38]
0x180042e9f  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180042ea4  mov     eax, [rsp+58h+arg_30]
0x180042eab  mov     [rsp+58h+samDesired], eax; samDesired
0x180042eaf  mov     eax, [rsp+58h+arg_28]
0x180042eb6  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180042eba  call    cs:__imp_RegCreateKeyExW
0x180042ec0  add     rsp, 50h
0x180042ec4  pop     rbx
0x180042ec5  retn
```
