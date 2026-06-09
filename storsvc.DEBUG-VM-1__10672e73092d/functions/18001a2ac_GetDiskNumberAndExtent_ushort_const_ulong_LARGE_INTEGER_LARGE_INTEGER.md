# GetDiskNumberAndExtent(ushort const *,ulong *,_LARGE_INTEGER *,_LARGE_INTEGER *)

- ea: `0x18001a2ac`
- end: `0x18001a4ff`
- name: `?GetDiskNumberAndExtent@@YAJPEBGPEAKPEAT_LARGE_INTEGER@@2@Z`
- size: `595`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, union _LARGE_INTEGER *, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18001a7c4`
- `0x180025420`
- `0x18002c080`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18000dd8c`
- `0x18000ddb0`
- `0x180012714`
- `0x180012734`
- `0x180019d4c`
- `0x18001a2ac`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a3e4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a459`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a3e4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a459`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001a2e3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001a2e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a377`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a377`

## string_xrefs

- `0x18001a2f7`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001a399`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001a3f5`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001a46a`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`
- `0x18001a4d6`: `onecore\drivers\storage\storsvc\service\storagehelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetDiskNumberAndExtent(
        const unsigned __int16 *a1,
        unsigned int *a2,
        union _LARGE_INTEGER *a3,
        union _LARGE_INTEGER *a4)
{
  const char *v6; // r9
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  HANDLE FileW; // rbx
  const char *v11; // r9
  unsigned int LastError; // ebx
  const char *v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  const char *v16; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Buf1[16]; // [rsp+54h] [rbp-ACh] BYREF
  int v22; // [rsp+64h] [rbp-9Ch]
  _BYTE OutBuffer[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v24; // [rsp+98h] [rbp-68h]
  LONGLONG v25; // [rsp+A0h] [rbp-60h]
  WCHAR szVolumeName[264]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  if ( !GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5CC,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
             v6);
  v8 = -1;
  do
    ++v8;
  while ( szVolumeName[v8] );
  v9 = 2 * v8 - 2;
  if ( v9 >= 0x208 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)szVolumeName + v9) = 0;
  FileW = CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v19 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5DA,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
                  v11);
LABEL_23:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    return LastError;
  }
  BytesReturned = 0;
  if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0xE0u, &BytesReturned, 0) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x5EA,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
            v13);
LABEL_10:
    LastError = v14;
    goto LABEL_23;
  }
  v15 = v24;
  if ( v24 == -1 )
  {
    memset_0(&v20, 0, 0x40u);
    if ( !DeviceIoControl(FileW, 0x240008u, 0, 0, &v20, 0x40u, &BytesReturned, 0) )
    {
      v14 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x5FA,
              (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
              v16);
      goto LABEL_10;
    }
    if ( v22 != 3 || memcmp_0(Buf1, RamdiskBootDiskGuid, 0x10u) )
    {
      LastError = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagehelper.cpp",
        (const char *)0x80070490LL,
        dwCreationDisposition);
      goto LABEL_23;
    }
    v15 = v24;
  }
  if ( a2 )
    *a2 = v15;
  if ( a4 )
    a4->QuadPart = v25;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return 0;
}

```

## disassembly

