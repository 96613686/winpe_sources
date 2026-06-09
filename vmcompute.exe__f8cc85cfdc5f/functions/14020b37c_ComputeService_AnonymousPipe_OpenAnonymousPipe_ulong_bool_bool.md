# ComputeService::AnonymousPipe::OpenAnonymousPipe(ulong,bool,bool)

- ea: `0x14020b37c`
- end: `0x14020b5cd`
- name: `?OpenAnonymousPipe@AnonymousPipe@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V12@@std@@K_N0@Z`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14020b114`

## callees

- `0x140024030`
- `0x140024f6c`
- `0x140080180`
- `0x1401332f0`
- `0x140142dac`
- `0x14020b37c`

## import_xrefs

- `ntdll!NtCreateNamedPipeFile` at `0x14020b4c2`
- `ntdll!NtCreateNamedPipeFile` at `0x14020b4c2`
- `ntdll!NtOpenFile` at `0x14020b548`
- `ntdll!NtOpenFile` at `0x14020b548`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14020b3df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14020b3df`

## string_xrefs

- `0x14020b405`: `onecore\vm\compute\common\compute\AnonymousPipe.h`
- `0x14020b4d9`: `onecore\vm\compute\common\compute\AnonymousPipe.h`
- `0x14020b55f`: `onecore\vm\compute\common\compute\AnonymousPipe.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall ComputeService::AnonymousPipe::OpenAnonymousPipe(
        void **a1,
        __int64 a2,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  int v4; // edi
  int v5; // esi
  HANDLE FileW; // rax
  const char *v8; // r9
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-89h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-89h]
  HANDLE v14[2]; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  void *NamedPipeFileHandle; // [rsp+B0h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+Fh] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+C0h] [rbp+17h] BYREF
  __int128 v19; // [rsp+C8h] [rbp+1Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = a4;
  v5 = a3;
  FileW = CreateFileW(L"\\\\.\\pipe\\", 0x80000000, 3u, 0, 3u, 0, 0);
  v14[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      v8);
  DefaultTimeOut.QuadPart = -1200000000;
  v19 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = FileW;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  IoStatusBlock = 0;
  NamedPipeFileHandle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &NamedPipeFileHandle,
    -1);
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
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = NamedPipeFileHandle;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &FileHandle,
    -1);
  v10 = NtOpenFile(&FileHandle, 0x40100080u, &ObjectAttributes, &IoStatusBlock, 3u, (32 * (v4 ^ 1)) | 0x40);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\AnonymousPipe.h",
      (const char *)(unsigned int)v10,
      dwCreationDispositiona);
  *a1 = NamedPipeFileHandle;
  NamedPipeFileHandle = (void *)-1LL;
  a1[1] = FileHandle;
  FileHandle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NamedPipeFileHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v14);
  return a1;
}

```

## disassembly

