# EnableUSN(ushort const *)

- ea: `0x180057898`
- end: `0x180057afb`
- name: `?EnableUSN@@YAXPEBG@Z`
- size: `611`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18005a8c8`

## callees

- `0x180002f50`
- `0x1800035c0`
- `0x18000d0ec`
- `0x180022d10`
- `0x180057898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057a60`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800578d2`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800578d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057969`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057969`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800579e2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180057a3c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800579e2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180057a3c`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x1800578fd`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x1800578fd`

## string_xrefs

- `0x180057a91`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057aa3`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057ab5`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057ac7`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057ae9`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EnableUSN(const unsigned __int16 *a1)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  unsigned __int64 v4; // rcx
  char *FileW; // rbx
  const char *v6; // r9
  DWORD LastError; // eax
  const char *v8; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  __int128 InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD OutBuffer[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+90h] [rbp-70h]
  WCHAR szVolumeName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  if ( !GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v1);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v2);
  if ( szVolumeName[0] )
  {
    v3 = -1;
    do
      ++v3;
    while ( szVolumeName[v3] );
    v4 = 2 * v3 - 2;
    if ( v4 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v4) = 0;
  }
  FileW = (char *)CreateFileW(szVolumeName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v6);
  BytesReturned = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  v13 = 0;
  if ( !DeviceIoControl(FileW, 0x900F4u, 0, 0, OutBuffer, 0x38u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 1179 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)LastError,
        dwCreationDisposition);
    InBuffer = 0;
    if ( !DeviceIoControl(FileW, 0x900E7u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        v8);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
}

```

## disassembly

