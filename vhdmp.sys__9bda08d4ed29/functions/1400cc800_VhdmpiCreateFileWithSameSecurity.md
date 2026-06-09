# VhdmpiCreateFileWithSameSecurity

- ea: `0x1400cc800`
- end: `0x1400cc99a`
- name: `VhdmpiCreateFileWithSameSecurity`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004dc10`
- `0x1400c75e4`

## callees

- `0x1400cc800`

## import_xrefs

- `ntoskrnl!IoCreateFileEx` at `0x1400cc94a`
- `ntoskrnl!IoCreateFileEx` at `0x1400cc94a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400cc885`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400cc885`
- `ntoskrnl!ZwClose` at `0x1400cc960`
- `ntoskrnl!ZwClose` at `0x1400cc960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc974`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc974`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc855`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc855`

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
0x1400cc800  mov     [rsp-8+Length], r8d
0x1400cc805  push    rbp
0x1400cc806  push    rbx
0x1400cc807  push    rsi
0x1400cc808  push    rdi
0x1400cc809  push    r14
0x1400cc80b  push    r15
0x1400cc80d  lea     rbp, [rsp-2Fh]
0x1400cc812  sub     rsp, 0D8h
0x1400cc819  xorps   xmm1, xmm1
0x1400cc81c  mov     [rbp+57h+FileHandle], 0
0x1400cc824  xorps   xmm0, xmm0
0x1400cc827  mov     eax, 200h
0x1400cc82c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400cc830  mov     [rbp+57h+Length], eax
0x1400cc833  mov     esi, r9d
0x1400cc836  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400cc83a  mov     r15, rdx
0x1400cc83d  mov     r14, rcx
0x1400cc840  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400cc844  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400cc848  mov     edx, eax
0x1400cc84a  mov     ecx, 100h
0x1400cc84f  mov     r8d, 7A444856h
0x1400cc855  call    cs:__imp_ExAllocatePool2
0x1400cc85c  nop     dword ptr [rax+rax+00h]
0x1400cc861  mov     rdi, rax
0x1400cc864  test    rax, rax
0x1400cc867  jz      loc_1400CC982
0x1400cc86d  mov     r9d, [rbp+57h+Length]; Length
0x1400cc871  lea     rax, [rbp+57h+Length]
0x1400cc875  mov     r8, rdi; SecurityDescriptor
0x1400cc878  mov     [rsp+100h+LengthNeeded], rax; LengthNeeded
0x1400cc87d  mov     edx, 4; SecurityInformation
0x1400cc882  mov     rcx, r15; Handle
0x1400cc885  call    cs:__imp_ZwQuerySecurityObject
0x1400cc88c  nop     dword ptr [rax+rax+00h]
0x1400cc891  mov     ebx, eax
0x1400cc893  cmp     eax, 0C0000023h
0x1400cc898  jnz     short loc_1400CC8B3
0x1400cc89a  mov     edx, 7A444856h; Tag
0x1400cc89f  mov     rcx, rdi; P
0x1400cc8a2  call    cs:__imp_ExFreePoolWithTag
0x1400cc8a9  nop     dword ptr [rax+rax+00h]
0x1400cc8ae  mov     eax, [rbp+57h+Length]
0x1400cc8b1  jmp     short loc_1400CC848
0x1400cc8b3  test    eax, eax
0x1400cc8b5  js      loc_1400CC96C
0x1400cc8bb  mov     [rsp+100h+DriverContext], 0; DriverContext
0x1400cc8c4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400cc8c8  mov     [rsp+100h+Options], 101h; Options
0x1400cc8d0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400cc8d4  mov     [rsp+100h+InternalParameters], 0; InternalParameters
0x1400cc8dd  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400cc8e1  mov     [rsp+100h+CreateFileType], 0; CreateFileType
0x1400cc8e9  mov     edx, 0C0000000h; DesiredAccess
0x1400cc8ee  mov     [rsp+100h+EaLength], 0; EaLength
0x1400cc8f6  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x1400cc8ff  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x1400cc907  mov     [rsp+100h+Disposition], esi; Disposition
0x1400cc90b  mov     [rsp+100h+ShareAccess], 1; ShareAccess
0x1400cc913  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1400cc91b  mov     [rsp+100h+LengthNeeded], 0; AllocationSize
0x1400cc924  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400cc92b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400cc933  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400cc93a  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1400cc93e  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdi
0x1400cc942  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x1400cc94a  call    cs:__imp_IoCreateFileEx
0x1400cc951  nop     dword ptr [rax+rax+00h]
0x1400cc956  mov     ebx, eax
0x1400cc958  test    eax, eax
0x1400cc95a  js      short loc_1400CC96C
0x1400cc95c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400cc960  call    cs:__imp_ZwClose
0x1400cc967  nop     dword ptr [rax+rax+00h]
0x1400cc96c  mov     edx, 7A444856h; Tag
0x1400cc971  mov     rcx, rdi; P
0x1400cc974  call    cs:__imp_ExFreePoolWithTag
0x1400cc97b  nop     dword ptr [rax+rax+00h]
0x1400cc980  jmp     short loc_1400CC987
0x1400cc982  mov     ebx, 0C000009Ah
0x1400cc987  mov     eax, ebx
0x1400cc989  add     rsp, 0D8h
0x1400cc990  pop     r15
0x1400cc992  pop     r14
0x1400cc994  pop     rdi
0x1400cc995  pop     rsi
0x1400cc996  pop     rbx
0x1400cc997  pop     rbp
0x1400cc998  retn
```
