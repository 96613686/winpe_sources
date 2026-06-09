# SmpCreateProtectedPrefixes

- ea: `0x14000a140`
- end: `0x14000ac93`
- name: `SmpCreateProtectedPrefixes`
- size: `2899`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x14000a140`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14000aaa7`
- `ntdll!NtOpenFile` at `0x14000ab0a`
- `ntdll!NtOpenFile` at `0x14000aaa7`
- `ntdll!NtOpenFile` at `0x14000ab0a`
- `ntdll!NtClose` at `0x14000abc8`
- `ntdll!NtClose` at `0x14000abd7`
- `ntdll!NtClose` at `0x14000abc8`
- `ntdll!NtClose` at `0x14000abd7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a466`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a4cc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a607`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a74c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a88e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a8f4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a95a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a9e2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a466`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a4cc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a607`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a74c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a88e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a8f4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a95a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000a9e2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000a2ec`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000a2ec`
- `ntdll!RtlCreateAcl` at `0x14000a30e`
- `ntdll!RtlCreateAcl` at `0x14000a5c4`
- `ntdll!RtlCreateAcl` at `0x14000a709`
- `ntdll!RtlCreateAcl` at `0x14000a84e`
- `ntdll!RtlCreateAcl` at `0x14000a99f`
- `ntdll!RtlCreateAcl` at `0x14000a30e`
- `ntdll!RtlCreateAcl` at `0x14000a5c4`
- `ntdll!RtlCreateAcl` at `0x14000a709`
- `ntdll!RtlCreateAcl` at `0x14000a84e`
- `ntdll!RtlCreateAcl` at `0x14000a99f`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a489`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a4ef`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a62a`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a76f`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a8b1`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a917`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a97d`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a489`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a4ef`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a62a`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a76f`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a8b1`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a917`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000a97d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000a331`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000a331`
- `ntdll!NtSetSecurityObject` at `0x14000aac7`
- `ntdll!NtSetSecurityObject` at `0x14000ab2a`
- `ntdll!NtSetSecurityObject` at `0x14000aac7`
- `ntdll!NtSetSecurityObject` at `0x14000ab2a`
- `ntdll!NtCreateFile` at `0x14000a3ad`
- `ntdll!NtCreateFile` at `0x14000a411`
- `ntdll!NtCreateFile` at `0x14000a54b`
- `ntdll!NtCreateFile` at `0x14000a5ac`
- `ntdll!NtCreateFile` at `0x14000a686`
- `ntdll!NtCreateFile` at `0x14000a6e7`
- `ntdll!NtCreateFile` at `0x14000a7cb`
- `ntdll!NtCreateFile` at `0x14000a82c`
- `ntdll!NtCreateFile` at `0x14000ab9f`
- `ntdll!NtCreateFile` at `0x14000a3ad`
- `ntdll!NtCreateFile` at `0x14000a411`
- `ntdll!NtCreateFile` at `0x14000a54b`
- `ntdll!NtCreateFile` at `0x14000a5ac`
- `ntdll!NtCreateFile` at `0x14000a686`
- `ntdll!NtCreateFile` at `0x14000a6e7`
- `ntdll!NtCreateFile` at `0x14000a7cb`
- `ntdll!NtCreateFile` at `0x14000a82c`
- `ntdll!NtCreateFile` at `0x14000ab9f`
- `ntdll!RtlAddMandatoryAce` at `0x14000aa12`
- `ntdll!RtlAddMandatoryAce` at `0x14000aa12`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x14000aa35`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x14000aa35`
- `ntdll!RtlAdjustPrivilege` at `0x14000aa54`
- `ntdll!RtlAdjustPrivilege` at `0x14000abf3`
- `ntdll!RtlAdjustPrivilege` at `0x14000aa54`
- `ntdll!RtlAdjustPrivilege` at `0x14000abf3`
- `ntdll!RtlFreeSid` at `0x14000ac02`
- `ntdll!RtlFreeSid` at `0x14000ac11`
- `ntdll!RtlFreeSid` at `0x14000ac20`
- `ntdll!RtlFreeSid` at `0x14000ac2f`
- `ntdll!RtlFreeSid` at `0x14000ac3e`
- `ntdll!RtlFreeSid` at `0x14000ac4d`
- `ntdll!RtlFreeSid` at `0x14000ac5c`
- `ntdll!RtlFreeSid` at `0x14000ac6b`
- `ntdll!RtlFreeSid` at `0x14000ac02`
- `ntdll!RtlFreeSid` at `0x14000ac11`
- `ntdll!RtlFreeSid` at `0x14000ac20`
- `ntdll!RtlFreeSid` at `0x14000ac2f`
- `ntdll!RtlFreeSid` at `0x14000ac3e`
- `ntdll!RtlFreeSid` at `0x14000ac4d`
- `ntdll!RtlFreeSid` at `0x14000ac5c`
- `ntdll!RtlFreeSid` at `0x14000ac6b`

