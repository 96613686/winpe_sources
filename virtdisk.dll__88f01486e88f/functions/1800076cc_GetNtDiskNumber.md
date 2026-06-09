# GetNtDiskNumber

- ea: `0x1800076cc`
- end: `0x1800078ed`
- name: `GetNtDiskNumber`
- size: `545`
- prototype: `ULONG __fastcall(PCWSTR SourceString, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180001010`
- `0x180004b50`

## callees

- `0x180005730`
- `0x1800076cc`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800077a3`
- `ntdll!NtCreateFile` at `0x1800077a3`
- `ntdll!NtCreateEvent` at `0x1800077d0`
- `ntdll!NtCreateEvent` at `0x1800077d0`
- `ntdll!NtDeviceIoControlFile` at `0x180007827`
- `ntdll!NtDeviceIoControlFile` at `0x180007827`
- `ntdll!NtWaitForSingleObject` at `0x180007845`
- `ntdll!NtWaitForSingleObject` at `0x180007845`
- `ntdll!NtClose` at `0x180007897`
- `ntdll!NtClose` at `0x1800078b1`
- `ntdll!NtClose` at `0x180007897`
- `ntdll!NtClose` at `0x1800078b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800078bf`
- `ntdll!RtlNtStatusToDosError` at `0x1800078bf`
- `ntdll!RtlInitUnicodeString` at `0x18000772a`
- `ntdll!RtlInitUnicodeString` at `0x18000772a`

## pseudocode

```c
ULONG __fastcall GetNtDiskNumber(PCWSTR SourceString, __int64 a2)
{
  int Status; // ebx
  __int64 v4; // rcx
  int v5; // eax
  HANDLE EventHandle; // [rsp+60h] [rbp-29h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+27h] BYREF
  __int64 OutputBuffer; // [rsp+C0h] [rbp+37h] BYREF
  int v13; // [rsp+C8h] [rbp+3Fh]

  OutputBuffer = 0;
  v13 = 0;
  FileHandle = (HANDLE)-1LL;
  EventHandle = (HANDLE)-1LL;
  DestinationString = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  Status = NtCreateFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0, 0, 0);
  if ( Status >= 0 )
  {
    Status = NtCreateEvent(&EventHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( Status >= 0 )
    {
      Status = NtDeviceIoControlFile(
                 FileHandle,
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 0x2D1080u,
                 0,
                 0,
                 &OutputBuffer,
                 0xCu);
      if ( Status == 259 )
      {
        NtWaitForSingleObject(EventHandle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status >= 0 )
      {
        if ( (unsigned int)OutputBuffer <= 0x24 && (v4 = 0x1000000084LL, _bittest64(&v4, (unsigned int)OutputBuffer)) )
        {
          Status = 0;
          v5 = v13;
          *(_QWORD *)a2 = OutputBuffer;
          *(_DWORD *)(a2 + 8) = v5;
        }
        else
        {
          Status = -1073741811;
        }
      }
    }
  }
  if ( (char *)EventHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtClose(EventHandle);
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtClose(FileHandle);
  return RtlNtStatusToDosError(Status);
}

```

## disassembly

```asm
0x1800076cc  mov     [rsp-8+arg_10], rbx
0x1800076d1  mov     [rsp-8+arg_18], rdi
0x1800076d6  push    rbp
0x1800076d7  lea     rbp, [rsp-57h]
0x1800076dc  sub     rsp, 0E0h
0x1800076e3  mov     rax, cs:__security_cookie
0x1800076ea  xor     rax, rsp
0x1800076ed  mov     [rbp+57h+var_10], rax
0x1800076f1  xorps   xmm0, xmm0
0x1800076f4  xor     eax, eax
0x1800076f6  mov     [rbp+57h+OutputBuffer], rax
0x1800076fa  mov     rdi, rdx
0x1800076fd  mov     [rbp+57h+var_18], eax
0x180007700  xorps   xmm1, xmm1
0x180007703  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007707  mov     rdx, rcx; SourceString
0x18000770a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000770e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180007712  mov     [rbp+57h+FileHandle], rax
0x180007716  mov     [rbp+57h+EventHandle], rax
0x18000771a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000771e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180007722  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180007726  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000772a  call    cs:__imp_RtlInitUnicodeString
0x180007731  nop     dword ptr [rax+rax+00h]
0x180007736  mov     [rsp+0E0h+EaLength], 0; EaLength
0x18000773e  lea     rax, [rbp+57h+DestinationString]
0x180007742  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x18000774b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000774f  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x180007757  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000775b  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x180007763  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180007767  mov     edx, 80h; DesiredAccess
0x18000776c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180007774  xorps   xmm0, xmm0
0x180007777  mov     [rsp+0E0h+FileAttributes], edx; FileAttributes
0x18000777b  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x180007784  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000778b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180007793  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000779a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000779e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800077a3  call    cs:__imp_NtCreateFile
0x1800077aa  nop     dword ptr [rax+rax+00h]
0x1800077af  mov     ebx, eax
0x1800077b1  test    eax, eax
0x1800077b3  js      loc_180007889
0x1800077b9  mov     r9d, 1; EventType
0x1800077bf  mov     byte ptr [rsp+0E0h+AllocationSize], 0; InitialState
0x1800077c4  xor     r8d, r8d; ObjectAttributes
0x1800077c7  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x1800077cb  mov     edx, 1F0003h; DesiredAccess
0x1800077d0  call    cs:__imp_NtCreateEvent
0x1800077d7  nop     dword ptr [rax+rax+00h]
0x1800077dc  mov     ebx, eax
0x1800077de  test    eax, eax
0x1800077e0  js      loc_180007889
0x1800077e6  mov     rdx, [rbp+57h+EventHandle]; Event
0x1800077ea  lea     rax, [rbp+57h+OutputBuffer]
0x1800077ee  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800077f2  xor     r9d, r9d; ApcContext
0x1800077f5  mov     dword ptr [rsp+0E0h+EaBuffer], 0Ch; OutputBufferLength
0x1800077fd  xor     r8d, r8d; ApcRoutine
0x180007800  mov     qword ptr [rsp+0E0h+CreateOptions], rax; OutputBuffer
0x180007805  lea     rax, [rbp+57h+IoStatusBlock]
0x180007809  mov     [rsp+0E0h+CreateDisposition], 0; InputBufferLength
0x180007811  mov     qword ptr [rsp+0E0h+ShareAccess], 0; InputBuffer
0x18000781a  mov     [rsp+0E0h+FileAttributes], 2D1080h; IoControlCode
0x180007822  mov     [rsp+0E0h+AllocationSize], rax; IoStatusBlock
0x180007827  call    cs:__imp_NtDeviceIoControlFile
0x18000782e  nop     dword ptr [rax+rax+00h]
0x180007833  mov     ebx, eax
0x180007835  cmp     eax, 103h
0x18000783a  jnz     short loc_180007854
0x18000783c  mov     rcx, [rbp+57h+EventHandle]; Handle
0x180007840  xor     r8d, r8d; Timeout
0x180007843  xor     edx, edx; Alertable
0x180007845  call    cs:__imp_NtWaitForSingleObject
0x18000784c  nop     dword ptr [rax+rax+00h]
0x180007851  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x180007854  test    ebx, ebx
0x180007856  js      short loc_180007889
0x180007858  cmp     dword ptr [rbp+57h+OutputBuffer], 24h ; '$'
0x18000785c  ja      short loc_180007884
0x18000785e  mov     eax, dword ptr [rbp+57h+OutputBuffer]
0x180007861  mov     rcx, 1000000084h
0x18000786b  bt      rcx, rax
0x18000786f  jnb     short loc_180007884
0x180007871  movsd   xmm0, [rbp+57h+OutputBuffer]
0x180007876  xor     ebx, ebx
0x180007878  mov     eax, [rbp+57h+var_18]
0x18000787b  movsd   qword ptr [rdi], xmm0
0x18000787f  mov     [rdi+8], eax
0x180007882  jmp     short loc_180007889
0x180007884  mov     ebx, 0C000000Dh
0x180007889  mov     rcx, [rbp+57h+EventHandle]; Handle
0x18000788d  lea     rax, [rcx-1]
0x180007891  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007895  ja      short loc_1800078A3
0x180007897  call    cs:__imp_NtClose
0x18000789e  nop     dword ptr [rax+rax+00h]
0x1800078a3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800078a7  lea     rax, [rcx-1]
0x1800078ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800078af  ja      short loc_1800078BD
0x1800078b1  call    cs:__imp_NtClose
0x1800078b8  nop     dword ptr [rax+rax+00h]
0x1800078bd  mov     ecx, ebx; Status
0x1800078bf  call    cs:__imp_RtlNtStatusToDosError
0x1800078c6  nop     dword ptr [rax+rax+00h]
0x1800078cb  mov     rcx, [rbp+57h+var_10]
0x1800078cf  xor     rcx, rsp; StackCookie
0x1800078d2  call    __security_check_cookie
0x1800078d7  lea     r11, [rsp+0E0h+var_s0]
0x1800078df  mov     rbx, [r11+20h]
0x1800078e3  mov     rdi, [r11+28h]
0x1800078e7  mov     rsp, r11
0x1800078ea  pop     rbp
0x1800078eb  retn
```
