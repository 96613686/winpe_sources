# EnsureTasksFolderExists(ushort *,int)

- ea: `0x18002a734`
- end: `0x18002a8f7`
- name: `?EnsureTasksFolderExists@@YAJPEAGH@Z`
- size: `451`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002ae64`
- `0x18002c5d4`

## callees

- `0x18002a5c0`
- `0x18002a734`
- `0x18002b23c`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a87f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8cb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a849`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a849`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a875`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a875`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a763`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a763`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002a796`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002a796`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a7cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a7cc`

## pseudocode

```c
__int64 __fastcall EnsureTasksFolderExists(unsigned __int16 *a1, int a2)
{
  signed int DesktopIni; // ebx
  const WCHAR *v6; // rcx
  unsigned int v7; // ecx
  signed int LastError; // eax
  int v9; // eax
  unsigned int v10; // ecx
  signed int v11; // eax
  signed int v12; // eax
  int v13; // eax
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-D8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-D0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+16Ah] [rbp+6Ah]

  DesktopIni = 0;
  if ( GetFileAttributesW(a1) == -1 )
  {
    SecurityDescriptor = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
      return 2147500037LL;
    v6 = L"D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;AU)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)S:(AU;SAFAOICI;FWDCSDWDWO;;;WD)(AU;SAFAO"
          "ICI;FWDCSDWDWO;;;AN)";
    if ( v18 != 1 )
      v6 = L"D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;BO)(A;;0x1200ab;;;SO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)S:(AU;SAFAOICI;FWDCS"
            "DWDWO;;;WD)(AU;SAFAOICI;FWDCSDWDWO;;;AN)";
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
      goto LABEL_10;
    LastError = GetLastError();
    DesktopIni = LastError;
    if ( LastError > 0 )
      DesktopIni = (unsigned __int16)LastError | 0x80070000;
    if ( DesktopIni >= 0 )
    {
LABEL_10:
      v14 = 0;
      v9 = EnablePrivilege(v7, 1, &v14);
      if ( v9 )
      {
        if ( v9 > 0 )
          DesktopIni = (unsigned __int16)v9 | 0x80070000;
        else
          DesktopIni = v9;
      }
      if ( DesktopIni >= 0 )
      {
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        *(_QWORD *)&SecurityAttributes.nLength = 24;
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
        if ( !CreateDirectoryW(a1, &SecurityAttributes) )
        {
          v11 = GetLastError();
          DesktopIni = v11;
          if ( v11 > 0 )
            DesktopIni = (unsigned __int16)v11 | 0x80070000;
        }
        if ( a2 && DesktopIni >= 0 )
        {
          if ( SetFileAttributesW(a1, 4u) )
            goto LABEL_24;
          v12 = GetLastError();
          DesktopIni = v12;
          if ( v12 > 0 )
            DesktopIni = (unsigned __int16)v12 | 0x80070000;
          if ( DesktopIni >= 0 )
LABEL_24:
            DesktopIni = CreateDesktopIni(a1);
        }
        if ( !v14 )
        {
          v13 = EnablePrivilege(v10, 0, 0);
          if ( v13 )
          {
            if ( DesktopIni >= 0 )
            {
              if ( v13 > 0 )
                DesktopIni = (unsigned __int16)v13 | 0x80070000;
              else
                DesktopIni = v13;
            }
          }
        }
      }
      LocalFree(SecurityDescriptor);
    }
  }
  return (unsigned int)DesktopIni;
}

```

## disassembly

