# BiCreateVhdRamdiskBootDevice

- ea: `0x180067c70`
- end: `0x180067e7e`
- name: `BiCreateVhdRamdiskBootDevice`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800677a4`

## callees

- `0x180003c78`
- `0x180004829`
- `0x180067c70`

## import_xrefs

- `ntdll!ZwClose` at `0x180067d79`
- `ntdll!ZwClose` at `0x180067d79`
- `ntdll!ZwDeviceIoControlFile` at `0x180067d67`
- `ntdll!ZwDeviceIoControlFile` at `0x180067d67`
- `ntdll!ZwOpenFile` at `0x180067d1d`
- `ntdll!ZwOpenFile` at `0x180067d1d`
- `ntdll!RtlAllocateHeap` at `0x180067dcd`
- `ntdll!RtlAllocateHeap` at `0x180067dcd`
- `ntdll!RtlInitUnicodeString` at `0x180067cce`
- `ntdll!RtlInitUnicodeString` at `0x180067cce`

## pseudocode

```c
__int64 __fastcall BiCreateVhdRamdiskBootDevice(__int64 a1, _QWORD *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  size_t v6; // rsi
  unsigned int v7; // r14d
  char *Heap; // rax
  char *v9; // rbx
  int v10; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  _BYTE OutputBuffer[20]; // [rsp+A0h] [rbp-29h] BYREF
  int v16; // [rsp+B4h] [rbp-15h]
  __int64 v17; // [rsp+C0h] [rbp-9h]
  int v18; // [rsp+C8h] [rbp-1h]
  __int64 v19; // [rsp+D0h] [rbp+7h]
  void *FileHandle; // [rsp+140h] [rbp+77h] BYREF

  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  memset_0(OutputBuffer, 0, 0x40u);
  DestinationString = 0;
  FileHandle = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v4 = ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v4 >= 0 )
  {
    v4 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose(FileHandle);
    if ( v4 >= 0 )
    {
      if ( v16 == 3 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)(a1 + 2 * v5 + 106) );
        v6 = 2 * v5 + 2;
        v7 = 2 * v5 + 106;
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v9 = Heap;
        if ( Heap )
        {
          memset_0(Heap, 0, v7);
          *(_DWORD *)v9 = 0;
          *((_DWORD *)v9 + 4) = 5;
          *(_QWORD *)(v9 + 28) = 5;
          *((_DWORD *)v9 + 6) = v6 + 84;
          *((_DWORD *)v9 + 2) = v7;
          *((_DWORD *)v9 + 5) = 1;
          *((_DWORD *)v9 + 10) = 72;
          *((_DWORD *)v9 + 9) = 16;
          *((_DWORD *)v9 + 12) = 3;
          *(_QWORD *)(v9 + 52) = v19 << 12;
          *(_QWORD *)(v9 + 60) = v17;
          v10 = v18;
          *((_DWORD *)v9 + 18) = 1;
          *((_DWORD *)v9 + 20) = 5;
          *((_DWORD *)v9 + 17) = v10;
          *((_DWORD *)v9 + 19) = 12;
          memcpy_0(v9 + 104, (const void *)(a1 + 106), v6);
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
0x180067c70  push    rbp
0x180067c72  push    rbx
0x180067c73  push    rsi
0x180067c74  push    rdi
0x180067c75  push    r12
0x180067c77  push    r13
0x180067c79  push    r14
0x180067c7b  push    r15
0x180067c7d  lea     rbp, [rsp-1Fh]
0x180067c82  sub     rsp, 0E8h
0x180067c89  xorps   xmm0, xmm0
0x180067c8c  xor     eax, eax
0x180067c8e  mov     r12, rdx
0x180067c91  mov     rdi, rcx
0x180067c94  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180067c98  xor     edx, edx; Val
0x180067c9a  lea     rcx, [rbp+57h+var_80]; void *
0x180067c9e  lea     esi, [rax+40h]
0x180067ca1  mov     r8d, esi; Size
0x180067ca4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180067ca8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180067cac  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180067cb0  call    memset_0
0x180067cb5  xorps   xmm0, xmm0
0x180067cb8  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x180067cbf  xor     r13d, r13d
0x180067cc2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180067cc6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180067cca  mov     [rbp+57h+FileHandle], r13
0x180067cce  call    cs:__imp_RtlInitUnicodeString
0x180067cd5  nop     dword ptr [rax+rax+00h]
0x180067cda  lea     rax, [rbp+57h+DestinationString]
0x180067cde  mov     [rsp+120h+OpenOptions], 20h ; ' '; OpenOptions
0x180067ce6  xorps   xmm0, xmm0
0x180067ce9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180067ced  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180067cf1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180067cf8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180067cfc  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180067d00  mov     edx, 0C0000000h; DesiredAccess
0x180067d05  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180067d0c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180067d10  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x180067d18  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180067d1d  call    cs:__imp_ZwOpenFile
0x180067d24  nop     dword ptr [rax+rax+00h]
0x180067d29  mov     ebx, eax
0x180067d2b  test    eax, eax
0x180067d2d  js      loc_180067E67
0x180067d33  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180067d37  lea     rax, [rbp+57h+var_80]
0x180067d3b  mov     [rsp+120h+OutputBufferLength], esi; OutputBufferLength
0x180067d3f  xor     r9d, r9d; ApcContext
0x180067d42  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x180067d47  xor     r8d, r8d; ApcRoutine
0x180067d4a  mov     [rsp+120h+InputBufferLength], r13d; InputBufferLength
0x180067d4f  lea     rax, [rbp+57h+IoStatusBlock]
0x180067d53  mov     [rsp+120h+InputBuffer], r13; InputBuffer
0x180067d58  xor     edx, edx; Event
0x180067d5a  mov     [rsp+120h+OpenOptions], 240008h; IoControlCode
0x180067d62  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x180067d67  call    cs:__imp_ZwDeviceIoControlFile
0x180067d6e  nop     dword ptr [rax+rax+00h]
0x180067d73  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180067d77  mov     ebx, eax
0x180067d79  call    cs:__imp_ZwClose
0x180067d80  nop     dword ptr [rax+rax+00h]
0x180067d85  test    ebx, ebx
0x180067d87  js      loc_180067E67
0x180067d8d  cmp     [rbp+57h+var_6C], 3
0x180067d91  jz      short loc_180067D9D
0x180067d93  mov     ebx, 0C0000010h
0x180067d98  jmp     loc_180067E67
0x180067d9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180067da1  inc     rax
0x180067da4  cmp     [rdi+rax*2+6Ah], r13w
0x180067daa  jnz     short loc_180067DA1
0x180067dac  mov     rcx, gs:60h
0x180067db5  lea     rsi, ds:2[rax*2]
0x180067dbd  lea     r14d, [rsi+68h]
0x180067dc1  xor     edx, edx; Flags
0x180067dc3  mov     r8d, r14d; Size
0x180067dc6  mov     r15d, r14d
0x180067dc9  mov     rcx, [rcx+30h]; HeapHandle
0x180067dcd  call    cs:__imp_RtlAllocateHeap
0x180067dd4  nop     dword ptr [rax+rax+00h]
0x180067dd9  mov     rbx, rax
0x180067ddc  test    rax, rax
0x180067ddf  jnz     short loc_180067DE8
0x180067de1  mov     ebx, 0C000009Ah
0x180067de6  jmp     short loc_180067E67
0x180067de8  mov     r8, r15; Size
0x180067deb  xor     edx, edx; Val
0x180067ded  mov     rcx, rbx; void *
0x180067df0  call    memset_0
0x180067df5  mov     edx, 5
0x180067dfa  mov     [rbx], r13d
0x180067dfd  mov     [rbx+10h], edx
0x180067e00  lea     eax, [rsi+54h]
0x180067e03  mov     [rbx+1Ch], rdx
0x180067e07  mov     r8, rsi; Size
0x180067e0a  mov     [rbx+18h], eax
0x180067e0d  lea     ecx, [rdx-4]
0x180067e10  mov     [rbx+8], r14d
0x180067e14  mov     [rbx+14h], ecx
0x180067e17  mov     dword ptr [rbx+28h], 48h ; 'H'
0x180067e1e  mov     dword ptr [rbx+24h], 10h
0x180067e25  mov     dword ptr [rbx+30h], 3
0x180067e2c  mov     rax, [rbp+57h+var_50]
0x180067e30  shl     rax, 0Ch
0x180067e34  mov     [rbx+34h], rax
0x180067e38  mov     rax, [rbp+57h+var_60]
0x180067e3c  mov     [rbx+3Ch], rax
0x180067e40  mov     eax, [rbp+57h+var_58]
0x180067e43  mov     [rbx+48h], ecx
0x180067e46  lea     rcx, [rbx+68h]; void *
0x180067e4a  mov     [rbx+50h], edx
0x180067e4d  lea     rdx, [rdi+6Ah]; Src
0x180067e51  mov     [rbx+44h], eax
0x180067e54  mov     dword ptr [rbx+4Ch], 0Ch
0x180067e5b  call    memcpy_0
0x180067e60  mov     [r12], rbx
0x180067e64  mov     ebx, r13d
0x180067e67  mov     eax, ebx
0x180067e69  add     rsp, 0E8h
0x180067e70  pop     r15
0x180067e72  pop     r14
0x180067e74  pop     r13
0x180067e76  pop     r12
0x180067e78  pop     rdi
0x180067e79  pop     rsi
0x180067e7a  pop     rbx
0x180067e7b  pop     rbp
0x180067e7c  retn
```
