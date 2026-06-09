# _SetDeletePrivilegeOnFile(ushort const *,void *)

- ea: `0x180007fc4`
- end: `0x180008102`
- name: `?_SetDeletePrivilegeOnFile@@YAJPEBGPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180008108`

## callees

- `0x180002230`
- `0x180005968`
- `0x180007fc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080c0`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000805e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000805e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000808c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800080b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000808c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800080b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008047`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008047`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007ffa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007ffa`

## pseudocode

```c
__int64 __fastcall _SetDeletePrivilegeOnFile(LPCWSTR lpFileName, PSID Sid)
{
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-238h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-230h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+30h] [rbp-228h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v3 = StringCchPrintfW(StringSecurityDescriptor, 0x104u, L"D:(A;;FA;;;%s)", StringSid);
    if ( v3 >= 0 )
    {
      SecurityDescriptor = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      {
        if ( !SetFileSecurityW(lpFileName, 4u, SecurityDescriptor) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2147467259;
        }
        LocalFree(SecurityDescriptor);
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
      }
    }
    LocalFree(StringSid);
  }
  else
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( v3 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007fc4  mov     [rsp+arg_10], rbx
0x180007fc9  push    rdi
0x180007fca  sub     rsp, 250h
0x180007fd1  mov     rax, cs:__security_cookie
0x180007fd8  xor     rax, rsp
0x180007fdb  mov     [rsp+258h+var_18], rax
0x180007fe3  mov     rax, rdx
0x180007fe6  mov     [rsp+258h+StringSid], 0
0x180007fef  mov     rdi, rcx
0x180007ff2  lea     rdx, [rsp+258h+StringSid]; StringSid
0x180007ff7  mov     rcx, rax; Sid
0x180007ffa  call    cs:__imp_ConvertSidToStringSidW
0x180008000  test    eax, eax
0x180008002  jz      loc_1800080C0
0x180008008  mov     r9, [rsp+258h+StringSid]
0x18000800d  lea     r8, aDAFaS; "D:(A;;FA;;;%s)"
0x180008014  mov     edx, 104h; unsigned __int64
0x180008019  lea     rcx, [rsp+258h+StringSecurityDescriptor]; unsigned __int16 *
0x18000801e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008023  mov     ebx, eax
0x180008025  test    eax, eax
0x180008027  js      loc_1800080B3
0x18000802d  xor     r9d, r9d; SecurityDescriptorSize
0x180008030  mov     [rsp+258h+SecurityDescriptor], 0
0x180008039  lea     r8, [rsp+258h+SecurityDescriptor]; SecurityDescriptor
0x18000803e  lea     rcx, [rsp+258h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180008043  lea     edx, [r9+1]; StringSDRevision
0x180008047  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000804d  test    eax, eax
0x18000804f  jz      short loc_180008094
0x180008051  mov     r8, [rsp+258h+SecurityDescriptor]; pSecurityDescriptor
0x180008056  mov     edx, 4; SecurityInformation
0x18000805b  mov     rcx, rdi; lpFileName
0x18000805e  call    cs:__imp_SetFileSecurityW
0x180008064  test    eax, eax
0x180008066  jnz     short loc_180008087
0x180008068  call    cs:__imp_GetLastError
0x18000806e  mov     ebx, eax
0x180008070  test    eax, eax
0x180008072  jle     short loc_18000807D
0x180008074  movzx   ebx, ax
0x180008077  or      ebx, 80070000h
0x18000807d  test    ebx, ebx
0x18000807f  mov     eax, 80004005h
0x180008084  cmovns  ebx, eax
0x180008087  mov     rcx, [rsp+258h+SecurityDescriptor]; hMem
0x18000808c  call    cs:__imp_LocalFree
0x180008092  jmp     short loc_1800080B3
0x180008094  call    cs:__imp_GetLastError
0x18000809a  mov     ebx, eax
0x18000809c  test    eax, eax
0x18000809e  jle     short loc_1800080A9
0x1800080a0  movzx   ebx, ax
0x1800080a3  or      ebx, 80070000h
0x1800080a9  test    ebx, ebx
0x1800080ab  mov     eax, 80004005h
0x1800080b0  cmovns  ebx, eax
0x1800080b3  mov     rcx, [rsp+258h+StringSid]; hMem
0x1800080b8  call    cs:__imp_LocalFree
0x1800080be  jmp     short loc_1800080DF
0x1800080c0  call    cs:__imp_GetLastError
0x1800080c6  mov     ebx, eax
0x1800080c8  test    eax, eax
0x1800080ca  jle     short loc_1800080D5
0x1800080cc  movzx   ebx, ax
0x1800080cf  or      ebx, 80070000h
0x1800080d5  test    ebx, ebx
0x1800080d7  mov     eax, 80004005h
0x1800080dc  cmovns  ebx, eax
0x1800080df  mov     eax, ebx
0x1800080e1  mov     rcx, [rsp+258h+var_18]
0x1800080e9  xor     rcx, rsp; StackCookie
0x1800080ec  call    __security_check_cookie
0x1800080f1  mov     rbx, [rsp+258h+arg_10]
0x1800080f9  add     rsp, 250h
0x180008100  pop     rdi
0x180008101  retn
```