```asm
0x18001a2ac  push    rbp
0x18001a2ae  push    rbx
0x18001a2af  push    rsi
0x18001a2b0  push    rdi
0x18001a2b1  push    r15
0x18001a2b3  lea     rbp, [rsp-290h]
0x18001a2bb  sub     rsp, 390h
0x18001a2c2  mov     rax, cs:__security_cookie
0x18001a2c9  xor     rax, rsp
0x18001a2cc  mov     [rbp+2B0h+var_30], rax
0x18001a2d3  mov     rdi, r9
0x18001a2d6  mov     rsi, rdx
0x18001a2d9  mov     r8d, 104h; cchBufferLength
0x18001a2df  lea     rdx, [rbp+2B0h+szVolumeName]; lpszVolumeName
0x18001a2e3  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18001a2e9  xor     r15d, r15d
0x18001a2ec  test    eax, eax
0x18001a2ee  jnz     short loc_18001A325
0x18001a2f0  mov     rcx, [rbp+2B8h]; this
0x18001a2f7  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001a2fe  mov     edx, 5CCh; void *
0x18001a303  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a308  mov     rcx, [rbp+2B0h+var_30]
0x18001a30f  xor     rcx, rsp; StackCookie
0x18001a312  call    __security_check_cookie
0x18001a317  add     rsp, 390h
0x18001a31e  pop     r15
0x18001a320  pop     rdi
0x18001a321  pop     rsi
0x18001a322  pop     rbx
0x18001a323  pop     rbp
0x18001a324  retn
0x18001a325  lea     rcx, [rbp+2B0h+szVolumeName]
0x18001a329  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a32d  inc     rax
0x18001a330  cmp     [rcx+rax*2], r15w
0x18001a335  jnz     short loc_18001A32D
0x18001a337  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001a33f  cmp     rcx, 208h
0x18001a346  jnb     loc_18001A4F9
0x18001a34c  mov     [rbp+rcx+2B0h+szVolumeName], r15w
0x18001a352  mov     [rsp+3B0h+hTemplateFile], r15; hTemplateFile
0x18001a357  mov     [rsp+3B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001a35f  mov     [rsp+3B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a367  xor     r9d, r9d; lpSecurityAttributes
0x18001a36a  mov     edx, 80000000h; dwDesiredAccess
0x18001a36f  lea     r8d, [r9+3]; dwShareMode
0x18001a373  lea     rcx, [rbp+2B0h+szVolumeName]; lpFileName
0x18001a377  call    cs:__imp_CreateFileW
0x18001a37d  mov     rbx, rax
0x18001a380  mov     [rsp+3B0h+var_368], rax
0x18001a385  lea     rcx, [rax+1]
0x18001a389  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001a390  jnz     short loc_18001A3B1
0x18001a392  mov     rcx, [rbp+2B8h]; this
0x18001a399  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001a3a0  mov     edx, 5DAh; void *
0x18001a3a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a3aa  mov     ebx, eax
0x18001a3ac  jmp     loc_18001A4E8
0x18001a3b1  mov     [rsp+3B0h+BytesReturned], r15d
0x18001a3b6  mov     [rsp+3B0h+lpOverlapped], r15; lpOverlapped
0x18001a3bb  lea     rax, [rsp+3B0h+BytesReturned]
0x18001a3c0  mov     [rsp+3B0h+hTemplateFile], rax; lpBytesReturned
0x18001a3c5  mov     [rsp+3B0h+dwFlagsAndAttributes], 0E0h; nOutBufferSize
0x18001a3cd  lea     rax, [rbp+2B0h+OutBuffer]
0x18001a3d1  mov     qword ptr [rsp+3B0h+dwCreationDisposition], rax; lpOutBuffer
0x18001a3d6  xor     r9d, r9d; nInBufferSize
0x18001a3d9  xor     r8d, r8d; lpInBuffer
0x18001a3dc  mov     edx, 560000h; dwIoControlCode
0x18001a3e1  mov     rcx, rbx; hDevice
0x18001a3e4  call    cs:__imp_DeviceIoControl
0x18001a3ea  test    eax, eax
0x18001a3ec  jnz     short loc_18001A40E
0x18001a3ee  mov     rcx, [rbp+2B8h]; this
0x18001a3f5  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001a3fc  mov     edx, 5EAh; void *
0x18001a401  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a406  nop
0x18001a407  mov     ebx, eax
0x18001a409  jmp     loc_18001A4E8
0x18001a40e  mov     eax, [rbp+2B0h+var_318]
0x18001a411  cmp     eax, 0FFFFFFFFh
0x18001a414  jnz     loc_18001A4A3
0x18001a41a  xor     edx, edx; Val
0x18001a41c  lea     r8d, [rdx+40h]; Size
0x18001a420  lea     rcx, [rsp+3B0h+var_360]; void *
0x18001a425  call    memset_0
0x18001a42a  mov     [rsp+3B0h+lpOverlapped], r15; lpOverlapped
0x18001a42f  lea     rax, [rsp+3B0h+BytesReturned]
0x18001a434  mov     [rsp+3B0h+hTemplateFile], rax; lpBytesReturned
0x18001a439  mov     [rsp+3B0h+dwFlagsAndAttributes], 40h ; '@'; nOutBufferSize
0x18001a441  lea     rax, [rsp+3B0h+var_360]
0x18001a446  mov     qword ptr [rsp+3B0h+dwCreationDisposition], rax; int
0x18001a44b  xor     r9d, r9d; nInBufferSize
0x18001a44e  xor     r8d, r8d; lpInBuffer
0x18001a451  mov     edx, 240008h; dwIoControlCode
0x18001a456  mov     rcx, rbx; hDevice
0x18001a459  call    cs:__imp_DeviceIoControl
0x18001a45f  test    eax, eax
0x18001a461  jnz     short loc_18001A47E
0x18001a463  mov     rcx, [rbp+2B8h]; this
0x18001a46a  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001a471  mov     edx, 5FAh; void *
0x18001a476  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a47b  nop
0x18001a47c  jmp     short loc_18001A407
0x18001a47e  cmp     [rsp+3B0h+var_34C], 3
0x18001a483  jnz     short loc_18001A4C7
0x18001a485  mov     r8d, 10h; Size
0x18001a48b  lea     rdx, RamdiskBootDiskGuid; Buf2
0x18001a492  lea     rcx, [rsp+3B0h+Buf1]; Buf1
0x18001a497  call    memcmp_0
0x18001a49c  test    eax, eax
0x18001a49e  jnz     short loc_18001A4C7
0x18001a4a0  mov     eax, [rbp+2B0h+var_318]
0x18001a4a3  test    rsi, rsi
0x18001a4a6  jz      short loc_18001A4AA
0x18001a4a8  mov     [rsi], eax
0x18001a4aa  test    rdi, rdi
0x18001a4ad  jz      short loc_18001A4B6
0x18001a4af  mov     rax, [rbp+2B0h+var_310]
0x18001a4b3  mov     [rdi], rax
0x18001a4b6  lea     rcx, [rsp+3B0h+var_368]
0x18001a4bb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a4c0  xor     eax, eax
0x18001a4c2  jmp     loc_18001A308
0x18001a4c7  mov     rcx, [rbp+2B8h]; this
0x18001a4ce  mov     ebx, 80070490h
0x18001a4d3  mov     r9d, ebx; char *
0x18001a4d6  lea     r8, aOnecoreDrivers_15; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001a4dd  mov     edx, 5FFh; void *
0x18001a4e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4e7  nop
0x18001a4e8  lea     rcx, [rsp+3B0h+var_368]
0x18001a4ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a4f2  mov     eax, ebx
0x18001a4f4  jmp     loc_18001A308
0x18001a4f9  call    __report_rangecheckfailure
```
