# WerpCreateStoreDirectory

- ea: `0x14000eb08`
- end: `0x14000ee78`
- name: `WerpCreateStoreDirectory`
- size: `880`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f8bc`
- `0x1400122c0`

## callees

- `0x14000d174`
- `0x14000eb08`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee4d`
- `ntoskrnl!ZwClose` at `0x14000eded`
- `ntoskrnl!ZwClose` at `0x14000eded`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000ed33`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000ed33`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ed14`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ed14`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000ecc7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000ecf3`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000ecc7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000ecf3`
- `ntoskrnl!RtlLengthSid` at `0x14000ebb4`
- `ntoskrnl!RtlLengthSid` at `0x14000ec2b`
- `ntoskrnl!RtlLengthSid` at `0x14000ebb4`
- `ntoskrnl!RtlLengthSid` at `0x14000ec2b`
- `ntoskrnl!IoCreateFile` at `0x14000edd7`
- `ntoskrnl!IoCreateFile` at `0x14000edd7`
- `ntoskrnl!RtlCreateAcl` at `0x14000ec96`
- `ntoskrnl!RtlCreateAcl` at `0x14000ec96`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ec72`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ec72`
- `ksecdd!SecLookupWellKnownSid` at `0x14000eb56`
- `ksecdd!SecLookupWellKnownSid` at `0x14000eb9b`
- `ksecdd!SecLookupWellKnownSid` at `0x14000ebcf`
- `ksecdd!SecLookupWellKnownSid` at `0x14000ec12`
- `ksecdd!SecLookupWellKnownSid` at `0x14000eb56`
- `ksecdd!SecLookupWellKnownSid` at `0x14000eb9b`
- `ksecdd!SecLookupWellKnownSid` at `0x14000ebcf`
- `ksecdd!SecLookupWellKnownSid` at `0x14000ec12`

## pseudocode

