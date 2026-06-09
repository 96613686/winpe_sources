# DuplicateHandleInPidKMode(void *,ulong,void * *)

- ea: `0x18002c17c`
- end: `0x18002c36d`
- name: `?DuplicateHandleInPidKMode@@YAJPEAXKPEAPEAX@Z`
- size: `497`
- prototype: `__int64 __fastcall(void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180060880`

## callees

- `0x180009940`
- `0x180015020`
- `0x18002c17c`
- `0x180033f60`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18002c283`
- `ntdll!NtCreateFile` at `0x18002c283`
- `ntdll!RtlInitUnicodeString` at `0x18002c206`
- `ntdll!RtlInitUnicodeString` at `0x18002c206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c30f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002c2ff`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002c2ff`

## string_xrefs

- `0x18002c2a3`: `CreateFile( DynVc ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DuplicateHandleInPidKMode(void *a1, int a2, void **a3)
{
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+60h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+7h] BYREF
  void *OutBuffer; // [rsp+C0h] [rbp+17h] BYREF
  void *InBuffer; // [rsp+C8h] [rbp+1Fh] BYREF
  int v17; // [rsp+D0h] [rbp+27h]

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  BytesReturned = 0;
  if ( a3 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\DrDynVc");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0, 0, 0);
    v6 = v7 | 0x10000000;
    if ( v7 >= 0 )
    {
      InBuffer = a1;
      v17 = a2;
      OutBuffer = 0;
      if ( DeviceIoControl(FileHandle, 0x388407u, &InBuffer, 0xCu, &OutBuffer, 8u, &BytesReturned, 0) )
      {
        *a3 = OutBuffer;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "IOCTL( DynVC, DuplicateHandle ) failed 0x%x", v6);
      }
    }
    else
    {
      _DbgPrintMessage(8, "CreateFile( DynVc ) failed: 0x%x in %s", v6, "DuplicateHandleInPidKMode");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "phTarget", "DuplicateHandleInPidKMode");
    v6 = -2147024809;
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&FileHandle);
  return v6;
}

```

## disassembly

```asm
0x18002c17c  push    rbp
0x18002c17e  push    rbx
0x18002c17f  push    rsi
0x18002c180  push    rdi
0x18002c181  push    r14
0x18002c183  lea     rbp, [rsp-37h]
0x18002c188  sub     rsp, 0E0h
0x18002c18f  mov     rax, cs:__security_cookie
0x18002c196  xor     rax, rsp
0x18002c199  mov     [rbp+57h+var_28], rax
0x18002c19d  mov     rdi, r8
0x18002c1a0  mov     r14d, edx
0x18002c1a3  mov     rsi, rcx
0x18002c1a6  xorps   xmm0, xmm0
0x18002c1a9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002c1ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002c1b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c1b5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002c1b9  xorps   xmm1, xmm1
0x18002c1bc  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18002c1c0  mov     [rbp+57h+FileHandle], 0
0x18002c1c8  mov     [rbp+57h+BytesReturned], 0
0x18002c1cf  test    r8, r8
0x18002c1d2  jnz     short loc_18002C1FB
0x18002c1d4  lea     r9, aDuplicatehandl; "DuplicateHandleInPidKMode"
0x18002c1db  lea     r8, aPhtarget; "phTarget"
0x18002c1e2  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002c1e9  lea     ecx, [rdi+8]; int
0x18002c1ec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c1f1  mov     ebx, 80070057h
0x18002c1f6  jmp     loc_18002C347
0x18002c1fb  lea     rdx, SourceString; "\\Device\\DrDynVc"
0x18002c202  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002c206  call    cs:__imp_RtlInitUnicodeString
0x18002c20d  nop     dword ptr [rax+rax+00h]
0x18002c212  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002c219  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002c221  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002c228  lea     rax, [rbp+57h+DestinationString]
0x18002c22c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002c230  xorps   xmm0, xmm0
0x18002c233  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c238  mov     [rsp+100h+EaLength], 0; EaLength
0x18002c240  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18002c249  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18002c251  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x18002c259  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x18002c261  mov     [rsp+100h+FileAttributes], 0; FileAttributes
0x18002c269  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x18002c272  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002c276  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002c27a  mov     edx, 0C0100000h; DesiredAccess
0x18002c27f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002c283  call    cs:__imp_NtCreateFile
0x18002c28a  nop     dword ptr [rax+rax+00h]
0x18002c28f  mov     ebx, eax
0x18002c291  or      ebx, 10000000h
0x18002c297  jge     short loc_18002C2B9
0x18002c299  lea     r9, aDuplicatehandl; "DuplicateHandleInPidKMode"
0x18002c2a0  mov     r8d, ebx
0x18002c2a3  lea     rdx, aCreatefileDynv; "CreateFile( DynVc ) failed: 0x%x in %s"
0x18002c2aa  mov     ecx, 8; int
0x18002c2af  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c2b4  jmp     loc_18002C347
0x18002c2b9  mov     [rbp+57h+InBuffer], rsi
0x18002c2bd  mov     [rbp+57h+var_30], r14d
0x18002c2c1  mov     [rbp+57h+OutBuffer], 0
0x18002c2c9  mov     qword ptr [rsp+100h+CreateDisposition], 0; lpOverlapped
0x18002c2d2  lea     rax, [rbp+57h+BytesReturned]
0x18002c2d6  mov     qword ptr [rsp+100h+ShareAccess], rax; lpBytesReturned
0x18002c2db  mov     [rsp+100h+FileAttributes], 8; nOutBufferSize
0x18002c2e3  lea     rax, [rbp+57h+OutBuffer]
0x18002c2e7  mov     [rsp+100h+AllocationSize], rax; lpOutBuffer
0x18002c2ec  mov     r9d, 0Ch; nInBufferSize
0x18002c2f2  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002c2f6  mov     edx, 388407h; dwIoControlCode
0x18002c2fb  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x18002c2ff  call    cs:__imp_DeviceIoControl
0x18002c306  nop     dword ptr [rax+rax+00h]
0x18002c30b  test    eax, eax
0x18002c30d  jnz     short loc_18002C340
0x18002c30f  call    cs:__imp_GetLastError
0x18002c316  nop     dword ptr [rax+rax+00h]
0x18002c31b  mov     ebx, eax
0x18002c31d  test    eax, eax
0x18002c31f  jle     short loc_18002C32A
0x18002c321  movzx   ebx, ax
0x18002c324  or      ebx, 80070000h
0x18002c32a  mov     r8d, ebx
0x18002c32d  lea     rdx, aIoctlDynvcDupl; "IOCTL( DynVC, DuplicateHandle ) failed "...
0x18002c334  mov     ecx, 8; int
0x18002c339  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c33e  jmp     short loc_18002C347
0x18002c340  mov     rcx, [rbp+57h+OutBuffer]
0x18002c344  mov     [rdi], rcx
0x18002c347  lea     rcx, [rbp+57h+FileHandle]; this
0x18002c34b  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18002c350  mov     eax, ebx
0x18002c352  mov     rcx, [rbp+57h+var_28]
0x18002c356  xor     rcx, rsp; StackCookie
0x18002c359  call    __security_check_cookie
0x18002c35e  add     rsp, 0E0h
0x18002c365  pop     r14
0x18002c367  pop     rdi
0x18002c368  pop     rsi
0x18002c369  pop     rbx
0x18002c36a  pop     rbp
0x18002c36b  retn
```