```asm
0x18002a734  mov     [rsp-8+arg_8], rbx
0x18002a739  mov     [rsp-8+arg_10], rsi
0x18002a73e  push    rbp
0x18002a73f  push    rdi
0x18002a740  push    r15
0x18002a742  lea     rbp, [rsp-80h]
0x18002a747  sub     rsp, 180h
0x18002a74e  mov     rax, cs:__security_cookie
0x18002a755  xor     rax, rsp
0x18002a758  mov     [rbp+90h+var_20], rax
0x18002a75c  mov     esi, edx
0x18002a75e  mov     rdi, rcx
0x18002a761  xor     ebx, ebx
0x18002a763  call    cs:__imp_GetFileAttributesW
0x18002a769  cmp     eax, 0FFFFFFFFh
0x18002a76c  jnz     loc_18002A8D1
0x18002a772  xor     edx, edx; Val
0x18002a774  mov     [rsp+190h+SecurityDescriptor], rbx
0x18002a779  mov     r8d, 118h; Size
0x18002a77f  lea     rcx, [rsp+190h+VersionInformation.dwMajorVersion]; void *
0x18002a784  call    memset_0
0x18002a789  lea     rcx, [rsp+190h+VersionInformation]; lpVersionInformation
0x18002a78e  mov     [rsp+190h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002a796  call    cs:__imp_GetVersionExW
0x18002a79c  test    eax, eax
0x18002a79e  jnz     short loc_18002A7AA
0x18002a7a0  mov     eax, 80004005h
0x18002a7a5  jmp     loc_18002A8D3
0x18002a7aa  cmp     [rbp+90h+var_26], 1
0x18002a7ae  lea     rax, aDPAOiciioFaCoA; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;BO)"...
0x18002a7b5  lea     rcx, aDPAOiciioFaCoA_0; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;AU)"...
0x18002a7bc  cmovnz  rcx, rax; StringSecurityDescriptor
0x18002a7c0  lea     r8, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x18002a7c5  xor     r9d, r9d; SecurityDescriptorSize
0x18002a7c8  lea     edx, [r9+1]; StringSDRevision
0x18002a7cc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002a7d2  mov     r15d, 80070000h
0x18002a7d8  test    eax, eax
0x18002a7da  jnz     short loc_18002A7F6
0x18002a7dc  call    cs:__imp_GetLastError
0x18002a7e2  mov     ebx, eax
0x18002a7e4  test    eax, eax
0x18002a7e6  jle     short loc_18002A7EE
0x18002a7e8  movzx   ebx, ax
0x18002a7eb  or      ebx, r15d
0x18002a7ee  test    ebx, ebx
0x18002a7f0  js      loc_18002A8D1
0x18002a7f6  lea     r8, [rsp+190h+var_170]; int *
0x18002a7fb  mov     [rsp+190h+var_170], 0
0x18002a803  mov     edx, 1; int
0x18002a808  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x18002a80d  test    eax, eax
0x18002a80f  jz      short loc_18002A81D
0x18002a811  jg      short loc_18002A817
0x18002a813  mov     ebx, eax
0x18002a815  jmp     short loc_18002A81D
0x18002a817  movzx   ebx, ax
0x18002a81a  or      ebx, r15d
0x18002a81d  test    ebx, ebx
0x18002a81f  js      loc_18002A8C6
0x18002a825  mov     rax, [rsp+190h+SecurityDescriptor]
0x18002a82a  lea     rdx, [rsp+190h+SecurityAttributes]; lpSecurityAttributes
0x18002a82f  mov     rcx, rdi; lpPathName
0x18002a832  mov     [rsp+190h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002a837  mov     qword ptr [rsp+190h+SecurityAttributes.nLength], 18h
0x18002a840  mov     qword ptr [rsp+190h+SecurityAttributes.bInheritHandle], 0
0x18002a849  call    cs:__imp_CreateDirectoryW
0x18002a84f  test    eax, eax
0x18002a851  jnz     short loc_18002A865
0x18002a853  call    cs:__imp_GetLastError
0x18002a859  mov     ebx, eax
0x18002a85b  test    eax, eax
0x18002a85d  jle     short loc_18002A865
0x18002a85f  movzx   ebx, ax
0x18002a862  or      ebx, r15d
0x18002a865  test    esi, esi
0x18002a867  jz      short loc_18002A89F
0x18002a869  test    ebx, ebx
0x18002a86b  js      short loc_18002A89F
0x18002a86d  mov     edx, 4; dwFileAttributes
0x18002a872  mov     rcx, rdi; lpFileName
0x18002a875  call    cs:__imp_SetFileAttributesW
0x18002a87b  test    eax, eax
0x18002a87d  jnz     short loc_18002A895
0x18002a87f  call    cs:__imp_GetLastError
0x18002a885  mov     ebx, eax
0x18002a887  test    eax, eax
0x18002a889  jle     short loc_18002A891
0x18002a88b  movzx   ebx, ax
0x18002a88e  or      ebx, r15d
0x18002a891  test    ebx, ebx
0x18002a893  js      short loc_18002A89F
0x18002a895  mov     rcx, rdi; unsigned __int16 *
0x18002a898  call    ?CreateDesktopIni@@YAJPEBG@Z; CreateDesktopIni(ushort const *)
0x18002a89d  mov     ebx, eax
0x18002a89f  cmp     [rsp+190h+var_170], 0
0x18002a8a4  jnz     short loc_18002A8C6
0x18002a8a6  xor     r8d, r8d; int *
0x18002a8a9  xor     edx, edx; int
0x18002a8ab  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x18002a8b0  test    eax, eax
0x18002a8b2  jz      short loc_18002A8C6
0x18002a8b4  test    ebx, ebx
0x18002a8b6  js      short loc_18002A8C6
0x18002a8b8  test    eax, eax
0x18002a8ba  jg      short loc_18002A8C0
0x18002a8bc  mov     ebx, eax
0x18002a8be  jmp     short loc_18002A8C6
0x18002a8c0  movzx   ebx, ax
0x18002a8c3  or      ebx, r15d
0x18002a8c6  mov     rcx, [rsp+190h+SecurityDescriptor]; hMem
0x18002a8cb  call    cs:__imp_LocalFree
0x18002a8d1  mov     eax, ebx
0x18002a8d3  mov     rcx, [rbp+90h+var_20]
0x18002a8d7  xor     rcx, rsp; StackCookie
0x18002a8da  call    __security_check_cookie
0x18002a8df  lea     r11, [rsp+190h+var_10]
0x18002a8e7  mov     rbx, [r11+28h]
0x18002a8eb  mov     rsi, [r11+30h]
0x18002a8ef  mov     rsp, r11
0x18002a8f2  pop     r15
0x18002a8f4  pop     rdi
0x18002a8f5  pop     rbp
0x18002a8f6  retn
```
