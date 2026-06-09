# RedirectionContextCreateRdpdrHandle(_REDIRECTION_CONTEXT *)

- ea: `0x18000f860`
- end: `0x18000f99c`
- name: `?RedirectionContextCreateRdpdrHandle@@YAJPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f270`
- `0x1800114e0`

## callees

- `0x18000f860`
- `0x18001be10`
- `0x1800219d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f8aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f8aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f970`
- `ntdll!RtlInitUnicodeString` at `0x18000f8ea`
- `ntdll!RtlInitUnicodeString` at `0x18000f8ea`
- `ntdll!NtCreateFile` at `0x18000f965`
- `ntdll!NtCreateFile` at `0x18000f965`

## pseudocode

```c
__int64 __fastcall RedirectionContextCreateRdpdrHandle(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[128]; // [rsp+B0h] [rbp-50h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( lpCriticalSection[2].DebugInfo )
  {
    v2 = 0;
  }
  else
  {
    StringCbPrintfW(
      SourceString,
      0x100u,
      L"\\Device\\RdpDr\\TSCLIENT\\%S\\%d",
      "SCARD",
      LODWORD(lpCriticalSection[1].SpinCount));
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtCreateFile(
           (PHANDLE)&lpCriticalSection[2].DebugInfo,
           0xC0100000,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           3u,
           0,
           0,
           0,
           0);
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x18000f860  mov     [rsp-8+arg_8], rbx
0x18000f865  mov     [rsp-8+arg_10], rdi
0x18000f86a  push    rbp
0x18000f86b  lea     rbp, [rsp-0C0h]
0x18000f873  sub     rsp, 1C0h
0x18000f87a  mov     rax, cs:__security_cookie
0x18000f881  xor     rax, rsp
0x18000f884  mov     [rbp+0C0h+var_10], rax
0x18000f88b  xorps   xmm0, xmm0
0x18000f88e  xorps   xmm1, xmm1
0x18000f891  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm0
0x18000f896  mov     rbx, rcx
0x18000f899  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x18000f89d  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f8a1  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x18000f8a6  movups  xmmword ptr [rbp+0C0h+IoStatusBlock], xmm1
0x18000f8aa  call    cs:__imp_EnterCriticalSection
0x18000f8b0  cmp     qword ptr [rbx+50h], 0
0x18000f8b5  jz      short loc_18000F8BE
0x18000f8b7  xor     edi, edi
0x18000f8b9  jmp     loc_18000F96D
0x18000f8be  mov     eax, [rbx+48h]
0x18000f8c1  lea     r9, aScard; "SCARD"
0x18000f8c8  lea     r8, aDeviceRdpdrTsc; "\\Device\\RdpDr\\TSCLIENT\\%S\\%d"
0x18000f8cf  mov     dword ptr [rsp+1C0h+AllocationSize], eax
0x18000f8d3  mov     edx, 100h; unsigned __int64
0x18000f8d8  lea     rcx, [rbp+0C0h+SourceString]; unsigned __int16 *
0x18000f8dc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f8e1  lea     rdx, [rbp+0C0h+SourceString]; SourceString
0x18000f8e5  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x18000f8ea  call    cs:__imp_RtlInitUnicodeString
0x18000f8f0  mov     [rsp+1C0h+EaLength], 0; EaLength
0x18000f8f8  lea     rax, [rsp+1C0h+DestinationString]
0x18000f8fd  mov     [rsp+1C0h+EaBuffer], 0; EaBuffer
0x18000f906  lea     r9, [rbp+0C0h+IoStatusBlock]; IoStatusBlock
0x18000f90a  mov     [rsp+1C0h+CreateOptions], 0; CreateOptions
0x18000f912  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x18000f917  mov     [rsp+1C0h+CreateDisposition], 0; CreateDisposition
0x18000f91f  lea     rcx, [rbx+50h]; FileHandle
0x18000f923  mov     [rsp+1C0h+ShareAccess], 3; ShareAccess
0x18000f92b  xorps   xmm0, xmm0
0x18000f92e  mov     [rsp+1C0h+FileAttributes], 0; FileAttributes
0x18000f936  mov     edx, 0C0100000h; DesiredAccess
0x18000f93b  mov     [rsp+1C0h+AllocationSize], 0; AllocationSize
0x18000f944  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x18000f94c  mov     [rsp+1C0h+ObjectAttributes.RootDirectory], 0
0x18000f955  mov     [rbp+0C0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000f95c  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rax
0x18000f960  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f965  call    cs:__imp_NtCreateFile
0x18000f96b  mov     edi, eax
0x18000f96d  mov     rcx, rbx; lpCriticalSection
0x18000f970  call    cs:__imp_LeaveCriticalSection
0x18000f976  mov     eax, edi
0x18000f978  mov     rcx, [rbp+0C0h+var_10]
0x18000f97f  xor     rcx, rsp; StackCookie
0x18000f982  call    __security_check_cookie
0x18000f987  lea     r11, [rsp+1C0h+var_s0]
0x18000f98f  mov     rbx, [r11+18h]
0x18000f993  mov     rdi, [r11+20h]
0x18000f997  mov     rsp, r11
0x18000f99a  pop     rbp
0x18000f99b  retn
```
