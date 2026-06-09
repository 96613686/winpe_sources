# UmpoCopyToTemp

- ea: `0x180011c1c`
- end: `0x180011f44`
- name: `UmpoCopyToTemp`
- size: `808`
- prototype: `__int64 __fastcall(const WCHAR *, wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180012254`

## callees

- `0x180001170`
- `0x18000ab20`
- `0x18000abb0`
- `0x18000f3dc`
- `0x180010070`
- `0x180011c1c`
- `0x180012864`
- `0x180018850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e2d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011e98`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011e98`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011d56`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011d56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011de7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011e6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011de7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011e6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011ec3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011ec3`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180011ef8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180011ef8`
- `RPCRT4!UuidCreate` at `0x180011cd9`
- `RPCRT4!UuidCreate` at `0x180011cd9`
- `RPCRT4!RpcRevertToSelf` at `0x180011e02`
- `RPCRT4!RpcRevertToSelf` at `0x180011e38`
- `RPCRT4!RpcRevertToSelf` at `0x180011e02`
- `RPCRT4!RpcRevertToSelf` at `0x180011e38`
- `RPCRT4!RpcImpersonateClient` at `0x180011dae`
- `RPCRT4!RpcImpersonateClient` at `0x180011dae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011c8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011c8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f11`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180011cc6`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180011cc6`

## pseudocode

