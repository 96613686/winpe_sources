# CredStore::OpenCredManagerKey(wmi::AutoRegKey &)

- ea: `0x180017758`
- end: `0x1800177c9`
- name: `?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(CredStore *__hidden this, struct wmi::AutoRegKey *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017ab4`
- `0x180018444`

## callees

- `0x180017758`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800177b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800177b2`

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
0x180017758  mov     r11, rsp
0x18001775b  sub     rsp, 78h
0x18001775f  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180017766  xor     r9d, r9d; lpClass
0x180017769  mov     qword ptr [r11-38h], 0
0x180017771  xor     r8d, r8d; Reserved
0x180017774  mov     [r11-40h], rdx
0x180017778  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001777f  mov     [r11-20h], rax
0x180017783  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001778a  lea     rax, [r11-28h]
0x18001778e  mov     qword ptr [r11-28h], 18h
0x180017796  mov     [r11-48h], rax
0x18001779a  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x1800177a2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800177aa  mov     qword ptr [r11-18h], 0
0x1800177b2  call    cs:__imp_RegCreateKeyExW
0x1800177b8  test    eax, eax
0x1800177ba  jle     short loc_1800177C4
0x1800177bc  movzx   eax, ax
0x1800177bf  or      eax, 80070000h
0x1800177c4  add     rsp, 78h
0x1800177c8  retn
```
