# VhdmpiOpenPrefetchFile(_UNICODE_STRING const *,void * *,_VHD_PREFETCH_FILE_HEADER *)

- ea: `0x1400b8af4`
- end: `0x1400b8d3e`
- name: `?VhdmpiOpenPrefetchFile@@YAJPEBU_UNICODE_STRING@@PEAPEAXPEAU_VHD_PREFETCH_FILE_HEADER@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, void **, struct _VHD_PREFETCH_FILE_HEADER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b88dc`

## callees

- `0x140023560`
- `0x140035e94`
- `0x1400b8af4`
- `0x1400b92b8`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400b8c0a`
- `ntoskrnl!ZwCreateFile` at `0x1400b8c0a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8b76`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8b76`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400b8b8d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400b8b8d`
- `ntoskrnl!ZwClose` at `0x1400b8d0e`
- `ntoskrnl!ZwClose` at `0x1400b8d0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8cf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8cf5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8b4c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b8b4c`

## string_xrefs

- `0x1400b8cbd`: `Failed while opening prefetch file: %wZ, status = 0x%08x`
- `0x1400b8c6f`: `VhdmpiOpenPrefetchFile`
- `0x1400b8ccb`: `VhdmpiOpenPrefetchFile`

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
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
        TraceEvents("VhdmpiOpenPrefetchFile", 0x25Au, v11, v10, "Prefetch file not found: %wZ", &DestinationString);
    }
    else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
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
0x1400b8af4  mov     [rsp-8+arg_8], rbx
0x1400b8af9  mov     [rsp-8+arg_10], rsi
0x1400b8afe  push    rbp
0x1400b8aff  push    rdi
0x1400b8b00  push    r14
0x1400b8b02  lea     rbp, [rsp-47h]
0x1400b8b07  sub     rsp, 0B0h
0x1400b8b0e  movzx   esi, word ptr [rcx]
0x1400b8b11  xorps   xmm0, xmm0
0x1400b8b14  mov     rdi, r8
0x1400b8b17  mov     [rbp+57h+FileHandle], 0
0x1400b8b1f  mov     r14, rdx
0x1400b8b22  mov     rbx, rcx
0x1400b8b25  xorps   xmm1, xmm1
0x1400b8b28  add     esi, 14h
0x1400b8b2b  mov     edx, esi
0x1400b8b2d  mov     ecx, 100h
0x1400b8b32  mov     r8d, 46444856h
0x1400b8b38  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400b8b3c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1400b8b40  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400b8b44  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400b8b48  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b8b4c  call    cs:__imp_ExAllocatePool2
0x1400b8b53  nop     dword ptr [rax+rax+00h]
0x1400b8b58  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400b8b5c  test    rax, rax
0x1400b8b5f  jnz     short loc_1400B8B6B
0x1400b8b61  mov     ebx, 0C000009Ah
0x1400b8b66  jmp     loc_1400B8CE7
0x1400b8b6b  mov     rdx, rbx; SourceString
0x1400b8b6e  mov     [rbp+57h+DestinationString.MaximumLength], si
0x1400b8b72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400b8b76  call    cs:__imp_RtlCopyUnicodeString
0x1400b8b7d  nop     dword ptr [rax+rax+00h]
0x1400b8b82  lea     rdx, aPrefetch; ".prefetch"
0x1400b8b89  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400b8b8d  call    cs:__imp_RtlAppendUnicodeToString
0x1400b8b94  nop     dword ptr [rax+rax+00h]
0x1400b8b99  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1400b8ba1  lea     rax, [rbp+57h+DestinationString]
0x1400b8ba5  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1400b8bae  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400b8bb2  mov     [rsp+0C0h+CreateOptions], 60h ; '`'; CreateOptions
0x1400b8bba  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400b8bbe  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x1400b8bc6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400b8bca  mov     dword ptr [rsp+0C0h+ShareAccess], 0; ShareAccess
0x1400b8bd2  xorps   xmm0, xmm0
0x1400b8bd5  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1400b8bdd  mov     edx, 0C0000000h; DesiredAccess
0x1400b8be2  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x1400b8beb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400b8bf2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400b8bfa  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x1400b8c01  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400b8c05  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b8c0a  call    cs:__imp_ZwCreateFile
0x1400b8c11  nop     dword ptr [rax+rax+00h]
0x1400b8c16  mov     ebx, eax
0x1400b8c18  test    eax, eax
0x1400b8c1a  jns     loc_1400B8CD9
0x1400b8c20  cmp     eax, 0C0000034h
0x1400b8c25  jnz     short loc_1400B8C82
0x1400b8c27  mov     ecx, cs:dword_140087708
0x1400b8c2d  mov     r8d, 4
0x1400b8c33  cmp     ecx, r8d
0x1400b8c36  jbe     loc_1400B8CE7
0x1400b8c3c  mov     edx, 10000h
0x1400b8c41  lea     rcx, dword_140087708
0x1400b8c48  call    _tlgKeywordOn
0x1400b8c4d  test    al, al
0x1400b8c4f  jz      loc_1400B8CE7
0x1400b8c55  lea     rax, [rbp+57h+DestinationString]
0x1400b8c59  mov     ecx, 25Ah
0x1400b8c5e  mov     qword ptr [rsp+0C0h+FileAttributes], rax; char
0x1400b8c63  mov     r9d, edx; int
0x1400b8c66  lea     rax, aPrefetchFileNo; "Prefetch file not found: %wZ"
0x1400b8c6d  mov     edx, ecx; int
0x1400b8c6f  lea     rcx, aVhdmpiopenpref; "VhdmpiOpenPrefetchFile"
0x1400b8c76  mov     [rsp+0C0h+AllocationSize], rax; char *
0x1400b8c7b  call    TraceEvents
0x1400b8c80  jmp     short loc_1400B8CE7
0x1400b8c82  mov     eax, cs:dword_140087708
0x1400b8c88  mov     r8d, 2
0x1400b8c8e  cmp     eax, r8d
0x1400b8c91  jbe     short loc_1400B8CE7
0x1400b8c93  mov     edx, 10000h
0x1400b8c98  lea     rcx, dword_140087708
0x1400b8c9f  call    _tlgKeywordOn
0x1400b8ca4  test    al, al
0x1400b8ca6  jz      short loc_1400B8CE7
0x1400b8ca8  lea     rax, [rbp+57h+DestinationString]
0x1400b8cac  mov     dword ptr [rsp+0C0h+ShareAccess], ebx
0x1400b8cb0  mov     qword ptr [rsp+0C0h+FileAttributes], rax; char
0x1400b8cb5  mov     ecx, 261h
0x1400b8cba  mov     r9d, edx; int
0x1400b8cbd  lea     rax, aFailedWhileOpe; "Failed while opening prefetch file: %wZ"...
0x1400b8cc4  mov     edx, ecx; int
0x1400b8cc6  mov     [rsp+0C0h+AllocationSize], rax; char *
0x1400b8ccb  lea     rcx, aVhdmpiopenpref; "VhdmpiOpenPrefetchFile"
0x1400b8cd2  call    TraceEvents
0x1400b8cd7  jmp     short loc_1400B8CE7
0x1400b8cd9  mov     rcx, [rbp+57h+FileHandle]; void *
0x1400b8cdd  mov     rdx, rdi; struct _VHD_PREFETCH_FILE_HEADER *
0x1400b8ce0  call    ?VhdmpiValidatePrefetchFile@@YAJPEAXPEAU_VHD_PREFETCH_FILE_HEADER@@@Z; VhdmpiValidatePrefetchFile(void *,_VHD_PREFETCH_FILE_HEADER *)
0x1400b8ce5  mov     ebx, eax
0x1400b8ce7  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1400b8ceb  test    rcx, rcx
0x1400b8cee  jz      short loc_1400B8D01
0x1400b8cf0  mov     edx, 46444856h; Tag
0x1400b8cf5  call    cs:__imp_ExFreePoolWithTag
0x1400b8cfc  nop     dword ptr [rax+rax+00h]
0x1400b8d01  test    ebx, ebx
0x1400b8d03  jns     short loc_1400B8D1C
0x1400b8d05  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400b8d09  test    rcx, rcx
0x1400b8d0c  jz      short loc_1400B8D23
0x1400b8d0e  call    cs:__imp_ZwClose
0x1400b8d15  nop     dword ptr [rax+rax+00h]
0x1400b8d1a  jmp     short loc_1400B8D23
0x1400b8d1c  mov     rax, [rbp+57h+FileHandle]
0x1400b8d20  mov     [r14], rax
0x1400b8d23  lea     r11, [rsp+0C0h+var_10]
0x1400b8d2b  mov     eax, ebx
0x1400b8d2d  mov     rbx, [r11+28h]
0x1400b8d31  mov     rsi, [r11+30h]
0x1400b8d35  mov     rsp, r11
0x1400b8d38  pop     r14
0x1400b8d3a  pop     rdi
0x1400b8d3b  pop     rbp
0x1400b8d3c  retn
```
