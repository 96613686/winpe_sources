# VhdmpiOpenPrefetchFile(_UNICODE_STRING const *,void * *,_VHD_PREFETCH_FILE_HEADER *)

- ea: `0x1400b8ae4`
- end: `0x1400b8d2e`
- name: `?VhdmpiOpenPrefetchFile@@YAJPEBU_UNICODE_STRING@@PEAPEAXPEAU_VHD_PREFETCH_FILE_HEADER@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, void **, struct _VHD_PREFETCH_FILE_HEADER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b88cc`

## callees

- `0x140023980`
- `0x140036284`
- `0x1400b8ae4`
- `0x1400b92a8`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400b8bfa`
- `ntoskrnl!ZwCreateFile` at `0x1400b8bfa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8b66`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8b66`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400b8b7d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400b8b7d`
- `ntoskrnl!ZwClose` at `0x1400b8cfe`
- `ntoskrnl!ZwClose` at `0x1400b8cfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8ce5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8ce5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8b3c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8b3c`

## string_xrefs

- `0x1400b8cad`: `Failed while opening prefetch file: %wZ, status = 0x%08x`
- `0x1400b8c5f`: `VhdmpiOpenPrefetchFile`
- `0x1400b8cbb`: `VhdmpiOpenPrefetchFile`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenPrefetchFile(
        PCUNICODE_STRING SourceString,
        void **a2,
        struct _VHD_PREFETCH_FILE_HEADER *a3)
{
  int Length; // esi
  unsigned int v7; // esi
  int v8; // ebx
  NTSTATUS v9; // eax
  unsigned int v10; // edx
  unsigned __int8 v11; // r8
  unsigned int v12; // edx
  unsigned __int8 v13; // r8
  __int64 ShareAccess; // [rsp+30h] [rbp-39h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+67h] BYREF

  Length = SourceString->Length;
  FileHandle = 0;
  v7 = Length + 20;
  *(_QWORD *)&DestinationString.Length = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v7, 1178880086);
  if ( DestinationString.Buffer )
  {
    DestinationString.MaximumLength = v7;
    RtlCopyUnicodeString(&DestinationString, SourceString);
    RtlAppendUnicodeToString(&DestinationString, L".prefetch");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1600;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwCreateFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x60u, 0, 0);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v8 = VhdmpiValidatePrefetchFile(FileHandle, a3);
    }
    else if ( v9 == -1073741772 )
    {
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
        TraceEvents("VhdmpiOpenPrefetchFile", 0x25Au, v11, v10, "Prefetch file not found: %wZ", &DestinationString);
    }
    else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      LODWORD(ShareAccess) = v8;
      TraceEvents(
        "VhdmpiOpenPrefetchFile",
        0x261u,
        v13,
        v12,
        "Failed while opening prefetch file: %wZ, status = 0x%08x",
        &DestinationString,
        ShareAccess);
    }
  }
  else
  {
    v8 = -1073741670;
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x46444856u);
  if ( v8 >= 0 )
  {
    *a2 = FileHandle;
  }
  else if ( FileHandle )
  {
    ZwClose(FileHandle);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b8ae4  mov     [rsp-8+arg_8], rbx
0x1400b8ae9  mov     [rsp-8+arg_10], rsi
0x1400b8aee  push    rbp
0x1400b8aef  push    rdi
0x1400b8af0  push    r14
0x1400b8af2  lea     rbp, [rsp-47h]
0x1400b8af7  sub     rsp, 0B0h
0x1400b8afe  movzx   esi, word ptr [rcx]
0x1400b8b01  xorps   xmm0, xmm0
0x1400b8b04  mov     rdi, r8
0x1400b8b07  mov     [rbp+57h+FileHandle], 0
0x1400b8b0f  mov     r14, rdx
0x1400b8b12  mov     rbx, rcx
0x1400b8b15  xorps   xmm1, xmm1
0x1400b8b18  add     esi, 14h
0x1400b8b1b  mov     edx, esi
0x1400b8b1d  mov     ecx, 100h
0x1400b8b22  mov     r8d, 46444856h
0x1400b8b28  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400b8b2c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1400b8b30  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400b8b34  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400b8b38  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b8b3c  call    cs:__imp_ExAllocatePool2
0x1400b8b43  nop     dword ptr [rax+rax+00h]
0x1400b8b48  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400b8b4c  test    rax, rax
0x1400b8b4f  jnz     short loc_1400B8B5B
0x1400b8b51  mov     ebx, 0C000009Ah
0x1400b8b56  jmp     loc_1400B8CD7
0x1400b8b5b  mov     rdx, rbx; SourceString
0x1400b8b5e  mov     [rbp+57h+DestinationString.MaximumLength], si
0x1400b8b62  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400b8b66  call    cs:__imp_RtlCopyUnicodeString
0x1400b8b6d  nop     dword ptr [rax+rax+00h]
0x1400b8b72  lea     rdx, aPrefetch; ".prefetch"
0x1400b8b79  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400b8b7d  call    cs:__imp_RtlAppendUnicodeToString
0x1400b8b84  nop     dword ptr [rax+rax+00h]
0x1400b8b89  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1400b8b91  lea     rax, [rbp+57h+DestinationString]
0x1400b8b95  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1400b8b9e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400b8ba2  mov     [rsp+0C0h+CreateOptions], 60h ; '`'; CreateOptions
0x1400b8baa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400b8bae  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x1400b8bb6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400b8bba  mov     dword ptr [rsp+0C0h+ShareAccess], 0; ShareAccess
0x1400b8bc2  xorps   xmm0, xmm0
0x1400b8bc5  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1400b8bcd  mov     edx, 0C0000000h; DesiredAccess
0x1400b8bd2  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x1400b8bdb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400b8be2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400b8bea  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x1400b8bf1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400b8bf5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b8bfa  call    cs:__imp_ZwCreateFile
0x1400b8c01  nop     dword ptr [rax+rax+00h]
0x1400b8c06  mov     ebx, eax
0x1400b8c08  test    eax, eax
0x1400b8c0a  jns     loc_1400B8CC9
0x1400b8c10  cmp     eax, 0C0000034h
0x1400b8c15  jnz     short loc_1400B8C72
0x1400b8c17  mov     ecx, cs:dword_1400876D0
0x1400b8c1d  mov     r8d, 4
0x1400b8c23  cmp     ecx, r8d
0x1400b8c26  jbe     loc_1400B8CD7
0x1400b8c2c  mov     edx, 10000h
0x1400b8c31  lea     rcx, dword_1400876D0
0x1400b8c38  call    _tlgKeywordOn
0x1400b8c3d  test    al, al
0x1400b8c3f  jz      loc_1400B8CD7
0x1400b8c45  lea     rax, [rbp+57h+DestinationString]
0x1400b8c49  mov     ecx, 25Ah
0x1400b8c4e  mov     qword ptr [rsp+0C0h+FileAttributes], rax; char
0x1400b8c53  mov     r9d, edx; int
0x1400b8c56  lea     rax, aPrefetchFileNo; "Prefetch file not found: %wZ"
0x1400b8c5d  mov     edx, ecx; int
0x1400b8c5f  lea     rcx, aVhdmpiopenpref; "VhdmpiOpenPrefetchFile"
0x1400b8c66  mov     [rsp+0C0h+AllocationSize], rax; char *
0x1400b8c6b  call    TraceEvents
0x1400b8c70  jmp     short loc_1400B8CD7
0x1400b8c72  mov     eax, cs:dword_1400876D0
0x1400b8c78  mov     r8d, 2
0x1400b8c7e  cmp     eax, r8d
0x1400b8c81  jbe     short loc_1400B8CD7
0x1400b8c83  mov     edx, 10000h
0x1400b8c88  lea     rcx, dword_1400876D0
0x1400b8c8f  call    _tlgKeywordOn
0x1400b8c94  test    al, al
0x1400b8c96  jz      short loc_1400B8CD7
0x1400b8c98  lea     rax, [rbp+57h+DestinationString]
0x1400b8c9c  mov     dword ptr [rsp+0C0h+ShareAccess], ebx
0x1400b8ca0  mov     qword ptr [rsp+0C0h+FileAttributes], rax; char
0x1400b8ca5  mov     ecx, 261h
0x1400b8caa  mov     r9d, edx; int
0x1400b8cad  lea     rax, aFailedWhileOpe; "Failed while opening prefetch file: %wZ"...
0x1400b8cb4  mov     edx, ecx; int
0x1400b8cb6  mov     [rsp+0C0h+AllocationSize], rax; char *
0x1400b8cbb  lea     rcx, aVhdmpiopenpref; "VhdmpiOpenPrefetchFile"
0x1400b8cc2  call    TraceEvents
0x1400b8cc7  jmp     short loc_1400B8CD7
0x1400b8cc9  mov     rcx, [rbp+57h+FileHandle]; void *
0x1400b8ccd  mov     rdx, rdi; struct _VHD_PREFETCH_FILE_HEADER *
0x1400b8cd0  call    ?VhdmpiValidatePrefetchFile@@YAJPEAXPEAU_VHD_PREFETCH_FILE_HEADER@@@Z; VhdmpiValidatePrefetchFile(void *,_VHD_PREFETCH_FILE_HEADER *)
0x1400b8cd5  mov     ebx, eax
0x1400b8cd7  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1400b8cdb  test    rcx, rcx
0x1400b8cde  jz      short loc_1400B8CF1
0x1400b8ce0  mov     edx, 46444856h; Tag
0x1400b8ce5  call    cs:__imp_ExFreePoolWithTag
0x1400b8cec  nop     dword ptr [rax+rax+00h]
0x1400b8cf1  test    ebx, ebx
0x1400b8cf3  jns     short loc_1400B8D0C
0x1400b8cf5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400b8cf9  test    rcx, rcx
0x1400b8cfc  jz      short loc_1400B8D13
0x1400b8cfe  call    cs:__imp_ZwClose
0x1400b8d05  nop     dword ptr [rax+rax+00h]
0x1400b8d0a  jmp     short loc_1400B8D13
0x1400b8d0c  mov     rax, [rbp+57h+FileHandle]
0x1400b8d10  mov     [r14], rax
0x1400b8d13  lea     r11, [rsp+0C0h+var_10]
0x1400b8d1b  mov     eax, ebx
0x1400b8d1d  mov     rbx, [r11+28h]
0x1400b8d21  mov     rsi, [r11+30h]
0x1400b8d25  mov     rsp, r11
0x1400b8d28  pop     r14
0x1400b8d2a  pop     rdi
0x1400b8d2b  pop     rbp
0x1400b8d2c  retn
```
