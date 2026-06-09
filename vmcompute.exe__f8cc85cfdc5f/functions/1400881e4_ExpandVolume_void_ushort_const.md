# ExpandVolume(void *,ushort const *)

- ea: `0x1400881e4`
- end: `0x140088430`
- name: `?ExpandVolume@@YA_NPEAXPEBG@Z`
- size: `588`
- prototype: `bool __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140088438`

## callees

- `0x140017040`
- `0x14001d490`
- `0x140024030`
- `0x1400881e4`
- `0x14012309c`
- `0x140126054`
- `0x1401332f0`
- `0x140200fd0`
- `0x140233e00`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x140088320`
- `ntdll!NtQueryVolumeInformationFile` at `0x140088320`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140088295`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140088295`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400883c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400883c5`

## string_xrefs

- `0x1400882d9`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x14008833d`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1400883e2`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ExpandVolume(void *a1, const unsigned __int16 *a2)
{
  char v3; // si
  __int64 v4; // r14
  LPCWSTR *v5; // rax
  __int64 v6; // rdx
  LPCWSTR *v7; // rcx
  const WCHAR *v8; // rcx
  char *FileW; // rax
  void *v10; // rbx
  LPCWSTR *v11; // rdx
  LPCWSTR *v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // rcx
  LPCWSTR *v15; // rdi
  unsigned int v16; // eax
  char *v18; // [rsp+40h] [rbp-39h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v20; // [rsp+58h] [rbp-21h]
  unsigned __int64 v21; // [rsp+60h] [rbp-19h]
  DWORD BytesReturned; // [rsp+68h] [rbp-11h] BYREF
  __int64 InBuffer; // [rsp+70h] [rbp-9h] BYREF
  __int128 FsInformation; // [rsp+78h] [rbp-1h] BYREF
  __int128 v25; // [rsp+88h] [rbp+Fh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = 0;
  v4 = ExpandPartition(a1);
  std::wstring::wstring(lpFileName, a2);
  while ( v20 )
  {
    v5 = lpFileName;
    if ( v21 > 7 )
      v5 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v5 + v20 - 1) != 92 )
      break;
    v6 = --v20;
    v7 = lpFileName;
    if ( v21 > 7 )
      v7 = (LPCWSTR *)lpFileName[0];
    *((_WORD *)v7 + v6) = 0;
  }
  v8 = (const WCHAR *)lpFileName;
  if ( v21 > 7 )
    v8 = lpFileName[0];
  FileW = (char *)CreateFileW(v8, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
  v10 = FileW;
  v18 = FileW;
  v11 = lpFileName;
  if ( v21 > 7 )
    v11 = (LPCWSTR *)lpFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x33E,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"%ls",
    (const char *)v11);
  FsInformation = 0;
  v25 = 0;
  IoStatusBlock = 0;
  v12 = lpFileName;
  if ( v21 > 7 )
    v12 = (LPCWSTR *)lpFileName[0];
  v13 = NtQueryVolumeInformationFile(v10, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x347,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)v13,
    (int)"%ls",
    (const char *)v12);
  v14 = v4 / (unsigned int)(HIDWORD(v25) * DWORD2(v25));
  if ( (__int64)FsInformation + 1 < v14 )
  {
    InBuffer = v14 * DWORD2(v25);
    BytesReturned = 0;
    v15 = lpFileName;
    if ( v21 > 7 )
      v15 = (LPCWSTR *)lpFileName[0];
    v16 = DeviceIoControl(v10, 0x900F0u, &InBuffer, 8u, 0, 0, &BytesReturned, 0);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)v16,
      (int)"%ls",
      (const char *)v15);
    v3 = 1;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  return v3;
}

