# UWF_CONFIG_INTERFACE_EX::GetFilterState(bool *,bool *)

- ea: `0x1800025a0`
- end: `0x1800025d2`
- name: `?GetFilterState@UWF_CONFIG_INTERFACE_EX@@UEAAJPEA_N0@Z`
- size: `50`
- prototype: `int __fastcall(UWF_CONFIG_INTERFACE_EX *this, bool *, bool *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800025a0`

## import_xrefs

- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x1800025b2`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x1800025c6`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x1800025b2`
- `uwfcfgmgmt!UwfCfgGetFilterEnabled` at `0x1800025c6`

## pseudocode

```c
int __fastcall UWF_CONFIG_INTERFACE_EX::GetFilterState(UWF_CONFIG_INTERFACE_EX *this, bool *a2, bool *a3)
{
  int result; // eax

  result = 0;
  if ( !a2 || (result = UwfCfgGetFilterEnabled(1, a2), result >= 0) )
  {
    if ( a3 )
      return UwfCfgGetFilterEnabled(0, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800025a0  push    rbx
0x1800025a2  sub     rsp, 20h
0x1800025a6  xor     eax, eax
0x1800025a8  mov     rbx, r8
0x1800025ab  test    rdx, rdx
0x1800025ae  jz      short loc_1800025BC
0x1800025b0  mov     cl, 1
0x1800025b2  call    cs:__imp_?UwfCfgGetFilterEnabled@@YAJ_NPEA_N@Z; UwfCfgGetFilterEnabled(bool,bool *)
0x1800025b8  test    eax, eax
0x1800025ba  js      short loc_1800025CC
0x1800025bc  test    rbx, rbx
0x1800025bf  jz      short loc_1800025CC
0x1800025c1  mov     rdx, rbx
0x1800025c4  xor     ecx, ecx
0x1800025c6  call    cs:__imp_?UwfCfgGetFilterEnabled@@YAJ_NPEA_N@Z; UwfCfgGetFilterEnabled(bool,bool *)
0x1800025cc  add     rsp, 20h
0x1800025d0  pop     rbx
0x1800025d1  retn
```
