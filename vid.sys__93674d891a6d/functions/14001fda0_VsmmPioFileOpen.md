# VsmmPioFileOpen

- ea: `0x14001fda0`
- end: `0x14002007b`
- name: `VsmmPioFileOpen`
- size: `731`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400e3a80`
- `0x1400e44c8`

## callees

- `0x1400080f4`
- `0x14001fd50`
- `0x14001fda0`
- `0x140021c60`
- `0x140022340`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ffd6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ffd6`
- `ntoskrnl!ZwSetInformationFile` at `0x14002002f`
- `ntoskrnl!ZwSetInformationFile` at `0x140020067`
- `ntoskrnl!ZwSetInformationFile` at `0x14002002f`
- `ntoskrnl!ZwSetInformationFile` at `0x140020067`
- `ntoskrnl!ZwCreateFile` at `0x14001ffa3`
- `ntoskrnl!ZwCreateFile` at `0x14001ffa3`
- `ntoskrnl!RtlCreateAcl` at `0x14001fed5`
- `ntoskrnl!RtlCreateAcl` at `0x14001fed5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001fef4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001fef4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001ff18`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001ff18`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001fff4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001fff4`

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

  v3 = (void **)(a1 + 85);
  a1[86] = 0;
  v27 = 0;
  a1[87] = 0;
  a1[85] = -1;
  Acl = 0;
  AllocationSize.QuadPart = 0;
  FileInformation.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  v23.QuadPart = 0;
  v19 = 0x740072u;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  IoStatusBlock = 0;
  a1[88] = -1;
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
0x14001fda0  mov     [rsp-8+arg_18], rbx
0x14001fda5  push    rbp
0x14001fda6  push    rsi
0x14001fda7  push    rdi
0x14001fda8  push    r14
0x14001fdaa  push    r15
0x14001fdac  lea     rbp, [rsp-90h]
0x14001fdb4  sub     rsp, 190h
0x14001fdbb  mov     rax, cs:__security_cookie
0x14001fdc2  xor     rax, rsp
0x14001fdc5  mov     [rbp+0B0h+var_30], rax
0x14001fdcc  xor     r15d, r15d
0x14001fdcf  lea     rdi, [rcx+2A8h]
0x14001fdd6  xor     eax, eax
0x14001fdd8  mov     [rdi+8], r15
0x14001fddc  xorps   xmm0, xmm0
0x14001fddf  mov     [rbp+0B0h+var_B8], rax
0x14001fde3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001fde7  mov     [rdi+10h], r15
0x14001fdeb  mov     [rdi], rax
0x14001fdee  mov     rsi, rcx
0x14001fdf1  movups  [rsp+1B0h+var_148], xmm0
0x14001fdf6  mov     qword ptr [rsp+1B0h+Acl.AclRevision], r15
0x14001fdfb  mov     r14, rdx
0x14001fdfe  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x14001fe02  mov     qword ptr [rsp+1B0h+var_150], r15
0x14001fe07  lea     ecx, [r15+72h]
0x14001fe0b  xorps   xmm1, xmm1
0x14001fe0e  mov     [rbp+0B0h+FileInformation], r15
0x14001fe12  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x14001fe16  mov     [rbp+0B0h+var_120], r15
0x14001fe1a  mov     rbx, r8
0x14001fe1d  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x14001fe21  mov     qword ptr [rsp+1B0h+var_148], 740072h
0x14001fe2a  movups  [rbp+0B0h+SecurityDescriptor], xmm1
0x14001fe2e  movups  [rbp+0B0h+var_C8], xmm1
0x14001fe32  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x14001fe36  mov     [rdi+18h], rax
0x14001fe3a  lea     rax, [rbp+0B0h+var_B0]
0x14001fe3e  mov     rdx, [rsi+8]
0x14001fe42  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x14001fe47  movzx   eax, word ptr [rdx+68h]
0x14001fe4b  cmp     ax, cx
0x14001fe4e  jbe     short loc_14001FE86
0x14001fe50  mov     ebx, 0C000000Dh
0x14001fe55  mov     rcx, rsi
0x14001fe58  call    VsmmPioFileClose
0x14001fe5d  mov     eax, ebx
0x14001fe5f  mov     rcx, [rbp+0B0h+var_30]
0x14001fe66  xor     rcx, rsp; StackCookie
0x14001fe69  call    __security_check_cookie
0x14001fe6e  mov     rbx, [rsp+1B0h+arg_18]
0x14001fe76  add     rsp, 190h
0x14001fe7d  pop     r15
0x14001fe7f  pop     r14
0x14001fe81  pop     rdi
0x14001fe82  pop     rsi
0x14001fe83  pop     rbp
0x14001fe84  retn
0x14001fe86  mov     rdx, [rdx+70h]; Src
0x14001fe8a  lea     rcx, [rbp+0B0h+var_B0]; void *
0x14001fe8e  mov     r8, rax; Size
0x14001fe91  call    memmove
0x14001fe96  mov     rax, [rsi+8]
0x14001fe9a  lea     r8, a016llxSlp; ".%016llX.slp"
0x14001fea1  movzx   edx, word ptr [rsp+1B0h+var_148+2]
0x14001fea6  mov     r9, rbx
0x14001fea9  movzx   ecx, word ptr [rax+68h]
0x14001fead  mov     rax, qword ptr [rsp+1B0h+var_148+8]
0x14001feb2  sub     rdx, rcx; cbDest
0x14001feb5  shr     rcx, 1
0x14001feb8  lea     rcx, [rax+rcx*2]; pszDest
0x14001febc  call    RtlStringCbPrintfW
0x14001fec1  mov     ebx, eax
0x14001fec3  test    eax, eax
0x14001fec5  js      short loc_14001FE55
0x14001fec7  mov     edx, 8; AclLength
0x14001fecc  lea     rcx, [rsp+1B0h+Acl]; Acl
0x14001fed1  lea     r8d, [rdx-6]; AclRevision
0x14001fed5  call    cs:__imp_RtlCreateAcl
0x14001fedc  nop     dword ptr [rax+rax+00h]
0x14001fee1  mov     ebx, eax
0x14001fee3  test    eax, eax
0x14001fee5  js      loc_14001FE55
0x14001feeb  mov     edx, 1; Revision
0x14001fef0  lea     rcx, [rbp+0B0h+SecurityDescriptor]; SecurityDescriptor
0x14001fef4  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001fefb  nop     dword ptr [rax+rax+00h]
0x14001ff00  mov     ebx, eax
0x14001ff02  test    eax, eax
0x14001ff04  js      loc_14001FE55
0x14001ff0a  xor     r9d, r9d; DaclDefaulted
0x14001ff0d  lea     r8, [rsp+1B0h+Acl]; Dacl
0x14001ff12  mov     dl, 1; DaclPresent
0x14001ff14  lea     rcx, [rbp+0B0h+SecurityDescriptor]; SecurityDescriptor
0x14001ff18  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001ff1f  nop     dword ptr [rax+rax+00h]
0x14001ff24  mov     ebx, eax
0x14001ff26  test    eax, eax
0x14001ff28  js      loc_14001FE55
0x14001ff2e  mov     [rsp+1B0h+EaLength], r15d; EaLength
0x14001ff33  lea     rax, [rsp+1B0h+var_148]
0x14001ff38  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14001ff3c  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x14001ff40  mov     [rsp+1B0h+EaBuffer], r15; EaBuffer
0x14001ff45  lea     rax, [rbp+0B0h+SecurityDescriptor]
0x14001ff49  mov     [rbp+0B0h+ObjectAttributes.SecurityDescriptor], rax
0x14001ff4d  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x14001ff51  mov     rax, [rsi+30h]
0x14001ff55  mov     edx, 10183h; DesiredAccess
0x14001ff5a  mov     [rsp+1B0h+CreateOptions], 1848h; CreateOptions
0x14001ff62  mov     rcx, rdi; FileHandle
0x14001ff65  shl     rax, 0Ch
0x14001ff69  mov     [rsp+1B0h+CreateDisposition], 5; CreateDisposition
0x14001ff71  mov     qword ptr [rsp+1B0h+var_150], rax
0x14001ff76  lea     rax, [rsp+1B0h+var_150]
0x14001ff7b  mov     [rsp+1B0h+ShareAccess], r15d; ShareAccess
0x14001ff80  mov     [rsp+1B0h+FileAttributes], 80h; FileAttributes
0x14001ff88  mov     [rsp+1B0h+AllocationSize], rax; AllocationSize
0x14001ff8d  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x14001ff94  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r14
0x14001ff98  mov     [rbp+0B0h+ObjectAttributes.Attributes], 200h
0x14001ff9f  mov     [rbp+0B0h+ObjectAttributes.SecurityQualityOfService], r15
0x14001ffa3  call    cs:__imp_ZwCreateFile
0x14001ffaa  nop     dword ptr [rax+rax+00h]
0x14001ffaf  mov     ebx, eax
0x14001ffb1  test    eax, eax
0x14001ffb3  js      loc_14001FE55
0x14001ffb9  mov     rcx, [rdi]; Handle
0x14001ffbc  lea     rax, [rbp+0B0h+Object]
0x14001ffc0  mov     qword ptr [rsp+1B0h+FileAttributes], r15; HandleInformation
0x14001ffc5  xor     r9d, r9d; AccessMode
0x14001ffc8  xor     r8d, r8d; ObjectType
0x14001ffcb  mov     [rsp+1B0h+AllocationSize], rax; Object
0x14001ffd0  xor     edx, edx; DesiredAccess
0x14001ffd2  mov     [rbp+0B0h+Object], r15
0x14001ffd6  call    cs:__imp_ObReferenceObjectByHandle
0x14001ffdd  nop     dword ptr [rax+rax+00h]
0x14001ffe2  mov     rcx, [rbp+0B0h+Object]; FileObject
0x14001ffe6  mov     ebx, eax
0x14001ffe8  mov     [rdi+8], rcx
0x14001ffec  test    eax, eax
0x14001ffee  js      loc_14001FE55
0x14001fff4  call    cs:__imp_IoGetRelatedDeviceObject
0x14001fffb  nop     dword ptr [rax+rax+00h]
0x140020000  mov     [rdi+10h], rax
0x140020004  test    rax, rax
0x140020007  jz      loc_14001FE50
0x14002000d  mov     rax, qword ptr [rsp+1B0h+var_150]
0x140020012  lea     r8, [rbp+0B0h+FileInformation]; FileInformation
0x140020016  mov     rcx, [rdi]; FileHandle
0x140020019  lea     rdx, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x14002001d  mov     r9d, 8; Length
0x140020023  mov     [rbp+0B0h+FileInformation], rax
0x140020027  mov     dword ptr [rsp+1B0h+AllocationSize], 14h; FileInformationClass
0x14002002f  call    cs:__imp_ZwSetInformationFile
0x140020036  nop     dword ptr [rax+rax+00h]
0x14002003b  mov     ebx, eax
0x14002003d  test    eax, eax
0x14002003f  js      loc_14001FE55
0x140020045  mov     rax, qword ptr [rsp+1B0h+var_150]
0x14002004a  lea     r8, [rbp+0B0h+var_120]; FileInformation
0x14002004e  mov     rcx, [rdi]; FileHandle
0x140020051  lea     rdx, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x140020055  mov     r9d, 8; Length
0x14002005b  mov     [rbp+0B0h+var_120], rax
0x14002005f  mov     dword ptr [rsp+1B0h+AllocationSize], 27h ; '''; FileInformationClass
0x140020067  call    cs:__imp_ZwSetInformationFile
0x14002006e  nop     dword ptr [rax+rax+00h]
0x140020073  mov     ebx, r15d
0x140020076  jmp     loc_14001FE5D
```
