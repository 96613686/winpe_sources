# CUmRdpPrn::GetPrinterConfigInfo(ushort const *,uchar * *,ulong *)

- ea: `0x180014e4c`
- end: `0x180014fd5`
- name: `?GetPrinterConfigInfo@CUmRdpPrn@@AEAAKPEBGPEAPEAEPEAK@Z`
- size: `393`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017a98`

## callees

- `0x1800090b0`
- `0x18001449c`
- `0x1800146a0`
- `0x180014e4c`
- `0x180015094`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014ef5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014ef5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014ed5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014ed5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014faf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014faf`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014f4d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014f4d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f85`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014f39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014f39`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::GetPrinterConfigInfo(
        void **this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned int UserAcledTempPath; // eax
  unsigned int v9; // r9d
  unsigned __int16 *v10; // rcx
  DWORD TempFile; // ebx
  const unsigned __int16 *v12; // r9
  HANDLE FileW; // rax
  void *v14; // rdi
  DWORD FileSize; // ebx
  unsigned __int8 *v16; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v20[264]; // [rsp+260h] [rbp-248h] BYREF

  *a4 = 0;
  NumberOfBytesRead = 0;
  UserAcledTempPath = GetUserAcledTempPath(this[23], (unsigned int)a2, v20);
  v10 = v20;
  if ( UserAcledTempPath - 1 > 0x103 )
    v10 = L".";
  TempFile = CreateTempFile(v10, this[23], FileName, v9);
  if ( !TempFile )
  {
    if ( !ImpersonateLoggedOnUser(this[23]) )
      goto LABEL_14;
    TempFile = CUmRdpPrn::CallPrintUiPersistFunc((CUmRdpPrn *)this, a2, FileName, v12);
    if ( !RevertToSelf() )
      TempFile = GetLastError();
    if ( TempFile )
      goto LABEL_15;
    FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v14 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_14:
      TempFile = GetLastError();
    }
    else
    {
      FileSize = GetFileSize(FileW, 0);
      v16 = (unsigned __int8 *)ALLOCMEM(FileSize);
      *a3 = v16;
      if ( v16 && ReadFile(v14, v16, FileSize, &NumberOfBytesRead, 0) )
      {
        TempFile = 0;
        *a4 = NumberOfBytesRead;
      }
      else
      {
        TempFile = GetLastError();
      }
      CloseHandle(v14);
    }
LABEL_15:
    DeleteFileW(FileName);
  }
  return TempFile;
}

