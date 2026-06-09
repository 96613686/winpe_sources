# BiGetPartitionVhdFilePathFromUnicodeString

- ea: `0x140031500`
- end: `0x14003166a`
- name: `BiGetPartitionVhdFilePathFromUnicodeString`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b43c`
- `0x1400314d0`

## callees

- `0x14000da0d`
- `0x14000da55`
- `0x14000db06`
- `0x14000db18`
- `0x140031500`
- `0x140031f44`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003158a`
- `ntoskrnl!ExAllocatePool2` at `0x14003158a`

## pseudocode

```c
ULONG *__fastcall BiGetPartitionVhdFilePathFromUnicodeString(struct _UNICODE_STRING *a1)
{
  ULONG *v1; // rbx
  ULONG OutputBufferLength; // edi
  int i; // esi
  ULONG *OutputBuffer; // rax
  NTSTATUS v5; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  int InputBuffer; // [rsp+B0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF
  ULONG *v11; // [rsp+C0h] [rbp+77h]

  ObjectAttributes.ObjectName = a1;
  InputBuffer = 0;
  v11 = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v1 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  if ( ZwOpenFile_0(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    OutputBufferLength = 520;
    for ( i = 1; ; i = 2 )
    {
      OutputBuffer = (ULONG *)ExAllocatePool2(258, OutputBufferLength, 1262764866);
      v1 = OutputBuffer;
      if ( !OutputBuffer )
        break;
      InputBuffer = 1;
      v5 = ZwDeviceIoControlFile_0(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x2D5928u,
             &InputBuffer,
             4u,
             OutputBuffer,
             OutputBufferLength);
      if ( v5 != -1073741789 )
      {
        if ( v5 < 0 )
        {
LABEL_11:
          ExFreePoolWithTag_0(v1, 0x4B444342u);
          v1 = 0;
          break;
        }
        if ( (int)BiTranslateSymbolicLinkFile((PCWSTR)v1) >= 0 )
        {
          ExFreePoolWithTag_0(v1, 0x4B444342u);
          v1 = v11;
        }
        break;
      }
      if ( i != 1 )
        goto LABEL_11;
      OutputBufferLength = *v1;
      ExFreePoolWithTag_0(v1, 0x4B444342u);
    }
  }
  if ( FileHandle )
    ZwClose_0(FileHandle);
  return v1;
}

```

## disassembly

```asm
0x140031500  mov     [rsp-8+arg_18], rbx
0x140031505  push    rbp
0x140031506  push    rsi
0x140031507  push    rdi
0x140031508  lea     rbp, [rsp-47h]
0x14003150d  sub     rsp, 90h
0x140031514  xor     eax, eax
0x140031516  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14003151a  xorps   xmm0, xmm0
0x14003151d  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x140031525  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031529  mov     [rbp+57h+arg_0], eax
0x14003152c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140031530  mov     [rbp+57h+arg_10], rax
0x140031534  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140031538  mov     [rbp+57h+FileHandle], rax
0x14003153c  mov     edx, 0C0100000h; DesiredAccess
0x140031541  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140031545  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140031549  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140031551  xor     ebx, ebx
0x140031553  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140031558  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140031560  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x140031568  call    ZwOpenFile_0
0x14003156d  test    eax, eax
0x14003156f  js      loc_140031645
0x140031575  mov     edi, 208h
0x14003157a  lea     esi, [rbx+1]
0x14003157d  mov     edx, edi
0x14003157f  mov     ecx, 102h
0x140031584  mov     r8d, 4B444342h
0x14003158a  call    cs:__imp_ExAllocatePool2
0x140031591  nop     dword ptr [rax+rax+00h]
0x140031596  mov     rbx, rax
0x140031599  test    rax, rax
0x14003159c  jz      loc_140031631
0x1400315a2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400315a6  xor     r9d, r9d; ApcContext
0x1400315a9  mov     [rsp+0A0h+OutputBufferLength], edi; OutputBufferLength
0x1400315ad  xor     r8d, r8d; ApcRoutine
0x1400315b0  mov     [rsp+0A0h+OutputBuffer], rax; OutputBuffer
0x1400315b5  xor     edx, edx; Event
0x1400315b7  mov     [rsp+0A0h+InputBufferLength], 4; InputBufferLength
0x1400315bf  lea     rax, [rbp+57h+arg_0]
0x1400315c3  mov     [rsp+0A0h+InputBuffer], rax; InputBuffer
0x1400315c8  lea     rax, [rbp+57h+IoStatusBlock]
0x1400315cc  mov     [rsp+0A0h+OpenOptions], 2D5928h; IoControlCode
0x1400315d4  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x1400315d9  mov     [rbp+57h+arg_0], 1
0x1400315e0  call    ZwDeviceIoControlFile_0
0x1400315e5  cmp     eax, 0C0000023h
0x1400315ea  jnz     short loc_14003160A
0x1400315ec  cmp     esi, 1
0x1400315ef  jnz     short loc_140031636
0x1400315f1  mov     edi, [rbx]
0x1400315f3  mov     edx, 4B444342h; Tag
0x1400315f8  mov     rcx, rbx; P
0x1400315fb  call    ExFreePoolWithTag_0
0x140031600  mov     esi, 2
0x140031605  jmp     loc_14003157D
0x14003160a  test    eax, eax
0x14003160c  js      short loc_140031636
0x14003160e  lea     rdx, [rbp+57h+arg_10]
0x140031612  mov     rcx, rbx; SourceString
0x140031615  call    BiTranslateSymbolicLinkFile
0x14003161a  test    eax, eax
0x14003161c  js      short loc_140031645
0x14003161e  mov     edx, 4B444342h; Tag
0x140031623  mov     rcx, rbx; P
0x140031626  call    ExFreePoolWithTag_0
0x14003162b  mov     rbx, [rbp+57h+arg_10]
0x14003162f  jmp     short loc_140031645
0x140031631  test    rbx, rbx
0x140031634  jz      short loc_140031645
0x140031636  mov     edx, 4B444342h; Tag
0x14003163b  mov     rcx, rbx; P
0x14003163e  call    ExFreePoolWithTag_0
0x140031643  xor     ebx, ebx
0x140031645  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140031649  test    rcx, rcx
0x14003164c  jz      short loc_140031653
0x14003164e  call    ZwClose_0
0x140031653  mov     rax, rbx
0x140031656  mov     rbx, [rsp+0A0h+arg_18]
0x14003165e  add     rsp, 90h
0x140031665  pop     rdi
0x140031666  pop     rsi
0x140031667  pop     rbp
0x140031668  retn
```
