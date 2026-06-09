# BiCreateVhdRamdiskBootDevice

- ea: `0x140030b8c`
- end: `0x140030d7a`
- name: `BiCreateVhdRamdiskBootDevice`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x14003074c`

## callees

- `0x14000da31`
- `0x14000da55`
- `0x14000db06`
- `0x14000db18`
- `0x1400116c0`
- `0x1400119c0`
- `0x140030b8c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030cc9`
- `ntoskrnl!ExAllocatePool2` at `0x140030cc9`

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
0x140030b8c  push    rbp
0x140030b8e  push    rbx
0x140030b8f  push    rsi
0x140030b90  push    rdi
0x140030b91  push    r12
0x140030b93  push    r13
0x140030b95  push    r14
0x140030b97  push    r15
0x140030b99  lea     rbp, [rsp-1Fh]
0x140030b9e  sub     rsp, 0E8h
0x140030ba5  xorps   xmm0, xmm0
0x140030ba8  xor     eax, eax
0x140030baa  mov     r12, rdx
0x140030bad  mov     rdi, rcx
0x140030bb0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140030bb4  xor     edx, edx; Val
0x140030bb6  lea     rcx, [rbp+57h+var_80]; void *
0x140030bba  lea     esi, [rax+40h]
0x140030bbd  mov     r8d, esi; Size
0x140030bc0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140030bc4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140030bc8  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140030bcc  call    memset
0x140030bd1  xorps   xmm0, xmm0
0x140030bd4  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140030bdb  xor     r13d, r13d
0x140030bde  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140030be2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140030be6  mov     [rbp+57h+FileHandle], r13
0x140030bea  call    RtlInitUnicodeString_0
0x140030bef  lea     rax, [rbp+57h+DestinationString]
0x140030bf3  mov     [rsp+120h+OpenOptions], 20h ; ' '; OpenOptions
0x140030bfb  xorps   xmm0, xmm0
0x140030bfe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140030c02  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140030c06  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140030c0d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140030c11  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x140030c15  mov     edx, 0C0000000h; DesiredAccess
0x140030c1a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140030c21  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030c25  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140030c2d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140030c32  call    ZwOpenFile_0
0x140030c37  mov     ebx, eax
0x140030c39  test    eax, eax
0x140030c3b  js      loc_140030D63
0x140030c41  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140030c45  lea     rax, [rbp+57h+var_80]
0x140030c49  mov     [rsp+120h+OutputBufferLength], esi; OutputBufferLength
0x140030c4d  xor     r9d, r9d; ApcContext
0x140030c50  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x140030c55  xor     r8d, r8d; ApcRoutine
0x140030c58  mov     [rsp+120h+InputBufferLength], r13d; InputBufferLength
0x140030c5d  lea     rax, [rbp+57h+IoStatusBlock]
0x140030c61  mov     [rsp+120h+InputBuffer], r13; InputBuffer
0x140030c66  xor     edx, edx; Event
0x140030c68  mov     [rsp+120h+OpenOptions], 240008h; IoControlCode
0x140030c70  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x140030c75  call    ZwDeviceIoControlFile_0
0x140030c7a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140030c7e  mov     ebx, eax
0x140030c80  call    ZwClose_0
0x140030c85  test    ebx, ebx
0x140030c87  js      loc_140030D63
0x140030c8d  cmp     [rbp+57h+var_6C], 3
0x140030c91  jz      short loc_140030C9D
0x140030c93  mov     ebx, 0C0000010h
0x140030c98  jmp     loc_140030D63
0x140030c9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140030ca1  inc     rax
0x140030ca4  cmp     [rdi+rax*2+6Ah], r13w
0x140030caa  jnz     short loc_140030CA1
0x140030cac  lea     rsi, ds:2[rax*2]
0x140030cb4  mov     r8d, 4B444342h
0x140030cba  lea     r14d, [rsi+68h]
0x140030cbe  mov     ecx, 102h
0x140030cc3  mov     edx, r14d
0x140030cc6  mov     r15d, r14d
0x140030cc9  call    cs:__imp_ExAllocatePool2
0x140030cd0  nop     dword ptr [rax+rax+00h]
0x140030cd5  mov     rbx, rax
0x140030cd8  test    rax, rax
0x140030cdb  jnz     short loc_140030CE4
0x140030cdd  mov     ebx, 0C000009Ah
0x140030ce2  jmp     short loc_140030D63
0x140030ce4  mov     r8, r15; Size
0x140030ce7  xor     edx, edx; Val
0x140030ce9  mov     rcx, rbx; void *
0x140030cec  call    memset
0x140030cf1  mov     edx, 5
0x140030cf6  mov     [rbx], r13d
0x140030cf9  mov     [rbx+10h], edx
0x140030cfc  lea     eax, [rsi+54h]
0x140030cff  mov     [rbx+1Ch], rdx
0x140030d03  mov     r8, rsi; Size
0x140030d06  mov     [rbx+18h], eax
0x140030d09  lea     ecx, [rdx-4]
0x140030d0c  mov     [rbx+8], r14d
0x140030d10  mov     [rbx+14h], ecx
0x140030d13  mov     dword ptr [rbx+28h], 48h ; 'H'
0x140030d1a  mov     dword ptr [rbx+24h], 10h
0x140030d21  mov     dword ptr [rbx+30h], 3
0x140030d28  mov     rax, [rbp+57h+var_50]
0x140030d2c  shl     rax, 0Ch
0x140030d30  mov     [rbx+34h], rax
0x140030d34  mov     rax, [rbp+57h+var_60]
0x140030d38  mov     [rbx+3Ch], rax
0x140030d3c  mov     eax, [rbp+57h+var_58]
0x140030d3f  mov     [rbx+48h], ecx
0x140030d42  lea     rcx, [rbx+68h]; void *
0x140030d46  mov     [rbx+50h], edx
0x140030d49  lea     rdx, [rdi+6Ah]; Src
0x140030d4d  mov     [rbx+44h], eax
0x140030d50  mov     dword ptr [rbx+4Ch], 0Ch
0x140030d57  call    memmove
0x140030d5c  mov     [r12], rbx
0x140030d60  mov     ebx, r13d
0x140030d63  mov     eax, ebx
0x140030d65  add     rsp, 0E8h
0x140030d6c  pop     r15
0x140030d6e  pop     r14
0x140030d70  pop     r13
0x140030d72  pop     r12
0x140030d74  pop     rdi
0x140030d75  pop     rsi
0x140030d76  pop     rbx
0x140030d77  pop     rbp
0x140030d78  retn
```
