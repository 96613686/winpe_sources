# WcShouldAutoAttach

- ea: `0x14002e444`
- end: `0x14002e890`
- name: `WcShouldAutoAttach`
- size: `1100`
- prototype: `bool __fastcall(PFLT_INSTANCE InitiatingInstance, PFLT_VOLUME Volume)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140032d80`

## callees

- `0x1400020c4`
- `0x14002e444`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002e60d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002e60d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e49c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e49c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e750`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e750`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e558`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e558`
- `ntoskrnl!ExAllocatePool2` at `0x14002e5c3`
- `ntoskrnl!ExAllocatePool2` at `0x14002e5c3`
- `FLTMGR!FltCreateFileEx` at `0x14002e69f`
- `FLTMGR!FltCreateFileEx` at `0x14002e69f`
- `FLTMGR!FltReadFile` at `0x14002e70f`
- `FLTMGR!FltReadFile` at `0x14002e70f`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14002e6c9`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14002e6c9`
- `FLTMGR!FltGetVolumeName` at `0x14002e4b1`
- `FLTMGR!FltGetVolumeName` at `0x14002e5ec`
- `FLTMGR!FltGetVolumeName` at `0x14002e4b1`
- `FLTMGR!FltGetVolumeName` at `0x14002e5ec`
- `FLTMGR!FltClose` at `0x14002e761`
- `FLTMGR!FltClose` at `0x14002e761`

## pseudocode

```c
bool __fastcall WcShouldAutoAttach(PFLT_INSTANCE InitiatingInstance, PFLT_VOLUME Volume)
{
  bool v3; // di
  int v5; // edx
  unsigned int v6; // eax
  int v7; // r9d
  NTSTATUS VolumeName; // ecx
  NTSTATUS appended; // ecx
  _BYTE *PoolAlignedWithTag; // rbx
  NTSTATUS v12; // ecx
  char IoStatusBlock; // [rsp+30h] [rbp-89h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-81h]
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-39h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-31h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK v19; // [rsp+A8h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-1h] BYREF
  ULONG BufferSizeNeeded; // [rsp+130h] [rbp+77h] BYREF
  ULONG BytesRead; // [rsp+138h] [rbp+7Fh] BYREF

  v3 = 0;
  BufferSizeNeeded = 0;
  FileHandle = 0;
  FileObject = 0;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v19 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( FltGetVolumeName(Volume, 0, &BufferSizeNeeded) == -1073741789 )
  {
    v6 = 2 * (unsigned __int16)BufferSizeNeeded;
    if ( v6 > 0xFFFF )
    {
      DestinationString.MaximumLength = -1;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_7;
      LODWORD(AllocationSize) = -1073741675;
      v7 = 178;
      IoStatusBlock = -30;
      goto LABEL_5;
    }
    if ( (unsigned __int16)(v6 + 8) < (unsigned __int16)v6 )
    {
      DestinationString.MaximumLength = -1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = -1073741675;
        v7 = 179;
        IoStatusBlock = -23;
        goto LABEL_5;
      }
    }
    else if ( (unsigned __int16)(v6 + 80) < (unsigned __int16)(v6 + 8) )
    {
      DestinationString.MaximumLength = -1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = -1073741675;
        v7 = 180;
        IoStatusBlock = -16;
        goto LABEL_5;
      }
    }
    else
    {
      DestinationString.MaximumLength = v6 + 80;
      DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)(v6 + 80), 1852195671);
      if ( DestinationString.Buffer )
      {
        DestinationString.Length = 0;
        VolumeName = FltGetVolumeName(Volume, &DestinationString, &BufferSizeNeeded);
        if ( VolumeName < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(AllocationSize) = VolumeName;
            v7 = 182;
            IoStatusBlock = -2;
            goto LABEL_5;
          }
        }
        else
        {
          appended = RtlAppendUnicodeToString(&DestinationString, L"\\System Volume Information\\Wcifs.md");
          if ( appended < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(AllocationSize) = appended;
              v7 = 183;
              IoStatusBlock = 5;
              goto LABEL_5;
            }
          }
          else
          {
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 512;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( FltCreateFileEx(
                   Globals,
                   InitiatingInstance,
                   &FileHandle,
                   &FileObject,
                   1u,
                   &ObjectAttributes,
                   &v19,
                   0,
                   0,
                   5u,
                   1u,
                   0,
                   0,
                   0,
                   0) >= 0 )
            {
              ByteOffset.QuadPart = 0;
              PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(InitiatingInstance, PagedPool, 0x1000u, 0x61614357u);
              if ( PoolAlignedWithTag )
              {
                v12 = FltReadFile(
                        InitiatingInstance,
                        FileObject,
                        &ByteOffset,
                        0x1000u,
                        PoolAlignedWithTag,
                        1u,
                        &BytesRead,
                        0,
                        0);
                if ( v12 >= 0 )
                {
                  if ( BytesRead >= 4 )
                    v3 = (*PoolAlignedWithTag & 1) != 0;
                }
                else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LODWORD(AllocationSize) = v12;
                  v7 = 184;
                  IoStatusBlock = 60;
LABEL_5:
                  LOBYTE(v5) = 2;
                  WPP_RECORDER_SF_sDd(
                    wil_details_featureDescriptors_a->DeviceExtension,
                    v5,
                    14,
                    v7,
                    (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
                    (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
                    IoStatusBlock,
                    AllocationSize);
                }
              }
            }
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(AllocationSize) = -1073741670;
        v7 = 181;
        IoStatusBlock = -9;
        goto LABEL_5;
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(AllocationSize) = -1073741808;
    v7 = 177;
    IoStatusBlock = -38;
    goto LABEL_5;
  }
LABEL_7:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return v3;
}

```

