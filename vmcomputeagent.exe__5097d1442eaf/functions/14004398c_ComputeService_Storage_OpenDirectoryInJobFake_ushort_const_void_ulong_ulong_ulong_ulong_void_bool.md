# ComputeService::Storage::OpenDirectoryInJobFake(ushort const *,void *,ulong,ulong,ulong,ulong,void *,bool *)

- ea: `0x14004398c`
- end: `0x140043b00`
- name: `?OpenDirectoryInJobFake@Storage@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXKKKK1PEA_N@Z`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140042bc4`
- `0x140043140`

## callees

- `0x140005360`
- `0x14004398c`
- `0x140044880`
- `0x140044adc`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x140043a86`
- `ntdll!RtlFreeUnicodeString` at `0x140043a86`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400439da`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400439da`
- `ntdll!RtlInitUnicodeString` at `0x1400439fb`
- `ntdll!RtlInitUnicodeString` at `0x1400439fb`
- `ntdll!NtCreateFile` at `0x140043a7a`
- `ntdll!NtCreateFile` at `0x140043a7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043aae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140043aae`

## string_xrefs

- `0x140043ae1`: `onecore\vm\compute\shared\storage\storageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall ComputeService::Storage::OpenDirectoryInJobFake(
        void **a1,
        const WCHAR *a2,
        void *a3,
        ACCESS_MASK a4,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        int a7)
{
  int v10; // eax
  NTSTATUS v11; // edi
  void *v12; // rdx
  unsigned int v13; // r8d
  int AllocationSize; // [rsp+20h] [rbp-B1h]
  int AllocationSizea; // [rsp+20h] [rbp-B1h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-69h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-31h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+37h]

  FileHandle = a1;
  DestinationString = 0;
  UnicodeString = 0;
  if ( a3 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
  }
  else
  {
    v10 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a2, &UnicodeString, 0, 0);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
        (const char *)(unsigned int)v10,
        AllocationSize);
    DestinationString = UnicodeString;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  v11 = NtCreateFile(
          &FileHandle,
          a4,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          ShareAccess,
          CreateDisposition,
          a7 | 1,
          0,
          0);
  RtlFreeUnicodeString(&UnicodeString);
  if ( v11 != -1073741766 )
  {
    if ( v11 >= 0 )
    {
      *a1 = FileHandle;
      return a1;
    }
LABEL_13:
    wil::details::in1diag3::Throw_NtStatus(retaddr, v12, v13, (const char *)(unsigned int)v11, AllocationSizea);
  }
  if ( CreateDisposition != 1 )
    goto LABEL_13;
  *a1 = (void *)-1LL;
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(FileHandle);
  return a1;
}

```

## disassembly

```asm
0x14004398c  push    rbp
0x14004398e  push    rbx
0x14004398f  push    rsi
0x140043990  push    rdi
0x140043991  push    r14
0x140043993  lea     rbp, [rsp-0Fh]
0x140043998  sub     rsp, 0E0h
0x14004399f  mov     rax, cs:__security_cookie
0x1400439a6  xor     rax, rsp
0x1400439a9  mov     [rbp+2Fh+var_30], rax
0x1400439ad  mov     r14d, r9d
0x1400439b0  mov     rdi, r8
0x1400439b3  mov     rax, rdx
0x1400439b6  mov     rbx, rcx
0x1400439b9  mov     [rbp+2Fh+FileHandle], rcx
0x1400439bd  xorps   xmm0, xmm0
0x1400439c0  movups  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x1400439c4  xorps   xmm1, xmm1
0x1400439c7  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm1
0x1400439cb  test    r8, r8
0x1400439ce  jnz     short loc_1400439F7
0x1400439d0  xor     r9d, r9d
0x1400439d3  lea     rdx, [rbp+2Fh+UnicodeString]
0x1400439d7  mov     rcx, rax
0x1400439da  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1400439e0  mov     rcx, [rbp+37h]; this
0x1400439e4  test    eax, eax
0x1400439e6  js      loc_140043ADE
0x1400439ec  movaps  xmm0, xmmword ptr [rbp+2Fh+UnicodeString.Length]
0x1400439f0  movdqa  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x1400439f5  jmp     short loc_140043A01
0x1400439f7  lea     rcx, [rbp+2Fh+DestinationString]; DestinationString
0x1400439fb  call    cs:__imp_RtlInitUnicodeString
0x140043a01  mov     qword ptr [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x140043a09  mov     qword ptr [rbp+2Fh+ObjectAttributes.Attributes], 40h ; '@'
0x140043a11  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], rdi
0x140043a15  lea     rax, [rbp+2Fh+DestinationString]
0x140043a19  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x140043a1d  xorps   xmm0, xmm0
0x140043a20  movdqu  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140043a25  movups  xmmword ptr [rbp+2Fh+IoStatusBlock], xmm0
0x140043a29  mov     [rbp+2Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x140043a31  mov     eax, [rbp+2Fh+arg_30]
0x140043a34  or      eax, 1
0x140043a37  mov     [rsp+100h+EaLength], 0; EaLength
0x140043a3f  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x140043a48  mov     [rsp+100h+CreateOptions], eax; CreateOptions
0x140043a4c  mov     esi, [rbp+2Fh+arg_28]
0x140043a4f  mov     [rsp+100h+CreateDisposition], esi; CreateDisposition
0x140043a53  mov     eax, [rbp+2Fh+arg_20]
0x140043a56  mov     [rsp+100h+ShareAccess], eax; ShareAccess
0x140043a5a  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x140043a62  mov     [rsp+100h+AllocationSize], 0; int
0x140043a6b  lea     r9, [rbp+2Fh+IoStatusBlock]; IoStatusBlock
0x140043a6f  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x140043a73  mov     edx, r14d; DesiredAccess
0x140043a76  lea     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x140043a7a  call    cs:__imp_NtCreateFile
0x140043a80  mov     edi, eax
0x140043a82  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x140043a86  call    cs:__imp_RtlFreeUnicodeString
0x140043a8c  cmp     edi, 0C000003Ah
0x140043a92  jnz     short loc_140043AD1
0x140043a94  cmp     esi, 1
0x140043a97  jnz     short loc_140043AF3
0x140043a99  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x140043aa0  mov     rcx, [rbp+2Fh+FileHandle]; hObject
0x140043aa4  lea     rdx, [rcx-1]
0x140043aa8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140043aac  ja      short loc_140043AB4
0x140043aae  call    cs:__imp_CloseHandle
0x140043ab4  mov     rax, rbx
0x140043ab7  mov     rcx, [rbp+2Fh+var_30]
0x140043abb  xor     rcx, rsp; StackCookie
0x140043abe  call    __security_check_cookie
0x140043ac3  add     rsp, 0E0h
0x140043aca  pop     r14
0x140043acc  pop     rdi
0x140043acd  pop     rsi
0x140043ace  pop     rbx
0x140043acf  pop     rbp
0x140043ad0  retn
0x140043ad1  test    edi, edi
0x140043ad3  js      short loc_140043AF3
0x140043ad5  mov     rax, [rbp+2Fh+FileHandle]
0x140043ad9  mov     [rbx], rax
0x140043adc  jmp     short loc_140043AB4
0x140043ade  mov     r9d, eax; char *
0x140043ae1  lea     r8, aOnecoreVmCompu_20; "onecore\\vm\\compute\\shared\\storage\\"...
0x140043ae8  mov     edx, 122h; void *
0x140043aed  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140043af3  mov     rcx, [rbp+37h]; this
0x140043af7  mov     r9d, edi; char *
0x140043afa  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