## string_xrefs

- `0x14000a1f4`: `\Device\NamedPipe\ProtectedPrefix\LocalService`
- `0x14000a215`: `\Device\mailslot\ProtectedPrefix\NetWorkService`
- `0x14000a20a`: `\Device\NamedPipe\ProtectedPrefix\NetWorkService`
- `0x14000a1ff`: `\Device\mailslot\ProtectedPrefix\LocalService`

## pseudocode

```c
__int64 SmpCreateProtectedPrefixes()
{
  NTSTATUS v0; // ebx
  NTSTATUS v1; // eax
  char v2; // di
  void *FileAttributes; // [rsp+30h] [rbp-D8h]
  _QWORD ObjectAttributes[7]; // [rsp+68h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-68h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp-50h] BYREF
  PSID v9; // [rsp+C0h] [rbp-48h] BYREF
  PSID Sid; // [rsp+C8h] [rbp-40h] BYREF
  PSID v11; // [rsp+D0h] [rbp-38h] BYREF
  PSID v12; // [rsp+D8h] [rbp-30h] BYREF
  PSID v13; // [rsp+E0h] [rbp-28h] BYREF
  PSID v14; // [rsp+E8h] [rbp-20h] BYREF
  PSID v15; // [rsp+F0h] [rbp-18h] BYREF
  PSID v16; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v17[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v18[2]; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v19[2]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v20[2]; // [rsp+130h] [rbp+28h] BYREF
  _QWORD v21[2]; // [rsp+140h] [rbp+38h] BYREF
  _QWORD v22[2]; // [rsp+150h] [rbp+48h] BYREF
  _QWORD v23[2]; // [rsp+160h] [rbp+58h] BYREF
  _QWORD v24[2]; // [rsp+170h] [rbp+68h] BYREF
  _QWORD v25[2]; // [rsp+180h] [rbp+78h] BYREF
  _QWORD v26[2]; // [rsp+190h] [rbp+88h] BYREF
  _QWORD v27[2]; // [rsp+1A0h] [rbp+98h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v29; // [rsp+1D0h] [rbp+C8h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+1D8h] [rbp+D0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v31; // [rsp+1E0h] [rbp+D8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v32; // [rsp+1E8h] [rbp+E0h] BYREF
  _ACL Acl; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _ACL Sacl; // [rsp+608h] [rbp+500h] BYREF

  v29 = 0;
  *(_DWORD *)v31.Value = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v32.Value = 0;
  v25[1] = L"\\Device\\NamedPipe\\";
  Handle = 0;
  v26[1] = L"\\Device\\mailslot\\";
  FileHandle = 0;
  v17[1] = L"\\Device\\NamedPipe\\ProtectedPrefix";
  v18[1] = L"\\Device\\mailslot\\ProtectedPrefix";
  v19[1] = L"\\Device\\NamedPipe\\ProtectedPrefix\\Administrators";
  v20[1] = L"\\Device\\mailslot\\ProtectedPrefix\\Administrators";
  v21[1] = L"\\Device\\NamedPipe\\ProtectedPrefix\\LocalService";
  v22[1] = L"\\Device\\mailslot\\ProtectedPrefix\\LocalService";
  v23[1] = L"\\Device\\NamedPipe\\ProtectedPrefix\\NetWorkService";
  v24[1] = L"\\Device\\mailslot\\ProtectedPrefix\\NetWorkService";
  v27[1] = L"\\Device\\NamedPipe\\Sessions";
  memset(&ObjectAttributes[1], 0, 44);
  *(_WORD *)&v31.Value[4] = 256;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  IoStatusBlock = 0;
  *(_WORD *)&v32.Value[4] = 4096;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  Sid = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v9 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  LOBYTE(ObjectAttributes[0]) = 1;
  v25[0] = 2490404;
  v26[0] = 2359330;
  v17[0] = 4456514;
  v18[0] = 4325440;
  v19[0] = 6422624;
  v20[0] = 6291550;
  v21[0] = 6160476;
  v22[0] = 6029402;
  v23[0] = 6422624;
  v24[0] = 6291550;
  v27[0] = 3538996;
  v0 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v0 >= 0 )
  {
    v0 = RtlCreateAcl(&Acl, 0x408u, 2u);
    if ( v0 >= 0 )
    {
      v0 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
      if ( v0 >= 0 )
      {
        ObjectAttributes[3] = v17;
        LODWORD(ObjectAttributes[1]) = 48;
        ObjectAttributes[2] = 0;
        LODWORD(ObjectAttributes[4]) = 64;
        ObjectAttributes[5] = SecurityDescriptor;
        ObjectAttributes[6] = 0;
        v0 = NtCreateFile(
               &PipePrefix1,
               0x1F01FFu,
               (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
               &IoStatusBlock,
               0,
               0x80u,
               3u,
               2u,
               1u,
               0,
               0);
        if ( v0 >= 0 )
        {
          ObjectAttributes[3] = v18;
          v1 = NtCreateFile(
                 &MailPrefix1,
                 0x1F01FFu,
                 (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                 &IoStatusBlock,
                 0,
                 0x80u,
                 3u,
                 2u,
                 1u,
                 0,
                 0);
          v0 = v1;
          if ( v1 == -1073741766 )
          {
            v2 = 0;
          }
          else
          {
            v2 = 1;
            if ( v1 < 0 )
              goto LABEL_46;
          }
          v0 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
          if ( v0 >= 0 )
          {
            v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, Sid);
            if ( v0 >= 0 )
            {
              v0 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v11);
              if ( v0 >= 0 )
              {
                v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v11);
                if ( v0 >= 0 )
                {
                  ObjectAttributes[3] = v19;
                  v0 = NtCreateFile(
                         &PipePrefix2,
                         0x1F01FFu,
                         (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                         &IoStatusBlock,
                         0,
                         0x80u,
                         3u,
                         2u,
                         1u,
                         0,
                         0);
                  if ( v0 >= 0 )
                  {
                    if ( v2 )
                    {
                      ObjectAttributes[3] = v20;
                      NtCreateFile(
                        &MailPrefix2,
                        0x1F01FFu,
                        (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                        &IoStatusBlock,
                        0,
                        0x80u,
                        3u,
                        2u,
                        1u,
                        0,
                        0);
                    }
                    v0 = RtlCreateAcl(&Acl, 0x408u, 2u);
                    if ( v0 >= 0 )
                    {
                      v0 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &v12);
                      if ( v0 >= 0 )
                      {
                        v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v12);
                        if ( v0 >= 0 )
                        {
                          ObjectAttributes[3] = v21;
                          v0 = NtCreateFile(
                                 &PipePrefix3,
                                 0x1F01FFu,
                                 (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                 &IoStatusBlock,
                                 0,
                                 0x80u,
                                 3u,
                                 2u,
                                 1u,
                                 0,
                                 0);
                          if ( v0 >= 0 )
                          {
                            if ( !v2
                              || (ObjectAttributes[3] = v22,
                                  v0 = NtCreateFile(
                                         &MailPrefix3,
                                         0x1F01FFu,
                                         (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                         &IoStatusBlock,
                                         0,
                                         0x80u,
                                         3u,
                                         2u,
                                         1u,
                                         0,
                                         0),
                                  v0 >= 0) )
                            {
                              v0 = RtlCreateAcl(&Acl, 0x408u, 2u);
                              if ( v0 >= 0 )
                              {
                                v0 = RtlAllocateAndInitializeSid(
                                       &IdentifierAuthority,
                                       1u,
                                       0x14u,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       &v13);
                                if ( v0 >= 0 )
                                {
                                  v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v13);
                                  if ( v0 >= 0 )
                                  {
                                    ObjectAttributes[3] = v23;
                                    v0 = NtCreateFile(
                                           &PipePrefix4,
                                           0x1F01FFu,
                                           (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                           &IoStatusBlock,
                                           0,
                                           0x80u,
                                           3u,
                                           2u,
                                           1u,
                                           0,
                                           0);
                                    if ( v0 >= 0 )
                                    {
                                      if ( !v2
                                        || (ObjectAttributes[3] = v24,
                                            v0 = NtCreateFile(
                                                   &MailPrefix4,
                                                   0x1F01FFu,
                                                   (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                                   &IoStatusBlock,
                                                   0,
                                                   0x80u,
                                                   3u,
                                                   2u,
                                                   1u,
                                                   0,
                                                   0),
                                            v0 >= 0) )
                                      {
                                        v0 = RtlCreateAcl(&Acl, 0x408u, 2u);
                                        if ( v0 >= 0 )
                                        {
                                          v0 = RtlAllocateAndInitializeSid(&v31, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v9);
                                          if ( v0 >= 0 )
                                          {
                                            v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v9);
                                            if ( v0 >= 0 )
                                            {
                                              v0 = RtlAllocateAndInitializeSid(
                                                     &IdentifierAuthority,
                                                     1u,
                                                     0xCu,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     &v16);
                                              if ( v0 >= 0 )
                                              {
                                                v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v16);
                                                if ( v0 >= 0 )
                                                {
                                                  v0 = RtlAllocateAndInitializeSid(
                                                         &IdentifierAuthority,
                                                         1u,
                                                         7u,
                                                         0,
                                                         0,
                                                         0,
                                                         0,
                                                         0,
                                                         0,
                                                         0,
                                                         &v15);
                                                  if ( v0 >= 0 )
                                                  {
                                                    v0 = RtlAddAccessAllowedAce(&Acl, 2u, 2u, v15);
                                                    if ( v0 >= 0 )
                                                    {
                                                      v0 = RtlCreateAcl(&Sacl, 0x408u, 2u);
                                                      if ( v0 >= 0 )
                                                      {
                                                        v0 = RtlAllocateAndInitializeSid(
                                                               &v32,
                                                               1u,
                                                               0x1000u,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               &v14);
                                                        if ( v0 >= 0 )
                                                        {
                                                          LODWORD(FileAttributes) = 1;
                                                          v0 = RtlAddMandatoryAce(
                                                                 &Sacl,
                                                                 2u,
                                                                 0,
                                                                 (ULONG)v14,
                                                                 0x11u,
                                                                 FileAttributes);
                                                          if ( v0 >= 0 )
                                                          {
                                                            v0 = RtlSetSaclSecurityDescriptor(
                                                                   SecurityDescriptor,
                                                                   1u,
                                                                   &Sacl,
                                                                   0);
                                                            if ( v0 >= 0 )
                                                            {
                                                              if ( RtlAdjustPrivilege(
                                                                     8u,
                                                                     1u,
                                                                     0,
                                                                     (PBOOLEAN)ObjectAttributes) < 0 )
                                                                LOBYTE(ObjectAttributes[0]) = 1;
                                                              ObjectAttributes[3] = v25;
                                                              LODWORD(ObjectAttributes[1]) = 48;
                                                              ObjectAttributes[2] = 0;
                                                              LODWORD(ObjectAttributes[4]) = 64;
                                                              *(_OWORD *)&ObjectAttributes[5] = 0;
                                                              v0 = NtOpenFile(
                                                                     &FileHandle,
                                                                     0x11E0000u,
                                                                     (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                                                     &IoStatusBlock,
                                                                     3u,
                                                                     0x20u);
                                                              if ( v0 >= 0 )
                                                              {
                                                                v0 = NtSetSecurityObject(
                                                                       FileHandle,
                                                                       0x1Cu,
                                                                       SecurityDescriptor);
                                                                if ( v0 >= 0 )
                                                                {
                                                                  if ( v2 )
                                                                  {
                                                                    ObjectAttributes[3] = v26;
                                                                    v0 = NtOpenFile(
                                                                           &Handle,
                                                                           0x11E0000u,
                                                                           (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                                                           &IoStatusBlock,
                                                                           3u,
                                                                           0x20u);
                                                                    if ( v0 < 0 )
                                                                      goto LABEL_46;
                                                                    NtSetSecurityObject(
                                                                      Handle,
                                                                      0x1Cu,
                                                                      SecurityDescriptor);
                                                                  }
                                                                  ObjectAttributes[3] = v27;
                                                                  LODWORD(ObjectAttributes[1]) = 48;
                                                                  ObjectAttributes[2] = 0;
                                                                  LODWORD(ObjectAttributes[4]) = 64;
                                                                  ObjectAttributes[5] = SmpPrimarySecurityDescriptor;
                                                                  ObjectAttributes[6] = 0;
                                                                  v0 = NtCreateFile(
                                                                         &SmpPipeSessionsPrefix,
                                                                         0x1F01FFu,
                                                                         (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                                                                         &IoStatusBlock,
                                                                         0,
                                                                         0x80u,
                                                                         3u,
                                                                         2u,
                                                                         1u,
                                                                         0,
                                                                         0);
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
LABEL_46:
  if ( Handle )
    NtClose(Handle);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( !LOBYTE(ObjectAttributes[0]) )
    RtlAdjustPrivilege(8u, 0, 0, (PBOOLEAN)ObjectAttributes);
  if ( v9 )
    RtlFreeSid(v9);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v11 )
    RtlFreeSid(v11);
  if ( v12 )
    RtlFreeSid(v12);
  if ( v13 )
    RtlFreeSid(v13);
  if ( v14 )
    RtlFreeSid(v14);
  if ( v15 )
    RtlFreeSid(v15);
  if ( v16 )
    RtlFreeSid(v16);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000a140  mov     r11, rsp
0x14000a143  mov     [r11+20h], rbx
0x14000a147  push    rbp
0x14000a148  lea     rbp, [r11-928h]
0x14000a14f  sub     rsp, 0A20h
0x14000a156  mov     rax, cs:__security_cookie
0x14000a15d  xor     rax, rsp
0x14000a160  mov     [rbp+920h+var_10], rax
0x14000a167  xor     eax, eax
0x14000a169  mov     [r11+8], rsi
0x14000a16d  mov     [rbp+920h+var_858], rax
0x14000a174  lea     rcx, [rbp+920h+SecurityDescriptor]; SecurityDescriptor
0x14000a17b  mov     dword ptr [rbp+920h+var_848.Value], eax
0x14000a181  xor     esi, esi
0x14000a183  mov     dword ptr [rbp+920h+IdentifierAuthority.Value], eax
0x14000a189  xorps   xmm0, xmm0
0x14000a18c  mov     dword ptr [rbp+920h+var_840.Value], eax
0x14000a192  xorps   xmm1, xmm1
0x14000a195  lea     rax, aDeviceNamedpip_4; "\\Device\\NamedPipe\\"
0x14000a19c  mov     [r11+18h], r14
0x14000a1a0  mov     [rbp+920h+var_8A0], rax
0x14000a1a7  mov     edx, 1; Revision
0x14000a1ac  lea     rax, aDeviceMailslot_2; "\\Device\\mailslot\\"
0x14000a1b3  mov     [rbp+920h+Handle], rsi
0x14000a1b7  mov     [rbp+920h+var_890], rax
0x14000a1be  mov     r14d, 40h ; '@'
0x14000a1c4  lea     rax, aDeviceNamedpip_3; "\\Device\\NamedPipe\\ProtectedPrefix"
0x14000a1cb  mov     [rbp+920h+FileHandle], rsi
0x14000a1cf  mov     [rbp+920h+var_920], rax
0x14000a1d3  lea     rax, aDeviceMailslot_1; "\\Device\\mailslot\\ProtectedPrefix"
0x14000a1da  mov     [rbp+920h+var_910], rax
0x14000a1de  lea     rax, aDeviceNamedpip_1; "\\Device\\NamedPipe\\ProtectedPrefix\\A"...
0x14000a1e5  mov     [rbp+920h+var_900], rax
0x14000a1e9  lea     rax, aDeviceMailslot_0; "\\Device\\mailslot\\ProtectedPrefix\\Ad"...
0x14000a1f0  mov     [rbp+920h+var_8F0], rax
0x14000a1f4  lea     rax, aDeviceNamedpip; "\\Device\\NamedPipe\\ProtectedPrefix\\L"...
0x14000a1fb  mov     [rbp+920h+var_8E0], rax
0x14000a1ff  lea     rax, aDeviceMailslot_3; "\\Device\\mailslot\\ProtectedPrefix\\Lo"...
0x14000a206  mov     [rbp+920h+var_8D0], rax
0x14000a20a  lea     rax, aDeviceNamedpip_0; "\\Device\\NamedPipe\\ProtectedPrefix\\N"...
0x14000a211  mov     [rbp+920h+var_8C0], rax
0x14000a215  lea     rax, aDeviceMailslot; "\\Device\\mailslot\\ProtectedPrefix\\Ne"...
0x14000a21c  mov     [rbp+920h+var_8B0], rax
0x14000a220  lea     rax, aDeviceNamedpip_2; "\\Device\\NamedPipe\\Sessions"
0x14000a227  movups  xmmword ptr [rsp+0A20h+ObjectAttributes+18h], xmm0
0x14000a22c  mov     [rbp+920h+var_880], rax
0x14000a233  movups  xmmword ptr [rsp+0A20h+ObjectAttributes+8], xmm0
0x14000a238  mov     word ptr [rbp+920h+var_848.Value+4], 100h
0x14000a241  movups  xmmword ptr [rbp+920h+ObjectAttributes+24h], xmm0
0x14000a245  mov     word ptr [rbp+920h+IdentifierAuthority.Value+4], 500h
0x14000a24e  movups  xmmword ptr [rbp+920h+IoStatusBlock], xmm0
0x14000a252  mov     word ptr [rbp+920h+var_840.Value+4], 1000h
0x14000a25b  movups  [rbp+920h+SecurityDescriptor], xmm1
0x14000a262  mov     [rbp+920h+Sid], rsi
0x14000a266  movups  [rbp+920h+var_868], xmm1
0x14000a26d  mov     [rbp+920h+var_958], rsi
0x14000a271  mov     [rbp+920h+var_950], rsi
0x14000a275  mov     [rbp+920h+var_948], rsi
0x14000a279  mov     [rbp+920h+var_968], rsi
0x14000a27d  mov     [rbp+920h+var_940], rsi
0x14000a281  mov     [rbp+920h+var_938], rsi
0x14000a285  mov     [rbp+920h+var_930], rsi
0x14000a289  mov     [rsp+0A20h+ObjectAttributes], 1
0x14000a28e  mov     [rbp+920h+var_8A8], 260024h
0x14000a296  mov     [rbp+920h+var_898], 240022h
0x14000a2a1  mov     [rbp+920h+var_928], 440042h
0x14000a2a9  mov     [rbp+920h+var_918], 420040h
0x14000a2b1  mov     [rbp+920h+var_908], 620060h
0x14000a2b9  mov     [rbp+920h+var_8F8], 60005Eh
0x14000a2c1  mov     [rbp+920h+var_8E8], 5E005Ch
0x14000a2c9  mov     [rbp+920h+var_8D8], 5C005Ah
0x14000a2d1  mov     [rbp+920h+var_8C8], 620060h
0x14000a2d9  mov     [rbp+920h+var_8B8], 60005Eh
0x14000a2e1  mov     [rbp+920h+var_888], 360034h
0x14000a2ec  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000a2f2  mov     ebx, eax
0x14000a2f4  test    eax, eax
0x14000a2f6  js      loc_14000ABAF
0x14000a2fc  mov     edx, 408h; AclLength
0x14000a301  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a308  mov     r8d, 2; AclRevision
0x14000a30e  call    cs:__imp_RtlCreateAcl
0x14000a314  mov     ebx, eax
0x14000a316  test    eax, eax
0x14000a318  js      loc_14000ABAF
0x14000a31e  xor     r9d, r9d; DaclDefaulted
0x14000a321  lea     r8, [rbp+920h+Acl]; Dacl
0x14000a328  mov     dl, 1; DaclPresent
0x14000a32a  lea     rcx, [rbp+920h+SecurityDescriptor]; SecurityDescriptor
0x14000a331  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000a337  mov     ebx, eax
0x14000a339  test    eax, eax
0x14000a33b  js      loc_14000ABAF
0x14000a341  mov     [rsp+50h], esi; EaLength
0x14000a345  lea     rax, [rbp+920h+var_928]
0x14000a349  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a34e  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a352  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a35a  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a35f  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a367  lea     rcx, PipePrefix1; FileHandle
0x14000a36e  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a373  mov     edx, 1F01FFh; DesiredAccess
0x14000a378  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a380  lea     rax, [rbp+920h+SecurityDescriptor]
0x14000a387  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a38f  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a394  mov     dword ptr [rsp+0A20h+ObjectAttributes+8], 30h ; '0'
0x14000a39c  mov     qword ptr [rsp+0A20h+ObjectAttributes+10h], rsi
0x14000a3a1  mov     dword ptr [rbp+920h+ObjectAttributes+20h], r14d
0x14000a3a5  mov     qword ptr [rbp+920h+ObjectAttributes+28h], rax
0x14000a3a9  mov     qword ptr [rbp+920h+ObjectAttributes+30h], rsi
0x14000a3ad  call    cs:__imp_NtCreateFile
0x14000a3b3  mov     ebx, eax
0x14000a3b5  test    eax, eax
0x14000a3b7  js      loc_14000ABAF
0x14000a3bd  mov     [rsp+50h], esi; EaLength
0x14000a3c1  lea     rax, [rbp+920h+var_918]
0x14000a3c5  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a3ca  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a3ce  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a3d6  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a3db  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a3e3  lea     rcx, MailPrefix1; FileHandle
0x14000a3ea  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a3f2  mov     edx, 1F01FFh; DesiredAccess
0x14000a3f7  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a3ff  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a404  mov     [rsp+0A20h+arg_8], rdi
0x14000a40c  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a411  call    cs:__imp_NtCreateFile
0x14000a417  mov     ebx, eax
0x14000a419  cmp     eax, 0C000003Ah
0x14000a41e  jnz     short loc_14000A425
0x14000a420  xor     dil, dil
0x14000a423  jmp     short loc_14000A430
0x14000a425  mov     dil, 1
0x14000a428  test    eax, eax
0x14000a42a  js      loc_14000ABA7
0x14000a430  lea     rax, [rbp+920h+Sid]
0x14000a434  mov     r9d, 220h; SubAuthority1
0x14000a43a  mov     [rsp+50h], rax; Sid
0x14000a43f  lea     rcx, [rbp+920h+IdentifierAuthority]; IdentifierAuthority
0x14000a446  mov     dword ptr [rsp+0A20h+EaBuffer], esi; SubAuthority7
0x14000a44a  mov     r8d, 20h ; ' '; SubAuthority0
0x14000a450  mov     [rsp+0A20h+CreateOptions], esi; SubAuthority6
0x14000a454  mov     dl, 2; SubAuthorityCount
0x14000a456  mov     [rsp+0A20h+CreateDisposition], esi; SubAuthority5
0x14000a45a  mov     [rsp+0A20h+ShareAccess], esi; SubAuthority4
0x14000a45e  mov     dword ptr [rsp+0A20h+FileAttributes], esi; SubAuthority3
0x14000a462  mov     dword ptr [rsp+0A20h+AllocationSize], esi; SubAuthority2
0x14000a466  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000a46c  mov     ebx, eax
0x14000a46e  test    eax, eax
0x14000a470  js      loc_14000ABA7
0x14000a476  mov     r9, [rbp+920h+Sid]; Sid
0x14000a47a  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a481  mov     edx, 2; AceRevision
0x14000a486  mov     r8d, edx; AccessMask
0x14000a489  call    cs:__imp_RtlAddAccessAllowedAce
0x14000a48f  mov     ebx, eax
0x14000a491  test    eax, eax
0x14000a493  js      loc_14000ABA7
0x14000a499  lea     rax, [rbp+920h+var_958]
0x14000a49d  xor     r9d, r9d; SubAuthority1
0x14000a4a0  mov     [rsp+50h], rax; Sid
0x14000a4a5  lea     rcx, [rbp+920h+IdentifierAuthority]; IdentifierAuthority
0x14000a4ac  mov     dword ptr [rsp+0A20h+EaBuffer], esi; SubAuthority7
0x14000a4b0  mov     r8d, 12h; SubAuthority0
0x14000a4b6  mov     [rsp+0A20h+CreateOptions], esi; SubAuthority6
0x14000a4ba  mov     dl, 1; SubAuthorityCount
0x14000a4bc  mov     [rsp+0A20h+CreateDisposition], esi; SubAuthority5
0x14000a4c0  mov     [rsp+0A20h+ShareAccess], esi; SubAuthority4
0x14000a4c4  mov     dword ptr [rsp+0A20h+FileAttributes], esi; SubAuthority3
0x14000a4c8  mov     dword ptr [rsp+0A20h+AllocationSize], esi; SubAuthority2
0x14000a4cc  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000a4d2  mov     ebx, eax
0x14000a4d4  test    eax, eax
0x14000a4d6  js      loc_14000ABA7
0x14000a4dc  mov     r9, [rbp+920h+var_958]; Sid
0x14000a4e0  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a4e7  mov     edx, 2; AceRevision
0x14000a4ec  mov     r8d, edx; AccessMask
0x14000a4ef  call    cs:__imp_RtlAddAccessAllowedAce
0x14000a4f5  mov     ebx, eax
0x14000a4f7  test    eax, eax
0x14000a4f9  js      loc_14000ABA7
0x14000a4ff  mov     [rsp+50h], esi; EaLength
0x14000a503  lea     rax, [rbp+920h+var_908]
0x14000a507  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a50c  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a510  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a518  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a51d  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a525  lea     rcx, PipePrefix2; FileHandle
0x14000a52c  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a534  mov     edx, 1F01FFh; DesiredAccess
0x14000a539  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a541  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a546  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a54b  call    cs:__imp_NtCreateFile
0x14000a551  mov     ebx, eax
0x14000a553  test    eax, eax
0x14000a555  js      loc_14000ABA7
0x14000a55b  test    dil, dil
0x14000a55e  jz      short loc_14000A5B2
0x14000a560  mov     [rsp+50h], esi; EaLength
0x14000a564  lea     rax, [rbp+920h+var_8F8]
0x14000a568  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a56d  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a571  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a579  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a57e  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a586  lea     rcx, MailPrefix2; FileHandle
0x14000a58d  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a595  mov     edx, 1F01FFh; DesiredAccess
0x14000a59a  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a5a2  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a5a7  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a5ac  call    cs:__imp_NtCreateFile
0x14000a5b2  mov     edx, 408h; AclLength
0x14000a5b7  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a5be  mov     r8d, 2; AclRevision
0x14000a5c4  call    cs:__imp_RtlCreateAcl
0x14000a5ca  mov     ebx, eax
0x14000a5cc  test    eax, eax
0x14000a5ce  js      loc_14000ABA7
0x14000a5d4  lea     rax, [rbp+920h+var_950]
0x14000a5d8  xor     r9d, r9d; SubAuthority1
0x14000a5db  mov     [rsp+50h], rax; Sid
0x14000a5e0  lea     rcx, [rbp+920h+IdentifierAuthority]; IdentifierAuthority
0x14000a5e7  mov     dword ptr [rsp+0A20h+EaBuffer], esi; SubAuthority7
0x14000a5eb  mov     r8d, 13h; SubAuthority0
0x14000a5f1  mov     [rsp+0A20h+CreateOptions], esi; SubAuthority6
0x14000a5f5  mov     dl, 1; SubAuthorityCount
0x14000a5f7  mov     [rsp+0A20h+CreateDisposition], esi; SubAuthority5
0x14000a5fb  mov     [rsp+0A20h+ShareAccess], esi; SubAuthority4
0x14000a5ff  mov     dword ptr [rsp+0A20h+FileAttributes], esi; SubAuthority3
0x14000a603  mov     dword ptr [rsp+0A20h+AllocationSize], esi; SubAuthority2
0x14000a607  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000a60d  mov     ebx, eax
0x14000a60f  test    eax, eax
0x14000a611  js      loc_14000ABA7
0x14000a617  mov     r9, [rbp+920h+var_950]; Sid
0x14000a61b  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a622  mov     edx, 2; AceRevision
0x14000a627  mov     r8d, edx; AccessMask
0x14000a62a  call    cs:__imp_RtlAddAccessAllowedAce
0x14000a630  mov     ebx, eax
0x14000a632  test    eax, eax
0x14000a634  js      loc_14000ABA7
0x14000a63a  mov     [rsp+50h], esi; EaLength
0x14000a63e  lea     rax, [rbp+920h+var_8E8]
0x14000a642  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a647  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a64b  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a653  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a658  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a660  lea     rcx, PipePrefix3; FileHandle
0x14000a667  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a66f  mov     edx, 1F01FFh; DesiredAccess
0x14000a674  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a67c  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a681  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a686  call    cs:__imp_NtCreateFile
0x14000a68c  mov     ebx, eax
0x14000a68e  test    eax, eax
0x14000a690  js      loc_14000ABA7
0x14000a696  test    dil, dil
0x14000a699  jz      short loc_14000A6F7
0x14000a69b  mov     [rsp+50h], esi; EaLength
0x14000a69f  lea     rax, [rbp+920h+var_8D8]
0x14000a6a3  mov     [rsp+0A20h+EaBuffer], rsi; EaBuffer
0x14000a6a8  lea     r9, [rbp+920h+IoStatusBlock]; IoStatusBlock
0x14000a6ac  mov     [rsp+0A20h+CreateOptions], 1; CreateOptions
0x14000a6b4  lea     r8, [rsp+0A20h+ObjectAttributes+8]; ObjectAttributes
0x14000a6b9  mov     [rsp+0A20h+CreateDisposition], 2; CreateDisposition
0x14000a6c1  lea     rcx, MailPrefix3; FileHandle
0x14000a6c8  mov     [rsp+0A20h+ShareAccess], 3; ShareAccess
0x14000a6d0  mov     edx, 1F01FFh; DesiredAccess
0x14000a6d5  mov     dword ptr [rsp+0A20h+FileAttributes], 80h; FileAttributes
0x14000a6dd  mov     [rsp+0A20h+AllocationSize], rsi; AllocationSize
0x14000a6e2  mov     qword ptr [rsp+0A20h+ObjectAttributes+18h], rax
0x14000a6e7  call    cs:__imp_NtCreateFile
0x14000a6ed  mov     ebx, eax
0x14000a6ef  test    eax, eax
0x14000a6f1  js      loc_14000ABA7
0x14000a6f7  mov     edx, 408h; AclLength
0x14000a6fc  lea     rcx, [rbp+920h+Acl]; Acl
0x14000a703  mov     r8d, 2; AclRevision
0x14000a709  call    cs:__imp_RtlCreateAcl
0x14000a70f  mov     ebx, eax
0x14000a711  test    eax, eax
0x14000a713  js      loc_14000ABA7
0x14000a719  lea     rax, [rbp+920h+var_948]
0x14000a71d  xor     r9d, r9d; SubAuthority1
0x14000a720  mov     [rsp+50h], rax; Sid
0x14000a725  lea     rcx, [rbp+920h+IdentifierAuthority]; IdentifierAuthority
0x14000a72c  mov     dword ptr [rsp+0A20h+EaBuffer], esi; SubAuthority7
0x14000a730  mov     r8d, 14h; SubAuthority0
  ... truncated ...
```
