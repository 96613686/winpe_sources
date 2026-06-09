# WerpCreateReportDirectory

- ea: `0x14000e260`
- end: `0x14000e45b`
- name: `WerpCreateReportDirectory`
- size: `507`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000dc94`

## callees

- `0x140001ab8`
- `0x140002750`
- `0x140002c40`
- `0x14000e260`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e346`
- `ntoskrnl!DbgPrintEx` at `0x14000e346`
- `ntoskrnl!ZwClose` at `0x14000e41f`
- `ntoskrnl!ZwClose` at `0x14000e41f`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e37c`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e37c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e2fb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e2fb`
- `ntoskrnl!IoCreateFile` at `0x14000e409`
- `ntoskrnl!IoCreateFile` at `0x14000e409`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e35b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e35b`

## string_xrefs

- `0x14000e33c`: `WERKERNELHOST: Failed to initialize report directory ReportType, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall WerpCreateReportDirectory(__int64 a1)
{
  NTSTATUS v2; // ebx
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v11; // [rsp+E8h] [rbp-18h]
  _DWORD Owner[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v13[528]; // [rsp+100h] [rbp+0h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(v13, 0, 0x208u);
  Owner[0] = 257;
  Owner[1] = 83886080;
  *(_QWORD *)&DestinationString.Length = 34078720;
  v11 = 0;
  Owner[2] = 18;
  DestinationString.Buffer = (PWSTR)v13;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  RtlCopyUnicodeString(&DestinationString, &WerKernelLiveReportRootPath);
  v2 = RtlUnicodeStringCatString(&DestinationString, L"\\");
  if ( v2 >= 0 )
  {
    v3 = RtlUnicodeStringCatString(&DestinationString, (NTSTRSAFE_PCWSTR)(a1 + 24));
    v2 = v3;
    if ( v3 >= 0 )
    {
      v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v2 >= 0 )
      {
        v2 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
        if ( v2 >= 0 )
        {
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
          ObjectAttributes.SecurityQualityOfService = 0;
          v4 = IoCreateFile(
                 &FileHandle,
                 0x10000000u,
                 &ObjectAttributes,
                 &IoStatusBlock,
                 0,
                 0x80u,
                 3u,
                 2u,
                 1u,
                 0,
                 0,
                 CreateFileTypeNone,
                 0,
                 0x100u);
          v2 = v4;
          if ( v4 < 0 )
          {
            if ( v4 == -1073741771 || IoStatusBlock.Information == 4 )
              return 0;
          }
          else
          {
            ZwClose(FileHandle);
          }
        }
      }
    }
    else
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Failed to initialize report directory ReportType, status 0x%X\n", v3);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000e260  push    rbp
0x14000e262  push    rbx
0x14000e263  push    rsi
0x14000e264  push    rdi
0x14000e265  lea     rbp, [rsp-228h]
0x14000e26d  sub     rsp, 328h
0x14000e274  mov     rax, cs:__security_cookie
0x14000e27b  xor     rax, rsp
0x14000e27e  mov     [rbp+240h+var_30], rax
0x14000e285  xorps   xmm0, xmm0
0x14000e288  mov     rdi, rcx
0x14000e28b  movups  xmmword ptr [rbp+240h+ObjectAttributes.ObjectName], xmm0
0x14000e28f  mov     ebx, 208h
0x14000e294  lea     rcx, [rbp+240h+var_240]; void *
0x14000e298  xor     esi, esi
0x14000e29a  mov     r8d, ebx; Size
0x14000e29d  xor     eax, eax
0x14000e29f  mov     [rbp+240h+FileHandle], rsi
0x14000e2a3  xor     edx, edx; Val
0x14000e2a5  movups  xmmword ptr [rbp+240h+ObjectAttributes+1Ch], xmm0
0x14000e2a9  movups  xmmword ptr [rbp+240h+IoStatusBlock], xmm0
0x14000e2ad  movups  xmmword ptr [rbp+240h+ObjectAttributes.Length], xmm0
0x14000e2b1  call    memset
0x14000e2b6  xorps   xmm0, xmm0
0x14000e2b9  mov     [rbp+240h+Owner], 101h
0x14000e2c0  xor     eax, eax
0x14000e2c2  mov     [rbp+240h+var_24C], 5000000h
0x14000e2c9  movups  xmmword ptr [rsp+340h+DestinationString.Length], xmm0
0x14000e2ce  mov     [rbp+240h+var_258], rax
0x14000e2d2  lea     rdx, WerKernelLiveReportRootPath; SourceString
0x14000e2d9  lea     rax, [rbp+240h+var_240]
0x14000e2dd  mov     [rbp+240h+var_248], 12h
0x14000e2e4  lea     rcx, [rsp+340h+DestinationString]; DestinationString
0x14000e2e9  mov     [rsp+340h+DestinationString.Buffer], rax
0x14000e2ee  movups  [rbp+240h+SecurityDescriptor], xmm0
0x14000e2f2  mov     [rsp+340h+DestinationString.MaximumLength], bx
0x14000e2f7  movups  [rbp+240h+var_268], xmm0
0x14000e2fb  call    cs:__imp_RtlCopyUnicodeString
0x14000e302  nop     dword ptr [rax+rax+00h]
0x14000e307  lea     rdx, pszSrc; "\\"
0x14000e30e  lea     rcx, [rsp+340h+DestinationString]; DestinationString
0x14000e313  call    RtlUnicodeStringCatString
0x14000e318  mov     ebx, eax
0x14000e31a  test    eax, eax
0x14000e31c  js      loc_14000E43D
0x14000e322  lea     rdx, [rdi+18h]; pszSrc
0x14000e326  lea     rcx, [rsp+340h+DestinationString]; DestinationString
0x14000e32b  call    RtlUnicodeStringCatString
0x14000e330  lea     edx, [rsi+1]; Revision
0x14000e333  mov     ebx, eax
0x14000e335  test    eax, eax
0x14000e337  jns     short loc_14000E357
0x14000e339  mov     r9d, eax
0x14000e33c  lea     r8, aWerkernelhostF_5; "WERKERNELHOST: Failed to initialize rep"...
0x14000e343  lea     ecx, [rsi+5]; ComponentId
0x14000e346  call    cs:__imp_DbgPrintEx
0x14000e34d  nop     dword ptr [rax+rax+00h]
0x14000e352  jmp     loc_14000E43D
0x14000e357  lea     rcx, [rbp+240h+SecurityDescriptor]; SecurityDescriptor
0x14000e35b  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000e362  nop     dword ptr [rax+rax+00h]
0x14000e367  mov     ebx, eax
0x14000e369  test    eax, eax
0x14000e36b  js      loc_14000E43D
0x14000e371  xor     r8d, r8d; OwnerDefaulted
0x14000e374  lea     rdx, [rbp+240h+Owner]; Owner
0x14000e378  lea     rcx, [rbp+240h+SecurityDescriptor]; SecurityDescriptor
0x14000e37c  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000e383  nop     dword ptr [rax+rax+00h]
0x14000e388  mov     ebx, eax
0x14000e38a  test    eax, eax
0x14000e38c  js      loc_14000E43D
0x14000e392  mov     [rsp+340h+Options], 100h; Options
0x14000e39a  lea     rax, [rsp+340h+DestinationString]
0x14000e39f  mov     [rsp+340h+InternalParameters], rsi; InternalParameters
0x14000e3a4  lea     r9, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x14000e3a8  mov     [rsp+340h+CreateFileType], esi; CreateFileType
0x14000e3ac  lea     r8, [rbp+240h+ObjectAttributes]; ObjectAttributes
0x14000e3b0  mov     [rsp+340h+EaLength], esi; EaLength
0x14000e3b4  lea     rcx, [rbp+240h+FileHandle]; FileHandle
0x14000e3b8  mov     [rsp+340h+EaBuffer], rsi; EaBuffer
0x14000e3bd  mov     edx, 10000000h; DesiredAccess
0x14000e3c2  mov     [rsp+340h+CreateOptions], 1; CreateOptions
0x14000e3ca  mov     [rsp+340h+Disposition], 2; Disposition
0x14000e3d2  mov     [rbp+240h+ObjectAttributes.ObjectName], rax
0x14000e3d6  lea     rax, [rbp+240h+SecurityDescriptor]
0x14000e3da  mov     [rsp+340h+ShareAccess], 3; ShareAccess
0x14000e3e2  mov     [rsp+340h+FileAttributes], 80h; FileAttributes
0x14000e3ea  mov     [rsp+340h+AllocationSize], rsi; AllocationSize
0x14000e3ef  mov     [rbp+240h+ObjectAttributes.Length], 30h ; '0'
0x14000e3f6  mov     [rbp+240h+ObjectAttributes.RootDirectory], rsi
0x14000e3fa  mov     [rbp+240h+ObjectAttributes.Attributes], 240h
0x14000e401  mov     [rbp+240h+ObjectAttributes.SecurityDescriptor], rax
0x14000e405  mov     [rbp+240h+ObjectAttributes.SecurityQualityOfService], rsi
0x14000e409  call    cs:__imp_IoCreateFile
0x14000e410  nop     dword ptr [rax+rax+00h]
0x14000e415  mov     ebx, eax
0x14000e417  test    eax, eax
0x14000e419  js      short loc_14000E42D
0x14000e41b  mov     rcx, [rbp+240h+FileHandle]; Handle
0x14000e41f  call    cs:__imp_ZwClose
0x14000e426  nop     dword ptr [rax+rax+00h]
0x14000e42b  jmp     short loc_14000E43D
0x14000e42d  cmp     eax, 0C0000035h
0x14000e432  jz      short loc_14000E43B
0x14000e434  cmp     [rbp+240h+IoStatusBlock.Information], 4
0x14000e439  jnz     short loc_14000E43D
0x14000e43b  mov     ebx, esi
0x14000e43d  mov     eax, ebx
0x14000e43f  mov     rcx, [rbp+240h+var_30]
0x14000e446  xor     rcx, rsp; StackCookie
0x14000e449  call    __security_check_cookie
0x14000e44e  add     rsp, 328h
0x14000e455  pop     rdi
0x14000e456  pop     rsi
0x14000e457  pop     rbx
0x14000e458  pop     rbp
0x14000e459  retn
```
