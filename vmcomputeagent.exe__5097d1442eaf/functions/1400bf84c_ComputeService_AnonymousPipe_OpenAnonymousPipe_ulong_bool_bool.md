# ComputeService::AnonymousPipe::OpenAnonymousPipe(ulong,bool,bool)

- ea: `0x1400bf84c`
- end: `0x1400bfa66`
- name: `?OpenAnonymousPipe@AnonymousPipe@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V12@@std@@K_N0@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400bf578`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x140044adc`
- `0x1400bf84c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400bf9d3`
- `ntdll!NtOpenFile` at `0x1400bf9d3`
- `ntdll!NtCreateNamedPipeFile` at `0x1400bf96e`
- `ntdll!NtCreateNamedPipeFile` at `0x1400bf96e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400bfa05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400bfa05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bf8aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bf8aa`

## string_xrefs

- `0x1400bfa2d`: `onecore\vm\compute\common\compute\AnonymousPipe.h`
- `0x1400bfa3f`: `onecore\vm\compute\common\compute\AnonymousPipe.h`
- `0x1400bfa54`: `onecore\vm\compute\common\compute\AnonymousPipe.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall ComputeService::AnonymousPipe::OpenAnonymousPipe(
        void **a1,
        __int64 a2,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  int v4; // r14d
  int v5; // esi
  char *FileW; // rbx
  const char *v8; // r9
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-A9h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-A9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-49h] BYREF
  void *NamedPipeFileHandle; // [rsp+B0h] [rbp-19h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp-11h] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v18; // [rsp+C8h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v4 = a4;
  v5 = a3;
  DefaultTimeOut.QuadPart = (LONGLONG)a1;
  FileW = (char *)CreateFileW(L"\\\\.\\pipe\\", 0x80000000, 3u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      v8);
  DefaultTimeOut.QuadPart = -1200000000;
  v18 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = FileW;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
  IoStatusBlock = 0;
  NamedPipeFileHandle = (void *)-1LL;
  v9 = NtCreateNamedPipeFile(
         &NamedPipeFileHandle,
         0x80100100,
         &ObjectAttributes,
         &IoStatusBlock,
         3u,
         2u,
         32 * (v5 ^ 1),
         0,
         0,
         0,
         1u,
         0x1000u,
         0x1000u,
         &DefaultTimeOut);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = NamedPipeFileHandle;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = (void *)-1LL;
  v10 = NtOpenFile(&FileHandle, 0x40100080u, &ObjectAttributes, &IoStatusBlock, 3u, (32 * (v4 ^ 1)) | 0x40);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      (const char *)(unsigned int)v10,
      dwCreationDispositiona);
  *a1 = NamedPipeFileHandle;
  NamedPipeFileHandle = (void *)-1LL;
  a1[1] = FileHandle;
  FileHandle = (void *)-1LL;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return a1;
}

