# ExpandVolume(void *,ushort const *)

- ea: `0x140040bc4`
- end: `0x140040e1b`
- name: `?ExpandVolume@@YA_NPEAXPEBG@Z`
- size: `599`
- prototype: `bool __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14004218c`

## callees

- `0x140005360`
- `0x140008760`
- `0x14001e4f4`
- `0x140040878`
- `0x140040bc4`
- `0x1400415c0`
- `0x14004161c`
- `0x140041688`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x140040d1b`
- `ntdll!NtQueryVolumeInformationFile` at `0x140040d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040de0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140040c96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140040c96`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140040da8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140040da8`

## string_xrefs

- `0x140040cd4`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040d32`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040dbf`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+1Fh] BYREF
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
    (bool)"%ls",
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
      (__int64)"%ls",
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
0x140040bc4  mov     [rsp-8+arg_10], rbx
0x140040bc9  mov     [rsp-8+arg_18], rsi
0x140040bce  push    rbp
0x140040bcf  push    rdi
0x140040bd0  push    r13
0x140040bd2  push    r14
0x140040bd4  push    r15
0x140040bd6  lea     rbp, [rsp-37h]
0x140040bdb  sub     rsp, 0B0h
0x140040be2  mov     rax, cs:__security_cookie
0x140040be9  xor     rax, rsp
0x140040bec  mov     [rbp+57h+var_28], rax
0x140040bf0  mov     rbx, rdx
0x140040bf3  xor     r15d, r15d
0x140040bf6  mov     sil, r15b
0x140040bf9  call    ?ExpandPartition@@YA_JPEAX@Z; ExpandPartition(void *)
0x140040bfe  mov     r14, rax
0x140040c01  xorps   xmm0, xmm0
0x140040c04  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x140040c08  mov     [rbp+57h+var_78], r15
0x140040c0c  mov     [rbp+57h+var_70], r15
0x140040c10  or      r8, 0FFFFFFFFFFFFFFFFh
0x140040c14  inc     r8
0x140040c17  cmp     [rbx+r8*2], r15w
0x140040c1c  jnz     short loc_140040C14
0x140040c1e  mov     rdx, rbx
0x140040c21  lea     rcx, [rbp+57h+lpFileName]
0x140040c25  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140040c2a  nop
0x140040c2b  mov     r8, [rbp+57h+var_70]
0x140040c2f  mov     r9, [rbp+57h+lpFileName]
0x140040c33  mov     rdx, [rbp+57h+var_78]
0x140040c37  test    rdx, rdx
0x140040c3a  jz      short loc_140040C6A
0x140040c3c  lea     rax, [rbp+57h+lpFileName]
0x140040c40  cmp     r8, 7
0x140040c44  cmova   rax, r9
0x140040c48  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x140040c4e  jnz     short loc_140040C6A
0x140040c50  dec     rdx
0x140040c53  mov     [rbp+57h+var_78], rdx
0x140040c57  lea     rcx, [rbp+57h+lpFileName]
0x140040c5b  cmp     r8, 7
0x140040c5f  cmova   rcx, r9
0x140040c63  mov     [rcx+rdx*2], r15w
0x140040c68  jmp     short loc_140040C2B
0x140040c6a  lea     rcx, [rbp+57h+lpFileName]
0x140040c6e  cmp     r8, 7
0x140040c72  cmova   rcx, r9; lpFileName
0x140040c76  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x140040c7b  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140040c83  mov     r8d, 3; dwShareMode
0x140040c89  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x140040c8e  xor     r9d, r9d; lpSecurityAttributes
0x140040c91  mov     edx, 0C0000000h; dwDesiredAccess
0x140040c96  call    cs:__imp_CreateFileW
0x140040c9c  mov     rbx, rax
0x140040c9f  mov     [rbp+57h+var_90], rax
0x140040ca3  lea     rdx, [rbp+57h+lpFileName]
0x140040ca7  cmp     [rbp+57h+var_70], 7
0x140040cac  cmova   rdx, [rbp+57h+lpFileName]
0x140040cb1  dec     rax
0x140040cb4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140040cb8  setnbe  al
0x140040cbb  mov     rcx, [rbp+5Fh]; this
0x140040cbf  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdx; char *
0x140040cc4  lea     r13, aLs; "%ls"
0x140040ccb  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; bool
0x140040cd0  movzx   r9d, al; char *
0x140040cd4  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040cdb  mov     edx, 33Eh; void *
0x140040ce0  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140040ce5  xorps   xmm0, xmm0
0x140040ce8  movups  [rbp+57h+FsInformation], xmm0
0x140040cec  movups  [rbp+57h+var_48], xmm0
0x140040cf0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140040cf4  lea     rdi, [rbp+57h+lpFileName]
0x140040cf8  cmp     [rbp+57h+var_70], 7
0x140040cfd  cmova   rdi, [rbp+57h+lpFileName]
0x140040d02  mov     [rsp+0D0h+dwCreationDisposition], 7; FsInformationClass
0x140040d0a  mov     r9d, 20h ; ' '; Length
0x140040d10  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x140040d14  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140040d18  mov     rcx, rbx; FileHandle
0x140040d1b  call    cs:__imp_NtQueryVolumeInformationFile
0x140040d21  mov     rcx, [rbp+5Fh]; this
0x140040d25  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x140040d2a  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; int
0x140040d2f  mov     r9d, eax; char *
0x140040d32  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040d39  mov     edx, 347h; void *
0x140040d3e  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140040d43  mov     ecx, dword ptr [rbp+57h+var_48+8]
0x140040d46  imul    ecx, dword ptr [rbp+57h+var_48+0Ch]
0x140040d4a  mov     rax, r14
0x140040d4d  cqo
0x140040d4f  idiv    rcx
0x140040d52  mov     rcx, rax
0x140040d55  mov     rax, qword ptr [rbp+57h+FsInformation]
0x140040d59  inc     rax
0x140040d5c  cmp     rax, rcx
0x140040d5f  jge     short loc_140040DD3
0x140040d61  mov     eax, dword ptr [rbp+57h+var_48+8]
0x140040d64  imul    rax, rcx
0x140040d68  mov     [rbp+57h+InBuffer], rax
0x140040d6c  mov     [rbp+57h+BytesReturned], r15d
0x140040d70  lea     rdi, [rbp+57h+lpFileName]
0x140040d74  cmp     [rbp+57h+var_70], 7
0x140040d79  cmova   rdi, [rbp+57h+lpFileName]
0x140040d7e  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x140040d83  lea     rax, [rbp+57h+BytesReturned]
0x140040d87  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x140040d8c  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x140040d91  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOutBuffer
0x140040d96  mov     r9d, 8; nInBufferSize
0x140040d9c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x140040da0  mov     edx, 900F0h; dwIoControlCode
0x140040da5  mov     rcx, rbx; hDevice
0x140040da8  call    cs:__imp_DeviceIoControl
0x140040dae  mov     rcx, [rbp+5Fh]; this
0x140040db2  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x140040db7  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; __int64
0x140040dbc  mov     r9d, eax; char *
0x140040dbf  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040dc6  mov     edx, 360h; void *
0x140040dcb  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x140040dd0  mov     sil, 1
0x140040dd3  lea     rcx, [rbx-1]
0x140040dd7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140040ddb  ja      short loc_140040DE7
0x140040ddd  mov     rcx, rbx; hObject
0x140040de0  call    cs:__imp_CloseHandle
0x140040de6  nop
0x140040de7  lea     rcx, [rbp+57h+lpFileName]; void *
0x140040deb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040df0  mov     al, sil
0x140040df3  mov     rcx, [rbp+57h+var_28]
0x140040df7  xor     rcx, rsp; StackCookie
0x140040dfa  call    __security_check_cookie
0x140040dff  lea     r11, [rsp+0D0h+var_20]
0x140040e07  mov     rbx, [r11+40h]
0x140040e0b  mov     rsi, [r11+48h]
0x140040e0f  mov     rsp, r11
0x140040e12  pop     r15
0x140040e14  pop     r14
0x140040e16  pop     r13
0x140040e18  pop     rdi
0x140040e19  pop     rbp
0x140040e1a  retn
```
