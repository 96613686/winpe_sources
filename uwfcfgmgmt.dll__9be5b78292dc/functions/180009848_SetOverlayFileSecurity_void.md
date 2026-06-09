# SetOverlayFileSecurity(void *)

- ea: `0x180009848`
- end: `0x1800098c8`
- name: `?SetOverlayFileSecurity@@YAJPEAX@Z`
- size: `128`
- prototype: `signed int __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006bb0`
- `0x1800098d0`

## callees

- `0x180009848`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x1800098a1`
- `ntdll!NtSetSecurityObject` at `0x1800098a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009876`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009876`

## pseudocode

```c
signed int __fastcall SetOverlayFileSecurity(HANDLE Handle)
{
  signed int result; // eax
  NTSTATUS v3; // ebx
  int v4; // ebx
  ULONG v5; // [rsp+38h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  v5 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;FA;;;SY)(A;;FA;;;BA)", 1u, &SecurityDescriptor, &v5) )
  {
    v3 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
    if ( v3 >= 0 )
      v4 = 0;
    else
      v4 = v3 | 0x10000000;
    LocalFree(SecurityDescriptor);
    return v4;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180009848  mov     rax, rsp
0x18000984b  push    rbx
0x18000984c  sub     rsp, 20h
0x180009850  mov     rbx, rcx
0x180009853  mov     qword ptr [rax+18h], 0
0x18000985b  lea     rcx, StringSecurityDescriptor; "D:(A;;FA;;;SY)(A;;FA;;;BA)"
0x180009862  mov     dword ptr [rax+10h], 0
0x180009869  lea     r9, [rax+10h]; SecurityDescriptorSize
0x18000986d  mov     edx, 1; StringSDRevision
0x180009872  lea     r8, [rax+18h]; SecurityDescriptor
0x180009876  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000987c  test    eax, eax
0x18000987e  jnz     short loc_180009894
0x180009880  call    cs:__imp_GetLastError
0x180009886  test    eax, eax
0x180009888  jle     short loc_1800098C2
0x18000988a  movzx   eax, ax
0x18000988d  or      eax, 80070000h
0x180009892  jmp     short loc_1800098C2
0x180009894  mov     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180009899  mov     edx, 4; SecurityInformation
0x18000989e  mov     rcx, rbx; Handle
0x1800098a1  call    cs:__imp_NtSetSecurityObject
0x1800098a7  mov     ebx, eax
0x1800098a9  test    eax, eax
0x1800098ab  jns     short loc_1800098B3
0x1800098ad  bts     ebx, 1Ch
0x1800098b1  jmp     short loc_1800098B5
0x1800098b3  xor     ebx, ebx
0x1800098b5  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x1800098ba  call    cs:__imp_LocalFree
0x1800098c0  mov     eax, ebx
0x1800098c2  add     rsp, 20h
0x1800098c6  pop     rbx
0x1800098c7  retn
```