```

## disassembly

```asm
0x1400bf84c  push    rbp
0x1400bf84e  push    rbx
0x1400bf84f  push    rsi
0x1400bf850  push    rdi
0x1400bf851  push    r12
0x1400bf853  push    r14
0x1400bf855  lea     rbp, [rsp-2Fh]
0x1400bf85a  sub     rsp, 0F8h
0x1400bf861  mov     rax, cs:__security_cookie
0x1400bf868  xor     rax, rsp
0x1400bf86b  mov     [rbp+57h+var_38], rax
0x1400bf86f  movzx   r14d, r9b
0x1400bf873  movzx   esi, r8b
0x1400bf877  mov     rdi, rcx
0x1400bf87a  mov     qword ptr [rbp+57h+var_60], rcx
0x1400bf87e  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x1400bf887  mov     [rsp+120h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400bf88f  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x1400bf897  xor     r9d, r9d; lpSecurityAttributes
0x1400bf89a  mov     edx, 80000000h; dwDesiredAccess
0x1400bf89f  lea     r8d, [r9+3]; dwShareMode
0x1400bf8a3  lea     rcx, FileName; "\\\\.\\pipe\\"
0x1400bf8aa  call    cs:__imp_CreateFileW
0x1400bf8b0  mov     rbx, rax
0x1400bf8b3  mov     [rbp+57h+var_A8], rax
0x1400bf8b7  inc     rax
0x1400bf8ba  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400bf8c0  setz    al
0x1400bf8c3  mov     rcx, [rbp+5Fh]; this
0x1400bf8c7  test    al, al
0x1400bf8c9  jnz     loc_1400BFA3F
0x1400bf8cf  mov     qword ptr [rbp+57h+var_60], 0FFFFFFFFB8797400h
0x1400bf8d7  xorps   xmm0, xmm0
0x1400bf8da  movups  [rbp+57h+var_58], xmm0
0x1400bf8de  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bf8e6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x1400bf8ee  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400bf8f2  lea     rax, [rbp+57h+var_58]
0x1400bf8f6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400bf8fa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bf8ff  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400bf903  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400bf907  mov     [rbp+57h+NamedPipeFileHandle], r12
0x1400bf90b  mov     eax, esi
0x1400bf90d  xor     eax, 1
0x1400bf910  shl     eax, 5
0x1400bf913  lea     rcx, [rbp+57h+var_60]
0x1400bf917  mov     [rsp+120h+DefaultTimeOut], rcx; DefaultTimeOut
0x1400bf91c  mov     ecx, 1000h
0x1400bf921  mov     [rsp+120h+OutBufferSize], ecx; OutBufferSize
0x1400bf925  mov     [rsp+120h+InBufferSize], ecx; InBufferSize
0x1400bf929  mov     [rsp+120h+MaxInstances], 1; MaxInstances
0x1400bf931  mov     [rsp+120h+NonBlocking], 0; NonBlocking
0x1400bf939  mov     [rsp+120h+ReadModeMessage], 0; ReadModeMessage
0x1400bf941  mov     [rsp+120h+WriteModeMessage], 0; WriteModeMessage
0x1400bf949  mov     dword ptr [rsp+120h+hTemplateFile], eax; CreateOptions
0x1400bf94d  mov     [rsp+120h+dwFlagsAndAttributes], 2; CreateDisposition
0x1400bf955  mov     [rsp+120h+dwCreationDisposition], 3; int
0x1400bf95d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400bf961  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bf965  mov     edx, 80100100h; DesiredAccess
0x1400bf96a  lea     rcx, [rbp+57h+NamedPipeFileHandle]; NamedPipeFileHandle
0x1400bf96e  call    cs:__imp_NtCreateNamedPipeFile
0x1400bf974  mov     rcx, [rbp+5Fh]; this
0x1400bf978  test    eax, eax
0x1400bf97a  js      loc_1400BFA51
0x1400bf980  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bf987  mov     rax, [rbp+57h+NamedPipeFileHandle]
0x1400bf98b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400bf98f  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1400bf996  lea     rax, [rbp+57h+var_58]
0x1400bf99a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400bf99e  xorps   xmm0, xmm0
0x1400bf9a1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bf9a6  mov     [rbp+57h+FileHandle], r12
0x1400bf9aa  mov     eax, r14d
0x1400bf9ad  xor     eax, 1
0x1400bf9b0  shl     eax, 5
0x1400bf9b3  or      eax, 40h
0x1400bf9b6  mov     [rsp+120h+dwFlagsAndAttributes], eax; OpenOptions
0x1400bf9ba  mov     [rsp+120h+dwCreationDisposition], 3; int
0x1400bf9c2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400bf9c6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bf9ca  mov     edx, 40100080h; DesiredAccess
0x1400bf9cf  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400bf9d3  call    cs:__imp_NtOpenFile
0x1400bf9d9  mov     rcx, [rbp+5Fh]; this
0x1400bf9dd  test    eax, eax
0x1400bf9df  js      short loc_1400BFA2A
0x1400bf9e1  mov     rax, [rbp+57h+NamedPipeFileHandle]
0x1400bf9e5  mov     [rdi], rax
0x1400bf9e8  mov     [rbp+57h+NamedPipeFileHandle], r12
0x1400bf9ec  mov     rcx, [rbp+57h+FileHandle]
0x1400bf9f0  mov     [rdi+8], rcx
0x1400bf9f4  mov     [rbp+57h+FileHandle], r12
0x1400bf9f8  lea     rcx, [rbx-1]
0x1400bf9fc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400bfa00  ja      short loc_1400BFA0B
0x1400bfa02  mov     rcx, rbx; hObject
0x1400bfa05  call    cs:__imp_CloseHandle
0x1400bfa0b  mov     rax, rdi
0x1400bfa0e  mov     rcx, [rbp+57h+var_38]
0x1400bfa12  xor     rcx, rsp; StackCookie
0x1400bfa15  call    __security_check_cookie
0x1400bfa1a  add     rsp, 0F8h
0x1400bfa21  pop     r14
0x1400bfa23  pop     r12
0x1400bfa25  pop     rdi
0x1400bfa26  pop     rsi
0x1400bfa27  pop     rbx
0x1400bfa28  pop     rbp
0x1400bfa29  retn
0x1400bfa2a  mov     r9d, eax; char *
0x1400bfa2d  lea     r8, aOnecoreVmCompu_35; "onecore\\vm\\compute\\common\\compute\\"...
0x1400bfa34  mov     edx, 68h ; 'h'; void *
0x1400bfa39  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400bfa3f  lea     r8, aOnecoreVmCompu_35; "onecore\\vm\\compute\\common\\compute\\"...
0x1400bfa46  mov     edx, 3Fh ; '?'; void *
0x1400bfa4b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bfa51  mov     r9d, eax; char *
0x1400bfa54  lea     r8, aOnecoreVmCompu_35; "onecore\\vm\\compute\\common\\compute\\"...
0x1400bfa5b  mov     edx, 59h ; 'Y'; void *
0x1400bfa60  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