```

## disassembly

```asm
0x1400881e4  mov     [rsp-8+arg_10], rbx
0x1400881e9  push    rbp
0x1400881ea  push    rsi
0x1400881eb  push    rdi
0x1400881ec  push    r13
0x1400881ee  push    r14
0x1400881f0  lea     rbp, [rsp-37h]
0x1400881f5  sub     rsp, 0B0h
0x1400881fc  mov     rax, cs:__security_cookie
0x140088203  xor     rax, rsp
0x140088206  mov     [rbp+57h+var_28], rax
0x14008820a  mov     rbx, rdx
0x14008820d  xor     sil, sil
0x140088210  call    ?ExpandPartition@@YA_JPEAX@Z; ExpandPartition(void *)
0x140088215  mov     r14, rax
0x140088218  mov     rdx, rbx
0x14008821b  lea     rcx, [rbp+57h+lpFileName]
0x14008821f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140088224  nop
0x140088225  mov     r8, [rbp+57h+var_70]
0x140088229  mov     r9, [rbp+57h+lpFileName]
0x14008822d  mov     rdx, [rbp+57h+var_78]
0x140088231  test    rdx, rdx
0x140088234  jz      short loc_140088265
0x140088236  lea     rax, [rbp+57h+lpFileName]
0x14008823a  cmp     r8, 7
0x14008823e  cmova   rax, r9
0x140088242  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x140088248  jnz     short loc_140088265
0x14008824a  dec     rdx
0x14008824d  mov     [rbp+57h+var_78], rdx
0x140088251  lea     rcx, [rbp+57h+lpFileName]
0x140088255  cmp     r8, 7
0x140088259  cmova   rcx, r9
0x14008825d  xor     eax, eax
0x14008825f  mov     [rcx+rdx*2], ax
0x140088263  jmp     short loc_140088225
0x140088265  lea     rcx, [rbp+57h+lpFileName]
0x140088269  cmp     r8, 7
0x14008826d  cmova   rcx, r9; lpFileName
0x140088271  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x14008827a  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140088282  mov     r8d, 3; dwShareMode
0x140088288  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x14008828d  xor     r9d, r9d; lpSecurityAttributes
0x140088290  mov     edx, 0C0000000h; dwDesiredAccess
0x140088295  call    cs:__imp_CreateFileW
0x14008829c  nop     dword ptr [rax+rax+00h]
0x1400882a1  mov     rbx, rax
0x1400882a4  mov     [rbp+57h+var_90], rax
0x1400882a8  lea     rdx, [rbp+57h+lpFileName]
0x1400882ac  cmp     [rbp+57h+var_70], 7
0x1400882b1  cmova   rdx, [rbp+57h+lpFileName]
0x1400882b6  dec     rax
0x1400882b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400882bd  setnbe  al
0x1400882c0  mov     rcx, [rbp+5Fh]; this
0x1400882c4  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdx; char *
0x1400882c9  lea     r13, aLs; "%ls"
0x1400882d0  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; bool
0x1400882d5  movzx   r9d, al; char *
0x1400882d9  lea     r8, aOnecoreVmCompu_92; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400882e0  mov     edx, 33Eh; void *
0x1400882e5  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1400882ea  xorps   xmm0, xmm0
0x1400882ed  movups  [rbp+57h+FsInformation], xmm0
0x1400882f1  movups  [rbp+57h+var_48], xmm0
0x1400882f5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400882f9  lea     rdi, [rbp+57h+lpFileName]
0x1400882fd  cmp     [rbp+57h+var_70], 7
0x140088302  cmova   rdi, [rbp+57h+lpFileName]
0x140088307  mov     [rsp+0D0h+dwCreationDisposition], 7; FsInformationClass
0x14008830f  mov     r9d, 20h ; ' '; Length
0x140088315  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x140088319  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14008831d  mov     rcx, rbx; FileHandle
0x140088320  call    cs:__imp_NtQueryVolumeInformationFile
0x140088327  nop     dword ptr [rax+rax+00h]
0x14008832c  mov     rcx, [rbp+5Fh]; this
0x140088330  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x140088335  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; int
0x14008833a  mov     r9d, eax; char *
0x14008833d  lea     r8, aOnecoreVmCompu_92; "onecore\\vm\\compute\\shared\\storage\\"...
0x140088344  mov     edx, 347h; void *
0x140088349  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x14008834e  mov     ecx, dword ptr [rbp+57h+var_48+8]
0x140088351  imul    ecx, dword ptr [rbp+57h+var_48+0Ch]
0x140088355  mov     rax, r14
0x140088358  cqo
0x14008835a  idiv    rcx
0x14008835d  mov     rcx, rax
0x140088360  mov     rax, qword ptr [rbp+57h+FsInformation]
0x140088364  inc     rax
0x140088367  cmp     rax, rcx
0x14008836a  jge     loc_1400883F6
0x140088370  mov     eax, dword ptr [rbp+57h+var_48+8]
0x140088373  imul    rax, rcx
0x140088377  mov     [rbp+57h+InBuffer], rax
0x14008837b  mov     [rbp+57h+BytesReturned], 0
0x140088382  lea     rdi, [rbp+57h+lpFileName]
0x140088386  cmp     [rbp+57h+var_70], 7
0x14008838b  cmova   rdi, [rbp+57h+lpFileName]
0x140088390  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x140088399  lea     rax, [rbp+57h+BytesReturned]
0x14008839d  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x1400883a2  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1400883aa  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOutBuffer
0x1400883b3  mov     r9d, 8; nInBufferSize
0x1400883b9  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1400883bd  mov     edx, 900F0h; dwIoControlCode
0x1400883c2  mov     rcx, rbx; hDevice
0x1400883c5  call    cs:__imp_DeviceIoControl
0x1400883cc  nop     dword ptr [rax+rax+00h]
0x1400883d1  mov     rcx, [rbp+5Fh]; this
0x1400883d5  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x1400883da  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; int
0x1400883df  mov     r9d, eax; char *
0x1400883e2  lea     r8, aOnecoreVmCompu_92; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400883e9  mov     edx, 360h; void *
0x1400883ee  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1400883f3  mov     sil, 1
0x1400883f6  lea     rcx, [rbp+57h+var_90]; void *
0x1400883fa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400883ff  nop
0x140088400  lea     rcx, [rbp+57h+lpFileName]; this
0x140088404  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140088409  mov     al, sil
0x14008840c  mov     rcx, [rbp+57h+var_28]
0x140088410  xor     rcx, rsp; StackCookie
0x140088413  call    __security_check_cookie
0x140088418  mov     rbx, [rsp+0D0h+arg_10]
0x140088420  add     rsp, 0B0h
0x140088427  pop     r14
0x140088429  pop     r13
0x14008842b  pop     rdi
0x14008842c  pop     rsi
0x14008842d  pop     rbp
0x14008842e  retn
```