```c
__int64 WerpCreateStoreDirectory()
{
  __int64 v0; // rdx
  NTSTATUS SecurityDescriptor; // ebx
  void *Mem; // rax
  void *v3; // r15
  void *v4; // rsi
  struct _ACL *v5; // rdi
  ULONG v6; // r12d
  __int64 v7; // rdx
  void *v8; // rax
  void *Sid; // r14
  ULONG v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  ULONG v13; // r12d
  NTSTATUS v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  ULONG SidSize; // [rsp+E0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+E8h] [rbp+6Fh] BYREF

  FileHandle = 0;
  SidSize = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  SecurityDescriptor = SecLookupWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &SidSize);
  if ( SecurityDescriptor == -1073741789 )
  {
    Mem = (void *)WerpAllocateMem(SidSize, v0);
    v3 = Mem;
    if ( Mem )
    {
      v4 = 0;
      v5 = 0;
      SecurityDescriptor = SecLookupWellKnownSid(WinBuiltinAdministratorsSid, Mem, SidSize, &SidSize);
      if ( SecurityDescriptor >= 0 )
      {
        v6 = RtlLengthSid(v3);
        SecurityDescriptor = SecLookupWellKnownSid(WinLocalSystemSid, 0, 0, &SidSize);
        if ( SecurityDescriptor == -1073741789 )
        {
          v8 = (void *)WerpAllocateMem(SidSize, v7);
          Sid = v8;
          if ( v8 )
          {
            SecurityDescriptor = SecLookupWellKnownSid(WinLocalSystemSid, v8, SidSize, &SidSize);
            if ( SecurityDescriptor >= 0 )
            {
              v10 = RtlLengthSid(Sid);
              v4 = (void *)WerpAllocateMem(40, v11);
              if ( v4 && (v13 = v10 + v6, (v5 = (struct _ACL *)WerpAllocateMem(v13 + 32, v12)) != 0) )
              {
                SecurityDescriptor = RtlCreateSecurityDescriptor(v4, 1u);
                if ( SecurityDescriptor >= 0 )
                {
                  SecurityDescriptor = RtlCreateAcl(v5, v13 + 32, 2u);
                  if ( SecurityDescriptor >= 0 )
                  {
                    SecurityDescriptor = RtlAddAccessAllowedAceEx(v5, 2u, 3u, 0x10000000u, Sid);
                    if ( SecurityDescriptor >= 0 )
                    {
                      SecurityDescriptor = RtlAddAccessAllowedAceEx(v5, 2u, 3u, 0x10000000u, v3);
                      if ( SecurityDescriptor >= 0 )
                      {
                        SecurityDescriptor = RtlSetDaclSecurityDescriptor(v4, 1u, v5, 0);
                        if ( SecurityDescriptor >= 0 )
                        {
                          SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v4, Sid, 0);
                          if ( SecurityDescriptor >= 0 )
                          {
                            ObjectAttributes.Length = 48;
                            ObjectAttributes.RootDirectory = 0;
                            ObjectAttributes.Attributes = 576;
                            ObjectAttributes.ObjectName = &WerKernelLiveReportRootPath;
                            ObjectAttributes.SecurityDescriptor = v4;
                            ObjectAttributes.SecurityQualityOfService = 0;
                            v14 = IoCreateFile(
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
                            SecurityDescriptor = v14;
                            if ( v14 < 0 )
                            {
                              if ( v14 == -1073741771 || IoStatusBlock.Information == 4 )
                                SecurityDescriptor = 0;
                            }
                            else
                            {
                              ZwClose(FileHandle);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                SecurityDescriptor = -1073741823;
              }
            }
            ExFreePoolWithTag(Sid, 0);
          }
          else
          {
            SecurityDescriptor = -1073741823;
          }
        }
      }
      ExFreePoolWithTag(v3, 0);
      if ( v4 )
        ExFreePoolWithTag(v4, 0);
      if ( v5 )
        ExFreePoolWithTag(v5, 0);
    }
    else
    {
      return (unsigned int)-1073741823;
    }
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14000eb08  mov     [rsp-8+arg_10], rbx
0x14000eb0d  mov     [rsp-8+arg_18], rsi
0x14000eb12  push    rbp
0x14000eb13  push    rdi
0x14000eb14  push    r12
0x14000eb16  push    r14
0x14000eb18  push    r15
0x14000eb1a  lea     rbp, [rsp-37h]
0x14000eb1f  sub     rsp, 0B0h
0x14000eb26  xorps   xmm0, xmm0
0x14000eb29  mov     [rbp+57h+FileHandle], 0
0x14000eb31  xor     eax, eax
0x14000eb33  lea     r9, [rbp+57h+SidSize]; SidSize
0x14000eb37  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000eb3b  xor     r8d, r8d; SidBufferSize
0x14000eb3e  mov     [rbp+57h+SidSize], eax
0x14000eb41  xor     edx, edx; Sid
0x14000eb43  lea     r14d, [rax+1Ah]
0x14000eb47  mov     ecx, r14d; SidType
0x14000eb4a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000eb4e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000eb52  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000eb56  call    cs:__imp_SecLookupWellKnownSid
0x14000eb5d  nop     dword ptr [rax+rax+00h]
0x14000eb62  mov     ebx, eax
0x14000eb64  cmp     eax, 0C0000023h
0x14000eb69  jnz     loc_14000EE59
0x14000eb6f  mov     ecx, [rbp+57h+SidSize]
0x14000eb72  call    WerpAllocateMem
0x14000eb77  mov     r15, rax
0x14000eb7a  test    rax, rax
0x14000eb7d  jnz     short loc_14000EB89
0x14000eb7f  mov     ebx, 0C0000001h
0x14000eb84  jmp     loc_14000EE59
0x14000eb89  mov     r8d, [rbp+57h+SidSize]; SidBufferSize
0x14000eb8d  lea     r9, [rbp+57h+SidSize]; SidSize
0x14000eb91  mov     rdx, r15; Sid
0x14000eb94  mov     ecx, r14d; SidType
0x14000eb97  xor     esi, esi
0x14000eb99  xor     edi, edi
0x14000eb9b  call    cs:__imp_SecLookupWellKnownSid
0x14000eba2  nop     dword ptr [rax+rax+00h]
0x14000eba7  mov     ebx, eax
0x14000eba9  test    eax, eax
0x14000ebab  js      loc_14000EE1C
0x14000ebb1  mov     rcx, r15; Sid
0x14000ebb4  call    cs:__imp_RtlLengthSid
0x14000ebbb  nop     dword ptr [rax+rax+00h]
0x14000ebc0  lea     r9, [rbp+57h+SidSize]; SidSize
0x14000ebc4  xor     r8d, r8d; SidBufferSize
0x14000ebc7  xor     edx, edx; Sid
0x14000ebc9  lea     ecx, [rsi+16h]; SidType
0x14000ebcc  mov     r12d, eax
0x14000ebcf  call    cs:__imp_SecLookupWellKnownSid
0x14000ebd6  nop     dword ptr [rax+rax+00h]
0x14000ebdb  mov     ebx, eax
0x14000ebdd  cmp     eax, 0C0000023h
0x14000ebe2  jnz     loc_14000EE1C
0x14000ebe8  mov     ecx, [rbp+57h+SidSize]
0x14000ebeb  call    WerpAllocateMem
0x14000ebf0  mov     r14, rax
0x14000ebf3  test    rax, rax
0x14000ebf6  jnz     short loc_14000EC02
0x14000ebf8  mov     ebx, 0C0000001h
0x14000ebfd  jmp     loc_14000EE1C
0x14000ec02  mov     r8d, [rbp+57h+SidSize]; SidBufferSize
0x14000ec06  lea     r9, [rbp+57h+SidSize]; SidSize
0x14000ec0a  mov     rdx, r14; Sid
0x14000ec0d  mov     ecx, 16h; SidType
0x14000ec12  call    cs:__imp_SecLookupWellKnownSid
0x14000ec19  nop     dword ptr [rax+rax+00h]
0x14000ec1e  mov     ebx, eax
0x14000ec20  test    eax, eax
0x14000ec22  js      loc_14000EE0B
0x14000ec28  mov     rcx, r14; Sid
0x14000ec2b  call    cs:__imp_RtlLengthSid
0x14000ec32  nop     dword ptr [rax+rax+00h]
0x14000ec37  mov     ecx, 28h ; '('
0x14000ec3c  mov     ebx, eax
0x14000ec3e  call    WerpAllocateMem
0x14000ec43  mov     rsi, rax
0x14000ec46  test    rax, rax
0x14000ec49  jnz     short loc_14000EC55
0x14000ec4b  mov     ebx, 0C0000001h
0x14000ec50  jmp     loc_14000EE0B
0x14000ec55  add     r12d, ebx
0x14000ec58  lea     ecx, [r12+20h]
0x14000ec5d  call    WerpAllocateMem
0x14000ec62  mov     rdi, rax
0x14000ec65  test    rax, rax
0x14000ec68  jz      short loc_14000EC4B
0x14000ec6a  mov     edx, 1; Revision
0x14000ec6f  mov     rcx, rsi; SecurityDescriptor
0x14000ec72  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000ec79  nop     dword ptr [rax+rax+00h]
0x14000ec7e  mov     ebx, eax
0x14000ec80  test    eax, eax
0x14000ec82  js      loc_14000EE0B
0x14000ec88  mov     r8d, 2; AclRevision
0x14000ec8e  lea     edx, [r12+20h]; AclLength
0x14000ec93  mov     rcx, rdi; Acl
0x14000ec96  call    cs:__imp_RtlCreateAcl
0x14000ec9d  nop     dword ptr [rax+rax+00h]
0x14000eca2  mov     ebx, eax
0x14000eca4  test    eax, eax
0x14000eca6  js      loc_14000EE0B
0x14000ecac  mov     r8d, 3; AceFlags
0x14000ecb2  mov     [rsp+0D0h+Sid], r14; Sid
0x14000ecb7  mov     r9d, 10000000h; AccessMask
0x14000ecbd  mov     rcx, rdi; Acl
0x14000ecc0  lea     r12d, [r8-1]
0x14000ecc4  mov     edx, r12d; AceRevision
0x14000ecc7  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14000ecce  nop     dword ptr [rax+rax+00h]
0x14000ecd3  mov     ebx, eax
0x14000ecd5  test    eax, eax
0x14000ecd7  js      loc_14000EE0B
0x14000ecdd  mov     r9d, 10000000h; AccessMask
0x14000ece3  mov     [rsp+0D0h+Sid], r15; Sid
0x14000ece8  lea     r8d, [r12+1]; AceFlags
0x14000eced  mov     edx, r12d; AceRevision
0x14000ecf0  mov     rcx, rdi; Acl
0x14000ecf3  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14000ecfa  nop     dword ptr [rax+rax+00h]
0x14000ecff  mov     ebx, eax
0x14000ed01  test    eax, eax
0x14000ed03  js      loc_14000EE0B
0x14000ed09  xor     r9d, r9d; DaclDefaulted
0x14000ed0c  mov     r8, rdi; Dacl
0x14000ed0f  mov     dl, 1; DaclPresent
0x14000ed11  mov     rcx, rsi; SecurityDescriptor
0x14000ed14  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000ed1b  nop     dword ptr [rax+rax+00h]
0x14000ed20  mov     ebx, eax
0x14000ed22  test    eax, eax
0x14000ed24  js      loc_14000EE0B
0x14000ed2a  xor     r8d, r8d; OwnerDefaulted
0x14000ed2d  mov     rdx, r14; Owner
0x14000ed30  mov     rcx, rsi; SecurityDescriptor
0x14000ed33  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000ed3a  nop     dword ptr [rax+rax+00h]
0x14000ed3f  mov     ebx, eax
0x14000ed41  test    eax, eax
0x14000ed43  js      loc_14000EE0B
0x14000ed49  mov     [rsp+0D0h+Options], 100h; Options
0x14000ed51  lea     rax, WerKernelLiveReportRootPath
0x14000ed58  mov     [rsp+0D0h+InternalParameters], 0; InternalParameters
0x14000ed61  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000ed65  mov     [rsp+0D0h+CreateFileType], 0; CreateFileType
0x14000ed6d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000ed71  mov     [rsp+0D0h+EaLength], 0; EaLength
0x14000ed79  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000ed7d  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x14000ed86  mov     edx, 10000000h; DesiredAccess
0x14000ed8b  mov     [rsp+0D0h+CreateOptions], 1; CreateOptions
0x14000ed93  mov     [rsp+0D0h+Disposition], r12d; Disposition
0x14000ed98  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x14000eda0  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x14000eda8  mov     [rsp+0D0h+Sid], 0; AllocationSize
0x14000edb1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000edb8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000edc0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000edc7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000edcb  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rsi
0x14000edcf  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x14000edd7  call    cs:__imp_IoCreateFile
0x14000edde  nop     dword ptr [rax+rax+00h]
0x14000ede3  mov     ebx, eax
0x14000ede5  test    eax, eax
0x14000ede7  js      short loc_14000EDFB
0x14000ede9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000eded  call    cs:__imp_ZwClose
0x14000edf4  nop     dword ptr [rax+rax+00h]
0x14000edf9  jmp     short loc_14000EE0B
0x14000edfb  cmp     eax, 0C0000035h
0x14000ee00  jz      short loc_14000EE09
0x14000ee02  cmp     [rbp+57h+IoStatusBlock.Information], 4
0x14000ee07  jnz     short loc_14000EE0B
0x14000ee09  xor     ebx, ebx
0x14000ee0b  xor     edx, edx; Tag
0x14000ee0d  mov     rcx, r14; P
0x14000ee10  call    cs:__imp_ExFreePoolWithTag
0x14000ee17  nop     dword ptr [rax+rax+00h]
0x14000ee1c  xor     edx, edx; Tag
0x14000ee1e  mov     rcx, r15; P
0x14000ee21  call    cs:__imp_ExFreePoolWithTag
0x14000ee28  nop     dword ptr [rax+rax+00h]
0x14000ee2d  test    rsi, rsi
0x14000ee30  jz      short loc_14000EE43
0x14000ee32  xor     edx, edx; Tag
0x14000ee34  mov     rcx, rsi; P
0x14000ee37  call    cs:__imp_ExFreePoolWithTag
0x14000ee3e  nop     dword ptr [rax+rax+00h]
0x14000ee43  test    rdi, rdi
0x14000ee46  jz      short loc_14000EE59
0x14000ee48  xor     edx, edx; Tag
0x14000ee4a  mov     rcx, rdi; P
0x14000ee4d  call    cs:__imp_ExFreePoolWithTag
0x14000ee54  nop     dword ptr [rax+rax+00h]
0x14000ee59  lea     r11, [rsp+0D0h+var_20]
0x14000ee61  mov     eax, ebx
0x14000ee63  mov     rbx, [r11+40h]
0x14000ee67  mov     rsi, [r11+48h]
0x14000ee6b  mov     rsp, r11
0x14000ee6e  pop     r15
0x14000ee70  pop     r14
0x14000ee72  pop     r12
0x14000ee74  pop     rdi
0x14000ee75  pop     rbp
0x14000ee76  retn
```
