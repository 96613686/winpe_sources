# SetAdminRights

- ea: `0x18001cbe0`
- end: `0x18001cc26`
- name: `SetAdminRights`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012af0`
- `0x18001ca88`

## callees

- `0x18001cbe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc0b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cc01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cc01`

## pseudocode

```c
signed int __fastcall SetAdminRights(__int64 a1)
{
  signed int result; // eax
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptorSize = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;GA;;;BA)",
         1u,
         (PSECURITY_DESCRIPTOR *)(a1 + 8),
         &SecurityDescriptorSize) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001cbe0  sub     rsp, 28h
0x18001cbe4  lea     r8, [rcx+8]; SecurityDescriptor
0x18001cbe8  mov     [rsp+28h+SecurityDescriptorSize], 0
0x18001cbf0  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GA;;;BA)"
0x18001cbf7  mov     edx, 1; StringSDRevision
0x18001cbfc  lea     r9, [rsp+28h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001cc01  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001cc07  test    eax, eax
0x18001cc09  jnz     short loc_18001CC1F
0x18001cc0b  call    cs:__imp_GetLastError
0x18001cc11  test    eax, eax
0x18001cc13  jle     short loc_18001CC21
0x18001cc15  movzx   eax, ax
0x18001cc18  or      eax, 80070000h
0x18001cc1d  jmp     short loc_18001CC21
0x18001cc1f  xor     eax, eax
0x18001cc21  add     rsp, 28h
0x18001cc25  retn
```
