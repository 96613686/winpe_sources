# SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)

- ea: `0x14001c8d0`
- end: `0x14001c93a`
- name: `?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z`
- size: `106`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001c64c`

## callees

- `0x14000ea8c`
- `0x1400136e4`
- `0x14001c8d0`

## string_xrefs

- `0x14001c8dc`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`
- `0x14001c907`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenUserConfigKey(struct ATL::CRegKey *this)
{
  unsigned __int16 *v2; // r9
  HKEY v4; // [rsp+30h] [rbp-18h]
  unsigned int v5; // [rsp+58h] [rbp+10h] BYREF

  if ( (unsigned int)ATL::CRegKey::Open(this, HKEY_CURRENT_USER, SettingsCopier::_ATConfigKeyString, 0x20019u) )
    return (unsigned int)ATL::CRegKey::Create(
                           this,
                           HKEY_CURRENT_USER,
                           SettingsCopier::_ATConfigKeyString,
                           v2,
                           1u,
                           0x20019u,
                           v4,
                           &v5) != 0
         ? 0x80004005
         : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x14001c8d0  push    rbx
0x14001c8d2  sub     rsp, 40h
0x14001c8d6  mov     r9d, 20019h; unsigned int
0x14001c8dc  lea     r8, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001c8e3  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001c8ea  mov     rbx, rcx
0x14001c8ed  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001c8f2  test    eax, eax
0x14001c8f4  jz      short loc_14001C931
0x14001c8f6  lea     rax, [rsp+48h+arg_8]
0x14001c8fb  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001c902  mov     [rsp+48h+var_10], rax; unsigned int *
0x14001c907  lea     r8, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001c90e  mov     [rsp+48h+var_20], 20019h; REGSAM
0x14001c916  mov     rcx, rbx; this
0x14001c919  mov     [rsp+48h+var_28], 1; DWORD
0x14001c921  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001c926  neg     eax
0x14001c928  sbb     eax, eax
0x14001c92a  and     eax, 80004005h
0x14001c92f  jmp     short loc_14001C933
0x14001c931  xor     eax, eax
0x14001c933  add     rsp, 40h
0x14001c937  pop     rbx
0x14001c938  retn
```
