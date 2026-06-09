# ComputeService::Storage::OpenDirectoryInJobFake(ushort const *,void *,ulong,ulong,ulong,ulong,void *,bool *)

- ea: `0x140232db8`
- end: `0x140232f52`
- name: `?OpenDirectoryInJobFake@Storage@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXKKKK1PEA_N@Z`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400899cc`
- `0x1400d40b8`

## callees

- `0x140024030`
- `0x140024f6c`
- `0x1401332f0`
- `0x140142dac`
- `0x140232db8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140232e40`
- `ntdll!RtlInitUnicodeString` at `0x140232e40`
- `ntdll!RtlFreeUnicodeString` at `0x140232ee3`
- `ntdll!RtlFreeUnicodeString` at `0x140232ee3`
- `ntdll!NtCreateFile` at `0x140232ed1`
- `ntdll!NtCreateFile` at `0x140232ed1`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x140232e08`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x140232e08`

## string_xrefs

- `0x140232e1f`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x140232f40`: `onecore\vm\compute\shared\storage\storageutilities.cpp`

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
  int AllocationSize; // [rsp+20h] [rbp-C1h]
  int AllocationSizea; // [rsp+20h] [rbp-C1h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-79h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-41h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+37h]

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
      wil::details::in1diag3::Throw_NtStatus(
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
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &FileHandle,
    -1);
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
      FileHandle = (void *)-1LL;
      goto LABEL_9;
    }
LABEL_12:
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      (const char *)(unsigned int)v11,
      AllocationSizea);
  }
  if ( CreateDisposition != 1 )
    goto LABEL_12;
  *a1 = (void *)-1LL;
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return a1;
}

```

## disassembly

```asm
0x140232db8  push    rbp
0x140232dba  push    rbx
0x140232dbb  push    rsi
0x140232dbc  push    rdi
0x140232dbd  push    r12
0x140232dbf  push    r14
0x140232dc1  lea     rbp, [rsp-7]
0x140232dc6  sub     rsp, 0E8h
0x140232dcd  mov     rax, cs:__security_cookie
0x140232dd4  xor     rax, rsp
0x140232dd7  mov     [rbp+2Fh+var_40], rax
0x140232ddb  mov     r14d, r9d
0x140232dde  mov     rdi, r8
0x140232de1  mov     rax, rdx
0x140232de4  mov     rbx, rcx
0x140232de7  mov     [rbp+2Fh+FileHandle], rcx
0x140232deb  xorps   xmm0, xmm0
0x140232dee  movups  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x140232df2  xorps   xmm1, xmm1
0x140232df5  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm1
0x140232df9  test    r8, r8
0x140232dfc  jnz     short loc_140232E3C
0x140232dfe  xor     r9d, r9d
0x140232e01  lea     rdx, [rbp+2Fh+UnicodeString]
0x140232e05  mov     rcx, rax
0x140232e08  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x140232e0f  nop     dword ptr [rax+rax+00h]
0x140232e14  mov     rcx, [rbp+37h]; this
0x140232e18  test    eax, eax
0x140232e1a  jns     short loc_140232E31
0x140232e1c  mov     r9d, eax; char *
0x140232e1f  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140232e26  mov     edx, 122h; void *
0x140232e2b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x140232e31  movaps  xmm0, xmmword ptr [rbp+2Fh+UnicodeString.Length]
0x140232e35  movdqa  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x140232e3a  jmp     short loc_140232E4C
0x140232e3c  lea     rcx, [rbp+2Fh+DestinationString]; DestinationString
0x140232e40  call    cs:__imp_RtlInitUnicodeString
0x140232e47  nop     dword ptr [rax+rax+00h]
0x140232e4c  mov     qword ptr [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x140232e54  mov     qword ptr [rbp+2Fh+ObjectAttributes.Attributes], 40h ; '@'
0x140232e5c  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], rdi
0x140232e60  lea     rax, [rbp+2Fh+DestinationString]
0x140232e64  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x140232e68  xorps   xmm0, xmm0
0x140232e6b  movdqu  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140232e70  movups  xmmword ptr [rbp+2Fh+IoStatusBlock], xmm0
0x140232e74  or      r12, 0FFFFFFFFFFFFFFFFh
0x140232e78  mov     [rbp+2Fh+FileHandle], r12
0x140232e7c  mov     rdx, r12
0x140232e7f  lea     rcx, [rbp+2Fh+FileHandle]
0x140232e83  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140232e88  mov     eax, [rbp+2Fh+arg_30]
0x140232e8b  or      eax, 1
0x140232e8e  mov     [rsp+110h+EaLength], 0; EaLength
0x140232e96  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x140232e9f  mov     [rsp+110h+CreateOptions], eax; CreateOptions
0x140232ea3  mov     esi, [rbp+2Fh+arg_28]
0x140232ea6  mov     [rsp+110h+CreateDisposition], esi; CreateDisposition
0x140232eaa  mov     eax, [rbp+2Fh+arg_20]
0x140232ead  mov     [rsp+110h+ShareAccess], eax; ShareAccess
0x140232eb1  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x140232eb9  mov     [rsp+110h+AllocationSize], 0; int
0x140232ec2  lea     r9, [rbp+2Fh+IoStatusBlock]; IoStatusBlock
0x140232ec6  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x140232eca  mov     edx, r14d; DesiredAccess
0x140232ecd  lea     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x140232ed1  call    cs:__imp_NtCreateFile
0x140232ed8  nop     dword ptr [rax+rax+00h]
0x140232edd  mov     edi, eax
0x140232edf  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x140232ee3  call    cs:__imp_RtlFreeUnicodeString
0x140232eea  nop     dword ptr [rax+rax+00h]
0x140232eef  cmp     edi, 0C000003Ah
0x140232ef5  jnz     short loc_140232F28
0x140232ef7  cmp     esi, 1
0x140232efa  jnz     short loc_140232F39
0x140232efc  mov     [rbx], r12
0x140232eff  lea     rcx, [rbp+2Fh+FileHandle]; void *
0x140232f03  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140232f08  mov     rax, rbx
0x140232f0b  mov     rcx, [rbp+2Fh+var_40]
0x140232f0f  xor     rcx, rsp; StackCookie
0x140232f12  call    __security_check_cookie
0x140232f17  add     rsp, 0E8h
0x140232f1e  pop     r14
0x140232f20  pop     r12
0x140232f22  pop     rdi
0x140232f23  pop     rsi
0x140232f24  pop     rbx
0x140232f25  pop     rbp
0x140232f26  retn
0x140232f28  test    edi, edi
0x140232f2a  js      short loc_140232F39
0x140232f2c  mov     rax, [rbp+2Fh+FileHandle]
0x140232f30  mov     [rbx], rax
0x140232f33  mov     [rbp+2Fh+FileHandle], r12
0x140232f37  jmp     short loc_140232EFF
0x140232f39  mov     rcx, [rbp+37h]; this
0x140232f3d  mov     r9d, edi; char *
0x140232f40  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140232f47  mov     edx, 155h; void *
0x140232f4c  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