```

## disassembly

```asm
0x180014e4c  push    rbx
0x180014e4e  push    rbp
0x180014e4f  push    rsi
0x180014e50  push    rdi
0x180014e51  push    r14
0x180014e53  sub     rsp, 480h
0x180014e5a  mov     rax, cs:__security_cookie
0x180014e61  xor     rax, rsp
0x180014e64  mov     [rsp+4A8h+var_38], rax
0x180014e6c  mov     r14, r8
0x180014e6f  mov     dword ptr [r9], 0
0x180014e76  mov     rdi, rcx
0x180014e79  mov     [rsp+4A8h+NumberOfBytesRead], 0
0x180014e81  mov     rcx, [rcx+0B8h]; void *
0x180014e88  lea     r8, [rsp+4A8h+var_248]; unsigned __int16 *
0x180014e90  mov     rsi, r9
0x180014e93  mov     rbp, rdx
0x180014e96  call    ?GetUserAcledTempPath@@YAKPEAXKPEAG@Z; GetUserAcledTempPath(void *,ulong,ushort *)
0x180014e9b  mov     rdx, [rdi+0B8h]; void *
0x180014ea2  lea     r8, [rsp+4A8h+FileName]; unsigned __int16 *
0x180014ea7  dec     eax
0x180014ea9  lea     rcx, [rsp+4A8h+var_248]
0x180014eb1  cmp     eax, 103h
0x180014eb6  jbe     short loc_180014EBF
0x180014eb8  lea     rcx, asc_18004E468; "."
0x180014ebf  call    ?CreateTempFile@@YAKPEAGPEAX0K@Z; CreateTempFile(ushort *,void *,ushort *,ulong)
0x180014ec4  mov     ebx, eax
0x180014ec6  test    eax, eax
0x180014ec8  jnz     loc_180014FB5
0x180014ece  mov     rcx, [rdi+0B8h]; hToken
0x180014ed5  call    cs:__imp_ImpersonateLoggedOnUser
0x180014edb  test    eax, eax
0x180014edd  jz      loc_180014FA2
0x180014ee3  lea     r8, [rsp+4A8h+FileName]; unsigned __int16 *
0x180014ee8  mov     rdx, rbp; unsigned __int16 *
0x180014eeb  mov     rcx, rdi; this
0x180014eee  call    ?CallPrintUiPersistFunc@CUmRdpPrn@@AEAAKPEBG00@Z; CUmRdpPrn::CallPrintUiPersistFunc(ushort const *,ushort const *,ushort const *)
0x180014ef3  mov     ebx, eax
0x180014ef5  call    cs:__imp_RevertToSelf
0x180014efb  test    eax, eax
0x180014efd  jnz     short loc_180014F07
0x180014eff  call    cs:__imp_GetLastError
0x180014f05  mov     ebx, eax
0x180014f07  test    ebx, ebx
0x180014f09  jnz     loc_180014FAA
0x180014f0f  mov     [rsp+4A8h+hTemplateFile], 0; hTemplateFile
0x180014f18  lea     r8d, [rbx+1]; dwShareMode
0x180014f1c  mov     [rsp+4A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014f24  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x180014f29  xor     r9d, r9d; lpSecurityAttributes
0x180014f2c  mov     [rsp+4A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180014f34  mov     edx, 80000000h; dwDesiredAccess
0x180014f39  call    cs:__imp_CreateFileW
0x180014f3f  mov     rdi, rax
0x180014f42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014f46  jz      short loc_180014FA2
0x180014f48  xor     edx, edx; lpFileSizeHigh
0x180014f4a  mov     rcx, rax; hFile
0x180014f4d  call    cs:__imp_GetFileSize
0x180014f53  mov     ecx, eax; dwBytes
0x180014f55  mov     ebx, eax
0x180014f57  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180014f5c  mov     [r14], rax
0x180014f5f  test    rax, rax
0x180014f62  jnz     short loc_180014F6E
0x180014f64  call    cs:__imp_GetLastError
0x180014f6a  mov     ebx, eax
0x180014f6c  jmp     short loc_180014F97
0x180014f6e  lea     r9, [rsp+4A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180014f73  mov     qword ptr [rsp+4A8h+dwCreationDisposition], 0; lpOverlapped
0x180014f7c  mov     r8d, ebx; nNumberOfBytesToRead
0x180014f7f  mov     rdx, rax; lpBuffer
0x180014f82  mov     rcx, rdi; hFile
0x180014f85  call    cs:__imp_ReadFile
0x180014f8b  test    eax, eax
0x180014f8d  jz      short loc_180014F64
0x180014f8f  mov     eax, [rsp+4A8h+NumberOfBytesRead]
0x180014f93  xor     ebx, ebx
0x180014f95  mov     [rsi], eax
0x180014f97  mov     rcx, rdi; hObject
0x180014f9a  call    cs:__imp_CloseHandle
0x180014fa0  jmp     short loc_180014FAA
0x180014fa2  call    cs:__imp_GetLastError
0x180014fa8  mov     ebx, eax
0x180014faa  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x180014faf  call    cs:__imp_DeleteFileW
0x180014fb5  mov     eax, ebx
0x180014fb7  mov     rcx, [rsp+4A8h+var_38]
0x180014fbf  xor     rcx, rsp; StackCookie
0x180014fc2  call    __security_check_cookie
0x180014fc7  add     rsp, 480h
0x180014fce  pop     r14
0x180014fd0  pop     rdi
0x180014fd1  pop     rsi
0x180014fd2  pop     rbp
0x180014fd3  pop     rbx
0x180014fd4  retn
```
