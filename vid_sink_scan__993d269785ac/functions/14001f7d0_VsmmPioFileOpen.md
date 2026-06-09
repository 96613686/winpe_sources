# VsmmPioFileOpen

- ea: `0x14001f7d0`
- end: `0x14001faab`
- name: `VsmmPioFileOpen`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD *, void *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400e0eb0`
- `0x1400e1900`

## callees

- `0x14000882c`
- `0x14001f780`
- `0x14001f7d0`
- `0x140021650`
- `0x140021d40`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001fa06`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001fa06`
- `ntoskrnl!ZwSetInformationFile` at `0x14001fa5f`
- `ntoskrnl!ZwSetInformationFile` at `0x14001fa97`
- `ntoskrnl!ZwSetInformationFile` at `0x14001fa5f`
- `ntoskrnl!ZwSetInformationFile` at `0x14001fa97`
- `ntoskrnl!ZwCreateFile` at `0x14001f9d3`
- `ntoskrnl!ZwCreateFile` at `0x14001f9d3`
- `ntoskrnl!RtlCreateAcl` at `0x14001f905`
- `ntoskrnl!RtlCreateAcl` at `0x14001f905`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001f924`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001f924`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001f948`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001f948`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001fa24`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001fa24`

## pseudocode

```c
__int64 __fastcall VsmmPioFileOpen(_QWORD *a1, void *a2, __int64 a3)
{
  void **v3; // rdi
  __int64 v7; // rdx
  size_t v8; // rax
  NTSTATUS v9; // ebx
  unsigned __int64 v11; // rcx
  void *v12; // rcx
  NTSTATUS v13; // eax
  struct _FILE_OBJECT *v14; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  void *v16; // rcx
  void *v17; // rcx
  union _LARGE_INTEGER AllocationSize; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h] BYREF
  _ACL Acl; // [rsp+78h] [rbp-88h] BYREF
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER FileInformation; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER v23; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-8h]
  _BYTE v28[128]; // [rsp+100h] [rbp+0h] BYREF

  v3 = (void **)(a1 + 76);
  a1[77] = 0;
  v27 = 0;
  a1[78] = 0;
  a1[76] = -1;
  Acl = 0;
  AllocationSize.QuadPart = 0;
  FileInformation.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  v23.QuadPart = 0;
  v19 = 0x740072u;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  IoStatusBlock = 0;
  a1[79] = -1;
  v7 = a1[1];
  *((_QWORD *)&v19 + 1) = v28;
  v8 = *(unsigned __int16 *)(v7 + 104);
  if ( (unsigned __int16)v8 > 0x72u )
    goto LABEL_2;
  memmove(v28, *(const void **)(v7 + 112), v8);
  v11 = *(unsigned __int16 *)(a1[1] + 104LL);
  v9 = RtlStringCbPrintfW(
         (NTSTRSAFE_PWSTR)(*((_QWORD *)&v19 + 1) + 2 * (v11 >> 1)),
         WORD1(v19) - v11,
         L".%016llX.slp",
         a3);
  if ( v9 < 0 )
    goto LABEL_3;
  v9 = RtlCreateAcl(&Acl, 8u, 2u);
  if ( v9 < 0 )
    goto LABEL_3;
  v9 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v9 < 0 )
    goto LABEL_3;
  v9 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
  if ( v9 < 0 )
    goto LABEL_3;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  AllocationSize.QuadPart = a1[6] << 12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.SecurityQualityOfService = 0;
  v9 = ZwCreateFile(v3, 0x10183u, &ObjectAttributes, &IoStatusBlock, &AllocationSize, 0x80u, 0, 5u, 0x1848u, 0, 0);
  if ( v9 < 0 )
    goto LABEL_3;
  v12 = *v3;
  Object = 0;
  v13 = ObReferenceObjectByHandle(v12, 0, 0, 0, &Object, 0);
  v14 = (struct _FILE_OBJECT *)Object;
  v9 = v13;
  v3[1] = Object;
  if ( v13 < 0 )
    goto LABEL_3;
  RelatedDeviceObject = IoGetRelatedDeviceObject(v14);
  v3[2] = RelatedDeviceObject;
  if ( RelatedDeviceObject )
  {
    v16 = *v3;
    FileInformation = AllocationSize;
    v9 = ZwSetInformationFile(v16, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
    if ( v9 >= 0 )
    {
      v17 = *v3;
      v23 = AllocationSize;
      ZwSetInformationFile(v17, &IoStatusBlock, &v23, 8u, FileValidDataLengthInformation);
      return 0;
    }
  }
  else
  {
LABEL_2:
    v9 = -1073741811;
  }
LABEL_3:
  VsmmPioFileClose(a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001f7d0  mov     [rsp-8+arg_18], rbx
0x14001f7d5  push    rbp
0x14001f7d6  push    rsi
0x14001f7d7  push    rdi
0x14001f7d8  push    r14
0x14001f7da  push    r15
0x14001f7dc  lea     rbp, [rsp-90h]
0x14001f7e4  sub     rsp, 190h
0x14001f7eb  mov     rax, cs:__security_cookie
0x14001f7f2  xor     rax, rsp
0x14001f7f5  mov     [rbp+0B0h+var_30], rax
0x14001f7fc  xor     r15d, r15d
0x14001f7ff  lea     rdi, [rcx+260h]
0x14001f806  xor     eax, eax
0x14001f808  mov     [rdi+8], r15
0x14001f80c  xorps   xmm0, xmm0
0x14001f80f  mov     [rbp+0B0h+var_B8], rax
0x14001f813  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f817  mov     [rdi+10h], r15
0x14001f81b  mov     [rdi], rax
0x14001f81e  mov     rsi, rcx
0x14001f821  movups  [rsp+1B0h+var_148], xmm0
0x14001f826  mov     qword ptr [rsp+1B0h+Acl.AclRevision], r15
0x14001f82b  mov     r14, rdx
0x14001f82e  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x14001f832  mov     qword ptr [rsp+1B0h+var_150], r15
0x14001f837  lea     ecx, [r15+72h]
0x14001f83b  xorps   xmm1, xmm1
0x14001f83e  mov     [rbp+0B0h+FileInformation], r15
0x14001f842  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x14001f846  mov     [rbp+0B0h+var_120], r15
0x14001f84a  mov     rbx, r8
0x14001f84d  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x14001f851  mov     qword ptr [rsp+1B0h+var_148], 740072h
0x14001f85a  movups  [rbp+0B0h+SecurityDescriptor], xmm1
0x14001f85e  movups  [rbp+0B0h+var_C8], xmm1
0x14001f862  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x14001f866  mov     [rdi+18h], rax
0x14001f86a  lea     rax, [rbp+0B0h+var_B0]
0x14001f86e  mov     rdx, [rsi+8]
0x14001f872  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x14001f877  movzx   eax, word ptr [rdx+68h]
0x14001f87b  cmp     ax, cx
0x14001f87e  jbe     short loc_14001F8B6
0x14001f880  mov     ebx, 0C000000Dh
0x14001f885  mov     rcx, rsi
0x14001f888  call    VsmmPioFileClose
0x14001f88d  mov     eax, ebx
0x14001f88f  mov     rcx, [rbp+0B0h+var_30]
0x14001f896  xor     rcx, rsp; StackCookie
0x14001f899  call    __security_check_cookie
0x14001f89e  mov     rbx, [rsp+1B0h+arg_18]
0x14001f8a6  add     rsp, 190h
0x14001f8ad  pop     r15
0x14001f8af  pop     r14
0x14001f8b1  pop     rdi
0x14001f8b2  pop     rsi
0x14001f8b3  pop     rbp
0x14001f8b4  retn
0x14001f8b6  mov     rdx, [rdx+70h]; Src
0x14001f8ba  lea     rcx, [rbp+0B0h+var_B0]; void *
0x14001f8be  mov     r8, rax; Size
0x14001f8c1  call    memmove
0x14001f8c6  mov     rax, [rsi+8]
0x14001f8ca  lea     r8, a016llxSlp; ".%016llX.slp"
0x14001f8d1  movzx   edx, word ptr [rsp+1B0h+var_148+2]
0x14001f8d6  mov     r9, rbx
0x14001f8d9  movzx   ecx, word ptr [rax+68h]
0x14001f8dd  mov     rax, qword ptr [rsp+1B0h+var_148+8]
0x14001f8e2  sub     rdx, rcx; cbDest
0x14001f8e5  shr     rcx, 1
0x14001f8e8  lea     rcx, [rax+rcx*2]; pszDest
0x14001f8ec  call    RtlStringCbPrintfW
0x14001f8f1  mov     ebx, eax
0x14001f8f3  test    eax, eax
0x14001f8f5  js      short loc_14001F885
0x14001f8f7  mov     edx, 8; AclLength
0x14001f8fc  lea     rcx, [rsp+1B0h+Acl]; Acl
0x14001f901  lea     r8d, [rdx-6]; AclRevision
0x14001f905  call    cs:__imp_RtlCreateAcl
0x14001f90c  nop     dword ptr [rax+rax+00h]
0x14001f911  mov     ebx, eax
0x14001f913  test    eax, eax
0x14001f915  js      loc_14001F885
0x14001f91b  mov     edx, 1; Revision
0x14001f920  lea     rcx, [rbp+0B0h+SecurityDescriptor]; SecurityDescriptor
0x14001f924  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001f92b  nop     dword ptr [rax+rax+00h]
0x14001f930  mov     ebx, eax
0x14001f932  test    eax, eax
0x14001f934  js      loc_14001F885
0x14001f93a  xor     r9d, r9d; DaclDefaulted
0x14001f93d  lea     r8, [rsp+1B0h+Acl]; Dacl
0x14001f942  mov     dl, 1; DaclPresent
0x14001f944  lea     rcx, [rbp+0B0h+SecurityDescriptor]; SecurityDescriptor
0x14001f948  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001f94f  nop     dword ptr [rax+rax+00h]
0x14001f954  mov     ebx, eax
0x14001f956  test    eax, eax
0x14001f958  js      loc_14001F885
0x14001f95e  mov     [rsp+1B0h+EaLength], r15d; EaLength
0x14001f963  lea     rax, [rsp+1B0h+var_148]
0x14001f968  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14001f96c  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x14001f970  mov     [rsp+1B0h+EaBuffer], r15; EaBuffer
0x14001f975  lea     rax, [rbp+0B0h+SecurityDescriptor]
0x14001f979  mov     [rbp+0B0h+ObjectAttributes.SecurityDescriptor], rax
0x14001f97d  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x14001f981  mov     rax, [rsi+30h]
0x14001f985  mov     edx, 10183h; DesiredAccess
0x14001f98a  mov     [rsp+1B0h+CreateOptions], 1848h; CreateOptions
0x14001f992  mov     rcx, rdi; FileHandle
0x14001f995  shl     rax, 0Ch
0x14001f999  mov     [rsp+1B0h+CreateDisposition], 5; CreateDisposition
0x14001f9a1  mov     qword ptr [rsp+1B0h+var_150], rax
0x14001f9a6  lea     rax, [rsp+1B0h+var_150]
0x14001f9ab  mov     [rsp+1B0h+ShareAccess], r15d; ShareAccess
0x14001f9b0  mov     [rsp+1B0h+FileAttributes], 80h; FileAttributes
0x14001f9b8  mov     [rsp+1B0h+AllocationSize], rax; AllocationSize
0x14001f9bd  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x14001f9c4  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r14
0x14001f9c8  mov     [rbp+0B0h+ObjectAttributes.Attributes], 200h
0x14001f9cf  mov     [rbp+0B0h+ObjectAttributes.SecurityQualityOfService], r15
0x14001f9d3  call    cs:__imp_ZwCreateFile
0x14001f9da  nop     dword ptr [rax+rax+00h]
0x14001f9df  mov     ebx, eax
0x14001f9e1  test    eax, eax
0x14001f9e3  js      loc_14001F885
0x14001f9e9  mov     rcx, [rdi]; Handle
0x14001f9ec  lea     rax, [rbp+0B0h+Object]
0x14001f9f0  mov     qword ptr [rsp+1B0h+FileAttributes], r15; HandleInformation
0x14001f9f5  xor     r9d, r9d; AccessMode
0x14001f9f8  xor     r8d, r8d; ObjectType
0x14001f9fb  mov     [rsp+1B0h+AllocationSize], rax; Object
0x14001fa00  xor     edx, edx; DesiredAccess
0x14001fa02  mov     [rbp+0B0h+Object], r15
0x14001fa06  call    cs:__imp_ObReferenceObjectByHandle
0x14001fa0d  nop     dword ptr [rax+rax+00h]
0x14001fa12  mov     rcx, [rbp+0B0h+Object]; FileObject
0x14001fa16  mov     ebx, eax
0x14001fa18  mov     [rdi+8], rcx
0x14001fa1c  test    eax, eax
0x14001fa1e  js      loc_14001F885
0x14001fa24  call    cs:__imp_IoGetRelatedDeviceObject
0x14001fa2b  nop     dword ptr [rax+rax+00h]
0x14001fa30  mov     [rdi+10h], rax
0x14001fa34  test    rax, rax
0x14001fa37  jz      loc_14001F880
0x14001fa3d  mov     rax, qword ptr [rsp+1B0h+var_150]
0x14001fa42  lea     r8, [rbp+0B0h+FileInformation]; FileInformation
0x14001fa46  mov     rcx, [rdi]; FileHandle
0x14001fa49  lea     rdx, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x14001fa4d  mov     r9d, 8; Length
0x14001fa53  mov     [rbp+0B0h+FileInformation], rax
0x14001fa57  mov     dword ptr [rsp+1B0h+AllocationSize], 14h; FileInformationClass
0x14001fa5f  call    cs:__imp_ZwSetInformationFile
0x14001fa66  nop     dword ptr [rax+rax+00h]
0x14001fa6b  mov     ebx, eax
0x14001fa6d  test    eax, eax
0x14001fa6f  js      loc_14001F885
0x14001fa75  mov     rax, qword ptr [rsp+1B0h+var_150]
0x14001fa7a  lea     r8, [rbp+0B0h+var_120]; FileInformation
0x14001fa7e  mov     rcx, [rdi]; FileHandle
0x14001fa81  lea     rdx, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x14001fa85  mov     r9d, 8; Length
0x14001fa8b  mov     [rbp+0B0h+var_120], rax
0x14001fa8f  mov     dword ptr [rsp+1B0h+AllocationSize], 27h ; '''; FileInformationClass
0x14001fa97  call    cs:__imp_ZwSetInformationFile
0x14001fa9e  nop     dword ptr [rax+rax+00h]
0x14001faa3  mov     ebx, r15d
0x14001faa6  jmp     loc_14001F88D
```
