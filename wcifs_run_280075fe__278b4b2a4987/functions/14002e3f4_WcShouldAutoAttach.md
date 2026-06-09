# WcShouldAutoAttach

- ea: `0x14002e3f4`
- end: `0x14002e840`
- name: `WcShouldAutoAttach`
- size: `1100`
- prototype: `__int64 __fastcall(PFLT_INSTANCE InitiatingInstance, PFLT_VOLUME Volume)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140032d30`

## callees

- `0x1400020c4`
- `0x14002e3f4`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002e5bd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002e5bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e44c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e44c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e700`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e700`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e508`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e508`
- `ntoskrnl!ExAllocatePool2` at `0x14002e573`
- `ntoskrnl!ExAllocatePool2` at `0x14002e573`
- `FLTMGR!FltCreateFileEx` at `0x14002e64f`
- `FLTMGR!FltCreateFileEx` at `0x14002e64f`
- `FLTMGR!FltReadFile` at `0x14002e6bf`
- `FLTMGR!FltReadFile` at `0x14002e6bf`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14002e679`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14002e679`
- `FLTMGR!FltGetVolumeName` at `0x14002e461`
- `FLTMGR!FltGetVolumeName` at `0x14002e59c`
- `FLTMGR!FltGetVolumeName` at `0x14002e461`
- `FLTMGR!FltGetVolumeName` at `0x14002e59c`
- `FLTMGR!FltClose` at `0x14002e711`
- `FLTMGR!FltClose` at `0x14002e711`

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
  char AllocationSize; // [rsp+38h] [rbp-81h]
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
      AllocationSize = -107;
      v7 = 178;
      IoStatusBlock = -30;
      goto LABEL_5;
    }
    if ( (unsigned __int16)(v6 + 8) < (unsigned __int16)v6 )
    {
      DestinationString.MaximumLength = -1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        AllocationSize = -107;
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
        AllocationSize = -107;
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
            AllocationSize = VolumeName;
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
              AllocationSize = appended;
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
                  AllocationSize = v12;
                  v7 = 184;
                  IoStatusBlock = 60;
LABEL_5:
                  LOBYTE(v5) = 2;
                  WPP_RECORDER_SF_sDd(
                    WPP_GLOBAL_Control->DeviceExtension,
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
        AllocationSize = -102;
        v7 = 181;
        IoStatusBlock = -9;
        goto LABEL_5;
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    AllocationSize = 16;
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
0x14002e3f4  mov     [rsp-8+arg_0], rbx
0x14002e3f9  push    rbp
0x14002e3fa  push    rsi
0x14002e3fb  push    rdi
0x14002e3fc  push    r14
0x14002e3fe  push    r15
0x14002e400  lea     rbp, [rsp-37h]
0x14002e405  sub     rsp, 0F0h
0x14002e40c  xorps   xmm0, xmm0
0x14002e40f  xor     r14d, r14d
0x14002e412  mov     rbx, rdx
0x14002e415  movzx   edi, r14b
0x14002e419  mov     rsi, rcx
0x14002e41c  mov     [rbp+57h+BufferSizeNeeded], r14d
0x14002e420  movups  xmmword ptr [rbp+57h+var_58.ObjectName], xmm0
0x14002e424  xor     eax, eax
0x14002e426  mov     [rbp+57h+FileHandle], r14
0x14002e42a  xor     edx, edx; SourceString
0x14002e42c  mov     [rbp+57h+FileObject], r14
0x14002e430  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002e434  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14002e438  movups  xmmword ptr [rbp+57h+var_58+1Ch], xmm0
0x14002e43c  mov     [rbp+57h+BytesRead], r14d
0x14002e440  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002e444  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x14002e448  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x14002e44c  call    cs:__imp_RtlInitUnicodeString
0x14002e453  nop     dword ptr [rax+rax+00h]
0x14002e458  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x14002e45c  xor     edx, edx; VolumeName
0x14002e45e  mov     rcx, rbx; Volume
0x14002e461  call    cs:__imp_FltGetVolumeName
0x14002e468  nop     dword ptr [rax+rax+00h]
0x14002e46d  cmp     eax, 0C0000023h
0x14002e472  jnz     short loc_14002E4E6
0x14002e474  movzx   eax, word ptr [rbp+57h+BufferSizeNeeded]
0x14002e478  mov     r8d, 0FFFFh
0x14002e47e  add     eax, eax
0x14002e480  cmp     eax, r8d
0x14002e483  jbe     loc_14002E549
0x14002e489  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e48e  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e495  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e49c  jz      short loc_14002E4FA
0x14002e49e  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e4a6  mov     r9d, 0B2h
0x14002e4ac  mov     dword ptr [rsp+110h+IoStatusBlock], 1EE2h
0x14002e4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4bb  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002e4c2  mov     [rsp+110h+ObjectAttributes], rax
0x14002e4c7  mov     r8d, 0Eh
0x14002e4cd  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002e4d4  mov     dl, 2
0x14002e4d6  mov     qword ptr [rsp+110h+DesiredAccess], rax
0x14002e4db  mov     rcx, [rcx+40h]
0x14002e4df  call    WPP_RECORDER_SF_sDd
0x14002e4e4  jmp     short loc_14002E4FA
0x14002e4e6  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e4ed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e4f4  jnz     loc_14002E785
0x14002e4fa  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14002e4fe  test    rcx, rcx
0x14002e501  jz      short loc_14002E514
0x14002e503  mov     edx, 6E664357h; Tag
0x14002e508  call    cs:__imp_ExFreePoolWithTag
0x14002e50f  nop     dword ptr [rax+rax+00h]
0x14002e514  mov     rcx, [rbp+57h+FileObject]; Object
0x14002e518  test    rcx, rcx
0x14002e51b  jnz     loc_14002E700
0x14002e521  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002e525  test    rcx, rcx
0x14002e528  jnz     loc_14002E711
0x14002e52e  mov     rbx, [rsp+110h+arg_0]
0x14002e536  mov     al, dil
0x14002e539  add     rsp, 0F0h
0x14002e540  pop     r15
0x14002e542  pop     r14
0x14002e544  pop     rdi
0x14002e545  pop     rsi
0x14002e546  pop     rbp
0x14002e547  retn
0x14002e549  lea     ecx, [rax+8]
0x14002e54c  cmp     cx, ax
0x14002e54f  jb      loc_14002E7A0
0x14002e555  lea     eax, [rcx+48h]
0x14002e558  cmp     ax, cx
0x14002e55b  jb      loc_14002E751
0x14002e561  movzx   edx, ax
0x14002e564  mov     ecx, 100h
0x14002e569  mov     r8d, 6E664357h
0x14002e56f  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x14002e573  call    cs:__imp_ExAllocatePool2
0x14002e57a  nop     dword ptr [rax+rax+00h]
0x14002e57f  mov     [rbp+57h+DestinationString.Buffer], rax
0x14002e583  test    rax, rax
0x14002e586  jz      loc_14002E722
0x14002e58c  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x14002e590  mov     [rbp+57h+DestinationString.Length], r14w
0x14002e595  lea     rdx, [rbp+57h+DestinationString]; VolumeName
0x14002e599  mov     rcx, rbx; Volume
0x14002e59c  call    cs:__imp_FltGetVolumeName
0x14002e5a3  nop     dword ptr [rax+rax+00h]
0x14002e5a8  mov     ecx, eax
0x14002e5aa  test    eax, eax
0x14002e5ac  js      loc_14002E7D4
0x14002e5b2  lea     rdx, Source; "\\System Volume Information\\Wcifs.md"
0x14002e5b9  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14002e5bd  call    cs:__imp_RtlAppendUnicodeToString
0x14002e5c4  nop     dword ptr [rax+rax+00h]
0x14002e5c9  mov     ecx, eax
0x14002e5cb  test    eax, eax
0x14002e5cd  js      loc_14002E7FF
0x14002e5d3  mov     rcx, cs:Globals; Filter
0x14002e5da  lea     rax, [rbp+57h+DestinationString]
0x14002e5de  mov     [rsp+110h+Flags], r14d; Flags
0x14002e5e3  lea     r9, [rbp+57h+FileObject]; FileObject
0x14002e5e7  mov     [rsp+110h+EaLength], r14d; EaLength
0x14002e5ec  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14002e5f0  mov     [rsp+110h+EaBuffer], r14; EaBuffer
0x14002e5f5  mov     r15d, 1
0x14002e5fb  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x14002e600  xorps   xmm0, xmm0
0x14002e603  mov     [rsp+110h+CreateDisposition], r15d; CreateDisposition
0x14002e608  mov     rdx, rsi; Instance
0x14002e60b  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x14002e613  mov     [rsp+110h+FileAttributes], r14d; FileAttributes
0x14002e618  mov     [rbp+57h+var_58.ObjectName], rax
0x14002e61c  lea     rax, [rbp+57h+var_68]
0x14002e620  mov     [rsp+110h+AllocationSize], r14; AllocationSize
0x14002e625  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14002e62a  lea     rax, [rbp+57h+var_58]
0x14002e62e  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14002e633  mov     [rsp+110h+DesiredAccess], r15d; DesiredAccess
0x14002e638  mov     [rbp+57h+var_58.Length], 30h ; '0'
0x14002e63f  mov     [rbp+57h+var_58.RootDirectory], r14
0x14002e643  mov     [rbp+57h+var_58.Attributes], 200h
0x14002e64a  movdqu  xmmword ptr [rbp+57h+var_58.SecurityDescriptor], xmm0
0x14002e64f  call    cs:__imp_FltCreateFileEx
0x14002e656  nop     dword ptr [rax+rax+00h]
0x14002e65b  test    eax, eax
0x14002e65d  js      loc_14002E4FA
0x14002e663  mov     r9d, 61614357h; Tag
0x14002e669  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14002e66d  mov     r8d, 1000h; NumberOfBytes
0x14002e673  mov     edx, r15d; PoolType
0x14002e676  mov     rcx, rsi; Instance
0x14002e679  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14002e680  nop     dword ptr [rax+rax+00h]
0x14002e685  mov     rbx, rax
0x14002e688  test    rax, rax
0x14002e68b  jz      loc_14002E4FA
0x14002e691  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14002e695  lea     rax, [rbp+57h+BytesRead]
0x14002e699  mov     qword ptr [rsp+110h+FileAttributes], r14; CallbackContext
0x14002e69e  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x14002e6a2  mov     [rsp+110h+AllocationSize], r14; CallbackRoutine
0x14002e6a7  mov     r9d, 1000h; Length
0x14002e6ad  mov     [rsp+110h+IoStatusBlock], rax; BytesRead
0x14002e6b2  mov     rcx, rsi; InitiatingInstance
0x14002e6b5  mov     dword ptr [rsp+110h+ObjectAttributes], r15d; Flags
0x14002e6ba  mov     qword ptr [rsp+110h+DesiredAccess], rbx; Buffer
0x14002e6bf  call    cs:__imp_FltReadFile
0x14002e6c6  nop     dword ptr [rax+rax+00h]
0x14002e6cb  mov     ecx, eax
0x14002e6cd  test    eax, eax
0x14002e6cf  jns     loc_14002E82A
0x14002e6d5  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e6dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e6e3  jz      loc_14002E4FA
0x14002e6e9  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e6ed  mov     r9d, 0B8h
0x14002e6f3  mov     dword ptr [rsp+110h+IoStatusBlock], 1F3Ch
0x14002e6fb  jmp     loc_14002E4B4
0x14002e700  call    cs:__imp_ObfDereferenceObject
0x14002e707  nop     dword ptr [rax+rax+00h]
0x14002e70c  jmp     loc_14002E521
0x14002e711  call    cs:__imp_FltClose
0x14002e718  nop     dword ptr [rax+rax+00h]
0x14002e71d  jmp     loc_14002E52E
0x14002e722  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e729  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e730  jz      loc_14002E4FA
0x14002e736  mov     dword ptr [rsp+110h+AllocationSize], 0C000009Ah
0x14002e73e  mov     r9d, 0B5h
0x14002e744  mov     dword ptr [rsp+110h+IoStatusBlock], 1EF7h
0x14002e74c  jmp     loc_14002E4B4
0x14002e751  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e756  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e75d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e764  jz      loc_14002E4FA
0x14002e76a  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e772  mov     r9d, 0B4h
0x14002e778  mov     dword ptr [rsp+110h+IoStatusBlock], 1EF0h
0x14002e780  jmp     loc_14002E4B4
0x14002e785  mov     dword ptr [rsp+110h+AllocationSize], 0C0000010h
0x14002e78d  mov     r9d, 0B1h
0x14002e793  mov     dword ptr [rsp+110h+IoStatusBlock], 1EDAh
0x14002e79b  jmp     loc_14002E4B4
0x14002e7a0  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x14002e7a5  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e7ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e7b3  jz      loc_14002E4FA
0x14002e7b9  mov     dword ptr [rsp+110h+AllocationSize], 0C0000095h
0x14002e7c1  mov     r9d, 0B3h
0x14002e7c7  mov     dword ptr [rsp+110h+IoStatusBlock], 1EE9h
0x14002e7cf  jmp     loc_14002E4B4
0x14002e7d4  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e7db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e7e2  jz      loc_14002E4FA
0x14002e7e8  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e7ec  mov     r9d, 0B6h
0x14002e7f2  mov     dword ptr [rsp+110h+IoStatusBlock], 1EFEh
0x14002e7fa  jmp     loc_14002E4B4
0x14002e7ff  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e806  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e80d  jz      loc_14002E4FA
0x14002e813  mov     dword ptr [rsp+110h+AllocationSize], ecx
0x14002e817  mov     r9d, 0B7h
0x14002e81d  mov     dword ptr [rsp+110h+IoStatusBlock], 1F05h
0x14002e825  jmp     loc_14002E4B4
0x14002e82a  cmp     [rbp+57h+BytesRead], 4
0x14002e82e  jb      loc_14002E4FA
0x14002e834  test    [rbx], r15b
0x14002e837  cmovnz  edi, r15d
0x14002e83b  jmp     loc_14002E4FA
```
