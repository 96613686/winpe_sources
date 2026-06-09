# CredStore::OpenCredManagerKey(wmi::AutoRegKey &)

- ea: `0x1800187f0`
- end: `0x180018868`
- name: `?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(CredStore *__hidden this, struct wmi::AutoRegKey *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018b84`
- `0x1800195a0`

## callees

- `0x1800187f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001884a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001884a`

## pseudocode

```c
LSTATUS __fastcall CredStore::OpenCredManagerKey(CredStore *this, HKEY *a2)
{
  LSTATUS result; // eax
  struct _SECURITY_ATTRIBUTES v3; // [rsp+50h] [rbp-28h] BYREF

  v3.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  *(_QWORD *)&v3.nLength = 24;
  *(_QWORD *)&v3.bInheritHandle = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom",
             0,
             0,
             0,
             0xF003Fu,
             &v3,
             a2,
             0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800187f0  mov     r11, rsp
0x1800187f3  sub     rsp, 78h
0x1800187f7  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x1800187fe  xor     r9d, r9d; lpClass
0x180018801  mov     qword ptr [r11-38h], 0
0x180018809  xor     r8d, r8d; Reserved
0x18001880c  mov     [r11-40h], rdx
0x180018810  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018817  mov     [r11-20h], rax
0x18001881b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180018822  lea     rax, [r11-28h]
0x180018826  mov     qword ptr [r11-28h], 18h
0x18001882e  mov     [r11-48h], rax
0x180018832  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18001883a  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180018842  mov     qword ptr [r11-18h], 0
0x18001884a  call    cs:__imp_RegCreateKeyExW
0x180018851  nop     dword ptr [rax+rax+00h]
0x180018856  test    eax, eax
0x180018858  jle     short loc_180018862
0x18001885a  movzx   eax, ax
0x18001885d  or      eax, 80070000h
0x180018862  add     rsp, 78h
0x180018866  retn
```