## disassembly

```asm
0x14002e444  mov     [rsp-8+arg_0], rbx
0x14002e449  push    rbp
0x14002e44a  push    rsi
0x14002e44b  push    rdi
0x14002e44c  push    r14
0x14002e44e  push    r15
0x14002e450  lea     rbp, [rsp-37h]
0x14002e455  sub     rsp, 0F0h
0x14002e45c  xorps   xmm0, xmm0
0x14002e45f  xor     r14d, r14d
0x14002e462  mov     rbx, rdx
0x14002e465  movzx   edi, r14b
0x14002e469  mov     rsi, rcx
0x14002e46c  mov     [rbp+57h+BufferSizeNeeded], r14d
0x14002e470  movups  xmmword ptr [rbp+57h+var_58.ObjectName], xmm0
0x14002e474  xor     eax, eax
0x14002e476  mov     [rbp+57h+FileHandle], r14
0x14002e47a  xor     edx, edx; SourceString
0x14002e47c  mov     [rbp+57h+FileObject], r14
0x14002e480  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002e484  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14002e488  movups  xmmword ptr [rbp+57h+var_58+1Ch], xmm0
0x14002e48c  mov     [rbp+57h+BytesRead], r14d
0x14002e490  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002e494  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x14002e498  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x14002e49c  call    cs:__imp_RtlInitUnicodeString
0x14002e4a3  nop     dword ptr [rax+rax+00h]
0x14002e4a8  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x14002e4ac  xor     edx, edx; VolumeName
0x14002e4ae  mov     rcx, rbx; Volume
0x14002e4b1  call    cs:__imp_FltGetVolumeName
0x14002e4b8  nop     dword ptr [rax+rax+00h]
0x14002e4bd  cmp     eax, 0C0000023h
0x14002e4c2  jnz     short loc_14002E536
0x14002e4c4  movzx   eax, word ptr [rbp+57h+BufferSizeNeeded]
0x14002e4c8  mov     r8d, 0FFFFh
0x14002e4ce  add     eax, eax
0x14002e4d0  cmp     eax, r8d
0x14002e4d3  jbe     loc_14002E599
0x14002e4d9  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e4de  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e4e5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e4ec  jz      short loc_14002E54A
0x14002e4ee  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e4f6  mov     r9d, 0B2h
0x14002e4fc  mov     dword ptr [rsp+110h+IoStatusBlock], 1EE2h
0x14002e504  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002e50b  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002e512  mov     [rsp+110h+ObjectAttributes], rax
0x14002e517  mov     r8d, 0Eh
0x14002e51d  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002e524  mov     dl, 2
0x14002e526  mov     qword ptr [rsp+110h+DesiredAccess], rax
0x14002e52b  mov     rcx, [rcx+40h]
0x14002e52f  call    WPP_RECORDER_SF_sDd
0x14002e534  jmp     short loc_14002E54A
0x14002e536  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e53d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e544  jnz     loc_14002E7D5
0x14002e54a  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14002e54e  test    rcx, rcx
0x14002e551  jz      short loc_14002E564
0x14002e553  mov     edx, 6E664357h; Tag
0x14002e558  call    cs:__imp_ExFreePoolWithTag
0x14002e55f  nop     dword ptr [rax+rax+00h]
0x14002e564  mov     rcx, [rbp+57h+FileObject]; Object
0x14002e568  test    rcx, rcx
0x14002e56b  jnz     loc_14002E750
0x14002e571  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002e575  test    rcx, rcx
0x14002e578  jnz     loc_14002E761
0x14002e57e  mov     rbx, [rsp+110h+arg_0]
0x14002e586  mov     al, dil
0x14002e589  add     rsp, 0F0h
0x14002e590  pop     r15
0x14002e592  pop     r14
0x14002e594  pop     rdi
0x14002e595  pop     rsi
0x14002e596  pop     rbp
0x14002e597  retn
0x14002e599  lea     ecx, [rax+8]
0x14002e59c  cmp     cx, ax
0x14002e59f  jb      loc_14002E7F0
0x14002e5a5  lea     eax, [rcx+48h]
0x14002e5a8  cmp     ax, cx
0x14002e5ab  jb      loc_14002E7A1
0x14002e5b1  movzx   edx, ax
0x14002e5b4  mov     ecx, 100h
0x14002e5b9  mov     r8d, 6E664357h
0x14002e5bf  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x14002e5c3  call    cs:__imp_ExAllocatePool2
0x14002e5ca  nop     dword ptr [rax+rax+00h]
0x14002e5cf  mov     [rbp+57h+DestinationString.Buffer], rax
0x14002e5d3  test    rax, rax
0x14002e5d6  jz      loc_14002E772
0x14002e5dc  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x14002e5e0  mov     [rbp+57h+DestinationString.Length], r14w
0x14002e5e5  lea     rdx, [rbp+57h+DestinationString]; VolumeName
0x14002e5e9  mov     rcx, rbx; Volume
0x14002e5ec  call    cs:__imp_FltGetVolumeName
0x14002e5f3  nop     dword ptr [rax+rax+00h]
0x14002e5f8  mov     ecx, eax
0x14002e5fa  test    eax, eax
0x14002e5fc  js      loc_14002E824
0x14002e602  lea     rdx, Source; "\\System Volume Information\\Wcifs.md"
0x14002e609  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14002e60d  call    cs:__imp_RtlAppendUnicodeToString
0x14002e614  nop     dword ptr [rax+rax+00h]
0x14002e619  mov     ecx, eax
0x14002e61b  test    eax, eax
0x14002e61d  js      loc_14002E84F
0x14002e623  mov     rcx, cs:Globals; Filter
0x14002e62a  lea     rax, [rbp+57h+DestinationString]
0x14002e62e  mov     [rsp+110h+Flags], r14d; Flags
0x14002e633  lea     r9, [rbp+57h+FileObject]; FileObject
0x14002e637  mov     [rsp+110h+EaLength], r14d; EaLength
0x14002e63c  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14002e640  mov     [rsp+110h+EaBuffer], r14; EaBuffer
0x14002e645  mov     r15d, 1
0x14002e64b  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x14002e650  xorps   xmm0, xmm0
0x14002e653  mov     [rsp+110h+CreateDisposition], r15d; CreateDisposition
0x14002e658  mov     rdx, rsi; Instance
0x14002e65b  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x14002e663  mov     [rsp+110h+FileAttributes], r14d; FileAttributes
0x14002e668  mov     [rbp+57h+var_58.ObjectName], rax
0x14002e66c  lea     rax, [rbp+57h+var_68]
0x14002e670  mov     [rsp+110h+AllocationSize], r14; AllocationSize
0x14002e675  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14002e67a  lea     rax, [rbp+57h+var_58]
0x14002e67e  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14002e683  mov     [rsp+110h+DesiredAccess], r15d; DesiredAccess
0x14002e688  mov     [rbp+57h+var_58.Length], 30h ; '0'
0x14002e68f  mov     [rbp+57h+var_58.RootDirectory], r14
0x14002e693  mov     [rbp+57h+var_58.Attributes], 200h
0x14002e69a  movdqu  xmmword ptr [rbp+57h+var_58.SecurityDescriptor], xmm0
0x14002e69f  call    cs:__imp_FltCreateFileEx
0x14002e6a6  nop     dword ptr [rax+rax+00h]
0x14002e6ab  test    eax, eax
0x14002e6ad  js      loc_14002E54A
0x14002e6b3  mov     r9d, 61614357h; Tag
0x14002e6b9  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14002e6bd  mov     r8d, 1000h; NumberOfBytes
0x14002e6c3  mov     edx, r15d; PoolType
0x14002e6c6  mov     rcx, rsi; Instance
0x14002e6c9  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14002e6d0  nop     dword ptr [rax+rax+00h]
0x14002e6d5  mov     rbx, rax
0x14002e6d8  test    rax, rax
0x14002e6db  jz      loc_14002E54A
0x14002e6e1  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14002e6e5  lea     rax, [rbp+57h+BytesRead]
0x14002e6e9  mov     qword ptr [rsp+110h+FileAttributes], r14; CallbackContext
0x14002e6ee  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x14002e6f2  mov     [rsp+110h+AllocationSize], r14; CallbackRoutine
0x14002e6f7  mov     r9d, 1000h; Length
0x14002e6fd  mov     [rsp+110h+IoStatusBlock], rax; BytesRead
0x14002e702  mov     rcx, rsi; InitiatingInstance
0x14002e705  mov     dword ptr [rsp+110h+ObjectAttributes], r15d; Flags
0x14002e70a  mov     qword ptr [rsp+110h+DesiredAccess], rbx; Buffer
0x14002e70f  call    cs:__imp_FltReadFile
0x14002e716  nop     dword ptr [rax+rax+00h]
0x14002e71b  mov     ecx, eax
0x14002e71d  test    eax, eax
0x14002e71f  jns     loc_14002E87A
0x14002e725  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e72c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e733  jz      loc_14002E54A
0x14002e739  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e73d  mov     r9d, 0B8h
0x14002e743  mov     dword ptr [rsp+110h+IoStatusBlock], 1F3Ch
0x14002e74b  jmp     loc_14002E504
0x14002e750  call    cs:__imp_ObfDereferenceObject
0x14002e757  nop     dword ptr [rax+rax+00h]
0x14002e75c  jmp     loc_14002E571
0x14002e761  call    cs:__imp_FltClose
0x14002e768  nop     dword ptr [rax+rax+00h]
0x14002e76d  jmp     loc_14002E57E
0x14002e772  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e779  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e780  jz      loc_14002E54A
0x14002e786  mov     dword ptr [rsp+110h+AllocationSize], 0C000009Ah
0x14002e78e  mov     r9d, 0B5h
0x14002e794  mov     dword ptr [rsp+110h+IoStatusBlock], 1EF7h
0x14002e79c  jmp     loc_14002E504
0x14002e7a1  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e7a6  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e7ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e7b4  jz      loc_14002E54A
0x14002e7ba  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e7c2  mov     r9d, 0B4h
0x14002e7c8  mov     dword ptr [rsp+110h+IoStatusBlock], 1EF0h
0x14002e7d0  jmp     loc_14002E504
0x14002e7d5  mov     dword ptr [rsp+110h+AllocationSize], 0C0000010h
0x14002e7dd  mov     r9d, 0B1h
0x14002e7e3  mov     dword ptr [rsp+110h+IoStatusBlock], 1EDAh
0x14002e7eb  jmp     loc_14002E504
0x14002e7f0  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e7f5  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e7fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e803  jz      loc_14002E54A
0x14002e809  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e811  mov     r9d, 0B3h
0x14002e817  mov     dword ptr [rsp+110h+IoStatusBlock], 1EE9h
0x14002e81f  jmp     loc_14002E504
0x14002e824  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e82b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e832  jz      loc_14002E54A
0x14002e838  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e83c  mov     r9d, 0B6h
0x14002e842  mov     dword ptr [rsp+110h+IoStatusBlock], 1EFEh
0x14002e84a  jmp     loc_14002E504
0x14002e84f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e856  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e85d  jz      loc_14002E54A
0x14002e863  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e867  mov     r9d, 0B7h
0x14002e86d  mov     dword ptr [rsp+110h+IoStatusBlock], 1F05h
0x14002e875  jmp     loc_14002E504
0x14002e87a  cmp     [rbp+57h+BytesRead], 4
0x14002e87e  jb      loc_14002E54A
0x14002e884  test    [rbx], r15b
0x14002e887  cmovnz  edi, r15d
0x14002e88b  jmp     loc_14002E54A
```