```asm
0x14020b37c  mov     [rsp-8+arg_8], rbx
0x14020b381  mov     [rsp-8+arg_10], rsi
0x14020b386  push    rbp
0x14020b387  push    rdi
0x14020b388  push    r15
0x14020b38a  lea     rbp, [rsp-47h]
0x14020b38f  sub     rsp, 0F0h
0x14020b396  mov     rax, cs:__security_cookie
0x14020b39d  xor     rax, rsp
0x14020b3a0  mov     [rbp+57h+var_18], rax
0x14020b3a4  movzx   edi, r9b
0x14020b3a8  movzx   esi, r8b
0x14020b3ac  mov     rbx, rcx
0x14020b3af  mov     [rbp+57h+var_90], rcx
0x14020b3b3  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x14020b3bc  mov     [rsp+100h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14020b3c4  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x14020b3cc  xor     r9d, r9d; lpSecurityAttributes
0x14020b3cf  mov     edx, 80000000h; dwDesiredAccess
0x14020b3d4  lea     r8d, [r9+3]; dwShareMode
0x14020b3d8  lea     rcx, aPipe_0; "\\\\.\\pipe\\"
0x14020b3df  call    cs:__imp_CreateFileW
0x14020b3e6  nop     dword ptr [rax+rax+00h]
0x14020b3eb  mov     [rbp+57h+var_90], rax
0x14020b3ef  lea     rcx, [rax+1]
0x14020b3f3  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14020b3fa  setz    dl
0x14020b3fd  mov     rcx, [rbp+5Fh]; this
0x14020b401  test    dl, dl
0x14020b403  jz      short loc_14020B417
0x14020b405  lea     r8, aOnecoreVmCompu_81; "onecore\\vm\\compute\\common\\compute\\"...
0x14020b40c  mov     edx, 3Fh ; '?'; void *
0x14020b411  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14020b417  mov     qword ptr [rbp+57h+var_40], 0FFFFFFFFB8797400h
0x14020b41f  xorps   xmm0, xmm0
0x14020b422  movups  [rbp+57h+var_38], xmm0
0x14020b426  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14020b42e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x14020b436  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14020b43a  lea     rax, [rbp+57h+var_38]
0x14020b43e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14020b442  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14020b447  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14020b44b  or      r15, 0FFFFFFFFFFFFFFFFh
0x14020b44f  mov     [rbp+57h+NamedPipeFileHandle], r15
0x14020b453  mov     rdx, r15
0x14020b456  lea     rcx, [rbp+57h+NamedPipeFileHandle]
0x14020b45a  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14020b45f  mov     eax, esi
0x14020b461  xor     eax, 1
0x14020b464  shl     eax, 5
0x14020b467  lea     rcx, [rbp+57h+var_40]
0x14020b46b  mov     [rsp+100h+DefaultTimeOut], rcx; DefaultTimeOut
0x14020b470  mov     ecx, 1000h
0x14020b475  mov     [rsp+100h+OutBufferSize], ecx; OutBufferSize
0x14020b479  mov     [rsp+100h+InBufferSize], ecx; InBufferSize
0x14020b47d  mov     [rsp+100h+MaxInstances], 1; MaxInstances
0x14020b485  mov     [rsp+100h+NonBlocking], 0; NonBlocking
0x14020b48d  mov     [rsp+100h+ReadModeMessage], 0; ReadModeMessage
0x14020b495  mov     [rsp+100h+WriteModeMessage], 0; WriteModeMessage
0x14020b49d  mov     dword ptr [rsp+100h+hTemplateFile], eax; CreateOptions
0x14020b4a1  mov     [rsp+100h+dwFlagsAndAttributes], 2; CreateDisposition
0x14020b4a9  mov     [rsp+100h+dwCreationDisposition], 3; int
0x14020b4b1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14020b4b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14020b4b9  mov     edx, 80100100h; DesiredAccess
0x14020b4be  lea     rcx, [rbp+57h+NamedPipeFileHandle]; NamedPipeFileHandle
0x14020b4c2  call    cs:__imp_NtCreateNamedPipeFile
0x14020b4c9  nop     dword ptr [rax+rax+00h]
0x14020b4ce  mov     rcx, [rbp+5Fh]; this
0x14020b4d2  test    eax, eax
0x14020b4d4  jns     short loc_14020B4EA
0x14020b4d6  mov     r9d, eax; char *
0x14020b4d9  lea     r8, aOnecoreVmCompu_81; "onecore\\vm\\compute\\common\\compute\\"...
0x14020b4e0  lea     edx, [r15+5Ah]; void *
0x14020b4e4  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14020b4ea  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14020b4f1  mov     rax, [rbp+57h+NamedPipeFileHandle]
0x14020b4f5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14020b4f9  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x14020b500  lea     rax, [rbp+57h+var_38]
0x14020b504  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14020b508  xorps   xmm0, xmm0
0x14020b50b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14020b510  mov     [rbp+57h+FileHandle], r15
0x14020b514  mov     rdx, r15
0x14020b517  lea     rcx, [rbp+57h+FileHandle]
0x14020b51b  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14020b520  mov     eax, edi
0x14020b522  xor     eax, 1
0x14020b525  shl     eax, 5
0x14020b528  or      eax, 40h
0x14020b52b  mov     [rsp+100h+dwFlagsAndAttributes], eax; OpenOptions
0x14020b52f  mov     [rsp+100h+dwCreationDisposition], 3; int
0x14020b537  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14020b53b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14020b53f  mov     edx, 40100080h; DesiredAccess
0x14020b544  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14020b548  call    cs:__imp_NtOpenFile
0x14020b54f  nop     dword ptr [rax+rax+00h]
0x14020b554  mov     rcx, [rbp+5Fh]; this
0x14020b558  test    eax, eax
0x14020b55a  jns     short loc_14020B571
0x14020b55c  mov     r9d, eax; char *
0x14020b55f  lea     r8, aOnecoreVmCompu_81; "onecore\\vm\\compute\\common\\compute\\"...
0x14020b566  mov     edx, 68h ; 'h'; void *
0x14020b56b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14020b571  mov     rcx, [rbp+57h+NamedPipeFileHandle]
0x14020b575  mov     [rbx], rcx
0x14020b578  mov     [rbp+57h+NamedPipeFileHandle], r15
0x14020b57c  mov     rcx, [rbp+57h+FileHandle]
0x14020b580  mov     [rbx+8], rcx
0x14020b584  mov     [rbp+57h+FileHandle], r15
0x14020b588  lea     rcx, [rbp+57h+FileHandle]; void *
0x14020b58c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14020b591  nop
0x14020b592  lea     rcx, [rbp+57h+NamedPipeFileHandle]; void *
0x14020b596  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14020b59b  nop
0x14020b59c  lea     rcx, [rbp+57h+var_90]; void *
0x14020b5a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14020b5a5  mov     rax, rbx
0x14020b5a8  mov     rcx, [rbp+57h+var_18]
0x14020b5ac  xor     rcx, rsp; StackCookie
0x14020b5af  call    __security_check_cookie
0x14020b5b4  lea     r11, [rsp+100h+var_10]
0x14020b5bc  mov     rbx, [r11+28h]
0x14020b5c0  mov     rsi, [r11+30h]
0x14020b5c4  mov     rsp, r11
0x14020b5c7  pop     r15
0x14020b5c9  pop     rdi
0x14020b5ca  pop     rbp
0x14020b5cb  retn
```
