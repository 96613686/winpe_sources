# Smb2NamedPipeInitialize

- ea: `0x140094fec`
- end: `0x14009518c`
- name: `Smb2NamedPipeInitialize`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140061f44`

## callees

- `0x1400224b8`
- `0x140094fec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009501e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009501e`
- `ntoskrnl!ZwClose` at `0x14009516b`
- `ntoskrnl!ZwClose` at `0x14009516b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009511b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009511b`
- `ntoskrnl!ZwCreateFile` at `0x14009509e`
- `ntoskrnl!ZwCreateFile` at `0x14009509e`

## pseudocode

```c
NTSTATUS Smb2NamedPipeInitialize()
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\NamedPipe\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwCreateFile(&Smb2NamedPipeHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( result >= 0 )
  {
    result = ObReferenceObjectByHandle(Smb2NamedPipeHandle, 0, 0, 0, &Smb2NamedPipeFileObject, 0);
    if ( result >= 0 )
      return result;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
        (unsigned int)result);
    }
    result = ZwClose(Smb2NamedPipeHandle);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        result = WPP_SF_d(
                   WPP_GLOBAL_Control->AttachedDevice,
                   10,
                   WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
                   (unsigned int)result);
    }
    Smb2NamedPipeFileObject = 0;
  }
  Smb2NamedPipeHandle = 0;
  return result;
}

```

## disassembly

```asm
0x140094fec  push    rbp
0x140094fee  lea     rbp, [rsp-57h]
0x140094ff3  sub     rsp, 0B0h
0x140094ffa  xorps   xmm0, xmm0
0x140094ffd  lea     rdx, aDeviceNamedpip; "\\Device\\NamedPipe\\"
0x140095004  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140095008  xor     eax, eax
0x14009500a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14009500e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140095012  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140095016  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009501a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14009501e  call    cs:__imp_RtlInitUnicodeString
0x140095025  nop     dword ptr [rax+rax+00h]
0x14009502a  mov     [rsp+0B0h+EaLength], 0; EaLength
0x140095032  lea     rax, [rbp+57h+DestinationString]
0x140095036  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x14009503f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140095043  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x14009504b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009504f  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x140095057  lea     rcx, Smb2NamedPipeHandle; FileHandle
0x14009505e  mov     [rsp+0B0h+ShareAccess], 3; ShareAccess
0x140095066  xorps   xmm0, xmm0
0x140095069  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x140095071  mov     edx, 0C0000000h; DesiredAccess
0x140095076  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x14009507f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140095086  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14009508e  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140095095  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140095099  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009509e  call    cs:__imp_ZwCreateFile
0x1400950a5  nop     dword ptr [rax+rax+00h]
0x1400950aa  test    eax, eax
0x1400950ac  jns     short loc_1400950F7
0x1400950ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400950b5  lea     rdx, WPP_GLOBAL_Control
0x1400950bc  cmp     rcx, rdx
0x1400950bf  jz      short loc_1400950E7
0x1400950c1  mov     edx, [rcx+2Ch]
0x1400950c4  test    dl, 1
0x1400950c7  jz      short loc_1400950E7
0x1400950c9  cmp     byte ptr [rcx+29h], 1
0x1400950cd  jb      short loc_1400950E7
0x1400950cf  mov     rcx, [rcx+18h]
0x1400950d3  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x1400950da  mov     edx, 0Ah
0x1400950df  mov     r9d, eax
0x1400950e2  call    WPP_SF_d
0x1400950e7  mov     cs:Smb2NamedPipeFileObject, 0
0x1400950f2  jmp     loc_140095177
0x1400950f7  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x1400950fe  lea     rax, Smb2NamedPipeFileObject
0x140095105  mov     qword ptr [rsp+0B0h+FileAttributes], 0; HandleInformation
0x14009510e  xor     r9d, r9d; AccessMode
0x140095111  xor     r8d, r8d; ObjectType
0x140095114  mov     [rsp+0B0h+AllocationSize], rax; Object
0x140095119  xor     edx, edx; DesiredAccess
0x14009511b  call    cs:__imp_ObReferenceObjectByHandle
0x140095122  nop     dword ptr [rax+rax+00h]
0x140095127  test    eax, eax
0x140095129  jns     short loc_140095182
0x14009512b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140095132  lea     rdx, WPP_GLOBAL_Control
0x140095139  cmp     rcx, rdx
0x14009513c  jz      short loc_140095164
0x14009513e  mov     edx, [rcx+2Ch]
0x140095141  test    dl, 1
0x140095144  jz      short loc_140095164
0x140095146  cmp     byte ptr [rcx+29h], 1
0x14009514a  jb      short loc_140095164
0x14009514c  mov     rcx, [rcx+18h]
0x140095150  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x140095157  mov     edx, 0Bh
0x14009515c  mov     r9d, eax
0x14009515f  call    WPP_SF_d
0x140095164  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x14009516b  call    cs:__imp_ZwClose
0x140095172  nop     dword ptr [rax+rax+00h]
0x140095177  mov     cs:Smb2NamedPipeHandle, 0
0x140095182  add     rsp, 0B0h
0x140095189  pop     rbp
0x14009518a  retn
```
