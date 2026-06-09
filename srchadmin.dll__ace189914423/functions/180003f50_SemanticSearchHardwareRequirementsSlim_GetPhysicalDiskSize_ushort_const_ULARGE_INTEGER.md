# SemanticSearchHardwareRequirementsSlim::GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x180003f50`
- end: `0x180004205`
- name: `?GetPhysicalDiskSize@SemanticSearchHardwareRequirementsSlim@@CAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18002b4a0`

## callees

- `0x180003f50`
- `0x18000433c`
- `0x180004fdc`
- `0x180005130`
- `0x180005cc0`
- `0x1800061b0`
- `0x18000687c`
- `0x180010c18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000410b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000410b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800040b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800040b2`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180003fc8`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180003fc8`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004038`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004038`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003ffb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003ffb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004166`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004166`

## pseudocode

```c
signed int __fastcall SemanticSearchHardwareRequirementsSlim::GetPhysicalDiskSize(
        WCHAR *lpszFileName,
        union _ULARGE_INTEGER *a2)
{
  WCHAR *v4; // rcx
  wil::details *v5; // rcx
  signed int result; // eax
  unsigned __int64 v7; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  unsigned int LastErrorFailHr; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v12; // rdi
  wil::details *v13; // rcx
  HANDLE v14; // rax
  unsigned __int64 v15; // rcx
  ULONGLONG QuadPart; // rdx
  __int64 v17; // rax
  HANDLE v18; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned[6]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Buffer[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  a2->QuadPart = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(szVolumePathName, 0, 0x208u);
  if ( lpszFileName )
  {
    v4 = lpszFileName;
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
    v4 = Buffer;
  }
  if ( !GetVolumePathNameW(v4, szVolumePathName, 0x104u)
    || !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    return wil::details::GetLastErrorFailHr(v5);
  }
  v20 = 0;
  result = StringCchLengthW(szVolumeName, 0x104u, &v20);
  if ( result >= 0 )
  {
    if ( v20 && *((_WORD *)&BytesReturned[5] + v20 + 1) == 92 )
    {
      v7 = 2 * v20 - 2;
      if ( v7 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)szVolumeName + v7) = 0;
    }
    FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
    v20 = (unsigned __int64)FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      LastErrorFailHr = LastError;
      if ( LastError > 0 )
        LastErrorFailHr = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_23;
    }
    BytesReturned[0] = 0;
    ProcessHeap = GetProcessHeap();
    v12 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x48C0u);
    if ( !v12 )
    {
      LastErrorFailHr = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\SemanticSearchHardwareRequirementsSlim.h",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
LABEL_23:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      return LastErrorFailHr;
    }
    if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v12, 0x48C0u, BytesReturned, 0) )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v12);
      goto LABEL_23;
    }
    v15 = 0;
    if ( v12[1] )
    {
      QuadPart = a2->QuadPart;
      do
      {
        v17 = 9 * v15++;
        QuadPart += *(_QWORD *)&v12[4 * v17 + 16];
        a2->QuadPart = QuadPart;
      }
      while ( v15 < v12[1] );
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v12);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003f50  mov     [rsp-8+arg_10], rbx
0x180003f55  mov     [rsp-8+arg_18], rsi
0x180003f5a  push    rbp
0x180003f5b  push    rdi
0x180003f5c  push    r15
0x180003f5e  lea     rbp, [rsp-5A0h]
0x180003f66  sub     rsp, 6A0h
0x180003f6d  mov     rax, cs:__security_cookie
0x180003f74  xor     rax, rsp
0x180003f77  mov     [rbp+5B0h+var_20], rax
0x180003f7e  mov     rsi, rdx
0x180003f81  mov     qword ptr [rdx], 0
0x180003f88  mov     rdi, rcx
0x180003f8b  mov     r15d, 208h
0x180003f91  mov     r8d, r15d; Size
0x180003f94  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x180003f99  xor     edx, edx; Val
0x180003f9b  call    memset_0
0x180003fa0  mov     r8d, r15d; Size
0x180003fa3  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x180003faa  xor     edx, edx; Val
0x180003fac  call    memset_0
0x180003fb1  test    rdi, rdi
0x180003fb4  jz      short loc_180003FDC
0x180003fb6  mov     ebx, 104h
0x180003fbb  mov     rcx, rdi; lpszFileName
0x180003fbe  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x180003fc5  mov     r8d, ebx; cchBufferLength
0x180003fc8  call    cs:__imp_GetVolumePathNameW
0x180003fce  test    eax, eax
0x180003fd0  jnz     short loc_180004029
0x180003fd2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fd7  jmp     loc_1800041DE
0x180003fdc  mov     r8, r15; Size
0x180003fdf  lea     rcx, [rbp+5B0h+Buffer]; void *
0x180003fe6  xor     edx, edx; Val
0x180003fe8  call    memset_0
0x180003fed  mov     ebx, 104h
0x180003ff2  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x180003ff9  mov     edx, ebx; uSize
0x180003ffb  call    cs:__imp_GetSystemDirectoryW
0x180004001  test    eax, eax
0x180004003  jnz     short loc_180004020
0x180004005  call    cs:__imp_GetLastError
0x18000400b  test    eax, eax
0x18000400d  jle     loc_1800041DE
0x180004013  movzx   eax, ax
0x180004016  or      eax, 80070000h
0x18000401b  jmp     loc_1800041DE
0x180004020  lea     rcx, [rbp+5B0h+Buffer]
0x180004027  jmp     short loc_180003FBE
0x180004029  mov     r8d, ebx; cchBufferLength
0x18000402c  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x180004031  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x180004038  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000403e  test    eax, eax
0x180004040  jz      short loc_180003FD2
0x180004042  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x180004047  mov     [rsp+6B0h+var_670], 0
0x180004050  mov     rdx, rbx; unsigned __int64
0x180004053  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x180004058  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000405d  test    eax, eax
0x18000405f  js      loc_1800041DE
0x180004065  mov     rax, [rsp+6B0h+var_670]
0x18000406a  test    rax, rax
0x18000406d  jz      short loc_18000408B
0x18000406f  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x180004075  jnz     short loc_18000408B
0x180004077  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000407f  cmp     rcx, r15
0x180004082  jnb     short loc_1800040E9
0x180004084  xor     eax, eax
0x180004086  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x18000408b  xor     r9d, r9d; lpSecurityAttributes
0x18000408e  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x180004097  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000409f  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x1800040a4  xor     edx, edx; dwDesiredAccess
0x1800040a6  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x1800040ae  lea     r8d, [r9+1]; dwShareMode
0x1800040b2  call    cs:__imp_CreateFileW
0x1800040b8  mov     rbx, rax
0x1800040bb  mov     [rsp+6B0h+var_670], rax
0x1800040c0  inc     rax
0x1800040c3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800040c9  jnz     short loc_1800040EF
0x1800040cb  call    cs:__imp_GetLastError
0x1800040d1  mov     ebx, eax
0x1800040d3  test    eax, eax
0x1800040d5  jle     loc_18000418B
0x1800040db  movzx   ebx, ax
0x1800040de  or      ebx, 80070000h
0x1800040e4  jmp     loc_18000418B
0x1800040e9  call    __report_rangecheckfailure
0x1800040ef  mov     [rsp+6B0h+BytesReturned], 0
0x1800040f7  call    cs:__imp_GetProcessHeap
0x1800040fd  mov     r15d, 48C0h
0x180004103  xor     edx, edx; dwFlags
0x180004105  mov     rcx, rax; hHeap
0x180004108  mov     r8d, r15d; dwBytes
0x18000410b  call    cs:__imp_HeapAlloc
0x180004111  mov     rdi, rax
0x180004114  test    rax, rax
0x180004117  jnz     short loc_18000413B
0x180004119  mov     rcx, [rbp+5B8h]; this
0x180004120  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\Semant"...
0x180004127  mov     ebx, 8007000Eh
0x18000412c  mov     edx, 161h; void *
0x180004131  mov     r9d, ebx; char *
0x180004134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004139  jmp     short loc_18000418B
0x18000413b  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x180004144  lea     rax, [rsp+6B0h+BytesReturned]
0x180004149  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x18000414e  xor     r9d, r9d; nInBufferSize
0x180004151  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180004156  xor     r8d, r8d; lpInBuffer
0x180004159  mov     edx, 70050h; dwIoControlCode
0x18000415e  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x180004163  mov     rcx, rbx; hDevice
0x180004166  call    cs:__imp_DeviceIoControl
0x18000416c  test    eax, eax
0x18000416e  jnz     short loc_180004199
0x180004170  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004175  mov     ebx, eax
0x180004177  call    cs:__imp_GetProcessHeap
0x18000417d  mov     r8, rdi; lpMem
0x180004180  xor     edx, edx; dwFlags
0x180004182  mov     rcx, rax; hHeap
0x180004185  call    cs:__imp_HeapFree
0x18000418b  lea     rcx, [rsp+6B0h+var_670]
0x180004190  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004195  mov     eax, ebx
0x180004197  jmp     short loc_1800041DE
0x180004199  xor     ecx, ecx
0x18000419b  cmp     [rdi+4], ecx
0x18000419e  jbe     short loc_1800041BE
0x1800041a0  mov     rdx, [rsi]
0x1800041a3  lea     rax, [rcx+rcx*8]
0x1800041a7  inc     rcx
0x1800041aa  shl     rax, 4
0x1800041ae  add     rdx, [rax+rdi+40h]
0x1800041b3  mov     [rsi], rdx
0x1800041b6  mov     eax, [rdi+4]
0x1800041b9  cmp     rcx, rax
0x1800041bc  jb      short loc_1800041A3
0x1800041be  call    cs:__imp_GetProcessHeap
0x1800041c4  mov     r8, rdi; lpMem
0x1800041c7  xor     edx, edx; dwFlags
0x1800041c9  mov     rcx, rax; hHeap
0x1800041cc  call    cs:__imp_HeapFree
0x1800041d2  lea     rcx, [rsp+6B0h+var_670]
0x1800041d7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800041dc  xor     eax, eax
0x1800041de  mov     rcx, [rbp+5B0h+var_20]
0x1800041e5  xor     rcx, rsp; StackCookie
0x1800041e8  call    __security_check_cookie
0x1800041ed  lea     r11, [rsp+6B0h+var_10]
0x1800041f5  mov     rbx, [r11+30h]
0x1800041f9  mov     rsi, [r11+38h]
0x1800041fd  mov     rsp, r11
0x180004200  pop     r15
0x180004202  pop     rdi
0x180004203  pop     rbp
0x180004204  retn
```
