# SsWriteDefaultSdToRegistry

- ea: `0x180026768`
- end: `0x1800267bc`
- name: `SsWriteDefaultSdToRegistry`
- size: `84`
- prototype: `BOOLEAN __fastcall(PCWSTR ValueName, PVOID ValueData)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000aa8c`

## callees

- `0x180026768`

## import_xrefs

- `ntdll!RtlWriteRegistryValue` at `0x1800267ab`
- `ntdll!RtlWriteRegistryValue` at `0x1800267ab`
- `ntdll!RtlValidSecurityDescriptor` at `0x18002677b`
- `ntdll!RtlValidSecurityDescriptor` at `0x18002677b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180026788`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180026788`

## string_xrefs

- `0x180026798`: `LanmanServer\DefaultSecurity`

## pseudocode

```c
BOOLEAN __fastcall SsWriteDefaultSdToRegistry(PCWSTR ValueName, PVOID ValueData)
{
  BOOLEAN result; // al
  ULONG ValueLength; // eax

  result = RtlValidSecurityDescriptor(ValueData);
  if ( result )
  {
    ValueLength = RtlLengthSecurityDescriptor(ValueData);
    return RtlWriteRegistryValue(1u, L"LanmanServer\\DefaultSecurity", ValueName, 3u, ValueData, ValueLength);
  }
  return result;
}

```

## disassembly

```asm
0x180026768  mov     [rsp+arg_0], rbx
0x18002676d  push    rdi
0x18002676e  sub     rsp, 30h
0x180026772  mov     rdi, rcx
0x180026775  mov     rbx, rdx
0x180026778  mov     rcx, rdx; SecurityDescriptor
0x18002677b  call    cs:__imp_RtlValidSecurityDescriptor
0x180026781  test    al, al
0x180026783  jz      short loc_1800267B1
0x180026785  mov     rcx, rbx; SecurityDescriptor
0x180026788  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002678e  mov     r9d, 3; ValueType
0x180026794  mov     [rsp+38h+ValueLength], eax; ValueLength
0x180026798  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18002679f  mov     [rsp+38h+ValueData], rbx; ValueData
0x1800267a4  mov     r8, rdi; ValueName
0x1800267a7  lea     ecx, [r9-2]; RelativeTo
0x1800267ab  call    cs:__imp_RtlWriteRegistryValue
0x1800267b1  mov     rbx, [rsp+38h+arg_0]
0x1800267b6  add     rsp, 30h
0x1800267ba  pop     rdi
0x1800267bb  retn
```
