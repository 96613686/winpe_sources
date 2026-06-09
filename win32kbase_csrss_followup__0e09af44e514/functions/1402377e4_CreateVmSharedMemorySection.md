# CreateVmSharedMemorySection

- ea: `0x1402377e4`
- end: `0x1402379db`
- name: `CreateVmSharedMemorySection`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14022eb40`

## callees

- `0x1402377e4`
- `0x1402379e4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140237996`
- `ntoskrnl!ZwClose` at `0x140237996`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402379b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402379b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402379c0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402379c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140237884`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140237884`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402378b8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402378b8`
- `ntoskrnl!ExAllocatePool2` at `0x14023785a`
- `ntoskrnl!ExAllocatePool2` at `0x14023785a`
- `ntoskrnl!ZwCreateSection` at `0x140237974`
- `ntoskrnl!ZwCreateSection` at `0x140237974`
- `ntoskrnl!ZwCreateFile` at `0x14023793b`
- `ntoskrnl!ZwCreateFile` at `0x14023793b`

## pseudocode

```c
__int64 __fastcall CreateVmSharedMemorySection(void **a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // rcx
  NTSTATUS appended; // ebx
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-51h] BYREF
  void *SectionHandle; // [rsp+78h] [rbp-41h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+Fh] BYREF

  FileHandle = 0;
  v5 = *a4;
  SectionHandle = 0;
  AllocationSize.QuadPart = (v5 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  Source = 0;
  Destination = 0;
  if ( v5 > 0 )
  {
    Destination.MaximumLength = 224;
    Destination.Buffer = (PWSTR)ExAllocatePool2(64, 224, 1801932115);
    if ( Destination.Buffer )
    {
      appended = RtlAppendUnicodeToString(
                   &Destination,
                   L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$\\");
      if ( appended >= 0 )
      {
        appended = StringFromGuid(a2, &Source);
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, &Source);
          if ( appended >= 0 )
          {
            ObjectAttributes.ObjectName = &Destination;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            appended = ZwCreateFile(
                         &FileHandle,
                         3u,
                         &ObjectAttributes,
                         &IoStatusBlock,
                         &AllocationSize,
                         0x80u,
                         0,
                         3u,
                         0,
                         0,
                         0);
            if ( appended >= 0 )
            {
              appended = ZwCreateSection(&SectionHandle, 6u, 0, 0, 4u, 0x8000000u, FileHandle);
              if ( appended >= 0 )
                *a1 = SectionHandle;
            }
          }
        }
      }
    }
    else
    {
      appended = -1073741670;
    }
    if ( FileHandle )
      ZwClose(FileHandle);
  }
  else
  {
    appended = -1073741582;
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x6B674D53u);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1402377e4  push    rbp
0x1402377e6  push    rbx
0x1402377e7  push    rsi
0x1402377e8  push    rdi
0x1402377e9  lea     rbp, [rsp-2Fh]
0x1402377ee  sub     rsp, 0E8h
0x1402377f5  xor     eax, eax
0x1402377f7  xorps   xmm0, xmm0
0x1402377fa  mov     [rbp+47h+FileHandle], rax
0x1402377fe  mov     rsi, rcx
0x140237801  mov     rcx, [r9]
0x140237804  xorps   xmm1, xmm1
0x140237807  mov     [rbp+47h+SectionHandle], rax
0x14023780b  mov     rdi, rdx
0x14023780e  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x140237812  lea     rax, [rcx+0FFFh]
0x140237819  and     rax, 0FFFFFFFFFFFFF000h
0x14023781f  mov     qword ptr [rbp+47h+var_80], rax
0x140237823  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x140237827  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14023782b  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x14023782f  movups  xmmword ptr [rbp+47h+Source.Length], xmm1
0x140237833  movups  xmmword ptr [rbp+47h+Destination.Length], xmm0
0x140237837  test    rcx, rcx
0x14023783a  jg      short loc_140237846
0x14023783c  mov     ebx, 0C00000F2h
0x140237841  jmp     loc_1402379A2
0x140237846  mov     edx, 0E0h
0x14023784b  mov     ecx, 40h ; '@'
0x140237850  mov     r8d, 6B674D53h
0x140237856  mov     [rbp+47h+Destination.MaximumLength], dx
0x14023785a  call    cs:__imp_ExAllocatePool2
0x140237861  nop     dword ptr [rax+rax+00h]
0x140237866  mov     [rbp+47h+Destination.Buffer], rax
0x14023786a  test    rax, rax
0x14023786d  jnz     short loc_140237879
0x14023786f  mov     ebx, 0C000009Ah
0x140237874  jmp     loc_14023798D
0x140237879  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x140237880  lea     rcx, [rbp+47h+Destination]; Destination
0x140237884  call    cs:__imp_RtlAppendUnicodeToString
0x14023788b  nop     dword ptr [rax+rax+00h]
0x140237890  mov     ebx, eax
0x140237892  test    eax, eax
0x140237894  js      loc_14023798D
0x14023789a  lea     rdx, [rbp+47h+Source]
0x14023789e  mov     rcx, rdi
0x1402378a1  call    StringFromGuid
0x1402378a6  mov     ebx, eax
0x1402378a8  test    eax, eax
0x1402378aa  js      loc_14023798D
0x1402378b0  lea     rdx, [rbp+47h+Source]; Source
0x1402378b4  lea     rcx, [rbp+47h+Destination]; Destination
0x1402378b8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1402378bf  nop     dword ptr [rax+rax+00h]
0x1402378c4  mov     ebx, eax
0x1402378c6  test    eax, eax
0x1402378c8  js      loc_14023798D
0x1402378ce  mov     [rsp+100h+EaLength], 0; EaLength
0x1402378d6  lea     rax, [rbp+47h+Destination]
0x1402378da  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x1402378e3  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x1402378e7  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x1402378ef  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1402378f3  mov     edx, 3; DesiredAccess
0x1402378f8  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1402378fc  mov     [rsp+100h+CreateDisposition], edx; CreateDisposition
0x140237900  lea     rax, [rbp+47h+var_80]
0x140237904  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x14023790c  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x140237910  xorps   xmm0, xmm0
0x140237913  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x14023791b  mov     [rsp+100h+AllocationSize], rax; AllocationSize
0x140237920  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x140237927  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x14023792f  mov     [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x140237936  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14023793b  call    cs:__imp_ZwCreateFile
0x140237942  nop     dword ptr [rax+rax+00h]
0x140237947  mov     ebx, eax
0x140237949  test    eax, eax
0x14023794b  js      short loc_14023798D
0x14023794d  mov     rax, [rbp+47h+FileHandle]
0x140237951  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x140237955  mov     qword ptr [rsp+100h+ShareAccess], rax; FileHandle
0x14023795a  xor     r9d, r9d; MaximumSize
0x14023795d  mov     [rsp+100h+FileAttributes], 8000000h; AllocationAttributes
0x140237965  xor     r8d, r8d; ObjectAttributes
0x140237968  mov     dword ptr [rsp+100h+AllocationSize], 4; SectionPageProtection
0x140237970  lea     edx, [r9+6]; DesiredAccess
0x140237974  call    cs:__imp_ZwCreateSection
0x14023797b  nop     dword ptr [rax+rax+00h]
0x140237980  mov     ebx, eax
0x140237982  test    eax, eax
0x140237984  js      short loc_14023798D
0x140237986  mov     rax, [rbp+47h+SectionHandle]
0x14023798a  mov     [rsi], rax
0x14023798d  mov     rcx, [rbp+47h+FileHandle]; Handle
0x140237991  test    rcx, rcx
0x140237994  jz      short loc_1402379A2
0x140237996  call    cs:__imp_ZwClose
0x14023799d  nop     dword ptr [rax+rax+00h]
0x1402379a2  mov     rcx, [rbp+47h+Destination.Buffer]; P
0x1402379a6  test    rcx, rcx
0x1402379a9  jz      short loc_1402379BC
0x1402379ab  mov     edx, 6B674D53h; Tag
0x1402379b0  call    cs:__imp_ExFreePoolWithTag
0x1402379b7  nop     dword ptr [rax+rax+00h]
0x1402379bc  lea     rcx, [rbp+47h+Source]; UnicodeString
0x1402379c0  call    cs:__imp_RtlFreeUnicodeString
0x1402379c7  nop     dword ptr [rax+rax+00h]
0x1402379cc  mov     eax, ebx
0x1402379ce  add     rsp, 0E8h
0x1402379d5  pop     rdi
0x1402379d6  pop     rsi
0x1402379d7  pop     rbx
0x1402379d8  pop     rbp
0x1402379d9  retn
```
