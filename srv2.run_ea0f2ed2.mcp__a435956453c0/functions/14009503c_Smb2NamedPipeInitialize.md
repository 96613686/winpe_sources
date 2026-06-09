# Smb2NamedPipeInitialize

- ea: `0x14009503c`
- end: `0x1400951dc`
- name: `Smb2NamedPipeInitialize`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140061f94`

## callees

- `0x1400224b8`
- `0x14009503c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009506e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009506e`
- `ntoskrnl!ZwClose` at `0x1400951bb`
- `ntoskrnl!ZwClose` at `0x1400951bb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009516b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009516b`
- `ntoskrnl!ZwCreateFile` at `0x1400950ee`
- `ntoskrnl!ZwCreateFile` at `0x1400950ee`

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
        &WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
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
                   &WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
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
0x14009503c  push    rbp
0x14009503e  lea     rbp, [rsp-57h]
0x140095043  sub     rsp, 0B0h
0x14009504a  xorps   xmm0, xmm0
0x14009504d  lea     rdx, aDeviceNamedpip; "\\Device\\NamedPipe\\"
0x140095054  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140095058  xor     eax, eax
0x14009505a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14009505e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140095062  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140095066  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009506a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14009506e  call    cs:__imp_RtlInitUnicodeString
0x140095075  nop     dword ptr [rax+rax+00h]
0x14009507a  mov     [rsp+0B0h+EaLength], 0; EaLength
0x140095082  lea     rax, [rbp+57h+DestinationString]
0x140095086  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x14009508f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140095093  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x14009509b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009509f  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x1400950a7  lea     rcx, Smb2NamedPipeHandle; FileHandle
0x1400950ae  mov     [rsp+0B0h+ShareAccess], 3; ShareAccess
0x1400950b6  xorps   xmm0, xmm0
0x1400950b9  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x1400950c1  mov     edx, 0C0000000h; DesiredAccess
0x1400950c6  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x1400950cf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400950d6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400950de  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400950e5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400950e9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400950ee  call    cs:__imp_ZwCreateFile
0x1400950f5  nop     dword ptr [rax+rax+00h]
0x1400950fa  test    eax, eax
0x1400950fc  jns     short loc_140095147
0x1400950fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140095105  lea     rdx, WPP_GLOBAL_Control
0x14009510c  cmp     rcx, rdx
0x14009510f  jz      short loc_140095137
0x140095111  mov     edx, [rcx+2Ch]
0x140095114  test    dl, 1
0x140095117  jz      short loc_140095137
0x140095119  cmp     byte ptr [rcx+29h], 1
0x14009511d  jb      short loc_140095137
0x14009511f  mov     rcx, [rcx+18h]
0x140095123  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x14009512a  mov     edx, 0Ah
0x14009512f  mov     r9d, eax
0x140095132  call    WPP_SF_d
0x140095137  mov     cs:Smb2NamedPipeFileObject, 0
0x140095142  jmp     loc_1400951C7
0x140095147  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x14009514e  lea     rax, Smb2NamedPipeFileObject
0x140095155  mov     qword ptr [rsp+0B0h+FileAttributes], 0; HandleInformation
0x14009515e  xor     r9d, r9d; AccessMode
0x140095161  xor     r8d, r8d; ObjectType
0x140095164  mov     [rsp+0B0h+AllocationSize], rax; Object
0x140095169  xor     edx, edx; DesiredAccess
0x14009516b  call    cs:__imp_ObReferenceObjectByHandle
0x140095172  nop     dword ptr [rax+rax+00h]
0x140095177  test    eax, eax
0x140095179  jns     short loc_1400951D2
0x14009517b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140095182  lea     rdx, WPP_GLOBAL_Control
0x140095189  cmp     rcx, rdx
0x14009518c  jz      short loc_1400951B4
0x14009518e  mov     edx, [rcx+2Ch]
0x140095191  test    dl, 1
0x140095194  jz      short loc_1400951B4
0x140095196  cmp     byte ptr [rcx+29h], 1
0x14009519a  jb      short loc_1400951B4
0x14009519c  mov     rcx, [rcx+18h]
0x1400951a0  lea     r8, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids
0x1400951a7  mov     edx, 0Bh
0x1400951ac  mov     r9d, eax
0x1400951af  call    WPP_SF_d
0x1400951b4  mov     rcx, cs:Smb2NamedPipeHandle; Handle
0x1400951bb  call    cs:__imp_ZwClose
0x1400951c2  nop     dword ptr [rax+rax+00h]
0x1400951c7  mov     cs:Smb2NamedPipeHandle, 0
0x1400951d2  add     rsp, 0B0h
0x1400951d9  pop     rbp
0x1400951da  retn
```
