# ExpandVolume(void *,ushort const *)

- ea: `0x18005fa48`
- end: `0x18005fcb8`
- name: `?ExpandVolume@@YA_NPEAXPEBG@Z`
- size: `624`
- prototype: `bool __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005c148`

## callees

- `0x180002f50`
- `0x180006660`
- `0x180014870`
- `0x180051ca8`
- `0x18005f6d8`
- `0x18005fa48`
- `0x180060864`
- `0x1800608c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fc76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fc76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005fb1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005fb1a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fc38`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fc38`
- `ntdll!NtQueryVolumeInformationFile` at `0x18005fba5`
- `ntdll!NtQueryVolumeInformationFile` at `0x18005fba5`

## string_xrefs

- `0x18005fb5e`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005fbc2`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005fc55`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ExpandVolume(void *a1, const unsigned __int16 *a2)
{
  char v3; // si
  __int64 v4; // r14
  unsigned __int64 v5; // r8
  LPCWSTR *v6; // rax
  __int64 v7; // rdx
  LPCWSTR *v8; // rcx
  const WCHAR *v9; // rcx
  char *FileW; // rax
  char *v11; // rbx
  LPCWSTR *v12; // rdx
  LPCWSTR *v13; // rdi
  unsigned int v14; // eax
  __int64 v15; // rcx
  LPCWSTR *v16; // rdi
  unsigned int v17; // eax
  __int64 v19; // [rsp+40h] [rbp-39h]
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v21; // [rsp+58h] [rbp-21h]
  unsigned __int64 v22; // [rsp+60h] [rbp-19h]
  DWORD BytesReturned; // [rsp+68h] [rbp-11h] BYREF
  __int64 InBuffer; // [rsp+70h] [rbp-9h] BYREF
  __int128 FsInformation; // [rsp+78h] [rbp-1h] BYREF
  __int128 v26; // [rsp+88h] [rbp+Fh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = 0;
  v4 = ExpandPartition(a1);
  *(_OWORD *)lpFileName = 0;
  v21 = 0;
  v22 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)lpFileName, a2, v5);
  while ( v21 )
  {
    v6 = lpFileName;
    if ( v22 > 7 )
      v6 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v6 + v21 - 1) != 92 )
      break;
    v7 = --v21;
    v8 = lpFileName;
    if ( v22 > 7 )
      v8 = (LPCWSTR *)lpFileName[0];
    *((_WORD *)v8 + v7) = 0;
  }
  v9 = (const WCHAR *)lpFileName;
  if ( v22 > 7 )
    v9 = lpFileName[0];
  FileW = (char *)CreateFileW(v9, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
  v11 = FileW;
  HIWORD(v19) = HIWORD(FileW);
  v12 = lpFileName;
  if ( v22 > 7 )
    v12 = (LPCWSTR *)lpFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x33E,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (void *)"%ls",
    (const char *)v12);
  FsInformation = 0;
  v26 = 0;
  IoStatusBlock = 0;
  v13 = lpFileName;
  if ( v22 > 7 )
    v13 = (LPCWSTR *)lpFileName[0];
  v14 = NtQueryVolumeInformationFile(v11, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x347,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)v14,
    (int)"%ls",
    (const char *)v13);
  v15 = v4 / (unsigned int)(HIDWORD(v26) * DWORD2(v26));
  if ( (__int64)FsInformation + 1 < v15 )
  {
    InBuffer = v15 * DWORD2(v26);
    BytesReturned = 0;
    v16 = lpFileName;
    if ( v22 > 7 )
      v16 = (LPCWSTR *)lpFileName[0];
    v17 = DeviceIoControl(v11, 0x900F0u, &InBuffer, 8u, 0, 0, &BytesReturned, 0);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)v17,
      (void *)"%ls",
      (const char *)v16);
    v3 = 1;
  }
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  std::wstring::~wstring(lpFileName);
  return v3;
}

```

## disassembly

