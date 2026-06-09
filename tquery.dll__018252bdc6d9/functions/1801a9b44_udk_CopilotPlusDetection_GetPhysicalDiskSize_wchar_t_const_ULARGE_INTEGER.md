# udk::CopilotPlusDetection::_GetPhysicalDiskSize(wchar_t const *,_ULARGE_INTEGER *)

- ea: `0x1801a9b44`
- end: `0x1801a9e6a`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEB_WPEAT_ULARGE_INTEGER@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const wchar_t *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1801a7f98`

## callees

- `0x180078410`
- `0x1800983c0`
- `0x1800db68c`
- `0x180147170`
- `0x180188d90`
- `0x1801895a0`
- `0x180189cce`
- `0x1801a9b44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a9d56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a9d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a9de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a9e2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a9de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a9e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9d42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9e1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9d42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9d1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801a9c05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801a9c05`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a9bbc`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a9c3b`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a9bbc`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a9c3b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a9d03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a9d03`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a9db1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a9db1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801a9c5b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801a9c5b`

## pseudocode

```c
signed int __fastcall udk::CopilotPlusDetection::_GetPhysicalDiskSize(
        LPCWSTR lpszFileName,
        wchar_t *a2,
        union _ULARGE_INTEGER *a3)
{
  const char *v5; // r9
  __int64 v6; // rdx
  signed int result; // eax
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int *v14; // rdi
  const char *v15; // r9
  HANDLE v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  HANDLE v20; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned[6]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Buffer[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  *(_QWORD *)a2 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(szVolumePathName, 0, 0x208u);
  if ( lpszFileName )
  {
    if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
    {
      v6 = 413;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  else
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
    {
      v6 = 423;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 426;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
             v5);
  }
  v23 = 0;
  v8 = StringCchLengthW(szVolumeName, 0x104u, &v23);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
    return v9;
  }
  if ( v23 && *((_WORD *)&BytesReturned[5] + v23 + 1) == 92 )
  {
    v10 = 2 * v23 - 2;
    if ( v10 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v10) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  v23 = (unsigned __int64)FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  BytesReturned[0] = 0;
  ProcessHeap = GetProcessHeap();
  v14 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x48C0u);
  if ( !v14 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_26:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    return v9;
  }
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v14, 0x48C0u, BytesReturned, 0) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1C4,
           (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
           v15);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
    goto LABEL_26;
  }
  v17 = 0;
  if ( v14[1] )
  {
    v18 = *(_QWORD *)a2;
    do
    {
      v19 = 9 * v17++;
      v18 += *(_QWORD *)&v14[4 * v19 + 16];
      *(_QWORD *)a2 = v18;
    }
    while ( v17 < v14[1] );
  }
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x1801a9b44  mov     [rsp-8+arg_10], rbx
0x1801a9b49  mov     [rsp-8+arg_18], rsi
0x1801a9b4e  push    rbp
0x1801a9b4f  push    rdi
0x1801a9b50  push    r15
0x1801a9b52  lea     rbp, [rsp-5A0h]
0x1801a9b5a  sub     rsp, 6A0h
0x1801a9b61  mov     rax, cs:__security_cookie
0x1801a9b68  xor     rax, rsp
0x1801a9b6b  mov     [rbp+5B0h+var_20], rax
0x1801a9b72  mov     rsi, rdx
0x1801a9b75  mov     qword ptr [rdx], 0
0x1801a9b7c  mov     rdi, rcx
0x1801a9b7f  mov     r15d, 208h
0x1801a9b85  mov     r8d, r15d; Size
0x1801a9b88  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x1801a9b8d  xor     edx, edx; Val
0x1801a9b8f  call    memset_0
0x1801a9b94  mov     r8d, r15d; Size
0x1801a9b97  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x1801a9b9e  xor     edx, edx; Val
0x1801a9ba0  call    memset_0
0x1801a9ba5  test    rdi, rdi
0x1801a9ba8  jz      short loc_1801A9BE6
0x1801a9baa  mov     ebx, 104h
0x1801a9baf  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1801a9bb6  mov     r8d, ebx; cchBufferLength
0x1801a9bb9  mov     rcx, rdi; lpszFileName
0x1801a9bbc  call    cs:__imp_GetVolumePathNameW
0x1801a9bc2  test    eax, eax
0x1801a9bc4  jnz     loc_1801A9C4C
0x1801a9bca  lea     edx, [r15-6Bh]; void *
0x1801a9bce  mov     rcx, [rbp+5B8h]; this
0x1801a9bd5  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a9bdc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a9be1  jmp     loc_1801A9E3D
0x1801a9be6  mov     r8, r15; Size
0x1801a9be9  lea     rcx, [rbp+5B0h+Buffer]; void *
0x1801a9bf0  xor     edx, edx; Val
0x1801a9bf2  call    memset_0
0x1801a9bf7  mov     ebx, 104h
0x1801a9bfc  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x1801a9c03  mov     edx, ebx; uSize
0x1801a9c05  call    cs:__imp_GetSystemDirectoryW
0x1801a9c0b  test    eax, eax
0x1801a9c0d  jnz     short loc_1801A9C2A
0x1801a9c0f  call    cs:__imp_GetLastError
0x1801a9c15  test    eax, eax
0x1801a9c17  jle     loc_1801A9E3D
0x1801a9c1d  movzx   eax, ax
0x1801a9c20  or      eax, 80070000h
0x1801a9c25  jmp     loc_1801A9E3D
0x1801a9c2a  mov     r8d, ebx; cchBufferLength
0x1801a9c2d  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1801a9c34  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x1801a9c3b  call    cs:__imp_GetVolumePathNameW
0x1801a9c41  test    eax, eax
0x1801a9c43  jnz     short loc_1801A9C4C
0x1801a9c45  mov     edx, 1A7h
0x1801a9c4a  jmp     short loc_1801A9BCE
0x1801a9c4c  mov     r8d, ebx; cchBufferLength
0x1801a9c4f  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x1801a9c54  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x1801a9c5b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801a9c61  test    eax, eax
0x1801a9c63  jnz     short loc_1801A9C6F
0x1801a9c65  mov     edx, 1AAh
0x1801a9c6a  jmp     loc_1801A9BCE
0x1801a9c6f  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x1801a9c74  mov     [rsp+6B0h+var_670], 0
0x1801a9c7d  mov     rdx, rbx; unsigned __int64
0x1801a9c80  lea     rcx, [rsp+6B0h+szVolumeName]; wchar_t *
0x1801a9c85  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1801a9c8a  mov     ebx, eax
0x1801a9c8c  test    eax, eax
0x1801a9c8e  jns     short loc_1801A9CB2
0x1801a9c90  mov     rcx, [rbp+5B8h]; this
0x1801a9c97  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a9c9e  mov     r9d, eax; char *
0x1801a9ca1  mov     edx, 1AEh; void *
0x1801a9ca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9cab  mov     eax, ebx
0x1801a9cad  jmp     loc_1801A9E3D
0x1801a9cb2  mov     rax, [rsp+6B0h+var_670]
0x1801a9cb7  test    rax, rax
0x1801a9cba  jz      short loc_1801A9CDC
0x1801a9cbc  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x1801a9cc2  jnz     short loc_1801A9CDC
0x1801a9cc4  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1801a9ccc  cmp     rcx, r15
0x1801a9ccf  jnb     loc_1801A9E64
0x1801a9cd5  xor     eax, eax
0x1801a9cd7  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x1801a9cdc  xor     r9d, r9d; lpSecurityAttributes
0x1801a9cdf  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x1801a9ce8  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1801a9cf0  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x1801a9cf5  xor     edx, edx; dwDesiredAccess
0x1801a9cf7  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x1801a9cff  lea     r8d, [r9+1]; dwShareMode
0x1801a9d03  call    cs:__imp_CreateFileW
0x1801a9d09  mov     rbx, rax
0x1801a9d0c  mov     [rsp+6B0h+var_670], rax
0x1801a9d11  inc     rax
0x1801a9d14  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801a9d1a  jnz     short loc_1801A9D3A
0x1801a9d1c  call    cs:__imp_GetLastError
0x1801a9d22  mov     ebx, eax
0x1801a9d24  test    eax, eax
0x1801a9d26  jle     loc_1801A9DE9
0x1801a9d2c  movzx   ebx, ax
0x1801a9d2f  or      ebx, 80070000h
0x1801a9d35  jmp     loc_1801A9DE9
0x1801a9d3a  mov     [rsp+6B0h+BytesReturned], 0
0x1801a9d42  call    cs:__imp_GetProcessHeap
0x1801a9d48  mov     r15d, 48C0h
0x1801a9d4e  xor     edx, edx; dwFlags
0x1801a9d50  mov     rcx, rax; hHeap
0x1801a9d53  mov     r8d, r15d; dwBytes
0x1801a9d56  call    cs:__imp_HeapAlloc
0x1801a9d5c  mov     rdi, rax
0x1801a9d5f  test    rax, rax
0x1801a9d62  jnz     short loc_1801A9D86
0x1801a9d64  mov     rcx, [rbp+5B8h]; this
0x1801a9d6b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a9d72  mov     ebx, 8007000Eh
0x1801a9d77  mov     edx, 1BEh; void *
0x1801a9d7c  mov     r9d, ebx; char *
0x1801a9d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9d84  jmp     short loc_1801A9DE9
0x1801a9d86  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1801a9d8f  lea     rax, [rsp+6B0h+BytesReturned]
0x1801a9d94  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1801a9d99  xor     r9d, r9d; nInBufferSize
0x1801a9d9c  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1801a9da1  xor     r8d, r8d; lpInBuffer
0x1801a9da4  mov     edx, 70050h; dwIoControlCode
0x1801a9da9  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1801a9dae  mov     rcx, rbx; hDevice
0x1801a9db1  call    cs:__imp_DeviceIoControl
0x1801a9db7  test    eax, eax
0x1801a9db9  jnz     short loc_1801A9DF8
0x1801a9dbb  mov     rcx, [rbp+5B8h]; this
0x1801a9dc2  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a9dc9  mov     edx, 1C4h; void *
0x1801a9dce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a9dd3  mov     ebx, eax
0x1801a9dd5  call    cs:__imp_GetProcessHeap
0x1801a9ddb  mov     r8, rdi; lpMem
0x1801a9dde  xor     edx, edx; dwFlags
0x1801a9de0  mov     rcx, rax; hHeap
0x1801a9de3  call    cs:__imp_HeapFree
0x1801a9de9  lea     rcx, [rsp+6B0h+var_670]
0x1801a9dee  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801a9df3  jmp     loc_1801A9CAB
0x1801a9df8  xor     ecx, ecx
0x1801a9dfa  cmp     [rdi+4], ecx
0x1801a9dfd  jbe     short loc_1801A9E1D
0x1801a9dff  mov     rdx, [rsi]
0x1801a9e02  lea     rax, [rcx+rcx*8]
0x1801a9e06  inc     rcx
0x1801a9e09  shl     rax, 4
0x1801a9e0d  add     rdx, [rax+rdi+40h]
0x1801a9e12  mov     [rsi], rdx
0x1801a9e15  mov     eax, [rdi+4]
0x1801a9e18  cmp     rcx, rax
0x1801a9e1b  jb      short loc_1801A9E02
0x1801a9e1d  call    cs:__imp_GetProcessHeap
0x1801a9e23  mov     r8, rdi; lpMem
0x1801a9e26  xor     edx, edx; dwFlags
0x1801a9e28  mov     rcx, rax; hHeap
0x1801a9e2b  call    cs:__imp_HeapFree
0x1801a9e31  lea     rcx, [rsp+6B0h+var_670]
0x1801a9e36  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801a9e3b  xor     eax, eax
0x1801a9e3d  mov     rcx, [rbp+5B0h+var_20]
0x1801a9e44  xor     rcx, rsp; StackCookie
0x1801a9e47  call    __security_check_cookie
0x1801a9e4c  lea     r11, [rsp+6B0h+var_10]
0x1801a9e54  mov     rbx, [r11+30h]
0x1801a9e58  mov     rsi, [r11+38h]
0x1801a9e5c  mov     rsp, r11
0x1801a9e5f  pop     r15
0x1801a9e61  pop     rdi
0x1801a9e62  pop     rbp
0x1801a9e63  retn
0x1801a9e64  call    __report_rangecheckfailure
```
