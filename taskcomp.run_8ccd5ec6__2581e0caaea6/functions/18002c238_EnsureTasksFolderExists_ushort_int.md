# EnsureTasksFolderExists(ushort *,int)

- ea: `0x18002c238`
- end: `0x18002c432`
- name: `?EnsureTasksFolderExists@@YAJPEAGH@Z`
- size: `506`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002ca08`
- `0x18002e3cc`

## callees

- `0x18002c0a4`
- `0x18002c238`
- `0x18002ce54`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c3ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c3ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c365`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c365`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c39d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c39d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c267`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c267`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002c2a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002c2a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c2dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c2dc`

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
0x18002c238  mov     [rsp-8+arg_8], rbx
0x18002c23d  mov     [rsp-8+arg_10], rsi
0x18002c242  push    rbp
0x18002c243  push    rdi
0x18002c244  push    r15
0x18002c246  lea     rbp, [rsp-80h]
0x18002c24b  sub     rsp, 180h
0x18002c252  mov     rax, cs:__security_cookie
0x18002c259  xor     rax, rsp
0x18002c25c  mov     [rbp+90h+var_20], rax
0x18002c260  mov     esi, edx
0x18002c262  mov     rdi, rcx
0x18002c265  xor     ebx, ebx
0x18002c267  call    cs:__imp_GetFileAttributesW
0x18002c26e  nop     dword ptr [rax+rax+00h]
0x18002c273  cmp     eax, 0FFFFFFFFh
0x18002c276  jnz     loc_18002C40B
0x18002c27c  xor     edx, edx; Val
0x18002c27e  mov     [rsp+190h+SecurityDescriptor], rbx
0x18002c283  mov     r8d, 118h; Size
0x18002c289  lea     rcx, [rsp+190h+VersionInformation.dwMajorVersion]; void *
0x18002c28e  call    memset_0
0x18002c293  lea     rcx, [rsp+190h+VersionInformation]; lpVersionInformation
0x18002c298  mov     [rsp+190h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002c2a0  call    cs:__imp_GetVersionExW
0x18002c2a7  nop     dword ptr [rax+rax+00h]
0x18002c2ac  test    eax, eax
0x18002c2ae  jnz     short loc_18002C2BA
0x18002c2b0  mov     eax, 80004005h
0x18002c2b5  jmp     loc_18002C40D
0x18002c2ba  cmp     [rbp+90h+var_26], 1
0x18002c2be  lea     rax, aDPAOiciioFaCoA; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;BO)"...
0x18002c2c5  lea     rcx, aDPAOiciioFaCoA_0; "D:P(A;OICIIO;FA;;;CO)(A;;0x1200ab;;;AU)"...
0x18002c2cc  cmovnz  rcx, rax; StringSecurityDescriptor
0x18002c2d0  lea     r8, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x18002c2d5  xor     r9d, r9d; SecurityDescriptorSize
0x18002c2d8  lea     edx, [r9+1]; StringSDRevision
0x18002c2dc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002c2e3  nop     dword ptr [rax+rax+00h]
0x18002c2e8  mov     r15d, 80070000h
0x18002c2ee  test    eax, eax
0x18002c2f0  jnz     short loc_18002C312
0x18002c2f2  call    cs:__imp_GetLastError
0x18002c2f9  nop     dword ptr [rax+rax+00h]
0x18002c2fe  mov     ebx, eax
0x18002c300  test    eax, eax
0x18002c302  jle     short loc_18002C30A
0x18002c304  movzx   ebx, ax
0x18002c307  or      ebx, r15d
0x18002c30a  test    ebx, ebx
0x18002c30c  js      loc_18002C40B
0x18002c312  lea     r8, [rsp+190h+var_170]; int *
0x18002c317  mov     [rsp+190h+var_170], 0
0x18002c31f  mov     edx, 1; int
0x18002c324  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x18002c329  test    eax, eax
0x18002c32b  jz      short loc_18002C339
0x18002c32d  jg      short loc_18002C333
0x18002c32f  mov     ebx, eax
0x18002c331  jmp     short loc_18002C339
0x18002c333  movzx   ebx, ax
0x18002c336  or      ebx, r15d
0x18002c339  test    ebx, ebx
0x18002c33b  js      loc_18002C3FA
0x18002c341  mov     rax, [rsp+190h+SecurityDescriptor]
0x18002c346  lea     rdx, [rsp+190h+SecurityAttributes]; lpSecurityAttributes
0x18002c34b  mov     rcx, rdi; lpPathName
0x18002c34e  mov     [rsp+190h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002c353  mov     qword ptr [rsp+190h+SecurityAttributes.nLength], 18h
0x18002c35c  mov     qword ptr [rsp+190h+SecurityAttributes.bInheritHandle], 0
0x18002c365  call    cs:__imp_CreateDirectoryW
0x18002c36c  nop     dword ptr [rax+rax+00h]
0x18002c371  test    eax, eax
0x18002c373  jnz     short loc_18002C38D
0x18002c375  call    cs:__imp_GetLastError
0x18002c37c  nop     dword ptr [rax+rax+00h]
0x18002c381  mov     ebx, eax
0x18002c383  test    eax, eax
0x18002c385  jle     short loc_18002C38D
0x18002c387  movzx   ebx, ax
0x18002c38a  or      ebx, r15d
0x18002c38d  test    esi, esi
0x18002c38f  jz      short loc_18002C3D3
0x18002c391  test    ebx, ebx
0x18002c393  js      short loc_18002C3D3
0x18002c395  mov     edx, 4; dwFileAttributes
0x18002c39a  mov     rcx, rdi; lpFileName
0x18002c39d  call    cs:__imp_SetFileAttributesW
0x18002c3a4  nop     dword ptr [rax+rax+00h]
0x18002c3a9  test    eax, eax
0x18002c3ab  jnz     short loc_18002C3C9
0x18002c3ad  call    cs:__imp_GetLastError
0x18002c3b4  nop     dword ptr [rax+rax+00h]
0x18002c3b9  mov     ebx, eax
0x18002c3bb  test    eax, eax
0x18002c3bd  jle     short loc_18002C3C5
0x18002c3bf  movzx   ebx, ax
0x18002c3c2  or      ebx, r15d
0x18002c3c5  test    ebx, ebx
0x18002c3c7  js      short loc_18002C3D3
0x18002c3c9  mov     rcx, rdi; unsigned __int16 *
0x18002c3cc  call    ?CreateDesktopIni@@YAJPEBG@Z; CreateDesktopIni(ushort const *)
0x18002c3d1  mov     ebx, eax
0x18002c3d3  cmp     [rsp+190h+var_170], 0
0x18002c3d8  jnz     short loc_18002C3FA
0x18002c3da  xor     r8d, r8d; int *
0x18002c3dd  xor     edx, edx; int
0x18002c3df  call    ?EnablePrivilege@@YAKKHPEAH@Z; EnablePrivilege(ulong,int,int *)
0x18002c3e4  test    eax, eax
0x18002c3e6  jz      short loc_18002C3FA
0x18002c3e8  test    ebx, ebx
0x18002c3ea  js      short loc_18002C3FA
0x18002c3ec  test    eax, eax
0x18002c3ee  jg      short loc_18002C3F4
0x18002c3f0  mov     ebx, eax
0x18002c3f2  jmp     short loc_18002C3FA
0x18002c3f4  movzx   ebx, ax
0x18002c3f7  or      ebx, r15d
0x18002c3fa  mov     rcx, [rsp+190h+SecurityDescriptor]; hMem
0x18002c3ff  call    cs:__imp_LocalFree
0x18002c406  nop     dword ptr [rax+rax+00h]
0x18002c40b  mov     eax, ebx
0x18002c40d  mov     rcx, [rbp+90h+var_20]
0x18002c411  xor     rcx, rsp; StackCookie
0x18002c414  call    __security_check_cookie
0x18002c419  lea     r11, [rsp+190h+var_10]
0x18002c421  mov     rbx, [r11+28h]
0x18002c425  mov     rsi, [r11+30h]
0x18002c429  mov     rsp, r11
0x18002c42c  pop     r15
0x18002c42e  pop     rdi
0x18002c42f  pop     rbp
0x18002c430  retn
```