```asm
0x18005fa48  mov     [rsp-8+arg_10], rbx
0x18005fa4d  mov     [rsp-8+arg_18], rsi
0x18005fa52  push    rbp
0x18005fa53  push    rdi
0x18005fa54  push    r13
0x18005fa56  push    r14
0x18005fa58  push    r15
0x18005fa5a  lea     rbp, [rsp-37h]
0x18005fa5f  sub     rsp, 0B0h
0x18005fa66  mov     rax, cs:__security_cookie
0x18005fa6d  xor     rax, rsp
0x18005fa70  mov     [rbp+57h+var_28], rax
0x18005fa74  mov     rbx, rdx
0x18005fa77  xor     r15d, r15d
0x18005fa7a  mov     sil, r15b
0x18005fa7d  call    ?ExpandPartition@@YA_JPEAX@Z; ExpandPartition(void *)
0x18005fa82  mov     r14, rax
0x18005fa85  xorps   xmm0, xmm0
0x18005fa88  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18005fa8c  mov     [rbp+57h+var_78], r15
0x18005fa90  mov     [rbp+57h+var_70], r15
0x18005fa94  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005fa98  inc     r8
0x18005fa9b  cmp     [rbx+r8*2], r15w
0x18005faa0  jnz     short loc_18005FA98
0x18005faa2  mov     rdx, rbx
0x18005faa5  lea     rcx, [rbp+57h+lpFileName]
0x18005faa9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005faae  nop
0x18005faaf  mov     r8, [rbp+57h+var_70]
0x18005fab3  mov     r9, [rbp+57h+lpFileName]
0x18005fab7  mov     rdx, [rbp+57h+var_78]
0x18005fabb  test    rdx, rdx
0x18005fabe  jz      short loc_18005FAEE
0x18005fac0  lea     rax, [rbp+57h+lpFileName]
0x18005fac4  cmp     r8, 7
0x18005fac8  cmova   rax, r9
0x18005facc  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18005fad2  jnz     short loc_18005FAEE
0x18005fad4  dec     rdx
0x18005fad7  mov     [rbp+57h+var_78], rdx
0x18005fadb  lea     rcx, [rbp+57h+lpFileName]
0x18005fadf  cmp     r8, 7
0x18005fae3  cmova   rcx, r9
0x18005fae7  mov     [rcx+rdx*2], r15w
0x18005faec  jmp     short loc_18005FAAF
0x18005faee  lea     rcx, [rbp+57h+lpFileName]
0x18005faf2  cmp     r8, 7
0x18005faf6  cmova   rcx, r9; lpFileName
0x18005fafa  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x18005faff  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18005fb07  mov     r8d, 3; dwShareMode
0x18005fb0d  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005fb12  xor     r9d, r9d; lpSecurityAttributes
0x18005fb15  mov     edx, 0C0000000h; dwDesiredAccess
0x18005fb1a  call    cs:__imp_CreateFileW
0x18005fb21  nop     dword ptr [rax+rax+00h]
0x18005fb26  mov     rbx, rax
0x18005fb29  mov     [rbp+57h+var_90], rax
0x18005fb2d  lea     rdx, [rbp+57h+lpFileName]
0x18005fb31  cmp     [rbp+57h+var_70], 7
0x18005fb36  cmova   rdx, [rbp+57h+lpFileName]
0x18005fb3b  dec     rax
0x18005fb3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005fb42  setnbe  al
0x18005fb45  mov     rcx, [rbp+5Fh]; this
0x18005fb49  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdx; char *
0x18005fb4e  lea     r13, aLs; "%ls"
0x18005fb55  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; void *
0x18005fb5a  movzx   r9d, al; char *
0x18005fb5e  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fb65  mov     edx, 33Eh; void *
0x18005fb6a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005fb6f  xorps   xmm0, xmm0
0x18005fb72  movups  [rbp+57h+FsInformation], xmm0
0x18005fb76  movups  [rbp+57h+var_48], xmm0
0x18005fb7a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005fb7e  lea     rdi, [rbp+57h+lpFileName]
0x18005fb82  cmp     [rbp+57h+var_70], 7
0x18005fb87  cmova   rdi, [rbp+57h+lpFileName]
0x18005fb8c  mov     [rsp+0D0h+dwCreationDisposition], 7; FsInformationClass
0x18005fb94  mov     r9d, 20h ; ' '; Length
0x18005fb9a  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x18005fb9e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005fba2  mov     rcx, rbx; FileHandle
0x18005fba5  call    cs:__imp_NtQueryVolumeInformationFile
0x18005fbac  nop     dword ptr [rax+rax+00h]
0x18005fbb1  mov     rcx, [rbp+5Fh]; this
0x18005fbb5  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x18005fbba  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; int
0x18005fbbf  mov     r9d, eax; char *
0x18005fbc2  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fbc9  mov     edx, 347h; void *
0x18005fbce  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005fbd3  mov     ecx, dword ptr [rbp+57h+var_48+8]
0x18005fbd6  imul    ecx, dword ptr [rbp+57h+var_48+0Ch]
0x18005fbda  mov     rax, r14
0x18005fbdd  cqo
0x18005fbdf  idiv    rcx
0x18005fbe2  mov     rcx, rax
0x18005fbe5  mov     rax, qword ptr [rbp+57h+FsInformation]
0x18005fbe9  inc     rax
0x18005fbec  cmp     rax, rcx
0x18005fbef  jge     short loc_18005FC69
0x18005fbf1  mov     eax, dword ptr [rbp+57h+var_48+8]
0x18005fbf4  imul    rax, rcx
0x18005fbf8  mov     [rbp+57h+InBuffer], rax
0x18005fbfc  mov     [rbp+57h+BytesReturned], r15d
0x18005fc00  lea     rdi, [rbp+57h+lpFileName]
0x18005fc04  cmp     [rbp+57h+var_70], 7
0x18005fc09  cmova   rdi, [rbp+57h+lpFileName]
0x18005fc0e  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x18005fc13  lea     rax, [rbp+57h+BytesReturned]
0x18005fc17  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x18005fc1c  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18005fc21  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOutBuffer
0x18005fc26  mov     r9d, 8; nInBufferSize
0x18005fc2c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18005fc30  mov     edx, 900F0h; dwIoControlCode
0x18005fc35  mov     rcx, rbx; hDevice
0x18005fc38  call    cs:__imp_DeviceIoControl
0x18005fc3f  nop     dword ptr [rax+rax+00h]
0x18005fc44  mov     rcx, [rbp+5Fh]; this
0x18005fc48  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x18005fc4d  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; void *
0x18005fc52  mov     r9d, eax; char *
0x18005fc55  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fc5c  mov     edx, 360h; void *
0x18005fc61  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18005fc66  mov     sil, 1
0x18005fc69  lea     rcx, [rbx-1]
0x18005fc6d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005fc71  ja      short loc_18005FC83
0x18005fc73  mov     rcx, rbx; hObject
0x18005fc76  call    cs:__imp_CloseHandle
0x18005fc7d  nop     dword ptr [rax+rax+00h]
0x18005fc82  nop
0x18005fc83  lea     rcx, [rbp+57h+lpFileName]
0x18005fc87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005fc8c  mov     al, sil
0x18005fc8f  mov     rcx, [rbp+57h+var_28]
0x18005fc93  xor     rcx, rsp; StackCookie
0x18005fc96  call    __security_check_cookie
0x18005fc9b  lea     r11, [rsp+0D0h+var_20]
0x18005fca3  mov     rbx, [r11+40h]
0x18005fca7  mov     rsi, [r11+48h]
0x18005fcab  mov     rsp, r11
0x18005fcae  pop     r15
0x18005fcb0  pop     r14
0x18005fcb2  pop     r13
0x18005fcb4  pop     rdi
0x18005fcb5  pop     rbp
0x18005fcb6  retn
```
