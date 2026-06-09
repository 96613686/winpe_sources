# VmpMarkDeleted(_DEVICE_OBJECT *,uchar)

- ea: `0x140012664`
- end: `0x14001270a`
- name: `?VmpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400046a4`
- `0x140016aa0`

## callees

- `0x140012664`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1400126ca`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400126ca`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400126d8`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400126d8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001268d`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001268d`
- `ntoskrnl!ZwClose` at `0x1400126f0`
- `ntoskrnl!ZwClose` at `0x1400126f0`

## string_xrefs

- `0x1400126a4`: `IsDeleted`

## pseudocode

```c
__int64 __fastcall VmpMarkDeleted(struct _DEVICE_OBJECT *a1, char a2)
{
  NTSTATUS v3; // ebx
  NTSTATUS v4; // eax
  int ValueData; // [rsp+50h] [rbp+18h] BYREF
  PCWSTR Path; // [rsp+58h] [rbp+20h] BYREF

  Path = 0;
  ValueData = 1;
  v3 = IoOpenDeviceRegistryKey(a1, 1u, 0x2001Fu, (PHANDLE)&Path);
  if ( v3 >= 0 )
  {
    if ( a2 )
      v4 = RtlWriteRegistryValue(0x40000000u, Path, L"IsDeleted", 4u, &ValueData, 4u);
    else
      v4 = RtlDeleteRegistryValue(0x40000000u, Path, L"IsDeleted");
    v3 = v4;
  }
  if ( Path )
    ZwClose((HANDLE)Path);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012664  mov     rax, rsp
0x140012667  mov     [rax+8], rbx
0x14001266b  push    rdi
0x14001266c  sub     rsp, 30h
0x140012670  mov     dil, dl
0x140012673  mov     qword ptr [rax+20h], 0
0x14001267b  mov     edx, 1; DevInstKeyType
0x140012680  lea     r9, [rax+20h]; DeviceRegKey
0x140012684  mov     r8d, 2001Fh; DesiredAccess
0x14001268a  mov     [rax+18h], edx
0x14001268d  call    cs:__imp_IoOpenDeviceRegistryKey
0x140012694  nop     dword ptr [rax+rax+00h]
0x140012699  mov     ebx, eax
0x14001269b  test    eax, eax
0x14001269d  js      short loc_1400126E6
0x14001269f  mov     rdx, [rsp+38h+Path]; Path
0x1400126a4  lea     r8, aIsdeleted; "IsDeleted"
0x1400126ab  mov     ecx, 40000000h; RelativeTo
0x1400126b0  test    dil, dil
0x1400126b3  jz      short loc_1400126D8
0x1400126b5  mov     r9d, 4; ValueType
0x1400126bb  lea     rax, [rsp+38h+arg_10]
0x1400126c0  mov     [rsp+38h+ValueLength], r9d; ValueLength
0x1400126c5  mov     [rsp+38h+ValueData], rax; ValueData
0x1400126ca  call    cs:__imp_RtlWriteRegistryValue
0x1400126d1  nop     dword ptr [rax+rax+00h]
0x1400126d6  jmp     short loc_1400126E4
0x1400126d8  call    cs:__imp_RtlDeleteRegistryValue
0x1400126df  nop     dword ptr [rax+rax+00h]
0x1400126e4  mov     ebx, eax
0x1400126e6  mov     rcx, [rsp+38h+Path]; Handle
0x1400126eb  test    rcx, rcx
0x1400126ee  jz      short loc_1400126FC
0x1400126f0  call    cs:__imp_ZwClose
0x1400126f7  nop     dword ptr [rax+rax+00h]
0x1400126fc  mov     eax, ebx
0x1400126fe  mov     rbx, [rsp+38h+arg_0]
0x140012703  add     rsp, 30h
0x140012707  pop     rdi
0x140012708  retn
```
