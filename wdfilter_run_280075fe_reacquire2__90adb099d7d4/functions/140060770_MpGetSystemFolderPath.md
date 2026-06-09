# MpGetSystemFolderPath

- ea: `0x140060770`
- end: `0x140060879`
- name: `MpGetSystemFolderPath`
- size: `265`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140037420`
- `0x14006087c`
- `0x140070c9c`
- `0x140086254`

## callees

- `0x1400118d0`
- `0x140060770`
- `0x140078e5c`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140060816`
- `ntoskrnl!ZwOpenFile` at `0x140060816`
- `ntoskrnl!IoFileObjectType` at `0x140060828`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400607c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400607c3`
- `ntoskrnl!ZwClose` at `0x140060849`
- `ntoskrnl!ZwClose` at `0x140060849`

## pseudocode

```c
__int64 __fastcall MpGetSystemFolderPath(PCWSTR SourceString)
{
  NTSTATUS ObjectNameByHandle; // ebx
  void *FileHandle; // [rsp+30h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+2Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp+3Fh] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectNameByHandle = ZwOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4020u);
  if ( ObjectNameByHandle >= 0 )
    ObjectNameByHandle = MpQueryObjectNameByHandle(FileHandle, (POBJECT_TYPE)IoFileObjectType);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)ObjectNameByHandle;
}

```

## disassembly

```asm
0x140060770  mov     [rsp-8+arg_10], rbx
0x140060775  mov     [rsp-8+arg_18], rdi
0x14006077a  push    rbp
0x14006077b  lea     rbp, [rsp-57h]
0x140060780  sub     rsp, 90h
0x140060787  mov     rax, cs:__security_cookie
0x14006078e  xor     rax, rsp
0x140060791  mov     [rbp+57h+var_8], rax
0x140060795  mov     rdi, rdx
0x140060798  mov     [rbp+57h+FileHandle], 0
0x1400607a0  mov     rdx, rcx; SourceString
0x1400607a3  mov     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x1400607aa  xorps   xmm0, xmm0
0x1400607ad  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x1400607b4  xorps   xmm1, xmm1
0x1400607b7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400607bb  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400607bf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1400607c3  call    cs:__imp_RtlInitUnicodeString
0x1400607ca  nop     dword ptr [rax+rax+00h]
0x1400607cf  lea     rax, [rbp+57h+DestinationString]
0x1400607d3  mov     [rsp+90h+OpenOptions], 4020h; OpenOptions
0x1400607db  xorps   xmm0, xmm0
0x1400607de  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400607e2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400607e6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400607ed  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400607f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400607f9  mov     edx, 100000h; DesiredAccess
0x1400607fe  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140060805  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140060809  mov     [rsp+90h+ShareAccess], 3; ShareAccess
0x140060811  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140060816  call    cs:__imp_ZwOpenFile
0x14006081d  nop     dword ptr [rax+rax+00h]
0x140060822  mov     ebx, eax
0x140060824  test    eax, eax
0x140060826  js      short loc_140060840
0x140060828  mov     rdx, cs:__imp_IoFileObjectType
0x14006082f  mov     r8, rdi
0x140060832  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140060836  mov     rdx, [rdx]; ObjectType
0x140060839  call    MpQueryObjectNameByHandle
0x14006083e  mov     ebx, eax
0x140060840  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140060844  test    rcx, rcx
0x140060847  jz      short loc_140060855
0x140060849  call    cs:__imp_ZwClose
0x140060850  nop     dword ptr [rax+rax+00h]
0x140060855  mov     eax, ebx
0x140060857  mov     rcx, [rbp+57h+var_8]
0x14006085b  xor     rcx, rsp; StackCookie
0x14006085e  call    __security_check_cookie
0x140060863  lea     r11, [rsp+90h+var_s0]
0x14006086b  mov     rbx, [r11+20h]
0x14006086f  mov     rdi, [r11+28h]
0x140060873  mov     rsp, r11
0x140060876  pop     rbp
0x140060877  retn
```