```asm
0x180057898  mov     [rsp-8+arg_8], rbx
0x18005789d  mov     [rsp-8+arg_10], rdi
0x1800578a2  push    rbp
0x1800578a3  lea     rbp, [rsp-3D0h]
0x1800578ab  sub     rsp, 4D0h
0x1800578b2  mov     rax, cs:__security_cookie
0x1800578b9  xor     rax, rsp
0x1800578bc  mov     [rbp+3D0h+var_10], rax
0x1800578c3  mov     ebx, 104h
0x1800578c8  mov     r8d, ebx; cchBufferLength
0x1800578cb  lea     rdx, [rbp+3D0h+szVolumePathName]; lpszVolumePathName
0x1800578d2  call    cs:__imp_GetVolumePathNameW
0x1800578d9  nop     dword ptr [rax+rax+00h]
0x1800578de  mov     rcx, [rbp+3D8h]; this
0x1800578e5  xor     edi, edi
0x1800578e7  test    eax, eax
0x1800578e9  jz      loc_180057AA3
0x1800578ef  mov     r8d, ebx; cchBufferLength
0x1800578f2  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x1800578f6  lea     rcx, [rbp+3D0h+szVolumePathName]; lpszVolumeMountPoint
0x1800578fd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180057904  nop     dword ptr [rax+rax+00h]
0x180057909  mov     rcx, [rbp+3D8h]; this
0x180057910  test    eax, eax
0x180057912  jz      loc_180057AB5
0x180057918  cmp     [rbp+3D0h+szVolumeName], di
0x18005791c  jz      short loc_180057949
0x18005791e  lea     rcx, [rbp+3D0h+szVolumeName]
0x180057922  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057926  inc     rax
0x180057929  cmp     [rcx+rax*2], di
0x18005792d  jnz     short loc_180057926
0x18005792f  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180057937  cmp     rcx, 208h
0x18005793e  jnb     loc_180057AD9
0x180057944  mov     [rbp+rcx+3D0h+szVolumeName], di
0x180057949  mov     [rsp+4D0h+hTemplateFile], rdi; hTemplateFile
0x18005794e  mov     [rsp+4D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180057952  mov     r8d, 3; dwShareMode
0x180057958  mov     [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005795d  xor     r9d, r9d; lpSecurityAttributes
0x180057960  mov     edx, 0C0000000h; dwDesiredAccess
0x180057965  lea     rcx, [rbp+3D0h+szVolumeName]; lpFileName
0x180057969  call    cs:__imp_CreateFileW
0x180057970  nop     dword ptr [rax+rax+00h]
0x180057975  mov     rbx, rax
0x180057978  mov     [rsp+4D0h+var_490], rax
0x18005797d  inc     rax
0x180057980  test    rax, 0FFFFFFFFFFFFFFFEh
0x180057986  setz    al
0x180057989  mov     rcx, [rbp+3D8h]; this
0x180057990  test    al, al
0x180057992  jnz     loc_180057AC7
0x180057998  mov     [rsp+4D0h+BytesReturned], edi
0x18005799c  xorps   xmm0, xmm0
0x18005799f  xor     eax, eax
0x1800579a1  movups  [rsp+4D0h+OutBuffer], xmm0
0x1800579a6  movups  [rsp+4D0h+var_460], xmm0
0x1800579ab  movups  [rbp+3D0h+var_450], xmm0
0x1800579af  mov     [rbp+3D0h+var_440], rax
0x1800579b3  mov     [rsp+4D0h+lpOverlapped], rdi; lpOverlapped
0x1800579b8  lea     rax, [rsp+4D0h+BytesReturned]
0x1800579bd  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x1800579c2  mov     [rsp+4D0h+dwFlagsAndAttributes], 38h ; '8'; nOutBufferSize
0x1800579ca  lea     rax, [rsp+4D0h+OutBuffer]
0x1800579cf  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax; unsigned int
0x1800579d4  xor     r9d, r9d; nInBufferSize
0x1800579d7  xor     r8d, r8d; lpInBuffer
0x1800579da  mov     edx, 900F4h; dwIoControlCode
0x1800579df  mov     rcx, rbx; hDevice
0x1800579e2  call    cs:__imp_DeviceIoControl
0x1800579e9  nop     dword ptr [rax+rax+00h]
0x1800579ee  test    eax, eax
0x1800579f0  jnz     short loc_180057A53
0x1800579f2  call    cs:__imp_GetLastError
0x1800579f9  nop     dword ptr [rax+rax+00h]
0x1800579fe  cmp     eax, 49Bh
0x180057a03  jnz     loc_180057ADF
0x180057a09  xorps   xmm0, xmm0
0x180057a0c  movups  [rsp+4D0h+InBuffer], xmm0
0x180057a11  mov     [rsp+4D0h+lpOverlapped], rdi; lpOverlapped
0x180057a16  lea     rax, [rsp+4D0h+BytesReturned]
0x180057a1b  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x180057a20  mov     [rsp+4D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180057a24  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rdi; lpOutBuffer
0x180057a29  mov     r9d, 10h; nInBufferSize
0x180057a2f  lea     r8, [rsp+4D0h+InBuffer]; lpInBuffer
0x180057a34  mov     edx, 900E7h; dwIoControlCode
0x180057a39  mov     rcx, rbx; hDevice
0x180057a3c  call    cs:__imp_DeviceIoControl
0x180057a43  nop     dword ptr [rax+rax+00h]
0x180057a48  mov     rcx, [rbp+3D8h]; this
0x180057a4f  test    eax, eax
0x180057a51  jz      short loc_180057A91
0x180057a53  lea     rax, [rbx-1]
0x180057a57  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180057a5b  ja      short loc_180057A6C
0x180057a5d  mov     rcx, rbx; hObject
0x180057a60  call    cs:__imp_CloseHandle
0x180057a67  nop     dword ptr [rax+rax+00h]
0x180057a6c  mov     rcx, [rbp+3D0h+var_10]
0x180057a73  xor     rcx, rsp; StackCookie
0x180057a76  call    __security_check_cookie
0x180057a7b  lea     r11, [rsp+4D0h+var_s0]
0x180057a83  mov     rbx, [r11+18h]
0x180057a87  mov     rdi, [r11+20h]
0x180057a8b  mov     rsp, r11
0x180057a8e  pop     rbp
0x180057a8f  retn
0x180057a91  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057a98  mov     edx, 140h; void *
0x180057a9d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057aa3  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057aaa  mov     edx, 109h; void *
0x180057aaf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057ab5  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057abc  mov     edx, 10Ch; void *
0x180057ac1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057ac7  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057ace  mov     edx, 11Dh; void *
0x180057ad3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057ad9  call    __report_rangecheckfailure
0x180057adf  mov     rcx, [rbp+3D8h]; this
0x180057ae6  mov     r9d, eax; char *
0x180057ae9  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180057af0  mov     edx, 133h; void *
0x180057af5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
