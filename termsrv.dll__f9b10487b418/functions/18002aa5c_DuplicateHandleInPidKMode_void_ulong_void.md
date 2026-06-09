# DuplicateHandleInPidKMode(void *,ulong,void * *)

- ea: `0x18002aa5c`
- end: `0x18002ac34`
- name: `?DuplicateHandleInPidKMode@@YAJPEAXKPEAPEAX@Z`
- size: `472`
- prototype: `__int64 __fastcall(void *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005d970`

## callees

- `0x18000a210`
- `0x1800148d0`
- `0x18002aa5c`
- `0x1800321f0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18002ab5d`
- `ntdll!NtCreateFile` at `0x18002ab5d`
- `ntdll!RtlInitUnicodeString` at `0x18002aae6`
- `ntdll!RtlInitUnicodeString` at `0x18002aae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002abdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002abdd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002abd3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002abd3`

## string_xrefs

- `0x18002ab77`: `CreateFile( DynVc ) failed: 0x%x in %s`

## pseudocode

```c
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
0x18002aa5c  push    rbp
0x18002aa5e  push    rbx
0x18002aa5f  push    rsi
0x18002aa60  push    rdi
0x18002aa61  push    r14
0x18002aa63  lea     rbp, [rsp-37h]
0x18002aa68  sub     rsp, 0E0h
0x18002aa6f  mov     rax, cs:__security_cookie
0x18002aa76  xor     rax, rsp
0x18002aa79  mov     [rbp+57h+var_28], rax
0x18002aa7d  mov     rdi, r8
0x18002aa80  mov     r14d, edx
0x18002aa83  mov     rsi, rcx
0x18002aa86  xorps   xmm0, xmm0
0x18002aa89  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002aa8d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002aa91  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002aa95  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002aa99  xorps   xmm1, xmm1
0x18002aa9c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18002aaa0  mov     [rbp+57h+FileHandle], 0
0x18002aaa8  mov     [rbp+57h+BytesReturned], 0
0x18002aaaf  test    r8, r8
0x18002aab2  jnz     short loc_18002AADB
0x18002aab4  lea     r9, aDuplicatehandl; "DuplicateHandleInPidKMode"
0x18002aabb  lea     r8, aPhtarget; "phTarget"
0x18002aac2  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002aac9  lea     ecx, [rdi+8]; int
0x18002aacc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aad1  mov     ebx, 80070057h
0x18002aad6  jmp     loc_18002AC0F
0x18002aadb  lea     rdx, SourceString; "\\Device\\DrDynVc"
0x18002aae2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002aae6  call    cs:__imp_RtlInitUnicodeString
0x18002aaec  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002aaf3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002aafb  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ab02  lea     rax, [rbp+57h+DestinationString]
0x18002ab06  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002ab0a  xorps   xmm0, xmm0
0x18002ab0d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ab12  mov     [rsp+100h+EaLength], 0; EaLength
0x18002ab1a  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18002ab23  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18002ab2b  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x18002ab33  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x18002ab3b  mov     [rsp+100h+FileAttributes], 0; FileAttributes
0x18002ab43  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x18002ab4c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002ab50  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ab54  mov     edx, 0C0100000h; DesiredAccess
0x18002ab59  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002ab5d  call    cs:__imp_NtCreateFile
0x18002ab63  mov     ebx, eax
0x18002ab65  or      ebx, 10000000h
0x18002ab6b  jge     short loc_18002AB8D
0x18002ab6d  lea     r9, aDuplicatehandl; "DuplicateHandleInPidKMode"
0x18002ab74  mov     r8d, ebx
0x18002ab77  lea     rdx, aCreatefileDynv; "CreateFile( DynVc ) failed: 0x%x in %s"
0x18002ab7e  mov     ecx, 8; int
0x18002ab83  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ab88  jmp     loc_18002AC0F
0x18002ab8d  mov     [rbp+57h+InBuffer], rsi
0x18002ab91  mov     [rbp+57h+var_30], r14d
0x18002ab95  mov     [rbp+57h+OutBuffer], 0
0x18002ab9d  mov     qword ptr [rsp+100h+CreateDisposition], 0; lpOverlapped
0x18002aba6  lea     rax, [rbp+57h+BytesReturned]
0x18002abaa  mov     qword ptr [rsp+100h+ShareAccess], rax; lpBytesReturned
0x18002abaf  mov     [rsp+100h+FileAttributes], 8; nOutBufferSize
0x18002abb7  lea     rax, [rbp+57h+OutBuffer]
0x18002abbb  mov     [rsp+100h+AllocationSize], rax; lpOutBuffer
0x18002abc0  mov     r9d, 0Ch; nInBufferSize
0x18002abc6  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002abca  mov     edx, 388407h; dwIoControlCode
0x18002abcf  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x18002abd3  call    cs:__imp_DeviceIoControl
0x18002abd9  test    eax, eax
0x18002abdb  jnz     short loc_18002AC08
0x18002abdd  call    cs:__imp_GetLastError
0x18002abe3  mov     ebx, eax
0x18002abe5  test    eax, eax
0x18002abe7  jle     short loc_18002ABF2
0x18002abe9  movzx   ebx, ax
0x18002abec  or      ebx, 80070000h
0x18002abf2  mov     r8d, ebx
0x18002abf5  lea     rdx, aIoctlDynvcDupl; "IOCTL( DynVC, DuplicateHandle ) failed "...
0x18002abfc  mov     ecx, 8; int
0x18002ac01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ac06  jmp     short loc_18002AC0F
0x18002ac08  mov     rcx, [rbp+57h+OutBuffer]
0x18002ac0c  mov     [rdi], rcx
0x18002ac0f  lea     rcx, [rbp+57h+FileHandle]; this
0x18002ac13  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18002ac18  mov     eax, ebx
0x18002ac1a  mov     rcx, [rbp+57h+var_28]
0x18002ac1e  xor     rcx, rsp; StackCookie
0x18002ac21  call    __security_check_cookie
0x18002ac26  add     rsp, 0E0h
0x18002ac2d  pop     r14
0x18002ac2f  pop     rdi
0x18002ac30  pop     rsi
0x18002ac31  pop     rbx
0x18002ac32  pop     rbp
0x18002ac33  retn
```
