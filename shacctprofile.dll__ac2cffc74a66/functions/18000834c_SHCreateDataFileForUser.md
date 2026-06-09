# SHCreateDataFileForUser

- ea: `0x18000834c`
- end: `0x180008553`
- name: `SHCreateDataFileForUser`
- size: `519`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006730`

## callees

- `0x180002230`
- `0x180005830`
- `0x180005968`
- `0x180007ce8`
- `0x180007f18`
- `0x18000834c`
- `0x18000855c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000849a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000849a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008509`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008525`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008525`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800084f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800084f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008485`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008485`

## pseudocode

```c
__int64 __fastcall SHCreateDataFileForUser(const unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  signed int UserPicturePath; // ebx
  unsigned int v7; // edx
  signed int LastError; // eax
  HANDLE v9; // rax
  signed int v10; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+270h] [rbp+170h] BYREF

  UserPicturePath = -2147024809;
  if ( a3 )
  {
    if ( a2 )
    {
      if ( a1 )
      {
        *a3 = 0;
        UserPicturePath = SHAcctAccountName2DataFileName(a1, StringSecurityDescriptor, (unsigned int)a3);
        if ( UserPicturePath >= 0 )
        {
          UserPicturePath = SHAcctGetUserPicturePath(FileName, v7);
          if ( UserPicturePath >= 0 )
          {
            UserPicturePath = StringCchCatW(FileName, 0x104u, L"\\");
            if ( UserPicturePath >= 0 )
            {
              UserPicturePath = StringCchCatW(FileName, 0x104u, StringSecurityDescriptor);
              if ( UserPicturePath >= 0 )
              {
                UserPicturePath = StringCchCatW(FileName, 0x104u, L".dat");
                if ( UserPicturePath >= 0 )
                {
                  UserPicturePath = SHDeleteDataFileForUser(a1);
                  if ( UserPicturePath >= 0 )
                  {
                    SecurityDescriptor = 0;
                    UserPicturePath = StringCchPrintfW(
                                        StringSecurityDescriptor,
                                        0x100u,
                                        L"D:(A;;FA;;;SY)(A;;FA;;;BA)(A;;FRFWSD;;;%s)",
                                        a2);
                    if ( UserPicturePath >= 0 )
                    {
                      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                              StringSecurityDescriptor,
                              1u,
                              &SecurityDescriptor,
                              0) )
                      {
                        LastError = GetLastError();
                        UserPicturePath = LastError;
                        if ( LastError > 0 )
                          UserPicturePath = (unsigned __int16)LastError | 0x80070000;
                        if ( UserPicturePath >= 0 )
                          UserPicturePath = -2147467259;
                      }
                      if ( UserPicturePath >= 0 )
                      {
                        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
                        *(_QWORD *)&SecurityAttributes.nLength = 24;
                        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                        v9 = CreateFileW(FileName, 2u, 0, &SecurityAttributes, 2u, 0x80u, 0);
                        if ( v9 == (HANDLE)-1LL )
                        {
                          v10 = GetLastError();
                          UserPicturePath = v10;
                          if ( v10 > 0 )
                            UserPicturePath = (unsigned __int16)v10 | 0x80070000;
                          if ( UserPicturePath >= 0 )
                            UserPicturePath = -2147467259;
                        }
                        else
                        {
                          *a3 = v9;
                        }
                        LocalFree(SecurityDescriptor);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)UserPicturePath;
}

```

## disassembly

```asm
0x18000834c  mov     [rsp-8+arg_18], rbx
0x180008351  push    rbp
0x180008352  push    rsi
0x180008353  push    rdi
0x180008354  push    r12
0x180008356  push    r14
0x180008358  lea     rbp, [rsp-390h]
0x180008360  sub     rsp, 490h
0x180008367  mov     rax, cs:__security_cookie
0x18000836e  xor     rax, rsp
0x180008371  mov     [rbp+3B0h+var_30], rax
0x180008378  mov     rsi, r8
0x18000837b  mov     r14, rdx
0x18000837e  mov     rdi, rcx
0x180008381  mov     ebx, 80070057h
0x180008386  test    r8, r8
0x180008389  jz      loc_18000852B
0x18000838f  test    rdx, rdx
0x180008392  jz      loc_18000852B
0x180008398  test    rcx, rcx
0x18000839b  jz      loc_18000852B
0x1800083a1  lea     rdx, [rbp+3B0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800083a8  mov     qword ptr [r8], 0
0x1800083af  call    ?SHAcctAccountName2DataFileName@@YAJPEBGPEAGK@Z; SHAcctAccountName2DataFileName(ushort const *,ushort *,ulong)
0x1800083b4  mov     ebx, eax
0x1800083b6  test    eax, eax
0x1800083b8  js      loc_18000852B
0x1800083be  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x1800083c3  call    ?SHAcctGetUserPicturePath@@YAJPEAGK@Z; SHAcctGetUserPicturePath(ushort *,ulong)
0x1800083c8  mov     ebx, eax
0x1800083ca  test    eax, eax
0x1800083cc  js      loc_18000852B
0x1800083d2  mov     r12d, 104h
0x1800083d8  lea     r8, asc_18000BDF8; "\\"
0x1800083df  mov     edx, r12d; unsigned __int64
0x1800083e2  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x1800083e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800083ec  mov     ebx, eax
0x1800083ee  test    eax, eax
0x1800083f0  js      loc_18000852B
0x1800083f6  lea     r8, [rbp+3B0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800083fd  mov     edx, r12d; unsigned __int64
0x180008400  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x180008405  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000840a  mov     ebx, eax
0x18000840c  test    eax, eax
0x18000840e  js      loc_18000852B
0x180008414  lea     r8, aDat; ".dat"
0x18000841b  mov     edx, r12d; unsigned __int64
0x18000841e  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x180008423  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008428  mov     ebx, eax
0x18000842a  test    eax, eax
0x18000842c  js      loc_18000852B
0x180008432  mov     rcx, rdi
0x180008435  call    SHDeleteDataFileForUser
0x18000843a  mov     ebx, eax
0x18000843c  test    eax, eax
0x18000843e  js      loc_18000852B
0x180008444  mov     r9, r14
0x180008447  mov     [rsp+4B0h+SecurityDescriptor], 0
0x180008450  lea     r8, aDAFaSyAFaBaAFr; "D:(A;;FA;;;SY)(A;;FA;;;BA)(A;;FRFWSD;;;"...
0x180008457  lea     edx, [r12-4]; unsigned __int64
0x18000845c  lea     rcx, [rbp+3B0h+StringSecurityDescriptor]; unsigned __int16 *
0x180008463  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008468  mov     ebx, eax
0x18000846a  test    eax, eax
0x18000846c  js      loc_18000852B
0x180008472  xor     r9d, r9d; SecurityDescriptorSize
0x180008475  lea     r8, [rsp+4B0h+SecurityDescriptor]; SecurityDescriptor
0x18000847a  lea     rcx, [rbp+3B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180008481  lea     edx, [r9+1]; StringSDRevision
0x180008485  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000848b  mov     edi, 80070000h
0x180008490  mov     r14d, 80004005h
0x180008496  test    eax, eax
0x180008498  jnz     short loc_1800084B1
0x18000849a  call    cs:__imp_GetLastError
0x1800084a0  mov     ebx, eax
0x1800084a2  test    eax, eax
0x1800084a4  jle     short loc_1800084AB
0x1800084a6  movzx   ebx, ax
0x1800084a9  or      ebx, edi
0x1800084ab  test    ebx, ebx
0x1800084ad  cmovns  ebx, r14d
0x1800084b1  test    ebx, ebx
0x1800084b3  js      short loc_18000852B
0x1800084b5  mov     rax, [rsp+4B0h+SecurityDescriptor]
0x1800084ba  lea     r9, [rsp+4B0h+SecurityAttributes]; lpSecurityAttributes
0x1800084bf  mov     [rsp+4B0h+hTemplateFile], 0; hTemplateFile
0x1800084c8  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x1800084cd  mov     edx, 2; dwDesiredAccess
0x1800084d2  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800084da  xor     r8d, r8d; dwShareMode
0x1800084dd  mov     [rsp+4B0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800084e2  mov     [rsp+4B0h+dwCreationDisposition], edx; dwCreationDisposition
0x1800084e6  mov     qword ptr [rsp+4B0h+SecurityAttributes.nLength], 18h
0x1800084ef  mov     qword ptr [rsp+4B0h+SecurityAttributes.bInheritHandle], 0
0x1800084f8  call    cs:__imp_CreateFileW
0x1800084fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008502  jz      short loc_180008509
0x180008504  mov     [rsi], rax
0x180008507  jmp     short loc_180008520
0x180008509  call    cs:__imp_GetLastError
0x18000850f  mov     ebx, eax
0x180008511  test    eax, eax
0x180008513  jle     short loc_18000851A
0x180008515  movzx   ebx, ax
0x180008518  or      ebx, edi
0x18000851a  test    ebx, ebx
0x18000851c  cmovns  ebx, r14d
0x180008520  mov     rcx, [rsp+4B0h+SecurityDescriptor]; hMem
0x180008525  call    cs:__imp_LocalFree
0x18000852b  mov     eax, ebx
0x18000852d  mov     rcx, [rbp+3B0h+var_30]
0x180008534  xor     rcx, rsp; StackCookie
0x180008537  call    __security_check_cookie
0x18000853c  mov     rbx, [rsp+4B0h+arg_18]
0x180008544  add     rsp, 490h
0x18000854b  pop     r14
0x18000854d  pop     r12
0x18000854f  pop     rdi
0x180008550  pop     rsi
0x180008551  pop     rbp
0x180008552  retn
```
