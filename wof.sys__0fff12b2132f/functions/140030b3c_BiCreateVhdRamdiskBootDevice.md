# BiCreateVhdRamdiskBootDevice

- ea: `0x140030b3c`
- end: `0x140030d2a`
- name: `BiCreateVhdRamdiskBootDevice`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1400306fc`

## callees

- `0x14000da31`
- `0x14000da55`
- `0x14000db06`
- `0x14000db18`
- `0x1400116c0`
- `0x1400119c0`
- `0x140030b3c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030c79`
- `ntoskrnl!ExAllocatePool2` at `0x140030c79`

## pseudocode

```c
__int64 __fastcall BiCreateVhdRamdiskBootDevice(__int64 a1, _QWORD *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  size_t v6; // rsi
  unsigned int v7; // r14d
  char *Pool2; // rax
  char *v9; // rbx
  int v10; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  _QWORD OutputBuffer[16]; // [rsp+A0h] [rbp-29h] BYREF
  void *FileHandle; // [rsp+140h] [rbp+77h] BYREF

  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  memset(OutputBuffer, 0, 0x40u);
  DestinationString = 0;
  FileHandle = 0;
  RtlInitUnicodeString_0(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v4 = ZwOpenFile_0(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v4 >= 0 )
  {
    v4 = ZwDeviceIoControlFile_0(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose_0(FileHandle);
    if ( v4 >= 0 )
    {
      if ( HIDWORD(OutputBuffer[2]) == 3 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)(a1 + 2 * v5 + 106) );
        v6 = 2 * v5 + 2;
        v7 = 2 * v5 + 106;
        Pool2 = (char *)ExAllocatePool2(258, v7, 1262764866);
        v9 = Pool2;
        if ( Pool2 )
        {
          memset(Pool2, 0, v7);
          *(_DWORD *)v9 = 0;
          *((_DWORD *)v9 + 4) = 5;
          *(_QWORD *)(v9 + 28) = 5;
          *((_DWORD *)v9 + 6) = v6 + 84;
          *((_DWORD *)v9 + 2) = v7;
          *((_DWORD *)v9 + 5) = 1;
          *((_DWORD *)v9 + 10) = 72;
          *((_DWORD *)v9 + 9) = 16;
          *((_DWORD *)v9 + 12) = 3;
          *(_QWORD *)(v9 + 52) = OutputBuffer[6] << 12;
          *(_QWORD *)(v9 + 60) = OutputBuffer[4];
          v10 = OutputBuffer[5];
          *((_DWORD *)v9 + 18) = 1;
          *((_DWORD *)v9 + 20) = 5;
          *((_DWORD *)v9 + 17) = v10;
          *((_DWORD *)v9 + 19) = 12;
          memmove(v9 + 104, (const void *)(a1 + 106), v6);
          *a2 = v9;
          return 0;
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
      else
      {
        return (unsigned int)-1073741808;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140030b3c  push    rbp
0x140030b3e  push    rbx
0x140030b3f  push    rsi
0x140030b40  push    rdi
0x140030b41  push    r12
0x140030b43  push    r13
0x140030b45  push    r14
0x140030b47  push    r15
0x140030b49  lea     rbp, [rsp-1Fh]
0x140030b4e  sub     rsp, 0E8h
0x140030b55  xorps   xmm0, xmm0
0x140030b58  xor     eax, eax
0x140030b5a  mov     r12, rdx
0x140030b5d  mov     rdi, rcx
0x140030b60  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140030b64  xor     edx, edx; Val
0x140030b66  lea     rcx, [rbp+57h+var_80]; void *
0x140030b6a  lea     esi, [rax+40h]
0x140030b6d  mov     r8d, esi; Size
0x140030b70  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140030b74  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140030b78  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140030b7c  call    memset
0x140030b81  xorps   xmm0, xmm0
0x140030b84  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140030b8b  xor     r13d, r13d
0x140030b8e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140030b92  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140030b96  mov     [rbp+57h+FileHandle], r13
0x140030b9a  call    RtlInitUnicodeString_0
0x140030b9f  lea     rax, [rbp+57h+DestinationString]
0x140030ba3  mov     [rsp+120h+OpenOptions], 20h ; ' '; OpenOptions
0x140030bab  xorps   xmm0, xmm0
0x140030bae  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140030bb2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140030bb6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140030bbd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140030bc1  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x140030bc5  mov     edx, 0C0000000h; DesiredAccess
0x140030bca  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140030bd1  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030bd5  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140030bdd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140030be2  call    ZwOpenFile_0
0x140030be7  mov     ebx, eax
0x140030be9  test    eax, eax
0x140030beb  js      loc_140030D13
0x140030bf1  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030bf5  lea     rax, [rbp+57h+var_80]
0x140030bf9  mov     [rsp+120h+OutputBufferLength], esi; OutputBufferLength
0x140030bfd  xor     r9d, r9d; ApcContext
0x140030c00  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x140030c05  xor     r8d, r8d; ApcRoutine
0x140030c08  mov     [rsp+120h+InputBufferLength], r13d; InputBufferLength
0x140030c0d  lea     rax, [rbp+57h+IoStatusBlock]
0x140030c11  mov     [rsp+120h+InputBuffer], r13; InputBuffer
0x140030c16  xor     edx, edx; Event
0x140030c18  mov     [rsp+120h+OpenOptions], 240008h; IoControlCode
0x140030c20  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x140030c25  call    ZwDeviceIoControlFile_0
0x140030c2a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140030c2e  mov     ebx, eax
0x140030c30  call    ZwClose_0
0x140030c35  test    ebx, ebx
0x140030c37  js      loc_140030D13
0x140030c3d  cmp     [rbp+57h+var_6C], 3
0x140030c41  jz      short loc_140030C4D
0x140030c43  mov     ebx, 0C0000010h
0x140030c48  jmp     loc_140030D13
0x140030c4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140030c51  inc     rax
0x140030c54  cmp     [rdi+rax*2+6Ah], r13w
0x140030c5a  jnz     short loc_140030C51
0x140030c5c  lea     rsi, ds:2[rax*2]
0x140030c64  mov     r8d, 4B444342h
0x140030c6a  lea     r14d, [rsi+68h]
0x140030c6e  mov     ecx, 102h
0x140030c73  mov     edx, r14d
0x140030c76  mov     r15d, r14d
0x140030c79  call    cs:__imp_ExAllocatePool2
0x140030c80  nop     dword ptr [rax+rax+00h]
0x140030c85  mov     rbx, rax
0x140030c88  test    rax, rax
0x140030c8b  jnz     short loc_140030C94
0x140030c8d  mov     ebx, 0C000009Ah
0x140030c92  jmp     short loc_140030D13
0x140030c94  mov     r8, r15; Size
0x140030c97  xor     edx, edx; Val
0x140030c99  mov     rcx, rbx; void *
0x140030c9c  call    memset
0x140030ca1  mov     edx, 5
0x140030ca6  mov     [rbx], r13d
0x140030ca9  mov     [rbx+10h], edx
0x140030cac  lea     eax, [rsi+54h]
0x140030caf  mov     [rbx+1Ch], rdx
0x140030cb3  mov     r8, rsi; Size
0x140030cb6  mov     [rbx+18h], eax
0x140030cb9  lea     ecx, [rdx-4]
0x140030cbc  mov     [rbx+8], r14d
0x140030cc0  mov     [rbx+14h], ecx
0x140030cc3  mov     dword ptr [rbx+28h], 48h ; 'H'
0x140030cca  mov     dword ptr [rbx+24h], 10h
0x140030cd1  mov     dword ptr [rbx+30h], 3
0x140030cd8  mov     rax, [rbp+57h+var_50]
0x140030cdc  shl     rax, 0Ch
0x140030ce0  mov     [rbx+34h], rax
0x140030ce4  mov     rax, [rbp+57h+var_60]
0x140030ce8  mov     [rbx+3Ch], rax
0x140030cec  mov     eax, [rbp+57h+var_58]
0x140030cef  mov     [rbx+48h], ecx
0x140030cf2  lea     rcx, [rbx+68h]; void *
0x140030cf6  mov     [rbx+50h], edx
0x140030cf9  lea     rdx, [rdi+6Ah]; Src
0x140030cfd  mov     [rbx+44h], eax
0x140030d00  mov     dword ptr [rbx+4Ch], 0Ch
0x140030d07  call    memmove
0x140030d0c  mov     [r12], rbx
0x140030d10  mov     ebx, r13d
0x140030d13  mov     eax, ebx
0x140030d15  add     rsp, 0E8h
0x140030d1c  pop     r15
0x140030d1e  pop     r14
0x140030d20  pop     r13
0x140030d22  pop     r12
0x140030d24  pop     rdi
0x140030d25  pop     rsi
0x140030d26  pop     rbx
0x140030d27  pop     rbp
0x140030d28  retn
```