```c
__int64 __fastcall UmpoCopyToTemp(const WCHAR *a1, wchar_t *a2)
{
  char v4; // r15
  int v5; // edi
  RPC_STATUS v6; // eax
  DWORD LastError; // ebx
  size_t *v8; // r8
  HANDLE FileW; // rsi
  __int64 v10; // rdi
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszSrc[40]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t psz[264]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Buffer[8192]; // [rsp+2E0h] [rbp+1E0h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, 20);
  v4 = 0;
  Uuid = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:SYG:SYD:P(A;CIOI;GA;;;SY)(A;CIOI;GA;;;CO)(A;CIOI;GA;;;BA)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v5 = 0;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    while ( (unsigned int)GetTempPath2W(260, psz) )
    {
      v6 = UuidCreate(&Uuid);
      LastError = v6;
      if ( v6 && v6 != 1824 )
        goto LABEL_38;
      UmpoInternalConvertGuidToStringBuffer(&Uuid, pszSrc);
      pcchLength = 0;
      if ( StringLengthWorkerW(psz, 0x104u, &pcchLength) < 0
        || StringCopyWorkerW(&psz[pcchLength], 260 - pcchLength, v8, pszSrc, 0x7FFFFFFEu) < 0 )
      {
        LastError = 87;
        goto LABEL_38;
      }
      if ( CreateDirectoryW(psz, &SecurityAttributes) )
      {
        v4 = 1;
LABEL_13:
        if ( StringCchPrintfW(a2, 0x104u, L"%s\\import.regf", psz) < 0 )
        {
          LastError = 87;
          goto LABEL_35;
        }
        LastError = RpcImpersonateClient(0);
        if ( !LastError )
        {
          FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            v10 = -1;
          }
          else
          {
            if ( RpcRevertToSelf() )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v10 = (__int64)CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
            if ( v10 != -1 )
            {
              while ( ReadFile(FileW, Buffer, 0x1000u, &NumberOfBytesRead, 0)
                   && WriteFile((HANDLE)v10, Buffer, NumberOfBytesRead, &NumberOfBytesWritten, 0) )
              {
                if ( NumberOfBytesRead != 4096 )
                  goto LABEL_19;
              }
            }
          }
          GetLastError();
LABEL_19:
          LastError = RpcRevertToSelf();
          if ( LastError )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( FileW != (HANDLE)-1LL )
            CloseHandle(FileW);
          if ( v10 != -1 )
            CloseHandle((HANDLE)v10);
          goto LABEL_34;
        }
        goto LABEL_35;
      }
      LastError = GetLastError();
      if ( LastError != 183 )
        goto LABEL_34;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)++v5 >= 2 )
        goto LABEL_13;
    }
  }
  LastError = GetLastError();
LABEL_34:
  if ( LastError )
  {
LABEL_35:
    if ( v4 && !RemoveDirectoryW(psz) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_38:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x180011c1c  mov     [rsp-8+arg_10], rbx
0x180011c21  mov     [rsp-8+arg_18], rsi
0x180011c26  push    rbp
0x180011c27  push    rdi
0x180011c28  push    r13
0x180011c2a  push    r14
0x180011c2c  push    r15
0x180011c2e  lea     rbp, [rsp-21F0h]
0x180011c36  mov     eax, 22F0h
0x180011c3b  call    _alloca_probe
0x180011c40  sub     rsp, rax
0x180011c43  mov     rax, cs:__security_cookie
0x180011c4a  xor     rax, rsp
0x180011c4d  mov     [rbp+2210h+var_30], rax
0x180011c54  xor     eax, eax
0x180011c56  lea     r8, [rsp+2310h+SecurityDescriptor]; SecurityDescriptor
0x180011c5b  xorps   xmm0, xmm0
0x180011c5e  mov     [rsp+2310h+SecurityAttributes.bInheritHandle], eax
0x180011c62  mov     r14, rdx
0x180011c65  mov     [rsp+2310h+NumberOfBytesRead], eax
0x180011c69  mov     rsi, rcx
0x180011c6c  mov     [rsp+2310h+NumberOfBytesWritten], eax
0x180011c70  lea     edx, [rax+1]; StringSDRevision
0x180011c73  mov     [rsp+2310h+SecurityDescriptor], rax
0x180011c78  xor     r9d, r9d; SecurityDescriptorSize
0x180011c7b  lea     rcx, aOSygSydPACioiG; "O:SYG:SYD:P(A;CIOI;GA;;;SY)(A;CIOI;GA;;"...
0x180011c82  movups  xmmword ptr [rsp+2310h+SecurityAttributes.nLength], xmm0
0x180011c87  xor     r15b, r15b
0x180011c8a  movups  xmmword ptr [rsp+2310h+Uuid.Data1], xmm0
0x180011c8f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180011c95  test    eax, eax
0x180011c97  jz      loc_180011EE3
0x180011c9d  mov     rax, [rsp+2310h+SecurityDescriptor]
0x180011ca2  xor     edi, edi
0x180011ca4  mov     [rsp+2310h+SecurityAttributes.lpSecurityDescriptor], rax
0x180011ca9  mov     r13d, 104h
0x180011caf  mov     [rsp+2310h+SecurityAttributes.nLength], 18h
0x180011cb7  mov     [rsp+2310h+SecurityAttributes.bInheritHandle], 0
0x180011cbf  lea     rdx, [rbp+2210h+psz]
0x180011cc3  mov     ecx, r13d
0x180011cc6  call    cs:__imp_GetTempPath2W
0x180011ccc  test    eax, eax
0x180011cce  jz      loc_180011EE3
0x180011cd4  lea     rcx, [rsp+2310h+Uuid]; Uuid
0x180011cd9  call    cs:__imp_UuidCreate
0x180011cdf  mov     ebx, eax
0x180011ce1  test    eax, eax
0x180011ce3  jz      short loc_180011CF0
0x180011ce5  cmp     eax, 720h
0x180011cea  jnz     loc_180011F07
0x180011cf0  lea     rdx, [rbp+2210h+pszSrc]
0x180011cf4  lea     rcx, [rsp+2310h+Uuid]
0x180011cf9  call    UmpoInternalConvertGuidToStringBuffer
0x180011cfe  lea     r8, [rsp+2310h+pcchLength]; pcchLength
0x180011d03  mov     [rsp+2310h+pcchLength], 0
0x180011d0c  lea     rcx, [rbp+2210h+psz]; psz
0x180011d10  mov     rdx, r13; cchMax
0x180011d13  call    StringLengthWorkerW
0x180011d18  test    eax, eax
0x180011d1a  js      loc_180011EDC
0x180011d20  mov     rax, [rsp+2310h+pcchLength]
0x180011d25  lea     rcx, [rbp+2210h+psz]
0x180011d29  mov     rdx, r13
0x180011d2c  mov     [rsp+2310h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180011d35  sub     rdx, rax; cchDest
0x180011d38  lea     r9, [rbp+2210h+pszSrc]; pszSrc
0x180011d3c  lea     rcx, [rcx+rax*2]; pszDest
0x180011d40  call    StringCopyWorkerW
0x180011d45  test    eax, eax
0x180011d47  js      loc_180011EDC
0x180011d4d  lea     rdx, [rsp+2310h+SecurityAttributes]; lpSecurityAttributes
0x180011d52  lea     rcx, [rbp+2210h+psz]; lpPathName
0x180011d56  call    cs:__imp_CreateDirectoryW
0x180011d5c  test    eax, eax
0x180011d5e  jnz     short loc_180011D85
0x180011d60  call    cs:__imp_GetLastError
0x180011d66  mov     ebx, eax
0x180011d68  cmp     eax, 0B7h
0x180011d6d  jnz     loc_180011EEB
0x180011d73  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011d78  inc     edi
0x180011d7a  cmp     edi, 2
0x180011d7d  jb      loc_180011CBF
0x180011d83  jmp     short loc_180011D88
0x180011d85  mov     r15b, 1
0x180011d88  lea     r9, [rbp+2210h+psz]
0x180011d8c  mov     rdx, r13; cchDest
0x180011d8f  lea     r8, aSImportRegf; "%s\\import.regf"
0x180011d96  mov     rcx, r14; pszDest
0x180011d99  call    StringCchPrintfW
0x180011d9e  test    eax, eax
0x180011da0  jns     short loc_180011DAC
0x180011da2  mov     ebx, 57h ; 'W'
0x180011da7  jmp     loc_180011EEF
0x180011dac  xor     ecx, ecx; BindingHandle
0x180011dae  call    cs:__imp_RpcImpersonateClient
0x180011db4  mov     ebx, eax
0x180011db6  test    eax, eax
0x180011db8  jnz     loc_180011EEF
0x180011dbe  mov     [rsp+2310h+hTemplateFile], 0; hTemplateFile
0x180011dc7  lea     r8d, [rax+1]; dwShareMode
0x180011dcb  mov     ebx, 80h
0x180011dd0  xor     r9d, r9d; lpSecurityAttributes
0x180011dd3  mov     [rsp+2310h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180011dd7  mov     edx, 80000000h; dwDesiredAccess
0x180011ddc  mov     rcx, rsi; lpFileName
0x180011ddf  mov     dword ptr [rsp+2310h+cchToCopy], 3; dwCreationDisposition
0x180011de7  call    cs:__imp_CreateFileW
0x180011ded  or      r13, 0FFFFFFFFFFFFFFFFh
0x180011df1  mov     rsi, rax
0x180011df4  cmp     rax, r13
0x180011df7  jnz     short loc_180011E38
0x180011df9  mov     rdi, r13
0x180011dfc  call    cs:__imp_GetLastError
0x180011e02  call    cs:__imp_RpcRevertToSelf
0x180011e08  mov     ebx, eax
0x180011e0a  test    eax, eax
0x180011e0c  jz      short loc_180011E13
0x180011e0e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011e13  cmp     rsi, r13
0x180011e16  jz      short loc_180011E21
0x180011e18  mov     rcx, rsi; hObject
0x180011e1b  call    cs:__imp_CloseHandle
0x180011e21  cmp     rdi, r13
0x180011e24  jz      loc_180011EEB
0x180011e2a  mov     rcx, rdi; hObject
0x180011e2d  call    cs:__imp_CloseHandle
0x180011e33  jmp     loc_180011EEB
0x180011e38  call    cs:__imp_RpcRevertToSelf
0x180011e3e  test    eax, eax
0x180011e40  jz      short loc_180011E47
0x180011e42  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011e47  mov     [rsp+2310h+hTemplateFile], 0; hTemplateFile
0x180011e50  xor     r9d, r9d; lpSecurityAttributes
0x180011e53  mov     [rsp+2310h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180011e57  xor     r8d, r8d; dwShareMode
0x180011e5a  mov     edx, 40000000h; dwDesiredAccess
0x180011e5f  mov     dword ptr [rsp+2310h+cchToCopy], 2; dwCreationDisposition
0x180011e67  mov     rcx, r14; lpFileName
0x180011e6a  call    cs:__imp_CreateFileW
0x180011e70  mov     rdi, rax
0x180011e73  cmp     rax, r13
0x180011e76  jz      short loc_180011DFC
0x180011e78  mov     ebx, 1000h
0x180011e7d  lea     r9, [rsp+2310h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180011e82  mov     [rsp+2310h+cchToCopy], 0; lpOverlapped
0x180011e8b  mov     r8d, ebx; nNumberOfBytesToRead
0x180011e8e  lea     rdx, [rbp+2210h+Buffer]; lpBuffer
0x180011e95  mov     rcx, rsi; hFile
0x180011e98  call    cs:__imp_ReadFile
0x180011e9e  test    eax, eax
0x180011ea0  jz      loc_180011DFC
0x180011ea6  mov     r8d, [rsp+2310h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x180011eab  lea     r9, [rsp+2310h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180011eb0  lea     rdx, [rbp+2210h+Buffer]; lpBuffer
0x180011eb7  mov     [rsp+2310h+cchToCopy], 0; lpOverlapped
0x180011ec0  mov     rcx, rdi; hFile
0x180011ec3  call    cs:__imp_WriteFile
0x180011ec9  test    eax, eax
0x180011ecb  jz      loc_180011DFC
0x180011ed1  cmp     [rsp+2310h+NumberOfBytesRead], ebx
0x180011ed5  jz      short loc_180011E7D
0x180011ed7  jmp     loc_180011E02
0x180011edc  mov     ebx, 57h ; 'W'
0x180011ee1  jmp     short loc_180011F07
0x180011ee3  call    cs:__imp_GetLastError
0x180011ee9  mov     ebx, eax
0x180011eeb  test    ebx, ebx
0x180011eed  jz      short loc_180011F07
0x180011eef  test    r15b, r15b
0x180011ef2  jz      short loc_180011F07
0x180011ef4  lea     rcx, [rbp+2210h+psz]; lpPathName
0x180011ef8  call    cs:__imp_RemoveDirectoryW
0x180011efe  test    eax, eax
0x180011f00  jnz     short loc_180011F07
0x180011f02  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011f07  mov     rcx, [rsp+2310h+SecurityDescriptor]; hMem
0x180011f0c  test    rcx, rcx
0x180011f0f  jz      short loc_180011F17
0x180011f11  call    cs:__imp_LocalFree
0x180011f17  mov     eax, ebx
0x180011f19  mov     rcx, [rbp+2210h+var_30]
0x180011f20  xor     rcx, rsp; StackCookie
0x180011f23  call    __security_check_cookie
0x180011f28  lea     r11, [rsp+2310h+var_20]
0x180011f30  mov     rbx, [r11+40h]
0x180011f34  mov     rsi, [r11+48h]
0x180011f38  mov     rsp, r11
0x180011f3b  pop     r15
0x180011f3d  pop     r14
0x180011f3f  pop     r13
0x180011f41  pop     rdi
0x180011f42  pop     rbp
0x180011f43  retn
```
