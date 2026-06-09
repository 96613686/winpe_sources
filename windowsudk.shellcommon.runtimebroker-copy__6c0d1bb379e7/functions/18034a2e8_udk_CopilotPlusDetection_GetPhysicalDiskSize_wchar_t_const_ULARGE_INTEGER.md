# udk::CopilotPlusDetection::_GetPhysicalDiskSize(wchar_t const *,_ULARGE_INTEGER *)

- ea: `0x18034a2e8`
- end: `0x18034a60a`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEB_WPEAT_ULARGE_INTEGER@@@Z`
- size: `802`
- prototype: `signed int __fastcall(LPCWSTR lpszFileName, wchar_t *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180349628`

## callees

- `0x1800773fc`
- `0x1800a14f8`
- `0x1800e2988`
- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d500`
- `0x18015d868`
- `0x18034a2e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a4e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a57b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a5c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a4e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a57b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18034a5c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18034a4fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18034a4fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18034a589`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18034a5d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18034a589`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18034a5d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034a3b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034a4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034a3b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034a4bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18034a3a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18034a3a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18034a4a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18034a4a3`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18034a360`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18034a3df`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18034a360`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18034a3df`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18034a3ff`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18034a3ff`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18034a557`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18034a557`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
    goto LABEL_27;
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
LABEL_27:
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
    goto LABEL_27;
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
0x18034a2e8  mov     [rsp-8+arg_10], rbx
0x18034a2ed  mov     [rsp-8+arg_18], rsi
0x18034a2f2  push    rbp
0x18034a2f3  push    rdi
0x18034a2f4  push    r15
0x18034a2f6  lea     rbp, [rsp-5A0h]
0x18034a2fe  sub     rsp, 6A0h
0x18034a305  mov     rax, cs:__security_cookie
0x18034a30c  xor     rax, rsp
0x18034a30f  mov     [rbp+5B0h+var_20], rax
0x18034a316  mov     rsi, rdx
0x18034a319  mov     qword ptr [rdx], 0
0x18034a320  mov     rdi, rcx
0x18034a323  mov     r15d, 208h
0x18034a329  mov     r8d, r15d; Size
0x18034a32c  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x18034a331  xor     edx, edx; Val
0x18034a333  call    memset_0
0x18034a338  mov     r8d, r15d; Size
0x18034a33b  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x18034a342  xor     edx, edx; Val
0x18034a344  call    memset_0
0x18034a349  test    rdi, rdi
0x18034a34c  jz      short loc_18034A38A
0x18034a34e  mov     ebx, 104h
0x18034a353  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18034a35a  mov     r8d, ebx; cchBufferLength
0x18034a35d  mov     rcx, rdi; lpszFileName
0x18034a360  call    cs:__imp_GetVolumePathNameW
0x18034a366  test    eax, eax
0x18034a368  jnz     loc_18034A3F0
0x18034a36e  lea     edx, [r15-6Bh]; void *
0x18034a372  mov     rcx, [rbp+5B8h]; this
0x18034a379  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18034a380  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18034a385  jmp     loc_18034A5E3
0x18034a38a  mov     r8, r15; Size
0x18034a38d  lea     rcx, [rbp+5B0h+Buffer]; void *
0x18034a394  xor     edx, edx; Val
0x18034a396  call    memset_0
0x18034a39b  mov     ebx, 104h
0x18034a3a0  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18034a3a7  mov     edx, ebx; uSize
0x18034a3a9  call    cs:__imp_GetSystemDirectoryW
0x18034a3af  test    eax, eax
0x18034a3b1  jnz     short loc_18034A3CE
0x18034a3b3  call    cs:__imp_GetLastError
0x18034a3b9  test    eax, eax
0x18034a3bb  jle     loc_18034A5E3
0x18034a3c1  movzx   eax, ax
0x18034a3c4  or      eax, 80070000h
0x18034a3c9  jmp     loc_18034A5E3
0x18034a3ce  mov     r8d, ebx; cchBufferLength
0x18034a3d1  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18034a3d8  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x18034a3df  call    cs:__imp_GetVolumePathNameW
0x18034a3e5  test    eax, eax
0x18034a3e7  jnz     short loc_18034A3F0
0x18034a3e9  mov     edx, 1A7h
0x18034a3ee  jmp     short loc_18034A372
0x18034a3f0  mov     r8d, ebx; cchBufferLength
0x18034a3f3  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18034a3f8  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x18034a3ff  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18034a405  test    eax, eax
0x18034a407  jnz     short loc_18034A413
0x18034a409  mov     edx, 1AAh
0x18034a40e  jmp     loc_18034A372
0x18034a413  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x18034a418  mov     [rsp+6B0h+var_670], 0
0x18034a421  mov     rdx, rbx; unsigned __int64
0x18034a424  lea     rcx, [rsp+6B0h+szVolumeName]; wchar_t *
0x18034a429  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18034a42e  mov     ebx, eax
0x18034a430  test    eax, eax
0x18034a432  jns     short loc_18034A456
0x18034a434  mov     rcx, [rbp+5B8h]; this
0x18034a43b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18034a442  mov     r9d, eax; char *
0x18034a445  mov     edx, 1AEh; void *
0x18034a44a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034a44f  mov     eax, ebx
0x18034a451  jmp     loc_18034A5E3
0x18034a456  mov     rax, [rsp+6B0h+var_670]
0x18034a45b  test    rax, rax
0x18034a45e  jz      short loc_18034A47C
0x18034a460  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x18034a466  jnz     short loc_18034A47C
0x18034a468  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18034a470  cmp     rcx, r15
0x18034a473  jnb     short loc_18034A4DA
0x18034a475  xor     eax, eax
0x18034a477  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x18034a47c  xor     r9d, r9d; lpSecurityAttributes
0x18034a47f  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x18034a488  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18034a490  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x18034a495  xor     edx, edx; dwDesiredAccess
0x18034a497  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x18034a49f  lea     r8d, [r9+1]; dwShareMode
0x18034a4a3  call    cs:__imp_CreateFileW
0x18034a4a9  mov     rbx, rax
0x18034a4ac  mov     [rsp+6B0h+var_670], rax
0x18034a4b1  inc     rax
0x18034a4b4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18034a4ba  jnz     short loc_18034A4E0
0x18034a4bc  call    cs:__imp_GetLastError
0x18034a4c2  mov     ebx, eax
0x18034a4c4  test    eax, eax
0x18034a4c6  jle     loc_18034A58F
0x18034a4cc  movzx   ebx, ax
0x18034a4cf  or      ebx, 80070000h
0x18034a4d5  jmp     loc_18034A58F
0x18034a4da  call    __report_rangecheckfailure
0x18034a4e0  mov     [rsp+6B0h+BytesReturned], 0
0x18034a4e8  call    cs:__imp_GetProcessHeap
0x18034a4ee  mov     r15d, 48C0h
0x18034a4f4  xor     edx, edx; dwFlags
0x18034a4f6  mov     rcx, rax; hHeap
0x18034a4f9  mov     r8d, r15d; dwBytes
0x18034a4fc  call    cs:__imp_HeapAlloc
0x18034a502  mov     rdi, rax
0x18034a505  test    rax, rax
0x18034a508  jnz     short loc_18034A52C
0x18034a50a  mov     rcx, [rbp+5B8h]; this
0x18034a511  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18034a518  mov     ebx, 8007000Eh
0x18034a51d  mov     edx, 1BEh; void *
0x18034a522  mov     r9d, ebx; char *
0x18034a525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034a52a  jmp     short loc_18034A58F
0x18034a52c  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x18034a535  lea     rax, [rsp+6B0h+BytesReturned]
0x18034a53a  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x18034a53f  xor     r9d, r9d; nInBufferSize
0x18034a542  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18034a547  xor     r8d, r8d; lpInBuffer
0x18034a54a  mov     edx, 70050h; dwIoControlCode
0x18034a54f  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x18034a554  mov     rcx, rbx; hDevice
0x18034a557  call    cs:__imp_DeviceIoControl
0x18034a55d  test    eax, eax
0x18034a55f  jnz     short loc_18034A59E
0x18034a561  mov     rcx, [rbp+5B8h]; this
0x18034a568  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18034a56f  mov     edx, 1C4h; void *
0x18034a574  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18034a579  mov     ebx, eax
0x18034a57b  call    cs:__imp_GetProcessHeap
0x18034a581  mov     r8, rdi; lpMem
0x18034a584  xor     edx, edx; dwFlags
0x18034a586  mov     rcx, rax; hHeap
0x18034a589  call    cs:__imp_HeapFree
0x18034a58f  lea     rcx, [rsp+6B0h+var_670]
0x18034a594  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18034a599  jmp     loc_18034A44F
0x18034a59e  xor     ecx, ecx
0x18034a5a0  cmp     [rdi+4], ecx
0x18034a5a3  jbe     short loc_18034A5C3
0x18034a5a5  mov     rdx, [rsi]
0x18034a5a8  lea     rax, [rcx+rcx*8]
0x18034a5ac  inc     rcx
0x18034a5af  shl     rax, 4
0x18034a5b3  add     rdx, [rax+rdi+40h]
0x18034a5b8  mov     [rsi], rdx
0x18034a5bb  mov     eax, [rdi+4]
0x18034a5be  cmp     rcx, rax
0x18034a5c1  jb      short loc_18034A5A8
0x18034a5c3  call    cs:__imp_GetProcessHeap
0x18034a5c9  mov     r8, rdi; lpMem
0x18034a5cc  xor     edx, edx; dwFlags
0x18034a5ce  mov     rcx, rax; hHeap
0x18034a5d1  call    cs:__imp_HeapFree
0x18034a5d7  lea     rcx, [rsp+6B0h+var_670]
0x18034a5dc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18034a5e1  xor     eax, eax
0x18034a5e3  mov     rcx, [rbp+5B0h+var_20]
0x18034a5ea  xor     rcx, rsp; StackCookie
0x18034a5ed  call    __security_check_cookie
0x18034a5f2  lea     r11, [rsp+6B0h+var_10]
0x18034a5fa  mov     rbx, [r11+30h]
0x18034a5fe  mov     rsi, [r11+38h]
0x18034a602  mov     rsp, r11
0x18034a605  pop     r15
0x18034a607  pop     rdi
0x18034a608  pop     rbp
0x18034a609  retn
```
