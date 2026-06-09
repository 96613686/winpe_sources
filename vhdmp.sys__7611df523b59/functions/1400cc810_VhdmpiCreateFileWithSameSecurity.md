# VhdmpiCreateFileWithSameSecurity

- ea: `0x1400cc810`
- end: `0x1400cc9aa`
- name: `VhdmpiCreateFileWithSameSecurity`
- size: `410`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, __int64, ULONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004d820`
- `0x1400c75f4`

## callees

- `0x1400cc810`

## import_xrefs

- `ntoskrnl!IoCreateFileEx` at `0x1400cc95a`
- `ntoskrnl!IoCreateFileEx` at `0x1400cc95a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400cc895`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400cc895`
- `ntoskrnl!ZwClose` at `0x1400cc970`
- `ntoskrnl!ZwClose` at `0x1400cc970`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc8b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc984`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc8b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc984`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc865`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc865`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateFileWithSameSecurity(struct _UNICODE_STRING *a1, void *a2, __int64 a3, ULONG a4)
{
  ULONG v4; // eax
  void *Pool2; // rdi
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  void *FileHandle; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-11h] BYREF
  ULONG Length; // [rsp+120h] [rbp+77h] BYREF

  FileHandle = 0;
  v4 = 512;
  IoStatusBlock = 0;
  Length = 512;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  while ( 1 )
  {
    Pool2 = (void *)ExAllocatePool2(256, v4, 2051295318);
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    v9 = ZwQuerySecurityObject(a2, 4u, Pool2, Length, &Length);
    v10 = v9;
    if ( v9 != -1073741789 )
      break;
    ExFreePoolWithTag(Pool2, 0x7A444856u);
    v4 = Length;
  }
  if ( v9 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    ObjectAttributes.SecurityDescriptor = Pool2;
    ObjectAttributes.SecurityQualityOfService = 0;
    v10 = IoCreateFileEx(
            &FileHandle,
            0xC0000000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            1u,
            a4,
            0,
            0,
            0,
            CreateFileTypeNone,
            0,
            0x101u,
            0);
    if ( v10 >= 0 )
      ZwClose(FileHandle);
  }
  ExFreePoolWithTag(Pool2, 0x7A444856u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400cc810  mov     [rsp-8+Length], r8d
0x1400cc815  push    rbp
0x1400cc816  push    rbx
0x1400cc817  push    rsi
0x1400cc818  push    rdi
0x1400cc819  push    r14
0x1400cc81b  push    r15
0x1400cc81d  lea     rbp, [rsp-2Fh]
0x1400cc822  sub     rsp, 0D8h
0x1400cc829  xorps   xmm1, xmm1
0x1400cc82c  mov     [rbp+57h+FileHandle], 0
0x1400cc834  xorps   xmm0, xmm0
0x1400cc837  mov     eax, 200h
0x1400cc83c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400cc840  mov     [rbp+57h+Length], eax
0x1400cc843  mov     esi, r9d
0x1400cc846  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400cc84a  mov     r15, rdx
0x1400cc84d  mov     r14, rcx
0x1400cc850  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400cc854  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400cc858  mov     edx, eax
0x1400cc85a  mov     ecx, 100h
0x1400cc85f  mov     r8d, 7A444856h
0x1400cc865  call    cs:__imp_ExAllocatePool2
0x1400cc86c  nop     dword ptr [rax+rax+00h]
0x1400cc871  mov     rdi, rax
0x1400cc874  test    rax, rax
0x1400cc877  jz      loc_1400CC992
0x1400cc87d  mov     r9d, [rbp+57h+Length]; Length
0x1400cc881  lea     rax, [rbp+57h+Length]
0x1400cc885  mov     r8, rdi; SecurityDescriptor
0x1400cc888  mov     [rsp+100h+LengthNeeded], rax; LengthNeeded
0x1400cc88d  mov     edx, 4; SecurityInformation
0x1400cc892  mov     rcx, r15; Handle
0x1400cc895  call    cs:__imp_ZwQuerySecurityObject
0x1400cc89c  nop     dword ptr [rax+rax+00h]
0x1400cc8a1  mov     ebx, eax
0x1400cc8a3  cmp     eax, 0C0000023h
0x1400cc8a8  jnz     short loc_1400CC8C3
0x1400cc8aa  mov     edx, 7A444856h; Tag
0x1400cc8af  mov     rcx, rdi; P
0x1400cc8b2  call    cs:__imp_ExFreePoolWithTag
0x1400cc8b9  nop     dword ptr [rax+rax+00h]
0x1400cc8be  mov     eax, [rbp+57h+Length]
0x1400cc8c1  jmp     short loc_1400CC858
0x1400cc8c3  test    eax, eax
0x1400cc8c5  js      loc_1400CC97C
0x1400cc8cb  mov     [rsp+100h+DriverContext], 0; DriverContext
0x1400cc8d4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400cc8d8  mov     [rsp+100h+Options], 101h; Options
0x1400cc8e0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400cc8e4  mov     [rsp+100h+InternalParameters], 0; InternalParameters
0x1400cc8ed  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400cc8f1  mov     [rsp+100h+CreateFileType], 0; CreateFileType
0x1400cc8f9  mov     edx, 0C0000000h; DesiredAccess
0x1400cc8fe  mov     [rsp+100h+EaLength], 0; EaLength
0x1400cc906  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x1400cc90f  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x1400cc917  mov     [rsp+100h+Disposition], esi; Disposition
0x1400cc91b  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x1400cc923  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1400cc92b  mov     [rsp+100h+LengthNeeded], 0; AllocationSize
0x1400cc934  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400cc93b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400cc943  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400cc94a  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1400cc94e  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x1400cc952  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x1400cc95a  call    cs:__imp_IoCreateFileEx
0x1400cc961  nop     dword ptr [rax+rax+00h]
0x1400cc966  mov     ebx, eax
0x1400cc968  test    eax, eax
0x1400cc96a  js      short loc_1400CC97C
0x1400cc96c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400cc970  call    cs:__imp_ZwClose
0x1400cc977  nop     dword ptr [rax+rax+00h]
0x1400cc97c  mov     edx, 7A444856h; Tag
0x1400cc981  mov     rcx, rdi; P
0x1400cc984  call    cs:__imp_ExFreePoolWithTag
0x1400cc98b  nop     dword ptr [rax+rax+00h]
0x1400cc990  jmp     short loc_1400CC997
0x1400cc992  mov     ebx, 0C000009Ah
0x1400cc997  mov     eax, ebx
0x1400cc999  add     rsp, 0D8h
0x1400cc9a0  pop     r15
0x1400cc9a2  pop     r14
0x1400cc9a4  pop     rdi
0x1400cc9a5  pop     rsi
0x1400cc9a6  pop     rbx
0x1400cc9a7  pop     rbp
0x1400cc9a8  retn
```
